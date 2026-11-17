# Advanced Project 06 - FinOps with OpenCost

## Project Profile

- Level: Advanced
- Suggested duration: 6-8 weeks
- Main tools: OpenCost, Prometheus, Grafana, Alertmanager, Python, Kubernetes

## Subject

Create a Kubernetes cost-visibility platform that allocates estimated cost by namespace, workload and team. Use the results to identify waste, recommend rightsizing and alert when a team exceeds its agreed budget.

## Prerequisites

- Kubernetes resources, requests, limits, labels and namespaces.
- Prometheus and Grafana fundamentals.
- Basic cloud billing and Python knowledge.

## Learning Goals

- Understand how Kubernetes usage maps to infrastructure cost.
- Design a consistent cost-allocation label policy.
- Detect idle, oversized and unallocated resources.
- Build useful cost and efficiency dashboards.
- Create budget alerts and actionable recommendations.

## Mandatory Milestones

1. Deploy OpenCost and connect it to Prometheus.
2. Create at least three team namespaces with consistent ownership and cost labels.
3. Deploy workloads with different CPU, memory and storage profiles.
4. Configure real cloud pricing when an approved integration is available, or document simulated local prices.
5. Build dashboards for daily cost, monthly estimate, namespace, workload and team allocation.
6. Identify idle and over-requested workloads.
7. Create at least two budget or anomaly alerts.
8. Produce a rightsizing report and apply one approved optimization.
9. Compare cost and service health before and after the change.
10. Export a weekly report in a simple machine-readable format.

## Deliverables

- OpenCost, Prometheus, Grafana and alert configuration.
- Kubernetes label and allocation policy.
- Dashboards and weekly report generator.
- Rightsizing analysis with before-and-after evidence.
- Pricing assumptions and limitations document.

## Validation

- Workload costs can be grouped by team and namespace.
- Unallocated cost is visible rather than silently ignored.
- Alerts fire when a controlled budget threshold is crossed.
- At least one recommendation reduces estimated cost without breaking the application SLO.
- The team can explain why local estimates may differ from a real cloud bill.

## Optional Extension

Build a simple forecasting script for the next 30 days. Forecasting is a bonus and must not replace correct cost allocation, budgets and rightsizing.
