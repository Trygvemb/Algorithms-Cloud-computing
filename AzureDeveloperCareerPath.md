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

## Implement Azure App Service web apps

[Link](https://learn.microsoft.com/en-au/training/paths/create-azure-app-service-web-apps/)

Learn how Azure App Service functions and how to create and update an app. Explore App Service authentication and authorization, configuring app settings, scale apps, and how to use deployment slots.

1. ### Explore Azure App Service

#### 1.1 **Describe Azure App Service key components and value.**

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

#### 1.2 **Explain how Azure App Service manages authentication and authorization.**

- **Authentication** in Azure App Service can be managed using **Azure Active Directory (Azure AD)** or third-party identity providers like **Google, Facebook, and Microsoft Accounts**.
- **App Service Authentication/Authorization** (also known as Easy Auth) can be configured to authenticate users without writing any custom authentication logic.
- **Azure AD** can be used for single sign-on (SSO), making it easy to integrate corporate logins for enterprise-level security.
- Developers can configure **OAuth 2.0** and **OpenID Connect** for handling authorization and token-based access.

#### 1.3 **Identify methods to control inbound and outbound traffic to your web app.**

- **Inbound Traffic Control**:
  - **IP Restrictions**: Limit incoming traffic to specific IP ranges to improve security.
  - **Virtual Network Integration**: Integrate your app with an Azure Virtual Network (VNet) to securely communicate with your other services.
  - **App Service Environment (ASE)**: Used to run apps in an isolated, highly secure environment.

- **Outbound Traffic Control**:
  - **Service Endpoints**: Securely connect your App Service to Azure services like Azure Storage and Azure SQL through private endpoints.
  - **Private Endpoints**: Use private links to ensure that all outbound traffic flows through a secure and private network, avoiding exposure to the public internet.
  - **Route Tables**: Control the route of outbound traffic to enforce security policies and direct traffic based on destination IP addresses.

#### 1.4 **Deploy an app to Azure App Service using Azure CLI commands.**

Deployed using Sandbox during the course

---

2. ### Configure web app settings

#### 2.1 **Create application settings that are bound to deployment slots.**

- **Deployment Slots**: Azure App Service allows you to create multiple deployment slots (e.g., staging, production) for your web app.
- **Slot-specific Settings**: Application settings can be configured to be slot-specific, meaning they can have different values in different slots.
  - **Example**: You might have a connection string that points to a test database in the staging slot and a production database in the production slot.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Deployment slots** and select the slot you want to configure.
  - Under **Settings**, select **Configuration** and add or modify the application settings.

#### 2.2 **Explain the options for installing SSL/TLS certificates for your app.**

- **SSL/TLS Certificates**: Secure your web app by installing SSL/TLS certificates.
- **Options**:
  - **App Service Managed Certificate**: Free SSL certificates provided by Azure for custom domains.
  - **Bring Your Own Certificate (BYOC)**: Upload your own SSL certificate purchased from a Certificate Authority (CA).
  - **Azure Key Vault**: Store and manage your SSL certificates securely in Azure Key Vault and bind them to your web app.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **TLS/SSL settings** and select **Private Key Certificates (.pfx)** to upload your certificate.
  - Bind the certificate to your custom domain under **Custom domains**.

#### 2.3 **Enable diagnostic logging for your app to aid in monitoring and debugging.**

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

#### 2.4 **Create virtual app to directory mappings.**

- **Virtual Applications**: Allows you to map a URL path to a specific directory in your web app.
- **Use Cases**: Useful for organizing large applications or hosting multiple applications under a single domain.
- **Configuration**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Configuration** and select the **Path mappings** tab.
  - Add a new virtual application by specifying the **Virtual Path** and the **Physical Path**.

---

3. ### Scale apps in Azure App Service

#### 3.1 **Identify scenarios for which autoscaling is an appropriate solution.**

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

#### 3.3 **Monitor the effects of autoscaling.**

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

4. ### Explore Azure App Service deployment slots

#### 4.1 **Describe the benefits of using deployment slots.**

- **Zero-Downtime Deployments**: Deployment slots allow you to deploy your app updates without any downtime by swapping slots.
- **Testing in Production**: You can test your app in a production-like environment before swapping it to the production slot.
- **Rollback Capability**: If an issue is found after swapping, you can quickly roll back to the previous version by swapping the slots again.
- **Configuration Differences**: Each slot can have its own configuration settings, such as connection strings and app settings, allowing for environment-specific configurations.

#### 4.2 **Understand how slot swapping operates in App Service.**

- **Slot Swapping**: The process of exchanging the content and configuration settings of two deployment slots.
- **Warm-Up**: Before swapping, the target slot is warmed up to ensure that the app is ready to handle traffic immediately after the swap.
- **Atomic Operation**: The swap operation is atomic, meaning it either completes fully or not at all, ensuring consistency.
- **Traffic Redirection**: After the swap, the traffic is redirected to the new slot seamlessly.

#### 4.3 **Perform manual swaps and enable auto swap.**

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

#### 4.4 **Route traffic manually and automatically.**

- **Manual Traffic Routing**:
  - Navigate to your App Service in the Azure portal.
  - Go to **Deployment slots** and select **Traffic routing**.
  - Manually adjust the traffic percentage for each slot to control the flow of traffic.

- **Automatic Traffic Routing**:
  - Use **Traffic Manager** to automatically route traffic based on performance, geographic location, or other criteria.
  - Configure **Traffic Manager** profiles and endpoints to manage traffic distribution across slots or different regions.