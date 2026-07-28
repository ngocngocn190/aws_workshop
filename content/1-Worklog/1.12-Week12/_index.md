---
title: "Week 12 Worklog"
date: 2026-07-27
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The content below is a proposed study plan for reference only. Please **do not copy it verbatim** into your report, including this warning message.
{{% /notice %}}

### Week 12 Objectives

* Perform comprehensive testing of the **AI AWS Advisor** project and complete the remaining project documentation.
* Clean up all AWS resources used throughout the project and prepare the final presentation and demonstration.

### Tasks for This Week

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - **Hands-on:** Execute key test cases (create a project, trigger resource synchronization, detect public S3 buckets, identify IAM users/roles with `AdministratorAccess`, etc.) | 27/07/2026 | 27/07/2026 | |
| Tue | - **Hands-on:** Review Collector Lambda and API Lambda logs using Amazon CloudWatch <br> - Write `docs/06-reflection.md` | 28/07/2026 | 28/07/2026 | |
| Wed | - **Hands-on:** Deploy the complete end-to-end application and verify that the dashboard displays real data from AWS | 29/07/2026 | 29/07/2026 | |
| Thu | - Review the project's security posture: verify IAM roles follow the principle of least privilege, ensure no access keys are hardcoded, and review audit logs in Amazon CloudWatch | 30/07/2026 | 30/07/2026 | |
| Fri | - Prepare the final project demonstration and presentation for the **AI AWS Advisor** project | 31/07/2026 | 31/07/2026 | |
| Sat | - **Hands-on:** Write `docs/05-cleanup.md` <br> - Clean up all AWS resources created during the project (AWS SAM stacks, DynamoDB tables, Amazon SNS topics, Amazon S3 buckets, CloudWatch Log Groups, etc.) | 01/08/2026 | 01/08/2026 | |

### Expected Outcomes

* Successfully pass all critical test cases, confirming that the system functions as designed.
* Gain the ability to use Amazon CloudWatch logs for debugging and troubleshooting, and complete a reflection document summarizing the project experience.
* Deploy a fully functional end-to-end version of the application, with the dashboard displaying real data from the AWS sandbox environment.
* Verify that the system follows essential AWS security best practices, including the principle of least privilege, avoiding hardcoded access keys, and maintaining an audit trail.
* Complete all materials required for the final project demonstration and presentation.
* Successfully clean up all AWS resources used throughout the project to prevent unnecessary charges after project completion.
* ...