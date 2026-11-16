# Beginner Project 07 - Monitoring

## Subject

Monitor the containerized application and detect a real failure using metrics, dashboards and alerts.

## Learning Goals

- Understand metrics, logs, dashboards and alerts.
- Add meaningful health checks and application metrics.
- Ask operational questions instead of only installing tools.
- Detect and investigate a controlled failure.

## Mandatory Work

- Reuse the application from Project 05.
- Add `/health` and `/metrics` endpoints to the application.
- Collect application and host metrics with Prometheus and suitable exporters.
- Create a Grafana dashboard showing availability, request rate, error rate, latency, CPU, memory and disk usage.
- Keep application logs in a consistent structured or key-value format.
- Create one alert for a user-facing problem such as high error rate or service unavailability.
- Stop a dependency or break a health endpoint and observe the signals.
- Document the investigation and recovery.

## Deliverables

- Monitoring service configuration.
- Prometheus scrape and alert rules.
- Exported Grafana dashboard configuration.
- Failure-test report with screenshots or command output that proves behavior.

## Validation

- The dashboard answers whether the service is up, slow or failing.
- The alert changes state during the controlled failure.
- The student identifies the failing component using collected signals.
- Monitoring data is not presented as application backup data.

## Estimated Time

One to two weeks.
