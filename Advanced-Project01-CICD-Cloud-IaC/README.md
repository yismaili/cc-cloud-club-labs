# Advanced Project 01 - CI/CD with Cloud Infrastructure as Code

## Project Profile

- Level: Intermediate to advanced
- Suggested duration: 8-10 weeks
- Main tools: Terraform, GitHub Actions, Docker, AWS or GCP

## Subject

Build an end-to-end delivery platform for a small web application. Terraform creates the cloud infrastructure, and a CI/CD pipeline tests, packages and releases immutable application versions to development and staging environments.

Production is optional and may only be used with instructor approval and a strict budget.

## Prerequisites

- Linux, Git, Docker and networking fundamentals.
- Basic Terraform and CI/CD experience.
- An instructor-approved cloud sandbox or education account.
- Completion of the beginner track or equivalent knowledge.

## Learning Goals

- Design reusable Terraform modules and environment configurations.
- Protect Terraform state with encryption, locking and access control.
- Build test, package, release and deployment pipeline stages.
- Use short-lived cloud authentication instead of stored access keys.
- Promote immutable artifacts between environments.
- Detect a failed release and roll back to a known artifact.

## Mandatory Milestones

1. Create a small application with at least two services and a health endpoint.
2. Create a network, public entry point, private application resources and private database using Terraform.
3. Separate development and staging state and variables.
4. Configure remote Terraform state with locking and encryption.
5. Authenticate GitHub Actions to the cloud using OIDC or another instructor-approved short-lived method.
6. Run formatting, linting, tests, Terraform validation and security checks in CI.
7. Build and push a Docker image tagged with a commit identifier and release version.
8. Deploy to development automatically after successful checks.
9. Promote the same image to staging through an approval gate.
10. Run post-deployment health checks and restore the previous image when validation fails.
11. Configure a cost budget, billing alert and complete cleanup workflow.

## Deliverables

- Application source and tests.
- Terraform modules and environment configuration.
- CI/CD workflow files.
- Architecture and pipeline diagrams.
- State, identity, secret and rollback design documents.
- Cost estimate and cleanup runbook.
- Evidence of one successful release and one blocked or rolled-back release.

## Validation

- No long-lived cloud credentials are committed or stored in workflow files.
- Pull requests cannot deploy before required checks pass.
- Development and staging use separate configuration and state.
- The same immutable image is promoted between environments.
- A failed health check stops promotion or triggers the documented rollback.
- `terraform destroy` removes all project resources selected for cleanup.

## Safety and Cost Rules

- Set an instructor-approved maximum budget before deployment.
- Use small resource sizes and short lab windows.
- Do not store personal or production data.
- Production deployment, public DNS and managed databases are optional when they create extra cost.
- The project fails if resources are left running without documentation.
