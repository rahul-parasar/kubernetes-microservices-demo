# Kubernetes Microservices Deployment 🚀

This project demonstrates how to deploy a microservices-based application on a Kubernetes cluster using Amazon Linux 2023.

## 🏗 Architecture
- Frontend Microservice (Nginx)
- Backend Microservice (Flask API)
- Kubernetes Deployments & Services

## 📁 Project Structure 
 -> backend/ 
 -> frontend/ 
 -> k8s/

## ⚙️ Prerequisites
- Amazon Linux 2023 EC2 Instance
- Docker
- kubectl
- Minikube
- Git

## 🚀 Setup Steps

1️⃣ Install Tools 
sudo yum install docker git -y 
sudo systemctl start docker 
sudo usermod -aG docker ec2-user 
newgrp docker

2️⃣ Start Kubernetes minikube start --driver=docker

3️⃣ Build and Push Images 
docker build -t backend-app backend/
docker build -t frontend-app frontend/
docker tag backend-app yourdockerhub/backend-app:v1
docker tag frontend-app yourdockerhub/frontend-app:v1
docker push yourdockerhub/backend-app:v1
docker push yourdockerhub/frontend-app:v1

4️⃣ Deploy to Kubernetes
kubectl apply -f k8s/

5️⃣ Access Application
minikube service frontend-service --url

✅ Output
Frontend webpage loads and backend API responds successfully.

