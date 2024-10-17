---
title: Azure Developer Career Path
---

[Link to Course](https://learn.microsoft.com/en-au/plans/prq5a8d0egog4j#learn-wwl-create-azure-app-service-web-apps)

You develop code, scripts, systems, and/or tools that reduce operational burden by automating complex and repetitive tasks, enable product engineering teams to increase the velocity at which they can safely deploy changes to production, and monitor the effects of changes across systems, services, and/or products.

## Learning outcomes

1. Develop Azure compute solutions
2. Develop for Azure storage
3. Implement Azure security
4. Monitor, troubleshoot, and optimize Azure solutions
5. Connect to and consume Azure services and third-party services

## 1 Implement Azure App Service web apps [Link](https://learn.microsoft.com/en-au/training/paths/create-azure-app-service-web-apps/)

Learn how Azure App Service functions and how to create and update an app. Explore App Service authentication and authorization, configuring app settings, scale apps, and how to use deployment slots.

### 1.1 Explore Azure App Service

#### 1.1.1 **Describe Azure App Service key components and value.**

- **Azure App Service** is a fully managed platform for building, deploying, and scaling web apps. It supports multiple programming languages like .NET, Java, Node.js, Python, and PHP.

- **Key components**:
  - **Web Apps**: Host and deploy web applications.
  - **API Apps**: Create and host RESTful APIs.
  - **Mobile Apps**: Build and host backend mobile services.
  - **App Service Environment (ASE)**: A fully isolated environment for running applications at scale in a private network.
- **Value**:
  - Fully managed infrastructure, meaning Azure handles the platform, scaling, and infrastructure updates.
  - Integrated continuous deployment with popular development environments such as GitHub, Azure DevOps, and Bitbucket.
  - Built-in load balancing, traffic management, and disaster recovery.  

#### 1.1.2 **Explain how Azure App Service manages authentication and authorization.**

- **Authentication** in Azure App Service can be managed using **Azure Active Directory (Azure AD)** or third-party identity providers like **Google, Facebook, and Microsoft Accounts**.
- **App Service Authentication/Authorization** (also known as Easy Auth) can be configured to authenticate users without writing any custom authentication logic.
- **Azure AD** can be used for single sign-on (SSO), making it easy to integrate corporate logins for enterprise-level security.
- Developers can configure **OAuth 2.0** and **OpenID Connect** for handling authorization and token-based access.

#### 1.1.3 **Identify methods to control inbound and outbound traffic to your web app.**

- **Inbound Traffic Control**:
  - **IP Restrictions**: Limit incoming traffic to specific IP ranges to improve security.
  - **Virtual Network Integration**: Integrate your app with an Azure Virtual Network (VNet) to securely communicate with your other services.
  - **App Service Environment (ASE)**: Used to run apps in an isolated, highly secure environment.

- **Outbound Traffic Control**:
  - **Service Endpoints**: Securely connect your App Service to Azure services like Azure Storage and Azure SQL through private endpoints.
  - **Private Endpoints**: Use private links to ensure that all outbound traffic flows through a secure and private network, avoiding exposure to the public internet.
  - **Route Tables**: Control the route of outbound traffic to enforce security policies and direct traffic based on destination IP addresses.

#### 1.1.4 **Deploy an app to Azure App Service using Azure CLI commands.**

Deployed using Sandbox during the course

---

### 1.2 Configure web app settings

#### 1.2.1 **Create application settings that are bound to deployment slots.**

- **Deployment Slots**: Azure App Service allows you to create multiple deployment slots (e.g., staging, production) for your web app.
- **Slot-specific Settings**: Application settings can be configured to be slot-specific, meaning they can have different values in different slots.
  - **Example**: You might have a connection string that points to a test database in the staging slot and a production database in the production slot.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Deployment slots** and select the slot you want to configure.
  - Under **Settings**, select **Configuration** and add or modify the application settings.

#### 1.2.2 **Explain the options for installing SSL/TLS certificates for your app.**

- **SSL/TLS Certificates**: Secure your web app by installing SSL/TLS certificates.
- **Options**:
  - **App Service Managed Certificate**: Free SSL certificates provided by Azure for custom domains.
  - **Bring Your Own Certificate (BYOC)**: Upload your own SSL certificate purchased from a Certificate Authority (CA).
  - **Azure Key Vault**: Store and manage your SSL certificates securely in Azure Key Vault and bind them to your web app.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **TLS/SSL settings** and select **Private Key Certificates (.pfx)** to upload your certificate.
  - Bind the certificate to your custom domain under **Custom domains**.

#### 1.2.3 **Enable diagnostic logging for your app to aid in monitoring and debugging.**

- **Diagnostic Logging**: Helps in monitoring and debugging your web app by capturing detailed logs.
- **Types of Logs**:
  - **Application Logging**: Captures logs generated by your application code.
  - **Web Server Logging**: Captures logs from the web server hosting your app.
  - **Detailed Error Messages**: Provides detailed error information for failed requests.
  - **Failed Request Tracing**: Captures detailed information about failed requests.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Monitoring** and select **Diagnostic settings**.
  - Enable the desired logging options and configure the log storage (e.g., Azure Storage, Log Analytics).

#### 1.2.4 **Create virtual app to directory mappings.**

- **Virtual Applications**: Allows you to map a URL path to a specific directory in your web app.
- **Use Cases**: Useful for organizing large applications or hosting multiple applications under a single domain.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Configuration** and select the **Path mappings** tab.
  - Add a new virtual application by specifying the **Virtual Path** and the **Physical Path**.

---

### 1.3 Scale apps in Azure App Service

#### 1.3.1 **Identify scenarios for which autoscaling is an appropriate solution.**

- **High Traffic Periods**: Autoscaling is useful when your web app experiences varying levels of traffic, such as during sales events or marketing campaigns.
- **Resource Optimization**: Helps in optimizing resource usage by scaling out during peak times and scaling in during off-peak times.
- **Cost Management**: Reduces costs by only using additional resources when necessary.
- **Performance Maintenance**: Ensures consistent performance by automatically adjusting resources based on demand.

#### 3.2 **Create autoscaling rules for a web app.**

- **Autoscaling Rules**: Define conditions under which your web app should scale out (add more instances) or scale in (remove instances).
- **Metrics**: Common metrics used for autoscaling include CPU usage, memory usage, and HTTP request count.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Scale out (App Service plan)** under **Settings**.
  - Select **Custom autoscale** and define your scaling rules based on the desired metrics and thresholds.
  - Save the configuration to apply the autoscaling rules.

#### 1.3.3 **Monitor the effects of autoscaling.**

- **Monitoring Tools**: Use Azure Monitor and Application Insights to track the performance and effects of autoscaling.
- **Metrics to Monitor**:
  - **Instance Count**: Number of instances running at any given time.
  - **CPU and Memory Usage**: Resource usage metrics to ensure the app is scaling appropriately.
  - **Response Time**: Monitor the response time to ensure performance is maintained.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Monitoring** and select **Metrics**.
  - Add the relevant metrics to your dashboard to visualize the effects of autoscaling.
  - Set up alerts to notify you of any issues or anomalies.

### 1.4 Explore Azure App Service deployment slots

#### 1.4.1 **Describe the benefits of using deployment slots.**

- **Zero-Downtime Deployments**: Deployment slots allow you to deploy your app updates without any downtime by swapping slots.
- **Testing in Production**: You can test your app in a production-like environment before swapping it to the production slot.
- **Rollback Capability**: If an issue is found after swapping, you can quickly roll back to the previous version by swapping the slots again.
- **Configuration Differences**: Each slot can have its own configuration settings, such as connection strings and app settings, allowing for environment-specific configurations.

#### 1.4.2 **Understand how slot swapping operates in App Service.**

- **Slot Swapping**: The process of exchanging the content and configuration settings of two deployment slots.
- **Warm-Up**: Before swapping, the target slot is warmed up to ensure that the app is ready to handle traffic immediately after the swap.
- **Atomic Operation**: The swap operation is atomic, meaning it either completes fully or not at all, ensuring consistency.
- **Traffic Redirection**: After the swap, the traffic is redirected to the new slot seamlessly.

#### 1.4.3 **Perform manual swaps and enable auto swap.**

- **Manual Swap**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Deployment slots** and select the slot you want to swap.
  - Click on **Swap** and choose the target slot to swap with.
  - Confirm the swap to initiate the process.

- **Auto Swap**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Deployment slots** and select the slot you want to configure for auto swap.
  - Under **Settings**, select **Configuration** and enable **Auto Swap**.
  - Specify the target slot for auto swap and save the configuration.

#### 1.4.4 **Route traffic manually and automatically.**

- **Manual Traffic Routing**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Deployment slots** and select **Traffic routing**.
  - Manually adjust the traffic percentage for each slot to control the flow of traffic.

- **Automatic Traffic Routing**:
  - Use **Traffic Manager** to automatically route traffic based on performance, geographic location, or other criteria.
  - Configure **Traffic Manager** profiles and endpoints to manage traffic distribution across slots or different regions.

## 2 Implement Azure Functions [Link](https://learn.microsoft.com/en-au/training/paths/implement-azure-functions/)

Learn how to create and deploy Azure Functions. Explore hosting options, bindings, and triggers.

### 2.1 Explore Azure Functions

Azure Functions lets you develop serverless applications on Microsoft Azure. You can write just the code you need for the problem at hand, without worrying about a whole application or the infrastructure to run it.

#### 2.1.1 **Explain functional differences between Azure Functions, Azure Logic Apps, and WebJobs.**

- **Azure Functions**: Serverless compute service that allows you to run event-driven code without managing infrastructure. Ideal for microservices, real-time processing, and scheduled tasks.
- **Azure Logic Apps**: Workflow automation service that integrates apps, data, services, and systems. Best for orchestrating complex workflows and integrating with various services.
- **WebJobs**: Feature of Azure App Service that runs background tasks. Suitable for long-running processes and tasks that need to run alongside web apps.

#### 2.1.2 **Describe Azure Functions hosting plan options.**

- **Consumption Plan**: Automatically scales and you only pay for the compute resources used. Ideal for small or unpredictable workloads.
- **Premium Plan**: Provides enhanced performance and VNET integration. Suitable for enterprise-level applications requiring consistent performance.
- **Dedicated (App Service) Plan**: Runs on dedicated VMs, allowing for more control over the environment. Best for applications with specific infrastructure requirements.

#### 2.1.3 **Describe how Azure Functions scale to meet business needs.**

- **Automatic Scaling**: Azure Functions automatically scale out based on demand, handling spikes in traffic without manual intervention.
- **Scaling Triggers**: Functions can scale based on various triggers such as HTTP requests, queue messages, or event grid events.
- **Custom Scaling Rules**: In Premium and Dedicated plans, you can define custom scaling rules to meet specific business requirements.

### 2.2 Develop Azure Functions

Functions share a few core technical concepts and components, regardless of the language or binding you use.

#### 2.2.1 **Explain the key components of a function and how they are structured**

- **Function**: The core unit of Azure Functions, containing the code that executes in response to a trigger.
- **Trigger**: Defines how a function is invoked. Common triggers include HTTP requests, timers, and messages from queues.
- **Bindings**: Simplify the connection to other services by declaratively connecting inputs and outputs to the function.
- **Function App**: A container for one or more functions, providing a shared execution context and configuration.

#### 2.2.2 **Create triggers and bindings to control when a function runs and where the output is directed**

- **Triggers**: Define the event that starts the function. Examples include:
  - **HTTP Trigger**: Runs the function in response to an HTTP request.
  - **Timer Trigger**: Runs the function on a specified schedule.
  - **Queue Trigger**: Runs the function when a new message is added to a queue.
- **Bindings**: Define the input and output data sources. Examples include:
  - **Input Bindings**: Read data from sources like Azure Storage, Cosmos DB, or HTTP requests.
  - **Output Bindings**: Write data to destinations like Azure Storage, Cosmos DB, or HTTP responses.

#### 2.2.3 **Connect a function to services in Azure**

- **Azure Storage**: Use bindings to read from or write to Azure Blob Storage, Table Storage, or Queues.
- **Cosmos DB**: Use bindings to interact with Cosmos DB for scalable and globally distributed data.
- **Event Grid**: Use triggers to respond to events from Azure services or custom sources.
- **Service Bus**: Use triggers and bindings to process messages from Azure Service Bus queues and topics.

#### 2.2.4 **Create a function by using Visual Studio Code and the Azure Functions Core Tools**

- **Setup**:
  - Install **Visual Studio Code** and the **Azure Functions extension**.
  - Install the **Azure Functions Core Tools**.
- **Create a New Function**:
  - Open Visual Studio Code and use the Azure Functions extension to create a new project.
  - Choose a language and a template for your function (e.g., HTTP trigger).
  - Implement the function logic in the generated code file.
- **Run and Test Locally**:
  - Use the Azure Functions Core Tools to run the function locally.
  - Test the function using tools like Postman or curl for HTTP triggers.
- **Deploy to Azure**:
  - Use the Azure Functions extension to deploy the function to Azure.
  - Monitor and manage the function in the Azure portal.

## 3 Develop solutions that use Blob storage [Link](https://learn.microsoft.com/en-au/training/paths/develop-solutions-that-use-blob-storage/)

Learn how to create Azure Blob storage resources, manage data through the blob storage lifecycle, and work with containers and items by using the Azure Blob storage client library V12 for .NET.

### 3.1 Explore Azure Blob storage

#### 3.1.1 **Understanding Azure Blob Storage: Features, Types of Storage Accounts, and Access Tiers**

- **Features**:
  - **Scalability**: Handles large amounts of unstructured data.
  - **Durability**: Data is replicated to ensure high availability.
  - **Security**: Supports encryption and access control mechanisms.
  - **Integration**: Easily integrates with other Azure services.

- **Types of Storage Accounts**:
  - **General-purpose v2**: Supports all storage services and features.
  - **Blob Storage**: Optimized for storing large amounts of unstructured data.
  - **Premium Block Blob**: Provides low-latency access for high transaction workloads.

- **Access Tiers**:
  - **Hot**: Optimized for data that is accessed frequently.
  - **Cool**: Suitable for data that is infrequently accessed and stored for at least 30 days.
  - **Archive**: Best for data that is rarely accessed and stored for at least 180 days.

#### 3.1.2 **Understanding Azure Blob Storage: Storage Accounts, Containers, and Blobs**

- **Storage Accounts**: Provide a unique namespace for your Azure Storage data.
- **Containers**: Organize blobs within a storage account, similar to directories in a file system.
- **Blobs**: Store the actual data. Types of blobs include:
  - **Block Blobs**: Store text and binary data, ideal for files and documents.
  - **Append Blobs**: Optimized for append operations, suitable for logging.
  - **Page Blobs**: Store random-access files up to 8 TB in size, used for virtual hard disks.

#### 3.1.3 **Understanding Azure Storage Security and Encryption Features**

- **Security Features**:
  - **Shared Access Signatures (SAS)**: Provide limited access to storage resources.
  - **Azure Active Directory (AAD)**: Integrate with AAD for fine-grained access control.
  - **Role-Based Access Control (RBAC)**: Assign roles to users and groups for access management.

- **Encryption Features**:
  - **Server-Side Encryption (SSE)**: Automatically encrypts data at rest using Microsoft-managed keys or customer-managed keys.
  - **Client-Side Encryption**: Encrypts data before uploading to Azure Storage.
  - **Transport Layer Security (TLS)**: Ensures data is encrypted during transit.

### 3.2 Manage the Azure Blob storage lifecycle

#### 3.2.1 **Describe how each of the access tiers is optimized**

- **Hot Tier**:
  - Optimized for data that is accessed frequently.
  - Low latency and high throughput.
  - Higher storage costs but lower access costs.

- **Cool Tier**:
  - Suitable for data that is infrequently accessed and stored for at least 30 days.
  - Lower storage costs compared to the hot tier.
  - Higher access costs and retrieval latency.

- **Archive Tier**:
  - Best for data that is rarely accessed and stored for at least 180 days.
  - Lowest storage costs.
  - Highest access costs and retrieval latency, as data needs to be rehydrated before access.

#### 3.2.2 **Create and implement a lifecycle policy**

- **Lifecycle Management**: Automates the transition of blobs between access tiers based on specified rules.
- **Policy Creation**:
  - Navigate to your storage account in the Azure portal.
  - Go to **Lifecycle Management** under **Data management**.
  - Define rules to transition blobs to cooler tiers or delete them based on their age or last access time.
  - Save the policy to apply it to your storage account.

#### 3.2.3 **Rehydrate blob data stored in an archive tier**

- **Rehydration Process**:
  - Navigate to your storage account in the Azure portal.
  - Go to the **Blobs** section and locate the archived blob.
  - Change the access tier of the blob to **Hot** or **Cool** to initiate rehydration.
  - The rehydration process may take several hours, depending on the size of the blob.
  - Once rehydrated, the blob will be accessible in the specified tier.

### 3.3 Work with Azure Blob storage

#### 3.3.1 **Create an application to create and manipulate data by using the Azure Storage client library for Blob storage**

- **Setup**:
  - Install the **Azure.Storage.Blobs** NuGet package in your .NET project.
  - Configure your **Azure Storage account connection string** in your application settings.

See the [official documentation](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-dotnet) for detailed instructions on creating and manipulating data using the Azure Storage client library for Blob storage.

## 4 Develop solutions that use Azure Cosmos DB [Link](https://learn.microsoft.com/en-au/training/paths/az-204-develop-solutions-that-use-azure-cosmos-db/)

Learn how to create Azure Cosmos DB resources with the appropriate consistency levels, and perform data operations by using the .NET SDK V3 for Azure Cosmos DB.

### 4.1 Explore Azure Cosmos DB

Azure Cosmos DB is a globally distributed database system that allows you to read and write data from the local replicas of your database and it transparently replicates the data to all the regions associated with your Cosmos account.

#### 4.1.1 **Identify the key benefits provided by Azure Cosmos DB**

- **Global Distribution**: Distribute data across multiple Azure regions with multi-master replication.
- **Elastic Scalability**: Automatically scale throughput and storage based on demand.
- **Low Latency**: Provides single-digit millisecond response times for both reads and writes.
- **Multiple APIs**: Supports various APIs including SQL, MongoDB, Cassandra, Gremlin, and Table.
- **Comprehensive SLAs**: Offers SLAs for availability, throughput, consistency, and latency.

#### 4.1.2 **Describe the elements in an Azure Cosmos DB account and how they're organized**

- **Account**: The top-level resource that contains databases.
- **Database**: A container for collections, graphs, or tables.
- **Container**: Stores items and is the unit of scalability.
- **Item**: The actual data stored in JSON format within a container.

#### 4.1.3 **Explain the different consistency levels and choose the correct one for your project**

- **Strong**: Guarantees linearizability, ensuring the most recent write is always read.
- **Bounded Staleness**: Guarantees reads lag behind writes by a specified time or number of versions.
- **Session**: Guarantees consistency within a single session.
- **Consistent Prefix**: Guarantees reads never see out-of-order writes.
- **Eventual**: Guarantees eventual consistency without ordering guarantees.

#### 4.1.4 **Explore the APIs supported in Azure Cosmos DB and choose the appropriate API for your solution**

- **SQL API**: For querying JSON documents using SQL syntax.
- **MongoDB API**: For applications using MongoDB drivers.
- **Cassandra API**: For applications using Cassandra drivers.
- **Gremlin API**: For graph-based applications.
- **Table API**: For applications using Azure Table storage.

#### 4.1.5 **Describe how request units impact costs**

- **Request Units (RUs)**: Measure the cost of database operations. Each operation consumes a certain number of RUs.
- **Cost Management**: Optimize costs by adjusting the provisioned throughput (RUs per second) based on workload requirements.

#### 4.1.6 **Create Azure Cosmos DB resources by using the Azure portal**

- **Setup**:
  - Navigate to the Azure portal and create a new Azure Cosmos DB account.
  - Choose the desired API and configure the account settings.
  - Create a new database and container within the account.
  - Define the partition key and provision throughput for the container.

### 4.2 Work with Azure Cosmos DB

#### 4.2.1 **Identify classes and methods used to create resources**

- **CosmosClient**: The primary class for interacting with Azure Cosmos DB.
- **Database**: Represents a database in Azure Cosmos DB.
- **Container**: Represents a container within a database.
- **Item**: Represents an item within a container.

#### 4.2.2 **Create resources by using the Azure Cosmos DB .NET v3 SDK**

- **Setup**:
  - Install the **Microsoft.Azure.Cosmos** NuGet package in your .NET project.
  - Initialize a **CosmosClient** instance with your connection string.
  - Use the client to create databases, containers, and items.

#### 4.2.3 **Write stored procedures, triggers, and user-defined functions by using JavaScript**

- **Stored Procedures**: Define server-side logic executed within a transaction.
- **Triggers**: Execute custom logic before or after operations on items.
- **User-Defined Functions (UDFs)**: Extend query capabilities with custom logic.

#### 4.2.4 **Implement change feed notifications**

- **Change Feed**: Provides a sorted list of changes (inserts and updates) to items within a container.
- **Setup**:
  - Use the **ChangeFeedProcessor** class to process changes.
  - Configure the processor to listen for changes and handle them accordingly.

## 5 Implement containerized solutions [Link](https://learn.microsoft.com/en-au/training/paths/az-204-implement-iaas-solutions/)

Learn how to create and deploy containerized solutions to Azure by using the Azure Container Registry, Azure Container Instances, and Azure Container Apps.

### 5.1 Manage container images in Azure Container Registry

Azure Container Registry (ACR) is a managed, private Docker registry service based on the open-source Docker Registry 2.0. Create and maintain Azure container registries to store and manage your private Docker container images.

#### 5.1.1 **Explain the features and benefits Azure Container Registry offers**

- **Managed Service**: Fully managed by Azure, reducing operational overhead.
- **Private Registry**: Securely store and manage Docker container images.
- **Integration**: Seamlessly integrates with Azure Kubernetes Service (AKS) and other Azure services.
- **Geo-Replication**: Replicate container images across multiple Azure regions for high availability.
- **ACR Tasks**: Automate image builds and deployments with ACR Tasks.

#### 5.1.2 **Describe how to use ACR Tasks to automate builds and deployments**

- **ACR Tasks**: Automate container image builds and deployments directly within ACR.
- **Build Tasks**: Define tasks to build images from Dockerfiles or source code repositories.
- **Multi-Step Tasks**: Create complex workflows with multiple steps, including build, test, and deploy.
- **Triggers**: Automatically trigger tasks based on source code changes, base image updates, or schedule.

#### 5.1.3 **Explain the elements in a Dockerfile**

- **FROM**: Specifies the base image for the container.
- **RUN**: Executes commands in the container during the build process.
- **COPY**: Copies files from the host to the container.
- **CMD**: Specifies the command to run when the container starts.
- **EXPOSE**: Defines the ports the container listens on.
- **ENV**: Sets environment variables in the container.

#### 5.1.4 **Build and run an image in the ACR by using Azure CLI**

- **Build Image**:
  - Use `az acr build` to build a Docker image from a Dockerfile.
  - Example: `az acr build --registry <ACR_NAME> --image <IMAGE_NAME> .`
- **Run Image**:
  - Use `az acr repository show-tags` to list available images.
  - Deploy the image to a container service like Azure Kubernetes Service (AKS) or Azure Container Instances (ACI).

### 5.2 Run container images in Azure Container Instances

Learn how Azure Container Instances can help you quickly deploy containers, how to set environment variables, and specify container restart policies.

#### 5.2.1 **Describe the benefits of Azure Container Instances and how resources are grouped**

- **Quick Deployment**: Deploy containers without managing virtual machines or orchestrators.
- **Scalability**: Scale containers up or down based on demand.
- **Isolation**: Run containers in isolated environments for security.
- **Resource Grouping**: Group related resources for easier management and billing.

#### 5.2.2 **Deploy a container instance in Azure by using the Azure CLI**

- **Deploy Container**:
  - Use `az container create` to deploy a container instance.
  - Example: `az container create --resource-group <RESOURCE_GROUP> --name <CONTAINER_NAME> --image <IMAGE_NAME> --cpu 1 --memory 1.5`

#### 5.2.3 **Start and stop containers using policies**

- **Restart Policies**:
  - **Always**: Always restart the container if it stops.
  - **OnFailure**: Restart the container only if it stops with an error.
  - **Never**: Never restart the container.
  - Example: `az container create --restart-policy OnFailure`

#### 5.2.4 **Set environment variables in your container instances**

- **Environment Variables**:
  - Use `--environment-variables` to set environment variables.
  - Example: `az container create --environment-variables KEY=VALUE`

#### 5.2.5 **Mount file shares in your container instances**

- **Mount Azure File Share**:
  - Use `--azure-file-volume-account-name`, `--azure-file-volume-account-key`, and `--azure-file-volume-share-name` to mount an Azure File Share.
  - Example: `az container create --azure-file-volume-account-name <STORAGE_ACCOUNT> --azure-file-volume-account-key <ACCOUNT_KEY> --azure-file-volume-share-name <SHARE_NAME>`

### 5.3 Implement Azure Container Apps

Learn how Azure Container Apps can help you deploy and manage microservices and containerized apps on a serverless platform that runs on top of Azure Kubernetes Service.

#### 5.3.1 **Describe the benefits of Azure Container Apps**

- **Serverless Platform**: Deploy and manage containerized apps without managing infrastructure.
- **Microservices**: Ideal for deploying microservices architectures.
- **Scalability**: Automatically scale based on HTTP traffic, events, or custom metrics.
- **Integration**: Integrates with Dapr for building distributed applications.

#### 5.3.2 **Deploy a container app in Azure by using the Azure CLI**

- **Deploy Container App**:
  - Use `az containerapp create` to deploy a container app.
  - Example: `az containerapp create --resource-group <RESOURCE_GROUP> --name <APP_NAME> --image <IMAGE_NAME> --environment <ENVIRONMENT_NAME>`

#### 5.3.3 **Start and stop containers using policies**

- **Scaling Policies**:
  - Define scaling rules based on HTTP traffic, events, or custom metrics.
  - Example: `az containerapp scale --name <APP_NAME> --resource-group <RESOURCE_GROUP> --min-replicas 1 --max-replicas 10`

#### 5.3.4 **Set environment variables in your container apps**

- **Environment Variables**:
  - Use `--env-vars` to set environment variables.
  - Example: `az containerapp update --name <APP_NAME> --resource-group <RESOURCE_GROUP> --env-vars KEY=VALUE`

#### 5.3.5 **Mount file shares in your container apps**

- **Mount Azure File Share**:
  - Use `--storage-account-name`, `--storage-account-key`, and `--storage-share-name` to mount an Azure File Share.
  - Example: `az containerapp update --name <APP_NAME> --resource-group <RESOURCE_GROUP> --storage-account-name <STORAGE_ACCOUNT> --storage-account-key <ACCOUNT_KEY> --storage-share-name <SHARE_NAME>`

## 6 Implement user authentication and authorization [Link](https://learn.microsoft.com/en-au/training/paths/az-204-implement-authentication-authorization/)

Learn how to implement authentication and authorization to resources by using the Microsoft identity platform, Microsoft Authentication Library, shared access signatures, and use Microsoft Graph.

### 6.1 Explore the Microsoft identity platform

#### 6.1.1 **Identify the components of the Microsoft identity platform**

- **Azure Active Directory (Azure AD)**: The backbone of the Microsoft identity platform, providing identity and access management.
- **OAuth 2.0 and OpenID Connect**: Protocols used for authentication and authorization.
- **Microsoft Authentication Library (MSAL)**: Libraries for integrating authentication into applications.

#### 6.1.2 **Describe the three types of service principals and how they relate to application objects**

- **User Principal**: Represents a user in Azure AD.
- **Application Principal**: Represents an application in Azure AD.
- **Managed Identity**: Represents a service principal for Azure resources, simplifying access to other resources.

#### 6.1.3 **Explain how permissions and user consent operate, and how conditional access impacts your application**

- **Permissions**: Define what an application can do on behalf of a user or itself.
- **User Consent**: Users must consent to the permissions an application requests.
- **Conditional Access**: Policies that control access to applications based on conditions like user location, device state, and risk level.

### 6.2 Implement authentication by using the Microsoft Authentication Library

#### 6.2.1 **Explain the benefits of using MSAL and the application types and scenarios it supports**

- **Benefits**: Simplifies authentication, supports multiple platforms, and integrates with Azure AD.
- **Application Types**: Supports web apps, mobile apps, desktop apps, and daemon apps.
- **Scenarios**: Single sign-on (SSO), multi-factor authentication (MFA), and conditional access.

#### 6.2.2 **Instantiate both public and confidential client apps from code**

- **Public Client**: Used for apps that run on devices or desktops.
  ```csharp
  var publicClientApp = PublicClientApplicationBuilder.Create(clientId)
      .WithRedirectUri(redirectUri)
      .Build();
  ```
- **Confidential Client**: Used for apps that run on servers.
  ```csharp
  var confidentialClientApp = ConfidentialClientApplicationBuilder.Create(clientId)
      .WithClientSecret(clientSecret)
      .WithRedirectUri(redirectUri)
      .Build();
  ```

#### 6.2.3 **Register an app with the Microsoft identity platform**

- **Azure Portal**: Navigate to Azure AD, select **App registrations**, and register a new application.
- **Configuration**: Set redirect URIs, configure API permissions, and generate client secrets.

#### 6.2.4 **Create an app that retrieves a token by using the MSAL.NET library**

- **Acquire Token**:
  ```csharp
  var result = await publicClientApp.AcquireTokenInteractive(scopes)
      .ExecuteAsync();
  ```

### 6.3 Implement shared access signatures

#### 6.3.1 **Identify the three types of shared access signatures**

- **User Delegation SAS**: Uses Azure AD credentials to delegate access.
- **Service SAS**: Grants limited access to resources in a storage account.
- **Account SAS**: Grants access to resources at the account level.

#### 6.3.2 **Explain when to implement shared access signatures**

- **Use Cases**: Grant temporary access to storage resources, delegate access without sharing keys, and control access at a granular level.

#### 6.3.3 **Create a stored access policy**

- **Stored Access Policy**: Defines the start time, expiry time, and permissions for a SAS.
  ```csharp
  BlobContainerClient containerClient = new BlobContainerClient(connectionString, containerName);
  containerClient.SetAccessPolicy(PublicAccessType.Blob, new[]
  {
      new BlobSignedIdentifier
      {
          Id = "policyId",
          AccessPolicy = new BlobAccessPolicy
          {
              StartsOn = DateTimeOffset.UtcNow,
              ExpiresOn = DateTimeOffset.UtcNow.AddHours(1),
              Permissions = "r"
          }
      }
  });
  ```

### 6.4 Explore Microsoft Graph

#### 6.4.1 **Explain the benefits of using Microsoft Graph**

- **Unified API**: Access data from Microsoft 365 services.
- **Rich Data**: Retrieve insights and data from various Microsoft services.
- **Integration**: Seamlessly integrate with Azure AD, Outlook, OneDrive, and more.

#### 6.4.2 **Perform operations on Microsoft Graph by using REST and SDKs**

- **REST API**:
  ```http
  GET https://graph.microsoft.com/v1.0/me
  ```
- **SDK**:
  ```csharp
  GraphServiceClient graphClient = new GraphServiceClient(authProvider);
  var user = await graphClient.Me.Request().GetAsync();
  ```

#### 6.4.3 **Apply best practices to help your applications get the most out of Microsoft Graph**

- **Throttling**: Handle rate limits and retry logic.
- **Batching**: Combine multiple requests into a single call.
- **Delta Queries**: Track changes efficiently using delta queries.
- **Security**: Implement proper authentication and authorization mechanisms.

## 7 Implement secure Azure solutions [Link](https://learn.microsoft.com/en-au/training/paths/az-204-implement-secure-cloud-solutions/)

Learn how to more securely deploy apps in Azure by using Azure Key Vault, managed identities, and Azure App Configuration.

### 7.1 Implement Azure Key Vault

Azure Key Vault is a cloud service for securely storing and accessing secrets. A secret is anything that you want to tightly control access to, such as API keys, passwords, certificates, or cryptographic keys.

#### 7.1.1 **Describe the benefits of using Azure Key Vault**

- **Centralized Secret Management**: Securely store and manage access to secrets in a central location.
- **Enhanced Security**: Secrets are protected by hardware security modules (HSMs) and access policies.
- **Simplified Access Control**: Integrate with Azure Active Directory (Azure AD) for fine-grained access control.
- **Audit and Compliance**: Track secret usage and access with detailed logging and monitoring.

#### 7.1.2 **Explain how to authenticate to Azure Key Vault**

- **Azure AD Integration**: Use Azure AD to authenticate and authorize access to Key Vault.
- **Managed Identities**: Simplify authentication by using managed identities for Azure resources.
- **Service Principals**: Use service principals to grant applications access to Key Vault.

#### 7.1.3 **Set and retrieve a secret from Azure Key Vault by using the Azure CLI**

- **Set a Secret**:
  ```bash
  az keyvault secret set --vault-name <VaultName> --name <SecretName> --value <SecretValue>
  ```
- **Retrieve a Secret**:
  ```bash
  az keyvault secret show --vault-name <VaultName> --name <SecretName>
  ```

### 7.2 Implement managed identities

A common challenge for developers is the management of secrets and credentials used to secure communication between different components making up a solution. Managed identities eliminate the need for developers to manage credentials.

#### 7.2.1 **Explain the differences between the two types of managed identities**

- **System-Assigned Managed Identity**: Automatically created and managed by Azure for a specific resource.
- **User-Assigned Managed Identity**: Created as a standalone Azure resource and can be assigned to multiple resources.

#### 7.2.2 **Describe the flows for user- and system-assigned managed identities**

- **System-Assigned Flow**: The identity is tied to the lifecycle of the resource and is automatically deleted when the resource is deleted.
- **User-Assigned Flow**: The identity is managed independently and can be assigned to multiple resources, providing more flexibility.

#### 7.2.3 **Configure managed identities**

- **Enable System-Assigned Managed Identity**:
  ```bash
  az vm identity assign --name <VMName> --resource-group <ResourceGroupName>
  ```
- **Create and Assign User-Assigned Managed Identity**:
  ```bash
  az identity create --name <IdentityName> --resource-group <ResourceGroupName>
  az vm identity assign --name <VMName> --resource-group <ResourceGroupName> --identities <IdentityId>
  ```

#### 7.2.4 **Acquire access tokens by using REST and code**

- **Acquire Token Using REST**:
  ```http
  GET http://169.254.169.254/metadata/identity/oauth2/token?api-version=2019-08-01&resource=<Resource>
  ```
- **Acquire Token Using Code**:
  ```csharp
  var azureServiceTokenProvider = new AzureServiceTokenProvider();
  string accessToken = await azureServiceTokenProvider.GetAccessTokenAsync("<Resource>");
  ```

### 7.3 Implement Azure App Configuration

Azure App Configuration provides a service to centrally manage application settings and feature flags.

#### 7.3.1 **Explain the benefits of using Azure App Configuration**

- **Centralized Management**: Manage all application settings and feature flags in one place.
- **Dynamic Configuration**: Update configuration settings without redeploying applications.
- **Feature Management**: Enable or disable features dynamically using feature flags.
- **Integration**: Seamlessly integrate with Azure services and development frameworks.

#### 7.3.2 **Describe how Azure App Configuration stores information**

- **Key-Value Pairs**: Store configuration settings as key-value pairs.
- **Labels**: Use labels to organize and version configuration settings.
- **Feature Flags**: Define and manage feature flags to control application behavior.

#### 7.3.3 **Implement feature management**

- **Create Feature Flag**:
  ```bash
  az appconfig feature set --name <AppConfigName> --feature <FeatureName> --label <Label>
  ```
- **Check Feature Status**:
  ```bash
  az appconfig feature show --name <AppConfigName> --feature <FeatureName> --label <Label>
  ```

#### 7.3.4 **Securely access your app configuration information**

- **Access Configuration**:
  ```csharp
  var client = new ConfigurationClient(new Uri("<AppConfigEndpoint>"), new DefaultAzureCredential());
  ConfigurationSetting setting = client.GetConfigurationSetting("<Key>", "<Label>");
  ```
- **Use Managed Identity**: Securely access App Configuration using managed identities for Azure resources.

## 8 Implement API Management [Link](https://learn.microsoft.com/en-us/training/modules/explore-api-management/1-introduction)

Learn how the API Management service functions, how to transform and secure APIs, and how to create a backend API.

### 8.1 Explore API Management

API Management helps organizations publish APIs to external, partner, and internal developers to unlock the potential of their data and services.

#### 8.1.1 **Describe the benefits of using Azure API Management**

- **Centralized Management**: Manage all your APIs in one place.
- **Security**: Protect APIs with built-in security features like OAuth, JWT validation, and IP filtering.
- **Transformation**: Modify requests and responses without changing backend services.
- **Monitoring**: Gain insights into API usage and performance with built-in analytics.

#### 8.1.2 **Describe the components, and their function, of the API Management service**

- **API Gateway**: Acts as a facade to backend services, handling requests and responses.
- **Developer Portal**: Provides a customizable interface for developers to discover and consume APIs.
- **Publisher Portal**: Allows API publishers to manage APIs, policies, and analytics.
- **Backend Services**: The actual services that process API requests.

#### 8.1.3 **Explain how API gateways can help manage calls to your APIs**

- **Rate Limiting**: Control the number of API calls to prevent overuse.
- **Caching**: Improve performance by caching responses.
- **Routing**: Direct requests to different backend services based on rules.
- **Transformation**: Modify request and response formats as needed.

#### 8.1.4 **Secure access to APIs by using subscriptions and certificates**

- **Subscriptions**: Require developers to subscribe to APIs, providing control over who can access them.
- **Certificates**: Use SSL/TLS certificates to secure communication between clients and the API gateway.
- **OAuth2**: Implement OAuth2 for secure and scalable access control.
- **IP Whitelisting**: Restrict access to APIs based on IP addresses.

#### 8.1.5 **Create a backend API**

- **Setup**:
  - Navigate to the Azure portal and create a new API Management instance.
  - Define a new API and configure its settings.
  - Connect the API to a backend service.
  - Apply policies to secure and transform the API as needed.


## 9 Develop message-based solutions [Link](https://learn.microsoft.com/en-au/training/paths/az-204-develop-message-based-solutions/)

Learn how to build applications with message-based architectures by integrating Azure Service Bus and Azure Queue Storage into your solution.

### 9.1 Discover Azure message queues

Azure supports two types of queue mechanisms: Service Bus queues and Storage queues.

#### 9.1.1 **Explain the features and use cases of Service Bus queues**

- **Features**:
  - **Advanced Messaging**: Supports queuing, publish/subscribe, and more advanced integration patterns.
  - **Reliability**: Ensures message delivery with features like dead-lettering and duplicate detection.
  - **Security**: Provides robust security with role-based access control (RBAC) and encryption.
  - **Integration**: Designed to integrate applications or components across different protocols, data contracts, and network environments.

- **Use Cases**:
  - **Decoupling Applications**: Helps in decoupling application components to improve scalability and reliability.
  - **Load Leveling**: Smooths out spikes in workload by queuing messages for later processing.
  - **Order Processing**: Ensures messages are processed in the order they were sent.

#### 9.1.2 **Describe the features and use cases of Storage queues**

- **Features**:
  - **Scalability**: Can store millions of messages, up to the total capacity limit of a storage account.
  - **Global Access**: Access messages from anywhere in the world via authenticated HTTP or HTTPS calls.
  - **Simple Interface**: Provides a straightforward API for managing messages.

- **Use Cases**:
  - **Backlog Processing**: Create a backlog of work to process asynchronously.
  - **Task Scheduling**: Schedule tasks to be processed at a later time.
  - **Event Notification**: Notify components of events that need to be processed.

### 9.2 Implement message-based solutions with Service Bus

#### 9.2.1 **Explain how the messaging entities that form the core capabilities of Service Bus operate**

- **Queues**: Store messages until they are retrieved and processed.
- **Topics and Subscriptions**: Enable publish/subscribe messaging patterns.
- **Relays**: Facilitate direct communication between applications.

#### 9.2.2 **Send and receive messages from a Service Bus queue by using .NET**

- **Setup**:
  - Install the **Azure.Messaging.ServiceBus** NuGet package in your .NET project.
  - Configure your **Service Bus connection string** in your application settings.

- **Send Message**:
  ```csharp
  var client = new ServiceBusClient(connectionString);
  var sender = client.CreateSender(queueName);
  var message = new ServiceBusMessage("Hello, Service Bus!");
  await sender.SendMessageAsync(message);
  ```

- **Receive Message**:
  ```csharp
  var client = new ServiceBusClient(connectionString);
  var receiver = client.CreateReceiver(queueName);
  var message = await receiver.ReceiveMessageAsync();
  Console.WriteLine(message.Body.ToString());
  ```

### 9.3 Implement message-based solutions with Azure Queue Storage

#### 9.3.1 **Identify the key components of Azure Queue Storage**

- **Queue**: A container for storing messages.
- **Message**: The actual data stored in the queue, which can be up to 64 KB in size.
- **Storage Account**: Provides a unique namespace for your Azure Storage data.

#### 9.3.2 **Create queues and manage messages in Azure Queue Storage by using .NET**

- **Setup**:
  - Install the **Azure.Storage.Queues** NuGet package in your .NET project.
  - Configure your **Azure Storage account connection string** in your application settings.

- **Create Queue**:
  ```csharp
  var queueClient = new QueueClient(connectionString, queueName);
  await queueClient.CreateIfNotExistsAsync();
  ```

- **Send Message**:
  ```csharp
  var queueClient = new QueueClient(connectionString, queueName);
  await queueClient.SendMessageAsync("Hello, Queue Storage!");
  ```

- **Receive Message**:
  ```csharp
  var queueClient = new QueueClient(connectionString, queueName);
  var message = await queueClient.ReceiveMessageAsync();
  Console.WriteLine(message.Value.MessageText);
  ```

### 9.4 Choose the appropriate queue mechanism for your solution

- **Service Bus Queues**: Best for complex messaging scenarios requiring advanced features like transactions, dead-lettering, and publish/subscribe patterns.
- **Storage Queues**: Ideal for simple, scalable, and cost-effective message queuing needs.