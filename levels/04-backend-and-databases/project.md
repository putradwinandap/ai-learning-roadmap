# Level 04 project: Gather

A **REST API** where users create events and others RSVP, with capacity limits and authentication.

**Location:** `learner/level-04/project/`

## Domain

- **User**: email, name, password (hashed).
- **Event**: title, description, start time, location, capacity, organiser (a user).
- **RSVP**: a user attending an event, with status `going` / `waitlisted` / `cancelled`.

## Requirements

### Must

| ID | Requirement |
|---|---|
| L04-M1 | **Auth**: register, log in, log out (or token expiry). Passwords hashed with bcrypt, scrypt or argon2. |
| L04-M2 | **Events CRUD**: anyone can list and view. Only logged-in users create. Only the organiser can update or delete. |
| L04-M3 | **RSVP**: a logged-in user can RSVP and cancel. When the event is full, new RSVPs are `waitlisted`. When someone cancels, the first waitlisted user is promoted. |
| L04-M4 | **Relational schema** with primary keys, foreign keys and constraints (e.g. unique user+event RSVP), created via **migrations**. |
| L04-M5 | **Pagination and filtering** on the event list (e.g. upcoming only, by date range or keyword). |
| L04-M6 | **Validation** of all input, with a consistent JSON error format and correct status codes (400, 401, 403, 404, 409, 422 as appropriate). |
| L04-M7 | **No SQL injection**: parameterised queries or a query builder/ORM everywhere. |
| L04-M8 | **Concurrency-safe capacity**: two simultaneous RSVPs for the last seat can't both become `going` (transaction, lock or constraint). |
| L04-M9 | **Config via environment variables**. No secrets in the repo. A `.env.example` is provided. |
| L04-M10 | **Integration tests** for auth, permissions, RSVP/waitlist logic and validation, run against a test database. ≥ 25 tests, all passing. |
| L04-M11 | **API documentation**: OpenAPI/Swagger spec, or a complete endpoints table in the README with example requests and responses. |
| L04-M12 | README: setup (database, migrations, seed), run, test, and environment variables. |

### Should

| ID | Requirement |
|---|---|
| L04-S1 | Seed script with realistic sample data. |
| L04-S2 | Database indexes for the main queries, with a note on why. |
| L04-S3 | Structured request logging (method, path, status, duration). |
| L04-S4 | Rate limiting on login. |
| L04-S5 | Layers separated: routes/controllers → services (business rules) → data access. |

### Stretch

| ID | Requirement |
|---|---|
| L04-X1 | Event attendee export as CSV (organiser only). |
| L04-X2 | Email verification or password reset flow (emails logged to the console are fine). |
| L04-X3 | ETags or caching headers on event list and detail. |

## Acceptance scenarios

1. Fresh clone → follow the README → the API runs and the tests pass.
2. Register, log in, create an event with capacity 2. Three users RSVP → 2 `going`, 1 `waitlisted`. One cancels → the waitlisted user is promoted.
3. A non-organiser tries to edit the event → 403. No token → 401.
4. Invalid payloads (missing title, negative capacity, past start date) → 400 or 422 with field-level errors.
5. A search term like `' OR 1=1 --` → treated as plain text.
6. The password hash in the DB is not the plain password.
