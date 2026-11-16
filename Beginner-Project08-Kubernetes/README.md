# Beginner Project 08 - Kubernetes

## Subject

Move the Docker Compose application to a small local Kubernetes cluster. You can use K3s, K3d or the built-in Kubernetes in Docker Desktop.

## Learning Goals

- Understand Pods, Deployments, Services, Ingress and namespaces.
- Configure health checks, resources and persistent storage.
- Scale and repair containerized workloads.
- Apply basic network isolation.

## Architecture

![Kubernetes architecture](images/k8s-architecture.png)

## Ephemeral vs Persistent Storage

- **Ephemeral:** data lives inside the container or an `emptyDir` volume and is lost when the Pod is deleted or restarted. Use it for temporary files and caches.
- **Persistent:** data lives in a PersistentVolume (requested with a PersistentVolumeClaim) and survives Pod deletion, restarts and rescheduling. Use it for databases and anything you cannot lose.

Show the difference: write data to both, delete the Pod, and compare what is left.

## Mandatory Work

**Cluster**
- Create a local cluster with K3s, K3d or Docker Desktop's built-in Kubernetes, with a reproducible setup script or documented steps.
- With K3d, map a host port to the cluster load balancer (for example `-p "8080:80@loadbalancer"`) so Ingress is reachable.
- Create a dedicated application namespace.

**Application**
- Deploy the web application and its internal dependency.
- Use ConfigMaps for normal configuration and Secrets for sensitive values.
- Pin image tags to a specific version. Never use `latest`.
- Run containers as non-root (`runAsNonRoot`, `allowPrivilegeEscalation: false`).
- Expose the application through an Ingress using a `.test` hostname (add it to `/etc/hosts`).

**Access**
- Show the application reachable with `kubectl port-forward` (for example `kubectl port-forward svc/web 8080:80 -n <namespace>`) for quick testing and debugging, in addition to Ingress.

**Reliability**
- Add readiness, liveness and startup probes where appropriate.
- Define CPU and memory requests and limits.
- Use persistent storage (a PersistentVolumeClaim) for stateful data, and demonstrate the difference from ephemeral storage.
- Run at least two application replicas and show recovery after deleting one Pod.

**Security**
- Add a default-deny NetworkPolicy and only the required allow rules.

**Delivery**
- Store all manifests in Git.
- Validate manifests before applying (`kubectl apply --dry-run=server`; optionally `kubeconform`).

## Allowed Resources

You may use the official Kubernetes documentation at https://kubernetes.io/docs/ while working. Useful pages:

- [Pods](https://kubernetes.io/docs/concepts/workloads/pods/)
- [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/)
- [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
- [Persistent Volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)
- [Liveness, readiness and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)
- [Port forwarding](https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/)
- [kubectl quick reference](https://kubernetes.io/docs/reference/kubectl/quick-reference/)

## Deliverables

- Cluster setup script.
- Kubernetes manifests organized by component.
- A small architecture diagram.
- A README with deployment, verification, failure and cleanup instructions.

## Validation

- All workloads become healthy from a clean cluster.
- The application is reachable through Ingress and through `kubectl port-forward`.
- Data survives a Pod restart on persistent storage, while ephemeral data is lost.
- Deleting one replica does not stop the application.
- An unauthorized test Pod cannot reach the protected service.

## Estimated Time

Two to three weeks.