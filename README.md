Step 1: Start Minikube

    Start Minikube:
    Open your terminal and start Minikube with the following command:

    bash

minikube start

Verify Minikube Status:
Check if Minikube is running correctly:

bash

    minikube status

Step 2: Set Up a Unique Namespace

    Create Your Namespace:
    Each student must create a unique Kubernetes namespace to isolate their resources:

    bash

kubectl create namespace <student-namespace>

Replace <student-namespace> with a unique identifier, such as your name or student ID.

Verify Namespace Creation:
List all namespaces to ensure yours has been created:

bash

    kubectl get namespaces

Step 3: Create a Simple Web Application

    Create a Dockerfile:
    In your project directory, create a Dockerfile for a simple Node.js web application:

    dockerfile

# Dockerfile
FROM node:14

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 8080
CMD ["node", "app.js"]
