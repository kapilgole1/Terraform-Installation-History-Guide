# Terraform Compared with Other Tools

Terraform, Ansible, and AWS CloudFormation all automate work, but they are designed for different jobs.

## Terraform and Ansible

| Terraform | Ansible |
| --- | --- |
| Creates and manages infrastructure | Configures existing machines |
| Manages networks, servers, databases, and DNS | Installs packages and configures files and services |
| Uses a state file | Does not normally manage infrastructure with a state file |
| Describes the desired result | Usually runs a list of tasks |

They can be used together. Terraform creates a server, and Ansible installs and configures the software on it.

## Terraform and CloudFormation

| Terraform | AWS CloudFormation |
| --- | --- |
| Works with AWS and many other platforms | Made mainly for AWS |
| Uses HCL files | Uses YAML or JSON files |
| Uses Terraform providers | Uses AWS services directly |
| Good for multi-cloud projects | Good for AWS-only projects |

## Which One Should You Use?

- Use Terraform when you want one workflow for several platforms.
- Use Ansible when the machines already exist and need software or configuration.
- Use CloudFormation when your work is only in AWS and native AWS integration is most important.

Many teams use Terraform and Ansible together instead of choosing only one.