# docker-cheat-sheet
# 🐳 Docker Cheat Sheet

A quick reference guide to the most commonly used Docker commands. Perfect for beginners and intermediate users managing containers, images, volumes, and Docker Compose projects.

---

## 🔧 Docker Installation

```bash
# Ubuntu
sudo apt update
sudo apt install docker.io

# Start and enable Docker
sudo systemctl start docker
sudo systemctl enable docker
```

## 🚀 Docker Containers

# Run a container (interactive)
docker run -it ubuntu bash

# Run and automatically remove the container after exit
docker run --rm ubuntu

# Run in detached mode
docker run -d nginx

# Start an existing container
docker start <container_id_or_name>

# Stop a container
docker stop <container_id_or_name>

# List running containers
docker ps

# List all containers
docker ps -a

# Remove a container
docker rm <container_id_or_name>

# Remove all stopped containers
docker container prune


## 📦 Docker Images

# Pull an image from Docker Hub
docker pull ubuntu

# Build an image from a Dockerfile
docker build -t my-image .

# List all images
docker images

# Remove an image
docker rmi <image_id_or_name>

# Remove all unused images
docker image prune


## 📁 Docker Volumes

# Create a volume
docker volume create my-volume

# List volumes
docker volume ls

# Inspect a volume
docker volume inspect my-volume

# Remove a volume
docker volume rm my-volume

# Remove all unused volumes
docker volume prune


## ⚙️ Docker Networks

# List networks
docker network ls

# Create a network
docker network create my-network

# Connect a container to a network
docker network connect my-network my-container

# Disconnect a container from a network
docker network disconnect my-network my-container


## 🧰 Docker Compose

# Start services
docker-compose up

# Start in detached mode
docker-compose up -d

# Stop services
docker-compose down

# Build or rebuild services
docker-compose build

# View service logs
docker-compose logs

# Scale services
docker-compose up --scale web=3


## 🔍 Useful Commands

# Execute a command inside a running container
docker exec -it <container_name> bash

# Show container logs
docker logs <container_id_or_name>

# Copy files from container to host
docker cp <container_id>:/path/in/container /host/path

# Display system-wide information
docker info

# Display Docker version
docker version


## 📄 Dockerfile Example

# Use an official base image
FROM node:18

# Set the working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the code
COPY . .

# Expose port
EXPOSE 3000

# Start the app
CMD ["npm", "start"]


## 🧹 Clean-Up Commands

# Stop all containers
docker stop $(docker ps -q)

# Remove all containers
docker rm $(docker ps -aq)

# Remove all images
docker rmi $(docker images -q)

# Remove all unused data (networks, images, volumes, containers)
docker system prune -a


## 📚 Resources
Docker Docs

Play with Docker

DockerHub