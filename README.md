# Discover Dollar – DevOps Engineer Intern Assignment  
**Submitted by :** Sachin Rao Duriyoyhanan  
**Email :** sachinace033@gmail.com  
**Date :** 28 November 2025 (submitted before 6 PM deadline)  
**Live Application :** http://34.201.144.60  
**GitHub Repository :** https://github.com/SachinRao033/MEAN-app-devops-assignment  
**Docker Hub :** https://hub.docker.com/u/sachinace033  

---

### Assignment Requirements – ALL COMPLETED

| Requirement                                      | Status | Proof / Link |
|--------------------------------------------------|--------|--------------|
| Public GitHub repository with complete code      | Done   | This repo |
| Dockerfiles for frontend & backend               | Done   | `frontend/Dockerfile`, `backend/Dockerfile` |
| Docker images built & pushed                     | Done   | `sachinace033/mean-frontend:latest`<br>`sachinace033/mean-backend:latest` |
| Ubuntu VM on cloud (AWS EC2 Free Tier)           | Done   | t2.micro, Public IP: 34.201.144.60 |
| Docker Compose deployment                        | Done   | `docker-compose.yml` |
| MongoDB using official Docker image              | Done   | `mongo:latest` service |
| Application accessible on **port 80** via Nginx  | Done   | http://34.201.144.60 |
| Full CRUD working (Create → Submit works!)       | Done   | Fixed API URL to `/api/tutorials` |
| CI/CD with GitHub Actions                        | Done   | `.github/workflows/cicd.yml` |
| Detailed README with screenshots                 | Done   | This file + `/screenshots` folder |

---

### Live Application
**URL:** http://34.201.144.60 (Port 80)  
**All CRUD operations fully functional**  
→ List, Create (Submit works), Edit, Delete, Search by title  
→ Data persists in MongoDB container

---

### Architecture Diagram
```bash
Internet → AWS EC2 (34.201.144.60:80)
↓
Nginx Reverse Proxy
├── /        → Angular Frontend Container
└── /api     → Node.js/Express Backend Container
↓
MongoDB Container (bezkoder_db)
```

---

### Project Structure
```bash
MEAN-app-devops-assignment/
├── backend/
│   └── Dockerfile
├── frontend/
│   ├── Dockerfile
│   └── nginx.conf
├── docker-compose.yml
├── nginx-reverse-proxy.conf
├── .github/workflows/cicd.yml
├── screenshots/ (all proof screenshots)
└── README.md (this file)
```
---

### Files Included (as required)
- `backend/Dockerfile`
- `frontend/Dockerfile`
- `frontend/nginx.conf`
- `docker-compose.yml`
- `nginx-reverse-proxy.conf`
- `.github/workflows/cicd.yml`
- `screenshots/` folder with all proofs
---

### 1. Repository Setup
- Go to GitHub > New Repository > Set it to public or private.
- Create a new GitHub repository (name : MEAN-app-devops-assignment)-- As ur wish.
- On your local machine, navigate to the extracted project folder.
  ```bash
  Initialize Git: `git init`
  Add all files: `git add .`
  Commit: `git commit -m "Initial commit of MEAN app code"`
  Add remote: `git remote add origin https://github.com/SachinRao033/MEAN-app-devops-assignment.git`
  Push: `git push -u origin main`
  ```
---

### 2. Containerization & Deployment
a. Create Dockerfiles
- In the backend directory, create `Dockerfile`
- And also frontend dir.,create `Dockerfile` and `nginx.conf`
- Commit and push these files to GitHub: `git add . && git commit -m "Uploaded Dockerfile and nginx.conf files" && git push`
##

b. Build and Push Docker Images
- Log in to Docker Hub: `docker login`
  ```bash
  Build backend: `cd backend && docker build -t sachinace033/mean-backend:latest .`
  Push backend: `docker push sachinace033/mean-backend:latest`
  Build frontend: `cd ../frontend && docker build -t sachinace033/mean-frontend:latest .`
  Push frontend: `docker push sachinace033/mean-frontend:latest`
  Take screenshots of the build/push process that has been uploaded to this file.
  ```
  
---
  
### 3. Launch AWS EC2 Ubuntu VM (Free Tier)
- AMI: Ubuntu Server 22.04 LTS or as per wish
- Instance: t2.micro (free tier)
- Security Group → Allow:
  ```bash
  SSH (22)
  HTTP (80)
  ```
- Custom TCP 8080, 8081 (optional, for debugging)
- Download .pem key
- After access the MobaXterm or Putty tools by a ssh port

##

### Local Setup & Deployment Instructions :
# Install Docker + Compose on VM:
  ```bash
   `sudo apt update -y`
   `sudo apt install docker.io docker-compose -y`
  ```
# Clone your repo on VM and test:
```bash
Commands :
  `git clone https://github.com/SachinRao033/MEAN-app-devops-assignment.git`
  `cd MEAN-app-devops-assignment/crud-dd-task-mean-app/`
```
# Backend - (Local system or VM )
```bash
Commands :
  `cd backend`
  `docker build -t sachinace033/mean-backend:latest .`
  `docker push sachinace033/mean-backend:latest`
```
# Frontend- (Local system or VM )
```bash
Commands :
  `cd ../frontend`
  `docker build -t sachinace033/mean-frontend:latest .`
  `docker push sachinace033/mean-frontend:latest`
```
# VM Test:
```bash
Commands :
  `docker-compose up -d`
  `Open browser → http://34.201.144.60` (Public IP of Ec2 Machine).
```

---

### 4. GitHub Actions CI/CD (Automatic Deploy on Push)
- On every push to `main`,GitHub Actions:
- Builds and pushes both Docker images
- SSH into AWS EC2
- Pulls latest code and redeploys with 
  `docker-compose up -d`
```bash
Create File: `.github/workflows/cicd.yml`
```

---

### 5. Infrastructure Details
- Cloud Provider: AWS EC2 (t2.micro – Free Tier)
- Instance Public IP: 34.201.144.60
- OS: Ubuntu Server 22.04 LTS
- Security Group: HTTP (80), SSH (22) open
- Instance will remain running for verification

---

### Screenshots (All Included in /screenshots folder)

|                   Description                      |   File / Link |
|----------------------------------------------------|---------------|
|  Application running (list view)                   |  screenshots/ |
|  Docker Compose up success                         |  screenshots/docker-compose.png |
|  Docker ps (all containers running)                |  screenshots/docker-ps.png |
|  Docker Hub images                                 |  screenshots/dockerhub.png |
|  GitHub Actions CI/CD success                      |  screenshots/github-actions.png |
|  AWS EC2 instance details                          |  screenshots/aws-ec2.png |
|  Security group (port 80 open)                     |  screenshots/security-group.png |
|  Nginx reverse proxy config                        |  screenshots/nginx-config.png |

---

Thank you for the opportunity!.

I enjoyed solving this real-world DevOps challenge and learned a lot in the process.

Submitted on: 28th November 2025 (before 6 PM deadline)

Live URL (please verify): [http://34.201.144.60](http://34.201.144.60)

Ready for the next round!

— Sachin Rao.D






