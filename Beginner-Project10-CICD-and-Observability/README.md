# Beginner Project 10 - CI/CD and Observability

## Subject

Test, package, release, observe and safely roll back the application built during the track.

## Introduction

For a quick introduction to CI/CD, watch [CI/CD Explained in 5 Minutes](https://www.youtube.com/watch?v=ddDJxFnv-qs) before starting the project.

## Learning Goals

- Understand the difference between CI, release and deployment.
- Promote immutable container images.
- Protect pipeline secrets and stop failed releases.
- Connect logs, metrics and traces during an incident.
- Roll back by reusing a known previous artifact.

## Mandatory Work

- Reuse the application from Project 05 or Project 08.
- Create a GitHub Actions workflow or an instructor-approved equivalent.
- Run formatting, linting, static validation and automated tests.
- Build a Docker image only after validation passes.
- Tag the image with a Git commit and a release version; never use `latest`.
- Push the image to an approved registry.
- Store registry and deployment credentials in pipeline secret storage.
- Add a release or deployment stage using a documented lab-safe model.
- Show the running version through an endpoint or application label.
- Produce consistent logs, application metrics and request correlation across two services.
- Create a dashboard and an alert tied to a user-facing symptom.
- Define one measurable SLI and SLO with a time window.
- Release a controlled failure and restore service using the previous image artifact.

## Supported Lab Deployment Models

- GitHub-hosted CI with a documented local release from the published image.
- GitHub Actions with a self-hosted runner inside the lab.
- Another instructor-approved pipeline that can safely reach the lab.

Students must explain whether their chosen model is continuous delivery or continuous deployment.

## Deliverables

- Pipeline workflow files.
- Tests and image build configuration.
- Dashboard, alert and observability configuration.
- Release and rollback runbook.
- Failure report showing what the pipeline caught and what runtime monitoring caught.

## Validation

- A failing test prevents image publication or promotion.
- A successful commit produces a traceable immutable image.
- The running version can be identified.
- The controlled failure is visible in operational signals.
- Rollback reuses the old image; it does not rebuild it.

## Estimated Time

Two to three weeks.

<p align="center">
  <img src="../images/next-level.png" alt="Hit the next level" width="600">
</p>
