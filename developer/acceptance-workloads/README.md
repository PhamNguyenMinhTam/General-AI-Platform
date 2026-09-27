# Generic Acceptance Workloads

These consumers prove that unrelated workloads can use the platform. Planned examples cover CPU, GPU, database, object storage, generic inference, LLM, embeddings, and metrics.

All examples must use synthetic inputs, small deterministic artifacts, explicit resource requests, health checks, structured logs, and teardown instructions. They must contain no application-specific business logic and must not download huge models.

Acceptance workloads are test consumers, not platform services and not external application modules.
