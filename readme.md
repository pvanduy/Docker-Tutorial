# Docker Learning Repository

Welcome to the Docker Learning Repository! This repository is designed to help you understand and master Docker, covering fundamental concepts, commands, and best practices.

## 📌 Table of Contents
- [Introduction](#-introduction)
- [Installation](#-installation)
- [Basic Docker Commands](#-basic-docker-commands)
- [Working with Dockerfiles](#-working-with-dockerfiles)
- [Docker Compose](#-docker-compose)
- [Best Practices](#-best-practices)
- [Troubleshooting](#-troubleshooting)

## 🚀 Introduction
Docker is a platform that enables developers to build, package, and distribute applications as lightweight, portable containers. It simplifies deployment and ensures consistency across different environments.

## 🛠 Installation
Follow the official Docker installation guide for your operating system:
- [Windows](https://docs.docker.com/desktop/install/windows-install/)
- [MacOS](https://docs.docker.com/desktop/install/mac-install/)
- [Linux](https://docs.docker.com/engine/install/)


## 📜 Basic Docker Commands
Here are some commonly used Docker commands:
```sh
# Check Docker version
$ docker --version

# Pull an image
$ docker pull ubuntu

# List Docker images
$ docker images

# Run a container
$ docker run -it ubuntu bash

# List running containers
$ docker ps
```
For a complete list of commands, check out the [basic-commands](basic_command/basic-commands.md) file.

## 🏗 Working with Dockerfiles
A **Dockerfile** is a script that contains instructions to build a Docker image. Example:
```dockerfile
FROM ubuntu:latest
RUN apt-get update && apt-get install -y curl
CMD ["bash"]
```
Check out the [Dockerfile-examples](basic_command/dockerfile-examples.md) file for more.

## 📦 Docker Compose
Docker Compose allows you to define multi-container applications. Example `docker-compose.yml`:
```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
```
Find more examples in the [docker-compose-examples](basic_command/docker-compose-examples.md) file.

## ✅ Best Practices
- Use small, optimized base images (e.g., `alpine`)
- Avoid storing secrets in Dockerfiles
- Use multi-stage builds to reduce image size
- Leverage `.dockerignore` to exclude unnecessary files

## 🔧 Troubleshooting
If you encounter issues, check out [docker-troubleshoot.md](docker-troubleshoot.md) for common problems and solutions.

---
🛠 **Docker-Tutorial !!!** 🚀
