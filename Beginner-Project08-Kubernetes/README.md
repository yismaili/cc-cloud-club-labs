# Beginner Project 08 - Kubernetes

## Subject

Move the Docker Compose application to a small local Kubernetes cluster using K3s or K3d.

## Learning Goals

- Understand Pods, Deployments, Services, Ingress and namespaces.
- Configure health checks, resources and persistent storage.
- Scale and repair containerized workloads.
- Apply basic network isolation.

## Mandatory Work

- Create a local K3s or K3d cluster with a reproducible setup script.
- Create a dedicated application namespace.
- Deploy the web application and its internal dependency.
- Use ConfigMaps for normal configuration and Secrets for sensitive values.
- Expose the application through an Ingress using a `.test` hostname.
- Add meaningful readiness, liveness and startup probes where appropriate.
- Define CPU and memory requests and limits.
- Use persistent storage for stateful data.
- Run at least two application replicas and demonstrate recovery after deleting one Pod.
- Add a default-deny NetworkPolicy and only the required allow rules.
- Store all manifests in Git and provide validation commands.

## Deliverables

- Cluster setup script.
- Kubernetes manifests organized by component.
- A small architecture diagram.
- A README with deployment, verification, failure and cleanup instructions.

## Validation

- All workloads become healthy from a clean cluster.
- The application is reachable through Ingress.
- Data survives a Pod restart.
- Deleting one replica does not stop the application.
- An unauthorized test Pod cannot reach the protected service.

## Estimated Time

Two to three weeks.
