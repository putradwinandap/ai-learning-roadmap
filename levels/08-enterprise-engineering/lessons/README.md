# Level 08 topics

Full lesson files are planned. Until then, your AI mentor teaches these topics in order (`/lesson`), using the resources below.

| # | Topic | Key ideas |
|---|---|---|
| 01 | Domain-driven design | Ubiquitous language, bounded contexts, aggregates, context maps |
| 02 | Modular monolith vs microservices | Module boundaries, enforcing them, when to split, the distributed-monolith trap |
| 03 | Service communication | REST vs gRPC, async events, schemas and versioning, API gateways |
| 04 | Event-driven architecture | Event brokers (Kafka, RabbitMQ, cloud queues), event sourcing and CQRS (when *not* to use them), sagas |
| 05 | Observability | Structured logging, metrics (RED/USE), distributed tracing with OpenTelemetry, dashboards |
| 06 | SLOs & alerting | Error budgets, burn-rate alerts, on-call basics, incident response, blameless postmortems |
| 07 | Enterprise security | Threat modelling (STRIDE), OWASP ASVS, OAuth 2.0/OIDC, SSO, RBAC/ABAC, secrets management, audit logs |
| 08 | Multi-tenancy | Isolation models (shared schema, schema per tenant, DB per tenant), tenant-aware authz, noisy neighbours |
| 09 | Cloud fundamentals | Compute options (VMs, containers, serverless), managed services, networking, IAM, cost awareness |
| 10 | Infrastructure as Code | Terraform/OpenTofu or Pulumi, state, modules, environments, policy as code |
| 11 | Kubernetes essentials | Pods, deployments, services, config/secrets, probes, when K8s is overkill |
| 12 | Data protection & compliance | PII, encryption at rest/in transit, retention, GDPR-style rights, backups and disaster recovery |
| 13 | Architecture documentation | C4 model, ADRs, runbooks, tech radar |
| 14 | Engineering at scale | Team topologies, ownership, platform engineering, inner source |

## Resources

- *Domain-Driven Design Distilled*, by Vaughn Vernon (book) · [DDD Crew on GitHub](https://github.com/ddd-crew)
- *Building Microservices*, 2nd ed., by Sam Newman (book)
- [OpenTelemetry documentation](https://opentelemetry.io/docs/)
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/)
- [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/) · [OWASP Threat Modeling](https://owasp.org/www-community/Threat_Modeling)
- [OAuth 2.0 simplified](https://www.oauth.com/)
- [Terraform tutorials](https://developer.hashicorp.com/terraform/tutorials) · [OpenTofu docs](https://opentofu.org/docs/)
- [Kubernetes basics tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [The C4 model](https://c4model.com/)
- [Team Topologies](https://teamtopologies.com/key-concepts)
