````markdown
# MeshGate DevOps Platform

A containerized DevOps project demonstrating a multi-service application using Docker and Docker Compose.

---

## Overview

The MeshGate DevOps Platform is a hands-on project designed to simulate a real-world application environment using modern DevOps practices.

It demonstrates how frontend and backend services are containerized, orchestrated, and communicate within a Docker network.

---

## Tech Stack

- Docker  
- Docker Compose  
- Python (Flask)  
- NGINX (Frontend static server)  
- Linux  

---

## Architecture

Client (Browser)  
        ↓  
Frontend (NGINX container)  
        ↓  
Backend API (Flask container)  

- Frontend serves static content and interacts with backend  
- Backend processes requests and returns responses  
- Services communicate via Docker internal network  

---

## Screenshots

### Application Running
![App](screenshots/frontend/01-frontend-running-local.png)

### Docker Containers
![Docker](screenshots/compose/01-docker-compose-up.png)

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/daviddigheji/meshgate-devops-platform.git
cd meshgate-devops-platform
````

---

### 2. Run the Application

```bash
docker compose down
docker compose up --build
```

---

### 3. Access in Browser

```
http://localhost:3000
```

---

## Key Features

* Multi-container application using Docker Compose
* Service communication via Docker network
* Clean and modular project structure
* Practical DevOps workflow (build → run → test)

---

## Documentation

[Technical Manual](docs/devops-platform-manual.md)

---

## Troubleshooting

### Containers not running

```bash
docker ps
```

If no containers are running:

```bash
docker compose up --build
```

---

### Containers exist but are stopped

```bash
docker ps -a
```

If you see "Exited":

```bash
docker rm meshgate-frontend meshgate-backend
docker compose up --build
```

---

### Container name already in use

```bash
docker compose down
docker compose up --build
```

---

### View logs

```bash
docker logs meshgate-frontend
docker logs meshgate-backend
```

---

## Future Improvements

* Add reverse proxy (NGINX)
* Implement CI/CD pipeline (GitHub Actions)
* Deploy to AWS ECS (Fargate)
* Add monitoring and logging

---

## Author

**David Digheji**
Cloud & DevOps Engineer

[david@daviddigheji.com](mailto:david@daviddigheji.com)
[https://daviddigheji.com](https://daviddigheji.com)
[https://github.com/daviddigheji](https://github.com/daviddigheji)

```

---
