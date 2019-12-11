#  Deploy web aplications to Azure

## DevOps

- People
- Processes
- Tools
- **Shared goal of continuous delivery (CD)**

Why DevOps?
- Better and faster feedback from the users
- Breaking the gap between devs and IT admins
- Higher quality of releases
  - Release smaller changes often
- The build and release process is (well)documented, via script (powershell etc)
  - working scripts is better documentation 

**Azure DevOps**
- Azure Boards
- Azure Pipelines
- Azure Repos
- Azure Test Plans
- Azure Artifacts

Azure Boards
- Agile tools
- Boards
- Planning
- Sprints
- Stand-ups

Azure Pipelines
- The build and release has to run somewhere
- Build agent
- Release agent
  - can also be installed on target server
- YAML description for pipeline definition
- HINT: **Git is recommended**
- Publish WebJob using Arguments -o /app_data/Jobs/Continuous
- HINT: MacOS build agent is available for use in Azure DevOps
- Pre-deployment conditions
- Service Principal in case that account in Azure Portal and Azure DevOps are different
- HINT: Deploy using Deployment slots, swap slot (enable slot when all tasks finished)
  - use task 'Invoke REST API request' after Deploy to start web app