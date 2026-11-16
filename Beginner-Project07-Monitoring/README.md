# Beginner Project 07 - Monitoring

## Subject

Monitor the containerized application and detect a real failure using metrics, dashboards and alerts.

## Learning Goals

- Understand metrics, logs, dashboards and alerts.
- Add meaningful health checks and application metrics.
- Ask operational questions instead of only installing tools.
- Detect and investigate a controlled failure.

## Mandatory Work

- Reuse the Docker Compose TODO application from Project 05.
- Reuse the application's `/healthz` and `/readyz` endpoints, and add a `/metrics` endpoint.
- Collect application and host metrics with Prometheus and suitable exporters.
- Create a Grafana dashboard showing availability, request rate, error rate, latency, CPU, memory and disk usage.
- Monitor `/readyz` using an HTTP probe or an application readiness metric, and show its status on the dashboard.
- Keep application logs in a consistent structured or key-value format.
- Create one alert for a user-facing problem such as high error rate or service unavailability. Document its condition and how long the condition must persist before the alert fires.
- Complete the required MariaDB failure exercise below.
- Document the investigation and recovery.

### Required Failure Exercise

1. Generate normal traffic by listing and creating TODO tasks.
2. Confirm that the dashboard shows requests, response times and successful readiness checks.
3. Stop MariaDB while leaving the application and monitoring services running.
4. Observe failed database-dependent requests, failed readiness checks and an alert becoming active after the configured duration.
5. Use the metrics and application logs to identify the database dependency as the cause.
6. Start MariaDB again and demonstrate application recovery, successful readiness checks and alert resolution.

Continue generating traffic during the outage and after recovery so the dashboard captures both phases. Include the commands, observed signals and alert timing in the failure-test report.

## Deliverables

- Monitoring service configuration.
- Prometheus scrape and alert rules.
- Exported Grafana dashboard configuration.
- Failure-test report with screenshots or command output that proves behavior.

## Validation

- The dashboard answers whether the service is up, slow or failing.
- The alert fires during the MariaDB outage and returns to its inactive state after recovery.
- TODO operations and readiness checks succeed again after MariaDB restarts, without manually restarting the application.
- The student identifies the failing component using collected signals.
- Monitoring data is not presented as application backup data.

## Estimated Time

One to two weeks.

<p align="center">
  <img src="../images/next-level.png" alt="Hit the next level" width="600">
</p>
