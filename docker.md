# Docker Cheatsheet

---

## 1. Images & Containers
- Pull image: `docker pull IMAGE`
- List images: `docker images`
- Run container: `docker run -d --name NAME IMAGE`
- List containers: `docker ps -a`

---

## 2. Dockerfile Basics
```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
```

---

## 3. Volumes & Networks
- Volume: `docker run -v host_path:container_path IMAGE`
- Network: `docker network create net`, `docker run --network net ...`

---

## 4. Docker Compose
```yaml
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
```
- Start: `docker-compose up`
- Stop: `docker-compose down`

---
