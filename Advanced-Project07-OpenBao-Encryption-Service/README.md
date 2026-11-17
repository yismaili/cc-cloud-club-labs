# Advanced Project 07 - OpenBao Encryption Service

## Project Profile

- Level: Advanced security
- Suggested duration: 8-10 weeks
- Main tools: OpenBao, Kubernetes, Transit secrets engine, REST or gRPC, Prometheus, Grafana

## Subject

Build a Kubernetes-native encryption service around OpenBao Transit. Applications send plaintext to an authenticated API and receive ciphertext without receiving or managing the encryption keys themselves.

The service must enforce per-application access policies, protect plaintext in transit and memory, and produce useful audit evidence without logging sensitive data.

## Prerequisites

- Kubernetes, TLS, authentication and API development.
- Basic cryptography and secrets-management concepts.
- Experience with ServiceAccounts, RBAC and NetworkPolicies.

## Learning Goals

- Understand encryption as a service and centralized key lifecycle management.
- Use the Transit engine without exposing raw encryption keys.
- Authenticate Kubernetes workloads through workload identity.
- Design least-privilege policies for applications and namespaces.
- Build a secure API and threat model.
- Monitor sensitive operations without recording plaintext.

## Mandatory Milestones

1. Deploy OpenBao with persistent storage and TLS in a dedicated namespace.
2. Document initialization, unseal and recovery procedures for the lab.
3. Enable the Transit secrets engine.
4. Configure Kubernetes authentication with short-lived identities.
5. Create separate policies for at least two sample applications.
6. Build an authenticated REST or gRPC API for encrypt, decrypt, rotate and metadata operations.
7. Ensure the API never returns raw keys and never logs plaintext or decrypted values.
8. Add input limits, timeouts, error handling and rate limiting.
9. Restrict traffic with Kubernetes RBAC and NetworkPolicies.
10. Enable audit logging and metrics for success, denial, latency and availability.
11. Rotate a key and prove that authorized old ciphertext remains usable.

## Deliverables

- OpenBao and application deployment configuration.
- API source, tests and interface documentation.
- Authentication and policy configuration.
- Threat model and data-flow diagram.
- Audit, monitoring and incident-response documentation.
- Demonstrations of authorized use, denied use and key rotation.

## Validation

- Application A cannot use Application B's encryption key.
- A workload without the correct identity is denied.
- Plaintext is returned only through authorized decrypt responses over TLS and is never logged.
- Key rotation creates a new version without silently losing authorized old data.
- Audit events identify the caller and action without exposing secret content.
- The team can restore the lab using its documented recovery procedure.

## Security Rules

- Use only synthetic test data.
- Never expose the OpenBao root token to applications.
- Do not run development mode for the final demonstration.
- Do not invent custom cryptographic algorithms.
- A key-list operation may return approved metadata only, never key material.
