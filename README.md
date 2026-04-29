# 🚀 MeshGate – Production-Ready Dockerized Web Application

A full-stack application demonstrating a **production-style DevOps setup** using Docker, Nginx reverse proxy, and Docker Compose.

---

## 📌 Overview

This project consists of:

- **Frontend**: Static HTML/CSS served via Nginx
- **Backend**: Python API returning JSON responses
- **Reverse Proxy**: Nginx routing `/api/` requests to backend
- **Containerization**: Docker
- **Orchestration**: Docker Compose

---

## 🏗️ Architecture

```text
Browser (localhost:3000)
        ↓
   Nginx (Frontend Container)
        ↓
   Backend Container (API)