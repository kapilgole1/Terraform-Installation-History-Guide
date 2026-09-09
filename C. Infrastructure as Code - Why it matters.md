# Why Infrastructure as Code Matters

## What Is It?

Infrastructure as code, or IaC, means writing infrastructure settings in files instead of creating everything manually in a web console.

Terraform is one tool used for IaC.

## Main Benefits

### Same Setup Every Time

The same code can create similar development, test, and production environments. This reduces mistakes caused by manual work.

### Easy Review

Infrastructure changes can be saved in Git. Other people can review the change before it is used.

### Easier Recovery

If an environment is lost, the code can help create it again. Important data still needs separate backups.

### Less Configuration Drift

Configuration drift happens when the real infrastructure becomes different from the code. Terraform can show these differences in a plan.

### Automation

A CI/CD system can check the code and run Terraform for approved changes.

## Important Safety Rules

- Review `terraform plan` before applying changes.
- Keep state files private because they may contain sensitive information.
- Never put passwords or access keys in `.tf` files.
- Give Terraform only the permissions it needs.
- Keep backups for important data.

## What Terraform Does Not Do

Terraform creates and manages infrastructure. You may still need other tools for server configuration, application deployment, secrets, logging, and monitoring.
