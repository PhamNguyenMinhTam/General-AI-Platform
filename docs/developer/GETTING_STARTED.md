# Getting Started

This repository describes a general-purpose local/private platform for unrelated future workloads. A consumer starts here, then follows the workload path that matches the need.

1. Obtain a project identity and approved endpoint information from the Platform Engineer.
2. Choose a workload template and declare CPU, memory, storage, and optional GPU requirements.
3. Build a small image with a health endpoint and structured logs.
4. Deploy through the approved CI/CD or workload interface.
5. Verify readiness, metrics, logs, and access boundaries.
6. Escalate infrastructure failures with workload ID, timestamp, endpoint, and relevant request IDs.

The developer role does not include host, cluster, IAM backend, storage, firewall, GPU driver, secrets, or backup administration.

## Consumer contract

Use published service endpoints, workload identity, resource requests, health checks, metrics, logs, and versioned artifacts. Do not depend on internal hostnames, privileged mounts, node paths, or undocumented infrastructure behavior.
