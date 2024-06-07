# Common Kubernetes Commands

This document provides a list of common Kubernetes commands along with brief descriptions.

Kubernetes provides a command line tool for communicating with a [Kubernetes](https://kubernetes.io/docs/reference/kubectl/) cluster's control plane, using the Kubernetes API.

This page contains a list of commonly used [kubectl](https://kubernetes.io/docs/reference/kubectl/quick-reference/) commands and flags.

kubectl controls the Kubernetes cluster manager.

Find more information in [Command line tool](https://kubernetes.io/docs/reference/kubectl/kubectl/) (kubectl).

## Cluster Management

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl cluster-info`      | Display cluster information.                              |
| `kubectl get nodes`         | List all nodes in the cluster.                            |
| `kubectl describe node`     | Show detailed information about a specific node.          |
| `kubectl cordon`            | Mark node as unschedulable.                               |
| `kubectl uncordon`          | Mark node as schedulable.                                 |
| `kubectl drain`             | Drain a node in preparation for maintenance.              |
| `kubectl taint`             | Taint a node to prevent it from accepting any pods that do not tolerate the taint. |

## Pod Management

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl get pods`          | List all pods in the namespace.                           |
| `kubectl get pods -A`       | List all pods across all namespaces.                      |
| `kubectl describe pod`      | Show detailed information about a specific pod.           |
| `kubectl logs`              | Print the logs for a container in a pod.                  |
| `kubectl exec`              | Execute a command in a container.                         |
| `kubectl port-forward`      | Forward one or more local ports to a pod.                 |
| `kubectl delete pod`        | Delete a pod.                                             |

## Service Management

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl get svc`           | List all services in the namespace.                       |
| `kubectl describe svc`      | Show detailed information about a specific service.       |
| `kubectl expose`            | Expose a resource as a new Kubernetes service.            |

## Deployment Management

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl get deployments`   | List all deployments in the namespace.                    |
| `kubectl describe deployment`| Show detailed information about a specific deployment.   |
| `kubectl create deployment` | Create a deployment.                                      |
| `kubectl scale`             | Scale a deployment.                                       |
| `kubectl set image`         | Update the image of a deployment.                         |
| `kubectl rollout status`    | Show the status of the rollout.                           |
| `kubectl rollout history`   | Show the rollout history.                                 |
| `kubectl rollout undo`      | Roll back to a previous deployment revision.              |

## Namespace Management

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl get namespaces`    | List all namespaces.                                      |
| `kubectl create namespace`  | Create a new namespace.                                   |
| `kubectl delete namespace`  | Delete a namespace.                                       |

## ConfigMap and Secret Management

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl get configmaps`    | List all ConfigMaps in the namespace.                     |
| `kubectl describe configmap`| Show detailed information about a specific ConfigMap.     |
| `kubectl create configmap`  | Create a ConfigMap.                                       |
| `kubectl delete configmap`  | Delete a ConfigMap.                                       |
| `kubectl get secrets`       | List all secrets in the namespace.                        |
| `kubectl describe secret`   | Show detailed information about a specific secret.        |
| `kubectl create secret`     | Create a secret.                                          |
| `kubectl delete secret`     | Delete a secret.                                          |

## Persistent Volume and Persistent Volume Claim Management

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl get pv`            | List all persistent volumes.                              |
| `kubectl get pvc`           | List all persistent volume claims in the namespace.       |
| `kubectl describe pv`       | Show detailed information about a specific persistent volume. |
| `kubectl describe pvc`      | Show detailed information about a specific persistent volume claim. |
| `kubectl delete pv`         | Delete a persistent volume.                               |
| `kubectl delete pvc`        | Delete a persistent volume claim.                         |

## Role-Based Access Control (RBAC) Management

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl get roles`         | List all roles in the namespace.                          |
| `kubectl get rolebindings`  | List all role bindings in the namespace.                  |
| `kubectl get clusterroles`  | List all cluster roles.                                   |
| `kubectl get clusterrolebindings`| List all cluster role bindings.                     |
| `kubectl describe role`     | Show detailed information about a specific role.          |
| `kubectl describe rolebinding`| Show detailed information about a specific role binding.|
| `kubectl describe clusterrole`| Show detailed information about a specific cluster role.|
| `kubectl describe clusterrolebinding`| Show detailed information about a specific cluster role binding. |

## Miscellaneous

| Command                     | Description                                               |
|-----------------------------|-----------------------------------------------------------|
| `kubectl apply`             | Apply a configuration to a resource by filename or stdin. |
| `kubectl create`            | Create a resource from a file or from stdin.              |
| `kubectl delete`            | Delete resources by filenames, stdin, resources and names, or by resources and label selector. |
| `kubectl edit`              | Edit a resource on the server.                            |
| `kubectl get events`        | List events in the namespace.                             |
| `kubectl label`             | Add or update labels on resources.                        |
| `kubectl annotate`          | Add or update annotations on resources.                   |
| `kubectl config view`       | Display merged kubeconfig settings.                       |
| `kubectl config use-context`| Set the current context in your kubeconfig.               |
| `kubectl version`           | Print the client and server version information.          |
