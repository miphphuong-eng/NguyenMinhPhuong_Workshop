
---
title: "1.8. Worklog Week 8"
weight: 8
draft: false
---

## Week 8 Objectives

- Understand AWS PrivateLink and how Interface VPC Endpoints enable private connectivity to AWS services.
- Learn how to configure an Interface VPC Endpoint for Amazon S3 to support hybrid access from on-premises environments.
- Understand the role of Elastic Network Interfaces (ENIs), private IP addresses, Security Groups, and Private DNS.
- Apply VPC Endpoint Policies to control access to Amazon S3 resources.
- Write and test custom JSON Endpoint Policies to restrict access to approved S3 buckets.
- Perform resource cleanup and review AWS costs after completing the practical exercises.

## Weekly Activities

| Day | Tasks | Start Date | Completion Date | Learning Resources |
|---|---|---|---|---|
| Monday | Study AWS PrivateLink and Interface VPC Endpoint architecture. Understand how Interface Endpoints create Elastic Network Interfaces (ENIs) with private IP addresses inside selected subnets. Learn how Private DNS simplifies service access. Compare Gateway and Interface Endpoints, focusing on their roles in connecting on-premises environments to AWS through VPN or Direct Connect. | 09/11/2026 | 09/11/2026 | [AWS PrivateLink Concepts](https://docs.aws.amazon.com/vpc/latest/privatelink/concepts.html) <br> [Amazon S3 Interface Endpoints](https://docs.aws.amazon.com/AmazonS3/latest/userguide/privatelink-interface-endpoints.html) |
| Tuesday | Create an Interface VPC Endpoint for Amazon S3 through the AWS Management Console. Select the appropriate VPC and subnets, configure the Security Group to allow HTTPS traffic on port 443 from the required source CIDR ranges, and review the endpoint's DNS configuration. Use `nslookup` or `dig` to inspect DNS resolution and identify the endpoint's private IP addresses. | 10/11/2026 | 10/11/2026 | [Interface VPC Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpce-interface-endpoints.html) |
| Wednesday | Study VPC Endpoint Policies and their relationship with IAM Policies and S3 Bucket Policies. Create a custom JSON Endpoint Policy to allow access only to approved company S3 buckets and specified actions. Review how the policy controls requests passing through the endpoint and understand the importance of applying least-privilege permissions. | 11/11/2026 | 11/11/2026 | [VPC Endpoint Policies](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html) |
| Thursday | Perform Endpoint Policy verification using AWS CLI. Test access to an approved company bucket using `aws s3 ls s3://allowed-company-bucket` and verify that the request is successful when all required permissions are configured. Test access to an external or unauthorized bucket using `aws s3 ls s3://external-personal-bucket` and verify that the request is denied by the Endpoint Policy. Record the results and review how Endpoint Policies help reduce the risk of unauthorized data transfers. | 12/11/2026 | 12/11/2026 | [VPC Endpoint Policies](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html) <br> [Preventing Data Exfiltration](https://aws.amazon.com/blogs/security/how-to-use-vpc-endpoint-policies-to-prevent-data-exfiltration/) |
| Friday | Perform resource cleanup after completing the exercises. Delete the Interface VPC Endpoint and verify that its associated endpoint network interfaces are removed automatically. Terminate test EC2 instances and delete test S3 buckets after confirming that they are no longer needed and are empty. Review AWS Billing and Cost Explorer to check for remaining charges or resources. Organize configuration files, JSON policy examples, screenshots, and technical notes to finalize Chapter 5 documentation. | 13/11/2026 | 13/11/2026 | [AWS PrivateLink Pricing](https://aws.amazon.com/privatelink/pricing/) <br> [AWS Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html) |
| Saturday | Participate in the Cloud Mastery event organized by FPT University. Attend event activities and explore topics related to cloud computing, AWS technologies, and practical cloud applications. Gain additional knowledge through shared experiences and discussions with other participants. | 14/11/2026 | 14/11/2026 | FPT University – Cloud Mastery Event |

## Week 8 Achievements

- Understood AWS PrivateLink and the architecture of Interface VPC Endpoints.
- Learned how Interface Endpoints use ENIs, private IP addresses, and Private DNS to provide private connectivity to AWS services.
- Understood how Interface VPC Endpoints can support hybrid access to Amazon S3 from on-premises environments through VPN or Direct Connect.
- Practiced creating an S3 Interface VPC Endpoint and configuring its Security Groups and DNS settings.
- Created custom JSON VPC Endpoint Policies to restrict access to approved S3 buckets and permitted actions.
- Tested authorized and unauthorized S3 access using AWS CLI and understood how Endpoint Policies help prevent unwanted data transfers.
- Practiced cleaning up AWS resources and reviewing billing information to reduce unnecessary cloud costs.
- Participated in the Cloud Mastery event organized by FPT University, gaining additional exposure to cloud computing technologies and learning experiences from the event.
- Organized technical notes, configuration examples, and screenshots for the Chapter 5 report.
