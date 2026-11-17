# Advanced Project 04 - Mini Kubernetes PaaS

## Project Profile

- Level: Advanced capstone
- Suggested duration: 10-12 weeks
- Main tools: Kubernetes, Helm, container registry, Python or Go, Traefik, cert-manager

## Subject

Build a small internal platform where an authenticated club user selects an approved Git repository and receives a deployed application with a stable URL. The platform should hide routine Kubernetes details without hiding security, limits or deployment status.

## Prerequisites

- Strong Kubernetes, Docker, networking and CI/CD skills.
- Basic API or CLI development.
- Experience with Helm and container registries.

## Learning Goals

- Design a safe developer-facing abstraction over Kubernetes.
- Build and track container artifacts.
- Generate repeatable application releases.
- Isolate teams with namespaces, quotas and policies.
- Report deployment status and history to users.
- Understand the security risks of building user-provided code.

## Mandatory Milestones

1. Create a Kubernetes cluster with Traefik as the ingress controller, cert-manager for TLS certificates and a container registry. Record the component versions and configuration.
2. Build an authenticated CLI or API for platform operations.
3. Accept only instructor-approved repositories during the project.
4. Build application images in an isolated job with resource and time limits.
5. Scan built images before deployment.
6. Create a namespace, ServiceAccount, quota and NetworkPolicy for each team.
7. Deploy applications using a controlled Helm chart or template.
8. Assign a predictable test domain and HTTPS endpoint using a Kubernetes Ingress with `spec.ingressClassName: traefik`. Reference a cert-manager-managed TLS Secret in the application namespace.
9. Store deployment history, image version and current health.
10. Provide logs and status without granting users cluster-admin access.
11. Implement delete and cleanup operations.

## Deliverables

- Platform API or CLI source and tests.
- Cluster, registry, Traefik and cert-manager configuration.
- Build and deployment templates.
- Authentication, authorization and threat-model documents.
- User and operator documentation.
- Demonstrations for deploy, update, failure, rollback and delete.

## Validation

- An authorized user can deploy an approved sample repository.
- An unauthorized user cannot operate another team's application.
- Builds must have resource and time limits and must not have unrestricted host access.
- A deployment receives an HTTPS URL through Traefik, presents a certificate trusted by the test client, and reports health and version.
- Deleting an application removes its resources without affecting other teams.

## Scope and Safety Rules

- Do not execute arbitrary public code on shared club infrastructure.
- With K3s or K3d, reuse the bundled Traefik installation when enabled; do not install a second controller for the same IngressClass.
- For local test domains, document the lab certificate authority and how clients trust it.
- A web dashboard is optional; a good CLI or API is enough.
- Multi-cluster support and full self-service DNS are bonuses.
- Clearly state that this is a learning platform, not a production public hosting service.

## References

- [Traefik Kubernetes Ingress configuration](https://doc.traefik.io/traefik/reference/routing-configuration/kubernetes/ingress/).
- [cert-manager certificates for Ingress](https://cert-manager.io/docs/usage/ingress/).
