# Lab 04 - Implement GitHub Actions for CI/CD

## Overview

This lab demonstrates how to implement a CI/CD workflow using GitHub Actions to build, test, and deploy the eShopOnWeb application to Azure App Service.
## Objectives

- Import eShopOnWeb into GitHub
- Configure GitHub Actions
- Create Azure Service Principal authentication
- Store Azure credentials as GitHub Secrets
- Deploy Azure resources using Bicep
- Deploy a .NET application to Azure App Service

## Workflow

GitHub Repository
        ↓
GitHub Actions
        ↓
Build & Test
        ↓
Deploy Infrastructure (Bicep)
        ↓
Deploy Web Application
        ↓
Azure App Service

## Key Configuration

### Environment Variables

```yaml
RESOURCE-GROUP: rg-eshoponweb-sp
LOCATION: southeastasia
TEMPLATE-FILE: infra/webapp.bicep
WEBAPP-NAME: eshoponweb-webapp-sptest001


### Screenshots



```md
## Screenshots

### Repository Imported

![Repository Imported](screenshots/github-repository-imported.png)

### Azure Credentials Secret

![Azure Secret](screenshots/github-secret-created.png)

### Successful GitHub Actions Workflow

![GitHub Actions Success](screenshots/github-actions-success.png)

### Running Azure Web Application

![Web App Running](screenshots/webapp-running.png)

## Results

- Successfully configured GitHub Actions CI/CD workflow
- Authenticated GitHub to Azure using a Service Principal
- Deployed Azure infrastructure using Bicep
- Published eShopOnWeb application to Azure App Service
- Verified successful application deployment

## Lessons Learned

- GitHub Actions can be used as a complete CI/CD platform.
- GitHub Secrets provide secure credential management.
- Azure Bicep simplifies infrastructure deployment.
- GitHub Actions integrates directly with Azure services for automated deployments.