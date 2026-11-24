
---
title: "Blog 3"
date: 2026-11-24
weight: 3
chapter: false
pre: "<b> 3.3. </b>"
---

# AMAZON EVENTBRIDGE SCHEDULER – A SMALL BUT POWERFUL SERVICE FOR AWS PROJECTS

During application development, many tasks do not need to be executed immediately. Instead, they must run at specific times or repeat at regular intervals. Examples include sending appointment reminders, updating data every 30 minutes, deleting expired records, or checking system status at the end of the day.

If we use an EC2 instance to handle these tasks, we need to maintain the server, configure its environment, and manage the scheduling mechanism ourselves. This can waste resources when a task only takes a few seconds to complete.

To address this problem, Amazon Web Services provides **Amazon EventBridge Scheduler** – a serverless scheduling service that automatically triggers AWS services at predefined times without requiring a dedicated server.

In this article, we will explore how EventBridge Scheduler works, its scheduling options, key features, and how to use it to automatically invoke AWS Lambda in a practical project.

### 1. What is Amazon EventBridge Scheduler?

Amazon EventBridge Scheduler is an AWS-managed scheduling service that allows users to create and manage tasks that run once at a specific time or repeatedly according to a defined schedule.

Instead of writing a program to continuously check the time and invoke an API, we only need to create a Schedule, define its execution time, and select a target service. EventBridge Scheduler automatically sends a request to that service when the configured schedule is triggered.

Some AWS services that can be invoked through EventBridge Scheduler include:

- **AWS Lambda:** Execute code for data processing or business logic.
- **Amazon ECS / AWS Fargate:** Launch containers to perform tasks that require more computing resources.
- **AWS Step Functions:** Start workflows consisting of multiple processing steps.
- **Amazon SNS:** Send notifications to subscribers.
- **Amazon SQS:** Place messages into a queue for later processing.
- **Amazon EventBridge Event Bus:** Publish events for other components in the system.

With Universal Targets, EventBridge Scheduler can invoke more than 6,000 API operations across more than 270 AWS services. This provides flexible integration with different components in a Cloud architecture.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/eventbridge-scheduler-architecture.png" alt="Amazon EventBridge Scheduler architecture" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Figure 1 - Illustration of how Amazon EventBridge Scheduler creates schedules and triggers target services on AWS.</em></p>
</div>

### 2. Scheduling Types in EventBridge Scheduler

One of the most useful features of EventBridge Scheduler is its support for different scheduling types, allowing developers to choose the option that best fits their application requirements.

**2.1. One-time Schedule**

A One-time Schedule triggers a task only once at a specified date and time.

Examples:

- Sending an appointment reminder to a user.
- Automatically sending a notification 24 hours after a user registers.
- Triggering a task on an order's expiration date.

This option is suitable for tasks that only need to run once rather than repeatedly.

**2.2. Rate-based Schedule**

A Rate-based Schedule executes tasks repeatedly at fixed time intervals.

Example:

```text
rate(30 minutes)
```

This expression instructs EventBridge Scheduler to invoke the target every 30 minutes.

Common use cases include:

- Periodically updating application data.
- Checking system status.
- Aggregating data at regular intervals.
- Automatically synchronizing information between services.

**2.3. Cron-based Schedule**

A Cron-based Schedule uses Cron expressions to define execution times based on minutes, hours, days, or days of the week.

Example:

```text
cron(0 8 ? * MON *)
```

This expression represents 8:00 AM every Monday in the time zone configured for the Schedule.

Another useful feature is local time zone support. For example:

```text
Asia/Ho_Chi_Minh
```

This allows developers to configure schedules based on Vietnam local time without manually converting every execution time to UTC.

### 3. Key Features of EventBridge Scheduler

EventBridge Scheduler is more than just a timer. It also provides built-in mechanisms that improve system reliability and reduce operational overhead.

**3.1. No Need to Maintain a Server (Serverless)**

This is one of the most noticeable advantages of using EventBridge Scheduler.

Imagine an application that needs to execute a task for a few seconds every 30 minutes. If we use EC2, the instance may still need to run continuously even though it spends most of its time doing nothing.

With EventBridge Scheduler, AWS manages the underlying scheduling infrastructure. Developers only need to configure the Schedule and Target without operating a dedicated server.

This helps:

- Reduce server administration tasks.
- Eliminate the need to write programs that continuously check the time.
- Reduce idle infrastructure resources.
- Scale more easily as the number of schedules increases.

**3.2. Retry Policy – Automatically Retry Failed Invocations**

In real-world applications, a target service may temporarily become unavailable, experience request throttling, or fail to process a request.

EventBridge Scheduler supports Retry Policy to automatically retry failed target invocations.

Some important configuration limits include:

- The maximum retention time for an unprocessed event can be configured up to 24 hours.
- The maximum number of retry attempts can be configured up to 185.
- Retry attempts use exponential backoff to increase the waiting time between attempts.

This gives the system additional opportunities to complete a task when the target experiences a temporary failure.

**3.3. Dead-letter Queue (DLQ)**

If Scheduler still cannot deliver an event to the target after the configured retry attempts, developers can configure an Amazon SQS Queue as a Dead-letter Queue.

Events that cannot be delivered successfully are sent to the DLQ for further investigation and processing.

For example, a notification task may fail because the Lambda Function is temporarily unavailable. Instead of losing track of the event, its information can be stored in the DLQ so the development team can investigate the cause and take appropriate action.

**3.4. Flexible Time Window**

Imagine thousands of schedules configured to run at 12:00 AM. If all requests are sent to the target system at the same time, the system may experience a sudden increase in workload.

Flexible Time Window allows AWS to distribute invocations across a configured time window.

For example, if a five-minute window is selected, Scheduler can invoke the target within five minutes after the scheduled time.

This feature is suitable for tasks that do not require execution at an exact moment. If a task needs to run closer to its scheduled time, Flexible Time Window can be turned off.

**3.5. Time Zone Support and Centralized Management**

EventBridge Scheduler allows schedules to be managed through the AWS Management Console, AWS CLI, and SDKs.

Users can also select a local time zone when creating a schedule, such as `Asia/Ho_Chi_Minh`.

For projects with multiple automated tasks, Schedule Groups can be used to organize schedules by purpose:

- `development-schedules`
- `production-schedules`
- `notification-schedules`

This organization makes it easier to manage and monitor schedules as a project grows.

### 4. Practical Example: Automatically Invoking AWS Lambda Every 30 Minutes

Imagine that our project has a periodic data collection feature. Every 30 minutes, the system needs to invoke a Lambda Function to retrieve new data and update the database.

There are two possible approaches:

**4.1. Traditional Approach: Using EC2 and Crontab**

If we use EC2, we need to perform the following tasks:

1. Launch an EC2 instance and configure its operating system.
2. Install the required environment, such as Python, Node.js, or AWS CLI.
3. Write a script to invoke the Lambda Function.
4. Configure `crontab` to execute the script every 30 minutes.
5. Manage logs, troubleshoot failures, and maintain the server.
6. Attach an IAM Role to EC2 to grant permission to invoke Lambda.

This approach can work, but it requires maintaining a server continuously even when the actual task only takes a few seconds.

**4.2. Using EventBridge Scheduler**

With EventBridge Scheduler, the workflow becomes much simpler and can be configured directly through the AWS Management Console.

**Step 1: Create a Schedule**

Open the AWS Management Console, navigate to Amazon EventBridge, and select Scheduler to create a new Schedule.

Choose Recurring schedule, then select Rate-based schedule and enter:

```text
rate(30 minutes)
```

If the task needs to run according to Vietnam local time, select `Asia/Ho_Chi_Minh` in the Schedule configuration.

**Step 2: Select the Target**

Choose AWS Lambda as the target service and specify the Lambda Function that needs to be invoked.

**Step 3: Configure the Execution Role**

Create or select an IAM Execution Role that allows EventBridge Scheduler to invoke the Lambda Function.

AWS can help create the Role during the configuration process. However, developers should review the granted permissions and ensure that the Role only has the permissions it needs.

**Step 4: Configure Failure Handling**

Depending on project requirements, developers can configure:

- Retry Policy to automatically retry failed target invocations.
- Amazon SQS DLQ to store events that cannot be delivered successfully.
- Flexible Time Window when the task does not require execution at an exact scheduled time.

After completing the configuration, EventBridge Scheduler automatically invokes Lambda according to the defined schedule without requiring a dedicated EC2 instance.

**4.3. Monitoring the Execution**

To verify whether the system is working correctly, developers can use:

- **Amazon CloudWatch Metrics:** Monitor invocation counts, failed invocations, and other Scheduler-related metrics.
- **AWS Lambda Monitor:** Check invocation counts, execution duration, and Lambda errors.
- **CloudWatch Logs:** Inspect logs generated by the Lambda Function and any Scheduler logging that has been configured.
- **Amazon SQS DLQ:** Inspect events that could not be successfully delivered to the target service.

Regular monitoring helps detect failures early and ensures that automated tasks run as expected.

### 5. Important Considerations

**5.1. Pricing and Free Tier**

According to the AWS pricing page, EventBridge Scheduler provides up to 14 million free invocations per month. After the free usage allowance, charges are based on the number of invocations and the AWS Region being used.

For student labs, academic projects, and applications with a relatively small number of scheduled tasks, this free usage allowance is useful for experimentation.

However, developers should remember that target services such as Lambda, ECS, SQS, and CloudWatch may have their own charges. Therefore, the entire automation workflow should not be assumed to be completely free.

**5.2. EventBridge Scheduler vs. EventBridge Rules**

Previously, many developers used EventBridge Rules to create scheduled tasks. However, these two features serve different purposes:

- **EventBridge Scheduler:** Designed for independent scheduling tasks. It supports One-time, Rate, and Cron schedules, along with Retry Policy, DLQ, and Flexible Time Window.
- **EventBridge Rules:** Primarily designed to filter events on an Event Bus and route matching events to targets based on Event Patterns. Rules also support Scheduled Rules.

AWS recommends EventBridge Scheduler for new scheduling requirements because it provides more specialized scheduling features and scalability.

**5.3. Security and Operational Best Practices**

- Grant IAM Execution Roles only the minimum permissions required.
- Avoid disabling Retry Policy and DLQ without considering the importance of the scheduled task.
- Monitor CloudWatch Metrics to detect failed invocations.
- Delete or configure automatic deletion for completed One-time Schedules if they are no longer needed.
- Review the costs of both Scheduler and the target services it invokes.

### 6. Conclusion

Amazon EventBridge Scheduler is a small service that solves a very common application development problem: automatically executing tasks according to a schedule without maintaining a dedicated server.

With its integration with multiple AWS services, different scheduling options, Retry Policy, Dead-letter Queue, and Flexible Time Window, Scheduler simplifies the implementation of automation workflows.

For student projects and serverless applications, this is a service worth learning and applying. Instead of building a scheduling system from scratch, developers can use an AWS-managed service to reduce development time and focus more on the application's core logic.

Thank you for reading! If you have used EventBridge Scheduler in your own projects or have experience optimizing scheduled tasks on AWS, feel free to share your thoughts and practical experiences!

### 7. References

1. **AWS Documentation – What is Amazon EventBridge Scheduler?**
   https://docs.aws.amazon.com/scheduler/latest/UserGuide/what-is-scheduler.html

2. **AWS Documentation – Schedule Types on EventBridge Scheduler**
   https://docs.aws.amazon.com/scheduler/latest/UserGuide/schedule-types.html

3. **AWS Documentation – Getting Started with EventBridge Scheduler**
   https://docs.aws.amazon.com/scheduler/latest/UserGuide/getting-started.html

4. **AWS Documentation – Configuring Flexible Time Windows**
   https://docs.aws.amazon.com/scheduler/latest/UserGuide/managing-schedule-flexible-time-windows.html

5. **AWS Documentation – Managing a Schedule**
   https://docs.aws.amazon.com/scheduler/latest/UserGuide/managing-schedule.html

6. **AWS Pricing – Amazon EventBridge**
   https://aws.amazon.com/eventbridge/pricing/
