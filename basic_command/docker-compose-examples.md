# Docker Compose Examples

This document provides examples of `docker-compose.yml` files for different use cases.

## 📌 Table of Contents
- [Basic Docker Compose](#-basic-docker-compose)
- [Docker Compose for Python Application](#-docker-compose-for-python-application)
- [Docker Compose for Node.js Application](#-docker-compose-for-nodejs-application)
- [Docker Compose for Java Application](#-docker-compose-for-java-application)
- [Docker Compose for Nginx and PHP](#-docker-compose-for-nginx-and-php)

## 🏗 Basic Docker Compose
A simple `docker-compose.yml` example for a single-container application.
```yaml
version: '3'
services:
  app:
    image: ubuntu:latest
    command: echo "Hello from Docker Compose!"
```

## 🐍 Docker Compose for Python Application
```yaml
version: '3.8'
services:
  web:
    build: .
    ports:
      - "5000:5000"
    volumes:
      - .:/app
    environment:
      - FLASK_ENV=development
```

## 🚀 Docker Compose for Node.js Application
```yaml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "3000:3000"
    volumes:
      - .:/usr/src/app
    environment:
      - NODE_ENV=production
```

## ☕ Docker Compose for Java Application
```yaml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "8080:8080"
    environment:
      - SPRING_PROFILES_ACTIVE=dev
```

## 🌐 Docker Compose for Nginx and PHP
```yaml
version: '3.8'
services:
  nginx:
    image: nginx:latest
    ports:
      - "80:80"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
  php:
    image: php:fpm
    volumes:
      - ./app:/var/www/html
```

---
🛠 **Docker Tutorial !!!** 🚀

