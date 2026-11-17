
---
title: "1.6. Worklog Week 6"
weight: 6
draft: false
---

## Week 6 Objectives

- Participate in a community workshop focused on making teddy bears as meaningful gifts for children, contributing to a charitable activity and developing teamwork and social responsibility.
- Understand Infrastructure as Code (IaC) principles and the benefits of using AWS CloudFormation to automate infrastructure provisioning and management.
- Learn CloudFormation template syntax in YAML, including Parameters, Resources, Outputs, and other essential template sections.
- Practice automating AWS resource management through AWS CLI and using JMESPath `--query` filters to retrieve and format resource information.
- Explore CloudFormation Stack lifecycle management, including stack creation, updates, rollback mechanisms, and Drift Detection.
- Apply the knowledge gained to design and deploy a basic two-tier AWS infrastructure consisting of networking components, EC2, and RDS using a CloudFormation template.

## Weekly Activities

| **Day** | **Tasks** | **Start Date** | **Completion Date** | **Learning Resources** |
| :--- | :--- | :--- | :--- | :--- |
| Monday | - Participate in a community workshop focused on making teddy bears to give as gifts to children.<br>- Take part in preparing materials, assembling teddy bears, and completing the handmade gifts for the charitable activity.<br>- Collaborate with other participants, share responsibilities, and contribute to creating meaningful gifts for children.<br>- Reflect on the importance of community engagement, teamwork, and social responsibility during the internship. | 26/10/2026 | 26/10/2026 | Community Workshop Activities |
| Tuesday | - Explore Infrastructure as Code (IaC) fundamentals and understand how infrastructure can be provisioned and managed through code instead of manual configuration.<br>- Study AWS CloudFormation and compare manual resource management through the AWS Console with automated provisioning using templates.<br>- Examine the structure of CloudFormation YAML templates, including `AWSTemplateFormatVersion`, `Description`, `Parameters`, `Resources`, and `Outputs`.<br>- Review the benefits of reusable templates, consistent deployments, and reduced configuration errors across environments. | 27/10/2026 | 27/10/2026 | [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)<br>[Template Anatomy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html) |
| Wednesday | - Practice writing a CloudFormation YAML template to provision basic VPC networking resources.<br>- Define resources such as `AWS::EC2::VPC`, `AWS::EC2::Subnet`, `AWS::EC2::InternetGateway`, `AWS::EC2::RouteTable`, and `AWS::EC2::SubnetRouteTableAssociation`.<br>- Apply CloudFormation Intrinsic Functions, including `!Ref`, `!Sub`, and `!GetAtt`, to reference resources and configure dependencies dynamically.<br>- Practice using AWS CLI in a Linux Bash environment to inspect AWS resources and retrieve information such as VPC IDs and EC2 public IP addresses.<br>- Use JMESPath expressions with the `--query` option and format command output as JSON for easier resource management and automation. | 28/10/2026 | 28/10/2026 | [CloudFormation Resource Reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)<br>[Intrinsic Functions](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference.html)<br>[AWS CLI Command Reference](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/index.html)<br>[Filtering AWS CLI Output](https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-filter.html) |
| Thursday | - Extend the CloudFormation template to include Security Groups, EC2 instances, and RDS database resources to form a basic two-tier architecture.<br>- Review resource dependencies and configure appropriate network access between the application and database layers.<br>- Study CloudFormation Stack Events and understand how automatic rollback works when resource creation or stack updates fail.<br>- Explore Stack Updates and Drift Detection to identify differences between the actual AWS resource configuration and the configuration declared in the template.<br>- Deploy the infrastructure using `aws cloudformation create-stack` and monitor the deployment process with `aws cloudformation describe-stack-events`.<br>- Verify the stack status, review the Outputs section, and retrieve the application endpoint if configured.<br>- Save the completed `template.yaml` file and organize screenshots and execution results as project evidence. | 29/10/2026 | 29/10/2026 | [Stack Management](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacks.html)<br>[Detecting Drift](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-stack-drift.html)<br>[AWS CLI CloudFormation](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/cloudformation/index.html)<br>[Deploying Stacks](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stacks.html) |

## Week 6 Achievements

- Participated in a community workshop and contributed to making handmade teddy bears as gifts for children, gaining experience in teamwork and community engagement.
- Developed an understanding of Infrastructure as Code (IaC) and the benefits of automated infrastructure provisioning, including consistency, reusability, and reduced manual configuration errors.
- Became familiar with CloudFormation YAML template structure and the use of Parameters, Resources, Outputs, and Intrinsic Functions such as `!Ref`, `!Sub`, and `!GetAtt`.
- Practiced defining AWS networking resources, including VPCs, Subnets, Internet Gateways, and Route Tables, through CloudFormation templates.
- Improved AWS CLI skills by using JMESPath `--query` filters to retrieve resource information and format command outputs for automation tasks.
- Gained a better understanding of CloudFormation Stack lifecycle management, resource dependencies, Stack Updates, automatic Rollbacks, and Drift Detection.
- Practiced deploying a two-tier infrastructure consisting of networking components, EC2, and RDS through CloudFormation and AWS CLI.
- Organized the `template.yaml` file and collected deployment screenshots and execution results to document the infrastructure automation process.
