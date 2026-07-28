---
title: "Week 7 Worklog"
date: 2026-06-22
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---


### Week 7 Objectives

* Learn about Amazon Route 53 and the Route 53 Resolver service.
* Practice building a Hybrid DNS architecture by integrating an on-premises DNS server (Microsoft Active Directory) with AWS DNS services.

### Tasks for This Week

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Learn the fundamentals of Amazon Route 53, Route 53 Resolver, and Hybrid DNS architecture <br>&emsp; + Outbound Endpoint <br>&emsp; + Inbound Endpoint <br>&emsp; + Resolver Rules | 22/06/2026 | 22/06/2026 | <https://000010.awsstudygroup.com/vi/1-introduce/> |
| Tue | - **Hands-on:** Create a Key Pair <br> - **Hands-on:** Deploy the sample infrastructure using an AWS CloudFormation template | 23/06/2026 | 23/06/2026 | <https://000010.awsstudygroup.com/vi/2-prerequiste/> |
| Wed | - **Hands-on:** Configure Security Groups <br> - **Hands-on:** Connect to the Remote Desktop Gateway (RDGW) | 24/06/2026 | 24/06/2026 | <https://000010.awsstudygroup.com/vi/3-connecttordgw/> |
| Thu | - **Hands-on:** Deploy Microsoft Active Directory | 25/06/2026 | 25/06/2026 | <https://000010.awsstudygroup.com/vi/4-setupad/> |
| Fri | - **Hands-on:** Configure Hybrid DNS <br>&emsp; + Create a Route 53 Outbound Endpoint <br>&emsp; + Create Route 53 Resolver Rules <br>&emsp; + Create Route 53 Inbound Endpoints | 26/06/2026 | 26/06/2026 | <https://000010.awsstudygroup.com/vi/5-setuphyriddns/> |
| Sat | - **Hands-on:** Verify bidirectional DNS name resolution <br> - Clean up all AWS resources created during the lab | 27/06/2026 | 27/06/2026 | <https://000010.awsstudygroup.com/vi/6-cleanup/> |

### Expected Outcomes

* Understand the purpose of Amazon Route 53 and the role of Route 53 Resolver in DNS name resolution between on-premises environments and AWS.
* Gain a solid understanding of the three core components of a Hybrid DNS architecture: Outbound Endpoints, Inbound Endpoints, and Resolver Rules.
* Deploy the sample infrastructure using AWS CloudFormation and configure the required Security Groups.
* Successfully connect to the Remote Desktop Gateway (RDGW) and deploy Microsoft Active Directory on AWS.
* Configure a complete Hybrid DNS solution that enables bidirectional DNS name resolution between an on-premises environment and AWS.
* Validate DNS resolution after configuration.
* Learn how to clean up AWS resources after completing the lab to avoid unnecessary charges.
* ...