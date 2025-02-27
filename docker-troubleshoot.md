# Docker Troubleshooting Guide

This document provides solutions to common Docker issues.

## 📌 Table of Contents
- [Docker Daemon Not Running](#-docker-daemon-not-running)
- [Permission Denied Errors](#-permission-denied-errors)
- [Container Exits Immediately](#-container-exits-immediately)
- [Port Already in Use](#-port-already-in-use)
- [No Space Left on Device](#-no-space-left-on-device)
- [Image Pull Failures](#-image-pull-failures)
- [Network Issues](#-network-issues)

## 🛠 Docker Daemon Not Running
### Issue:
```sh
Cannot connect to the Docker daemon at unix:///var/run/docker.sock.
```
### Solution:
- Check if the Docker service is running:
  ```sh
  sudo systemctl status docker
  ```
- Start the Docker service:
  ```sh
  sudo systemctl start docker
  ```
- Restart Docker:
  ```sh
  sudo systemctl restart docker
  ```

## 🔑 Permission Denied Errors
### Issue:
```sh
Got permission denied while trying to connect to the Docker daemon socket.
```
### Solution:
- Add your user to the Docker group:
  ```sh
  sudo usermod -aG docker $USER
  ```
- Log out and log back in, then verify with:
  ```sh
  docker info
  ```

## 🚀 Container Exits Immediately
### Issue:
```sh
Container runs and exits immediately.
```
### Solution:
- Check logs:
  ```sh
  docker logs <container_id>
  ```
- Run in interactive mode:
  ```sh
  docker run -it <image_name> /bin/bash
  ```

## 🔄 Port Already in Use
### Issue:
```sh
Bind for 0.0.0.0:8080 failed: port is already allocated.
```
### Solution:
- Find the process using the port:
  ```sh
  sudo lsof -i :8080
  ```
- Kill the process:
  ```sh
  sudo kill -9 <PID>
  ```

## 💾 No Space Left on Device
### Issue:
```sh
write /var/lib/docker/tmp/... no space left on device.
```
### Solution:
- Remove unused Docker objects:
  ```sh
  docker system prune -a
  ```
- Check disk usage:
  ```sh
  docker system df
  ```

## 🌐 Image Pull Failures
### Issue:
```sh
Error response from daemon: pull access denied.
```
### Solution:
- Log in to Docker Hub:
  ```sh
  docker login
  ```
- Check internet connection and DNS settings.

## 🔗 Network Issues
### Issue:
```sh
Network unreachable inside container.
```
### Solution:
- Restart Docker network:
  ```sh
  docker network prune
  ```
- Ensure the container is connected to the right network:
  ```sh
  docker network ls
  ```

---
🛠 **Docker Tutorial !!!** 🚀

