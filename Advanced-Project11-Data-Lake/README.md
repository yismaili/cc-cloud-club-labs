# Advanced Project 11 - Open Data Lake Platform

## Project Profile

- Level: Advanced data engineering
- Suggested duration: 10-12 weeks
- Main tools: Kafka with Strimzi, MinIO, Apache Iceberg, Trino, Kubernetes

## Subject

Build a small open data-lake laboratory for streaming e-commerce events, durable object storage and analytical SQL. The core project focuses on a working and observable data path; heavy processing and business-intelligence tools are optional extensions.

## Prerequisites

- Kubernetes, storage and distributed-system fundamentals.
- Python or Java development.
- Basic SQL, event-streaming and data-modeling knowledge.
- A shared machine or cluster with at least 16 GB of available memory recommended.

## Learning Goals

- Understand topics, partitions, offsets and consumer lag.
- Separate raw, cleaned and aggregated data layers.
- Store analytical data in an open table format.
- Query object-storage data through Trino.
- Monitor data freshness, failures and processing lag.
- Reason about replay, schema evolution and duplicate events.

## Mandatory Milestones

1. Deploy Kafka through Strimzi with persistent storage.
2. Create a versioned event schema and synthetic e-commerce event producer.
3. Configure topics, partitions, retention and consumer groups.
4. Deploy MinIO with protected credentials and persistent storage.
5. Build a lightweight consumer that validates events and writes raw data.
6. Store cleaned analytical data in Apache Iceberg tables.
7. Deploy Trino and configure an Iceberg catalog backed by MinIO.
8. Query raw and cleaned data and produce at least three useful analytical results.
9. Demonstrate consumer restart, event replay and duplicate handling.
10. Monitor Kafka health, consumer lag, processing failures and data freshness.

## Deliverables

- Kubernetes and operator configuration.
- Event producer and processing source.
- Schema and data-layer documentation.
- Iceberg catalog and Trino configuration.
- SQL queries and expected results.
- Monitoring dashboard and failure-test report.
- Architecture diagram showing event and data flow.

## Validation

- Events move from producer to Kafka and object storage.
- Invalid events are rejected or isolated without stopping valid processing.
- Trino can query the final Iceberg tables.
- Restarting a consumer does not silently lose committed data.
- Consumer lag and stale data are visible.
- The team can explain delivery semantics and known consistency limits.

## Optional Extensions

- Use Spark Structured Streaming for transformations.
- Add schema evolution and Iceberg time travel.
- Add dbt models for the curated layer.
- Connect Metabase to Trino.
- Test a durable Kafka backup or replication strategy.
