# AWS Certified Solutions Architect Associate SAA-C02

## What is the exam focusing on
- 30% Design Resilient Architecture
- 28% Design Performant Architectures
- 24% Design Secure Applications and Architectures 
- 18% Design Cost-Optimized Architectures

## Exam tips
- Understand differences between fault tolerant and high availability
- Assume that an answer using a single AZ is always incorrect.
- Managed services are preferred.
- For unstructured data S3 is a good solution.
- Look for caching options to improve performance.
- Know when to use auto scaling for a given architecture.
- Select the best instance size for a given workload.

## Exam Blueprint

### Data Resilient Architectures
- Design a multi-tier acrhitecture solution.
- Design highly available and/or fault tolerant architectures.
- Design decoupling mechanisms using AWS services.
- Choose appropriate resilient storage.

### Design High-Performing Architectures
- Identify elastic and scalable compute solutions for a workload.
- Select high-performing and scalable storage solutions for a workload.
- Select high-performing network solutions for a workload.
- Choose high-performing database solutions for a workload.

### Design Secure Applications and Architecture
- Design secure access to AWS resources.
- Design secure application tiers.
- Select appropriate data security options.

### Design Cost-Optimized Architectures
- Identify cost-effective storage solutions.
- Identify cost-effective compute and database services.
- Design cost-optimized network architectures.

### Whitepapers
- [Architecting for the Cloud: AWS Best Practices](https://s3.amazonaws.com/awsmedia/AWS_Cloud_Best_Practices.pdf)
- [AWS Security Best Practice](https://d1.awsstatic.com/whitepapers/Security/AWS_Security_Best_Practices.pdf)
- [Overview of Amazon Web Services](https://d0.awsstatic.com/whitepapers/aws-overview.pdf)
- [AWS Storage Services Overview](https://d0.awsstatic.com/whitepapers/AWS%20Storage%20Services%20Whitepaper-v9.pdf)
- [AWS Well Architected Framework](https://aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc)
- [Overview of Security Processes](https://d1.awsstatic.com/whitepapers/aws-security-whitepaper.pdf)

### Videos
- [AWS Events Videos](https://www.youtube.com/channel/UCdoadna9HFHsxXWhafhNvKw)
- [Another Day, Another Billion Packets](https://youtu.be/3qln2u1Vr2E)

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
## S3
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
