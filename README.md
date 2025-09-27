# 🚀 Docker Demo App

This is a simple demo application designed to demonstrate how to use **Docker** and **Docker Compose** to containerize and run Node.js applications.



### 🛠️ Installation
Before running this demo, make sure you have Docker installed on your system.
### 📥 Install Docker
- [Docker Desktop for Mac & Windows](https://www.docker.com/products/docker-desktop)
- [Docker Engine for Linux](https://docs.docker.com/engine/install/)
After installation, verify it's working:
```bash
docker --version
docker compose version
```

### 🐳 Check Existing Docker Images and Containers

🔍 View local Docker images:
```bash
docker images
```

🔍 View all containers (running + stopped):
```bash
docker ps -a
```

### 📦 Build and Run the App
🛠️ 1. Build a Docker image
```bash
docker build -t goals-node .
```

🚀 2. Run a container from the image
```bash
docker run -d -p 3000:80 --name goals-app goals-node
```

This maps port 80 inside the container to port 3000 on your machine
Now open your browser and visit

```bash
http://localhost:3000
```

### 🧰 Container Management
🛑 Stop the container:
```bash
docker stop goals-app
```
🔁 Start it again:
```bash
docker start goals-app
```
🗑️ Remove the container (optional):
```bash
docker rm goals-app
```

### ☁️ Push to Docker Hub
🔐 1. Log in to Docker Hub:
```bash
docker login
```

🌐 2. Create a repository at:
https://hub.docker.com
Name the repo the same as your image (e.g., goals-node)

🏷️ 3. Tag your image:
```bash
docker tag goals-node jrojascr/goals-node:latest
docker tag goals-node jrojascr/goals-node:v1
```
Replace jrojascr with your Docker Hub username if different.

📤 4. Push the image:
```bash
docker push jrojascr/goals-node:latest
docker push jrojascr/goals-node:v1
```

### ✅ Steps for Another User to Pull & Run Your the Image
1. Make sure the image is public
Go to: https://hub.docker.com/repositories
Find your repo (goals-node) → make sure it's marked as Public (under repo settings).
2. Share this command with them:
```bash
docker pull jrojascr/goals-node:latest
```
Replace latest with v1 or whatever tag you used, if needed.
3. Then, they can run it like this:
```bash
docker run -d -p 3000:80 --name goals-app jrojascr/goals-node:latest
```
or send them this Docker Hub link directly:
https://hub.docker.com/r/jrojascr/goals-node



