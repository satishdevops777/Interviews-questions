# DOCKER

1. What is Docker, and why is it used?
```
Answer: Docker is a containerization platform that packages applications with dependencies, ensuring consistency across environments.
```
2. What is the difference between a Docker image and a Docker container?
```
Answer:
Docker Image: A blueprint for creating containers.
Docker Container: A running instance of a Docker image.
```
3. How do you build a Docker image?
```
Answer:
docker build -t myapp .
```
4. What is a Dockerfile?
```
Answer: A script defining how to build a Docker image.
```
5. What is Docker Compose?
```
Answer: A tool for defining and running multi-container Docker applications using docker-compose.yml.
```
6. How do you remove a running Docker container?
```
Answer:
docker rm -f <container_id>
```
7. What is the difference between CMD and ENTRYPOINT in a Dockerfile?
```
Answer:
CMD provides default arguments but can be overridden.
ENTRYPOINT is always executed and cannot be overridden.
```
8. How do you persist data in Docker?
```
Answer: By using Docker Volumes or Bind Mounts.
```
9. What is the purpose of a multi-stage Docker build?
```
Answer: It reduces the final image size by discarding unnecessary files.
```
10. How do you run a Docker container in the background?
```
Answer:
docker run -d myapp
```
11. Coding Task Write a simple Dockerfile for a Python application.

```
FROM python:3.8
WORKDIR /app
COPY . /app
RUN pip install -r requirements.txt
CMD ["python", "app.py"]

```
