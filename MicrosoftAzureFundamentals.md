---
title: "Microsoft Azure Fundamentals"
---
## Module 1: Describe cloud concepts

### 1: Describe Cloud Computing

1. **Define Cloud Computing**
    - Cloud computing is the delivery of different services through the Internet, including data storage, servers, databases, networking, and software.

2. **Describe the Shared Responsibility Model**
    - The shared responsibility model defines the security responsibilities of cloud service providers and their customers to ensure accountability.

3. **Define Cloud Models, Including Public, Private, and Hybrid**
    - **Public Cloud**: Services are delivered over the public internet and shared across organizations.
    - **Private Cloud**: Services are maintained on a private network and used exclusively by one organization.
    - **Hybrid Cloud**: Combines public and private clouds, allowing data and applications to be shared between them.

4. **Identify Appropriate Use Cases for Each Cloud Model**
    - **Public Cloud**: Suitable for workloads with high scalability needs and less sensitive data.
    - **Private Cloud**: Ideal for organizations with strict regulatory requirements and sensitive data.
    - **Hybrid Cloud**: Best for businesses that require both flexibility and control over their data.

5. **Describe the Consumption-Based Model**
    - The consumption-based model allows users to pay only for the resources they use, similar to utility billing.

6. **Compare Cloud Pricing Models**
    - **Pay-as-you-go**: Pay for services as you use them without upfront costs.
    - **Reserved Instances**: Commit to using a specific amount of resources over a period for a discounted rate.
    - **Spot Pricing**: Purchase unused capacity at reduced rates, suitable for flexible, non-critical workloads.

### 2: Describe the Benefits of Using Cloud Services

1. **Describe the Benefits of High Availability and Scalability in the Cloud**
    - High availability ensures that cloud services are available with minimal downtime. Scalability allows resources to be adjusted based on demand.

2. **Describe the Benefits of Reliability and Predictability in the Cloud**
    - Reliability ensures consistent performance and uptime. Predictability allows for consistent and expected performance and costs.

3. **Describe the Benefits of Security and Governance in the Cloud**
    - Cloud providers offer robust security measures and compliance certifications to protect data and ensure regulatory compliance.

4. **Describe the Benefits of Manageability in the Cloud**
    - Cloud services offer tools and services to manage and monitor resources efficiently, reducing the complexity of IT management.

### 3: Describe Cloud Service Types

1. **Describe Infrastructure as a Service (IaaS)**
    - IaaS provides virtualized computing resources over the internet, such as virtual machines, storage, and networks.

2. **Describe Platform as a Service (PaaS)**
    - PaaS provides a platform allowing customers to develop, run, and manage applications without dealing with the underlying infrastructure.

3. **Describe Software as a Service (SaaS)**
    - SaaS delivers software applications over the internet, on a subscription basis, without the need for installation or maintenance.

4. **Identify Appropriate Use Cases for Each Cloud Service (IaaS, PaaS, SaaS)**
    - **IaaS**: Suitable for businesses needing control over their infrastructure without the cost of physical hardware.
    - **PaaS**: Ideal for developers who want to focus on building applications without managing the underlying infrastructure.
    - **SaaS**: Best for end-users who need access to software applications without worrying about maintenance or updates.

## Module 2: Microsoft Azure Fundamentals: Describe Azure architecture and services

### Part 2: Describe Azure architecture and services

#### 1: Describe the core architectural components of Azure

1. **Describe Azure regions, region pairs, and sovereign regions**
    - Azure regions are geographical areas containing one or more datacenters. Region pairs are two regions within the same geography for disaster recovery. Sovereign regions are isolated regions for compliance with specific regulations.

2. **Describe Availability Zones**
    - Availability Zones are physically separate locations within an Azure region, each with independent power, cooling, and networking to ensure high availability.

3. **Describe Azure datacenters**
    - Azure datacenters are facilities that house the physical servers and infrastructure supporting Azure services.

4. **Describe Azure resources and Resource Groups**
    - Azure resources are individual services or components, such as virtual machines or databases. Resource Groups are containers that hold related resources for management and organization.

5. **Describe subscriptions**
    - Subscriptions are agreements with Azure to use cloud services, providing access to resources and services.

6. **Describe management groups**
    - Management groups are containers that help manage access, policy, and compliance across multiple Azure subscriptions.

7. **Describe the hierarchy of resource groups, subscriptions, and management groups**
    - The hierarchy starts with management groups at the top, followed by subscriptions, and then resource groups, which contain the individual resources.

#### 2: Describe Azure compute and networking services

1. **Compare compute types, including container instances, virtual machines, and functions**
    - **Container Instances**: Lightweight, fast to start, and ideal for microservices and small applications.
    - **Virtual Machines (VMs)**: Provide full control over the operating system and applications, suitable for a wide range of workloads.
    - **Functions**: Serverless compute service that automatically scales and charges only for the compute time used, ideal for event-driven applications.

2. **Describe virtual machine (VM) options, including VMs, Virtual Machine Scale Sets, availability sets, Azure Virtual Desktop**
    - **VMs**: Individual virtual servers that can run various operating systems and applications.
    - **Virtual Machine Scale Sets**: Automatically manage and scale a set of identical VMs.
    - **Availability Sets**: Ensure that VMs are distributed across multiple isolated hardware nodes to avoid single points of failure.
    - **Azure Virtual Desktop**: A desktop and application virtualization service running on Azure.

3. **Describe resources required for virtual machines**
    - **Compute**: CPU and memory resources.
    - **Storage**: Disk storage for the operating system and data.
    - **Networking**: Virtual network interfaces and IP addresses.

4. **Describe application hosting options, including Azure Web Apps, containers, and virtual machines**
    - **Azure Web Apps**: Fully managed platform for building, deploying, and scaling web apps.
    - **Containers**: Lightweight, portable, and consistent environments for running applications.
    - **Virtual Machines**: Provide full control over the environment and are suitable for custom applications and legacy systems.

5. **Describe virtual networking, including the purpose of Azure Virtual Networks, Azure virtual subnets, peering, Azure DNS, VPN Gateway, and ExpressRoute**
    - **Azure Virtual Networks (VNet)**: Enable secure communication between Azure resources.
    - **Azure Virtual Subnets**: Segments within a VNet to organize and secure resources.
    - **Peering**: Connects VNets to allow resources to communicate across them.
    - **Azure DNS**: Provides domain name resolution for Azure services.
    - **VPN Gateway**: Establishes secure connections between Azure VNets and on-premises networks.
    - **ExpressRoute**: Provides private, high-bandwidth connections between Azure and on-premises networks.

6. **Define public and private endpoints**
    - **Public Endpoints**: Accessible over the internet.
    - **Private Endpoints**: Accessible only within a private network, enhancing security.

### Part 3: Describe Azure storage services

#### 1: Compare Azure storage services

1. **Azure Blob Storage**
    - Object storage solution for the cloud, optimized for storing massive amounts of unstructured data.

2. **Azure File Storage**
    - Fully managed file shares in the cloud that are accessible via the SMB protocol.

3. **Azure Queue Storage**
    - Service for storing large numbers of messages that can be accessed from anywhere via authenticated calls.

4. **Azure Table Storage**
    - NoSQL key-value store for rapid development using massive semi-structured datasets.

#### 2: Describe storage tiers

1. **Hot Tier**
    - Optimized for data that is accessed frequently.

2. **Cool Tier**
    - Optimized for data that is infrequently accessed and stored for at least 30 days.

3. **Cold Tier**
    - Optimized for data that is infrequently accessed and stored for at least 90 days.

4. **Archive Tier**
    - Optimized for data that is rarely accessed and stored for at least 180 days with flexible latency requirements.

#### 3: Describe redundancy options

1. **Locally Redundant Storage (LRS)**
    - Replicates data three times within a single datacenter.

2. **Zone-Redundant Storage (ZRS)**
    - Replicates data across three Azure availability zones in a region.

3. **Geo-Redundant Storage (GRS)**
    - Replicates data to a secondary region, providing higher durability.

4. **Read-Access Geo-Redundant Storage (RA-GRS)**
    - Same as GRS but also allows read access to the data in the secondary region.

#### 4: Describe storage account options and storage types

1. **General-purpose v2 (GPv2)**
    - Supports all the latest Azure storage features, including Blob, File, Queue, and Table storage.

2. **Blob Storage Accounts**
    - Specialized for storing unstructured data as blobs (objects).

3. **File Storage Accounts**
    - Specialized for file shares that use the SMB protocol.

#### 5: Identify options for moving files

1. **AzCopy**
    - Command-line utility for copying data to and from Azure storage.

2. **Azure Storage Explorer**
    - Standalone app for managing Azure storage data on Windows, macOS, and Linux.

3. **Azure File Sync**
    - Centralizes file shares in Azure Files while keeping the flexibility, performance, and compatibility of an on-premises file server.

#### 6: Describe migration options

1. **Azure Migrate**
    - Central hub for discovering, assessing, and migrating on-premises applications, infrastructure, and data to Azure.

2. **Azure Data Box**
    - Physical devices that help transfer large amounts of data to Azure when network transfer is not feasible.

### Part 4: Describe Azure identity, access, and security

#### 1: Describe directory services in Azure

1. **Microsoft Entra ID**
    - Microsoft Entra ID (formerly Azure Active Directory) is a cloud-based identity and access management service that helps employees sign in and access resources.

2. **Microsoft Entra Domain Services**
    - Provides managed domain services such as domain join, group policy, and LDAP, compatible with Windows Server Active Directory.

#### 2: Describe authentication methods in Azure

1. **Single Sign-On (SSO)**
    - Allows users to access multiple applications with a single set of login credentials, improving user experience and security.

2. **Multifactor Authentication (MFA)**
    - Requires two or more verification methods, adding an extra layer of security beyond just a password.

3. **Passwordless**
    - Authentication methods that do not require a password, such as biometrics or security keys, enhancing security and user convenience.

#### 3: Describe external identities and guest access in Azure

1. **External Identities**
    - Allows organizations to provide access to their resources to users outside their organization, such as partners or customers.

2. **Guest Access**
    - Enables collaboration by allowing external users to access internal resources while maintaining control over their data.

#### 4: Describe Microsoft Entra Conditional Access

- Conditional Access policies allow organizations to control access to their applications based on specific conditions, such as user location, device state, or risk level.

#### 5: Describe Azure Role Based Access Control (RBAC)

- RBAC allows organizations to manage access to Azure resources by assigning roles to users, groups, and applications, ensuring that users have only the permissions they need.

#### 6: Describe the concept of Zero Trust

- Zero Trust is a security model that assumes breaches are inevitable and focuses on verifying every access request, regardless of its origin, to protect resources.

#### 7: Describe the purpose of the defense in depth model

- Defense in depth is a layered security approach that uses multiple security measures to protect resources, ensuring that if one layer fails, others still provide protection.

#### 8: Describe the purpose of Microsoft Defender for Cloud

- Microsoft Defender for Cloud provides unified security management and advanced threat protection across hybrid cloud workloads, helping to detect and respond to threats.

## Module 3: Microsoft Azure Fundamentals: Describe Azure management and governance

### 1: Describe cost management in Azure

1. **Describe factors that can affect costs in Azure**
    - Factors that can affect costs in Azure include the type of resources used, the region where resources are deployed, the amount of data transfer, and the level of support and service agreements.

2. **Compare the Pricing calculator and Total Cost of Ownership (TCO) calculator**
    - **Pricing Calculator**: Helps estimate the cost of Azure services based on specific configurations and usage patterns.
    - **Total Cost of Ownership (TCO) Calculator**: Compares the cost of running workloads on-premises versus in Azure, considering factors like hardware, software, and operational costs.

3. **Describe the Microsoft Cost Management tool**
    - Microsoft Cost Management provides tools to monitor, allocate, and optimize cloud spending, helping organizations manage their Azure costs effectively.

4. **Describe the purpose of tags**
    - Tags are metadata elements that can be applied to Azure resources to organize and manage them effectively, enabling better cost tracking, resource management, and automation.

### 2: Describe features and tools in Azure for governance and compliance

1. **Describe the purpose of Microsoft Purview**
    - Microsoft Purview provides unified data governance solutions to manage and govern on-premises, multi-cloud, and software-as-a-service (SaaS) data.

2. **Describe the purpose of Azure Policy**
    - Azure Policy helps enforce organizational standards and assess compliance at scale by creating, assigning, and managing policies.

3. **Describe the purpose of resource locks**
    - Resource locks prevent accidental deletion or modification of critical resources by applying a lock at the subscription, resource group, or resource level.

4. **Describe the purpose of the Service Trust portal**
    - The Service Trust portal provides access to security, privacy, and compliance information for Microsoft services, helping organizations meet regulatory requirements.

### 3: Describe features and tools for managing and deploying Azure resources

1. **Describe Azure portal**
    - The Azure portal is a web-based interface that provides a unified view and management of Azure resources, allowing users to create, configure, and monitor services.

2. **Describe Azure Cloud Shell, including Azure CLI and Azure PowerShell**
    - Azure Cloud Shell is an integrated shell accessible from the Azure portal, providing a browser-based command-line experience with tools like Azure CLI and Azure PowerShell for managing Azure resources.

3. **Describe the purpose of Azure Arc**
    - Azure Arc extends Azure management and governance capabilities to on-premises, multi-cloud, and edge environments, enabling a consistent management experience across hybrid and multi-cloud environments.

4. **Describe Azure Resource Manager (ARM) and Azure ARM templates**
    - Azure Resource Manager (ARM) is the deployment and management service for Azure, providing a consistent management layer. ARM templates are JSON files that define the infrastructure and configuration for Azure resources, enabling repeatable deployments.

### 4: Describe monitoring tools in Azure

1. **Describe the purpose of Azure Advisor**
    - Azure Advisor provides personalized best practices and recommendations to optimize Azure deployments, focusing on high availability, security, performance, and cost.

2. **Describe Azure Service Health**
    - Azure Service Health provides personalized alerts and guidance when Azure service issues affect you, helping you understand the impact and keep your services running smoothly.

3. **Describe Azure Monitor, including Azure Log Analytics, Azure Monitor Alerts, and Application Insights**
    - **Azure Monitor**: Collects, analyzes, and acts on telemetry data from Azure and on-premises environments to maximize performance and availability.
    - **Azure Log Analytics**: A tool within Azure Monitor that helps collect and analyze log data from various sources.
    - **Azure Monitor Alerts**: Provides alerting and notification capabilities to proactively identify and address issues.
    - **Application Insights**: An application performance management service within Azure Monitor that helps monitor live applications, detect anomalies, and diagnose issues.

# Extended course with Microsoft AZ-305

[Link to Course](https://learn.microsoft.com/en-us/training/paths/microsoft-azure-architect-design-prerequisites/)

## Microsoft Cloud Adoption Framework for Azure

[Link to Module](https://learn.microsoft.com/en-us/training/modules/microsoft-cloud-adoption-framework-for-azure/)

1. **Learn How to Leverage the Cloud Adoption Framework to Identify Where Your Organization Is in the Digital Transformation Journey**
   - The Cloud Adoption Framework provides a structured approach to help organizations understand their current state in the digital transformation journey. It offers tools and best practices to assess readiness, plan adoption strategies, and implement changes effectively. By leveraging this framework, organizations can identify their strengths, weaknesses, and areas for improvement, ensuring a smoother transition to cloud technologies.

2. **Identify Triggers and Opportunities for Cloud Adoption**
   - Triggers for cloud adoption can include business events such as mergers, acquisitions, or the need for rapid scalability. Opportunities may arise from the need to innovate, reduce costs, or improve operational efficiency. The Cloud Adoption Framework helps organizations recognize these triggers and opportunities by providing a comprehensive analysis of business needs and aligning them with cloud capabilities. This ensures that cloud adoption is driven by strategic business goals rather than ad-hoc decisions.

3. **Recognize the Components Needed to Develop a Digital Transformation Strategy Around Your Business, People, and Technology**
   - Developing a digital transformation strategy involves aligning business objectives with technological capabilities and workforce readiness. Key components include:
     - **Business**: Understanding the organization's goals, market position, and competitive landscape to define clear objectives for digital transformation.
     - **People**: Assessing the skills and readiness of the workforce, providing necessary training, and fostering a culture of innovation and continuous improvement.
     - **Technology**: Identifying the right cloud services and solutions that align with business needs, ensuring security, compliance, and scalability. The Cloud Adoption Framework provides guidelines for integrating these components into a cohesive strategy that drives successful digital transformation.

## Introduction to the Microsoft Azure Well-Architected Framework

[Link to Module](https://learn.microsoft.com/en-us/training/modules/azure-well-architected-introduction/)

1. **Describe the Pillars of the Azure Well-Architected Framework**
   - The Azure Well-Architected Framework is built on five pillars:
     - **Reliability**: Ensures that your application can recover from failures and continue to function.
     - **Security**: Protects applications and data from threats.
     - **Cost Optimization**: Manages costs to maximize the value delivered.
     - **Operational Excellence**: Ensures that applications are effectively managed and operated.
     - **Performance Efficiency**: Ensures that the application performs well and scales to meet demands.

2. **Identify Key Principles for Creating a Solid Architectural Foundation**
   - Key principles for creating a solid architectural foundation include:
     - **Design for Reliability**: Implement strategies to handle failures and ensure continuous operation.
     - **Implement Security Best Practices**: Protect data and applications through robust security measures.
     - **Optimize Costs**: Use cost management tools and strategies to ensure efficient use of resources.
     - **Achieve Operational Excellence**: Use monitoring and management tools to maintain and improve operational processes.
     - **Ensure Performance Efficiency**: Design applications to scale and perform efficiently under varying loads.