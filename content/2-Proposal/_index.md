---
title: "Proposal"
date: 2026-06-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


This section provides a summary of the workshop content that is **planned** for implementation.

# AI AWS Advisor

## Cloud Operations Copilot – An AI Assistant for Cloud Engineers & DevOps to Automatically Manage, Analyze, and Optimize AWS Infrastructure

### 1. Executive Summary

**AI AWS Advisor** is an intelligent AWS infrastructure management platform that acts as a **Cloud Operations Copilot** for Cloud Engineers, DevOps Engineers, Solution Architects, System Administrators, and Technical Managers. Instead of opening multiple AWS Console pages to inspect each service individually, users only need to connect their AWS account once using an **IAM Role ARN** (without storing Access Keys).

The system automatically scans the entire AWS infrastructure every hour. AI analyzes the collected data, generates recommendations and security alerts, and presents them on a centralized dashboard. In addition, users can interact with the AI Copilot using natural language (Vietnamese or English) to ask questions about any aspect of their AWS environment.

---

### 2. Problem Statement

#### Current Challenges

Organizations using AWS often face challenges such as:

* Not knowing how many Amazon EC2 instances are running but unused.
* Identifying which Amazon S3 buckets are publicly accessible.
* Detecting IAM Roles with overly permissive policies (such as **AdministratorAccess**).
* Finding AWS Lambda functions that are over-provisioned for their actual workloads.
* Determining which AWS services generate the highest costs.
* Understanding the current security risks across the AWS environment.

Traditionally, answering these questions requires manually navigating through multiple AWS Console services such as Amazon EC2, Amazon S3, AWS IAM, and Amazon CloudWatch before consolidating the information, a process that typically takes **1–2 hours**.

#### Proposed Solution

AI AWS Advisor automatically collects infrastructure data every hour using **Resource Collector Lambda functions** (EC2, S3, IAM, Lambda, and CloudWatch) triggered by **Amazon EventBridge Scheduler**. The collectors securely access the target AWS account using **AWS STS (`sts:AssumeRole`)** and store the collected data in **Amazon DynamoDB**.

The collected information is then analyzed by **Amazon Bedrock (Claude AI)** to generate insights related to security, cost optimization, and performance. The system automatically classifies risks into **Critical, High, Medium,** and **Low** severity levels. Whenever a **Critical** issue is detected, **Amazon SNS** sends an email notification to the user.

Users can also interact directly with the AI Copilot using natural language to ask questions about their AWS infrastructure. The entire process is completed in **less than 30 seconds**, compared to the **1–2 hours** required for manual inspection.

#### Business Value & Return on Investment (ROI)

* **Time Savings:** Reduces manual infrastructure auditing time by more than **90%**, from several days to just a few minutes.
* **Cost Optimization:** Identifies approximately **15–35%** of unnecessary monthly AWS spending.
* **Idle Operating Cost:** Because the platform is built on a **Serverless pay-per-use architecture**, operating costs are almost **USD 0 per month** when there are no incoming requests.

---

### 3. Solution Architecture

The platform is built using an **AWS Serverless architecture**, consisting of the following components:

* **Frontend:** A React Dashboard communicates with the backend through **HTTPS** using **Amazon API Gateway**.

* **Backend:** Amazon API Gateway forwards requests to AWS Lambda functions responsible for business logic, including:

  * Projects API
  * Resources API
  * AI Analyze API

* **Database:** Data is stored in **Amazon DynamoDB**, which contains four tables:

  * `projects`
  * `resources`
  * `insights`
  * `alerts`

* **Resource Collection:** **Amazon EventBridge Scheduler** triggers the following Resource Collector Lambda functions every hour:

  * `ec2_collector`
  * `s3_collector`
  * `iam_collector`
  * `lambda_collector`
  * `cloudwatch_collector`

* **Cross-Account Access:** The Collector Lambda functions use **AWS STS AssumeRole** to securely access target AWS accounts and collect information from:

  * Amazon EC2
  * Amazon S3
  * AWS IAM
  * AWS Lambda
  * Amazon CloudWatch
  * Amazon RDS

* **AI Analysis:** After data collection, the information is sent to **Amazon Bedrock (Claude)** to analyze the infrastructure and generate actionable insights.

* **Notifications:** Whenever a **Critical** risk is detected, **Amazon SNS** automatically sends email notifications to users.

![Architecture](/images/2-Proposal/architecture.png)

#### AWS Services Used

* **AWS Lambda:** Serverless compute service with automatic scaling and a pay-per-use pricing model.
* **Amazon API Gateway:** Fully managed API service with native AWS Lambda integration and built-in authentication support.
* **Amazon DynamoDB:** Serverless NoSQL database offering low latency and a flexible schema suitable for storing data collected from multiple AWS services.
* **Amazon EventBridge:** AWS-native event scheduler with simple cron expressions and high reliability.
* **Amazon Bedrock:** Fully managed generative AI service that provides access to foundation models such as Claude without requiring model hosting.
* **Amazon SNS:** Fully managed messaging service that is simple to integrate with AWS Lambda for notifications.
* **Amazon CloudWatch:** Native AWS monitoring service that automatically collects metrics and stores logs without requiring additional infrastructure.

---

### 4. Technical Implementation

#### Implementation Phases

**Phase 1 – Security & Architecture Design**

* Configure IAM Cross-Account Trust Policies.
* Develop Infrastructure as Code (IaC) templates using **AWS SAM CLI**.
* Design a DynamoDB single-table schema containing `PROJECTS`, `RESOURCES`, `INSIGHTS`, and `ALERTS`.

**Phase 2 – Scanner Development & Amazon Bedrock Integration**

* Develop AWS resource collectors using the **boto3** SDK.
* Design prompt engineering strategies for **Claude 3** on Amazon Bedrock.
* Build automated test suites using **Pytest** and **Moto**.

**Phase 3 – Dashboard & AI Chatbot Development**

* Build the frontend using **React 18**, **Vite**, **Tailwind CSS**, and **Recharts**.
* Integrate the AI Copilot chatbot.
* Perform end-to-end testing and package the solution for deployment using **AWS CloudFormation**.


### 5. Project Roadmap & Milestones

* **Phase 0 – Foundation (Week 1):** Create a sandbox AWS account, set up IAM users for the team, create the GitHub repository, finalize the DynamoDB schema and API contracts, prepare the local development environment, and enable Amazon Bedrock in the AWS Console.

* **Phase 1 – Core Build (Weeks 2–3):** Create DynamoDB tables and IAM Roles for the Resource Collectors; implement EC2, S3, IAM, and Lambda Collectors to store data in DynamoDB; develop the `/projects` and `/resources` APIs; integrate Amazon Bedrock for AI analysis; connect the frontend to the backend APIs and display real data.

* **Phase 2 – Integration (Weeks 3–4):** Configure Amazon EventBridge to trigger the Resource Collectors every hour; automatically analyze collected data using AI after each scan; send Critical risk notifications via Amazon SNS; implement the AI chat endpoint; display AI-generated insights on the frontend; complete an end-to-end demonstration.

* **Phase 3 – Documentation & Finalization (Weeks 4–5):** Complete the bilingual (English/Vietnamese) workshop guide, capture all required screenshots, prepare the cleanup guide, write individual reflections, and conduct the final review based on the evaluation rubric.

---

### 6. Budget Estimation

The estimated costs can be viewed using the [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=621f38b12a1ef026842ba2ddfe46ff936ed4ab01).

Alternatively, download the [budget estimation document](../attachments/budget_estimation.pdf).

#### Infrastructure Cost

Estimated monthly infrastructure cost for **10 customer projects**, each scanning **1,000 AWS resources per day**:

| AWS Service                         | Usage                                                | Estimated Monthly Cost |
| :---------------------------------- | :--------------------------------------------------- | ---------------------: |
| **AWS Lambda**                      | 100,000 requests, 512 MB memory                      |      $0.00 (Free Tier) |
| **Amazon API Gateway**              | 50,000 REST API requests                             |                  $0.05 |
| **Amazon DynamoDB**                 | On-Demand (2 GB storage, 500,000 reads/writes)       |                  $0.25 |
| **Amazon Bedrock**                  | Claude 3 Haiku (1M input tokens, 200k output tokens) |                  $1.20 |
| **Amazon EventBridge & Amazon SNS** | 720 scheduled triggers/month, 100 emails             |                  $0.01 |
| **Total Estimated Monthly Cost**    | **Serverless Pay-As-You-Go**                         |       **~$1.51/month** |

**Estimated Annual Infrastructure Cost:** **~$18.12/year**

---

### 7. Risk Assessment & Mitigation Strategies

| Identified Risk                                        | Severity | Likelihood | Mitigation Strategy                                                                                                                                                                     |
| :----------------------------------------------------- | :------- | :--------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Amazon Bedrock API rate limits**                     | Medium   | Low        | Implement an **exponential backoff retry mechanism** and cache analysis results in Amazon DynamoDB to reduce API requests.                                                              |
| **Customer revokes IAM Role permissions**              | High     | Medium     | Catch `ClientError` exceptions during `sts:AssumeRole` calls and automatically update the project status to **Disconnected**.                                                           |
| **LLM generates inaccurate responses (Hallucination)** | High     | Low        | Require the model to return responses following a predefined **JSON schema**, and use a **regex-based fallback parser** in Python to validate and recover improperly formatted outputs. |
| **AWS spending exceeds the budget**                    | Medium   | Low        | Configure **AWS Budgets** to send alerts when monthly costs reach **USD 5**, and limit the execution frequency of scheduled tasks (cron jobs).                                          |

---

### 8. Expected Outcomes

1. **Automated Infrastructure Auditing:** Develop an AI-powered system capable of automatically inspecting and evaluating AWS resources every hour, significantly reducing reliance on manual infrastructure reviews.

2. **Enhanced Security:** Minimize the risk of credential exposure by using **temporary session tokens** through the **AWS STS `AssumeRole`** mechanism instead of long-lived access keys.

3. **A Reusable Enterprise Blueprint:** Deliver a reference architecture that can be reused for developing **B2B SaaS** applications based on the **AWS Serverless** architecture.
