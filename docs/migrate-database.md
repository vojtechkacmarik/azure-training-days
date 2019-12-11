# Moving your database to Azure

Database options in Azure:
- Azure SQL Database
- Microsoft SQL Server in Virtual Machines
- Azure Cosmos DB
- MySQL
- MariaDB
- PostgreSQL
- Redis

**Azure SQL Database**
- Hosted SQL Server
- No cross-database queries
- Managed Instance
  - Pricing based on server configuration - RAM, disk storage etc.  
- Single Database, Elastic Pools
  - Pricing based in DTU (database transaction unit) 
- DTU - "average" database transaction
- 5 DTU = 5 average database transactions per second
- Serverless option
  - pay less when the database is not used for a longer period of time
  - Auto-pause interval - 60 minutes or more
  - great for application which is used in defined time range
- Firewall and virtual network settings

**Azure SQL Database deployment options**
- Export/Import using SQL Management Studio
  - Bacpac format
  - SQL scripts - not good idea, very slow
- Transactional Replication
- Managed Instances: Azure Database Migration Service 
- SQL Management Studio: Deploy Database (directly to Azure)
  - add Firewall settings directly to Azure SQL Database using public API
  - direct access to Azure SQL database from SSMS

**HINT**: Tool **az** for provision powershell scripts, e.g. for simple duplications of existing Azure configuration

Next chapter: [Deploying your application faster and safer](deploy.md)