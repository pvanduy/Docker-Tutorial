# Docker Basic Commands

This document covers essential Docker commands that will help you get started with Docker.

## 📌 Table of Contents
- [Docker Version](#-docker-version)
- [Working with Images](#-working-with-images)
- [Managing Containers](#-managing-containers)
- [Container Logs](#-container-logs)
- [Networking](#-networking)
- [Volumes](#-volumes)
- [Cleanup](#-cleanup)

## 🛠 Docker Version
Check your installed Docker version:
```sh
$ docker --version
```
## 🏗 Working with Images
### Pull an image from Docker Hub:
```sh
$ docker pull <image_name>
```

Example:
```sh
$ docker pull ubuntu
```

### List downloaded images:
```sh
$ docker images
```

### Remove an image:
```sh
$ docker rmi <image_id>
```


## 🚀 Managing Containers
### Run a container interactively:
```sh
$ docker run -it <image_name> bash
```

### Run a container in detached mode:
```sh
$ docker run -d <image_name>
```

### List running containers:
```sh
$ docker ps
```

### List all containers (including stopped ones):
```sh
$ docker ps -a
```

### Stop a running container:
```sh
$ docker stop <container_id>
```

### Remove a container:
```sh
$ docker rm <container_id>
```


## 📜 Container Logs
View logs of a running container:
```sh
$ docker logs <container_id>
```

## 🔗 Networking
### List Docker networks:
```sh
$ docker network ls
```

### Create a new network:
```sh
$ docker network create <network_name>
```

### Connect a container to a network:
```sh
$ docker network connect <network_name> <container_id>
```


## 📦 Volumes
### List volumes:
```sh
$ docker volume ls
```

### Create a volume:
```sh
$ docker volume create <volume_name>
```

### Remove a volume:
```sh
$ docker volume rm <volume_name>
```


## 🧹 Cleanup
### Remove all stopped containers:
```sh
$ docker container prune
```

### Remove all unused images:
```sh
$ docker image prune -a
```

### Remove all unused volumes:
```sh
$ docker volume prune
```

---
🛠 **Docker Tutorial !!!** 🚀

