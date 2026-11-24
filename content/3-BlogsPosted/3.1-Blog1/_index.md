
---
title: "Blog 1"
date: 2026-11-23
weight: 1
chapter: false
pre: "<b> 3.1. </b>"
---

# BUILDING A CI/CD PIPELINE ON AWS: INTEGRATING DEVSECOPS TO PERFORM SECURITY CHECKS BEFORE PRODUCTION DEPLOYMENT

In modern software development, deploying source code to a Production environment quickly is no longer enough. An application may function normally while still containing security vulnerabilities, unsafe third-party dependencies, or AWS configurations that have not been properly secured.

If security checks are only performed after an application has been deployed, identifying and fixing issues can take more time, increase costs, and potentially affect system operations.

An effective solution is to integrate **DevSecOps** into the CI/CD Pipeline on AWS. This approach incorporates security checks throughout the development and deployment process, helping teams identify potential risks before the application is released to the Production environment.

### Architecture Overview

The CI/CD architecture integrated with DevSecOps uses multiple AWS services to automate application building, security testing, deployment, and system monitoring.

The main components include:

- **Git:** Manages source code and tracks changes made by developers.
- **AWS CodePipeline:** Orchestrates the entire CI/CD workflow.
- **AWS CodeCommit:** Stores the repository containing the application's source code.
- **AWS CodeBuild:** Builds the application and performs security checks.
- **AWS CodeDeploy:** Deploys the application to the target environment.
- **Amazon S3 & AWS CodeArtifact:** Store build artifacts and dependencies required during the build and deployment processes.
- **AWS Lambda:** Analyzes security scan results and supports the handling of security findings.
- **AWS Security Hub:** Aggregates security findings from multiple sources.
- **AWS Config:** Monitors and evaluates the configurations of AWS resources.
- **Amazon ECS:** Runs the application in Staging and Production environments.

### CI/CD Process Integrated with DevSecOps

The workflow is divided into several stages to ensure that the application is properly checked before being released to the Production environment.

**1. Commit – Push Source Code to Git**

When developers complete a source code change, they commit and push the changes to the repository.

- Git records changes made to the source code.
- AWS CodePipeline receives an event from the repository to trigger the pipeline.
- The build and testing stages are executed automatically.

**2. Build & Security Scan – Source Code Inspection**

AWS CodeBuild builds the application and integrates security testing tools into the workflow.

Two important security testing methods include:

- **SCA (Software Composition Analysis):**
  - Checks third-party libraries and dependencies used by the application.
  - Identifies dependency versions with known security vulnerabilities or potential risks.
- **SAST (Static Application Security Testing):**
  - Analyzes source code without executing the application.
  - Detects code patterns or programming practices that may introduce security weaknesses.

In the illustrated architecture, the tools used include Black Duck and SonarQube.

**3. Deploy – Deployment to the Staging Environment**

After the initial build and security checks are completed, the application is deployed to the Staging environment.

- AWS CodeDeploy manages the deployment process.
- Amazon ECS provides the environment in which the application runs.
- Staging acts as a testing environment before the application is released to Production.

**4. Test – Security Testing During Application Runtime**

After deployment to Staging, the system continues performing security checks while the application is running.

- **DAST (Dynamic Application Security Testing):**
  - Tests a running application by sending requests and analyzing the responses.
  - Identifies vulnerabilities that may appear during application execution.
- **IAST (Interactive Application Security Testing):**
  - Analyzes application behavior during runtime.
  - Helps detect security issues based on information collected while the application is operating.

In the illustrated architecture, the tools used include Appknox and Veracode.

**5. Manual Approval & Production Deployment**

Before the application is officially released, the testing results must be collected and evaluated.

- Review identified security issues and warnings.
- Assess risk levels and determine which issues need to be fixed.
- Require Manual Approval before proceeding with Production deployment.
- If the application meets the necessary requirements, AWS CodeDeploy deploys it to Amazon ECS in the Production environment.

Adding a manual approval stage helps development and security teams maintain better control over the application release process.

### Security Monitoring and Control

In addition to source code and application testing, the system needs monitoring mechanisms to track activities and detect unusual changes.

Several AWS services support this process:

- **AWS CloudTrail:** Records API activities and changes made within the AWS account.
- **AWS Config:** Monitors resource configurations and identifies changes that do not comply with established requirements.
- **AWS Security Hub:** Aggregates security findings from multiple services to support risk assessment.
- **AWS Lambda:** Analyzes scan results and helps automate the handling of certain security findings.
- **Amazon CloudWatch Logs & Events:** Monitors logs, events, and the execution status of the pipeline.

Combining these services gives DevOps and Security teams a more comprehensive view of the system's security status.

### Configuration and Access Management

A secure CI/CD Pipeline requires more than source code inspection. It must also control access permissions and protect application configuration information.

Important components include:

- **AWS IAM Role:**
  - Grants AWS services the permissions required to perform their tasks.
  - Applies the Least Privilege principle by granting only the permissions that are actually necessary.
- **AWS Systems Manager Parameter Store:**
  - Stores and manages application configuration parameters.
  - Reduces the need to place configuration information directly in source code.
- **Amazon S3:**
  - Stores artifacts required during the build and deployment processes.
- **Amazon SNS (Simple Notification Service):**
  - Sends Email notifications when pipeline activities or security checks generate events that require attention.

### Scenarios to Validate

To ensure that the pipeline works as expected, several practical scenarios should be tested:

- **Vulnerable Dependencies:** SCA detects an unsafe library and generates a warning before deployment.
- **Source Code Security Issues:** SAST identifies potential security problems during the build stage.
- **Runtime Application Vulnerabilities:** DAST and IAST help detect issues in the Staging environment.
- **Insecure AWS Configurations:** AWS Config records resources that do not meet the required configuration standards.
- **Deployment Failure:** CloudWatch Logs helps monitor and identify the causes of deployment errors.
- **Security Risk Detection:** Security Hub aggregates findings so that DevOps and Security teams can review and resolve them.

These scenarios help evaluate the pipeline's ability to detect, report, and control security risks throughout its operation.

### What I Learned

Through this CI/CD architecture integrated with DevSecOps, I gained a better understanding that security should be considered an essential part of the software development process rather than simply a final check before release.

Some important lessons include:

- Integrating SCA and SAST into the build stage to detect dependency and source code issues early.
- Using DAST and IAST to test applications in a running environment.
- Deploying applications to Staging before releasing them to Production.
- Adding Manual Approval to control important changes before release.
- Combining Security Hub, AWS Config, and CloudTrail to improve security monitoring and control.
- Applying the IAM Least Privilege principle to limit unnecessary access permissions.

The most important lesson I learned is that DevSecOps changes the security approach from checking applications only after deployment to performing continuous security checks throughout the software development lifecycle.

As a result, organizations can identify vulnerabilities earlier, reduce potential risks, and improve application reliability before releasing software to the Production environment.

### Images

The image below illustrates an AWS CI/CD Pipeline architecture integrated with DevSecOps tools and services to perform security testing, monitoring, and control before deploying an application to the Production environment.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/aws-devsecops-cicd-pipeline.jpg" alt="AWS CI/CD Pipeline integrated with DevSecOps" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Figure 1 - AWS CI/CD Pipeline integrated with DevSecOps for security checks before Production deployment</em></p>
</div>

### References

1. AWS CodePipeline: https://docs.aws.amazon.com/codepipeline/
2. AWS CodeBuild: https://docs.aws.amazon.com/codebuild/
3. AWS CodeDeploy: https://docs.aws.amazon.com/codedeploy/
4. AWS Security Hub: https://docs.aws.amazon.com/securityhub/
5. AWS Config: https://docs.aws.amazon.com/config/
6. AWS CloudTrail: https://docs.aws.amazon.com/cloudtrail/
7. Amazon ECS: https://docs.aws.amazon.com/ecs/
