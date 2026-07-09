# CI/CD Web Project

This project is set up to build a static website with Nginx inside a Docker container, push the image to Docker Hub, and deploy it with GitHub Actions.

## Required GitHub secrets

Add these in your GitHub repository under Settings > Secrets and variables > Actions:

- DOCKER_USERNAME
- DOCKER_PASSWORD
- SERVER_HOST
- SERVER_USERNAME
- SERVER_SSH_KEY
- SERVER_PORT (optional, defaults to 22)

## How it works

- On every push to the main branch, GitHub Actions builds the Docker image.
- The image is pushed to Docker Hub.
- A deployment step connects to your server and runs the new container.

## Local test

Run locally:

```bash
docker build -t cicd-web .
docker run -d --name cicd-web -p 80:80 cicd-web
```
