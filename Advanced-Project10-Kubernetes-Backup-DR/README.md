# Advanced Project 10 - Kubernetes Backup and Disaster Recovery

## Project Profile

- Level: Intermediate to advanced
- Suggested duration: 6-8 weeks
- Main tools: Velero, MinIO or approved object storage, Kubernetes, database-native backup tools

## Subject

Design, automate and test recovery for a stateful Kubernetes application. Protect Kubernetes resources and application data, then prove recovery by deleting workloads, namespaces and selected cluster state.

## Prerequisites

- Kubernetes storage and stateful workload knowledge.
- Database backup fundamentals.
- Basic object storage, encryption and access-control knowledge.

## Learning Goals

- Define realistic RPO and RTO targets.
- Understand the difference between resource backup, volume backup and database-consistent backup.
- Automate retention and restore testing.
- Recover from namespace and cluster-level failure.
- Identify data that is not protected by the chosen design.

## Mandatory Milestones

1. Deploy a stateful application with known test data.
2. Define RPO, RTO, retention and backup ownership.
3. Deploy Velero with MinIO or instructor-approved object storage.
4. Protect backup storage with credentials, restricted access and encryption where available.
5. Schedule Kubernetes resource and persistent-data backups.
6. Use a database-native dump or snapshot process for application-consistent recovery.
7. Delete and restore one application resource.
8. Delete and restore the complete application namespace.
9. Rebuild a clean cluster or recovery environment and restore the application.
10. Test backup corruption, missing credentials or an unavailable backup target.
11. Measure achieved recovery time and possible data loss.

## Deliverables

- Backup architecture and data-classification documents.
- Velero, storage and database-backup configuration.
- Backup schedules and retention policy.
- Step-by-step recovery runbooks.
- Evidence for resource, namespace and clean-environment restores.
- RPO and RTO results with improvement recommendations.

## Validation

- The restored application contains verified test data.
- A checksum or application query proves data integrity.
- Recovery works without using undeclared files from the failed environment.
- Expired backups are removed according to policy.
- The team can explain which secrets, external services and cluster components need separate protection.

## Safety Rules

- Use synthetic data only.
- Never test deletion against a shared or production cluster.
- Do not call a backup successful until a restore has been tested.
- Protect backup credentials and do not commit them to Git.
