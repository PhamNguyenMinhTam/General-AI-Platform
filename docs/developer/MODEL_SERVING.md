# Model Serving

A model-serving consumer uses an immutable, versioned model artifact and a documented endpoint. The request contract must specify input shape, output shape, model version, timeout, error behavior, and health state.

Consumers should record client latency and handle transient failures with bounded retries. They must not assume access to serving hosts or routing internals.

The Platform Engineer owns gateway, runtime, capacity, routing, scaling, authentication, rollout, and rollback. The Project / AI Engineer contributes model packaging, client examples, and benchmarks.
