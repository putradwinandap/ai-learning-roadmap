# Level 04 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L04-R1 | **API design** | Resource-oriented URLs, correct methods and status codes, consistent JSON and error format, pagination. | Documented with OpenAPI. Idempotency considered. Consistent naming everywhere. | Verbs in URLs, 200 for errors, inconsistent shapes. |
| L04-R2 | **Data modelling & SQL** | Normalised schema with PKs, FKs and constraints. Migrations. Efficient queries without N+1. | Indexes justified with EXPLAIN. Constraints enforce invariants in the DB too. | No foreign keys, schema changed by hand, N+1 loops. |
| L04-R3 | **Business logic & concurrency** | RSVP, waitlist and promotion correct. The capacity race is prevented. | Logic isolated in a service layer and tested at the unit level too. Clear transaction boundaries. | Overbooking possible, promotion bugs, rules in controllers. |
| L04-R4 | **Security** | Hashed passwords, authn and authz on every protected route, parameterised queries, no secrets committed, safe cookie/token handling. | Rate limiting. OWASP API Top 10 reviewed in the README. Least-privilege DB user. | Plain or weakly hashed passwords, missing ownership checks, SQL strings built by concatenation. |
| L04-R5 | **Validation & error handling** | All input validated at the boundary with field-level errors. Unexpected errors return 500 without leaking internals and are logged. | Central error handler, schema-based validation, request IDs in logs. | Crashes on bad input, stack traces sent to clients. |
| L04-R6 | **Testing** | ≥ 25 integration tests on a separate test DB, covering auth, permissions, RSVP logic and validation. All pass. | Fast, isolated tests (transactions/rollback or fresh schema), plus unit tests for services. | Tests against the dev DB, order-dependent tests, only happy paths. |
| L04-R7 | **Code structure** | Clear layers (routes → services → data). Config via environment. Readable code. | Dependency injection for the DB/clock. Small, focused modules. | Everything in one file, DB calls inside route handlers everywhere. |
| L04-R8 | **Documentation & DX** | A fresh clone runs with the README steps. `.env.example`. API documented. | One-command setup (script or Docker Compose). Seed data. | Missing steps, undocumented environment variables. |
