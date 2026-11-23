---
title: "Week 10 Worklog"
date: 2026-11-23
weight: 10
chapter: false
pre: "<b> 1.10. </b>"
---

# Week 10 Worklog

### Week 10 Objectives

- Configure AWS IoT Core Topic Rules to automatically store edge telemetry into Amazon S3 Raw Data Lake Buckets.
- Build AWS Lambda functions (Python/Node.js) to handle backend logic and configure Amazon API Gateway RESTful endpoints.
- Configure AWS Glue Crawlers to automatically catalog S3 schemas and create Glue ETL Jobs for transforming raw data into analytical Parquet format.
- Deploy a Next.js Web Dashboard onto AWS Amplify and integrate Amazon Cognito User Pools for researcher authentication.
- Research scalable cloud architecture patterns (Amazon ECS Fargate, ALB, Aurora Serverless v2, and ElastiCache) in preparation for technical blogging.

### Tasks Completed During the Week

| **Day** | **Tasks** | **Start Date** | **Completion Date** | **Learning Resources** |
| :--- | :--- | :--- | :--- | :--- |
| Monday | - Configure AWS IoT Core Rule subscribing to topic `lab/weather/telemetry`.<br>- Configure S3 action to write JSON payloads directly into Amazon S3 Raw Bucket, partitioned by `year=YYYY/month=MM/day=DD/`.<br>- Test publishing simulated MQTT messages and verify automated S3 object creation. | 23/11/2026 | 23/11/2026 | [AWS IoT S3 Action](https://docs.aws.amazon.com/iot/latest/developerguide/s3-rule-action.html)<br>[AWS IoT Rule Tutorial](https://docs.aws.amazon.com/iot/latest/developerguide/iot-write-to-s3.html) |
| Tuesday | - Develop an AWS Lambda function to query the latest weather telemetry data.<br>- Create an Amazon API Gateway REST API integrating with Lambda through GET `/api/weather/latest`.<br>- Configure CORS headers and verify endpoint responses using Postman. | 24/11/2026 | 24/11/2026 | [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)<br>[API Gateway Integration](https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started-with-lambda-integrations.html) |
| Wednesday | - Create an AWS Glue Crawler to inspect the S3 Raw Bucket and extract schema metadata into AWS Glue Data Catalog.<br>- Develop a PySpark Glue ETL Job to filter telemetry noise and export data to the S3 Processed Bucket in compressed Parquet format.<br>- Execute the Glue Job and verify transformed datasets in S3. | 25/11/2026 | 25/11/2026 | [AWS Glue Crawlers](https://docs.aws.amazon.com/glue/latest/dg/add-crawler.html)<br>[AWS Glue ETL Jobs](https://docs.aws.amazon.com/glue/latest/dg/author-job.html) |
| Thursday | - Create an Amazon Cognito User Pool named `WeatherLabUserPool` and configure App Client credentials.<br>- Deploy the Next.js Web Dashboard to AWS Amplify through Git repository integration.<br>- Integrate Amplify Auth SDK into the Next.js dashboard to secure weather monitoring views. | 26/11/2026 | 26/11/2026 | [AWS Amplify Hosting](https://docs.aws.amazon.com/amplify/latest/userguide/welcome.html)<br>[Amplify Authentication](https://docs.amplify.aws/lib/auth/getting-started/q/platform/js/) |
| Friday | - **Research & Lab Practice on Scalable Web Application Architecture:**<br>- Analyze scalability challenges in high-traffic e-commerce systems.<br>- Study and perform hands-on testing of the end-to-end traffic flow: Route 53 → CloudFront → AWS WAF → ALB → Amazon ECS Fargate → ElastiCache → Aurora Serverless v2.<br>- Collect AWS Solutions Guidance references and prepare technical content for Technical Blog 1. | 27/11/2026 | 27/11/2026 | [AWS Web Store Guidance](https://docs.aws.amazon.com/solutions/web-store-on-aws/)<br>[Amazon ECS Fargate](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html) |

### Week 10 Achievements

- Configured AWS IoT Core Rules to automatically capture MQTT telemetry and store raw JSON objects in partitioned Amazon S3 buckets.
- Developed AWS Lambda backend logic and Amazon API Gateway endpoints to provide weather telemetry data to web clients.
- Implemented AWS Glue Crawlers and Glue ETL Jobs to transform raw IoT data into optimized analytical Parquet files stored in S3.
- Deployed a Next.js frontend application on AWS Amplify and integrated Amazon Cognito User Pools for user authentication.
- Improved understanding of enterprise-scale cloud architectures involving Amazon ECS Fargate, Application Load Balancer (ALB), Aurora Serverless v2, and ElastiCache.
- Prepared architectural diagrams and technical references for Technical Blog 1: Scalable E-Commerce Architecture.
