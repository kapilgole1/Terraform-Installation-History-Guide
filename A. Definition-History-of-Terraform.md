# Definition and History of Terraform

## Definition

Terraform is an infrastructure-as-code tool used to define, provision, update, and remove infrastructure through configuration files. It uses a declarative model: you describe the desired end state, and Terraform determines the actions required to reach that state.

Terraform configurations are commonly written in HashiCorp Configuration Language (HCL). Providers allow Terraform to communicate with platforms such as AWS, Azure, Google Cloud, Kubernetes, and many SaaS services.

## How Terraform Works

1. The configuration declares resources and their relationships.
2. `terraform init` installs the required providers and prepares the working directory.
3. `terraform plan` compares the configuration, state, and real infrastructure, then shows the proposed changes.
4. `terraform apply` performs the approved changes.
5. Terraform records resource identity and metadata in a state file so future plans can calculate changes.

Example:

```hcl
resource "aws_s3_bucket" "logs" {
	bucket = "example-logs-bucket"
}
```

The example describes the desired bucket. It does not contain a sequence of API calls for creating the bucket.

## Short History

- Terraform was created by HashiCorp and publicly introduced in 2014.
- Its provider architecture enabled one configuration workflow across multiple infrastructure platforms.
- The Terraform ecosystem grew through reusable modules, community providers, and remote state workflows.
- Terraform 0.12 introduced major improvements to the HCL language and expression system.
- Later releases added features such as improved dependency handling, testing capabilities, and stronger support for modern infrastructure workflows.
- In 2023, HashiCorp changed Terraform's license from the Mozilla Public License 2.0 to the Business Source License 1.1. OpenTofu was then created as a separate open-source fork.

## Why It Matters

Terraform makes infrastructure changes reviewable, repeatable, and version-controlled. It does not remove the need for design, security review, backups, or operational monitoring; it provides a consistent way to manage the infrastructure definition and its changes.
