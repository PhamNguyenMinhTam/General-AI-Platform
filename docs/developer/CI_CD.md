# CI/CD

The generic pipeline stages are build, unit test, dependency and image scan, artifact publication, deployment through the approved interface, smoke test, and rollback or promotion.

Artifacts must be immutable and traceable to source revision. Credentials come from the approved secret mechanism. Pipeline examples must remain application-neutral and must not embed tokens.

Platform Engineer owns runners, registry, deployment controls, credentials, and policy gates. Project / AI Engineer contributes application tests, image metadata, health checks, and deployment configuration.
