---
title: "Requirements & Preparation"
date: 2026-07-07
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# Section 5.2 - System & Environment Requirements

To deploy and operate the **AI AWS Advisor** system, the development environment and AWS account must meet the following prerequisites.

---

## 1. AWS Account & Service Permission Requirements

- **AWS Account:** Administrator access (`AdministratorAccess`) is required.
- **Amazon Bedrock Model Access:**
  - The `Claude 3 Haiku` model must be enabled in the `us-east-1` or `ap-southeast-1` region via the AWS Console (**Bedrock -> Model access -> Request access**).
  - Model ID / ARN: `anthropic.claude-3-haiku-20240307-v1:0`.
  - **Important note for Anthropic models:** Bedrock requires you to submit a **Use Case Details form** (company name, website, industry, use case description) once through the Chat/Text Playground before the first API call. After Anthropic approves it (usually within 24 hours), the model becomes callable. If you see the message *"Your account is not authorized to perform this action"*, this is the reason — you need to submit this form.
  - **Alternative (no approval needed):** Change the Model ID in `template.yaml` to `amazon.nova-lite-v1:0` — Amazon's first-party models do not require Anthropic's manual approval step.
- **AWS CLI v2:** Installed and configured (`aws configure`).

**Figure - `aws configure` setup and verification via `aws sts get-caller-identity`:**

![AWS CLI Configure](/images/5-Workshop/5.2-Prerequisite/aws_cli_configure.png)

**Figure 1 - Amazon Bedrock Model Access page — the entire Anthropic Claude 3 family has been granted access (Access granted status in the `us-east-1` region):**

![Amazon Bedrock Model Access](/images/5-Workshop/5.2-Prerequisite/bedrock_model_access.png)

> **Verification note:** This screenshot was taken from the workshop author's AWS account at the time of publication. If your console shows *"Not available"* or *"Access denied"* for any Anthropic model, open the **Bedrock Chat/Text Playground** once and submit the **Use Case form** (company name, website, industry, target audience, use case description). Anthropic typically approves within 24 hours. Alternatively, simply switch the Model ID in `template.yaml` to `amazon.nova-lite-v1:0` — no manual approval step required.

---

## 2. Toolchain Verification

Before deploying, run the commands below in PowerShell / Terminal and compare the output with the recommended versions:

**Figure 2 - Toolchain version check: `aws / sam / python / node / docker`:**

![Toolchain Verification](/images/5-Workshop/5.2-Prerequisite/toolchain_check.png)

```bash
# Check tool versions
aws --version
sam --version
python --version
node --version
docker --version
```

If any command returns *"command not found"*, install the missing tool before continuing:
- **AWS CLI:** Download from [AWS CLI v2 installer](https://awscli.amazonaws.com/AWSCLIV2.msi).
- **AWS SAM CLI:** `pip install aws-sam-cli` or download from [AWS SAM CLI releases](https://github.com/aws/aws-sam-cli/releases).
- **Docker Desktop:** Install from [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/) (requires WSL 2 backend).
- **Python:** From [python.org](https://www.python.org/downloads/) (check **"Add to PATH"** during installation).
- **Node.js:** From [nodejs.org](https://nodejs.org/) (LTS 20.x recommended).

---

## 3. Serverless Backend Tools

- **AWS SAM CLI:** Toolset for packaging and deploying infrastructure as code (IaC - `template.yaml`).
- **Python 3.12+:** The main programming language for API Handlers and the AI Analyzer on AWS Lambda.
- **Docker Desktop:** Required by SAM CLI (`sam build --use-container`) to compile source code compatible with Lambda's Amazon Linux 2023 environment.

---

## 4. Frontend Tools & Environment Emulation

- **Node.js (v20.0 or later):** Runtime environment for React 19 / Vite 8. (Vite 8 requires Node 20+; the older Node 18 will fail when installing dependencies.)
- **npm / pnpm / yarn:** Node.js package manager.
- **DynamoDB Local:** Offline DynamoDB emulation via Docker Compose (`amazon/dynamodb-local`) for development without touching the real cloud database.

Refer back to **§2 Toolchain Verification** above — the same commands (`aws --version`, `sam --version`, `python --version`, `node --version`, `docker --version`) already confirmed that all tools listed in this section are installed.

---

## 5. Python Backend Libraries

The backend declares all Python packages in `backend/requirements.txt`. The most important libraries are:

| Library | Purpose |
|---|---|
| `boto3` | AWS SDK for Python (DynamoDB, Bedrock, STS, EC2, S3, IAM, CloudWatch) |
| `aws-lambda-powertools` | Structured logging, custom metrics, distributed tracing |
| `pydantic` | Runtime validation for JSON payloads |
| `botocore` | Low-level AWS SDK (bundled with `boto3`) — required for the `STS` and `bedrock-runtime` clients |

{{% notice warning %}}
**Do not commit secrets in `requirements-dev.txt`** to a public Git repo. The `env.json` file (used by SAM via `--parameter-overrides`) contains the alert recipient email and the Bedrock region override — treat it as runtime config, not source code.
{{% /notice %}}

---

## 6. Setting Up the Amazon Cognito User Pool

AI AWS Advisor uses **Amazon Cognito** as its identity provider. The SAM template (`template.yaml`) automatically creates:

- A **User Pool** (`ai-advisor-user-pool`) with `email` as the username attribute and auto-verified email enabled.
- A **User Pool Client** (`ai-advisor-web-client`) supporting the public OAuth flow (`ALLOW_USER_SRP_AUTH`, `ALLOW_USER_PASSWORD_AUTH`, `ALLOW_REFRESH_TOKEN_AUTH`).

After deployment, retrieve the 2 identifiers from the CloudFormation outputs:

```bash
aws cloudformation describe-stacks \
  --stack-name ai-aws-advisor \
  --query 'Stacks[0].Outputs[?OutputKey==`UserPoolId` || OutputKey==`UserPoolClientId`].OutputValue'
```

Create at least 1 Cognito user so the React dashboard can log in:

```bash
aws cognito-idp admin-create-user \
  --user-pool-id <UserPoolId> \
  --username admin@example.com \
  --user-attributes Name=email,Value=admin@example.com Name=email_verified,Value=true \
  --temporary-password "ChangeMe123!" \
  --message-action SUPPRESS
```

The user must change the temporary password on first login.

---

## 7. DynamoDB Local (Offline Development)

To develop locally without touching the cloud database, run **DynamoDB Local** in Docker:

```bash
docker run -d --name dynamodb-local \
  -p 8000:8000 \
  amazon/dynamodb-local:latest \
  -jar DynamoDBLocal.jar -inMemory -sharedDb
```

Then point the Lambda env to local by overriding `DYNAMODB_ENDPOINT_URL`:

```bash
DYNAMODB_ENDPOINT_URL=http://localhost:8000 \
  AWS_ACCESS_KEY_ID=dummy AWS_SECRET_ACCESS_KEY=dummy AWS_DEFAULT_REGION=us-east-1 \
  sam local start-api --env-vars env.json
```

{{% notice info %}}
**In production, `DYNAMODB_ENDPOINT_URL` must be `""`** (empty string). The SAM template defaults to empty, so Lambda will call the real DynamoDB when deployed.
{{% /notice %}}

---

## Section Summary

By completing the steps above, you now have:
- An AWS Administrator account with confirmed Bedrock model access (or the Nova Lite alternative).
- A verified Python/Node/Docker/SAM toolchain.
- A provisioned Cognito User Pool + Client (after the first `sam deploy`).
- An optional DynamoDB Local container for offline iteration.