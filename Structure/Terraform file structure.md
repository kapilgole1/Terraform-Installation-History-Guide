# Example Terraform Project Structure

A small Terraform project can look like this:

```text
terraform-project/
├── versions.tf
├── provider.tf
├── main.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars.example
├── .gitignore
└── README.md
```

## Simple Project

For a first practice project, you only need one file:

```text
terraform-project/
└── main.tf
```

As the project grows, split the configuration into files with clear purposes. Keep related files in the same folder when they belong to the same environment.

## Important Rule

Run Terraform commands from the folder that contains the `.tf` files:

```bash
terraform init
terraform plan
```

Do not store passwords, access keys, or local state files in a public Git repository.
