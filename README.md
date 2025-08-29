
---

# 🚀 GKE Cloud Build Deployment

This repository contains resources and configuration files for building and deploying applications to **Google Kubernetes Engine (GKE)** using **Cloud Build** and **Docker**.

## 📂 Repository Structure

```
.
├── k8s/                  # Kubernetes manifests (deployment, service, etc.)
├── public/               # Public assets (if any for the app)
├── Dockerfile            # Docker build file for the application
├── cloudbuild.yaml       # Cloud Build pipeline configuration
├── gkecloudbuild.docx    # Documentation guide for setup
└── README.md             # Project documentation
```

## ⚙️ Setup & Deployment

### 1️⃣ Prerequisites

* Google Cloud Project with billing enabled
* GKE Cluster created and running
* Cloud Build API enabled
* Artifact Registry or Container Registry enabled

### 2️⃣ Build & Push Image

Cloud Build automatically builds and pushes the image from `Dockerfile` when triggered.

```bash
gcloud builds submit --config cloudbuild.yaml .
```

### 3️⃣ Deploy to GKE

Apply Kubernetes manifests:

```bash
kubectl apply -f k8s/
```

### 4️⃣ Verify Deployment

```bash
kubectl get pods
kubectl get svc
```

Expose the service and access your app via LoadBalancer/Ingress.

## 📘 Documentation

For a step-by-step lab setup, refer to **gkecloudbuild.docx** in this repo.

---

