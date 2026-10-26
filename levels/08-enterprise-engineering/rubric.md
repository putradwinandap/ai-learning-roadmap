# Level 08 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L08-R1 | **Domain design & modularity** | Clear bounded contexts, boundaries enforced (module rules, separate data ownership), split decision justified. | Context map with relationship types. Boundaries checked automatically in CI. | Shared database tables across contexts, circular dependencies, a distributed monolith. |
| L08-R2 | **Multi-tenancy & authorization** | Tenant isolation enforced in every path, with tests. OIDC login. Roles enforced server-side. | Defence in depth (e.g. row-level security). Tenant-aware rate limits. | Tenant ID trusted from the client, missing checks on some endpoints. |
| L08-R3 | **Integration & events** | Versioned event schemas. Reliable publishing and idempotent consumers. Clear sync vs async choices. | Contract tests. Outbox. Replay strategy documented. | Events as an undocumented JSON blob, duplicate processing, chatty synchronous chains. |
| L08-R4 | **Observability & operations** | Correlated logs, RED metrics, end-to-end traces, dashboard, SLOs with burn-rate alerts and runbooks. | Game day and postmortem. Alerts tuned to avoid noise. | Logs without context, no traces across async boundaries, alerts on CPU only. |
| L08-R5 | **Security & compliance** | Threat model, ASVS L1 checklist, secret manager, audit log, PII inventory, encryption, retention, delete-my-data flow. | Policy as code. Security tests in CI. Least-privilege IAM everywhere. | Secrets in env files or code, missing audit trail, unknown PII locations. |
| L08-R6 | **Infrastructure as Code & delivery** | The whole environment in IaC with staging and production. Plan on PR, apply on merge, promotion flow. | Reusable modules, drift detection, cost estimate. | Click-ops resources, a single environment, manual applies. |
| L08-R7 | **Resilience & data safety** | Tested backup/restore. Graceful degradation when a dependency fails. | Disaster recovery with RPO/RTO targets met in a drill. | Untested backups, cascading failures. |
| L08-R8 | **Architecture documentation** | C4 diagrams, ≥ 5 meaningful ADRs, onboarding guide that works. | Docs kept in sync via CI (diagrams as code). | Outdated diagrams, ADRs written after the fact with no alternatives. |
