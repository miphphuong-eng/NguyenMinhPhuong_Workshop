
---
title: "1.7. Week 7 Worklog"
weight: 7
draft: false
---

## Week 7 Objectives

- Understand the concept and purpose of VPC Endpoints in AWS.
- Distinguish between Gateway Endpoints and Interface Endpoints.
- Learn how to configure an Amazon S3 Gateway VPC Endpoint.
- Access Amazon S3 privately from an EC2 instance in a Private Subnet without using an Internet Gateway or NAT Gateway.
- Test endpoint connectivity using AWS CLI and understand the related routing and security configurations.
- Evaluate the cost benefits of using a Gateway Endpoint instead of routing S3 traffic through a NAT Gateway.

## Weekly Activities

| Day | Tasks | Start Date | Completion Date | Learning Resources |
|---|---|---|---|---|
| Monday | Study the concept and purpose of VPC Endpoints. Learn the differences between Gateway Endpoints and Interface Endpoints. Understand how an S3 Gateway Endpoint uses AWS-managed Prefix Lists to route traffic privately through the AWS network. | 02/11/2026 | 02/11/2026 | [VPC Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints.html) |
| Tuesday | Review the existing VPC architecture, including Public and Private Subnets. Understand how an EC2 instance in a Private Subnet accesses AWS services without a direct Internet route. Check the EC2 instance, IAM permissions, Security Groups, and AWS CLI configuration before creating the endpoint. | 03/11/2026 | 03/11/2026 | [VPC Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html) |
| Wednesday | Create an Amazon S3 Gateway VPC Endpoint using the service name `com.amazonaws.ap-southeast-1.s3`. Associate the endpoint with the Route Table used by the Private Subnet. Verify the automatically added route using the S3 Prefix List and the VPC Endpoint ID. | 04/11/2026 | 04/11/2026 | [S3 VPC Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html) |
| Thursday | Test private access to Amazon S3 from the EC2 instance using AWS CLI commands such as `aws s3 ls` and `aws s3 cp`. Verify that S3 traffic is routed through the Gateway Endpoint. Review the Endpoint Policy, IAM permissions, and network configuration if access fails. Record the test results and capture screenshots as evidence. | 05/11/2026 | 05/11/2026 | [AWS CLI S3 Commands](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/index.html) |
| Friday | Compare the use of an S3 Gateway Endpoint with routing S3 traffic through a NAT Gateway. Review the configuration, connectivity test results, and security considerations. Summarize the advantages and limitations of Gateway Endpoints, then organize screenshots and technical notes for the weekly report. | 06/11/2026 | 06/11/2026 | [AWS PrivateLink Pricing](https://aws.amazon.com/privatelink/pricing/) |

## Week 7 Achievements

- Understood the purpose of VPC Endpoints and the differences between Gateway and Interface Endpoints.
- Learned how to create and configure an S3 Gateway VPC Endpoint.
- Understood how Route Tables use AWS-managed Prefix Lists to direct S3 traffic through the endpoint.
- Practiced accessing Amazon S3 privately from an EC2 instance in a Private Subnet using AWS CLI.
- Improved understanding of IAM permissions, Endpoint Policies, and network configurations required for private connectivity.
- Recognized the cost benefits of using an S3 Gateway Endpoint to avoid NAT Gateway data processing charges for applicable S3 traffic.
