# Terraform Setup and Installation

## Prerequisites

- A supported 64-bit operating system
- Internet access for downloading Terraform and providers
- A terminal or PowerShell
- Cloud credentials only when you plan to manage cloud resources

Do not put cloud access keys directly in Terraform files. Use the cloud provider's supported credential configuration, environment variables, or an approved credentials manager.

## Install on a Local Machine

### Windows

Using Chocolatey:

```powershell
choco install terraform
```

Using winget:

```powershell
winget install Hashicorp.Terraform
```

After installation, open a new PowerShell window and verify it:

```powershell
terraform version
```

If the command is not found, restart the terminal and check that Terraform's installation directory is in `PATH`.

### macOS

```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
terraform version
```

### Ubuntu or Debian

Use HashiCorp's official package repository or download the appropriate release from the official Terraform website. After installation, verify it with:

```bash
terraform version
```

Use the official installation instructions for the current repository key and package commands because those details can change.

## Create and Initialize a Test Directory

Create a separate working directory for each small experiment:

```bash
mkdir terraform-demo
cd terraform-demo
```

Create `main.tf`:

```hcl
terraform {
	required_version = ">= 1.6.0"
}

resource "local_file" "example" {
	filename = "${path.module}/example.txt"
	content  = "Managed by Terraform"
}
```

Run:

```bash
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply
```

Type `yes` only after reviewing the plan. To remove the test resource later:

```bash
terraform destroy
```

The `local` provider may be downloaded during `terraform init`. For a cloud example, configure the provider and credentials according to that cloud's official guidance before running a plan.

## Install on an AWS EC2 Instance

1. Launch an EC2 instance using a supported Linux distribution.
2. Connect through SSH or AWS Systems Manager.
3. Update the package metadata.

For Amazon Linux:

```bash
sudo dnf update -y
```

For Ubuntu:

```bash
sudo apt update
```

4. Install Terraform using HashiCorp's official Linux instructions for the selected distribution.
5. Verify the installation:

```bash
terraform version
```

## EC2 Credential Guidance

The preferred option is to attach an IAM role to the instance with only the permissions Terraform needs. Avoid storing long-lived AWS access keys in shell history, source files, or the Terraform directory.

## Recommended Project Files

```text
terraform-demo/
├── main.tf
├── variables.tf
├── outputs.tf
├── versions.tf
└── .gitignore
```

At minimum, add `.terraform/` and local state files to `.gitignore` for projects using a remote backend. Never commit secrets or state without reviewing its contents and the repository's security requirements.
