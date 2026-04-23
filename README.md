# Docker & Kubernetes Lab – Three-Tier Application  
INET 4031 – Introduction to Systems

This project builds and runs a three-tier web application using Docker (Lab 12) and then deploys it using Kubernetes (Lab 13).

## Project Overview
The application includes:
- Apache (Web) – Handles incoming requests  
- Flask (App) – Backend logic and API  
- MariaDB (Database) – Stores ticket data  

Apache sends requests to Flask, and Flask communicates with the database.

## Lab 12 – Docker Setup
Run the application with Docker:

git clone https://github.com/Shuyus11/inet4031-lab12-docker.git  
cd inet4031-lab12-docker  
sudo docker compose up --build -d  
sudo docker compose ps  

Access:  
http://192.168.56.2  

## Lab 13 – Kubernetes Deployment
Deploy using Kubernetes:

kubectl apply -f k8s/

Check resources:

kubectl get pods -n ticket-app  
kubectl get services -n ticket-app  
kubectl get pvc -n ticket-app  

Watch pods:

kubectl get pods -n ticket-app -w  

## What Changed
- Docker Compose runs containers manually on one machine  
- Kubernetes maintains a desired state automatically  
- Pods are restarted automatically if they fail  
- Services handle internal communication between components  
- Persistent storage is handled using a PVC  

## Access Application
http://192.168.56.2:30080  

## Verification
curl http://localhost:30080/health  
Expected: {"database": "connected", "status": "healthy"}  

curl http://localhost:30080/api/tickets  

## Self-Healing
kubectl delete pod <app-pod-name> -n ticket-app  

Kubernetes automatically recreates the pod to maintain the desired state.

## Repositories
Lab 12: https://github.com/Shuyus11/inet4031-lab12-docker  
Reference: https://github.com/Programming-Mellow/inet4031-testlab12  

## Author
Shu’ayb Yusuf  
INET 4031
