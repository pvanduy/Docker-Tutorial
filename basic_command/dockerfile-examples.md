# Dockerfile Examples

This document contains various Dockerfile examples for different use cases.

## 📌 Table of Contents
- [Basic Dockerfile](#-basic-dockerfile)
- [Dockerfile for Python Application](#-dockerfile-for-python-application)
- [Dockerfile for Node.js Application](#-dockerfile-for-nodejs-application)
- [Dockerfile for Java Application](#-dockerfile-for-java-application)
- [Dockerfile for Nginx](#-dockerfile-for-nginx)

## 🏗 Basic Dockerfile
A simple Dockerfile that uses an Ubuntu base image.
```dockerfile
# Use Ubuntu as the base image
FROM ubuntu:latest

# Set working directory
WORKDIR /app

# Copy files from host to container
COPY . /app

# Default command
CMD ["echo", "Hello from Docker!"]
```

## 🐍 Dockerfile for Python Application
```dockerfile
# Use official Python image as base
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy application files
COPY . /app

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Default command
CMD ["python", "app.py"]
```

## 🚀 Dockerfile for Node.js Application
```dockerfile
# Use official Node.js image
FROM node:18

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json package-lock.json ./
RUN npm install --production

# Copy the rest of the application
COPY . .

# Expose port
EXPOSE 3000

# Default command
CMD ["node", "server.js"]
```

## ☕ Dockerfile for Java Application
```dockerfile
# Use OpenJDK image
FROM openjdk:17

# Set working directory
WORKDIR /app

# Copy JAR file
COPY target/app.jar /app.jar

# Expose application port
EXPOSE 8080

# Run the application
CMD ["java", "-jar", "/app.jar"]
```

## 🌐 Dockerfile for Nginx
```dockerfile
# Use official Nginx image
FROM nginx:latest

# Copy custom configuration file
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
```

---
🛠 **Docker Tutorial !!!** 🚀

