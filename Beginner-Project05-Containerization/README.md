# Beginner Project 05 - Containerization

## Subject

Move a small web application and database into a reproducible Docker Compose stack.

## Learning Goals

- Build and run container images.
- Connect services with Docker networks.
- Persist data with Docker-managed named volumes.
- Configure applications without committing secrets.
- Use health checks and restart policies.

## Mandatory Work

- Run the project inside a VM or instructor-approved Linux environment.
- Create a small Python web application.
- Create separate services for NGINX, the application and a database.
- Write the application Dockerfile. Official pinned images may be used for NGINX and the database.
- Use explicit image versions; do not use `latest`.
- Expose only NGINX to the host on ports 80 and 443.
- Place frontend traffic and database traffic on appropriate Docker networks.
- Use Docker-managed named volumes for database and application data.
- Add health checks, restart policies and resource limits where supported.
- Commit `.env.example`, ignore the real `.env`, and never commit secrets.
- Provide a `Makefile` with `up`, `down`, `logs` and `clean` targets.

## Deliverables

- `compose.yaml` and one or more Dockerfiles.
- Application source and NGINX configuration.
- `.env.example`, `.gitignore` and `Makefile`.
- A README explaining architecture, commands and data persistence.

## Validation

- The application is reachable only through NGINX HTTPS.
- The database is not published to the host.
- Data survives `docker compose down` followed by `up`.
- An unhealthy container is visible and a stopped service follows its restart policy.

## Estimated Time

Two weeks.
