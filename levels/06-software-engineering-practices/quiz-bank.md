# Level 06 quiz bank

See [ai/quiz-protocol.md](../../ai/quiz-protocol.md).

## 1. Testing
- Explain the testing pyramid. Why fewer E2E tests than unit tests?
- Mock vs stub vs fake.
- What makes a test flaky? Name two causes and fixes.
- Why is 100% coverage not a goal in itself?

## 2. Docker
- Image vs container.
- Why use multi-stage builds?
- *Spot the problem:* a Dockerfile that copies the whole repo before installing dependencies (cache busting), runs as root, and includes `.env`.
- What does a Compose health check give you?

## 3. CI/CD
- Continuous integration vs continuous delivery vs continuous deployment.
- What does "build once, deploy many" mean?
- Where should deployment secrets live?
- How do you run DB migrations safely during a deploy?

## 4. Git workflow & review
- Trunk-based development vs GitFlow.
- Merge vs rebase: what changes in the history?
- What makes a good PR? What do you look for when reviewing?
- What is a conventional commit? How does it relate to semantic versioning?

## 5. Dependencies
- What does a lockfile guarantee?
- Explain MAJOR.MINOR.PATCH.
- What is a supply-chain attack? One mitigation.

## 6. Docs & legacy code
- What is an ADR and why keep them?
- What is a characterisation test?
