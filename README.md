# Containerized Python API

A simple Flask API containerized with Docker.

## Build the Docker Image

```bash
docker build -t flask-api .
```

## Run the Container

```bash
docker run -p 5000:5000 flask-api
```

## Test the API

Open http://localhost:5000 in your browser or use curl:

```bash
curl http://localhost:5000
```

Expected response: `{"message": "Hello, World!"}`

## CI/CD with GitHub Actions

This project uses GitHub Actions for CI/CD. On push to main branch, it:
- Lints and formats code with pre-commit hooks
- Performs static type checking with Pyright
- Builds and pushes Docker image to Docker Hub

### Setup GitHub Actions

1. Create a GitHub repository and push this code.
2. In repo settings > Secrets and variables > Actions:
   - Add variable `DOCKER_USERNAME` with your Docker Hub username.
   - Add secret `DOCKERHUB_TOKEN` with your Docker Hub PAT (Personal Access Token).
3. Invite contributor: Go to Settings > Collaborators > Add people, search for "maescriba".

Workflow runs automatically on push to main.