# Containerizing Microservices and Publishing Images to Registries

## 📌 Project Overview

This project demonstrates how to containerize a multi-service application and publish Docker images to both **Docker Hub** and **Amazon Elastic Container Registry (ECR)**. Each microservice is packaged into its own Docker image, tagged with version identifiers, and uploaded to container registries for reliable storage and deployment. The project showcases best practices for Docker image creation, versioning, registry authentication, and image distribution.

---

## 🎯 Objectives

- Containerize frontend and backend microservices.
- Build Docker images using Dockerfiles.
- Tag images using standard versioning conventions.
- Publish images to Docker Hub.
- Publish images to Amazon Elastic Container Registry (ECR).
- Verify image availability by pulling and running containers.

---

## 🏗️ Architecture

The project consists of the following components:

- **Frontend Service** – User interface containerized with Docker.
- **Backend Service** – API service containerized with Docker.
- **Docker Engine** – Builds and manages container images.
- **Docker Hub** – Public registry for storing Docker images.
- **Amazon ECR** – Private container registry hosted on AWS.
- **AWS CLI** – Authenticates Docker with Amazon ECR.

---

## 🛠️ Technologies Used

- Docker
- Docker CLI
- Docker Hub
- Amazon ECR
- AWS CLI
- Git
- GitHub
- Ubuntu / Linux

---

## 📂 Project Structure

> **Update this section to match your GitHub repository structure.**

```text
containerizing-microservices/
│
├── Screenshots/
│
├── Architecture.png
├── frontend/
│   ├── Dockerfile
│   └── ...
│
├── backend/
│   ├── Dockerfile
│   └── ...
│
├── README.md
└── .gitignore
```

---

## 🚀 Execution Steps

### 1. Build Frontend Image

```bash
docker build -t frontend-service:v1 ./frontend
```

---

### 2. Build Backend Image

```bash
docker build -t backend-service:v1 ./backend
```

---

### 3. Verify Docker Images

```bash
docker images
```

---

### 4. Login to Docker Hub

```bash
docker login
```

---

### 5. Tag Images for Docker Hub

```bash
docker tag frontend-service:v1 <dockerhub-username>/frontend-service:v1
docker tag backend-service:v1 <dockerhub-username>/backend-service:v1
```

---

### 6. Push Images to Docker Hub

```bash
docker push <dockerhub-username>/frontend-service:v1
docker push <dockerhub-username>/backend-service:v1
```

---

### 7. Authenticate with Amazon ECR

```bash
aws ecr get-login-password --region <aws-region> | docker login --username AWS --password-stdin <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com
```

---

### 8. Tag Images for Amazon ECR

```bash
docker tag frontend-service:v1 <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com/frontend-service:v1

docker tag backend-service:v1 <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com/backend-service:v1
```

---

### 9. Push Images to Amazon ECR

```bash
docker push <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com/frontend-service:v1

docker push <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com/backend-service:v1
```

---

### 10. Verify Published Images

Pull the images from the registry:

```bash
docker pull <dockerhub-username>/frontend-service:v1

docker pull <dockerhub-username>/backend-service:v1
```

Run the containers:

```bash
docker run -d -p 8080:80 <dockerhub-username>/frontend-service:v1

docker run -d -p 8081:8081 <dockerhub-username>/backend-service:v1
```

---

## 🔍 Verification Commands

```bash
docker images

docker ps

docker image ls

docker pull <image-name>

docker inspect <image-name>

aws ecr describe-repositories
```

---

## 📊 Key Features

- Docker image creation
- Multi-service containerization
- Docker image versioning
- Docker Hub integration
- Amazon ECR integration
- Registry authentication
- Image verification
- Consistent deployment across environments

---

## 📚 Learning Outcomes

Through this project, I gained hands-on experience with:

- Docker image creation
- Dockerfile optimization
- Docker image tagging
- Docker Hub
- Amazon Elastic Container Registry (ECR)
- AWS CLI
- Docker image distribution
- Container registry management

---

## ✅ Project Outcome

Successfully containerized frontend and backend microservices and published Docker images to both Docker Hub and Amazon Elastic Container Registry (ECR). The project demonstrates industry-standard practices for container image creation, versioning, registry management, and image distribution, ensuring reliable and consistent application deployments across multiple environments.

---

## 👨‍💻 Author

**Manoj Kumar**

- GitHub: https://github.com/ManojKumar8244
