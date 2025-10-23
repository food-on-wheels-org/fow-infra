# Infrastructure (fow-infra)

Contains Kubernetes manifests, ArgoCD configurations, and AWS deployment scripts for the Food-on-Wheels ecosystem.

---

## Overview
- Stores all YAML manifests for EKS deployment.  
- Uses ArgoCD for GitOps-driven synchronization.  
- Includes ingress configuration for AWS ALB.  
- Manages secrets and ConfigMaps for environment variables and credentials.

---

## Components
- Deployment, Service, and Ingress YAML files for each microservice.  
- ArgoCD Application CRDs under `argocd-apps/`.  
- RDS credentials defined as Kubernetes Secrets.  
- Jenkins and SonarQube integration documented.

---

## AWS Resources
| Resource | Purpose |
|-----------|----------|
| EKS Cluster | Hosts all containers |
| RDS (MySQL) | Persistent SQL data storage |
| MongoDB Atlas | NoSQL storage |
| EC2 | Jenkins and SonarQube host |
| ALB | External Ingress routing |

---

## GitOps Flow
1. Push manifests to GitHub.  
2. ArgoCD detects updates and syncs workloads to the EKS cluster.  
3. Cluster state managed declaratively through version control.

---

## CI/CD Pipeline
- Jenkins on EC2 builds, tests, and scans services using SonarQube.  
- Docker images published to DockerHub (`tejassrivathsa/*`).  
- ArgoCD deploys changes automatically to EKS.

---

