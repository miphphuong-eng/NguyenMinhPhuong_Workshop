
# Blog 1

# BUILDING A CI/CD PIPELINE ON AWS: INTEGRATING DEVSECOPS TO PERFORM SECURITY CHECKS BEFORE PRODUCTION DEPLOYMENT

In modern software development, deploying code to Production quickly is not enough. An application may run normally while still containing security vulnerabilities, vulnerable third-party dependencies, or insecure AWS configurations.

If security checks are only performed after an application has been deployed, identifying and resolving issues can take more time, increase costs, and potentially affect system operations.

One effective approach is to integrate **DevSecOps** into the CI/CD Pipeline on AWS. This approach introduces security checks throughout the development and deployment process, helping teams identify potential risks before an application reaches the Production environment.

### Architecture Overview

The CI/CD architecture integrated with DevSecOps uses multiple AWS services to automate application builds, security testing, deployment, and monitoring.

The main components include:

- **Git:** Manages source code and records changes made by developers.
- **AWS CodePipeline:** Orchestrates the entire CI/CD workflow.
- **AWS CodeCommit:** Stores the source code repository.
- **AWS CodeBuild:** Builds the application and performs security checks.
- **AWS CodeDeploy:** Deploys the application to the target environment.
- **Amazon S3 & AWS CodeArtifact:** Store build artifacts and dependencies required during the build and deployment process.
- **AWS Lambda:** Analyzes security scan results and helps process security findings.
- **AWS Security Hub:** Centralizes security findings from multiple sources.
- **AWS Config:** Monitors and evaluates AWS resource configurations.
- **Amazon ECS:** Runs the application in Staging and Production environments.

### CI/CD Workflow with DevSecOps

The workflow is divided into several stages to ensure that the application is properly checked before being released to Production.

**1. Commit – Pushing Source Code to Git**

When a developer completes a code change, the source code is committed and pushed to the repository.

- Git records changes made to the source code.
- AWS CodePipeline receives an event from the repository to trigger the pipeline.
- The build and testing stages are executed automatically.

**2. Build & Security Scan – Source Code Inspection**

AWS CodeBuild builds the application and integrates security testing tools into the process.

Two important security testing approaches are:

- **SCA (Software Composition Analysis):**
  - Examines third-party libraries and application dependencies.
  - Identifies dependency versions with known security vulnerabilities or risks.
- **SAST (Static Application Security Testing):**
  - Analyzes source code without executing the application.
  - Detects code patterns that may introduce security weaknesses.

The architecture illustrates tools such as Black Duck and SonarQube.

**3. Deploy – Deploying to the Staging Environment**

After the initial build and security checks are completed, the application is deployed to the Staging environment.

- AWS CodeDeploy manages the deployment process.
- Amazon ECS provides the environment in which the application runs.
- Staging serves as a testing environment before the application is released to Production.

**4. Test – Runtime Security Testing**

After deployment to Staging, the system continues performing security checks while the application is running.

- **DAST (Dynamic Application Security Testing):**
  - Tests a running application by sending requests and examining its responses.
  - Identifies vulnerabilities that may appear during application execution.
- **IAST (Interactive Application Security Testing):**
  - Analyzes application behavior during execution.
  - Helps identify security issues using information collected while the application is running.

The architecture illustrates tools such as Appknox and Veracode.

**5. Manual Approval & Production Deployment**

Before the application is officially released, the testing results must be collected and evaluated.

- Review detected security issues and warnings.
- Assess the risk level and identify problems that need to be resolved.
- Require Manual Approval before proceeding with Production deployment.
- If the application meets the required conditions, AWS CodeDeploy deploys it to Amazon ECS in the Production environment.

Adding a manual approval stage gives development and security teams better control over the release process.

### Security Monitoring and Control

In addition to source code and application testing, the system needs monitoring mechanisms to track activities and detect unexpected changes.

Several AWS services support this process:

- **AWS CloudTrail:** Records API activities and changes made within an AWS account.
- **AWS Config:** Monitors resource configurations and identifies changes that do not comply with requirements.
- **AWS Security Hub:** Aggregates security findings from multiple services to support risk assessment.
- **AWS Lambda:** Analyzes scan results and helps automate the handling of certain security findings.
- **Amazon CloudWatch Logs & Events:** Monitors logs, events, and pipeline execution status.

Combining these services gives DevOps and Security teams better visibility into the overall security status of the system.

### Configuration and Access Management

A secure CI/CD Pipeline must not only inspect source code but also control access permissions and protect application configuration information.

The key components include:

- **AWS IAM Role:**
  - Grants AWS services the permissions they need to perform their tasks.
  - Applies the Least Privilege principle by providing only the permissions required.
- **AWS Systems Manager Parameter Store:**
  - Stores and manages application configuration parameters.
  - Reduces the need to place configuration information directly in source code.
- **Amazon S3:**
  - Stores artifacts required for the build and deployment process.
- **Amazon SNS (Simple Notification Service):**
  - Sends Email notifications when pipeline activities or security checks generate events that require attention.

### Scenarios to Validate

To ensure that the pipeline works as expected, several practical scenarios should be tested:

- **Vulnerable dependencies:** SCA detects an insecure library and raises a warning before deployment.
- **Security issues in source code:** SAST identifies potential problems during the build stage.
- **Runtime application vulnerabilities:** DAST and IAST help identify issues in the Staging environment.
- **Insecure AWS configurations:** AWS Config records resources that do not meet configuration requirements.
- **Deployment failures:** CloudWatch Logs helps monitor and identify the causes of deployment errors.
- **Security risk findings:** Security Hub centralizes findings for DevOps and Security teams to review and address.

These scenarios help validate the pipeline's ability to detect, report, and control security risks throughout the workflow.

### What I Learned

From this DevSecOps-integrated CI/CD architecture, I gained a better understanding that security should be treated as an essential part of the software development process rather than a final check before release.

Some important lessons include:

- Integrate SCA and SAST into the build stage to identify dependency and source code issues early.
- Use DAST and IAST to inspect applications in a running environment.
- Deploy applications to Staging before releasing them to Production.
- Introduce Manual Approval to control important changes before release.
- Combine Security Hub, AWS Config, and CloudTrail to improve security monitoring and control.
- Apply IAM Least Privilege to reduce unnecessary access permissions.

The most important takeaway is that DevSecOps shifts security from post-deployment inspection to continuous security checks throughout the software development lifecycle.

As a result, organizations can identify vulnerabilities earlier, reduce potential risks, and improve application reliability before releasing software to the Production environment.

### Images

The following image illustrates an AWS CI/CD Pipeline integrated with DevSecOps tools and services to perform security checks, monitoring, and control before deploying an application to Production.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/aws-devsecops-cicd-pipeline.jpg" alt="AWS CI/CD Pipeline integrated with DevSecOps" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Figure 1 - AWS CI/CD Pipeline integrated with DevSecOps security checks before Production deployment</em></p>
</div>

### References

1. AWS CodePipeline: https://docs.aws.amazon.com/codepipeline/
2. AWS CodeBuild: https://docs.aws.amazon.com/codebuild/
3. AWS CodeDeploy: https://docs.aws.amazon.com/codedeploy/
4. AWS Security Hub: https://docs.aws.amazon.com/securityhub/
5. AWS Config: https://docs.aws.amazon.com/config/
6. AWS CloudTrail: https://docs.aws.amazon.com/cloudtrail/
7. Amazon ECS: https://docs.aws.amazon.com/ecs/
