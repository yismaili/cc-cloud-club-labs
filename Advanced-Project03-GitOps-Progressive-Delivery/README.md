# Advanced Project 03 - GitOps and Progressive Delivery

## Project Profile

- Level: Intermediate to advanced
- Suggested duration: 6-8 weeks
- Main tools: Argo CD, Argo Rollouts, Helm or Kustomize, Prometheus, Kubernetes

## Subject

Create a GitOps delivery platform where Git is the declared source of cluster state. Release applications through canary or blue-green deployments and automatically stop or roll back unhealthy versions using real service metrics.

## Prerequisites

- Strong Git, Docker and Kubernetes fundamentals.
- Basic CI/CD and monitoring experience.
- A reproducible Kubernetes cluster.

## Learning Goals

- Separate continuous integration from continuous delivery.
- Manage application and infrastructure configuration through Git.
- Detect and repair cluster drift.
- Promote releases using canary or blue-green strategies.
- Use metrics to make automated release decisions.
- Restrict GitOps permissions by team and namespace.

## Mandatory Milestones

1. Create separate repositories or clearly separated paths for application source and environment configuration.
2. Install Argo CD and create restricted projects for development and staging.
3. Package the application with Helm or Kustomize.
4. Deploy development and staging from Git without manual `kubectl apply` changes.
5. Enable automated sync, health checks and drift detection in development.
6. Require review or approval before staging promotion.
7. Install Argo Rollouts and implement one canary or blue-green strategy.
8. Use Prometheus analysis to check error rate or latency during promotion.
9. Release a broken version and demonstrate a stopped rollout or rollback.
10. Apply RBAC, NetworkPolicies and safe secret handling.

## Deliverables

- GitOps repository layout.
- Argo CD projects and application definitions.
- Helm chart or Kustomize overlays.
- Progressive-delivery and analysis configuration.
- Security model and promotion workflow diagram.
- Drift, failed-release and rollback demonstrations.

## Validation

- Manual changes are detected and corrected or reported according to policy.
- Development and staging use different controlled values.
- A release is promoted in measurable steps.
- A bad release does not receive full production-like traffic.
- Argo CD cannot manage unrelated namespaces or unrestricted cluster resources.

## Rules

- Secrets must not appear as plaintext in Git.
- Direct cluster changes are allowed only for documented bootstrap or emergency recovery.
- Automatic promotion must depend on meaningful application signals, not only Pod status.
