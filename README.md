# Containerizing Microservices and Publishing Images to Registries

## Problem Statement Overview
Modern cloud-native applications are composed of multiple independent microservices (frontend, backend API, database). To ensure consistent deployment across development, testing, and production environments, each microservice must be containerized into its own isolated image and published to centralized container registries for seamless deployment and distribution.

## Solution Approach
I containerized a multi-service web application consisting of a frontend UI and backend API:
1. **Containerization:** Written separate, optimized `Dockerfile`s for both the frontend and backend microservices.
2. **Local Build & Tagging:** Built Docker images locally and tagged them following standard versioning conventions (`latest`, `v1.0`).
3. **Public Registry Publishing:** Logged into Docker Hub, tagged the images with my repository prefix, and pushed them to public Docker Hub repositories.
4. **Private/Cloud Registry Publishing:** Authenticated the Docker CLI with AWS Elastic Container Registry (ECR) using the AWS CLI and pushed the microservice images to AWS ECR repositories.
5. **Verification:** Pulled and ran the microservice containers directly from the registry images to confirm operational readiness.

## Dependencies and Tools
* Ubuntu VM / Local Development Environment
* Docker Engine & Docker CLI
* AWS CLI (configured for ECR access)
* Docker Hub Account & Repositories
* AWS Elastic Container Registry (ECR)

## Execution Steps
1. **Build Microservice Images:**
   ```bash
   docker build -t frontend-service:v1 ./frontend
   docker build -t backend-service:v1 ./backend
