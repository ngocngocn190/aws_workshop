Markdown

```
---
title: "Week 10 Worklog"
date: 2026-07-13
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The content below is a proposed study plan for reference only. Please **do not copy it verbatim** into your report, including this warning message.
{{% /notice %}}

### Week 10 Objectives

* Begin the **Core Build** phase by implementing the Resource Collector and backend APIs for the **AI AWS Advisor** project.
* Complete the project documentation and repository structure according to standard Git repository requirements.

### Tasks for This Week

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - **Hands-on:** Set up the AWS SAM project structure (`template.yaml`, `requirements.txt`) <br> - Create the four DynamoDB tables (**projects**, **resources**, **insights**, **alerts**) | 13/07/2026 | 13/07/2026 | |
| Tue | - **Hands-on:** Create IAM roles for the Collector Lambda functions (AssumeRole configuration and least-privilege permissions) | 14/07/2026 | 14/07/2026 | |
| Wed | - **Hands-on:** Build Resource Collectors for **EC2** and **S3** (collecting instances, buckets, public access settings, ACLs, and related metadata) | 15/07/2026 | 15/07/2026 | |
| Thu | - **Hands-on:** Build Resource Collectors for **IAM**, **Lambda**, and **CloudWatch** | 16/07/2026 | 16/07/2026 | |
| Fri | - **Hands-on:** Implement API Lambda functions for `/projects` (CRUD operations) and `/resources` (GET operations) | 17/07/2026 | 17/07/2026 | |
| Sat | - Finalize Git repository documentation: `README.md`, `.gitignore`, and `docs/01-prerequisites.md` <br> - Standardize commit messages and pull request workflows according to the agreed branch strategy | 18/07/2026 | 18/07/2026 | |

### Expected Outcomes

* Set up a standard AWS SAM project structure and create all four DynamoDB tables based on the finalized schema.
* Create dedicated IAM roles for the Collector Lambda functions while following the **principle of least privilege**.
* Ensure the **EC2** and **S3 Resource Collectors** are operational and successfully store collected data in DynamoDB.
* Ensure the **IAM**, **Lambda**, and **CloudWatch Resource Collectors** are operational, completing the infrastructure data collection layer.
* Ensure the `/projects` and `/resources` APIs are functional and return data according to the finalized API contracts.
* Maintain a well-structured GitHub repository with a complete `README`, `.gitignore`, prerequisite documentation, and consistent branch and pull request practices across the team.
* ...
```
