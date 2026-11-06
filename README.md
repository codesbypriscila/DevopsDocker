# DevOps Lab · Docker

A small Flask "Hello World" app packaged in a Docker image, with a GitHub Actions workflow that builds the image and pushes it to Docker Hub.

Part of my DevOps labs (Electiva 2).

## What it shows

- Writing a **Dockerfile** for a Python app.
- Building and running the container locally.
- A **GitHub Actions** workflow (`.github/deploy.yml`) that, on every push to `main`, logs in to Docker Hub and builds and pushes the image.

## Tech stack

- **Python** + **Flask**
- **Docker**
- **GitHub Actions**
- **Docker Hub**

## Files

```
app.py            Flask app with one route: /
DockerFile        Image based on python:3.10-slim
Requirements.txt  Python dependencies
.github/deploy.yml  CI/CD workflow
```

## Running it locally

```bash
docker build -f DockerFile -t holamundo-app .
docker run -p 5000:5000 holamundo-app
```

Then open [http://localhost:5000](http://localhost:5000).

The workflow needs two repository secrets: `DOCKER_USERNAME` and `DOCKER_PASSWORD`.
