# WHAT
This project is the sample of local deployment of full stack application with Kubernetes. Application is written in React as frontend and go as backend language. The idea is how to get started with Kubernetes deployment and maybe next step is to deploy it to cloud with multi stage envrionment. 

# Backend 
1. Backend - Go
    - Web Framework - Gin Gonic // go.mod file 
    - Gin Gonic server - main.go file
    - Dockerfile - to run the server 

- Steps
    1. create a backend directory in the peoject root
    2. create main.go and fill out the sample go code
        - go mod init backend
        - go mod tidy
    3. create Dockerfile
        - docker build --tag 300974211/go-backend .
        - docker push 300974211/go-backend

# Frontend
2. Frontend - React
- steps 
    1. npx create-react-app client // in the root directory
    2. npm i axios  --save
    3. Update src/app.js code
    4. create a dockerfile
        - docker build -t 300974211/frontend
        - docker push 300974211/frontend

# Kubernetes manifest files
3. Kubernetes file 
- steps 
    1. create Backend deployment file with service
    2. create frontend deployment file with service
    3. create persistance volume // to persist database's data with service
    4. create database deployment file 
    5. create Ingress Service
        - NGINX Ingress Controller
        - kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.4.0/deploy/static/provider/cloud/deploy.yaml
        - minikube addons enable ingress

# Local deployment
4. Local Deploy
      1. on the project root execute: kubectl apply -f k8s
      2. check if everything is working as expected
        - kubectl get all
        - minikube dashboard
      3. Finally, let’s see if our application is indeed running. 
        - minikube ip

# Credit
5. Credit
    - https://betterprogramming.pub/deploy-a-full-stack-go-and-react-app-on-kubernetes-4f31cdd9a48b
