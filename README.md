# Full-Stack MEAN Application with Docker, AWS & CI/CD

This project demonstrates a complete production-style deployment of a Full-Stack **MEAN (MongoDB, Express, Angular, Node.js)** application using:

- 🐳 Docker (Multi-stage builds)
- 📦 Docker Compose
- ☁️ AWS EC2 (Ubuntu)
- 🔄 GitHub Actions CI/CD
- 📤 Docker Hub (Image Registry)
- 🌐 Nginx Reverse Proxy

---

## 🏗️ Architecture Overview

GitHub (Source Code)  
⬇  
GitHub Actions (CI/CD Pipeline)  
⬇  
Docker Hub (Image Registry)  
⬇  
AWS EC2 (Docker Compose Deployment)  
⬇  
Live Application (Port 80)

---

## 📦 Tech Stack

| Layer      | Technology |
|------------|------------|
| Frontend   | Angular 15 |
| Backend    | Node.js + Express |
| Database   | MongoDB |
| Container  | Docker (Multi-stage builds) |
| Orchestration | Docker Compose |
| Cloud      | AWS EC2 (Ubuntu) |
| CI/CD      | GitHub Actions |
| Reverse Proxy | Nginx (Alpine) |

---

## 🐳 Docker Setup

### Backend
- Node 18 Alpine
- Environment variable based MongoDB connection
- Optimized Dockerfile

### Frontend
- Multi-stage build
- Angular production build
- Nginx Alpine runtime image
- Lightweight final image (~62MB)

---

## ☁️ Deployment on AWS EC2

- Ubuntu Server
- Docker installed
- Docker Compose configured
- Security Group allows:
  - Port 22 (SSH)
  - Port 80 (HTTP)

Application accessible via: http://<EC2_PUBLIC_IP>


---

## 🔄 CI/CD Pipeline

GitHub Actions workflow automatically:

1. Builds backend & frontend Docker images
2. Pushes images to Docker Hub
3. SSH into EC2
4. Pulls latest images
5. Restarts containers

Workflow file:.github/workflows/ci-cd.yml


---

## 📁 Project Structure
mean-full-stack/
│
├── backend/
│ ├── Dockerfile
│ ├── .dockerignore
│
├── frontend/
│ ├── Dockerfile
│ ├── .dockerignore
│
├── docker-compose.yml
└── .github/workflows/ci-cd.yml



---

## 🚀 How To Run Locally

```bash
docker-compose up --build
Author - Naveen Parihar
