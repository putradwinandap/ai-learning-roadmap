# Level 08 project: Gather for Organisations

Companies want to use Gather internally: each **organisation** (tenant) has its own members, private events, SSO login, admins, audit trail and usage reports. Evolve Gather into an enterprise-grade system.

**Location:** your Gather repo (or a new one), recorded in `progress.md`.

## Requirements

### Must

| ID | Requirement |
|---|---|
| L08-M1 | **Domain model & boundaries**: a context map identifying at least 3 bounded contexts (e.g. Identity & Access, Events, Notifications, Reporting). Implemented as a **modular monolith with enforced module boundaries**, or as **≥ 3 services**. Justified in an ADR. |
| L08-M2 | **Multi-tenancy**: organisations with isolated data. Every query is tenant-scoped. Tests prove one tenant can't read another's data. |
| L08-M3 | **Identity**: login via OIDC (e.g. Keycloak, Auth0, Entra ID, Google), with roles (org admin, organiser, member) enforced server-side. |
| L08-M4 | **Async integration**: at least one cross-context flow uses events through a broker (e.g. "RSVP confirmed" → Notifications and Reporting), with versioned event schemas. |
| L08-M5 | **Observability**: structured JSON logs with correlation/trace IDs, metrics (RED for each service or module), distributed tracing with OpenTelemetry across the async flow, and a dashboard. |
| L08-M6 | **SLOs & alerts**: at least 2 SLOs with burn-rate alerts, plus a runbook for each alert. |
| L08-M7 | **Security**: STRIDE threat model, an OWASP ASVS Level 1 checklist with status, secrets in a secret manager (not env files in production), an **audit log** of admin and security-relevant actions. |
| L08-M8 | **Infrastructure as Code**: the whole cloud environment (network, compute, database, broker, secrets) provisioned by Terraform/OpenTofu/Pulumi, with separate `staging` and `production` configurations. |
| L08-M9 | **Data protection**: PII inventory, encryption in transit and at rest, a retention policy, a tested backup-and-restore procedure, and a "delete my data" flow. |
| L08-M10 | **Architecture documentation**: C4 diagrams (context, container, component for one part), ≥ 5 ADRs, and an onboarding guide for a new engineer. |
| L08-M11 | CI/CD from Level 06 extended: IaC plan on PR, apply on merge, deployment to staging, then promotion to production. |

### Should

| ID | Requirement |
|---|---|
| L08-S1 | Contract tests or schema registry checks for events and APIs. |
| L08-S2 | Admin usage report per organisation (Reporting context with its own read model). |
| L08-S3 | Policy as code (e.g. OPA/Conftest or cloud policies) checked in CI. |
| L08-S4 | A **game day**: simulate an incident and write a blameless postmortem. |
| L08-S5 | Cost estimate of the infrastructure, with optimisation ideas. |

### Stretch

| ID | Requirement |
|---|---|
| L08-X1 | Deploy on Kubernetes with Helm or Kustomize, including probes, resource limits and autoscaling. |
| L08-X2 | Per-tenant rate limits and quotas (noisy-neighbour protection). |
| L08-X3 | SCIM user provisioning, or SAML in addition to OIDC. |

## Acceptance scenarios

1. Two organisations exist. A user in org A can't see, guess or access org B's events via the UI or the API.
2. Log in via OIDC. An org admin can manage members, a member can't.
3. RSVP → the trace shows the request crossing the broker into the Notifications context. Logs share the trace ID.
4. `terraform plan` (or equivalent) on a fresh account recreates the environment from the code.
5. Restore the database from backup into staging, following the runbook.
6. Trigger an alert condition → the alert fires and the runbook explains what to do.
