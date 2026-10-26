# Level 07 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L07-R1 | **Requirements & estimation** | Clear requirements and SLOs. Estimates with calculations that drive later decisions. | Estimates validated against load test results. | Vague requirements, numbers with no reasoning, estimates ignored afterwards. |
| L07-R2 | **Architecture & trade-offs** | Coherent architecture with a diagram, flows explained, ≥ 3 decisions with alternatives. | Nuanced trade-offs (cost, complexity, team size). Knows when *not* to scale. | Buzzword architecture, microservices without justification, no alternatives. |
| L07-R3 | **Data & consistency** | Sound data design. Consistency choices made per feature and justified. | Partitioning or replica strategy with failure handling. | Ignores consistency, or the design overbooks under concurrency. |
| L07-R4 | **Caching** | Correct cache-aside with invalidation and TTLs. Measured hit rate. | Stampede protection. HTTP/CDN caching. | Stale data bugs, caching everything blindly, no invalidation. |
| L07-R5 | **Async processing & reliability** | Queue with retries, backoff, idempotent consumers, DLQ. Timeouts set. | Outbox pattern, circuit breaker, graceful degradation proven. | Lost or duplicated messages, infinite retries, blocking calls in the request path. |
| L07-R6 | **Correctness under load** | No overbooking in the concurrency test. Idempotency keys work. Rate limiting works. | Load tested beyond the target to find the breaking point. | Race conditions under load, rate limiter bypassable. |
| L07-R7 | **Measurement** | Before/after load tests with percentiles, compared to SLOs. | Bottleneck found by profiling and fixed. | Only averages, no baseline, results not compared. |
| L07-R8 | **Communication** | Design doc is structured, readable and complete. | Responded well to review comments. Doc updated after implementation. | Wall of text, missing sections, out of date with the code. |
