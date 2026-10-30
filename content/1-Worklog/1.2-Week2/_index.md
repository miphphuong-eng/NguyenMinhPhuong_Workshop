---
title: "1.2. Week 2 Worklog"
weight: 2
draft: false
---

## Week 2 Objectives

- Understand the architecture and fundamental components of Amazon Virtual Private Cloud (Amazon VPC).
- Learn how to allocate IPv4 CIDR Blocks and design network infrastructure on AWS.
- Differentiate between Public Subnets and Private Subnets based on routing configuration and Internet connectivity.
- Understand the functions and operating principles of Route Tables, Internet Gateways, and NAT Gateways.
- Explore network security mechanisms in VPC, including Security Groups and Network ACLs.
- Practice creating a VPC, configuring Subnets, and establishing connectivity between AWS resources.
- Test network connectivity between EC2 Instances and the Internet.
- Discuss and brainstorm AWS project ideas with 4 team members.
- Identify the problem statement, target users, and initial project scope.
- Research and select suitable AWS services for the team project.

---

## Weekly Activities

| Day | Activities | Start Date | Completion Date | Reference Materials |
| :---: | :--- | :---: | :---: | :--- |
| **Friday** | - Discuss the initial direction of the AWS project with 4 team members.<br>- Brainstorm and propose potential projects that can be implemented on the Cloud platform.<br>- Identify real-world problems to solve and define the target users.<br>- Discuss the initial project scope and key functional requirements.<br>- Explore Amazon VPC fundamentals and understand its role in AWS system architecture. | 28/08/2026 | 28/08/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| **Friday** | - Study Amazon VPC fundamentals and understand how virtual private networks operate on AWS.<br>- Explore IPv4 CIDR Blocks and learn how to define the IP address range for a VPC.<br>- Learn how to divide a VPC into Public Subnets and Private Subnets.<br>- Understand the functions of Route Tables and Internet Gateways.<br>- Analyze network traffic flows between Subnets and the Internet.<br>- Draw a basic VPC network architecture diagram before starting the deployment. | 04/09/2026 | 04/09/2026 | [Amazon VPC Workshop](https://000003.awsstudygroup.com/)<br>[VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html)<br>[Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)<br>[Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| **Friday** | - Practice creating an Amazon VPC and configuring its IPv4 CIDR Block.<br>- Create Public Subnets and Private Subnets inside the VPC.<br>- Create an Internet Gateway and attach it to the VPC.<br>- Create a Route Table for the Public Subnet and configure the default route `0.0.0.0/0` to the Internet Gateway.<br>- Associate the Route Table with the corresponding Public Subnet.<br>- Launch EC2 Instances in Public and Private Subnets to test network configurations.<br>- Verify network connectivity and analyze the differences between the two Subnet types. | 11/09/2026 | 11/09/2026 | [Amazon VPC Workshop](https://000003.awsstudygroup.com/)<br>[Create EC2 Server](https://000003.awsstudygroup.com/4-createec2server/4.1-createec2/)<br>[Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| **Friday** | - Study VPC network security mechanisms, including Security Groups and Network ACLs.<br>- Compare Security Groups at the Network Interface level with Network ACLs at the Subnet level.<br>- Understand the Stateful behavior of Security Groups and the Stateless behavior of Network ACLs.<br>- Practice configuring Inbound Rules and Outbound Rules for both security layers.<br>- Explore commonly used network ports such as SSH (22) and HTTP (80).<br>- Test network connectivity using SSH, HTTP, and ICMP (Ping).<br>- Observe connection behavior when Allow and Deny rules are modified. | 18/09/2026 | 18/09/2026 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)<br>[Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) |
| **Friday** | - Study the concept and operating principles of NAT Gateway.<br>- Understand the differences between NAT Gateway and Internet Gateway in AWS network architecture.<br>- Practice creating a NAT Gateway inside a Public Subnet.<br>- Allocate and associate an Elastic IP address with the NAT Gateway.<br>- Update the Private Subnet Route Table with the default route `0.0.0.0/0` pointing to the NAT Gateway.<br>- Verify outbound Internet connectivity from an EC2 Instance in the Private Subnet.<br>- Analyze how NAT Gateway allows Private Subnet resources to access the Internet without accepting directly initiated inbound connections from the Internet. | 25/09/2026 | 25/09/2026 | [NAT Gateway Workshop](https://000003.awsstudygroup.com/4-createec2server/4.3-natgateway/)<br>[NAT Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| **Sunday** | - Review all knowledge about Amazon VPC and its network components studied during the week.<br>- Recheck the configurations of VPC, Public Subnets, Private Subnets, Route Tables, Internet Gateway, and NAT Gateway.<br>- Review Security Groups and Network ACLs configurations.<br>- Complete the VPC network architecture diagram.<br>- Summarize practical results and capture screenshots as evidence for each configuration step.<br>- Review the status of AWS resources and clean up unused resources to avoid unnecessary charges.<br>- Organize the learning materials and complete the Week 2 Worklog. | 04/10/2026 | 04/10/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)<br>[AWS Cost Management](https://docs.aws.amazon.com/cost-management/) |

---

## Week 2 Achievements

- Collaborated with 4 team members to establish the initial direction of the AWS team project.
- Proposed and discussed project ideas, identified the problem statement, target users, and initial project scope.
- Understood the architecture and fundamental functions of Amazon VPC in building private network environments on AWS.
- Learned how to use IPv4 CIDR Blocks to define IP address ranges and divide networks into Subnets.
- Distinguished between Public Subnets and Private Subnets based on Route Table configurations and Internet connectivity.
- Understood the role of Route Tables in directing network traffic between Subnets and the Internet.
- Successfully practiced creating an Amazon VPC, configuring IPv4 CIDR Blocks, and provisioning Public and Private Subnets.
- Created and attached an Internet Gateway to the VPC, then configured Route Tables to enable Internet connectivity for the Public Subnet.
- Practiced launching EC2 Instances in different Subnets and testing network connectivity.
- Understood the key differences between Security Groups and Network ACLs:
  - Security Groups operate at the resource level and are stateful.
  - Network ACLs operate at the Subnet level and are stateless.
- Practiced configuring Inbound Rules and Outbound Rules to control network traffic.
- Tested connectivity using SSH, HTTP, and ICMP (Ping), and observed how security rules affect network access.
- Understood the operating principles of NAT Gateway and the role of Elastic IP in AWS network architecture.
- Successfully practiced creating a NAT Gateway in a Public Subnet and updating the Private Subnet Route Table.
- Verified outbound Internet connectivity from an EC2 Instance located in the Private Subnet.
- Completed the VPC network architecture diagram, summarized practical results, and captured screenshots as implementation evidence.
- Improved practical skills in network design, routing configuration, access control, and AWS resource management.
- Learned to review and clean up unused AWS resources after completing practical exercises to minimize unnecessary costs.
