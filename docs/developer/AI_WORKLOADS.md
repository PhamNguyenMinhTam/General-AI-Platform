# AI Workloads

Supported generic patterns include training, batch inference, online inference, GPU jobs, LLM serving, embedding serving, and model serving. Framework and model family remain selectable by workload requirements.

Training jobs must document dataset input, checkpoint output, artifact version, restart behavior, and resource requests. Inference services must document request/response contracts, health checks, timeouts, concurrency, and model version.

Use synthetic or small deterministic artifacts in examples. External projects provide their own data and business behavior; this repository provides platform contracts only.
