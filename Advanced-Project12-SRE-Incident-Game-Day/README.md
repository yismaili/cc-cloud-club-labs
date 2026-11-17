# Advanced Project 12 - SRE Incident Game Day

## Project Profile

- Level: Intermediate to advanced
- Suggested duration: 4-6 weeks
- Main tools: Kubernetes or Docker Compose, Prometheus, Grafana, Loki, OpenTelemetry, controlled fault scripts

## Subject

Prepare and run a realistic incident exercise for a small service. Students define reliability targets, create runbooks, rotate operational roles, respond to controlled failures and write a blameless postmortem with measurable follow-up actions.

## Prerequisites

- A working observable application.
- Monitoring, logging and basic incident-response knowledge.
- Completion of the beginner monitoring and CI/CD projects or equivalent experience.

## Learning Goals

- Turn technical signals into an organized incident response.
- Define SLIs, SLOs and an error budget.
- Use runbooks without following them blindly.
- Communicate status, decisions and risk during an incident.
- Measure detection, acknowledgement, mitigation and recovery time.
- Write a blameless postmortem and prioritize corrective actions.

## Mandatory Milestones

1. Select a small application and document its dependencies and user journey.
2. Define availability and latency SLIs with one SLO and error budget.
3. Create dashboards, alerts and at least three short runbooks.
4. Assign incident commander, operations, communications and observer roles.
5. Prepare safe scenarios for dependency outage, latency, bad release and resource exhaustion.
6. Keep scenario details hidden from responders before the exercise.
7. Run at least two timed incidents in a disposable environment.
8. Record a timeline, decisions, evidence, MTTD and MTTR.
9. Restore service and verify user-facing behavior.
10. Write a blameless postmortem with owners and deadlines for follow-up actions.
11. Repeat one scenario after improvements and compare results.

## Deliverables

- Service map and reliability targets.
- Dashboards, alerts and runbooks.
- Game-day scenario cards for instructors.
- Incident timeline and communication log.
- Blameless postmortem.
- Before-and-after reliability improvement report.

## Validation

- Alerts identify user impact without revealing the scenario directly.
- Responders use evidence from metrics, logs and traces.
- The incident commander maintains roles and a shared timeline.
- Recovery is verified from the user's perspective.
- Follow-up actions are specific, owned and testable.
- The repeated scenario shows whether the improvements helped.

## Safety Rules

- Run faults only in a disposable lab.
- Never surprise external users or attack shared infrastructure.
- Every scenario must have a tested emergency stop and recovery path.
- Evaluate the system and process, not individual blame.
