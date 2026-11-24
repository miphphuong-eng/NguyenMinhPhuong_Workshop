
---
title: "Blog 2"
date: 2026-11-24
weight: 2
chapter: false
pre: "<b> 3.2. </b>"
---

# AMAZON S3 – A STORAGE AND DATA SECURITY SOLUTION ON AWS

In the digital transformation era, data plays an essential role in the operation of businesses and modern information technology systems. From websites and mobile applications to Artificial Intelligence systems, almost every modern application requires a storage solution that is secure, flexible, and scalable.

However, as data continues to grow, traditional storage systems may introduce several challenges, including hardware investment costs, storage capacity limitations, scalability issues, and infrastructure maintenance.

To address these challenges, Amazon Web Services (AWS) provides **Amazon Simple Storage Service (Amazon S3)**. It is an object storage service that allows users to store and retrieve data with flexible scalability.

In this article, we will explore what Amazon S3 is, its Storage Classes, important data management and security features, and how S3 can be used in Data & Machine Learning architectures on AWS.

### 1. What is Amazon S3?

Amazon Simple Storage Service (Amazon S3) is an object storage service provided by Amazon Web Services.

Amazon S3 allows users to store and retrieve data through the Internet, AWS Management Console, AWS CLI, and supported APIs without directly managing physical storage infrastructure.

Data stored in Amazon S3 can include:

- Images and videos.
- PDF, Word, and Excel documents.
- Data backup files.
- Datasets for Machine Learning and Artificial Intelligence.
- Static website files such as HTML, CSS, and JavaScript.
- System logs and analytics data.

One of the main advantages of Amazon S3 is its ability to scale according to storage requirements. Instead of purchasing additional hard drives or servers when data volume increases, users can rely on AWS-managed storage infrastructure and pay based on actual usage.

In addition, S3 Standard is designed to provide 99.999999999% (11 nines) of data durability. This is a data durability figure, not a guarantee of 100% service availability.

### 2. Basic Components of Amazon S3

To understand how Amazon S3 works, we need to become familiar with three important concepts: Bucket, Object, and Object Key.

**2.1. Bucket**

A Bucket is a container used to store Objects in Amazon S3.

It can be understood as a dedicated storage area for the data of an application or system.

For example, an image management application may use a Bucket named:

`my-image-storage-demo`

Inside this Bucket, users can store profile pictures, product images, documents, and other types of data.

When creating an S3 Bucket, users need to select an appropriate AWS Region based on data location and system requirements.

**2.2. Object**

An Object is an individual unit of data stored in Amazon S3.

Each Object typically contains the actual file data and related descriptive information (Metadata).

Examples include:

- `avatar.jpg`
- `report.pdf`
- `dataset.csv`
- `backup.zip`

Unlike traditional disk-based storage systems, Amazon S3 uses an Object Storage model, where data is accessed through APIs and Object identifiers.

**2.3. Object Key**

An Object Key is the unique identifier of an Object within a Bucket.

For example:

`images/profile/avatar.jpg`

In this case, `images/profile/avatar.jpg` is the Object Key.

Although this naming structure looks similar to a traditional folder path, Amazon S3 primarily uses prefixes within Object Keys to organize data rather than a traditional physical directory structure.

This makes it easier for users to categorize, search, and manage their data.

### 3. Amazon S3 Storage Classes

Not all data needs to be accessed with the same frequency.

For example, product images on a website may be accessed every day, while backup files from several years ago may only be used when the system needs to be restored.

Amazon S3 provides multiple Storage Classes to support different storage requirements.

**3.1. Amazon S3 Storage Hierarchy**

Amazon S3 Storage Classes can be grouped according to data access frequency and retrieval requirements:

- **Frequently Accessed:** Data that is accessed regularly and requires low latency.
- **Infrequently Accessed:** Data that is accessed less frequently but still requires fast retrieval when needed.
- **Archive:** Long-term data storage for information that is rarely accessed and can tolerate longer retrieval times.

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/s3-storage-hierarchy.png" alt="Amazon S3 Storage Hierarchy" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Figure 1 - Amazon S3 storage hierarchy based on data access requirements.</em></p>
</div>

**3.2. Overview of the 8 Amazon S3 Storage Classes**

Amazon S3 provides multiple Storage Classes that users can select based on their requirements.

| Storage Class | Characteristics | Common Use Cases |
|---|---|---|
| S3 Standard | Designed for frequently accessed data | Websites, images, application data |
| S3 Intelligent-Tiering | Automatically optimizes storage tiers based on access patterns | Data with unpredictable access frequency |
| S3 Standard-IA | Infrequently accessed data requiring fast retrieval | Backups and long-term storage |
| S3 One Zone-IA | Stores data in a single Availability Zone | Re-creatable data |
| S3 Glacier Instant Retrieval | Rarely accessed data that still requires fast retrieval | Images and long-term records |
| S3 Glacier Flexible Retrieval | Long-term storage with flexible retrieval times | Backups and periodic archives |
| S3 Glacier Deep Archive | Designed for rarely accessed data stored over many years | Historical records and long-term archives |
| S3 Express One Zone | High-performance storage in a single Availability Zone | Applications requiring very low access latency |

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/s3-storage-classes.png" alt="Overview of 8 Amazon S3 Storage Classes" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Figure 2 - Overview of the eight Amazon S3 Storage Classes and their common use cases.</em></p>
</div>

Some important considerations when selecting a Storage Class:

- S3 Standard is suitable for frequently accessed data.
- S3 Intelligent-Tiering is useful when access frequency cannot be accurately predicted.
- S3 Standard-IA and One Zone-IA are suitable for infrequently accessed data that still requires fast retrieval.
- S3 Glacier Instant Retrieval is suitable for long-term data that still needs immediate access.
- S3 Glacier Flexible Retrieval and Deep Archive are designed for long-term storage where longer retrieval times are acceptable.
- S3 Express One Zone is suitable for applications requiring very low data access latency.

Choosing the right Storage Class can help optimize costs. However, users should also consider retrieval fees, request charges, minimum storage duration, and data recovery requirements.

In particular, S3 One Zone-IA and S3 Express One Zone store data in a single Availability Zone. Therefore, availability and fault tolerance requirements should be evaluated before using these classes.

### 4. Important Amazon S3 Features

Besides providing storage capabilities, Amazon S3 offers several features that help manage data lifecycles and improve security.

**4.1. S3 Versioning**

S3 Versioning is a feature that allows multiple versions of an Object to be stored within the same Bucket.

For example, consider a file named:

`project-report.pdf`

After updating the report, a user uploads a new version using the same Object Key.

When Versioning is enabled, S3 can retain both the previous and new versions.

This feature is particularly useful when:

- Data is accidentally overwritten.
- An Object is deleted by mistake.
- A previous version needs to be restored.
- Changes to stored data need to be tracked.

However, previous versions may continue generating storage costs. Therefore, Versioning should be combined with Lifecycle Rules to manage data effectively.

**4.2. S3 Lifecycle Rules**

S3 Lifecycle Rules allow users to automatically manage the lifecycle of Objects based on predefined rules.

For example, a log storage system may use the following policy:

- During the first 30 days: Store data in S3 Standard.
- After 30 days: Transition data to a Storage Class suitable for less frequent access.
- After the retention period expires: Automatically delete data according to the configured policy.

By using Lifecycle Rules, organizations can reduce manual management tasks and optimize storage costs.

**4.3. S3 Encryption**

Data security is one of the most important considerations when using Cloud Storage.

Amazon S3 supports data encryption to protect information at rest (Encryption at Rest).

Some common encryption methods include:

- **SSE-S3:** Amazon S3 manages the encryption keys. This is the default encryption method for new Objects uploaded to S3.
- **SSE-KMS:** Uses AWS Key Management Service (AWS KMS) to manage encryption keys and provide additional control.
- **SSE-C:** Users provide encryption keys with requests, while Amazon S3 performs the encryption and decryption operations.

The appropriate encryption method depends on security requirements and organizational key management policies.

**4.4. S3 Block Public Access**

One common security risk when using Cloud Storage is accidentally allowing public access to private data.

Amazon S3 provides Block Public Access to help prevent configurations that could unintentionally expose Buckets or Objects to the public.

This feature helps control:

- Public ACLs.
- Public Bucket Policies.
- Configurations that could allow public access.

For newly created Buckets, Block Public Access settings are enabled by default.

**Recommendation:** Keep Block Public Access enabled unless there is a specific requirement and the associated security risks have been properly evaluated.

For applications that need to deliver images or data to external users, solutions such as Amazon CloudFront with Origin Access Control or Presigned URLs can be considered.

### 5. Basic Guide: Creating and Managing an Amazon S3 Bucket

After understanding the concepts, we can practice creating a Bucket and uploading data to Amazon S3.

**Requirements:** An AWS account or an AWS environment with permission to use Amazon S3.

**Step 1: Access the AWS Management Console**

- Sign in to the AWS Management Console.
- Search for Amazon S3.
- Select Buckets to view the existing Bucket list.

**Step 2: Create an S3 Bucket**

Select Create bucket and enter the required information:

- **Bucket name:** Enter a unique name following S3 naming rules.
- **AWS Region:** Select an appropriate storage region.
- **Object Ownership:** Keep the default settings unless specific requirements exist.
- **Block Public Access:** Keep enabled to prevent unintended public access.
- **Versioning:** Optionally enable it to explore multiple Object versions.

After reviewing the configuration, select Create bucket.

**Step 3: Upload Data**

- Open the newly created Bucket.
- Select Upload.
- Choose a test file that does not contain personal or sensitive information, such as `demo.txt`.
- Select Upload to start the process.

After the upload is completed, the Object will appear in the Bucket's object list.

**Step 4: Check Object Information**

Select the uploaded Object to review:

- Object Key.
- Object Size.
- Storage Class.
- Metadata.
- Encryption.
- Version ID if Versioning is enabled.

**Step 5: Check Access Permissions**

If Block Public Access is enabled, having an Object URL does not mean that everyone on the Internet can access the data.

Users need appropriate permissions through IAM Policies, Bucket Policies, or other authorized access mechanisms.

This is an important concept to remember when developing applications that use Amazon S3.

**Step 6: Clean Up Test Resources**

After completing the practice:

- Delete unnecessary test Objects.
- Check previous versions if Versioning is enabled.
- Check Delete Markers.
- Delete the Bucket after it has been completely emptied.

Cleaning up resources helps prevent unnecessary storage costs.

**Note:** Perform these operations only in an authorized AWS environment and carefully review the data before deleting anything.

### 6. Real-World Application: Amazon S3 in Data & Machine Learning Architecture

Besides common storage applications, Amazon S3 also plays an important role in data processing and Machine Learning systems.

For example, a company wants to build an AI system capable of recognizing and classifying images.

In this scenario, Amazon S3 can be used to store input data, training datasets, models, and processing results.

A sample data structure may look like this:

```text
my-ai-dataset/
|
|-- raw-data/
|   |-- image_001.jpg
|   |-- image_002.jpg
|
|-- processed-data/
|   |-- image_001_processed.jpg
|
|-- train/
|   |-- training-data.csv
|
|-- validation/
|   |-- validation-data.csv
|
|-- models/
|   |-- model_v1.pth
|
|-- results/
    |-- predictions.csv
```

<div style="text-align: center; margin: 20px 0;">
  <img src="/NguyenMinhPhuong_Workshop/images/aws-data-ml-architecture.png" alt="Data and Machine Learning Architecture on AWS Cloud" style="width: 90%; max-width: 850px; border-radius: 8px;">
  <p><em>Figure 3 - Data & Machine Learning architecture on AWS Cloud using Amazon S3 for data storage and management.</em></p>
</div>

In this architecture, different components can work together as follows:

- **Amazon S3:** Stores raw data, processed data, training datasets, and output results.
- **AWS Glue:** Supports data discovery, preparation, and processing.
- **Amazon SageMaker:** Supports building, training, and deploying Machine Learning models.
- **AWS Lambda:** Can trigger processing tasks when new Objects are uploaded to S3.
- **Amazon CloudWatch:** Monitors system activities and the status of different components.

For example, when a user uploads a new image to S3, an event can trigger AWS Lambda to start a data processing task. The processed data can then be used in a training or prediction workflow with Amazon SageMaker.

After the process is completed, the model and prediction results can be stored back in Amazon S3 for evaluation and future use.

It is important to understand that Amazon S3 does not directly perform AI model training. S3 provides the storage layer, while processing and training tasks are performed by appropriate computing services.

### 7. Important Considerations When Using Amazon S3

To use Amazon S3 effectively, several factors should be considered:

**Data Security:**

- Avoid making Buckets containing private data publicly accessible.
- Apply the Least Privilege principle when assigning IAM permissions.
- Use Encryption to protect stored data.
- Regularly review Bucket Policies and Block Public Access settings.

**Cost Optimization:**

- Select Storage Classes based on actual access frequency.
- Use Lifecycle Rules to automate storage transitions.
- Monitor request, retrieval, and data transfer charges.
- Review older Object versions when Versioning is enabled.

**Data Management:**

- Organize Object Keys using a clear naming structure.
- Enable Versioning when data recovery is important.
- Configure appropriate data retention and deletion policies.

**System Design:**

- Select an appropriate AWS Region.
- Identify latency and availability requirements.
- Integrate Amazon S3 with other AWS services when building Data & AI systems.

### 8. What I Learned

Through exploring Amazon S3, I gained a better understanding of the role of Cloud Storage in building and operating modern technology systems.

Some important lessons include:

- Understanding how Amazon S3 organizes data through Buckets, Objects, and Object Keys.
- Distinguishing between Storage Classes and selecting appropriate classes based on access requirements.
- Understanding how Versioning helps recover data when unexpected problems occur.
- Using Lifecycle Rules to automate data lifecycle management and optimize storage costs.
- Understanding the roles of Encryption and Block Public Access in protecting data.
- Learning how to create Buckets, upload Objects, and inspect data information through the AWS Management Console.
- Understanding how Amazon S3 integrates into Data & Machine Learning architectures.

The most important lesson I learned is that choosing a storage service is not simply about finding a place to store data. We also need to consider how data is accessed, protected, managed, and optimized throughout its lifecycle.

Amazon S3 is a fundamental service for building Cloud Computing knowledge and exploring more advanced AWS architectures.

### 9. Conclusion

Amazon S3 is one of the fundamental storage services provided by Amazon Web Services.

With its Object Storage model, scalability, multiple Storage Classes, and features such as Versioning, Lifecycle Rules, Encryption, and Block Public Access, Amazon S3 can support many different storage requirements, ranging from frequently accessed application data to datasets that need to be retained for several years.

By learning and practicing with Amazon S3, we can better understand how data is organized, stored, managed, and protected in a Cloud Computing environment.

**Discussion Question:** When designing a system for storing large amounts of data, what factors should we consider when choosing between S3 Standard, S3 Intelligent-Tiering, and the S3 Glacier storage classes?

I look forward to exchanging ideas and learning more from the AWS Study Group community!

### 10. References

1. AWS Documentation – What is Amazon S3?
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html

2. AWS Documentation – Amazon S3 Storage Classes
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html

3. AWS Documentation – Managing the Lifecycle of Objects
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html

4. AWS Documentation – Using Versioning in S3 Buckets
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html

5. AWS Documentation – Protecting Data with Encryption
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingEncryption.html

6. AWS Documentation – Blocking Public Access to Your Amazon S3 Storage
   https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html

7. AWS Documentation – Amazon SageMaker
   https://docs.aws.amazon.com/sagemaker/
