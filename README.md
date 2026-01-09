# 🚀 ArgoCD GitOps Demo  
Kubernetes Application Deployment using ArgoCD (GitOps)

---

## 📌 Overview
This repository contains a **GitOps-style deployment configuration** using ArgoCD to manage Kubernetes applications declaratively.  
ArgoCD syncs Kubernetes manifests from this Git repo and ensures the cluster state matches the desired declared state automatically. :contentReference[oaicite:0]{index=0}

---

## 🛠 Tools & Technologies
✔ **ArgoCD** — Kubernetes GitOps continuous delivery tool  
✔ **Kubernetes** — Container orchestration platform  
✔ **kubectl** — CLI for Kubernetes  
✔ **GitHub** — Source of truth for manifests  
✔ **YAML** — Kubernetes & ArgoCD manifests

---

## 📁 Repository Structure
.
├── apps/ # Kubernetes app manifests
│ ├── deployment.yaml
│ └── service.yaml
├── argocd/ # ArgoCD application configs
│ └── app.yaml
├── README.md


---

## 📌 What This Repo Does
➡️ Provides **Kubernetes manifests** for one or more applications  
➡️ Contains **ArgoCD Application config** to instruct ArgoCD how to deploy those manifests  
➡️ Demonstrates **GitOps workflow**:  
GitHub (this repo) → ArgoCD → Kubernetes Cluster

ArgoCD will watch this repo and automatically sync changes to the cluster. :contentReference[oaicite:1]{index=1}

---

## 🔄 GitOps Flow (High Level)
1. **Push** changes to this GitHub repo  
2. ArgoCD continuously monitors the repo  
3. ArgoCD **syncs** the repository state to the Kubernetes cluster  
4. Cluster resources (Deployments, Services, etc.) are updated automatically

This is the core principle of *GitOps* — using Git as the **single source of truth** for deployment state. :contentReference[oaicite:2]{index=2}

---

## 📌 How to Use
### 1️⃣ Add this repo to ArgoCD
After installing ArgoCD in your Kubernetes cluster:

```sh
argocd repo add https://github.com/abhi2330/argocd1.git
```
2️⃣ Create the ArgoCD Application 
```sh
kubectl apply -f argocd/app.yaml -n argocd
```
3️⃣ Sync Application
From ArgoCD UI or CLI:
```sh
argocd app sync <app-name>

```
🧠 Why This Matters

- ✔ Continuous deployment using GitOps
- ✔ Git is the single source of truth
- ✔ ArgoCD ensures declarative synchronization
- ✔ Team-friendly and automated workflow

## 📌 Contact
- Created by Abhi — DevOps & Cloud Enthusiast
- GitHub: https://github.com/abhi2330
