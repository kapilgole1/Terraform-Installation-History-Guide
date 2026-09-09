# What Is Terraform?

Terraform is a tool for creating and managing infrastructure with code. Infrastructure can include servers, networks, databases, storage, and DNS records.

Instead of clicking through a cloud console, you write what you want in a `.tf` file. Terraform then works out what must be created, changed, or removed.

Terraform files normally use HashiCorp Configuration Language, also called HCL. Providers connect Terraform to platforms such as AWS, Azure, Google Cloud, and Kubernetes.

## Basic Terraform Workflow

1. Write the desired infrastructure in a `.tf` file.
2. Run `terraform init` to prepare the folder.
3. Run `terraform plan` to preview changes.
4. Run `terraform apply` to make the changes.
5. Terraform saves information about the resources in a state file.

Example:

```hcl
resource "local_file" "example" {
	filename = "${path.module}/example.txt"
	content  = "Hello from Terraform"
}
```

## Short History

- Terraform was created by HashiCorp and released publicly in 2014.
- Its provider system allowed one tool to work with many platforms.
- The Terraform community created reusable modules and providers.
- Terraform 0.12 brought major improvements to the HCL language.
- In 2023, HashiCorp changed Terraform's license. OpenTofu was later created as a separate open-source project.

## In Simple Words

Terraform helps you describe infrastructure, review changes before making them, and repeat the same setup when needed.
