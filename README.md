# General-AI-Platform

General-purpose local/private infrastructure and AI platform for multiple unrelated future workloads. This repository contains architecture, operating boundaries, developer-facing contracts, examples, and acceptance criteria. It does not claim that infrastructure has been deployed.

## Purpose and non-goals

The platform provides a path from physical infrastructure through network, compute, GPU, storage, containers, generic data services, AI runtimes, model serving, developer interfaces, observability, and automation. External projects are consumers, not modules.

It is intentionally not tied to an application, dataset, model family, ML framework, or vendor. Kubernetes, brokers, vector databases, distributed storage, and service meshes are not deployed by this scaffold; selection requires a documented requirement and architecture decision first.

## Ownership

The Platform Engineer is the final owner of architecture, data center, network, Linux hosts, compute, GPU infrastructure, storage, containers, data services, identity, security, observability, backup/recovery, isolation, and platform operations.

The Project / AI Engineer is a contributor to the developer-facing layer: workload templates, GPU examples, training/inference interfaces, model/LLM/embedding clients, health/metrics/logging conventions, CI/CD templates, SDK examples, onboarding documentation, and acceptance workloads. They do not administer hosts, switches, firewalls, storage, drivers, clusters, IAM, secrets, backups, or disaster recovery.

## Architecture

`Physical Infrastructure -> Network -> Compute -> GPU -> Storage -> Container Runtime -> Generic Data Services -> AI Runtime -> Model Serving -> Developer Interface -> Observability -> Automation -> External Workloads`

The architecture baseline is in `architecture/`. Platform operations are documented in `docs/operations/`; consumer onboarding is in `docs/developer/`.

## Repository tree

| Area | Purpose |
| --- | --- |
| `architecture/` | Topology, capacity, boundaries, and decisions |
| `compute/` | CPU, GPU, and virtualization infrastructure |
| `network/` | Topology, DNS, firewall, and remote access |
| `storage/` | Block, object, shared, backup, and recovery interfaces |
| `containers/` | Runtime, registry, image, orchestration, and workload conventions |
| `data-services/` | Generic relational, vector, cache, and messaging services |
| `ai-runtime/` | GPU, training, inference, LLM, and embedding runtime contracts |
| `model-serving/` | Gateway, runtimes, routing, clients, and benchmarks |
| `developer/` | SDKs, examples, templates, and acceptance consumers |
| `observability/` | Metrics, logs, dashboards, and alerts |
| `security/` | Identity, secrets, certificates, and policies |
| `automation/` | Provisioning, deployment, CI/CD, and maintenance |
| `tests/` | Domain and platform acceptance checks |

## Branch strategy

Stable branch: `main`.

Platform-owned branches: `platform/architecture`, `platform/datacenter`, `platform/network`, `platform/compute`, `platform/gpu-runtime`, `platform/storage`, `platform/containers`, `platform/data-services`, `platform/security`, `platform/observability`, `platform/backup`, and `platform/multiproject`.

Collaborative branches: `platform/ai-runtime`, `platform/model-serving`, `platform/developer-experience`, `platform/sdk`, `platform/workload-templates`, `platform/cicd`, and `platform/acceptance`. Do not create remote branches automatically.

## Developer experience

Consumers learn to request CPU/RAM/GPU, use persistent storage and generic data services, deploy inference, consume model/LLM/embedding services, expose health and metrics, write structured logs, use secrets safely, and debug deployments. Start with `docs/developer/GETTING_STARTED.md`.

## Security, observability, and CI/CD

Platform Engineer owns IAM, RBAC, least privilege, secrets infrastructure, TLS, certificates, network security, audit, host security, backup, restore, collection, dashboards, alerts, runners, registries, and deployment controls. Workloads use published interfaces and never commit credentials or rely on privileged host access.

## Multi-project isolation

Unrelated workloads must be isolated by identity, network policy, resource quotas, storage boundaries, scheduling controls, and audit signals. Acceptance workloads in `developer/acceptance-workloads/` use synthetic inputs and contain no business logic.

## Checklist and acceptance

`TASK_CHECKLIST.md` contains 14 Platform Engineer tasks and 14 collaborative developer/AI tasks. It is the implementation sequence and ownership record.

The repository passes the conceptual tests when the platform still makes sense after deleting every external application, and when a new AI Engineer can deploy a generic workload using developer documentation without learning data-center administration. This scaffold establishes the contracts and evidence to make those tests executable later.

## Current status

Architecture and scaffolding only. No hosts, networks, GPUs, data services, clusters, model servers, credentials, or external application workloads have been deployed by this repository.
