# 🚀 CoderCo Containers Challenge

## 🧠 Project Overview
This project is part of the CoderCo Containers Challenge, where the goal is to build and run a **multi-container Docker application** using Flask and Redis. It demonstrates how different services (web + database) can communicate with each other using Docker Compose.

## 📦 Application Architecture
The system consists of the following containers:

- **Flask App** (`web`): A Python Flask application exposing two endpoints.
- **Redis DB** (`redis`): A Redis instance used to persist a page visit counter.
- **NGINX** (`nginx`): Acts as a reverse proxy to forward traffic to the Flask app.

## 🔧 Features
### Flask Web App (`count.py`)
- `/`: Displays a welcome message.
- `/count`: Increments and displays a counter stored in Redis.

### Redis
- Acts as a key-value store for the visit counter.
- Configured with persistent volume support.

### NGINX
- Load balances traffic across Flask instances (scalable via Docker Compose).

## 🐳 Docker & Docker Compose
The application is fully containerised and orchestrated via Docker Compose.

### Services
| Service | Description               | Port    |
|---------|---------------------------|---------|
| `web`   | Flask application         | 5001    |
| `redis` | Redis database            | 6379    |
| `nginx` | Reverse proxy to Flask    | 5001    |

### Volumes
Redis data is stored persistently using a Docker volume (`redis-data`).

## 📁 Folder Structure
```bash
container_challenge/
├── count.py                # Flask app
├── Dockerfile              # Builds Flask image
├── docker-compose.yml      # Defines multi-container setup
├── nginx.conf              # NGINX config
└── README.md               # You're here!
