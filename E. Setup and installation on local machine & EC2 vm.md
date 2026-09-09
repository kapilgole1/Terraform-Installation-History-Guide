# Terraform Setup and Installation for Beginners

This guide shows how to install Terraform and run a small test. The test creates a local text file, so it does not need an AWS account.

## Before You Start

You need:

- A Windows, macOS, or Linux computer, or an AWS EC2 Linux server
- Internet access
- PowerShell or a terminal

## Step 1: Install Terraform

### Windows

Open PowerShell as a normal user and run:

```powershell
winget install Hashicorp.Terraform
```

Close and reopen PowerShell, then check the installation:

```powershell
terraform version
```

### macOS

If Homebrew is installed, run:

```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
terraform version
```

### Ubuntu or EC2 Linux

Install Terraform by following HashiCorp's current Linux installation instructions for your operating system. Then run:

```bash
terraform version
```

The Linux package commands can change, so use the current official instructions instead of copying old repository keys.

## Step 2: Create a Test Folder

Run these commands:

```bash
mkdir terraform-demo
cd terraform-demo
```

Create a file named `main.tf` and add:

```hcl
resource "local_file" "example" {
  filename = "${path.module}/example.txt"
  content  = "Hello from Terraform"
}
```

## Step 3: Run Terraform

Run each command in order:

```bash
terraform init
terraform plan
terraform apply
```

When Terraform asks for confirmation, type `yes`. Terraform will create `example.txt` in the test folder.

## Step 4: Remove the Test Resource

When you finish testing, run:

```bash
terraform destroy
```

Type `yes` to remove the file managed by Terraform.

## Using Terraform on an EC2 Instance

1. Create an EC2 instance with Amazon Linux or Ubuntu.
2. Connect to it with SSH or AWS Systems Manager.
3. Install Terraform using the current official Linux instructions.
4. Run `terraform version` to check it.

For AWS resources, attach an IAM role to the EC2 instance. Give the role only the permissions Terraform needs. Do not save AWS access keys in Terraform files.

## Important Files

Terraform may create a `.terraform` folder and state files. Do not commit these files or any passwords and access keys to Git. For team projects, use a protected remote backend for the state.
