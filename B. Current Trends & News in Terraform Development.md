# Important Terraform Practices Today

These are common practices used by Terraform teams. Always check the documentation for the Terraform version you are using.

## Shared State

When several people work on the same project, state is usually stored in a remote backend such as HCP Terraform or cloud storage. This gives the team one shared state and can prevent two people from changing it at the same time.

Remember:

- Do not commit state files to Git.
- Protect state because it may contain sensitive values.
- Keep development and production state separate.

## Modules

Teams use modules to reuse common setups, such as a network or a database. A good module has clear inputs, useful outputs, and simple documentation.

## Security Checks

Before applying changes, teams check for public resources, missing encryption, weak permissions, and missing tags. Passwords and access keys should come from a secret manager or protected environment variables.

## Testing and Review

Terraform changes are often reviewed in a pull request. A basic check is:

```bash
terraform fmt
terraform validate
terraform plan
```

The plan should be reviewed before anyone runs `terraform apply`.

## Terraform and OpenTofu

OpenTofu is a separate open-source project that came from the Terraform ecosystem. The tools are similar, but they have separate releases. Choose one tool for a project and use compatible versions of its CLI, providers, and modules.

## Drift and Cost

Teams regularly check whether real infrastructure still matches the code. They also remove unused resources and review the cost of planned changes.
