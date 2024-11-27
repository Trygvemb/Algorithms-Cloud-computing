---
title : "Projects"
---

### [Team Project - WePack.PMS](https://github.com/DMOoF23-S4-Team2/PMS-WePack)

### [Shopify GraphQL API Testing](ShopifyGraphQL.md)

### Hosting

#### Setup

- All resources are hosted on Azure under my student account. I made a single resource group for all the resources. This way I can easily manage all the resources in one place.

- Azure SQL Server database is used to store the data. I have created a database, implemented it in the code with Dotnet User Secrets.

- I tried to set up Azure App Service for hosting the site but ran into problems since there is both a front-end and a back-end. and we have to host them separately. I will try to host the front-end on Azure App Service and the back-end on Azure Functions.

- Started containerizing the application with docker to make sure both API, Web project and all dependencies is running properly.

- Made a small sample project to test hosting static web app and api. Build it with the help of Azure tutorial and set up Azure resources through CLI. Removed all the resources after testing. This worked well, but I don't think it will work for our project since we have a front-end and a back-end with multiple projects and dependencies.

- Had problems with setting up database in Key vault since it couldn't retrieve it locally. tried to solve this by setting up Azure Active Directory, but i don't have access to to this through y student account.

- Trying to Containerize the application with Docker. I have created a Dockerfile for the API and the Web project. I have also created a docker-compose file to run both projects together, but im having trouble getting it to run properly and want to learn more about how I can use Docker to host the application. I will be doing the following Microsoft Learn module to learn more about Docker: [Deploy and run a containerized web app with Azure App Service](https://learn.microsoft.com/en-us/training/modules/deploy-run-container-app-service/)

- I have now successfully containerized the application with Docker. I have created a Dockerfile.api and Dockerfile.web. I have also created a docker-compose file to run both projects together. I had a lot of trouble with the default routing in web layer. but after setting up multiple different fallback options it is now working. Also had to change the CORS policy to include the port 80 from the container to retrieve data from api.

- Created a Azure Container Registry and pushed the pms-wepack-api and pms-wepack-web image up, but I'm having some issues and think I'll try to push the whole container image up instead of the individual projects.

- Tried to get the sql database and key vault to work while running locally, but I came back to the same conclusion that i need to set up a Azure Service Principle to grant the app access, but i don't have permission from the school to set up Service Principles, so I'll have to try to just set it all up with hosting and hope that it works, maybe if I set up a CI/CD to begin with, then making changes won't be too difficult.

- I'm currently trying to change the containers over to use the Azure SQL database instead of the local database. I have set the key vault url in the docker-compose file and in the appsettings.jason file. 

- Found out that many of the issues I had was with port and routing from App to Docker Container to Azure Container app. I have now changed it so the ports in docker container is correctly mapped to the application.

- Another issue was with the frontend and the api endpoint calls. I had to create a javascript config file with a function that overrides ApiUrl in appsettings.json if it gets set in Azure. I have run the container environment successfully on my local machine and it is now ready to be pushed to Azure.

- Managed to get both container apps up and running and set the environment variables in azure, but the issues now is that I have been using HTTP and not HTTPS, so I have to set up a SSL certificate to get it to work. I will try to set up a self signed certificate and see if that works.

- Configured a self signed certificate for both front and backend and set development environment to use HTTP and production to use HTTPS. I can successfully retrieve data from the database both while running it in the container environment and while running locally in development mode. I have had to set database connection string in the backend appsettings, but this will be overridden in the Azure Container App.

- I had mapped the ports to use 443 HTTPS with the self signed certificate and that worked when i was running the container locally, but when i pushed it to Azure, it didn't work. Since it is not a verified certificate. Instead I went back to using 8080 HTTP and the container and then letting Azure handle the HTTPS. This worked and I can now access the application through the Azure Container App.

- Link to frontend container app
    - https://ca-wepack-web.bluestone-4e633029.swedencentral.azurecontainerapps.io/

- Link to backend container app
    - https://ca-wepack-api.bluestone-4e633029.swedencentral.azurecontainerapps.io/
