---
title: "Worklog Week 4"
date: 2025-06-08
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The content below is a proposed plan for reference only. Please **do not copy it verbatim** into your report, including this warning.
{{% /notice %}}

### Objectives for Week 4:

* Learn about Amazon RDS: how to deploy managed relational databases, connect them with EC2, and perform backup & restore.
* Learn about Amazon CloudWatch: monitoring metrics, logs, configuring alarms, and creating dashboards for AWS resources.

### Tasks to be completed this week:

| Day | Tasks | Start Date | Completion Date | Reference |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------ |
| 2 | - Learn the fundamentals of Amazon RDS: concepts, supported database engines, and when to use RDS <br> - **Hands-on:** Prepare VPC, EC2 Security Group, RDS Security Group, and DB Subnet Group | 08/06/2025 | 08/06/2025 | <https://000005.awsstudygroup.com/vi/1-introduce/> |
| 3 | - **Hands-on:** Launch an EC2 instance <br> - **Hands-on:** Create an Amazon RDS database instance | 09/06/2025 | 09/06/2025 | <https://000005.awsstudygroup.com/vi/3-create-ec2/> |
| 4 | - **Hands-on:** Deploy an application connecting EC2 with RDS <br> - **Hands-on:** Perform RDS backup and restore <br> - Clean up the created RDS resources | 10/06/2025 | 10/06/2025 | <https://000005.awsstudygroup.com/vi/5-deploy-app/> |
| 5 | - Learn the fundamentals of Amazon CloudWatch <br> - **Hands-on:** Perform preparation steps <br> - Learn CloudWatch Metrics: viewing metrics, search expressions, math expressions, and dynamic labels | 11/06/2025 | 11/06/2025 | <https://000008.awsstudygroup.com/vi/3-cloud-watch-metric/> |
| 6 | - Learn CloudWatch Logs: Logs, Logs Insights, and Metric Filters | 12/06/2025 | 12/06/2025 | <https://000008.awsstudygroup.com/vi/4-cloud-watch-logs/> |
| 7 | - Learn CloudWatch Alarms and Dashboards <br> - Clean up all CloudWatch resources created during the week | 13/06/2025 | 13/06/2025 | <https://000008.awsstudygroup.com/vi/5-cloud-watch-alarm/> |

### Expected outcomes for Week 4:

* Understand what Amazon RDS is, the supported database engines (Aurora, MySQL, MariaDB, Oracle, SQL Server, PostgreSQL), and when to choose RDS instead of deploying a database on EC2.
* Be able to prepare the required network infrastructure (VPC, Security Group, and DB Subnet Group) for an Amazon RDS instance.
* Successfully create an EC2 instance and an RDS database instance, then deploy an application that connects the two services.
* Know how to perform backup and restore operations for an Amazon RDS database.
* Understand Amazon CloudWatch and its role in monitoring AWS resources and applications.
* Be able to work with CloudWatch Metrics, including searching metrics, using math expressions, and creating dynamic labels.
* Know how to use CloudWatch Logs and Logs Insights to search and analyze logs, and create Metric Filters from log data.
* Configure CloudWatch Alarms to detect abnormal conditions and create Dashboards for centralized monitoring.
* Understand how to clean up AWS resources after completing hands-on labs to avoid unnecessary charges.