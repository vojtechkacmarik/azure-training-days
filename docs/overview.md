# Azure Training Days - Overview

##  Migrating web aplications to Azure

Web Applications options in Azure:
- Azure App Service
  - similar to web hosting, classic web sites
- Azure Container Instance, Azure Kubernetes Service
  - containerized applications, special environment
- Azure Virtual Machines
  - classic infrastructure as a service
  - when it is necessary to install some non-standard dependency (env.)

Azure App Service
- **App Service Plan**
  - environment for hosting Web app (like IIS hosted)
  - Shared (F1, D1) vs. Own (paid) e.g. per-customer (like on-premise) => decision which Plan to use
  - can host multiple apps
  - Windows vs Linux
  - different configurations per Plan
  - paid Plans (B1, B2, B3) provides own SSL certificates and custom domain names etc.
  - ACU - Azure Compute Units (metrics to monitor web app life)
  - cannot remote desktop access, install something on this 'machine'
  - Scalable => Scale out options, custom rules to add instance

- **Background jobs in Azure App Service**
  - Azure Web Jobs, for free
  - Microsoft.Azure.WebJobs.Extensions
  - deployed within App directory app_data

- **Filesystem in App Service**
  - persistent
  - backed in Azure Storage (like network disk)   
  - limited capacity

- **How to deploy App into App Service Plan**
  - first publish using Visual Studio, due some problems with initial settup and App preparation do cloud-hosted env.
  - configure DevOps pipeline to Publish automatically when App is normallu running in Azure
  - self-contained (included netcore) vs framework-dependent (netcore is installed on target environment)
  - **HINT**: **Kudu** - tool to analyze App Service, app-name.scm.azurewebsites.net
 
- **Azure Storage**
   - Blob Storage
     - Simple storage for binary data
     - not real filesystem, no folders, limited filtering capacities
     - [key, value] pair
     - cheapest way to store blobs, binary data
   - Table Storage
     - very simple document database 
     - Slow filtering and searching, no foreign-keys
     - Quick key-lookup
   - Storage Queues
     - string messages into Queue (max 64kB)
     - multiple Subscribers, message is delivered to only one of them
     - if message is not processed (timeout, error), it will apear in Queue again
     - WebJobs can be triggered by Message from Queue
     - **HINT**: not for big amount of Messages or frequently messages, instead use **Azure Service Bus**
 
HINT: Cloud Explorer in Visual Studio

## Moving your database to Azure