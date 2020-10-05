# AWS Certified Solutions Architect Associate SAA-C02

## Table of Contents

1. [Introduction](#introduction)

2. [AWS Overview](#aws-overview)

3. [Identity Access Management (IAM)](#identity-access-management-iam)

4. [Simple Storage Service (S3)](#simple-storage-service-s3)

## Introduciton

[The official AWS Solutions Architect - Associate (SAA-C02) exam guide](https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS-Certified-Solutions-Architect-Associate-Exam-Guide_v1.1_2019_08_27_FINAL.pdf)

### What is the exam focusing on

| Domain                                                 | % of Examination |
| ------------------------------------------------------ | ---------------- |
| Domain 1: Design Resilient Architecture                | 30%              |
| Domain 2: Design Performant Architectures              | 28%              |
| Domain 3: Design Secure Applications and Architectures | 24%              |
| Domain 4: Design Cost-Optimized Architectures          | 18%              |

#### Domain 1: Design Resilient Architecture

1.1 - Design a multi-tier architecture solution

1.2 - Design highly available and/or fault-tolerant architectures

1.3 - Design decoupling mechanisms using AWS services

1.4 - Choose appropriate resilient storage

#### Domain 2: Design highly available and/or fault-tolerant architectures

2.1 - Identify elastic and scalable computesolutions for a workload

2.2 - Select high-performing and scalable storage solutions for a workload

2.3 - Select high-performing networking solutions for a workload

2.4 - Choose high-performing database solutions for a workload

#### Domain 3: Design Secure Applications and Architectures

3.1 - Design secure access to AWS resources

3.2 - Design secure application tiers

3.3 - Select appropriate data security options

#### Domain 4: Design Cost-Optimized Architectures

4.1 - Identify cost-effective storage solutions

4.2 - Identify cost-effective compute and database services

4.3 - Design cost-optimized network architectures

### Exam tips

- Understand differences between fault tolerant and high availability
- Assume that an answer using a single AZ is always incorrect.
- Managed services are preferred.
- For unstructured data S3 is a good solution.
- Look for caching options to improve performance.
- Know when to use auto scaling for a given architecture.
- Select the best instance size for a given workload.

### Recommended Reading:

- [Architecting for the Cloud: AWS Best Practices](https://s3.amazonaws.com/awsmedia/AWS_Cloud_Best_Practices.pdf)
- [AWS Security Best Practice](https://d1.awsstatic.com/whitepapers/Security/AWS_Security_Best_Practices.pdf)
- [Overview of Amazon Web Services](https://d0.awsstatic.com/whitepapers/aws-overview.pdf)
- [AWS Storage Services Overview](https://d0.awsstatic.com/whitepapers/AWS%20Storage%20Services%20Whitepaper-v9.pdf)
- [AWS Well Architected Framework](https://aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc)
- [Overview of Security Processes](https://d1.awsstatic.com/whitepapers/aws-security-whitepaper.pdf)
- [Amazon VPC FAQs](https://aws.amazon.com/vpc/faqs/)
- [AWS Autoscaling FAQs](https://aws.amazon.com/autoscaling/faqs/)
- [Amazon EC2 FAQs](https://aws.amazon.com/ec2/faqs/)
- [Amazon EC2 Auto Scaling FAQs](https://aws.amazon.com/ec2/autoscaling/faqs/)
- [Amazon EBS FAQs](https://aws.amazon.com/ebs/faqs/)
- [Elastic network interfaces](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)
- [Amazon S3 FAQs](https://aws.amazon.com/s3/faqs/)
- [Elastic Load Balancing FAQs](https://aws.amazon.com/elasticloadbalancing/faqs/)
- [Amazon Route 53 FAQs](https://aws.amazon.com/route53/faqs/)
- [AWS Storage Gateway FAQs](https://aws.amazon.com/storagegateway/faqs/)
- [Amazon EFS FAQs](https://aws.amazon.com/efs/faq/)
- [Amazon FSx for Windows File Server FAQs](https://aws.amazon.com/fsx/windows/faqs/)
- [Amazon FSx for Lustre FAQs](https://aws.amazon.com/fsx/lustre/faqs/)
- [AWS Organizations FAQs](https://aws.amazon.com/organizations/faqs/)

### Videos

- [AWS Events Videos](https://www.youtube.com/channel/UCdoadna9HFHsxXWhafhNvKw)
- [Another Day, Another Billion Packets](https://youtu.be/3qln2u1Vr2E)
- [Pluralsight: Architecting for Reliability on AWS](https://app.pluralsight.com/library/courses/architecting-reliability-aws/table-of-contents)
- [Pluralsight: Architecting for Performance Efficiency on AWS](https://app.pluralsight.com/library/courses/architecting-performance-efficiency-aws/table-of-contents)
- [Pluralsight: Architecting for Security on AWS](https://app.pluralsight.com/library/courses/architecting-security-aws/table-of-contents)
- [Pluralsight: Make Cost-Optimized Decisions on AWS](https://app.pluralsight.com/library/courses/make-cost-optimized-decisions-aws/table-of-contents)
- [Pluralsight: Demystifying the AWS Certified Solutions Architect: Associate Exam](https://app.pluralsight.com/library/courses/demystifying-aws-certified-solutions-architect-associate-exam/table-of-contents)

### Web pages

- [AWS Architecture Center](https://aws.amazon.com/architecture/)

### Key areas and services

- Application Integration
- Desktop & App Streaming
- Management Tools
- Analytics
- Migration
- Security, Identity & Compliance
- Compute
- Storage
- Databases
- Network & Content Delivery
- AWS Global Infrastructure

## AWS Overview

- Availability Zone: Data Center (Could be one or many)
- Region: Geographical area, consist of 2 or more AZ.
- Edge location: Endpoints used for caching (CloudFront, CDN). There are more edge locations than regions (and AZ).

## Identity Access Management (IAM)

- Centralized control of your AWS account.
- Shared access to your AWS account.
- Granular permissions
- Identity federation (Google, LDAP, Facebook ...)
- Multifactor Authentication
- Temporary access for user/devices and services.
- Allows you to set up your own password rotation policy
- Integrates with many different AWS services.
- Supports PCI DSS Compliance

### IAM Definition

- Users: End user
- Groups: A collection of users. Will inherit the group permissions.
- Policies: JSON documents, called policy documents. Give permissions as to what a user/group/role is able to do.
- Roles: You create roles and then assign them to AWS resources.

### AWS Directory Service [SAA-C02]

### IAM Policies [SAA-C02]

### AWS Resource Access Manager (RAM) [SAA-C02]

### AWS Single Sign-On [SAA-C02]

## Simple Storage Service (S3)
### S3 Pricing Tiers [SAA-C02]
### S3 Security and Encryption
### S3 Versioning
### Lifecycle Management with S3
### S3 Object Lock and Glacier Vault Lock [SAA-C02]
### S3 Performance [SAA-C02]
### S3 Select and Glacier Select [SAA-C02]
### AWS Organizations and Consolidated Billing [SAA-C02]
### Sharing S3 Buckets Across Accounts [SAA-C02]
### S3 Transfer Acceleration
### AWS DataSync [SAA-C02]
## CloudFront
### CloudFront Signed URLs and Cookies [SAA-C02]
## Snowball
## Storage Gateway
## Athena vs. Macie [SAA-C02]
## EC2
### Security Groups
### EBS
### EBS Volumes and Snapshots
### AMI Types (EBS vs. Instance Store)
### ENI vs. ENA vs. EFA [SAA-C02]
### Encrypted Root Device Volumes and Snapshots - Lab
### Spot Instances and Spot Fleets [SAA-C02]
### EC2 Hibernate [SAA-C02]
## CloudWatch
### Identity and Access Management Roles
### Using Bootstrap Scripts
### Instance Metadata
### EFS [SAA-C02]
### Amazon FSx for Windows and Amazon FSx for Lustre [SAA-C02]
### EC2 Placement Groups
### HPC on AWS [SAA-C02]
### AWS WAF [SAA-C02]
## Databases on AWS
### RDS Instance
### RDS: Backups, Multi-AZ, and Read Replicas
### DynamoDB
### Redshift
### Aurora [SAA-C02]
### Elasticache
### Database Migration Service (DMS) [SAA-C02]
### Caching Strategies on AWS [SAA-C02]
### EMR Overview [SAA-C02]
## Route 53
### DNS
### Register a Domain Name
### Route 53 Routing Policies Available on AWS
### Route 53: Simple Routing Policy
### Route 53: Weighted Routing Policy
### Route 53: Latency-Based Policy
### Route 53: Failover Routing Policy
### Route 53: Geolocation Routing Policy
### Route 53: Geoproximity Routing Policy (Traffic Flow Only)
### Route 53: Multivalue Answer Policy
## VPCs
### NAT Instances and NAT Gateways
### Network Access Control Lists vs. Security Groups
### Custom VPCs and ELBs
### VPC Flow Logs
### Bastions
### Direct Connect
### Global Accelerator [SAA-C02]
### VPC Endpoints [SAA-C02]
### AWS PrivateLink [SAA-C02]
### AWS Transit Gateway [SAA-C02]
### AWS VPN CloudHub [SAA-C02]
### AWS Network Costs [SAA-C02]
## High Availabilty Architecture
### Elastic Load Balancers
### Load Balancers and Health Checks
### Advanced Load Balancer Theory [SAA-C02]
### Auto Scaling [SAA-C02]
### Launch Configurations and Auto Scaling Groups
### Elastic Beanstalk
### High Availability with Bastion Hosts [SAA-C02]
### On-Premises Strategies with AWS [SAA-C02]
### SQS [SAA-C02]
### Simple Workflow Service
### Simple Notification Service
### Elastic Transcoder
### API Gateway
### Kinesis
### Web Identity Federation and Cognito
### Event Processing Patterns [SAA-C02]
## Security
### Key Management Service (KMS) [SAA-C02]
### CloudHSM [SAA-C02]
### Systems Manager Parameter Store [SAA-C02]
### Secrets Manager [SAA-C02]
### AWS Shield [SAA-C02]
### Web Application Firewall (WAF) [SAA-C02]
## Serverless
### Lambda
### Serverless Application Model (SAM) [SAA-C02]
### Elastic Container Service (ECS) [SAA-C02]
