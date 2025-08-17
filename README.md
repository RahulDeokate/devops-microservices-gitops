# DevOps Microservices GitOps 📦
 
This repository contains the **Kubernetes manifests and Helm charts** for deploying the microservices application.  
It is managed with **GitOps principles using ArgoCD**, ensuring that the cluster state always matches the repository.
 
---
 
## 📂 Project Structure
 
devops-microservices-manifests/
│
│── helm-charts/                             
│   ├── auth-service/                        
│   │   ├── Chart.yaml
│   │   ├── values.yaml
│   │   ├── templates/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   └── ingress.yaml
│   │
│   └── profile-service/                     
│       ├── Chart.yaml
│       ├── values.yaml
│       ├── templates/
│           ├── deployment.yaml
│           ├── service.yaml
│           └── ingress.yaml
│
│── environments/                            
│   ├── dev/
│   │   ├── auth-service-values.yaml
│   │   ├── profile-service-values.yaml
│   │   └── kustomization.yaml               
│   │
│   ├── staging/
│   │   ├── auth-service-values.yaml
│   │   ├── profile-service-values.yaml
│   │   └── kustomization.yaml
│   │
│   └── prod/
│       ├── auth-service-values.yaml
│       ├── profile-service-values.yaml
│       └── kustomization.yaml
│
│── argocd/                                  
│   ├── auth-service-app.yaml
│   ├── profile-service-app.yaml
│   └── project.yaml                         
│
│── .gitignore
│── README.md
 
---
 
## ⚙️ Technologies Used
- **Kubernetes** for orchestration  
- **Helm Charts** for packaging applications  
- **ArgoCD** for GitOps-based continuous delivery  
- **DockerHub** as container registry  
 
---
 
## 🚀 Workflow
1. Docker images are built & pushed via Jenkins (in app repo).  
2. This repo contains **manifests & Helm values** for different environments (`dev`, `prod`).  
3. ArgoCD continuously monitors this repo:  
   - If a manifest changes (e.g., updated image tag)  
   - It syncs and applies the changes to the Kubernetes cluster automatically.  
 
---
 
## 📌 Learning Outcomes
- Understand **GitOps methodology**  
- Learn how to structure repos for **multi-environment deployments**  
- Gain experience with **Helm charts & values overrides**  
- Automate Kubernetes deployments using **ArgoCD**
 
 
---
 
App Repo = code, CI, and Docker builds.
 
GitOps Repo = manifests, Helm, and ArgoCD sync.
