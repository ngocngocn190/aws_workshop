---
title: "Week 3 Worklog"
date: 2025-06-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The following information is a planned schedule for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 3 Objectives:

* Learn about Amazon EC2: how to launch and configure instances on both Windows and Linux, and deploy a real application.
* Learn about Amazon S3: object storage, static website hosting, and acceleration with CloudFront.
* Practice applying IAM to restrict resource usage permissions and control costs.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                | Start Date | Completion Date | Reference Material                                              |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------------------------------ |
| 2   | - Learn the overview of Amazon EC2 <br> - **Practice:** Prepare the VPC & Security Group for Linux/Windows instances                                                                                            | 06/01/2025 | 06/01/2025      | <https://000004.awsstudygroup.com/vi/1-introduce/>                |
| 3   | - **Practice:** Launch & connect to a Windows instance and a Linux instance <br> - Learn basic EC2: <br>&emsp; + Change EC2 configuration <br>&emsp; + Create an EBS Snapshot <br>&emsp; + Create & launch a Custom AMI | 06/02/2025 | 06/02/2025      | <https://000004.awsstudygroup.com/vi/3-launchwindowsinstance/>    |
| 4   | - **Practice:** Deploy a Node.js application (AWS User Management) <br>&emsp; + On Linux: LAMP server, phpMyAdmin, Node.js <br>&emsp; + On Windows: XAMPP, Node.js <br> - Apply IAM to restrict resource usage permissions (region, instance type, EBS...) | 06/03/2025 | 06/03/2025      | <https://000004.awsstudygroup.com/vi/6-awsfcjmanagement-linux/>   |
| 5   | - Learn the overview of Amazon S3 <br> - **Practice:** Create an S3 bucket, upload data <br> - Enable static website hosting                                                                                    | 06/04/2025 | 06/04/2025      | <https://000057.awsstudygroup.com/vi/1-introduce/>                |
| 6   | - **Practice:** Configure Block Public Access & public objects <br> - Test the static website <br> - Accelerate the website with Amazon CloudFront                                                             | 06/05/2025 | 06/05/2025      | <https://000057.awsstudygroup.com/vi/7-cloudfront/>                |
| 7   | - **Practice:** Bucket Versioning, move & copy objects to another region <br> - Clean up all EC2 & S3 resources created this week                                                                              | 06/06/2025 | 06/06/2025      | <https://000057.awsstudygroup.com/vi/8-versioning/>                |

### Week 3 Expected Achievements:

* Understand how Amazon EC2 works and its basic components: instance, AMI, EBS, Security Group.

* Able to independently launch and connect to EC2 instances on both Windows Server and Amazon Linux.

* Successfully deployed a simple Node.js CRUD application (AWS User Management) on both operating systems.

* Know how to use IAM to restrict resource usage permissions (by region, instance type, time...) to help control costs.

* Understand what Amazon S3 is, how to create a bucket, upload data, and enable static website hosting.

* Know how to safely configure public access permissions, and how to accelerate a website with CloudFront.

* Understand how to manage object versioning in S3 and copy data across regions.

* Know how to clean up resources after practicing to avoid unwanted costs.