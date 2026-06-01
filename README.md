# Kubernetes Microservices Deployment Platform

A production-style microservices deployment platform built with Kubernetes, Docker, Helm, GitHub Actions, Prometheus, and Grafana. This project demonstrates modern DevOps practices including containerization, orchestration, CI/CD automation, monitoring, autoscaling, and secure ingress management.

## 🚀 Features

* Multi-container microservices architecture
* Dockerized frontend and backend applications
* Kubernetes Deployments and Services
* ConfigMaps for environment configuration
* Persistent Volumes for database storage
* NGINX Ingress Controller with TLS support
* Horizontal Pod Autoscaler (HPA)
* Helm-based application packaging and deployment
* GitHub Actions CI/CD pipeline
* Prometheus monitoring
* Grafana dashboards and visualization
* Production-style Kubernetes deployment workflow

---

## 🛠️ Tech Stack

### Containerization

* Docker

### Orchestration

* Kubernetes
* Helm

### Frontend

* React.js

### Backend

* Node.js
* Express.js

### Database

* MySQL

### CI/CD

* GitHub Actions

### Monitoring & Observability

* Prometheus
* Grafana

### Networking & Security

* NGINX Ingress Controller
* TLS/SSL Certificates

---

## 📂 Project Structure

```text
k8s-microservices-platform/

├── frontend/
│   ├── Dockerfile
│   └── React Application

├── backend/
│   ├── Dockerfile
│   └── Node.js API

├── database/
│   └── mysql-init.sql

├── k8s/
│   ├── frontend-deployment.yaml
│   ├── backend-deployment.yaml
│   ├── mysql-deployment.yaml
│   ├── services.yaml
│   ├── ingress.yaml
│   ├── configmap.yaml
│   ├── pvc.yaml
│   └── hpa.yaml

├── helm/
│   └── foodhub-chart/

└── .github/
    └── workflows/
        └── deploy.yml
```

---

## 🏗️ Architecture

```text
Internet
    |
NGINX Ingress
    |
----------------------------
|                          |
Frontend Service      Backend Service
(React App)           (Node.js API)
    |                      |
    ------------------------
              |
          MySQL
              |
      Persistent Volume

Monitoring:
Prometheus → Metrics Collection
Grafana → Dashboards

CI/CD:
GitHub Actions
      ↓
Docker Build
      ↓
Docker Registry
      ↓
Kubernetes Deployment
```

---

## ⚙️ Prerequisites

Before getting started, ensure the following tools are installed:

* Docker Desktop
* Kubernetes (Minikube or Kubernetes Cluster)
* kubectl
* Helm
* Git
* Node.js
* GitHub Account
* Docker Hub Account

---

## 🚀 Getting Started

### Clone Repository

```bash
git clone https://github.com/iamkeerthy/k8s-microservices-platform.git
cd k8s-microservices-platform
```

### Start Kubernetes Cluster

```bash
minikube start
```

Verify cluster:

```bash
kubectl get nodes
```

---

## 🐳 Build Docker Images

### Backend

```bash
cd backend
docker build -t backend .
```

### Frontend

```bash
cd frontend
docker build -t frontend .
```

---

## ☸️ Deploy to Kubernetes

Apply resources:

```bash
kubectl apply -f k8s/
```

Check deployments:

```bash
kubectl get deployments
kubectl get pods
kubectl get services
```

---

## 📦 Deploy with Helm

Create release:

```bash
helm install foodhub ./helm/foodhub-chart
```

Upgrade release:

```bash
helm upgrade foodhub ./helm/foodhub-chart
```

View releases:

```bash
helm list
```

---

## 🔐 Configure Ingress & TLS

Enable Ingress Controller:

```bash
minikube addons enable ingress
```

Apply ingress resources:

```bash
kubectl apply -f k8s/ingress.yaml
```

Create TLS secret:

```bash
kubectl create secret tls foodhub-tls \
--cert=tls.crt \
--key=tls.key
```

---

## 📈 Horizontal Pod Autoscaling

Enable metrics server:

```bash
minikube addons enable metrics-server
```

Apply HPA:

```bash
kubectl apply -f k8s/hpa.yaml
```

Verify:

```bash
kubectl get hpa
```

---

## 📊 Monitoring with Prometheus & Grafana

Install monitoring stack:

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm install prometheus \
prometheus-community/kube-prometheus-stack
```

Access Grafana:

```bash
kubectl port-forward svc/prometheus-grafana 3000:80
```

Open:

```text
http://localhost:3000
```

Monitor:

* Cluster Health
* Node Metrics
* CPU Usage
* Memory Usage
* Pod Status
* Network Traffic

---

## 🔄 CI/CD Pipeline

GitHub Actions workflow automatically:

1. Builds Docker Images
2. Pushes Images to Docker Registry
3. Deploys Updated Containers
4. Updates Kubernetes Resources

Workflow location:

```text
.github/workflows/deploy.yml
```

---

## 🎯 Learning Outcomes

This project demonstrates:

* Kubernetes Administration
* Docker Containerization
* Infrastructure as Code
* Helm Package Management
* CI/CD Automation
* Kubernetes Networking
* Ingress and TLS Configuration
* Autoscaling Strategies
* Monitoring and Observability
* Production Deployment Practices

---

## 👨‍💻 Author

Dunsan Keerthikan

Portfolio: https://iamkeerthy.vercel.app

GitHub: https://github.com/iamkeerthy

LinkedIn: https://linkedin.com/in/iamkeerthy
