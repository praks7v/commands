# Common Docker Commands

This document provides a list of common Docker commands along with brief descriptions.

The base command for the [Docker](https://docs.docker.com/reference/cli/docker/) CLI.
[Reference documentation](https://docs.docker.com/reference/).
## Container Management

| Command                              | Description                                       |
|--------------------------------------|---------------------------------------------------|
| `docker run`                         | Run a command in a new container.                 |
| `docker start`                       | Start one or more stopped containers.             |
| `docker stop`                        | Stop one or more running containers.              |
| `docker restart`                     | Restart one or more containers.                   |
| `docker pause`                       | Pause all processes within one or more containers.|
| `docker unpause`                     | Unpause all processes within one or more containers.|
| `docker rm`                          | Remove one or more containers.                    |
| `docker ps`                          | List containers.                                  |
| `docker exec`                        | Run a command in a running container.             |
| `docker logs`                        | Fetch the logs of a container.                    |
| `docker inspect`                     | Return low-level information on Docker objects.   |
| `docker top`                         | Display the running processes of a container.     |
| `docker attach`                      | Attach local standard input, output, and error streams to a running container. |
| `docker update`                      | Update configuration of one or more containers.   |

## Image Management

| Command                              | Description                                       |
|--------------------------------------|---------------------------------------------------|
| `docker build`                       | Build an image from a Dockerfile.                 |
| `docker pull`                        | Pull an image or a repository from a registry.    |
| `docker push`                        | Push an image or a repository to a registry.      |
| `docker images`                      | List images.                                      |
| `docker rmi`                         | Remove one or more images.                        |
| `docker tag`                         | Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE. |
| `docker save`                        | Save one or more images to a tar archive (streamed to STDOUT by default). |
| `docker load`                        | Load an image from a tar archive or STDIN.        |
| `docker history`                     | Show the history of an image.                     |

## Network Management

| Command                              | Description                                       |
|--------------------------------------|---------------------------------------------------|
| `docker network create`              | Create a new network.                             |
| `docker network inspect`             | Display detailed information on one or more networks. |
| `docker network ls`                  | List networks.                                    |
| `docker network rm`                  | Remove one or more networks.                      |
| `docker network connect`             | Connect a container to a network.                 |
| `docker network disconnect`          | Disconnect a container from a network.            |

## Volume Management

| Command                              | Description                                       |
|--------------------------------------|---------------------------------------------------|
| `docker volume create`               | Create a new volume.                              |
| `docker volume inspect`              | Display detailed information about one or more volumes. |
| `docker volume ls`                   | List volumes.                                     |
| `docker volume rm`                   | Remove one or more volumes.                       |
| `docker volume prune`                | Remove all unused local volumes.                  |

## System Management

| Command                              | Description                                       |
|--------------------------------------|---------------------------------------------------|
| `docker info`                        | Display system-wide information.                  |
| `docker version`                     | Show the Docker version information.              |
| `docker system df`                   | Show Docker disk usage.                           |
| `docker system prune`                | Remove unused data.                               |
| `docker stats`                       | Display a live stream of container(s) resource usage statistics. |

## Docker Compose

| Command                              | Description                                       |
|--------------------------------------|---------------------------------------------------|
| `docker-compose up`                  | Build, (re)create, start, and attach to containers for a service. |
| `docker-compose down`                | Stop and remove containers, networks, images, and volumes. |
| `docker-compose build`               | Build or rebuild services.                        |
| `docker-compose start`               | Start existing containers.                        |
| `docker-compose stop`                | Stop running containers without removing them.    |
| `docker-compose restart`             | Restart running containers.                       |
| `docker-compose ps`                  | List containers.                                  |
| `docker-compose logs`                | View output from containers.                      |
| `docker-compose exec`                | Execute a command in a running container.         |
| `docker-compose run`                 | Run a one-off command on a service.               |
| `docker-compose pull`                | Pull service images.                              |
| `docker-compose config`              | Validate and view the Compose file.               |

These commands form the basic toolkit for managing Docker containers, images, networks, volumes, and system-wide information.
