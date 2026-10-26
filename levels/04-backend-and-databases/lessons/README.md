# Level 04 topics

Full lesson files are planned. Until then, your AI mentor teaches these topics in order (`/lesson`), using the resources below.

| # | Topic | Key ideas |
|---|---|---|
| 01 | Servers & frameworks | Request/response lifecycle, routing, middleware, choosing a framework for your language |
| 02 | REST API design | Resources, nouns vs verbs, status codes, error format, idempotency, pagination, filtering, versioning |
| 03 | Relational modelling | Tables, primary/foreign keys, 1:N and N:M relationships, normalisation |
| 04 | SQL | SELECT/INSERT/UPDATE/DELETE, JOINs, GROUP BY, subqueries, NULL semantics |
| 05 | Working with a DB from code | Drivers, parameterised queries, SQL injection, query builders vs ORMs, N+1 queries |
| 06 | Migrations & seeding | Schema versioning, forward/backward migrations, seed data |
| 07 | Indexes & transactions | B-tree indexes, EXPLAIN, ACID, isolation levels at a high level, race conditions |
| 08 | Validation & errors | Validating at the boundary, schemas, consistent error responses, logging errors |
| 09 | Authentication | Password hashing (bcrypt/argon2), sessions vs. tokens (JWT), cookies and their flags |
| 10 | Authorization | Ownership checks, roles, least privilege, OWASP API Security Top 10 overview |
| 11 | Configuration & secrets | Environment variables, `.env` files, 12-factor config |
| 12 | API testing | Integration tests against a test database, fixtures, testing auth, OpenAPI docs |

## Framework suggestions per language

| Language | Framework options |
|---|---|
| Python | FastAPI, Flask, Django REST Framework |
| JavaScript/TypeScript | Express, Fastify, Hono, NestJS |
| Go | `net/http` + chi, Gin, Echo |
| Java/Kotlin | Spring Boot, Ktor |
| C# | ASP.NET Core Minimal APIs |
| PHP | Laravel, Symfony |

Database: **PostgreSQL** recommended. SQLite is acceptable for the core project.

## Resources

- [SQLBolt: interactive SQL lessons](https://sqlbolt.com/)
- [PostgreSQL tutorial](https://www.postgresqltutorial.com/)
- [Use The Index, Luke: SQL indexing](https://use-the-index-luke.com/)
- [Microsoft REST API guidelines](https://github.com/microsoft/api-guidelines)
- [OWASP API Security Top 10](https://owasp.org/API-Security/)
- [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
- [The Twelve-Factor App](https://12factor.net/)
