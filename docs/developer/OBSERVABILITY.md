# Observability

Every workload should expose:

- liveness and readiness
- request count and error count
- request latency and, where relevant, model inference time
- workload version and model version
- structured logs with timestamp, severity, request ID, and safe error fields

Use bounded labels. Never emit credentials, tokens, raw sensitive payloads, or unbounded user content by default.

Platform Engineer owns collection, storage, dashboards, retention, and alerts. Workload authors own compliant emission and useful context.
