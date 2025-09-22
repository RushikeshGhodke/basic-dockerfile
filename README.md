# Basic Dockerfile

A simple Docker project that demonstrates the basics of creating and running a Docker container using Alpine Linux.

**Project Page URL:** https://roadmap.sh/projects/basic-dockerfile

## Overview

This project contains a basic Dockerfile that creates a minimal Docker image based on Alpine Linux. When run, the container prints "Hello, Captain!" to the console and exits.

## Requirements Met

- ✅ Dockerfile is named `Dockerfile`
- ✅ Dockerfile is located in the root directory
- ✅ Base image is `alpine:latest`
- ✅ Contains instruction to print "Hello, Captain!" to console before exiting

## Project Structure

```
hello-captain/
├── Dockerfile
└── README.md
```

## Getting Started

### Prerequisites

- Docker installed on your system
- Basic understanding of Docker commands

### Building the Image

To build the Docker image, run the following command from the project root directory:

```bash
docker build -t hello-captain .
```

### Running the Container

To run the container and see the greeting message:

```bash
docker run hello-captain
```

You should see the output:
```
Hello, Captain!
```

## Dockerfile Explanation

```dockerfile
FROM alpine:latest
```
- Uses Alpine Linux as the base image (lightweight Linux distribution)

```dockerfile
CMD [ "echo", "Hello, Captain!" ]
```
- Defines the default command to execute when the container starts
- Uses the `echo` command to print "Hello, Captain!" to the console

## Advanced Version (Optional Enhancement)

For a more advanced version, you can modify the Dockerfile to accept a name as a build argument:

```dockerfile
FROM alpine:latest

ARG NAME=Captain

CMD echo "Hello, ${NAME}!"
```

Then build and run with a custom name:

```bash
# Build with custom name
docker build --build-arg NAME="YourName" -t hello-captain-advanced .

# Run the container
docker run hello-captain-advanced
```

## Docker Commands Reference

| Command | Description |
|---------|-------------|
| `docker build -t <tag> .` | Build image with a tag |
| `docker run <image>` | Run container from image |
| `docker images` | List all images |
| `docker ps -a` | List all containers |
| `docker rmi <image>` | Remove an image |
| `docker rm <container>` | Remove a container |
