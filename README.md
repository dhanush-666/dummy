# 🐳 DevOps Assignment: Nginx Reverse Proxy + Docker Compose

This project demonstrates a containerized microservices setup using **Docker Compose** and **Nginx** as a reverse proxy. Two backend services (a Golang app and a Python app) are routed via Nginx based on URL paths.

---

## 📁 Project Structure

```
.
├── docker-compose.yml
├── nginx
│   ├── nginx.conf
│   └── Dockerfile
├── service_1   # Golang service
│   ├── main.go
│   └── Dockerfile
├── service_2   # Python service
│   ├── app.py
│   └── Dockerfile
└── README.md
```

---

## 🚀 Getting Started

### ✅ Prerequisites

- Docker
- Docker Compose

### 📦 Setup

Clone the repository:

```bash
git clone https://github.com/dhanush-666/dummy.git
cd dummy
```

Build and start all services:

```bash
docker-compose up --build
```

---

## 🔁 Reverse Proxy Routing

Nginx (running as a container) handles incoming HTTP requests on port `8081` and routes them based on path:

| Path         | Service        | Description       |
|--------------|----------------|-------------------|
| `/service1`  | Golang App     | Handles Go logic  |
| `/service2`  | Python App     | Handles Python logic |

Example:

- [http://localhost:8081/service_1/hello]
- [http://localhost:8081/service_1/ping]
- [http://localhost:8081/service_2/hello]
- [http://localhost:8081/service_2/ping]


---

## 📊 Logging

Nginx is configured to log each request with the **timestamp** and **path** accessed. Logs can be viewed using:

```bash
docker logs nginx
```

---

## ❤️ Bonus Features

- ✅ Health checks are configured in `docker-compose.yml` to ensure each service is up and responsive.
- ✅ Nginx container logs all incoming requests.
- ✅ Single command deployment using Docker Compose.

---

## 🔍 Health Check

You can check container health using:

```bash
docker ps
```

Each service shows `healthy` in the status once ready.

---

## 🧑‍💻 Author

**Dhanush S**  
[GitHub](https://github.com/dhanush-666)
---

