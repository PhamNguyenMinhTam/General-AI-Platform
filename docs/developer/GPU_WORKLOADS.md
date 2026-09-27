# GPU Workloads

Request GPU capacity through the workload contract. Do not install drivers, modify host runtime settings, or assume a particular GPU model.

A generic GPU workload should:

- declare the number and class of devices it needs
- detect and report assigned devices and visible memory
- perform a small deterministic validation
- expose readiness and failure state
- emit bounded GPU and latency metrics
- avoid downloading large models during validation

The Platform Engineer owns hardware, drivers, allocation, partitioning, isolation, and recovery. The workload author owns packaging and consumer-side validation.
