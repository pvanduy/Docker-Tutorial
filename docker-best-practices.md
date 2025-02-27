# Docker Best Practices

This document outlines best practices for working with Docker efficiently and securely.

## 📌 Table of Contents
- [Use Official Images](#-use-official-images)
- [Keep Images Small](#-keep-images-small)
- [Use Multi-Stage Builds](#-use-multi-stage-builds)
- [Leverage .dockerignore](#-leverage-dockerignore)
- [Use Environment Variables](#-use-environment-variables)
- [Limit Container Privileges](#-limit-container-privileges)
- [Monitor and Clean Up Containers](#-monitor-and-clean-up-containers)
- [Tag and Version Images](#-tag-and-version-images)
- [Use Health Checks](#-use-health-checks)
- [Secure Your Docker Daemon](#-secure-your-docker-daemon)

## 🏗 Use Official Images
- Prefer official images from Docker Hub to ensure security and updates.
- Example:
  ```sh
  FROM python:3.9-slim
  ```

## 📉 Keep Images Small
- Use minimal base images like `alpine` to reduce attack surface and speed up builds.
- Example:
  ```sh
  FROM node:18-alpine
  ```

## 🚀 Use Multi-Stage Builds
- Reduce image size by separating build and runtime environments.
- Example:
  ```dockerfile
  FROM golang:1.18 AS builder
  WORKDIR /app
  COPY . .
  RUN go build -o myapp

  FROM alpine:latest
  WORKDIR /root/
  COPY --from=builder /app/myapp .
  CMD ["./myapp"]
  ```

## 📝 Leverage .dockerignore
- Exclude unnecessary files (e.g., `.git`, `node_modules`, `.env`).
- Example `.dockerignore`:
  ```
  node_modules
  .git
  .env
  ```

## 🔑 Use Environment Variables
- Avoid hardcoding secrets; use environment variables instead.
- Example:
  ```dockerfile
  ENV DATABASE_URL=mysql://user:pass@host/db
  ```

## 🔒 Limit Container Privileges
- Run containers as non-root users to enhance security.
- Example:
  ```dockerfile
  RUN adduser -D appuser
  USER appuser
  ```

## 🛠 Monitor and Clean Up Containers
- Regularly remove unused images, containers, and volumes.
- Commands:
  ```sh
  docker system prune -a
  ```

## 🏷 Tag and Version Images
- Use meaningful tags instead of `latest`.
- Example:
  ```sh
  docker build -t myapp:1.0.0 .
  ```

## 💡 Use Health Checks
- Ensure containers are running properly.
- Example:
  ```dockerfile
  HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD curl -f http://localhost || exit 1
  ```

## 🔐 Secure Your Docker Daemon
- Restrict access and enable TLS.
- Example:
  ```sh
  dockerd --tlsverify --tlscacert=ca.pem --tlscert=server-cert.pem --tlskey=server-key.pem
  ```

---
🛠 **Docker-Tutorial !!!** 🚀

