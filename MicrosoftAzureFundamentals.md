---
title: "Microsoft Azure Fundamentals"
---
## Part 1: Describe cloud concepts

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

## Part 2: Describe Azure architecture and services

### 1: Describe the core architectural components of Azure

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

### 2: Describe Azure compute and networking services

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

## Part 3: Describe Azure management and governance.

## Part 3: Describe Azure management and governance.
