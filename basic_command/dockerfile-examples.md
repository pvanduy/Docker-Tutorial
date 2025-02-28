# Dockerfile Examples

This document contains various Dockerfile examples for different use cases.

## 📌 Table of Contents
- [Basic Dockerfile](#-basic-dockerfile)
- [Dockerfile for Python Application](#-dockerfile-for-python-application)
- [Dockerfile for Node.js Application](#-dockerfile-for-nodejs-application)
- [Dockerfile for Java Application](#-dockerfile-for-java-application)
- [Dockerfile for Nginx](#-dockerfile-for-nginx)
- [Keywork trong Dockerfile](#-keywork-trong-dockerfile)

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

# 🔑 Keywork trong Dockerfile

Dockerfile là một tập tin định nghĩa cách tạo một Docker Image. Dưới đây là danh sách các từ khóa quan trọng trong Dockerfile.

---

## **1️⃣ FROM**
Xác định image cơ sở để tạo container.
```dockerfile
FROM ubuntu:20.04
```

---

## **2️⃣ RUN**
Thực thi lệnh trong quá trình build image.
```dockerfile
RUN apt-get update && apt-get install -y nginx
```

---

## **3️⃣ CMD**
Xác định lệnh mặc định chạy khi container khởi động.
```dockerfile
CMD ["nginx", "-g", "daemon off;"]
```

---

## **4️⃣ ENTRYPOINT**
Xác định lệnh chính khi container chạy, cho phép truyền tham số.
```dockerfile
ENTRYPOINT ["python", "app.py"]
```

---

## **5️⃣ COPY**
Sao chép file từ máy host vào container.
```dockerfile
COPY index.html /usr/share/nginx/html/
```

---

## **6️⃣ ADD**
Tương tự `COPY`, nhưng hỗ trợ tải file từ URL hoặc giải nén file `.tar.gz`.
```dockerfile
ADD https://example.com/file.tar.gz /app/
```

---

## **7️⃣ WORKDIR**
Thiết lập thư mục làm việc mặc định.
```dockerfile
WORKDIR /app
```

---

## **8️⃣ EXPOSE**
Khai báo cổng container sẽ lắng nghe.
```dockerfile
EXPOSE 80
```

---

## **9️⃣ ENV**
Thiết lập biến môi trường trong container.
```dockerfile
ENV APP_ENV=production
```

---

## **🔟 VOLUME**
Tạo volume để lưu trữ dữ liệu bên ngoài container.
```dockerfile
VOLUME ["/data"]
```

---

## **🔹 USER**
Chạy container với user không phải root.
```dockerfile
USER appuser
```

---

## **🚀 Ví dụ hoàn chỉnh về Dockerfile**
```dockerfile
# Sử dụng image cơ sở
FROM node:18-alpine

# Thiết lập thư mục làm việc
WORKDIR /app

# Copy file vào container
COPY . .

# Cài đặt dependencies
RUN npm install

# Thiết lập biến môi trường
ENV NODE_ENV=production

# Mở cổng 3000
EXPOSE 3000

# Lệnh khởi chạy container
CMD ["node", "server.js"]
```


---
🛠 **Docker Tutorial !!!** 🚀

