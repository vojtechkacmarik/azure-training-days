# Consolidating infrastructure with Azure Kubernetes Service

## Azure Container Service

- Fully managed service for container orchestration
- like a 'cluster' of containers
- Supports
  - Kubernetes

Kubernetes in Azure
- first class citizen
- you pay only for worker nodes (not for infrastructure management)
- standard tooling
- Portal integration for diagnostics

**Kubernetes**
- "K8s"
- Automated deployment and scaling of container workloads
- Supported in al cloud platforms
  - Amazon
  - Microsoft
  - Google
- **Pod**
  - standalone independent unit
  - wrapper for single container instance, e.g. web app
  - has its own IP adress
  - 'Ephemeral' 
- Service
  - "Proxy" for a group of pods of the same type
  - Selector - labels which help to match the pods
  - Azure Load Balancer

**Kubernetes Configuration**
- Azure Portal - basic conf
- CLI kubectl 
  - deploy_secrets.yaml for secrets, not in source control 
- Kubernetes Portal

Next chapter: [Summary](summary.md)