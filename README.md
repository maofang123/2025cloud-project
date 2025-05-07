# 2025cloud Project

This repository contains two Docker container images for the 2025cloud assignment:

1. **nginx**: A simple Nginx static web server
2. **app**: A minimal Flask web application

> 👉 **Docker Hub Repo**: `your-dockerhub-username/2025cloud` (public)

---

## 📂 Repository Structure

```
2025cloud-project/
│
├── nginx/                  # Nginx container
│   ├── Dockerfile
│   └── index.html
│
├── app/                    # Python Flask application container
│   ├── Dockerfile
│   └── app.py
│
└── README.md               # This file
```

---

## ⚙️ Prerequisites

* Docker installed locally
* (Optional) Docker Hub account with repository `2025cloud` created and public
* Git installed for version control

---

## 🏗️ Build Instructions

### 1. Build Nginx Image

```bash
# from project root
docker build -t your-dockerhub-username/2025cloud-nginx:latest ./nginx
```

### 2. Build Flask App Image

```bash
docker build -t your-dockerhub-username/2025cloud-app:latest ./app
```

---

## ▶️ Run Containers Locally

### Nginx

```bash
docker run -d -p 8080:80 your-dockerhub-username/2025cloud-nginx:latest
```

Open your browser at `http://localhost:8080` to see the Nginx welcome page.

### Flask App

```bash
docker run -d -p 5000:5000 your-dockerhub-username/2025cloud-app:latest
```

Open your browser at `http://localhost:5000` to see the Flask greeting.

---

## 📦 Push to Docker Hub

```bash
docker login

docker push your-dockerhub-username/2025cloud-nginx:latest
docker push your-dockerhub-username/2025cloud-app:latest
```

> Make sure your Docker Hub repo `2025cloud` is public to receive the images.

---

## 🛠️ Next Steps

1. **GitHub Actions**: Automate build & push on each commit.
2. **Tag Strategy**: Use semantic versioning (`v1.0.0`, `v1.1.0`, etc.) or branch-based tags (`dev`, `staging`, `latest`).
3. **Error Simulation**: Create a PR that deliberately breaks the Dockerfile to validate failure detection in CI.

---

## 📊 Workflow Overview

```mermaid
graph TD;
    Code[Push Code to GitHub] -->|Trigger Workflow| Build[Build Docker Images];
    Build --> Push[Push Images to Docker Hub];
    Push --> Deploy[Deploy Containers Locally or Remotely];
