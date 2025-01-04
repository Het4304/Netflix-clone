# DevSecOps Netflix Clone Application

This project demonstrates the deployment of a Netflix Clone application as a Docker container on a Kubernetes cluster (EKS) through a secure CI/CD pipeline using Jenkins. It integrates tools like Docker, SonarQube, Trivy, Prometheus, Grafana, ArgoCD, and Helm to ensure secure and efficient deployment processes.

---

## 📖 Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [Tech Stack](#tech-stack)
4. [Prerequisites](#prerequisites)
5. [Setup & Installation](#setup--installation)
6. [Usage](#usage)
7. [Screenshots](#screenshots)
8. [Best Practices](#best-practices)
9. [Future Scope](#future-scope)

---

## 🔍 Overview
The **DevSecOps Netflix Clone Application** combines secure development, containerization, orchestration, and monitoring to demonstrate the principles of DevSecOps. The project leverages AWS services, Kubernetes, and CI/CD pipelines to create a scalable and secure streaming platform.

---

## ✨ Features
- **Containerized Deployment**: Use Docker for efficient containerization.
- **CI/CD Pipelines**: Jenkins automates builds, tests, and deployments.
- **Static Code Analysis**: SonarQube ensures code quality and security.
- **Security Scans**: Trivy identifies vulnerabilities in containers.
- **Monitoring and Logging**: Prometheus and Grafana provide real-time metrics and insights.
- **GitOps Integration**: ArgoCD streamlines Kubernetes deployment.
- **Cloud-Native Deployment**: Elastic Load Balancer (ELB) and EKS on AWS for seamless scaling.

---

## 🛠 Tech Stack  
- **Containerization**: Docker  
- **Orchestration**: Kubernetes (AWS EKS)  
- **CI/CD**: Jenkins  
- **Security Tools**: SonarQube, Trivy  
- **Monitoring**: Prometheus, Grafana  
- **GitOps**: ArgoCD  
- **Cloud**: AWS (EKS, ELB)  

---

## 🔑 Prerequisites
1. **TMDB API Key**:
   - Visit [TMDB.org](https://www.themoviedb.org/).
   - Create an account.
   - Generate your API key from the developer section.
   - Use this key while running the Docker container.

2. **Tools Required**:
   - Docker
   - Kubernetes (kubectl, AWS EKS)
   - AWS Cli
   - Helm
   - Jenkins

---

## 🚀 Setup & Installation

## Image of the Netflix clone can be found on the dockerhub 
    - clouddeveloper45/netflix:latest

### Step 1: Clone the Repository For the Kubernetes File 
```bash
git clone https://github.com/your-repo-link
cd your-repo-name
```

### Step 2: Configure the TMDB API Key
Before running the container, set your TMDB API key as an environment variable:
```bash
export TMDB_API_KEY=<your-tmdb-api-key>
```

### Step 3: Build and Run the Docker Container
```bash
docker build -t netflix-clone .
docker run -e TMDB_API_KEY=$TMDB_API_KEY -p 3000:3000 netflix-clone
```

### Step 4: Deploy on Kubernetes
Using Helm charts, deploy the application:
```bash
    helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
    kubectl create namespace prometheus-node-exporter
    helm install prometheus-node-exporter prometheus-community/prometheus-node-exporter --namespace prometheus-node-exporter
```

### Step 5: Set Up Jenkins Pipeline
1. Configure the provided `Jenkinsfile` in Jenkins.
2. Add Trivy and SonarQube steps for static and container security analysis.
3. Trigger the pipeline to deploy the app on EKS.

### Step 6: Monitor with Prometheus and Grafana
- Access Grafana dashboards using the provided endpoint.
- Visualize metrics like CPU usage, memory utilization, and network traffic.

---

## 🎯 Usage
1. Access the application via the Node-IP URL:
   ```
   http://<node-ip>:30007
   ```


2. Features:
   - **Browse Movies**: View a catalog of movies and TV shows.
   - **Search by Genre**: Filter content by genre.
   - **Watch Content**: Stream trailers or movie previews.

---

## 📸 Screenshots

### 1. **Detail Modal**
![Detail Modal](/Images/detail-modal.png)

### 2. **Grid View by Genre**
![Grid View by Genre](/Images/grid-genre.png)

### 3. **Watch Interface**
![Watch Interface](/Images/watch.png)

### 4. **Mini Portal**
![Mini Portal](/Images/mini-portal.png)

### 5. **ArgoCD**
![Argo CD](/Images/ArgoCD.png)

### 6. **Grafana**
![Grafana 1](/Images/Grafana%20Dashboard-1.png)
![Grafana 2](/Images/Grafana%20Dashboard-2.png)

### 7. **Jenkins**
![Jenkins](/Images/Jenkins.png)

### 8. **EKS**
![EKS Node Capacity](/Images/EKS%20Node%20Capacity%20Status.png)
![EKS Node](/Images/EKS.png)
---

## 🛡 Best Practices
1. Use **IAM Roles** to restrict access to AWS services.
2. Implement **Role-Based Access Control (RBAC)** in Kubernetes.
3. Regularly update dependencies to patch vulnerabilities.
4. Run periodic Trivy and SonarQube scans for ongoing security checks.
5. Use **GitOps principles** for easier rollback and version control.

---

## 🚀 Future Scope
- Integrate **OAuth Authentication** for secure user logins.
- Implement **multi-region deployment** for high availability.
- Add **recommendation systems** using machine learning.
- Enhance logging with **ELK Stack (Elasticsearch, Logstash, Kibana)**.

---
