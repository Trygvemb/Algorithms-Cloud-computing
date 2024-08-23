# AWS Cloud Practitioner Essentials

#### [Home](index.md) - [Algorithms](Algorithms.md) - [Cloud Computing](CloudComputing.md) - [Projects](Projects.md)
---
[Back](CloudComputing.md)


## Module 1: Introduction to AWS

### Module Learning Objectives

1. **Summarize the benefits of AWS.**
    - **Learnings:** 
    On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing.

2. **Describe differences between on-demand delivery and cloud deployments.**
    - **Learnings:** 
    Private cloud deployment

3. **Summarize the pay-as-you-go pricing model.**
    - **Learnings:** 
    The aggregated cloud usage from a large number of customers results in lower pay-as-you-go prices.

---

## Module 2: Compute in the Cloud

### Module Learning Objectives

1. **Describe the benefits of Amazon EC2 at a basic level.**
    - **Learnings:** 
    Amazon Elastic Compute Cloud (Amazon EC2) provides secure, resizable compute capacity in the cloud as Amazon EC2 instances. 

2. **Identify the different Amazon EC2 instance types.**
    - **Learnings:** 
    General purpose instances.
    Compute optimized instances.
    Memory optimized instances.
    Accelerated computing instances.
    Storage optimized instances.

3. **Differentiate between the various billing options for Amazon EC2.**
    - **Learnings:** 
        - **On-Demand** Instances are ideal for short-term, irregular workloads that cannot be interrupted. No upfront costs or minimum contracts apply. The instances run continuously until you stop them, and you pay for only the compute time you use.

        - **Reserved Instances** are a billing discount applied to the use of On-Demand Instances in your account. There are two available types of Reserved Instances:

            - Standard Reserved Instances
            - Convertible Reserved Instances
        
        - **EC2 Instance Savings Plans** reduce your EC2 instance costs when you make an hourly spend commitment to an instance family and Region for a 1-year or 3-year term. This term commitment results in savings of up to 72 percent compared to On-Demand rates. Any usage up to the commitment is charged at the discounted Savings Plans rate (for example, $10 per hour). Any usage beyond the commitment is charged at regular On-Demand rates.

        - **Spot Instances** are ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity and offer you cost savings at up to 90% off of On-Demand prices.

        - **Dedicated Hosts** are physical servers with Amazon EC2 instance capacity that is fully dedicated to your use. 

4. **Summarize the benefits of Amazon EC2 Auto Scaling.**
    - **Learnings:** 
        - You start with only the resources you need and design your architecture to automatically respond to changing demand by scaling out or in. This lets you pay only for the resources you use and you will always have the capacity you need.

5. **Summarize the benefits of Elastic Load Balancing.**
    - **Learnings:** 
        - **Elastic Load Balancing** is the AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances. 

6. **Give an example of the uses for Elastic Load Balancing.**
    - **Learnings:** 
        - In Low demand periods there will only be the minimum allocated EC2 instances and the Elastic load balancing will direct the traffic to these, when demand rises there will be an increase in EC2 instances, these new instances will tell the Load Elastic Balancing that they are online and the Balancer will distribute the traffic between all instances.

7. **Summarize the differences between Amazon Simple Notification Service (Amazon SNS) and Amazon Simple Queue Service (Amazon SQS).**
    - **Learnings:** 
        - **(Amazon SNS)** is a publish/subscribe service. Using Amazon SNS topics, a publisher publishes messages to subscribers.
        - **(Amazon SQS)** is a message queuing service. You can send, store, and receive messages between software components, without losing messages or requiring other services to be available.

8. **Summarize additional AWS compute options.**
    - **Learnings:** 
        - **AWS Lambda** is a service that lets you run code without needing to provision or manage servers. 
        - **Amazon Elastic Container Service** (Amazon ECS) is a highly scalable, high-performance container management system that enables you to run and scale containerized applications on AWS. 
        - **Amazon Elastic Kubernetes Service** (Amazon EKS)(opens in a new tab) is a fully managed service that you can use to run Kubernetes on AWS. 
        - **AWS Fargate** is a serverless compute engine for containers. It works with both Amazon ECS and Amazon EKS.

---

## Module 3: [Module Name]

### Module Learning Objectives

1. **[Learning Objective 1]**
    - **Learnings:** 

2. **[Learning Objective 2]**
    - **Learnings:** 

3. **[Learning Objective 3]**
    - **Learnings:** 

4. **Summarize the benefits of Amazon EC2 Auto Scaling.**
    - **Learnings:** 

5. **Summarize the benefits of Elastic Load Balancing.**
    - **Learnings:** 

6. **Give an example of the uses for Elastic Load Balancing.**
    - **Learnings:** 

6. **Summarize the differences between Amazon Simple Notification Service (Amazon SNS) and Amazon Simple Queue Service (Amazon SQS).**
    - **Learnings:** 

7. **Summarize additional AWS compute options.**
    - **Learnings:** 
