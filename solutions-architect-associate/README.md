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

- **S3 Standard** - 99.99% availability and 11 9s durability. Data in this class is stored redundantly across mupliple devices in multiple facilities and is designed to withstand the failure of 2 concurrent data centers.

- **S3 Infequently Accessed (IA)** - For data that is needed less often, but when it is needed the data should be available quickly. The storage fee is cheaper, but you are charged for retrieval

- **S3 One Zone Infrequently Accessed (an improvement of legacy RRS / Reduced Redundancy Storage)** - For when you want the lower costs of IA, but do not require high availability. This is even cheaper because of the lack of HA.

- **S3 Intelligent Tiering** - Uses built-in ML/AI to determine the most cost-effective storage class and then automatically moves your data to the appropriate tier. It does this without operational overhead or perfomance impact.

- **S3 Glacier** - Low-cost storage class for data archiving. This class is for pure storage purposes where retrieval isn't needed often at all. Retrieval times range from minutes to hours. There are different retrieval methods depending on how acceptable the default retrieval times are for you:

  - Expedited: 1 - 5 minutes, but this option is the most expensive

  - Standard: 3 - 5 hours to restore

  - Bulk: 5 - 12 hours. This option has the lowest cost and is good for a large set of data

  The Expedited duration listed above could possibly be longer during rare situations of unusually high demand across all of AWS. If it is absolutely critical to have quicl access to your Glacier data under all circumstances, you must purchase _Provisioned Capacity_. Provisioned Capacity guarantees that Expedited retrievals always work within the time constraints of 1 to 5 minutes.

- **S3 Deep Glacier** - The lowest cost S3 storage where retrieval can take 12 hours.

| Storage Class         | Designed for                                                                | Durability (designed for) | Availability (designed for)         | Availability Zones | Min storage duration | Min billable object size | Other Considerations                                                                             |
| --------------------- | --------------------------------------------------------------------------- | ------------------------- | ----------------------------------- | ------------------ | -------------------- | ------------------------ | ------------------------------------------------------------------------------------------------ |
| STANDARD              | Frequently accessed data                                                    | 99.999999999%             | 99.99%                              | >= 3               | None                 | None                     | None                                                                                             |
| STANDARD_IA           | Long-lived, infrequently accessed data                                      | 99.999999999%             | 99.9%                               | >= 3               | 30 days              | 128 KB                   | Per GB retrieval fees apply                                                                      |
| INTELLIGENT_TIERING   | Long-lived data with changing or unkown access patterns                     | 99.999999999%             | 99.9%                               | >= 3               | 30 days              | None                     | Monitoring and automation fees per object apply. No retrieval fees                               |
| ONEZONE_IA            | Long-lived, infrequently accessed, non-critical data                        | 99.999999999%             | 99.5%                               | 1                  | 30 days              |  128 KB                  | Per GB retrieval fees apply. Not resilient to the loss of the Availability Zone                  |
| GLACIER               | Long-term data archiving with retrieval times ranging from minutes to hours | 99.999999999%             | 99.99.% (after you restore objects) | >= 3               | 90 days              | 40 KB                    | Per GB retrieval fees apply. You must first restore archived objects before you can access them. |
| DEEEP_ARCHIVE         | Archiving rarely accessed data with a default retrieval time of 12 hours    | 99.999999999%             | 99.99% (after you restore objects)  | >= 3               |  180 days            | 40 KB                    | Per GB retrieval fees apply. You must first restore archived objects before you can access them. |
| RRS (Not recommended) | Frequently accessed, non-critical data                                      | 99.99%                    | 99.99%                              | >= 3               |  None                | None                     | None                                                                                             |

### S3 Security and Encryption

S3 data can be encrypted both in transit and at rest.

- **Encryption In Transit** - When the traffic passing between one endpoint to another is indecipherable. Anyone eavesdropping between server A and server B won't be able to make sense of the information passing by. Encryption in transit for S3 is always achieved by SSL/TLS.

- **Encryption At Rest** - When the immobile data sitting inside S3 is encrypted. If someone breaks into a server, they still won't be able to access encrypted info within that server. Encryption at rest can be done either on the server-side or the client-side. The server side is when S3 encrypts your data as it is being written to disk and decrypts it when you access it. The client-side is when you personally encrypt the object on your own and then upload it into S3 afterwards.

You can encrypt data on the server-side in the following ways:

- **S3 Managed Keys / SSE - S3 (server side encryption s3)** - When Amazon manages the encryption and decryption keys for you automatically. In this scenario, you concede a little control to Amazon in exchange for ease of use.

- **AWS Key Management Service / SSE - KMS** - When Amazon and you both manage the encryption and decryption keys together.

- **Server Side Encryption with customer provided keys / SSE - C** - When you give Amazon your own keys that you manage. In this scenario you concede ease of use in exchange for more control.

### S3 Versioning

- When versioning is enabled, S3 stores all versions of an object including all writes and even deletes.

- It is a great feature for implicitly backing up content and for easy rollbacks in case of human error.

- It can be thought of as analogous to Git.

- Once versioning is enabled on a bucket, it cannot be disabled - only suspended.

- Versioning integrates with lifecycle rules so you can set rules to expire or migrate data based on their version

- Versioning also has MFA delete capability to provide an additional layer of security.

### Lifecycle Management with S3

- Automates the moving of objects between the different storage tiers.

- Can be used in conjunction with versioning

- Lifecycle rules can be applied to both current and previous versions of an object.

### S3 Cross Region Replication

- Cross region replication only work if versioning is enabled

- When cross region replication is enabled, no pre-existing data is transferred. Only new uploads into the original bucket are replicated. All subsequent updates are replicated.

- When you replicate the contents of one bucket to another, you can actually change the ownership of the content if you want. You can also change the storage tier of the new bucket with the replicated content.

- When files are deleted in the orginal bucket (via a delete marker as versioning prevents true deletions), those deletes are not replicated.

- [Cross Region Replication Overview](https://aws.amazon.com/solutions/cross-region-replication-monitor/)

- [What is and isn’t replicated such as encrypted objects, deletes, items in glacier, etc.](https://docs.aws.amazon.com/AmazonS3/latest/dev/replication-what-is-isnot-replicated.html#replication-what-is-not-replicated)

### S3 Object Lock and Glacier Vault Lock [SAA-C02]

### S3 Performance [SAA-C02]

- If the request rate for reading and writing objects to S3 is extremely high, then you can use hash keys or random strings to prefix the object's name. In such cases, the partions used to store the objects will be better distributed and therefor will allow better read/write performance on your objects

- If your S3 data is receiving a high number of GET requests from users, you should consider using Amazon CloudFront for performance optimization. By integrating CloudFront with S3, you can distribute content via CloudFront's cache to your users for lower latency and a higher data transfer rate. This also has the added bonus of sending fewer direct requests to S3 which will reduce costs. For example, suppose that you have a few objects and caches them. CloudFront can then serve future requests for the objects form its cache, reducing the total number of GET requests it sends to Amazon S3.

- [More information on how to ensure high performance in S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/optimizing-performance.html)

### S3 Select and Glacier Select [SAA-C02]

- S3 Select is an Amazon S3 feature that is designed to pull out only the data you need from an object, which can dramatically improve the performance and reduce the cost of applications that need to access data in S3.

- Most applications have to retrieve the entire object and then filter out only the required data for further analysis. S3 Select enabled applications to offload the heavy lifting of filtering and accessing data inside objects to the Amazon S3 service.

- As an example, let's imagine you're a developer at a larger retailer and you need to analyze the weekly sales data from a single store, but the data for all 200 stores is saced in a new GZIP-ed CSV every day.

  - Without S3 Select, you would need to download, decompress and process the entire
    CSV to get the data you needded.

  - With S3 Select, you can use a simple SQL expression to return only the data from the store you're intrested in, instead of retrieving the entire object.

- By reducing the volume of data that has to be loaded and processed by your applications, S3 Select can improve the performance of most applications that frequently access data from S3 by up to 400% because you're dealing with significantly less data

- You can aslo use S3 Select for Glacier

### AWS Organizations and Consolidated Billing [SAA-C02]

### Sharing S3 Buckets Across Accounts [SAA-C02]

### S3 Transfer Acceleration

- Transfer acceleration makes use of the CloudFront network by sending and receiving data at CDN points of presence (called edge locations) rather than slower uploads or downloads at the origin.
- This is accomplished by uploading to a distinct URL for the edge location instead of the bucket itself. This is then transferred of the AWS network backbone at a much faster speed.
- [You can test transfer acceleration speed directly in comparison to regular uploads.](https://s3-accelerate-speedtest.s3-accelerate.amazonaws.com/en/accelerate-speed-comparsion.html)

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
