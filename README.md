# 🚀 Enterprise DevSecOps Pipeline on AWS EKS

![Build Status](https://img.shields.io/badge/Pipeline-Passing-success)
![AWS](https://img.shields.io/badge/AWS-EKS%20%7C%20ECR-orange)

## 📖 Project Overview
This project implements a fully automated **CI/CD Pipeline** with integrated security scanning. It transitions a containerized web application from a local development environment to a production-ready **Amazon EKS** cluster.

### 🌟 Key Features
- **Automated CI/CD:** Powered by GitHub Actions for zero-touch deployment.
- **Security-First (DevSecOps):** Integrated **Trivy** vulnerability scanning.
- **Scalable Hosting:** Deployed on **Amazon EKS** with load-balanced replicas.
- **Identity & Access:** Secured via **AWS IAM** and Kubernetes Access Entries.

---

## 🛠 Tech Stack
- **Cloud:** AWS (EKS, ECR, IAM, VPC)
- **CI/CD:** GitHub Actions
- **Containers:** Docker
- **Security:** Aqua Security Trivy
- **Orchestration:** Kubernetes (kubectl, eksctl)

---

## 📸 Technical Walkthrough

### 1. The Pipeline Logic
The core of the project is the `.github/workflows/deploy.yml` file, which defines the build-scan-deploy logic.
![Pipeline Code](01-pipeline-workflow.png)

### 2. Cloud Infrastructure
The infrastructure was provisioned using `eksctl`, setting up a multi-node cluster in the `eu-west-1` region.
![Infrastructure](02-eks-cluster-ready.png)

### 3. Security & IAM
Following the **Principle of Least Privilege**, a dedicated IAM user was configured with specific permissions for ECR and EKS.
![IAM Setup](03-iam-security-setup.png)
![Permissions](04-iam-permissions-policy.png)

### 4. Kubernetes Authorization
To allow the external GitHub Runner to deploy code, I configured **EKS Access Entries** to map the IAM user to the cluster's administrative role.
![EKS Auth](06-cluster-authorization.png)

### 5. Deployment Success
The final pipeline run shows a successful build, security scan, and push to production.
![Pipeline Success](08-docker-push-verified.png)

### 6. Production Environment
Verification of the live environment showing pods running successfully across the cluster.
![Production](09-kubernetes-pods-running.png)

---

## 👤 Author
**Melvin Okwara**
*DevOps & Cloud Engineer*
