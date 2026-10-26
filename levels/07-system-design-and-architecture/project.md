# Level 07 project: Gather at Scale

Imagine Gather is growing to **1 million users and 50,000 events a month**, with popular events selling out in seconds. Design for it, then implement and measure the most important pieces.

**Location:** `docs/design/` in your Gather repo, plus code changes via PRs. Record the location in `progress.md`.

## Part A: Design document

### Must

| ID | Requirement |
|---|---|
| L07-M1 | **Requirements**: functional, non-functional (latency, availability, consistency) and explicit SLOs. |
| L07-M2 | **Estimates**: QPS (average and peak), storage growth, bandwidth, with the calculations shown. |
| L07-M3 | **Architecture diagram** of the target system, with a walkthrough of the main request flows (browse events, RSVP to a hot event). |
| L07-M4 | **Data design**: schema changes, indexes, read replicas or partitioning decisions, consistency choices per feature. |
| L07-M5 | **Trade-offs**: at least 3 significant decisions, each with alternatives considered and why they were rejected. |
| L07-M6 | **Risks & failure modes**: what happens when the cache, queue or database fails, and how the system degrades. |

## Part B: Implementation

### Must

| ID | Requirement |
|---|---|
| L07-M7 | **Caching**: cache event list and detail reads (e.g. Redis, cache-aside) with correct invalidation on update and RSVP. |
| L07-M8 | **Queue**: move slow side effects (confirmation emails, waitlist promotion notifications) to a background worker via a message queue. Retries with backoff, idempotent handlers, dead-letter handling. |
| L07-M9 | **Hot event protection**: RSVPs for a single popular event stay correct under heavy concurrent load (no overbooking), with an idempotency key on the RSVP endpoint. |
| L07-M10 | **Rate limiting** on public endpoints, with an algorithm you can explain. |
| L07-M11 | **Load test** (k6, Locust or similar) before and after, with results (p50/p95/p99 latency, throughput, error rate) in `docs/design/results.md`, compared against your SLOs. |

### Should

| ID | Requirement |
|---|---|
| L07-S1 | Cursor-based pagination for the event list. |
| L07-S2 | Timeouts and a circuit breaker around an external dependency (e.g. the email provider). |
| L07-S3 | Transactional outbox for reliable event publishing. |
| L07-S4 | Design review: the AI mentor (or a peer) reviews the design doc, and you respond to the comments in writing. |

### Stretch

| ID | Requirement |
|---|---|
| L07-X1 | CDN or HTTP caching headers for public pages. |
| L07-X2 | A read replica, with read/write splitting. |
| L07-X3 | Chaos experiment: kill the cache or worker during a load test and document what happens. |

## Acceptance scenarios

1. The design doc can be understood by an engineer who has never seen Gather.
2. A load test with 500 concurrent RSVPs for an event with 100 seats → exactly 100 `going`.
3. Stop the worker, RSVP, restart the worker → the confirmation is eventually sent exactly once.
4. Event update → cached data is never stale for longer than the documented bound.
