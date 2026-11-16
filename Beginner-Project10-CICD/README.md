# Beginner Project 10 - CI/CD

## Subject

Test, package, release and safely roll back the application built during the track.

## Introduction

For a quick introduction to CI/CD, watch [CI/CD Explained in 5 Minutes](https://www.youtube.com/watch?v=ddDJxFnv-qs) before starting the project.

## Learning Goals

- Understand the difference between CI, continuous delivery and continuous deployment.
- Promote immutable container images.
- Protect pipeline secrets and stop failed releases.
- Roll back by reusing a known previous artifact.

## CI vs Continuous Delivery vs Continuous Deployment

- **CI (Continuous Integration):** every change is automatically built and tested.
- **Continuous Delivery:** every passing change produces a release-ready image, but a human approves or triggers the deploy.
- **Continuous Deployment:** every passing change is deployed automatically, with no manual step.

You must state which one your pipeline implements and why.

## Mandatory Work

**Pipeline**
- Reuse the application from Project 05 or Project 08.
- Create a GitHub Actions workflow (or instructor-approved equivalent).
- Run formatting, linting, tests and a secret/vulnerability scan (e.g. Gitleaks, Trivy).
- Build the Docker image only after all checks pass.
- Pull requests only validate; pushes to `main` and version tags publish.

**Artifacts**
- Tag the image with the Git commit SHA and a release version. Never use `latest`.
- Push the image to Docker Hub.
- Keep Docker Hub credentials in pipeline secret storage (use a Docker Hub access token, not your password), with least-privilege permissions.
- Pin third-party actions to a commit SHA.

**Release and rollback**
- Show the running version through a `/version` endpoint or label.
- Document how to roll back by reusing a previous image tag (no rebuild).

## Optional: Deployment

Deploying is not required. If you want to, choose based on need:

| Option | How it works | Best when |
| --- | --- | --- |
| **Plain VM** | Pipeline (or you) SSHes in and runs `docker pull` + `docker compose up -d` with the new image tag | Simple app, one server, small team |
| **Simple `kubectl`** | Pipeline runs `kubectl set image` or `kubectl apply`; rollback with `kubectl rollout undo` | You already have a cluster and want a direct push model |
| **GitOps** | Pipeline only updates the image tag in a Git config repo; Argo CD or Flux in the cluster applies it. Rollback = `git revert` | You want Git as the source of truth and no cluster credentials in CI |

If you deploy, add a health check after deploy and treat a failed check as a failed release.

## Deliverables

- Workflow files, tests and Docker build config.
- Release and rollback notes.

## Validation

- A failing test or scan blocks publication.
- Each successful commit produces a traceable, immutable image on Docker Hub.
- The running version can be identified.
- Rollback reuses the old image.

## Estimated Time

One to two weeks.

