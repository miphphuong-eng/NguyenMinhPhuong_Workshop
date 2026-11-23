
---
title: "1.9. Week 9 Worklog"
weight: 9
draft: false
---

## Week 9 Objectives

- Analyze project requirements and develop the team proposal for "IoT Weather Platform for Lab Research" to support the research activities of the ITea Lab team.
- Define the project scope, objectives, and expected users, including an initial deployment of 5 Raspberry Pi and ESP32 weather stations with the ability to expand to 15 stations.
- Design a unified AWS Serverless architecture using AWS IoT Core, AWS Lambda, Amazon S3, AWS Glue, API Gateway, AWS Amplify, and Amazon Cognito.
- Define the MQTT-based telemetry ingestion workflow between edge devices and the AWS cloud platform.
- Develop architecture diagrams illustrating both Edge Architecture and Platform Architecture.
- Estimate monthly operating costs using AWS Pricing Calculator and identify potential technical and financial risks with appropriate mitigation strategies.

## Weekly Activities

| Day | Tasks | Start Date | Completion Date | Learning Resources |
|---|---|---|---|---|
| Monday | Organize a team meeting to review and finalize the proposal requirements for "IoT Weather Platform for Lab Research". Analyze the limitations of existing weather monitoring systems, including manual data collection, fragmented storage, and limited real-time monitoring capabilities. Identify the target users, consisting of 5 ITea Lab researchers, and define the main project problems, objectives, scope, and expected outcomes. | 16/11/2026 | 16/11/2026 | [AWS IoT Core Overview](https://docs.aws.amazon.com/iot/latest/developerguide/what-is-aws-iot.html) |
| Tuesday | Design the telemetry data ingestion workflow from ESP32 sensors through Raspberry Pi edge devices to AWS IoT Core using the MQTT protocol. Study AWS IoT Core Rules for routing incoming messages to backend services. Design the Amazon S3 Data Lake structure to separate Raw and Processed data. Review the data flow and consider how the platform can support an expansion from 5 to 15 weather stations. | 17/11/2026 | 17/11/2026 | [AWS IoT Rules](https://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html) <br> [Building Data Lakes on AWS](https://aws.amazon.com/solutions/implementations/data-lake-solution/) |
| Wednesday | Research data processing and analytics using AWS Glue, including Glue Crawlers and Data Catalog for discovering and organizing datasets. Define the role of AWS Lambda in processing incoming data and supporting backend operations. Evaluate Amazon API Gateway for exposing backend APIs, AWS Amplify for hosting the Next.js dashboard, and Amazon Cognito for user authentication. Compare AWS CDK for Infrastructure as Code with AWS SDK for application-level service integration. | 18/11/2026 | 18/11/2026 | [AWS Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html) <br> [Amazon Cognito User Pools](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| Thursday | Develop the system architecture diagrams. Draw the Edge Architecture to illustrate the data flow from ESP32 sensors to Raspberry Pi devices running Docker containers and transmitting telemetry through MQTT over Wi-Fi. Draw the Platform Architecture to describe interactions between AWS IoT Core, S3, AWS Glue, Lambda, API Gateway, Amplify, and Cognito. Prepare a risk management matrix covering network interruptions, sensor failures, data loss, and budget overruns. Propose mitigation strategies such as local data buffering, retry mechanisms, and resource monitoring. | 19/11/2026 | 19/11/2026 | [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) |
| Friday | Estimate monthly operating costs using AWS Pricing Calculator. Review the estimated service costs for AWS Lambda, Amazon S3, AWS Amplify, AWS Glue, and AWS IoT Core. Consolidate the preliminary monthly cost estimate of approximately $0.70, equivalent to $8.40 per year, based on the assumed usage and configuration. Review the assumptions and identify services whose costs may increase with data volume or usage. Finalize the proposal documentation, organize architecture diagrams and cost estimates, and integrate the bilingual content into the Hugo structure under `content/2-Proposal/`. Verify the website rendering and documentation links. | 20/11/2026 | 20/11/2026 | [AWS Pricing Calculator](https://calculator.aws/) |

## Week 9 Achievements

- Developed the team proposal for "IoT Weather Platform for Lab Research" to address the limitations of manual weather monitoring and fragmented data management.
- Defined the project scope for an initial deployment of 5 Raspberry Pi and ESP32 weather stations, with the capability to scale to 15 stations.
- Designed a proposed AWS Serverless architecture integrating AWS IoT Core, Amazon S3 Data Lake, AWS Glue, Lambda, API Gateway, Amplify, and Cognito.
- Established the MQTT-based telemetry ingestion workflow between edge devices and the AWS cloud platform.
- Produced architecture diagrams illustrating both Edge Architecture and Platform Architecture.
- Developed a risk management matrix addressing network interruptions, sensor failures, data loss, and budget overruns, including proposed mitigation strategies.
- Prepared a preliminary monthly infrastructure cost estimate of approximately $0.70 using AWS Pricing Calculator, subject to the defined usage assumptions.
- Organized and integrated the bilingual Proposal documentation into the Hugo platform under `content/2-Proposal/`.
