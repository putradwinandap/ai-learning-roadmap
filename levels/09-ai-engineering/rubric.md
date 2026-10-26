# Level 09 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L09-R1 | **Retrieval quality** | Sensible chunking and embeddings. Metadata filters. Answers grounded with correct citations. Retrieval metrics measured. | Hybrid search or reranking justified by eval data. Freshness handled when documents change. | Whole documents stuffed into the prompt, wrong citations, no retrieval metrics. |
| L09-R2 | **Tool use & agent design** | Well-defined tool schemas, validated inputs, confirmation before side effects, bounded loops. | Simplest workflow that works (agent only where needed). Clear error recovery. | Unbounded agent loops, actions without confirmation, unvalidated tool arguments. |
| L09-R3 | **Evaluation** | ≥ 40-case golden set across categories. Automated scoring with a documented judge rubric. Results tracked across versions. Evals in CI. | Judge validated against human labels. Error analysis drives changes. | A handful of manual spot checks, "it looks good", no regression gate. |
| L09-R4 | **Safety & security** | Tenant/permission-aware retrieval and tools. Injection test set with mitigations. No secrets in prompts or logs. | Defence in depth (input/output filtering, least-privilege tools). OWASP LLM Top 10 reviewed. | Cross-tenant leakage possible, injection triggers actions, PII logged. |
| L09-R5 | **Reliability & UX** | Timeouts, retries, fallbacks. Honest "I don't know". Structured outputs validated. | Streaming, good loading and error UX, graceful degradation when the provider is down. | Hallucinated events, crashes on provider errors, malformed JSON breaks the app. |
| L09-R6 | **Observability, cost & latency** | Full traces with tokens, cost and latency. p95 and cost per conversation reported. | Optimisations (caching, routing) measured against quality. Budget alerts. | No visibility into cost, unknown latency. |
| L09-R7 | **Engineering quality** | Prompts versioned in code, clean separation of retrieval, orchestration and tools. Tests for non-LLM logic. | Provider-agnostic abstraction where it pays off. Reproducible ingestion pipeline. | Prompts scattered as string literals, untestable glue code. |
| L09-R8 | **Documentation** | Design doc with decisions, eval methodology and results, limitations, cost estimate. | Clear model and prompt changelog with eval deltas. | Missing eval results or limitations. |
