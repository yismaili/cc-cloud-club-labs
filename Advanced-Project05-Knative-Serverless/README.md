# Advanced Project 05 - Knative Serverless Platform

## Project Profile

- Level: Intermediate to advanced
- Suggested duration: 6-8 weeks
- Main tools: Knative Serving, Knative Eventing, Kubernetes, Kourier, CloudEvents, k6, Grafana

## Subject

Build a self-hosted serverless laboratory on Kubernetes. Deploy HTTP services that scale to zero, connect asynchronous services with CloudEvents, and measure cold starts and autoscaling behavior under load.

The project teaches concepts similar to managed serverless platforms; it does not claim to reproduce every feature of AWS Lambda or another cloud service.

## Prerequisites

- Kubernetes, containers, HTTP and event-driven architecture fundamentals.
- A cluster with enough resources for Knative and monitoring.
- Basic application development in Python, Go or Node.js.

## Learning Goals

- Understand Knative Serving and Eventing resources.
- Observe scale-to-zero, activation and request-based autoscaling.
- Produce and consume portable CloudEvents.
- Measure cold-start and scaling tradeoffs.
- Configure routes, domains and TLS for serverless services.

## Mandatory Milestones

1. Install Knative Serving and Kourier or another approved networking layer.
2. Deploy an HTTP service and verify scale-to-zero and activation.
3. Configure a custom lab domain and TLS.
4. Install Knative Eventing and deploy a producer and consumer using CloudEvents.
5. Use an in-memory broker or channel for the learning demonstration.
6. Document that the in-memory transport is not durable production messaging.
7. Configure concurrency and autoscaling settings.
8. Run load tests with k6 and measure cold start, latency and replica count.
9. Create a dashboard for requests, errors, latency, activation and scaling.
10. Demonstrate delivery failure and retry behavior.

## Deliverables

- Cluster installation and application manifests.
- Event producer and consumer source.
- Load-test scenarios and results.
- Dashboard configuration.
- Architecture diagram and explanation of the request and event paths.
- Report comparing the lab with a managed serverless service.

## Validation

- An idle service scales to zero.
- A new request activates the service and returns a valid response.
- A CloudEvent reaches the correct consumer with required metadata.
- Load tests produce observable scaling behavior.
- Failure and retry behavior is demonstrated and explained.

## Optional Extensions

- Use a durable Kafka or RabbitMQ-backed event transport.
- Compare scale-to-zero configurations.
- Add event tracing across producer, broker and consumer.
