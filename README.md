# Introduction to Docker and Containers

## What are Containers?

In software development and deployment, developers often encountered the "it works on my machine" issue. Code that functioned perfectly on a local setup would fail in other environments due to inconsistencies in configurations, libraries, or dependencies.

## Docker

Docker is a powerful tool designed to eliminate these environment-related issues. Introduced in 2013 by Solomon Hykes, Docker is a containerization platform that transformed how software is built, shipped, and deployed.

Containers are isolated environments that package an application with all its dependencies and configurations. This ensures that the application works the same way across development, testing, and production environments.

> Docker enables developers to avoid the common "it works on my machine" problem.

Docker simplifies the deployment process, improves compatibility, and ensures consistency across environments.

## Advantages of Containers

### Portability Across Different Environments

Docker containers include everything an application needs to run. This ensures consistent behavior regardless of the environment.

### Resource Efficiency Compared to Virtual Machines

Containers share the host's OS kernel, making them more lightweight than virtual machines, which require their own OS instance.

### Rapid Application Deployment and Scaling

Containers can be started or stopped quickly, making it easy to scale applications up or down based on demand.

## Comparison of Docker Containers with Virtual Machines

| Feature              | Docker Containers                           | Virtual Machines                        |
|----------------------|---------------------------------------------|-----------------------------------------|
| Virtualization Type  | OS-level (shares host kernel)              | Hardware-level (runs guest OS)          |
| Resource Usage       | Lightweight, minimal overhead               | Heavy, each VM requires its own OS      |
| Startup Time         | Seconds                                     | Minutes                                 |
| Portability          | High (runs the same on any system)          | Less portable                           |
| Use Cases            | Microservices, CI/CD, lightweight apps      | Stronger isolation, legacy applications |

## Importance of Docker

### Technology and Industry Impact

Docker has transformed development by making environments more consistent and deployment more efficient. It is widely used in modern DevOps practices.

### Real-World Impact

Organizations using Docker benefit from faster development, better collaboration, and lower infrastructure costs.

## Target Audience

This course is intended for:

- DevOps professionals focused on deployment and orchestration.
- Developers seeking consistent workflows.
- Cloud engineers, QA engineers, tech enthusiasts, and students preparing for technical roles.

## Prerequisites

Before starting this course, learners should:

- Have completed *TechOps Career Essentials* and *Advanced TechOps*.
- Be comfortable with Linux and terminal commands.
- Understand basic cloud computing concepts.
- Be familiar with virtual machines and their role in deployment.

## Project Goals

By the end of the course, learners will:

- Understand container isolation and application packaging.
- Learn core Docker features, commands, and best practices.
- Compare Docker with virtual machines regarding resource usage.
- Deploy and scale applications using Docker.
- Ensure consistent application behavior across environments.

## Getting Started with Docker

### Installing Docker on Ubuntu 20.04 LTS

Launch an Ubuntu 20.04 LTS instance and connect to it. Then, run the following commands:

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

Add Docker repository:

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Update and install Docker:

```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Verify Docker status:

```bash
sudo systemctl status docker
```

Run Docker without `sudo`:

```bash
sudo usermod -aG docker ubuntu
```

---

## 🐳 Running the "Hello World" Container

Use `docker run`:

```bash
docker run hello-world
```

What happens:
- Pulls the `hello-world` image (if not local).
- Creates and starts a container.
- Prints a welcome message.

### 🧱 Docker Image and Container Lifecycle

- **Image**: Immutable template for containers (code, runtime, dependencies).
- **Container**: A running instance of an image.

Lifecycle: `create → start → stop → delete`.

Check available images:

```bash
docker images
```

---

## Basic Docker Commands

### `docker run`

```bash
docker run hello-world
```

Run a container from an image.

### `docker ps`

```bash
docker ps          # Show running containers
docker ps -a       # Show all (running + stopped)
```

### `docker stop`

```bash
docker stop <CONTAINER_ID>
```

Stop a running container.

### `docker pull`

```bash
docker pull <IMAGE_NAME>
```

Download an image from Docker Hub.

---

```
