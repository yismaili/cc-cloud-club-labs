# Advanced Project 08 - Kubernetes Runtime Security

## Project Profile

- Level: Advanced security
- Suggested duration: 8-10 weeks
- Main tools: Kyverno, Tetragon, eBPF, Helm, Kubernetes

## Subject

Protect Kubernetes workloads at two stages. Kyverno prevents insecure resources from entering the cluster, while Tetragon observes and optionally blocks suspicious behavior after a container starts.

## Prerequisites

- Strong Kubernetes and Linux security knowledge.
- Basic understanding of admission control and system calls.
- A disposable Linux lab with a compatible kernel, eBPF and BTF support.

## Learning Goals

- Distinguish preventive admission policy from runtime detection.
- Write and test policy as code.
- Understand how eBPF observes process and file activity.
- Investigate security events using cluster context.
- Measure policy coverage, noise and operational impact.

## Mandatory Milestones

1. Verify and document the lab kernel and eBPF requirements before installation.
2. Install Kyverno and Tetragon through pinned, reproducible configuration.
3. Create dedicated application namespaces and scope Kyverno application policies to their explicit names or administrator-managed namespace labels. Document the infrastructure namespaces outside this scope, including those running Kyverno and Tetragon, and explain their required host access.
4. Use RBAC to prevent application users from creating namespaces, changing scope labels, policies or exceptions, or deploying into infrastructure namespaces.
5. In the application namespaces, create Kyverno policies that block privileged containers, host namespaces, unsafe capabilities and unapproved registries.
6. Require resource limits, non-root execution and a read-only root filesystem where the sample workload supports them.
7. Test every policy with accepted and rejected manifests and prove that application users cannot bypass its namespace scope.
8. Create Tetragon policies for process execution, shell access and sensitive file activity.
9. Enrich security events with namespace, Pod, container and workload identity.
10. Simulate approved incidents in a disposable application namespace.
11. Create a small investigation runbook and event dashboard or report.
12. Demonstrate one scenario where admission policy prevents risk and another where runtime detection finds behavior that admission policy cannot see.
13. With all policies enabled, restart the Tetragon DaemonSet and recreate a compliant application Pod. Verify that the agents become Ready, new process and file events arrive, and prohibited application manifests remain rejected.

## Deliverables

- Kernel and environment compatibility report.
- Kyverno and Tetragon policy files.
- Namespace-scope and RBAC configuration, with justification for infrastructure exclusions and any additional policy exceptions.
- Positive and negative policy tests.
- Attack-simulation scripts using harmless lab actions.
- Security event report and investigation runbook.
- Architecture and control-coverage diagrams.

## Validation

- Noncompliant application resources are rejected with clear policy messages.
- Compliant application resources continue to deploy normally.
- Application users cannot change policy scope or exceptions, create namespaces, or deploy workloads into excluded infrastructure namespaces.
- Tetragon restarts successfully with the application policies enabled and continues collecting fresh events.
- Tetragon detects the selected process and file events.
- Events identify the affected workload and namespace.
- The team explains gaps, false positives and performance tradeoffs.

## Safety Rules

- Use only a disposable lab cluster.
- Any additional policy exception must identify the affected rules and specific infrastructure workloads, have a documented reason, and be managed only by the lab administrator. Application users must not receive a general policy bypass.
- Runtime blocking is optional and must be tested on a noncritical workload first.
- Do not disable host security features to force compatibility without instructor approval.
- Do not run destructive malware or attack external systems.
