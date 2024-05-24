# Common Helm Commands

This document provides a list of common Helm commands along with brief descriptions.

Here you’ll find the list of CLI commands for [Helm](https://helm.sh/docs/helm/), with help info on their usage.

Helm [cheatsheet](https://helm.sh/docs/intro/cheatsheet/) featuring all the necessary commands required to manage an application through Helm.
## Helm Basics

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm create`                | Create a new Helm chart.                                  |
| `helm lint`                  | Run linting on a chart to check for errors.               |
| `helm package`               | Package a chart directory into a chart archive.           |
| `helm search hub`            | Search for charts in the Helm Hub.                        |
| `helm search repo`           | Search for charts in the Helm repository.                 |
| `helm show all`              | Show details of a chart.                                  |
| `helm show chart`            | Show the chart’s definition.                              |
| `helm show values`           | Show the chart’s values.                                  |
| `helm show readme`           | Show the chart’s README.                                  |
| `helm show hooks`            | Show the chart’s hooks.                                   |

## Helm Repositories

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm repo add`              | Add a Helm repository.                                    |
| `helm repo list`             | List all Helm repositories.                               |
| `helm repo update`           | Update information on available charts from the chart repositories. |
| `helm repo remove`           | Remove one or more Helm repositories.                     |

## Helm Chart Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm install`               | Install a Helm chart.                                     |
| `helm upgrade`               | Upgrade a release to a new chart or version.              |
| `helm rollback`              | Roll back a release to a previous revision.               |
| `helm uninstall`             | Uninstall a release.                                      |
| `helm list`                  | List all Helm releases.                                   |
| `helm status`                | Display the status of a named release.                    |
| `helm history`               | Fetch release history.                                    |

## Helm Release Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm get`                   | Download information about a release.                     |
| `helm get all`               | Download all information for a named release.             |
| `helm get hooks`             | Download all hooks for a named release.                   |
| `helm get manifest`          | Download the manifest for a named release.                |
| `helm get notes`             | Download the notes for a named release.                   |
| `helm get values`            | Download the values file for a named release.             |

## Helm Environment

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm env`                   | Display Helm environment information.                     |

## Helm Template Rendering

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm template`              | Render templates locally and display the output.          |

## Helm Dependency Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm dependency list`       | List the dependencies for a chart.                        |
| `helm dependency update`     | Update the dependencies for a chart.                      |
| `helm dependency build`      | Rebuild the dependencies for a chart.                     |

## Helm Plugins

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm plugin list`           | List installed Helm plugins.                              |
| `helm plugin install`        | Install a Helm plugin from a URL.                         |
| `helm plugin update`         | Update a Helm plugin.                                     |
| `helm plugin remove`         | Remove a Helm plugin.                                     |

## Helm Completion

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm completion bash`       | Generate Bash autocompletions script.                     |
| `helm completion zsh`        | Generate Zsh autocompletions script.                      |

## Helm Miscellaneous

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `helm version`               | Display the Helm client version information.              |
| `helm help`                  | Provide help for Helm commands.                           |

These commands form the basic toolkit for managing Kubernetes applications using Helm.
