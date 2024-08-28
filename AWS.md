---
title: "AWS Cloud Practitioner Essentials"
header:
    [Home](index.md) - [Algorithms](Algorithms.md) - [Cloud Computing](CloudComputing.md) - [Projects](Projects.md)
date: 2022-01-13 17:30:00 -0700
categories:
  - Notes
tags:
  - Cloud Computing
  - AWS
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
    - The shared responsibility model divides into customer responsibilities (commonly referred to as “security in the cloud”) and AWS responsibilities (commonly referred to as “security of the cloud”).
    - Customers are responsible for the security of everything that they create and put in the AWS Cloud.
    - AWS operates, manages, and controls the components at all layers of infrastructure. This includes areas such as the host operating system, the virtualization layer, and even the physical security of the data centers from which services operate.
2. **Describe multi-factor authentication (MFA).**
    - MFA is an extra layer of security usually made with autogenerated codes that you will have to use to log in. An example is a code sent to your phone or an Authenticated app that generates new codes every 60 sec and is configured to your service.
3. **Differentiate between the AWS Identity and Access Management (IAM) security levels.**
    - **Root User** When you first create an AWS account, you begin with an identity known as the root user. The Root User has full access and should be see as the owner and not used for everyday tasks.
    AWS Identity and Access Management (IAM) provides security at different levels:

    - **IAM Users:** Individual accounts with specific permissions.
    - **IAM Groups:** Collections of users with shared permissions for easier management.
    - **IAM Roles:** Temporary permissions for users, applications, or services, reducing credential exposure.
    - **IAM Policies:** JSON documents defining what actions are allowed or denied for users, groups, or roles.
    - **IAM Identity Providers:** Allows federated access using external identity systems, enabling single sign-on (SSO). 

    These levels control and secure access to AWS resources efficiently.

4. **Explain the main benefits of AWS Organizations.**
    - In AWS Organizations, you can centrally control permissions for the accounts in your organization by using service control policies (SCPs)(opens in a new tab). SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.
5. **Describe security policies at a basic level.**
    - IAM policy is a document that allows or denies permissions to AWS services and resources.
6. **Summarize the benefits of compliance with AWS.**
    - 1. **Security Assurance:** AWS provides a secure infrastructure that meets global compliance standards, helping businesses protect sensitive data and maintain trust with customers.
  
    - **Regulatory Alignment:** AWS supports various industry-specific standards (e.g., GDPR, HIPAA), making it easier for organizations to comply with regulatory requirements.

    - **Audit Support:** AWS offers tools and certifications that simplify the auditing process, reducing the time and effort needed to demonstrate compliance.

    - **Global Reach:** AWS compliance programs are recognized internationally, enabling businesses to expand into new markets with confidence.

    - **Continuous Monitoring:** AWS provides automated tools for monitoring and maintaining compliance, ensuring that your environment remains secure and compliant over time.
7. **Explain additional AWS security services at a basic level.**
    - **AWS Shield** is a service that protects applications against DDoS attacks. AWS Shield provides two levels of protection: Standard and Advanced.
        - AWS Shield Standard automatically protects all AWS customers at no cost. It protects your AWS resources from the most common, frequently occurring types of DDoS attacks. As network traffic comes into your applications, AWS Shield Standard uses a variety of analysis techniques to detect malicious traffic in real time and automatically mitigates it.
        - AWS Shield Advanced is a paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks. It also integrates with other services such as Amazon CloudFront, Amazon Route 53, and Elastic Load Balancing. Additionally, you can integrate AWS Shield with AWS WAF by writing custom rules to mitigate complex DDoS attacks.
    - **AWS Key Management Service (AWS KMS)** enables you to perform encryption operations through the use of cryptographic keys. A cryptographic key is a random string of digits used for locking (encrypting) and unlocking (decrypting) data. You can use AWS KMS to create, manage, and use cryptographic keys.

    - **AWS WAF** is a web application firewall that lets you monitor network requests that come into your web applications. AWS WAF works together with Amazon CloudFront and an Application Load Balancer. Recall the network access control lists. AWS WAF works in a similar way to block or allow traffic. However, it does this by using a web access control list (ACL)(opens in a new tab) to protect your AWS resources.

    - **Amazon Inspector** helps to improve the security and compliance of applications by running automated security assessments. It checks applications for security vulnerabilities and deviations from security best practices, such as open access to Amazon EC2 instances and installations of vulnerable software versions.

    - **Amazon GuardDuty** is a service that provides intelligent threat detection for your AWS infrastructure and resources. It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.

### 7: Monitoring and Analytics

1. **Summarize approaches to monitoring your AWS environment.**

2. **Describe the benefits of Amazon CloudWatch.**
    - **Amazon CloudWatch** is a web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics.
        - CloudWatch uses metrics to represent the data points for your resources. AWS services send metrics to CloudWatch. CloudWatch then uses these metrics to create graphs automatically that show how performance has changed over time.
        - With CloudWatch, you can create **alarms** that automatically perform actions if the value of your metric has gone above or below a predefined threshold.
        - **CloudWatch dashboard** feature enables you to access all the metrics for your resources from a single location. For example, you can use a CloudWatch dashboard to monitor the CPU utilization of an Amazon EC2 instance, the total number of requests made to an Amazon S3 bucket, and more.

3. **Describe the benefits of AWS CloudTrail.**
    - **AWS CloudTrail** records API calls for your account. The recorded information includes the identity of the API caller, the time of the API call, the source IP address of the API caller, and more. You can think of CloudTrail as a “trail” of breadcrumbs (or a log of actions) that someone has left behind them.
        - Within CloudTrail, you can also enable **CloudTrail Insights**. This optional feature allows CloudTrail to automatically detect unusual API activities in your AWS account.
4. **Describe the benefits of AWS Trusted Advisor.**
    - **AWS Trusted Advisor** is a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices in five categories: cost optimization, performance, security, fault tolerance, and service limits.

### 8: Pricing and Support

1. **Describe AWS pricing and support models.**
    - Pay for what you use.
        - For each service, you pay for exactly the amount of resources that you actually use, without requiring long-term contracts or complex licensing.
    - Pay less when you reserve.
        - Some services offer reservation options that provide a significant discount compared to On-Demand Instance pricing.
    - Pay less with volume-based discounts when you use more.
        - Some services offer tiered pricing, so the per-unit cost is incrementally lower with increased usage.

    - **AWS Pricing Calculator** lets you explore AWS services and create an estimate for the cost of your use cases on AWS. You can organize your AWS estimates by groups that you define. A group can reflect how your company is organized, such as providing estimates by cost center.

    -Use the **AWS Billing & Cost Management dashboard** to pay your AWS bill, monitor your usage, and analyze and control your costs.

2. **Describe the AWS Free Tier.**
    - The AWS Free Tier(opens in a new tab) enables you to begin using certain services without having to worry about incurring costs for the specified period.
        - Three types of offers are available:
            - Always Free
            - 12 Months Free
            - Trials
3. **Describe key benefits of AWS Organizations and consolidated billing.**
    - **AWS Organizations**, a service that enables you to manage multiple AWS accounts from a central location. AWS Organizations also provides the option for consolidated billing.
        - **The consolidated billing** feature of AWS Organizations enables you to receive a single bill for all AWS accounts in your organization. By consolidating, you can easily track the combined costs of all the linked accounts in your organization. The default maximum number of accounts allowed for an organization is 4, but you can contact AWS Support to increase your quota, if needed.
4. **Explain the benefits of AWS Budgets.**
    - AWS Budgets(opens in a new tab), you can create budgets to plan your service usage, service costs, and instance reservations.

        - The information in AWS Budgets updates three times a day. This helps you to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.

        - In AWS Budgets, you can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.
5. **Explain the benefits of AWS Cost Explorer.**
    - **AWS Cost Explorer** is a tool that lets you visualize, understand, and manage your AWS costs and usage over time.
    - AWS Cost Explorer includes a default report of the costs and usage for your top five cost-accruing AWS services. You can apply custom filters and groups to analyze your data. For example, you can view resource usage at the hourly level.
6. **Explain the primary benefits of the AWS Pricing Calculator.**
    - **AWS Pricing Calculator** offers several benefits, including the ability to estimate costs before deployment to ensure budget alignment, compare different configurations for cost-effectiveness through scenario modeling, and provide detailed cost breakdowns for enhanced transparency. It also calculates potential savings from Reserved Instances and Savings Plans, and supports comprehensive cost assessments across a broad range of AWS services, aiding in efficient financial management and decision-making.
7. **Distinguish between the various AWS Support Plans.**
    - AWS offers four different **Support plans** to help you troubleshoot issues, lower costs, and efficiently use AWS services.
        - **Basic Support** is free for all AWS customers. It includes access to whitepapers, documentation, and support communities. With Basic Support, you can also contact AWS for billing questions and service limit increases.
        - **Developer, Business, Enterprise On-Ramp, and Enterprise Support plans** include all the benefits of Basic Support, in addition to the ability to open an unrestricted number of technical support cases. These Support plans have pay-by-the-month pricing and require no long-term contracts.

8. **Describe the benefits of AWS Marketplace.**
    - AWS Marketplace(opens in a new tab) is a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS.

### 9: Migration and Innovation

1. **Understand migration and innovation in the AWS Cloud.**
    - Understanding migration and innovation in the AWS Cloud involves two key processes: migrating existing infrastructure and leveraging cloud resources for technological advancement. Migration includes assessing, planning, and executing the transfer of databases, applications, and servers to the cloud, facilitated by AWS tools like AWS Migration Hub and AWS Database Migration Service.
2. **Summarize the AWS Cloud Adoption Framework (AWS CAF).**
    - **AWS Cloud Adoption Framework (AWS CAF)** organizes guidance into six areas of focus, called Perspectives. Each Perspective addresses distinct responsibilities. The planning process helps the right people across the organization prepare for the changes ahead.
        - **Business Perspective** ensures that IT aligns with business needs and that IT investments link to key business results.
        - **People Perspective** supports development of an organization-wide change management strategy for successful cloud adoption.
        - **Governance Perspective** focuses on the skills and processes to align IT strategy with business strategy. This ensures that you maximize the business value and minimize risks.
        - **Platform Perspective** includes principles and patterns for implementing new solutions on the cloud, and migrating on-premises workloads to the cloud.
        - **Security Perspective** ensures that the organization meets security objectives for visibility, auditability, control, and agility.
        - **Operations Perspective** helps you to enable, run, use, operate, and recover IT workloads to the level agreed upon with your business stakeholders.
3. **Summarize the six key factors of a cloud migration strategy.**
    - **Rehosting** also known as “lift-and-shift” involves moving applications without changes. In the scenario of a large legacy migration, in which the company is looking to implement its migration and scale quickly to meet a business case, the majority of applications are rehosted.
    - **Replatforming**, also known as “lift, tinker, and shift,” involves making a few cloud optimizations to realize a tangible benefit. Optimization is achieved without changing the core architecture of the application.
    - **Refactoring** (also known as re-architecting) involves reimagining how an application is architected and developed by using cloud-native features. Refactoring is driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.
    - **Repurchasing** involves moving from a traditional license to a software-as-a-service model.
    - **Retaining** consists of keeping applications that are critical for the business in the source environment. This might include applications that require major refactoring before they can be migrated, or, work that can be postponed until a later time.
    - **Retiring** is the process of removing applications that are no longer needed.

4. **Describe the benefits of AWS data migration solutions, such as AWS Snowcone, AWS Snowball, and AWS Snowmobile.**
    - **AWS Snow Family** is a collection of physical devices that help to physically transport up to exabytes of data into and out of AWS.
        - **AWS Snowcone** is a small, rugged, and secure edge computing and data transfer device. It features 2 CPUs, 4 GB of memory, and up to 14 TB of usable storage.
        - AWS Snowball(opens in a new tab) offers two types of devices:
            - Snowball Edge Storage Optimized devices are well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs.
            - Snowball Edge Compute Optimized provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks.
        - AWS Snowmobile(opens in a new tab) is an exabyte-scale data transfer service used to move large amounts of data to AWS. You can transfer up to 100 petabytes of data per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.
5. **Summarize the broad scope of innovative solutions that AWS offers.**
    AWS offers a wide array of innovative solutions across various domains, enhancing business capabilities and fostering technological advancement. Here’s an overview in an unordered list format:

- **Compute Power:**
  - Amazon EC2 for scalable virtual servers.
  - AWS Lambda for serverless computing.
  - AWS Elastic Beanstalk for easy application deployment.

- **Storage Solutions:**
  - Amazon S3 for scalable object storage.
  - Amazon EBS for block storage solutions.
  - Amazon Glacier for long-term archival storage.

- **Database Services:**
  - Amazon RDS for managed relational databases.
  - Amazon DynamoDB for managed NoSQL databases.
  - Amazon Redshift for data warehousing solutions.

- **Machine Learning and Artificial Intelligence:**
  - AWS SageMaker for building, training, and deploying ML models.
  - AWS Rekognition for image and video analysis.

- **Internet of Things (IoT):**
  - AWS IoT Core to connect and manage IoT devices.
  - AWS IoT Analytics for analyzing IoT device data.

- **Security and Compliance:**
  - AWS Identity and Access Management (IAM) for secure access controls.
  - Amazon Cognito for user authentication.
  - AWS Shield for DDoS protection.

- **Analytics and Big Data:**
  - AWS Data Pipeline for data transportation and transformation.
  - AWS Lake Formation for building secure data lakes.
  - Amazon QuickSight for business intelligence and visualization.

- **Developer Tools:**
  - AWS CodeCommit for source control service.
  - AWS CodeBuild for compiling source code and running tests.
  - AWS CodeDeploy for automating code deployments.

- **Migration & Transfer Services:**
  - AWS Migration Hub for centralizing and monitoring migrations.
  - AWS Database Migration Service for simplifying database transfers.
  - Snow Family devices (Snowcone, Snowball, Snowmobile) for physical data transfer.

- **Augmented and Virtual Reality:**
  - AWS Sumerian for creating and running AR and VR applications.

- **Blockchain:**
  - Amazon Managed Blockchain for supporting blockchain network setups with Hyperledger Fabric and Ethereum.
  
### 10: The cloud journey

1. **Summarize the six pillars of the Well-Architected Framework.**

    - **Operational Excellence:** This pillar focuses on running and monitoring systems to deliver business value and continually improving processes and procedures. Key practices include automation of changes, responding to events, and defining standards to manage daily operations.

    - **Security:** The Security pillar emphasizes the protection of information & systems. Key topics include data confidentiality and integrity, identifying and managing who can do what with privilege management, protecting systems, and establishing controls to detect security events.

    - **Reliability:** This pillar ensures a workload performs its intended function correctly and consistently when it’s expected to. This involves the setup, monitoring, and rigorously testing of failover and recovery mechanisms to handle interruptions and the ability to dynamically acquire computing resources to meet demand and mitigate disruptions.

    - **Performance Efficiency:** This focuses on using computing resources efficiently to meet system requirements and maintaining that efficiency as demand changes and technologies evolve. It involves selecting the right resource types and sizes based on workload requirements, monitoring performance, and making informed decisions to maintain efficiency as business needs evolve.

    - **Cost Optimization:** The Cost Optimization pillar focuses on avoiding unnecessary costs. Key practices include understanding and controlling where money is being spent, selecting the most appropriate and right number of resource types, analyzing spend over time, and scaling to meet business needs without overspending.

    - **Sustainability:** Introduced to help you learn, measure, and improve your workloads using environmental best practices for cloud computing. This pillar helps organizations reduce the energy consumption of their applications and downstream impacts on the environment, which can also help to optimize costs.

2. **Explain the six benefits of cloud computing.**

    - **Trade Upfront Expense for Variable Expense:**
        - Instead of investing heavily in data centers and servers before knowing how you will use them, you pay only when you consume computing resources and based on how much you use. This shifts capital expenditure to operational expenditure.

    - **Benefit from Massive Economies of Scale:**
        - By using cloud services, you benefit from the economies of scale that a large organization like AWS achieves. Due to the vast amount of resources used, cloud providers can achieve higher efficiencies and lower costs per unit, which they can pass on to customers.

    - **Stop Guessing Capacity:**
        - The cloud provides the ability to access as much or as little capacity as you need, and dynamically scale to meet the particular requirements of your workload. This eliminates the need to predict and purchase capacity ahead of demands.

    - **Increase Speed and Agility:**
        - Cloud services provide developers and IT departments with the ability to quickly set up systems and deploy applications without having to wait for hardware, procure software, or deal with other long lead times associated with IT procurement. This agility can give businesses a significant competitive advantage.

    - **Stop Spending Money on Running and Maintaining Data Centers:**
        - Cloud computing removes the need for costly data center operations, including the hardware procurement, facilities management, and other overheads involved in running physical data centers. This not only reduces IT costs but also allows IT teams to focus on more important business goals.

    - **Go Global in Minutes:**
        - Deploying applications in multiple regions around the world can be done with just a few clicks. This means enterprises can provide lower latency and a better experience for their customers at minimal cost.

### 11: AWS Certified Cloud Practitioner

1. **Determine resources for preparing for the AWS Certified Cloud Practitioner exam.**
    - 
2. **Describe the benefits of becoming AWS Certified.**

3. **Exam Tips**
    - **Read the Full Question:** Ensure you understand every part of the question, paying attention to key words or phrases that might influence your answer choice.
    - **Predict the Answer:** Before looking at the response options, try to predict the correct answer based on your knowledge. This helps you focus on the right track without being swayed by incorrect options.
    - **Eliminate Incorrect Options:** Review all the response options and eliminate those you know are incorrect. This narrows down the choices and increases the likelihood of selecting the correct response.