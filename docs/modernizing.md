#  Modernizing your application with containers and serverless

## What is container?

Virtual machines
- massive izolation
- heavy and not too flexible

**Containers**
- more isolation than process
  - file system, network, registry (on Windows) 
- izolation is less than VMs but sufficient
  - shared kernel, drivers 
- quick start
- image is small
- flexible for many use cases (for further use)
- no more "works on my machine" because of missing libraries

**Docker**
- most popular Container
- Docker Engine, runs in Operatins System (OS)
  - from OS point of view it is a standard process 
- https://github.com/dotnet/dotnet-docker 
- **HINT**: use Docker for Linux for netcore app, more flexible and fast
- Visual Studio: Add Docker support for enable docker in project

Container filesystem
- Layered approach (immutable, in case some change is created then new layer introduced)
- Same layers shared
- Container is 'state-less', it can be stopped (killed) or started everytime, everywhere => 'ephemeral'
  - application should be designed for that
- 'volume' - some changes can be writed to filesystem 

**When to use containers?**
- Microservices architecture
  - different pieces of code in different technologies
  - simplification to environment distribution, works with containers is same
- Consistent builds
  - all dependencies are defined via container, not necessary to instal something to target environment

**How to start with containers?**
- Install Docker for Windows
  - https://docs.docker.com/docker-for-windows/ 
- Requires Hyper-V 
- Docker settings
  - Shared drives (app_data, source codes)
  - Subnet settings 
- Dockerfile - contains image settings
  - _FROM_ defines other layer from previous one
  - **HINT**: for testing real environment use Release build version
- Docker-compose.yml for container orchestration
  - for start many containers at once 
  - set as startup project 
- `docker image ls` list all images
- `docker ps` list of running containers
- `docker logs hasId` list of log messages

Azure Container Instance
- "Here is the container - host it for me"
- Simple container applications
- Short-time scenarios
  - docs.microsoft.com - runnable C# code samples
  - per second pricing 

**Azure Container Registry**
- add container to Container Registry
- `docker tag` add alias
- `docker push` add container to registry
- in Azure portal in App Service click to Container settings to set up pubished container for app usage

Next chapter: [Consolidating infrastructure with Azure Kubernetes Service](consolidating.md)