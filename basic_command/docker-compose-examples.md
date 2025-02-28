# Docker Compose Examples

This document provides examples of `docker-compose.yml` files for different use cases.

## 📌 Table of Contents
- [Basic Docker Compose](#-basic-docker-compose)
- [Docker Compose for Python Application](#-docker-compose-for-python-application)
- [Docker Compose for Node.js Application](#-docker-compose-for-nodejs-application)
- [Docker Compose for Java Application](#-docker-compose-for-java-application)
- [Docker Compose for Nginx and PHP](#-docker-compose-for-nginx-and-php)
- [Keywork trong Docker Compose](#-keywork-trong-docker-compose)

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



# 🔑 Keywork trong Docker Compose

Trong tệp `docker-compose.yml`, có một số từ khóa quan trọng giúp bạn định nghĩa và quản lý container dễ dàng. Dưới đây là danh sách các từ khóa chính và cách sử dụng chúng.

---

## **1️⃣ version**
Xác định phiên bản của Docker Compose.
```yaml
version: '3.8'  # Phiên bản Docker Compose
```

---

## **2️⃣ services**
Khai báo danh sách các container cần chạy.
```yaml
services:
  web:
    image: nginx
```

---

## **3️⃣ image**
Chỉ định image Docker cần sử dụng.
```yaml
services:
  web:
    image: nginx:latest
```

---

## **4️⃣ build**
Khai báo thư mục chứa `Dockerfile` để build image.
```yaml
services:
  web:
    build: .
```

---

## **5️⃣ container_name**
Đặt tên cụ thể cho container.
```yaml
services:
  web:
    container_name: my_nginx
```

---

## **6️⃣ ports**
Định nghĩa ánh xạ cổng giữa máy host và container.
```yaml
services:
  web:
    ports:
      - "8080:80"  # Map cổng 8080 của host -> cổng 80 của container
```

---

## **7️⃣ environment**
Thiết lập biến môi trường cho container.
```yaml
services:
  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: example
```

---

## **8️⃣ volumes**
Gắn volume để lưu trữ dữ liệu giữa các lần chạy container.
```yaml
services:
  db:
    image: mysql:5.7
    volumes:
      - db_data:/var/lib/mysql
volumes:
  db_data:
```

---

## **9️⃣ networks**
Tạo mạng riêng để các container có thể giao tiếp với nhau.
```yaml
services:
  web:
    image: nginx
    networks:
      - my_network
  app:
    image: my_app
    networks:
      - my_network
networks:
  my_network:
```

---

## **🔟 depends_on**
Xác định thứ tự khởi động container.
```yaml
services:
  web:
    image: nginx
    depends_on:
      - db
  db:
    image: mysql:5.7
```
⚠️ **Lưu ý**: `depends_on` chỉ đảm bảo thứ tự khởi động, không đảm bảo dịch vụ đã sẵn sàng.

---

## **🔹 Các từ khóa khác**
| Từ khóa         | Mô tả |
|-----------------|--------------------------------|
| `restart` | Cấu hình chính sách khởi động lại (`always`, `unless-stopped`, `no`) |
| `command` | Ghi đè lệnh mặc định khi chạy container |
| `entrypoint` | Ghi đè entrypoint của image |
| `extra_hosts` | Thêm entry vào `/etc/hosts` trong container |
| `privileged` | Chạy container với quyền root |
| `cap_add` / `cap_drop` | Cấp hoặc loại bỏ quyền của container |

---

## 🚀 **Ví dụ đầy đủ về Docker Compose**
```yaml
version: '3.8'
services:
  web:
    build: .
    ports:
      - "8080:80"
    depends_on:
      - db
    networks:
      - app_network
  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: example
    volumes:
      - db_data:/var/lib/mysql
    networks:
      - app_network
volumes:
  db_data:
networks:
  app_network:
```

---
🛠 **Docker Tutorial !!!** 🚀

