# Advanced Project 02 - Observability and SRE

## Project Profile

- Level: Intermediate to advanced
- Suggested duration: 6-8 weeks
- Main tools: Prometheus, Grafana, Loki, OpenTelemetry, Tempo or Jaeger, Kubernetes

## Subject

Instrument and operate a multi-service application using metrics, logs and distributed traces. Define service-level indicators and objectives, then use operational signals to detect, investigate and recover from controlled failures.

## Prerequisites

- Docker and Kubernetes fundamentals.
- Basic application development and HTTP knowledge.
- Basic monitoring knowledge from the beginner track.
- A machine or shared cluster with enough memory for the selected stack.

## Learning Goals

- Instrument application behavior instead of only monitoring infrastructure.
- Propagate trace context and request IDs across services.
- Define measurable SLIs, SLOs and an error budget.
- Build dashboards that answer operational questions.
- Create symptom-based alerts with useful runbooks.
- Investigate failures by connecting metrics, logs and traces.

## Mandatory Milestones

1. Deploy an application with at least three communicating services.
2. Add health endpoints, structured logs and RED metrics: rate, errors and duration.
3. Instrument requests with OpenTelemetry and propagate trace context across services.
4. Deploy Prometheus, Grafana, Loki and Tempo or Jaeger.
5. Create dashboards for availability, traffic, error rate, latency, saturation and release version.
6. Define at least two SLIs and one SLO with a clear measurement window.
7. Create at least two alerts tied to user-visible symptoms.
8. Link alerts to short operational runbooks.
9. Simulate dependency failure, high latency and elevated error rate.
10. Use collected signals to identify the cause and document recovery.

## Deliverables

- Instrumented application source.
- Observability deployment configuration.
- Exported dashboards, alerts and data-source configuration.
- SLI, SLO and error-budget document.
- Three failure reports showing metrics, logs and traces.
- Operator runbooks and a final system diagram.

## Validation

- A single request can be followed across service boundaries.
- Logs contain trace or request correlation fields.
- Dashboards identify whether the system is down, slow or failing.
- Alerts fire during the relevant failure and recover afterward.
- The team can diagnose an evaluator-selected failure without guessing.

## Resource Rules

- Publish minimum CPU, memory and storage requirements.
- Use retention limits suitable for the lab.
- External notification services such as Slack or Discord are optional.
- A lightweight stack is acceptable when hardware cannot run every component.
