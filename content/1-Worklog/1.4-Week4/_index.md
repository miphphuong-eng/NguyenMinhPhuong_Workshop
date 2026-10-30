
---
title: "1.4. Week 4 Worklog"
weight: 4
draft: false
---

## Week 4 Objectives

- Gain an in-depth understanding of managed relational database architecture on AWS through Amazon Relational Database Service (Amazon RDS).
- Explore and compare supported Database Engines, including PostgreSQL, MySQL, MariaDB, and Amazon Aurora, to select an appropriate engine based on application requirements.
- Understand Multi-AZ Deployments for High Availability (HA) and Read Replicas for horizontal read scalability.
- Practice creating DB Subnet Groups, configuring Security Groups, and deploying Amazon RDS securely within Private Subnets.
- Learn how to connect Backend applications to Amazon RDS and manage database structures through SQL Migration Scripts.
- Understand Automated Backups, Manual DB Snapshots, and database restoration procedures for disaster recovery.
- Apply network security principles to restrict database access to authorized resources only.

---

## Weekly Activities

| Day | Activities | Start Date | End Date | References |
| :---: | :--- | :---: | :---: | :--- |
| **Monday** | - Explore Amazon RDS and understand its role in deploying and managing relational databases on AWS.<br>- Compare self-managed databases running on EC2 Instances with fully managed Amazon RDS solutions.<br>- Research popular Database Engines, including PostgreSQL, MySQL, MariaDB, and Amazon Aurora.<br>- Explore DB Instance configuration components such as Instance Classes, Storage Types (gp2, gp3, io1), DB Parameter Groups, and Option Groups.<br>- Analyze how to select database resources based on application performance, storage capacity, and workload requirements. | 12/10/2026 | 12/10/2026 | [Amazon RDS User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)<br>[RDS Storage Types](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html) |
| **Tuesday** | - Study High Availability (HA) mechanisms in Amazon RDS through Multi-AZ Deployments.<br>- Explore synchronous replication to a standby instance and automatic failover capabilities.<br>- Practice reviewing Multi-AZ configuration options to improve database availability during infrastructure failures.<br>- Learn about Read Replicas and asynchronous data replication mechanisms.<br>- Analyze how Read Replicas distribute read queries and reduce workloads on the primary Database Instance.<br>- Compare the use cases of Multi-AZ Deployments and Read Replicas in real-world system architectures. | 13/10/2026 | 13/10/2026 | [RDS High Availability (Multi-AZ)](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)<br>[RDS Read Replicas](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html) |
| **Wednesday** | - Practice creating a DB Subnet Group using Private Subnets across multiple Availability Zones.<br>- Understand the role of DB Subnet Groups in determining where Amazon RDS can be deployed within a VPC.<br>- Create and configure a dedicated Security Group for the RDS Instance.<br>- Configure Inbound Rules to allow database connections exclusively from the EC2 Web Server Security Group through the appropriate ports, such as PostgreSQL (5432) or MySQL (3306).<br>- Practice deploying an Amazon RDS PostgreSQL Instance within a Private Subnet.<br>- Disable Public Accessibility to prevent direct database access from the Internet.<br>- Review network configurations and security rules after deployment. | 14/10/2026 | 14/10/2026 | [RDS Subnet Groups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceinaVPC.html)<br>[RDS Security Groups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.RDSSecurityGroups.html) |
| **Thursday** | - Explore the process of connecting a Backend application or EC2 Instance to Amazon RDS PostgreSQL.<br>- Practice connecting to an RDS Instance from an EC2 Instance in a Public Subnet using `psql` or pgAdmin.<br>- Verify connectivity using the database Endpoint, Port, Database Name, and authentication credentials.<br>- Write and execute SQL Migration Scripts to create Tables, Indexes, and initialize application data.<br>- Verify the database structure after executing migration scripts.<br>- Learn how to configure Database Connection Strings through Environment Variables on the Backend Server.<br>- Apply secure credential management practices and avoid storing database connection information directly in Source Code. | 15/10/2026 | 15/10/2026 | [Connect to RDS Instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html)<br>[PostgreSQL on RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_PostgreSQL.html) |
| **Friday** | - Explore Automated Backup mechanisms and the concepts of Recovery Point Objective (RPO) and Recovery Time Objective (RTO).<br>- Distinguish between Automated Backups and Manual DB Snapshots for data protection and recovery.<br>- Practice creating a Manual DB Snapshot from an existing RDS Instance.<br>- Test the restoration process by creating a new DB Instance from the previously created Snapshot.<br>- Review Security Group Rules to ensure that database ports are not publicly exposed to the Internet.<br>- Recheck Multi-AZ settings, DB Subnet Groups, Public Accessibility, and database access permissions.<br>- Capture screenshot evidence, summarize practical results, and complete the Week 4 Worklog. | 16/10/2026 | 16/10/2026 | [RDS Backups & Snapshots](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html)<br>[Restoring DB Instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_RestoreFromSnapshot.html) |

---

## Week 4 Achievements

- Gained a clear understanding of Amazon RDS architecture, its core capabilities, and operational advantages over managing databases directly on EC2 Instances.
- Understood the characteristics of supported Database Engines, including PostgreSQL, MySQL, MariaDB, and Amazon Aurora.
- Learned how to select appropriate DB Instance Classes and Storage Types based on performance, capacity, and cost requirements.
- Understood how Multi-AZ Deployments improve database availability and support automatic failover during infrastructure failures.
- Gained knowledge of Read Replicas and how they improve database scalability by distributing read workloads.
- Distinguished between the use cases of Multi-AZ Deployments and Read Replicas in database architecture.
- Practiced creating DB Subnet Groups across Private Subnets in multiple Availability Zones.
- Successfully deployed an Amazon RDS PostgreSQL Instance within Private Subnets with Public Accessibility disabled to prevent direct Internet access.
- Configured Security Groups to allow database connections only from authorized EC2 Web Servers through the required database ports.
- Established connectivity between an EC2 Instance and Amazon RDS PostgreSQL using the appropriate Endpoint and authentication credentials.
- Practiced writing and executing SQL Migration Scripts to create Tables, Indexes, and initialize application data.
- Learned how to configure Database Connection Strings through Environment Variables to protect Backend Application credentials.
- Understood the role of Automated Backups in protecting data and supporting database recovery.
- Distinguished between Automated Backups and Manual DB Snapshots and learned the database restoration process.
- Practiced creating Manual DB Snapshots and verifying data recovery by launching a new DB Instance from a Snapshot.
- Improved skills in designing, deploying, and securing database infrastructure on AWS.
- Completed practical documentation and captured screenshot evidence of RDS architecture, network configurations, and data protection mechanisms.
