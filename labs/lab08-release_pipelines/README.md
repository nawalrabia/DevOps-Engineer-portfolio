# Control Deployments using Release Gates (Azure DevOps)

## 📌 Overview

This project demonstrates how to implement **controlled CI/CD deployments using Azure DevOps Release Pipelines with Approvals and Release Gates**.

The solution simulates a real-world DevOps workflow where deployments are only promoted to production after meeting defined quality and monitoring conditions.

---

## 🎯 Objectives

- Configure Azure DevOps CI/CD pipelines
- Deploy application to multiple environments (DevTest & Production)
- Implement **pre-deployment approvals**
- Implement **post-deployment release gates using Azure Monitor**
- Block production deployment when application issues are detected

---

## 🏗️ Architecture

- Azure DevOps YAML CI Pipeline (build)
- Classic Release Pipeline (CD)
- Azure App Service (DevTest & Production)
- Application Insights (monitoring)
- Azure Monitor Alerts (quality gate)

---

## 🔧 Tools & Services Used

- Azure DevOps Pipelines
- Azure App Service
- Azure Monitor / Application Insights
- GitHub (repository hosting)
- Azure CLI

---

## 🚀 Pipeline Flow

1. Code committed to repository
2. CI pipeline builds .NET application
3. Artifact published (Web.zip)
4. Release pipeline triggered automatically
5. Deployment to **DevTest environment**
6. Pre-deployment approval required
7. Post-deployment gate checks:
   - Azure Monitor alerts
8. If no active issues → deploy to Production

---

## 🔐 Release Gates Configured

### Pre-Deployment Gate
- Manual approval required before DevTest deployment

### Post-Deployment Gate
- Azure Monitor Alerts query
- Blocks promotion if:
  - Failed requests exist
  - Active alerts detected in Application Insights

---

## 🧪 Test Scenario

- Application deliberately triggered error using `/discount`
- Application Insights captured failed requests
- Alert created (Severity 2)
- Release gate blocked production deployment

---

## 📸 Screenshots

> Add screenshots in a `/screenshots` folder

### 1. Azure DevOps CI Pipeline Run
`screenshots/ci-pipeline-success.png`

### 2. Release Pipeline Stages (DevTest + Production)
`screenshots/pipeline_stages_success.png`

### 3. Pre-Deployment Approval Gate
`screenshots/pre-deployment-approval.png`

### 4. Post-Deployment Gate Configuration
`screenshots/post-deployment-gate.png`

### 5. Application Insights Alert
`screenshots/app-insights-alert.png`

### 6. Failed Request Trigger (/discount page)
`screenshots/webapp-error.png`

### 7. Production Deployment Blocked / Passed Gate
`screenshots/gate-evaluation.png`

---

## 🧠 Key Learnings

- How release gates enforce production safety
- Integration of monitoring into CI/CD pipelines
- Using Azure Monitor as a deployment control mechanism
- Implementing approval-based deployment strategy

---

## 📌 Conclusion

This project demonstrates a production-grade CI/CD pipeline with governance controls, ensuring only validated and healthy deployments reach production.