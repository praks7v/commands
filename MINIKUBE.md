# Common Minikube Commands

This document provides a list of common Minikube commands along with brief descriptions.

## Minikube Cluster Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube start`             | Start a local Kubernetes cluster.                         |
| `minikube stop`              | Stop a running local Kubernetes cluster.                  |
| `minikube delete`            | Delete a local Kubernetes cluster.                        |
| `minikube status`            | Display the status of the local Kubernetes cluster.       |
| `minikube pause`             | Pause Kubernetes without impacting deployed applications. |
| `minikube unpause`           | Unpause a Kubernetes cluster.                             |
| `minikube restart`           | Restart a local Kubernetes cluster.                       |
| `minikube update-context`    | Update kubeconfig to use minikube cluster.                |

## Minikube Configuration

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube config view`       | Display the Minikube config.                              |
| `minikube config set`        | Set a value in the Minikube config.                       |
| `minikube config unset`      | Unset a value in the Minikube config.                     |

## Minikube Addons

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube addons list`       | List all available addons.                                |
| `minikube addons enable`     | Enable an addon.                                          |
| `minikube addons disable`    | Disable an addon.                                         |

## Minikube Dashboard

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube dashboard`         | Open the Kubernetes dashboard in a web browser.           |

## Minikube Service Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube service`           | Access a service in the Minikube cluster.                 |
| `minikube service list`      | List the URLs for services in your local Kubernetes cluster. |

## Minikube Environment

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube docker-env`        | Configure environment to use Minikube's Docker daemon.    |
| `minikube podman-env`        | Configure environment to use Minikube's Podman service.   |

## Minikube SSH

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube ssh`               | Log into or run a command on a Minikube node with SSH.    |

## Minikube Mount

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube mount`             | Mount a local directory into the Minikube cluster.        |

## Minikube Tunnel

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube tunnel`            | Create a network tunnel to access Kubernetes services.    |

## Minikube Version and Update

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube version`           | Show the Minikube version information.                    |
| `minikube update-check`      | Check for updates to Minikube.                            |
| `minikube update-context`    | Update kubeconfig to use Minikube cluster.                |

## Miscellaneous

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `minikube cache add`         | Add an image to local cache.                              |
| `minikube cache delete`      | Delete an image from the cache.                           |
| `minikube cache list`        | List all images in the cache.                             |
| `minikube completion`        | Generate shell completion for Minikube commands.          |
| `minikube options`           | Show a list of global command-line options (applies to all commands). |

These commands form the basic toolkit for managing a local Kubernetes cluster using Minikube.
