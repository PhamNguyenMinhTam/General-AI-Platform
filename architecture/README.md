# Architecture

The platform is layered in this order:

`Physical Infrastructure -> Network -> Compute -> GPU -> Storage -> Container Runtime -> Generic Data Services -> AI Runtime -> Model Serving -> Developer Interface -> Observability -> Automation -> External Workloads`

External projects are consumers, not modules in this repository. Platform Engineer owns infrastructure and operations. Project / AI Engineer contributes to workload-facing interfaces, examples, SDKs, documentation, and acceptance tests.

## Non-goals

- No application-specific business logic or datasets.
- No assumption that Kubernetes, a message broker, vector database, distributed storage, or service mesh is required.
- No claim that infrastructure is deployed.

See `architecture/topology/`, `architecture/capacity/`, and `architecture/decisions/` for the decision record areas.
