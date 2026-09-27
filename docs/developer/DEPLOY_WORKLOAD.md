# Deploy a Workload

A workload should declare:

- immutable image and version
- CPU and memory requests/limits
- optional GPU request
- ports and health endpoints
- persistent storage needs
- service identity and secret references
- metrics and log behavior
- shutdown and restart expectations

Use the approved template and deployment interface. The Platform Engineer owns the runtime, scheduling, registry, admission, and rollout controls.

## Debug order

1. Confirm the image and version exist.
2. Check configuration and secret references without printing secret values.
3. Check resource admission and quota.
4. Check readiness and dependency connectivity.
5. Inspect structured logs and metrics.
6. Provide request IDs and timestamps when escalating.

Never fix a workload by asking for host access or bypassing policy.
