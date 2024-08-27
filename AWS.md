# AWS Cloud Practitioner Essentials

#### [Home](index.md) - [Algorithms](Algorithms.md) - [Cloud Computing](CloudComputing.md) - [Projects](Projects.md)

---

### 1: Introduction to AWS

1. **Summarize the benefits of AWS.**
   - On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing.

2. **Describe differences between on-demand delivery and cloud deployments.**
   - Private cloud deployment

3. **Summarize the pay-as-you-go pricing model.**
   - The aggregated cloud usage from a large number of customers results in lower pay-as-you-go prices.

---

### 2: Compute in the Cloud

1. **Describe the benefits of Amazon EC2 at a basic level.**
    - Amazon Elastic Compute Cloud (Amazon EC2) provides secure, resizable compute  capacity in the cloud as Amazon EC2 instances.

2. **Identify the different Amazon EC2 instance types.**
    - General purpose instances.
    - Compute optimized instances.
    - Memory optimized instances.
    - Accelerated computing instances.
    - Storage optimized instances.

3. **Differentiate between the various billing options for Amazon EC2.** 

    - **On-Demand** Instances are ideal for short-term, irregular workloads that cannot be interrupted. No upfront costs or minimum contracts apply. The instances run continuously until you stop them, and you pay for only the compute time you use.

    - **Reserved Instances** are a billing discount applied to the use of On-Demand Instances in your account. There are two available types of Reserved Instances:

        - Standard Reserved Instances
        - Convertible Reserved Instances

    - **EC2 Instance Savings Plans** reduce your EC2 instance costs when you make an hourly spend commitment to an instance family and Region for a 1-year or 3-year term. This term commitment results in savings of up to 72 percent compared to On-Demand rates. Any usage up to the commitment is charged at the discounted Savings Plans rate (for example, $10 per hour). Any usage beyond the commitment is charged at regular On-Demand rates.

    - **Spot Instances** are ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity and offer you cost savings at up to 90% off of On-Demand prices.

    - **Dedicated Hosts** are physical servers with Amazon EC2 instance capacity that is fully dedicated to your use.

4. **Summarize the benefits of Amazon EC2 Auto Scaling.** 
    - You start with only the resources you need and design your architecture to automatically respond to changing demand by scaling out or in. This lets you pay only for the resources you use and you will always have the capacity you need.

5. **Summarize the benefits of Elastic Load Balancing.** 
    - **Elastic Load Balancing** is the AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances.

6. **Give an example of the uses for Elastic Load Balancing.** 
    - In Low demand periods there will only be the minimum allocated EC2 instances and the Elastic load balancing will direct the traffic to these, when demand rises there will be an increase in EC2 instances, these new instances will tell the Load Elastic Balancing that they are online and the Balancer will distribute the traffic between all instances.

7. **Summarize the differences between Amazon Simple Notification Service (Amazon SNS) and Amazon Simple Queue Service (Amazon SQS).** 
    - **(Amazon SNS)** is a publish/subscribe service. Using Amazon SNS topics, a publisher publishes messages to subscribers. - **(Amazon SQS)** is a message queuing service. You can send, store, and receive messages between software components, without losing messages or requiring other services to be available.

8. **Summarize additional AWS compute options.** 
    - **AWS Lambda** is a service that lets you run code without needing to provision or manage servers. - **Amazon Elastic Container Service** (Amazon ECS) is a highly scalable, high-performance container management system that enables you to run and scale containerized applications on AWS. - **Amazon Elastic Kubernetes Service** (Amazon EKS)(opens in a new tab) is a fully managed service that you can use to run Kubernetes on AWS. - **AWS Fargate** is a serverless compute engine for containers. It works with both Amazon ECS and Amazon EKS.

---

### 3: Infrastructure and Reliability

1.**Summarize the benefits of the AWS Global Infrastructure.**
    - AWS Global Infrastructure is the term used to explain how aws has set up there data center. It's spread out over multiple center in a region and spans multiple regions, so if one Data center losses power or a natural disaster where to happen the overall structure would still remain.

2.**Describe the basic concept of Availability Zones.**
    - An Availability Zone is a single data center or a group of data centers within a Region. Availability Zones are located tens of miles apart from each other. This is close enough to have low latency (the time between when content requested and received) between Availability Zones. However, if a disaster occurs in one part of the Region, they are distant enough to reduce the chance that multiple Availability Zones are affected.

3.**Describe the benefits of Amazon CloudFront and edge locations.**
    - An edge location is a site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery.
    - CloudFront retrieves the files from the caches stored in the Edge Location and delivers them to the customer.

4.**Compare different methods for provisioning AWS services.**
    - **The AWS Management Console** is a web-based interface for accessing and managing AWS services. You can quickly access recently used services and search for other services by name, keyword, or acronym. The console includes wizards and automated workflows that can simplify the process of completing tasks.
    - **AWS Command Line Interface.** AWS CLI enables you to control multiple AWS services directly from the command line within one tool.
    - **Software development kits.** SDKs make it easier for you to use AWS services through an API designed for your programming language or platform. SDKs enable you to use AWS services with your existing applications or create entirely new applications that will run on AWS.
    - **AWS Elastic Beanstalk**, you provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:
    - **AWS CloudFormation** you can treat your infrastructure as code. This means that you can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.

### 4. Networking

Here’s a breakdown of the networking concepts from the Amazon Cloud Practitioner Essentials course:

1. **Describe the basic concepts of networking.**
   - **Networking** involves the interconnection of devices to share resources, communicate, and exchange data. It includes components like routers, switches, firewalls, and protocols (e.g., TCP/IP) that ensure data is transmitted securely and efficiently. In the context of AWS, networking allows different AWS services and resources to communicate with each other and with the internet.

2. **Describe the difference between public and private networking resources.**
   - **Public Networking Resources** are accessible over the internet. For example, AWS public IP addresses can be reached by anyone with internet access. Services like Amazon S3 (Simple Storage Service) or Amazon EC2 instances with public IPs are examples.
   - **Private Networking Resources** are isolated from the public internet and can only be accessed from within a private network. In AWS, this is typically managed using Virtual Private Clouds (VPCs) where instances or databases are only accessible within the private network or through a VPN or Direct Connect.

3. **Explain a virtual private gateway using a real-life scenario.**
   - A **Virtual Private Gateway (VGW)** is a resource that allows you to establish a VPN connection between your on-premises network and your AWS VPC. 
   - **Scenario:** Imagine your company has an on-premises data center and you want to securely extend your network to the cloud to use AWS resources. You could set up a VGW in your AWS VPC and establish a VPN connection, allowing secure communication between your data center and your AWS environment.

4. **Explain a virtual private network (VPN) using a real-life scenario.**
   - A **Virtual Private Network (VPN)** extends your private network across a public network, allowing secure access to resources as if you were directly connected to the private network.
   - **Scenario:** Suppose you are working from home and need secure access to your company’s internal resources hosted on AWS. You can use a VPN connection to securely connect to your company’s AWS VPC, allowing you to access internal applications and data as though you were in the office.

5. **Describe the benefit of AWS Direct Connect.**
   - **AWS Direct Connect** is a dedicated network connection between your on-premises data center and AWS, providing a more reliable and faster connection than typical internet-based connections. 
   - **Benefit:** It reduces latency, provides consistent performance, and can be more cost-effective for large-scale data transfers, making it ideal for hybrid cloud setups where consistent, high-performance connectivity is required.

6. **Describe the benefit of hybrid deployments.**
   - **Hybrid Deployments** combine on-premises infrastructure with cloud resources, allowing organizations to use both environments efficiently. 
   - **Benefit:** They provide flexibility, allowing businesses to keep sensitive data on-premises while taking advantage of the scalability and flexibility of the cloud. This can also facilitate gradual cloud migration and disaster recovery solutions.

7. **Describe the layers of security used in an IT strategy.**
   - **Security Layers** in IT typically include:
     - **Physical Security:** Protects the physical infrastructure like data centers.
     - **Network Security:** Involves firewalls, VPNs, and secure protocols to protect data in transit.
     - **Application Security:** Focuses on securing applications through practices like input validation and encryption.
     - **Data Security:** Involves encryption and access controls to protect data at rest.
     - **Identity and Access Management (IAM):** Ensures that only authorized users have access to resources.
     - **Monitoring and Logging:** Continuously tracks activities for suspicious behavior.
   - In AWS, these layers are supported by services like AWS IAM, AWS Shield, AWS WAF, and AWS CloudTrail.

8. **Describe the services customers use to interact with the AWS global network.**
   - Customers interact with the AWS global network through services like:
     - **Amazon VPC (Virtual Private Cloud):** Allows you to create isolated networks within AWS.
     - **AWS Direct Connect:** Provides a dedicated network connection to AWS.
     - **Amazon Route 53:** A DNS service that routes end-user requests to AWS resources.
     - **AWS Global Accelerator:** Improves the availability and performance of your applications using the AWS global network.
     - **Elastic Load Balancing (ELB):** Distributes incoming traffic across multiple AWS resources to ensure high availability.

### 5: Storage and Databases

1. **Summarize the basic concept of storage and databases.**
Here’s a summary of the basic concepts of **storage and databases** in the context of AWS:
    - **Storage** refers to the way data is saved and accessed in the cloud. AWS offers various storage services to meet different needs, such as file storage, block storage, and object storage.
    - **Amazon S3 (Simple Storage Service):** Provides scalable object storage for a wide range of data types. It's ideal for storing large volumes of unstructured data, like backups, media files, and logs.
    - **Amazon EBS (Elastic Block Store):** Provides block storage for use with Amazon EC2 instances. It is akin to a virtual hard drive and is used for storing data that requires frequent read/write access.
    - **Amazon EFS (Elastic File System):** Provides scalable file storage for use with EC2 instances. It supports shared access across multiple instances and is ideal for applications requiring a common file system.

2. **Describe the benefits of Amazon Elastic Block Store (Amazon EBS).**
    - Block storage breaks those files down to small component parts or blocks. This means, for that 80-gigabyte file, when you make an edit to one scene in the film and save that change, the engine only updates the blocks where those bits live.

3. **Describe the benefits of Amazon Simple Storage Service (Amazon S3).**
    - Amazon Simple Storage Service (Amazon S3)(opens in a new tab) is a service that provides object-level storage. Amazon S3 stores data as objects in buckets. The data might be an image, video, text document, or any other type of file. Metadata contains information about what the data is, how it is used, the object size, and so on. An object’s key is its unique identifier.

4. **Describe the benefits of Amazon Elastic File System (Amazon EFS).**
    - Amazon Elastic File System (Amazon EFS)(opens in a new tab) is a scalable file system used with AWS Cloud services and on-premises resources. As you add and remove files, Amazon EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications.

5. **Summarize various storage solutions.**
    - **Amazon RDS (Relational Database Service):** Manages relational databases, such as MySQL, PostgreSQL, and Oracle. It's ideal for structured data that requires complex queries and transactions.
    - **Amazon DynamoDB:** A fully managed NoSQL database service that offers high performance and scalability for applications requiring fast, consistent read and write performance.
    - **Amazon Aurora:** A MySQL and PostgreSQL-compatible relational database that offers the performance and availability of high-end commercial databases at a lower cost.
    - **Amazon Redshift:** A fast, fully managed data warehouse service for big data analytics, allowing you to run complex queries across petabytes of data.
    - **Amazon Neptune:** A managed graph database service that makes it easy to build and run applications that work with highly connected datasets.

6. **Describe the benefits of Amazon Relational Database Service (Amazon RDS).**
    - Amazon Relational Database Service (Amazon RDS)(opens in a new tab) is a service that enables you to run relational databases in the AWS Cloud.

    - Amazon RDS is a managed service that automates tasks such as hardware provisioning, database setup, patching, and backups.

7. **Describe the benefits of Amazon DynamoDB.**
    - Amazon DynamoDB(opens in a new tab) is a key-value database service. It delivers single-digit millisecond performance at any scale.

    - DynamoDB is serverless, which means that you do not have to provision, patch, or manage servers. You also do not have to install, maintain, or operate software.

    - As the size of your database shrinks or grows, DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance. This makes it a suitable choice for use cases that require high performance while scaling.

    - In a nonrelational database, you create tables. A table is a place where you can store and query data.

    - Nonrelational databases are sometimes referred to as “NoSQL databases” because they use structures other than rows and columns to organize data. One type of structural approach for nonrelational databases is key-value pairs. With key-value pairs, data is organized into items (keys), and items have attributes (values). You can think of attributes as being different features of your data.

    - In a key-value database, you can add or remove attributes from items in the table at any time. Additionally, not every item in the table has to have the same attributes.

8. **Summarize various database services.**
    - **AWS Database Migration Service (AWS DMS)** enables you to migrate relational databases, nonrelational databases, and other types of data stores.
    - **Amazon DocumentDB** is a document database service that supports MongoDB workloads. (MongoDB is a document database program.)
    - **Amazon Neptune** is a graph database service.
    - **Amazon Quantum Ledger Database (Amazon QLDB)** is a ledger database service.
    - **Amazon Managed Blockchain** is a service that you can use to create and manage blockchain networks with open-source frameworks.
    - **Amazon ElastiCache** is a service that adds caching layers on top of your databases to help improve the read times of common requests.
    - **Amazon DynamoDB Accelerator (DAX)** is an in-memory cache for DynamoDB.

### 6: Security

1. **Explain the benefits of the shared responsibility model.**

2. **Describe multi-factor authentication (MFA).**

3. **Differentiate between the AWS Identity and Access Management (IAM) security levels.**

4. **Explain the main benefits of AWS Organizations.**

5. **Describe security policies at a basic level.**

6. **Summarize the benefits of compliance with AWS.**

7. **Explain additional AWS security services at a basic level.**

### 7: Monitoring and Analytics

1. **Summarize approaches to monitoring your AWS environment.**

2. **Describe the benefits of Amazon CloudWatch.**

3. **Describe the benefits of AWS CloudTrail.**

4. **Describe the benefits of AWS Trusted Advisor.**

### 8: Pricing and Support

1. **Describe AWS pricing and support models.**

2. **Describe the AWS Free Tier.**

3. **Describe key benefits of AWS Organizations and consolidated billing.**

4. **Explain the benefits of AWS Budgets.**

5. **Explain the benefits of AWS Cost Explorer.**

6. **Explain the primary benefits of the AWS Pricing Calculator.**

7. **Distinguish between the various AWS Support Plans.**

8. **Describe the benefits of AWS Marketplace.**

### 9: Migration and Innovation

1. **Understand migration and innovation in the AWS Cloud.**

2. **Summarize the AWS Cloud Adoption Framework (AWS CAF).**

3. **Summarize the six key factors of a cloud migration strategy.**

4. **Describe the benefits of AWS data migration solutions, such as AWS Snowcone, AWS Snowball, and AWS Snowmobile.**

5. **Summarize the broad scope of innovative solutions that AWS offers.**

### 10: The cloud journey

1. **Summarize the six pillars of the Well-Architected Framework.**

2. **Explain the six benefits of cloud computing.**

### 11: AWS Certified Cloud Practitioner

1. **Determine resources for preparing for the AWS Certified Cloud Practitioner exam.**

2. **Describe the benefits of becoming AWS Certified.**
