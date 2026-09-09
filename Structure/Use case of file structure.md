# When to Use Separate Terraform Files

## Start with One File

Use one `main.tf` file when you are learning Terraform or testing a small example. It is easier to see the complete configuration in one place.

## Split Files When the Project Grows

Use separate files when the configuration becomes difficult to read. A common split is:

1. Put version requirements in `versions.tf`.
2. Put provider settings in `provider.tf`.
3. Put resources in `main.tf`.
4. Put changeable values in `variables.tf`.
5. Put useful results in `outputs.tf`.

This makes it easier to find a setting without creating a new Terraform project for every file.

## Use Different Folders for Different Environments

Keep development and production configurations separate when they need different state or permissions:

```text
terraform-project/
├── dev/
│   ├── main.tf
│   └── variables.tf
└── prod/
	├── main.tf
	└── variables.tf
```

Run Terraform in the environment folder you want to manage. Each folder should use its own state and credentials.

## Use Modules for Repeated Infrastructure

Use a module when the same group of resources is needed in more than one place. For example, a network module can be used for development and production with different variable values.

Do not create many small files just for the sake of having more files. Organize the project when it improves understanding and maintenance.
