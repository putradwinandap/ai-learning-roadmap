# Level 07 topics

Full lesson files are planned. Until then, your AI mentor teaches these topics in order (`/lesson`), using the resources below.

| # | Topic | Key ideas |
|---|---|---|
| 01 | Requirements & estimation | Functional vs non-functional requirements, SLAs/SLOs, QPS, storage and bandwidth estimates |
| 02 | Scaling basics | Vertical vs horizontal, stateless services, load balancers, sticky sessions and why to avoid them |
| 03 | Caching | Cache-aside, write-through, TTLs, invalidation, stampedes, CDN and HTTP caching |
| 04 | Queues & async processing | Producers/consumers, at-least-once delivery, retries with backoff, idempotency, DLQs, outbox pattern |
| 05 | Databases at scale | Read replicas, partitioning/sharding, connection pooling, SQL vs NoSQL trade-offs |
| 06 | Consistency | CAP, PACELC, eventual consistency, read-your-writes, distributed transactions and sagas |
| 07 | API design at scale | Versioning, cursor pagination, rate limiting algorithms, idempotency keys, webhooks |
| 08 | Reliability | Timeouts, retries, circuit breakers, bulkheads, graceful degradation |
| 09 | Performance measurement | Latency percentiles, load testing (k6, Locust), profiling, finding bottlenecks |
| 10 | Architecture styles | Layered, hexagonal/clean architecture, event-driven, modular monolith vs microservices |
| 11 | Design docs & reviews | Structure of a design doc, alternatives considered, risks, review etiquette |
| 12 | Classic case studies | URL shortener, news feed, chat, rate limiter, ticket booking |

## Resources

- [The System Design Primer](https://github.com/donnemartin/system-design-primer)
- *Designing Data-Intensive Applications*, by Martin Kleppmann (book)
- [ByteByteGo blog](https://blog.bytebytego.com/)
- [High Scalability](http://highscalability.com/)
- [Google SRE book (free)](https://sre.google/sre-book/table-of-contents/), chapters on SLOs and handling overload
- [k6 load testing docs](https://grafana.com/docs/k6/latest/)
- [Martin Fowler: Microservice prerequisites](https://martinfowler.com/bliki/MicroservicePrerequisites.html)
