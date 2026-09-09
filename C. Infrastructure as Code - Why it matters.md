# Infrastructure as Code: Why It Matters

## What Is Infrastructure as Code?

Infrastructure as code (IaC) means defining infrastructure in machine-readable files instead of creating every resource manually through a web console. The files can be reviewed, tested, versioned, and executed consistently.

## Why Teams Use IaC

### Repeatability

The same configuration can create similar environments for development, testing, and production. This reduces differences caused by manual setup.

### Version Control

Infrastructure changes can be committed with a clear history. Pull requests make it possible to review what will change before it is applied.

### Faster Recovery

When infrastructure is documented as code, a damaged or temporary environment can be recreated more reliably. Recovery still depends on backups for data and on correct external dependencies.

### Reduced Configuration Drift

Manual changes can make real infrastructure differ from the intended design. IaC tools compare the declared configuration with the current state and expose unexpected differences.

### Standardization

Modules and shared conventions can enforce naming, tags, networking rules, encryption, and access patterns across projects.

### Automation and Auditability

CI/CD pipelines can run formatting, validation, security checks, plans, approvals, and applies. The resulting plan and commit history provide an audit trail.

## Limitations and Responsibilities

IaC is not automatically safe. Teams must still:

- Protect state files because they may contain sensitive values.
- Review plans for destructive changes and data-loss risk.
- Manage credentials with least privilege.
- Separate environments and control who can apply changes.
- Back up important data independently of infrastructure code.
- Pin tool and provider versions for predictable behavior.

## Terraform's Role

Terraform is one IaC implementation. It is especially useful for provisioning cloud resources and managing dependencies between them. Application deployment, server configuration, secrets management, and monitoring may require additional tools.
