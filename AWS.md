# AWS Cloud Practitioner Essentials

#### [Home](index.md) - [Algorithms](Algorithms.md) - [Cloud Computing](CloudComputing.md) - [Projects](Projects.md)

---

## Module 1: Introduction to AWS

1. **Summarize the benefits of AWS.**
   - On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing.

2. **Describe differences between on-demand delivery and cloud deployments.**
   - Private cloud deployment

3. **Summarize the pay-as-you-go pricing model.**
   - The aggregated cloud usage from a large number of customers results in lower pay-as-you-go prices.

---

## Module 2: Compute in the Cloud

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

## Module 3: Infrastructure and Reliability

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

## Module 4: Networking

1. **Describe the basic concepts of networking.**

2. **Describe the difference between public and private networking resources.**

3. **Explain a virtual private gateway using a real life scenario.**

4. **Explain a virtual private network (VPN) using a real life scenario.**

5. **Describe the benefit of AWS Direct Connect.**

6. **Describe the benefit of hybrid deployments.**

7. **Describe the layers of security used in an IT strategy.**

8. **Describe the services customers use to interact with the AWS global network.**

## Module 5: Storage and Databases

1. **Summarize the basic concept of storage and databases.**

2. **Describe the benefits of Amazon Elastic Block Store (Amazon EBS).**

3. **Describe the benefits of Amazon Simple Storage Service (Amazon S3).**

4. **Describe the benefits of Amazon Elastic File System (Amazon EFS).**

5. **Summarize various storage solutions.**

6. **Describe the benefits of Amazon Relational Database Service (Amazon RDS).**

7. **Describe the benefits of Amazon DynamoDB.**

8. **Summarize various database services.**

## Module 6: Security

1. **Explain the benefits of the shared responsibility model.**

2. **Describe multi-factor authentication (MFA).**

3. **Differentiate between the AWS Identity and Access Management (IAM) security levels.**

4. **Explain the main benefits of AWS Organizations.**

5. **Describe security policies at a basic level.**

6. **Summarize the benefits of compliance with AWS.**

7. **Explain additional AWS security services at a basic level.**

## Module 7: Monitoring and Analytics

1. **Summarize approaches to monitoring your AWS environment.**

2. **Describe the benefits of Amazon CloudWatch.**

3. **Describe the benefits of AWS CloudTrail.**

4. **Describe the benefits of AWS Trusted Advisor.**

## Module 8: Pricing and Support

1. **Describe AWS pricing and support models.**

2. **Describe the AWS Free Tier.**

3. **Describe key benefits of AWS Organizations and consolidated billing.**

4. **Explain the benefits of AWS Budgets.**

5. **Explain the benefits of AWS Cost Explorer.**

6. **Explain the primary benefits of the AWS Pricing Calculator.**

7. **Distinguish between the various AWS Support Plans.**

8. **Describe the benefits of AWS Marketplace.**

## Module 9: Migration and Innovation

1. **Understand migration and innovation in the AWS Cloud.**

2. **Summarize the AWS Cloud Adoption Framework (AWS CAF).**

3. **Summarize the six key factors of a cloud migration strategy.**

4. **Describe the benefits of AWS data migration solutions, such as AWS Snowcone, AWS Snowball, and AWS Snowmobile.**

5. **Summarize the broad scope of innovative solutions that AWS offers.**

## Module 10: The cloud journey

1. **Summarize the six pillars of the Well-Architected Framework.**

2. **Explain the six benefits of cloud computing.**

## Module 11: AWS Certified Cloud Practitioner

1. **Determine resources for preparing for the AWS Certified Cloud Practitioner exam.**

2. **Describe the benefits of becoming AWS Certified.**
