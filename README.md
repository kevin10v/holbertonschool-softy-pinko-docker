# Holberton School — Softy Pinko Docker

![Holberton](https://img.shields.io/badge/Holberton-School-red?style=flat-square) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask)

## Description

This project containerizes the **Softy Pinko** web application — a full-stack app with a Flask API backend and a static HTML/CSS/JS frontend — using **Docker** and **Docker Compose**. It demonstrates how to split an application into isolated services and orchestrate them together.

## Architecture

```
                    ┌─────────────────┐
                    │   Load Balancer  │  (HAProxy / Nginx)
                    └────────┬────────┘
                             │
            ┌────────────────┴─────────────────┐
            │                                  │
   ┌────────▼────────┐              ┌──────────▼──────────┐
   │  Front-End      │              │   Back-End (Flask)   │
   │  (Static Files) │              │   REST API           │
   └─────────────────┘              └─────────────────────┘
```

## Services

| Service | Technology | Port |
|---------|-----------|------|
| Front-End | Nginx + HTML/CSS/JS | 80 |
| Back-End | Python Flask | 5252 |
| Load Balancer | HAProxy | 80 |

## Getting Started

```bash
# Clone the repository
git clone https://github.com/kevinvoka/holbertonschool-softy-pinko-docker.git
cd holbertonschool-softy-pinko-docker

# Build and run all services
docker-compose up --build

# Access the app
open http://localhost
```

## Docker Commands

```bash
# Build a single image
docker build -t softy-pinko-back-end ./back-end

# Run a container
docker run -p 5252:5252 softy-pinko-back-end

# Stop all containers
docker-compose down
```

## Learning Objectives

- Understand containerization and the benefits of Docker
- Write `Dockerfile` for Python Flask applications
- Use `docker-compose` to orchestrate multi-service applications
- Configure a load balancer to distribute traffic across containers
- Understand networking between Docker containers

## Technologies

| Tool | Version |
|------|---------|
| Docker | 24.x |
| Docker Compose | 2.x |
| Python | 3.9+ |
| Flask | 2.x |
| Nginx | 1.x |
| HAProxy | 2.x |

## Author

**Kevin Voka** — [GitHub](https://github.com/kevinvoka)

