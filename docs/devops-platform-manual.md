
# MeshGate DevOps Platform – User & Technical Manual

## Overview

MeshGate is a containerized DevOps platform that demonstrates a basic multi-service application using Docker and Docker Compose.

It consists of:
- Frontend (NGINX serving static content)
- Backend (Flask API)
- Docker-based orchestration

The platform shows how services communicate within a containerized environment.

---

## Architecture

Client (Browser)  
        ↓  
Frontend (NGINX container)  
        ↓  
Backend API (Flask container)  

All services run in Docker containers and communicate over a shared Docker network.

---

## Prerequisites

Ensure the following are installed:

- Docker
- Docker Compose
- Git

Check versions:

```bash
docker --version
docker compose version
````

---

## Running the Application

### 1. Clone the repository

```bash
git clone https://github.com/daviddigheji/meshgate-devops-platform.git
cd meshgate-devops-platform
```

---

### 2. Start services

```bash
docker compose down
docker compose up --build
```

---

### 3. Access application

Open your browser:

```
http://localhost:3000
```

---

## Service Verification

### Check running containers

```bash
docker ps
```

Expected containers:

- meshgate-frontend
- meshgate-backend

---

### Test backend connectivity from frontend

```bash
docker exec meshgate-frontend wget -qO- http://meshgate-backend:5000/
```

---

## Project Structure

```
meshgate-devops-platform/
│
├── services/
│   ├── frontend/
│   │   └── Dockerfile
│   │
│   └── backend/
│       ├── app.py
│       └── Dockerfile
│
├── docker-compose.yml
├── screenshots/
├── docs/
│   └── devops-platform-manual.md
│
└── README.md
```

---

## Screenshots

### Application Running

![App](../screenshots/frontend/01-frontend-running-local.png)

### Docker Compose Running

![Compose](../screenshots/compose/01-docker-compose-up.png)

---

## Troubleshooting

### Issue: Application not opening on [http://localhost:3000](http://localhost:3000)

#### Cause:

Containers are not running.

#### Solution:

```bash
docker ps
```

If no containers are running:

```bash
docker compose up --build
```

---

### Issue: Containers exist but are stopped (Exited)

Check all containers:

```bash
docker ps -a
```

If you see "Exited":

```bash
docker rm meshgate-frontend meshgate-backend
docker compose up --build
```

---

### Issue: Container name already in use

Error:

```
Conflict. The container name is already in use
```

#### Solution:

```bash
docker compose down
docker compose up --build
```

---

###  Issue: Port already in use

```bash
lsof -i :3000
kill -9 <PID>
```

---

### Issue: Frontend or backend not starting

Check logs:

```bash
docker logs meshgate-frontend
docker logs meshgate-backend
```

---

### Issue: Backend not reachable

Check:

* Backend container is running
* Correct service name (`meshgate-backend`)
* Docker network is active

---

##  Design Considerations

* Services communicate via Docker internal network
* Backend is isolated from direct external access
* Separation of frontend and backend components
* Lightweight architecture suitable for local development and learning

---

##  Future Improvements

* Add reverse proxy (NGINX)
* Implement CI/CD pipeline using GitHub Actions
* Deploy to AWS ECS (Fargate)
* Add monitoring and logging

---

## Author

**David Digheji**
Cloud & DevOps Engineer

[david@daviddigheji.com](mailto:david@daviddigheji.com)
[https://daviddigheji.com](https://daviddigheji.com)
[https://github.com/daviddigheji](https://github.com/daviddigheji)

````

---