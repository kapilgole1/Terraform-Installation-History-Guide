# Terraform Compared with Other Tools

## Terraform vs Ansible

Terraform and Ansible can both automate infrastructure, but they solve different problems.

| Area | Terraform | Ansible |
| --- | --- | --- |
| Main purpose | Provision and manage infrastructure | Configure operating systems and deploy applications |
| Approach | Declarative: describe the desired state | Usually procedural: define the steps to perform |
| State | Stores resource state in a state file or remote backend | Does not normally keep an infrastructure state file |
| Typical resources | VPCs, networks, databases, instances, DNS, SaaS services | Packages, files, services, users, application configuration |
| Best use | Creating, changing, and destroying infrastructure consistently | Configuring machines after they exist |

They are often used together: Terraform creates the infrastructure, and Ansible configures the operating system and application on it.

## Terraform vs AWS CloudFormation

| Area | Terraform | AWS CloudFormation |
| --- | --- | --- |
| Cloud support | Multi-cloud and many third-party providers | Primarily AWS |
| Configuration | HCL, with JSON also supported | YAML or JSON |
| State management | Terraform state managed locally or in a remote backend | AWS manages stack state as part of the stack |
| Portability | Useful when an organization uses multiple platforms | Strong integration with AWS services |
| Ecosystem | Terraform providers and modules | AWS resources, templates, and CloudFormation modules |

Choose Terraform when multi-cloud support, a common workflow, or a broad provider ecosystem matters. Choose CloudFormation when the environment is AWS-only and deep native AWS integration is the priority.

## Key Decision

Terraform is an infrastructure provisioning tool, not a replacement for every automation tool. A practical workflow may use Terraform for infrastructure, Ansible for server configuration, and a CI/CD system for application releases.