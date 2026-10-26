# Level 04 quiz bank

See [ai/quiz-protocol.md](../../ai/quiz-protocol.md).

## 1. REST & HTTP APIs
- Design the URLs and methods for "list RSVPs of an event" and "cancel my RSVP".
- 401 vs 403. 400 vs 422. When to use 409?
- What does idempotent mean? Which methods are idempotent?

## 2. Relational modelling & SQL
- Model a many-to-many relationship. Why is a join table needed?
- *Predict:* rows returned by an INNER JOIN vs a LEFT JOIN on sample tables.
- Write (in words or SQL) a query for "events with more than 10 going RSVPs".
- What does NULL = NULL return in SQL?

## 3. Data access
- What is SQL injection? *Spot the bug:* a query built with string concatenation.
- What is the N+1 query problem and how do you fix it?
- ORM vs query builder vs raw SQL: trade-offs.

## 4. Indexes & transactions
- What does an index speed up, and what does it cost?
- Explain ACID in one sentence each.
- *Apply:* two requests take the last seat at the same time. What can go wrong, and two ways to prevent it?

## 5. Auth
- Why hash passwords instead of encrypting them? Why bcrypt/argon2 instead of SHA-256?
- Sessions vs JWT: trade-offs.
- What do the `HttpOnly`, `Secure` and `SameSite` cookie flags do?
- Authentication vs authorization.

## 6. Config, validation, testing
- Why keep configuration in environment variables?
- Why validate at the boundary?
- Why should integration tests use a separate database?
