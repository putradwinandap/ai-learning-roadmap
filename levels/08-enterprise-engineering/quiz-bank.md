# Level 08 quiz bank

See [ai/quiz-protocol.md](../../ai/quiz-protocol.md).

## 1. DDD & architecture
- What is a bounded context? How does it help large teams?
- Modular monolith vs microservices: name three costs of microservices.
- What is a "distributed monolith"?

## 2. Integration
- REST vs gRPC vs async events: when to use each.
- How do you version an event schema without breaking consumers?
- What is a saga? Orchestration vs choreography.
- When is event sourcing/CQRS *not* worth it?

## 3. Observability & operations
- Logs vs metrics vs traces: what question does each answer?
- RED vs USE metrics.
- What is an error budget? What is a burn-rate alert?
- What makes a postmortem "blameless", and why does it matter?

## 4. Security
- Walk through STRIDE with one example threat per letter for Gather.
- OAuth 2.0 vs OIDC. What is an ID token?
- RBAC vs ABAC.
- Why do audit logs need to be tamper-evident?

## 5. Multi-tenancy & data
- Compare three tenant isolation models.
- *Spot the bug:* an endpoint that reads `tenantId` from the request body.
- RPO vs RTO. Why must backups be tested?
- What counts as PII? Name two techniques to protect it.

## 6. Cloud & IaC
- Why Infrastructure as Code? What is Terraform state, and why must it be protected?
- What is configuration drift?
- When is Kubernetes overkill?
