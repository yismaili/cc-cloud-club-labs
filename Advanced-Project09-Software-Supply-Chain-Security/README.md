# Advanced Project 09 - Software Supply Chain Security

## Project Profile

- Level: Advanced security
- Suggested duration: 6-8 weeks
- Main tools: GitHub Actions, Syft, Grype or Trivy, Cosign, OCI registry, Kyverno, Kubernetes

## Subject

Secure the path from source code to a running Kubernetes workload. Generate software bills of materials, scan dependencies and images, sign approved artifacts, create provenance, and prevent untrusted images from entering the cluster.

## Prerequisites

- CI/CD, Docker, registries and Kubernetes.
- Basic public-key, identity and vulnerability-management concepts.
- A sample application with automated tests.

## Learning Goals

- Identify risks across source, build, registry and deployment stages.
- Generate and store an SBOM for each release.
- Sign images and verify their identity and digest.
- Use short-lived CI identity for keyless signing where supported.
- Enforce deployment policy without relying on mutable tags.
- Respond to a vulnerable dependency or leaked secret safely.

## Mandatory Milestones

1. Create a pipeline with linting, tests and secret scanning.
2. Build an image from a pinned base and tag it with an immutable identifier.
3. Scan application dependencies and the final container image.
4. Define a documented vulnerability policy with severity and exception rules.
5. Generate an SBOM and attach or publish it with the image.
6. Sign the image and create build provenance or an attestation.
7. Verify signatures and identity before deployment.
8. Configure Kyverno to reject unsigned, untrusted or mutable-tag images.
9. Introduce an approved vulnerable dependency and show the pipeline response.
10. Patch, rebuild, sign and deploy the corrected artifact.

## Deliverables

- Secure CI/CD workflows.
- Scanner, SBOM, signing and policy configuration.
- Kubernetes verification policies and tests.
- Threat model for the software delivery chain.
- Vulnerability exception process.
- Evidence for blocked and successful deployments.

## Validation

- An unsigned image is rejected.
- A signature from an unapproved identity is rejected.
- The deployed digest matches the signed and scanned digest.
- Every release has an SBOM that can be retrieved.
- A policy failure prevents promotion.
- The team can trace a running workload back to source commit and build workflow.

## Security Rules

- Never commit signing private keys or registry credentials.
- Prefer short-lived identity over static CI credentials.
- Do not mark every vulnerability as ignored to make the build pass.
- Document accepted risk, expiry and owner for every exception.
