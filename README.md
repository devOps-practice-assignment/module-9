## Assignment 9 Submission

- Name: Md Khayrul Hasan
- Submission date: 5 May 2026
- GitHub repo: https://github.com/devOps-practice-assignment/module-9.git
- DockerHub image: https://hub.docker.com/repository/docker/khayrul/module-3-deployment-app/tags
- PDF: Assignment_9_Docker_Docker_Compose_Submission.pdf

## App Overview

- Routes:
  - `/` returns an HTML page
  - `/api` returns JSON
- Default port:
  - Local Node: `PORT` env var or `5000`

## Run Locally (Node)

Prerequisite: Node 22

```bash
npm install
npm run check
npm start
```

Open:
- http://localhost:5000/
- http://localhost:5000/api

## Run with Docker Compose (Nginx + Express)

This setup runs:
- Nginx from an official image (`nginx:alpine`)
- Express app built from the provided `Dockerfile`
- Public access on port `8080` (Nginx reverse-proxies to the Express container)

```bash
docker compose up --build -d
docker compose ps
```

Open:
- http://localhost:8080/
- http://localhost:8080/api

Stop:
```bash
docker compose down
```

## Push Image to DockerHub

```bash
docker login
docker images
docker tag module-3-deployment-app:latest khayrul/module-3-deployment-app:latest
docker push khayrul/module-3-deployment-app:latest
```
