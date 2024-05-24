# Common Terraform Commands

This document provides a list of common Terraform commands along with brief descriptions.

Terraform is an infrastructure as code tool that lets you build, change, and version infrastructure safely and efficiently. This includes low-level components like compute instances, storage, and networking, as well as high-level components like DNS entries and SaaS features.

The command line interface to Terraform is the [terraform command](https://developer.hashicorp.com/terraform/cli/commands), which accepts a variety of subcommands such as terraform init or terraform plan

## Initialization

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform init`             | Initialize a new or existing Terraform configuration.     |

## Configuration Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform validate`         | Validate the configuration files in a directory.          |
| `terraform fmt`              | Format Terraform configuration files to a canonical format. |

## Planning and Execution

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform plan`             | Generate and show an execution plan.                      |
| `terraform apply`            | Apply the changes required to reach the desired state of the configuration. |
| `terraform destroy`          | Destroy Terraform-managed infrastructure.                 |

## Resource Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform refresh`          | Update the state file with the real-world resources.      |
| `terraform import`           | Import existing infrastructure into your Terraform state. |
| `terraform taint`            | Mark a resource for recreation.                           |
| `terraform untaint`          | Remove the 'tainted' state from a resource.               |

## State Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform state list`       | List resources in the state file.                         |
| `terraform state show`       | Show detailed state data for a resource.                  |
| `terraform state pull`       | Pull the current state and output it to stdout.           |
| `terraform state push`       | Update remote state from a local state file.              |
| `terraform state rm`         | Remove instances from the state file.                     |
| `terraform state mv`         | Move an item in the state file.                           |

## Output Management

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform output`           | Show the outputs of your Terraform configuration.         |

## Modules

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform get`              | Download and update modules mentioned in the configuration. |
| `terraform module`           | Interact with Terraform modules.                          |

## Providers

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform providers`        | Show the providers required for the configuration.        |

## Workspaces

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform workspace list`   | List all workspaces.                                      |
| `terraform workspace new`    | Create a new workspace.                                   |
| `terraform workspace select` | Switch to another workspace.                              |
| `terraform workspace delete` | Delete a workspace.                                       |
| `terraform workspace show`   | Show the current workspace.                               |

## Miscellaneous

| Command                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `terraform version`          | Show the current Terraform version.                       |
| `terraform providers`        | Show providers required for the configuration.            |
| `terraform debug`            | Enable debugging output for Terraform commands.           |
| `terraform graph`            | Generate a visual representation of the configuration.    |
| `terraform login`            | Obtain and save credentials for Terraform Cloud or Terraform Enterprise. |
| `terraform logout`           | Remove locally-stored credentials.                        |
| `terraform force-unlock`     | Manually unlock the state for a configuration.            |

These commands form the basic toolkit for managing infrastructure as code using Terraform.
