---
tags:
  - DevOps
  - Docker
  - Cheatsheet
title: Docker Cheat Sheet
draft:
---

## Basic Commands
- `docker --version`: Check Docker version
- `docker info`: Display system-wide information
- `docker pull <image>`: Pull image from registry
- `docker images`: List all images
- `docker rmi <image>`: Remove image

## Container Management
- `docker run -it <image> <cmd>`: Run container interactively
- `docker run -d <image>`: Run container in detached mode
- `docker ps`: List running containers
- `docker ps -a`: List all containers
- `docker stop <container>`: Stop running container
- `docker start <container>`: Start stopped container
- `docker restart <container>`: Restart container
- `docker rm <container>`: Remove container
- `docker exec -it <container> <cmd>`: Execute command in running container

## Image Building
- `docker build -t <name:tag> .`: Build image from Dockerfile
- `docker tag <source> <target>`: Create a tag for an image
- `docker push <image>`: Push image to registry

## Container Configuration
- `-p <host_port>:<container_port>`: Map ports
- `-v <host_path>:<container_path>`: Mount volume
- `--name <name>`: Assign name to container
- `-e <key>=<value>`: Set environment variable
- `--network <network>`: Connect container to network

## Volume Management
- `docker volume create <volume>`: Create a volume
- `docker volume ls`: List volumes
- `docker volume rm <volume>`: Remove volume
- `docker volume inspect <volume>`: Display volume details

## Network Management
- `docker network create <network>`: Create a network
- `docker network ls`: List networks
- `docker network rm <network>`: Remove network
- `docker network connect <network> <container>`: Connect container to network

## Cleanup
- `docker system prune`: Remove unused data
- `docker container prune`: Remove stopped containers
- `docker image prune`: Remove unused images
- `docker volume prune`: Remove unused volumes

## Dockerfile Basics
``` dockerfile
FROM <image>          # Base image
WORKDIR <path>        # Set working directory
COPY <src> <dst>      # Copy files to container
RUN <command>         # Execute command during build
CMD ["<command>"]     # Default command to run
EXPOSE <port>         # Document ports
ENV <key>=<value>     # Set environment variable
```