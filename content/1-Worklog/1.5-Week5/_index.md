
---
title: "1.5. Worklog Week 5"
weight: 5
draft: false
---

## Week 5 Objectives

- Understand the role of centralized monitoring and logging in AWS environments and explore the core capabilities of Amazon CloudWatch, including Metrics, Logs, Alarms, and Dashboards.
- Learn how to monitor EC2 instances through system metrics, identify abnormal resource utilization, and configure CloudWatch Alarms to detect potential infrastructure issues.
- Understand the integration between Amazon CloudWatch and Amazon Simple Notification Service (SNS) to deliver automated email notifications when monitoring thresholds are reached.
- Explore AWS CloudTrail and understand how it records API activities, tracks user actions, and supports security auditing and compliance requirements.
- Learn how to manage and optimize AWS spending using AWS Cost Explorer and AWS Budgets, including analyzing service costs and configuring budget threshold notifications.
- Gain practical experience installing and configuring the CloudWatch Agent on EC2 instances to collect memory and disk metrics, forward system logs, and build a centralized monitoring dashboard.

## Weekly Activities

| **Day** | **Tasks** | **Start Date** | **Completion Date** | **Learning Resources** |
| :--- | :--- | :--- | :--- | :--- |
| Monday | - Study the architecture and fundamental components of Amazon CloudWatch, including Metrics, Namespaces, Dimensions, Log Groups, and Log Streams.<br>- Perform hands-on exercises to view EC2 monitoring metrics and understand how CloudWatch collects and displays resource information.<br>- Compare Basic Monitoring (5-minute intervals) with Detailed Monitoring (1-minute intervals) and understand their differences in monitoring frequency and cost.<br>- Analyze important EC2 metrics such as CPUUtilization, StatusCheckFailed, NetworkIn, and NetworkOut to identify potential performance issues. | 19/10/2026 | 19/10/2026 | [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html)<br>[CloudWatch Concepts](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_concepts.html) |
| Tuesday | - Explore the Publish/Subscribe messaging model of Amazon SNS and understand how SNS Topics distribute notifications to subscribed endpoints.<br>- Create an SNS Topic named `CloudWatch-Alerts-Topic` and configure an email subscription, including confirming the subscription through the verification email.<br>- Create a CloudWatch Alarm to monitor EC2 CPU utilization with a threshold of 80% over a configured evaluation period.<br>- Connect the alarm to the SNS Topic and test the notification workflow to understand how AWS automatically sends email alerts when the alarm enters the ALARM state. | 20/10/2026 | 20/10/2026 | [Amazon SNS User Guide](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)<br>[CloudWatch Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html) |
| Wednesday | - Study AWS CloudTrail and understand its role in recording account activities, API requests, and changes made to AWS resources.<br>- Examine the structure of CloudTrail Events, focusing on User Identity, Event Time, Event Source, Source IP Address, and Request Parameters.<br>- Practice reviewing recent API activities through CloudTrail Event History to identify who performed an action, when it occurred, and which AWS service was involved.<br>- Configure a multi-region CloudTrail Trail to collect management events and deliver log files to an Amazon S3 bucket for centralized auditing and long-term retention. | 21/10/2026 | 21/10/2026 | [AWS CloudTrail User Guide](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)<br>[CloudTrail Events](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html) |
| Thursday | - Explore AWS Cost Management and understand how cloud expenditure can be monitored and controlled across different AWS services.<br>- Use AWS Cost Explorer to review historical spending, group costs by service and region, and identify resources that contribute significantly to the monthly bill.<br>- Learn how to create an AWS Budget with a defined monthly spending limit and configure notifications when actual or forecasted costs reach 80% of the budget.<br>- Review budget alerts and understand how cost monitoring helps prevent unexpected charges from resources such as EC2 instances, RDS databases, and NAT Gateways. | 22/10/2026 | 22/10/2026 | [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-whatis.html)<br>[AWS Budgets Guide](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html) |
| Friday | - **Hands-on Practice and Centralized Monitoring:**<br>- Install and configure the CloudWatch Agent on a Linux EC2 instance and prepare the agent configuration for collecting additional system information.<br>- Enable memory and disk utilization metrics, which are not included in standard EC2 basic monitoring by default.<br>- Configure the agent to collect system log files, such as `/var/log/syslog`, and forward log data to the appropriate CloudWatch Log Group.<br>- Create a custom CloudWatch Dashboard containing CPU utilization, memory usage, disk utilization, network traffic, and RDS connection metrics.<br>- Review the dashboard widgets and verify that monitoring data is being received correctly.<br>- Capture screenshots of the configurations, alarms, and dashboard as evidence of the completed hands-on exercises. | 23/10/2026 | 23/10/2026 | [CloudWatch Agent Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html)<br>[CloudWatch Dashboards](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html) |

## Week 5 Achievements

- Gained a comprehensive understanding of Amazon CloudWatch and its role in centralized infrastructure monitoring, metric collection, log management, and performance analysis.
- Practiced monitoring EC2 instances through essential system metrics and understood the differences between Basic Monitoring and Detailed Monitoring.
- Successfully created an Amazon SNS Topic, configured email subscriptions, and integrated SNS with CloudWatch Alarms to automate incident notifications.
- Configured a CPU utilization alarm with an 80% threshold and understood how CloudWatch evaluates monitoring data and triggers notifications when resource usage becomes abnormal.
- Developed a practical understanding of AWS CloudTrail, including API event history, user activity tracking, and the use of Amazon S3 for storing audit logs.
- Used AWS Cost Explorer to analyze cloud expenditure and configured AWS Budgets to monitor monthly spending and receive notifications when budget thresholds were reached.
- Installed and configured the CloudWatch Agent on EC2 to collect additional memory and disk metrics and forward system logs to CloudWatch Logs.
- Created a centralized CloudWatch Dashboard to provide an overview of infrastructure health and monitor important resources, including EC2, RDS, and network activity.
- Improved the ability to identify infrastructure issues, monitor resource utilization, review system activities, and control AWS operating costs through centralized monitoring tools.
