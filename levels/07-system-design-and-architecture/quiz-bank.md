# Level 07 quiz bank

See [ai/quiz-protocol.md](../../ai/quiz-protocol.md). Most questions here are *Explain* and *Apply*.

## 1. Requirements & estimation
- SLA vs SLO vs SLI.
- *Apply:* 10 million page views a day. What is the average QPS? A reasonable peak QPS?

## 2. Scaling
- Why must services be stateless to scale horizontally?
- What does a load balancer do? Name two balancing strategies.

## 3. Caching
- Cache-aside vs write-through.
- What is a cache stampede and how do you prevent it?
- "There are only two hard things in computer science..." Why is cache invalidation hard?

## 4. Queues
- Why move work to a queue?
- At-least-once delivery: what does it imply for consumers?
- What is a dead-letter queue? What is the outbox pattern for?

## 5. Data at scale
- Replication vs partitioning.
- Explain CAP. What does PACELC add?
- When would you choose a NoSQL store over PostgreSQL?

## 6. API & reliability
- Offset vs cursor pagination.
- Token bucket rate limiting, explained.
- Why do retries need backoff and jitter? Why idempotency keys?
- What does a circuit breaker do?

## 7. Architecture & measurement
- Modular monolith vs microservices: when does each fit?
- Why look at p99 latency instead of the average?
- *Apply:* design a URL shortener at a high level in 5 bullet points.
