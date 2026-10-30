
---
title: "1.3. Week 3 Worklog"
weight: 3
draft: false
---

## Week 3 Objectives

- Gain an in-depth understanding of Amazon S3 Object Storage, Bucket structures, Object Keys, Metadata, and Versioning.
- Differentiate S3 Storage Classes (Standard, Intelligent-Tiering, Standard-IA, and Glacier) to optimize data storage costs.
- Master S3 security best practices, including Block Public Access, Bucket Policies, ACLs, and Server-Side Encryption (SSE-S3 and SSE-KMS).
- Understand the core components of AWS Identity and Access Management (IAM), including Users, Groups, Roles, and Policies.
- Understand and apply the Principle of Least Privilege to AWS access management.
- Integrate the AWSSDK.S3 library into a C#/.NET Backend application.
- Implement file upload, download, and deletion operations using Amazon S3.
- Implement Pre-signed URLs for secure, time-limited file sharing.
- Learn and configure CORS to allow Frontend applications to communicate with Amazon S3.
- Configure S3 Lifecycle Policies to automatically manage object lifecycles and clean up unused data.

---

## Weekly Activities

| Day | Activities | Start Date | End Date | References |
| :---: | :--- | :---: | :---: | :--- |
| **Monday** | - Explore Amazon S3 and perform hands-on exercises on Object Storage fundamentals.<br>- Practice creating S3 Buckets and uploading Objects.<br>- Learn about Object Keys and how to manage Object Metadata.<br>- Enable and test Object Versioning to manage multiple versions of stored data.<br>- Analyze S3 Storage Classes, including Standard, Intelligent-Tiering, Standard-IA, and Glacier.<br>- Compare the characteristics, use cases, and costs of each storage class. | 05/10/2026 | 05/10/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)<br>[S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/) |
| **Tuesday** | - Study data security mechanisms in Amazon S3.<br>- Practice enabling Block Public Access to prevent accidental exposure of data to the Internet.<br>- Explore how Bucket Policies and Access Control Lists (ACLs) work.<br>- Write JSON-based Bucket Policies to control access to S3 resources.<br>- Learn about Encryption at Rest.<br>- Practice configuring Server-Side Encryption using SSE-S3 and SSE-KMS.<br>- Verify access permissions and encryption settings for Objects stored in the Bucket. | 06/10/2026 | 06/10/2026 | [Amazon S3 Security](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html)<br>[S3 Bucket Policies](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-policies.html) |
| **Wednesday** | - Study the fundamentals of AWS Identity and Access Management (IAM).<br>- Differentiate IAM components, including Users, Groups, Roles, and Policies.<br>- Learn the Principle of Least Privilege in Cloud security management.<br>- Practice creating a dedicated IAM User for the Backend application.<br>- Create a JSON-based IAM Policy with specifically restricted permissions, such as `s3:GetObject` and `s3:PutObject`.<br>- Verify the IAM User's access permissions and ensure the application can only perform authorized operations.<br>- Learn how to securely manage AWS credentials. | 07/10/2026 | 07/10/2026 | [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)<br>[IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) |
| **Thursday** | - Learn how to integrate the AWSSDK.S3 library into C#/.NET Backend projects.<br>- Install and configure the AWSSDK.S3 package in the project.<br>- Build an S3Service class to manage Amazon S3 operations.<br>- Implement `PutObjectAsync`, `GetObjectAsync`, and `DeleteObjectAsync` methods to support Object upload, download, and deletion.<br>- Learn and implement Pre-signed URLs to share private Objects without making the Bucket publicly accessible.<br>- Configure Pre-signed URLs with an expiration time of 15–30 minutes.<br>- Learn how to manage AWS Access Keys and Secret Keys through Environment Variables to reduce the risk of credential exposure. | 08/10/2026 | 08/10/2026 | [AWS SDK for .NET S3 Guide](https://docs.aws.amazon.com/sdk-for-net/v3/developer-guide/s3-index.html)<br>[Pre-signed URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/ShareObjectPreSignedURL.html) |
| **Friday** | - Perform testing and troubleshoot issues encountered when integrating Amazon S3 with Backend and Frontend applications.<br>- Diagnose and fix CORS errors when the Frontend browser uses Pre-signed URLs to upload files to S3.<br>- Configure S3 Bucket CORS Rules with appropriate AllowedOrigins and AllowedMethods.<br>- Test browser-based file uploads after configuring CORS.<br>- Configure S3 Lifecycle Rules to automatically delete unused temporary files in the `temp/` folder after 7 days.<br>- Review security policies, IAM permissions, and Object management functions.<br>- Capture screenshot evidence, summarize practical results, and complete the Week 3 Worklog. | 09/10/2026 | 09/10/2026 | [S3 CORS Configuration](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html)<br>[S3 Lifecycle Management](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html) |

---

## Week 3 Achievements

- Gained an in-depth understanding of Amazon S3 Object Storage, Bucket structures, Objects, Metadata, and Versioning.
- Differentiated S3 Storage Classes and understood how to select suitable storage classes to optimize performance and costs.
- Practiced creating S3 Buckets, uploading Objects, managing Metadata, and checking data versions.
- Understood Amazon S3 security mechanisms, including Block Public Access, Bucket Policies, and ACLs.
- Practiced writing JSON-based Bucket Policies to control access to S3 resources.
- Understood and configured Encryption at Rest using Server-Side Encryption, including SSE-S3 and SSE-KMS.
- Mastered the core components of AWS IAM, including Users, Groups, Roles, and Policies.
- Understood and applied the Principle of Least Privilege to restrict access according to the application's actual requirements.
- Practiced creating IAM Users and configuring JSON Policies with specifically restricted S3 permissions.
- Successfully integrated the AWSSDK.S3 library into a C#/.NET Backend project.
- Built an S3Service class supporting Object upload, download, and deletion through asynchronous methods.
- Implemented Pre-signed URLs to securely share private Objects without making the S3 Bucket publicly accessible.
- Understood how to manage AWS Access Keys and Secret Keys through Environment Variables.
- Learned and configured CORS to allow Frontend applications to communicate with Amazon S3.
- Practiced troubleshooting CORS-related errors when using Pre-signed URLs for S3 file uploads.
- Configured S3 Lifecycle Rules to automatically manage and clean up temporary files after a specified period.
- Improved skills in integrating Cloud storage services with C#/.NET Backend applications while strengthening knowledge of AWS security and data management.
