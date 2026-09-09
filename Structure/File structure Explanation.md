# Terraform File Structure Explained

Terraform does not require specific file names. It reads every `.tf` file in the current folder. The names below are common because they make a project easier for people to understand.

| File | Purpose |
| --- | --- |
| `versions.tf` | Sets the required Terraform and provider versions. |
| `provider.tf` | Configures the cloud or service provider. |
| `main.tf` | Holds the main resources for the project. |
| `variables.tf` | Declares values that can change between environments. |
| `terraform.tfvars` | Provides values for variables. Do not commit secrets in this file. |
| `outputs.tf` | Shows useful information after Terraform creates resources. |
| `data.tf` | Reads information that already exists. |
| `locals.tf` | Stores calculated or repeated values used by the configuration. |
| `README.md` | Explains how to use the project. |
| `.gitignore` | Prevents local files and secrets from being committed. |

## Example

`variables.tf`:

```hcl
variable "environment" {
	type    = string
	default = "dev"
}
```

`main.tf`:

```hcl
resource "local_file" "example" {
	filename = "${path.module}/${var.environment}.txt"
	content  = "Terraform example"
}
```

Terraform loads both files together, so `main.tf` can use the variable declared in `variables.tf`.
