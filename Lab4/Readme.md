# About me 
### Full name: Anani Thierry Kassa
### Student ID: 041140713

## 1- Demo Video (Max 5 minutes)
https://youtu.be/gsLWilPnais

## 2- Answer the following in your README.md file.

- What are the main differences between a Docker image and a Docker container?
    A Docker image is used to create a Docker container while Docker container is used to run an application

- Explain how Docker's layered architecture improves efficiency.
   - Layers are cached and reused 

- Why does each container get its own writable layer?
   - When you run a container, Docker adds a thin writable layer on top of the read-only image layers which makes the container get its own layer.

- What are the benefits of using Docker Compose over running containers individually?
    - Docker Compose is a tool for defining and running multi-container applications.
    - It allows us to define multiple services and their relationships in a single docker-compose.ymlfile.
    - Simplifies storage configuration across multiple containers.

## 3- GitHub Repository (Submission Repo)
- see Github repo