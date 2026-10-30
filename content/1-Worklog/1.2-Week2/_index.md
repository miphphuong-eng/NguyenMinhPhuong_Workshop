---
title: "1.2. Week 2 Worklog"
weight: 2
draft: false
---

## Week 2 Objectives

- Learn about the architecture of Amazon Virtual Private Cloud (Amazon VPC) and its fundamental components.
- Understand IPv4 CIDR Block allocation and network design on AWS.
- Distinguish between Public Subnets and Private Subnets based on routing configurations and Internet connectivity.
- Understand the functions and operating principles of Route Tables, Internet Gateway, and NAT Gateway.
- Explore network security mechanisms in VPC, including Security Groups and Network ACLs.
- Practice creating a VPC, configuring Subnets, and establishing connectivity between AWS resources.
- Test network connectivity between EC2 Instances and the Internet.
- Discuss AWS project ideas with four team members.
- Identify the problem to be solved, target users, and the initial project scope.
- Research and select suitable AWS services for the development of the team project.

---

## Weekly Activities

| Day | Activities | Start Date | End Date | References |
| :---: | :--- | :---: | :---: | :--- |
| **Monday** | - Discuss the initial direction of the AWS project with four team members.<br>- Brainstorm and propose project ideas that can be implemented on the Cloud platform.<br>- Identify real-world problems to solve and define the target users.<br>- Discuss the initial project scope and main functional requirements.<br>- Learn about Amazon VPC and its role in AWS system architecture. | 28/09/2026 | 28/09/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| **Tuesday** | - Learn the fundamentals of Amazon VPC and how virtual private networks operate on AWS.<br>- Study IPv4 CIDR Blocks and how to define the IP address range for a VPC.<br>- Learn how to divide a VPC into Public Subnets and Private Subnets.<br>- Explore the functions of Route Tables and Internet Gateway.<br>- Analyze network traffic flows between Subnets and the Internet.<br>- Draft a VPC network architecture diagram before practical implementation. | 29/09/2026 | 29/09/2026 | [Amazon VPC Workshop](https://000003.awsstudygroup.com/)<br>[VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html)<br>[Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)<br>[Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| **Wednesday** | - Practice creating an Amazon VPC and configuring its IPv4 CIDR Block.<br>- Create Public Subnets and Private Subnets inside the VPC.<br>- Create an Internet Gateway and attach it to the VPC.<br>- Create a Route Table for the Public Subnet and configure the default route `0.0.0.0/0` to the Internet Gateway.<br>- Associate the Route Table with the corresponding Public Subnet.<br>- Launch EC2 Instances in Public and Private Subnets to test network configurations.<br>- Test connectivity and analyze the differences between the two types of Subnets. | 30/09/2026 | 30/09/2026 | [Amazon VPC Workshop](https://000003.awsstudygroup.com/)<br>[Create EC2 Server](https://000003.awsstudygroup.com/4-createec2server/4.1-createec2/)<br>[Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| **Thursday** | - Learn about network security mechanisms using Security Groups and Network ACLs.<br>- Distinguish between Security Groups, which operate at the Network Interface level, and Network ACLs, which operate at the Subnet level.<br>- Understand the Stateful behavior of Security Groups and the Stateless behavior of Network ACLs.<br>- Practice configuring Inbound Rules and Outbound Rules for each security layer.<br>- Learn about common network ports such as SSH (22) and HTTP (80).<br>- Test network traffic using SSH, HTTP, and ICMP (Ping).<br>- Observe the results when changing rules to allow or deny network connections. | 01/10/2026 | 01/10/2026 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)<br>[Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) |
| **Friday** | - Learn about the concept and operating principles of NAT Gateway.<br>- Distinguish between the functions of NAT Gateway and Internet Gateway in AWS network architecture.<br>- Practice creating a NAT Gateway inside a Public Subnet.<br>- Allocate and associate an Elastic IP with the NAT Gateway.<br>- Update the Private Subnet's Route Table with the default route `0.0.0.0/0` pointing to the NAT Gateway.<br>- Test outbound Internet connectivity from an EC2 Instance in the Private Subnet.<br>- Analyze how NAT Gateway allows resources in Private Subnets to access the Internet without accepting directly initiated inbound connections from the Internet. | 02/10/2026 | 02/10/2026 | [NAT Gateway Workshop](https://000003.awsstudygroup.com/4-createec2server/4.3-natgateway/)<br>[NAT Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| **Sunday** | - Review the knowledge of Amazon VPC and the network components studied during the week.<br>- Recheck the configurations of VPC, Public Subnets, Private Subnets, Route Tables, Internet Gateway, and NAT Gateway.<br>- Review Security Groups and Network ACLs rules.<br>- Complete the VPC network architecture diagram.<br>- Summarize practical results and capture screenshots as evidence of each configuration step.<br>- Check the status of AWS resources and clean up unused resources to avoid unnecessary charges.<br>- Consolidate the activities and complete the Week 2 Worklog. | 04/10/2026 | 04/10/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)<br>[AWS Cost Management](https://docs.aws.amazon.com/cost-management/) |

---

## Week 2 Achievements

- Collaborated and discussed with four team members to establish the initial direction of the AWS project.
- Proposed and discussed project ideas, identified problems to solve, target users, and the initial implementation scope.
- Understood the architecture and fundamental functions of Amazon VPC in building private virtual networks on AWS.
- Learned how to use IPv4 CIDR Blocks to define IP address ranges and divide Subnets.
- Distinguished between Public Subnets and Private Subnets based on Route Table configurations and Internet connectivity.
- Understood the role of Route Tables in routing network traffic between Subnets and the Internet.
- Practiced creating an Amazon VPC, configuring IPv4 CIDR Blocks, and deploying Public Subnets and Private Subnets.
- Created and attached an Internet Gateway to the VPC, then configured Route Tables to enable Internet connectivity for the Public Subnet.
- Practiced launching EC2 Instances in different Subnets and testing network connectivity.
- Understood the differences between Security Groups and Network ACLs:
  - Security Groups operate at the resource level and use a Stateful mechanism.
  - Network ACLs operate at the Subnet level and use a Stateless mechanism.
- Practiced configuring Inbound Rules and Outbound Rules to control network traffic.
- Tested connectivity through SSH, HTTP, and ICMP (Ping), while observing how security rules affect network access.
- Understood the operating principles of NAT Gateway and the role of Elastic IP in AWS network architecture.
- Practiced creating a NAT Gateway in a Public Subnet and updating the Route Table for a Private Subnet.
- Tested outbound Internet connectivity from an EC2 Instance in a Private Subnet.
- Completed the VPC network architecture diagram, summarized practical results, and saved screenshots as evidence.
- Improved skills in network design, routing configuration, access control, and AWS resource management.
- Learned how to review and clean up AWS resources after practical exercises to minimize unnecessary costs.
