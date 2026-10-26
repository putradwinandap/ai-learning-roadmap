# AI Learning Roadmap

**From your first line of code to enterprise engineering, with an AI mentor that grades your work instead of doing it for you.**

This repo is a free, self-paced curriculum in 10 levels. Each level has lessons, a required project, a rubric, and a quiz. You learn with any AI coding assistant (Claude Code, Cursor, Copilot, Codex, ...). The rules in [`AGENTS.md`](AGENTS.md) make that assistant behave like a strict but helpful **mentor and corrector**: it explains, asks questions, gives hints, reviews your project against the rubric, and decides whether you are ready for the next level. It will not write your project for you.

## Levels

| # | Level | You will learn | You will build |
|---|---|---|---|
| 00 | [Mindset & Tools](levels/00-mindset-and-tools/) | How to learn, terminal, Git/GitHub, editor, using AI correctly | Your fork set up + a first "hello" CLI with clean commits |
| 01 | [Programming Fundamentals](levels/01-programming-fundamentals/) | Variables, types, control flow, functions, collections, I/O, files, errors, debugging | A CLI expense tracker that saves to a file |
| 02 | [Data Structures, Algorithms & Clean Code](levels/02-data-structures-algorithms-clean-code/) | Complexity, data structures, recursion, sorting/searching, OOP/FP, naming, unit tests | A library-management CLI with a test suite |
| 03 | [Web Fundamentals](levels/03-web-fundamentals/) | HTTP, HTML/CSS, browser JavaScript, DOM, fetch, accessibility | An interactive web app using a public API |
| 04 | [Backend & Databases](levels/04-backend-and-databases/) | REST, SQL, data modeling, migrations, validation, authentication | A REST API backed by a relational database |
| 05 | [Fullstack Applications](levels/05-fullstack-applications/) | Frontend frameworks, auth flows, state, deployment | A deployed fullstack application |
| 06 | [Software Engineering Practices](levels/06-software-engineering-practices/) | Testing pyramid, CI/CD, Docker, code review, team Git workflow | CI, tests and containers added to your Level 05 app |
| 07 | [System Design & Architecture](levels/07-system-design-and-architecture/) | Scalability, caching, queues, consistency, API design | A design doc + a feature built with cache and queue |
| 08 | [Enterprise Engineering](levels/08-enterprise-engineering/) | Modular monoliths/microservices, observability, security, cloud, IaC, ADRs | A multi-service system with observability, IaC and ADRs |
| 09 | [AI Engineering](levels/09-ai-engineering/) | LLM APIs, prompting, RAG, tool use/agents, evals, cost and safety | A RAG or agent application with an eval suite |

Levels 00–01 are fully written. Levels 02–09 have their goals, project, rubric and quiz bank ready, with topic lists and curated resources for lessons. The full lessons are coming.

## Quick start

1. **Fork** this repo to your GitHub account, then clone your fork:
   ```bash
   git clone https://github.com/<your-username>/ai-learning-roadmap.git
   ```
2. **Open the folder in your AI coding assistant.** It reads [`AGENTS.md`](AGENTS.md) automatically (Claude Code reads it via [`CLAUDE.md`](CLAUDE.md)).
3. **Start onboarding.** In Claude Code, run `/start`. In other tools, type: `Start onboarding`.
   The AI asks for your preferred human language and programming language, then creates `learner/profile.md` and `learner/progress.md`.
4. **Follow the loop for each level:**

   ```text
   /lesson  →  exercises  →  build the project  →  /review-project  →  fix  →  /quiz  →  next level
   ```

Full guide: [docs/how-to-use.md](docs/how-to-use.md).

### Commands (Claude Code)

| Command | What it does |
|---|---|
| `/start` | Onboarding: creates your profile and progress file |
| `/lesson` | Walks you through the next lesson of your active level |
| `/hint` | Gives the next step of the hint ladder, never the full answer |
| `/review-project` | Grades your project against the level rubric and saves a report |
| `/quiz` | Checks your understanding of the level's concepts |
| `/progress` | Shows where you are and what's left to pass the level |

In other tools you can say the same thing in plain words ("review my project", "give me a hint", "quiz me").

## Programming languages

The core of every level is **language-agnostic**: concepts, project spec and rubric apply to any language. On top of that, each level gets **tracks** for specific programming languages, with setup, idiomatic examples, tooling and extra rubric criteria.

| Level | Python | JavaScript | More (TypeScript, Go, Java, C#, PHP, ...) |
|---|---|---|---|
| 00 | ✅ | ✅ | planned |
| 01 | ✅ | ✅ | planned |
| 02–09 | planned | planned | planned |

No track for your language yet? You can still use it. The AI falls back to the core content and its own knowledge of your language's idioms. Want to add one? See [docs/adding-a-track.md](docs/adding-a-track.md).

## Translations

All content is written in **English**, which is the source of truth. The AI **always replies in the language you choose** in your profile, so you can learn in Bahasa Indonesia, Español, or any other language today, even before a translation exists.

| Language | Status |
|---|---|
| English | ✅ source |
| Bahasa Indonesia | planned |
| Others | contributions welcome, see [docs/translating.md](docs/translating.md) |

## Repo layout

```text
AGENTS.md            Rules for the AI mentor/corrector (all tools)
CLAUDE.md            Claude Code entry point (imports AGENTS.md)
ai/                  Detailed AI protocols: hints, reviews, quizzes, level gates, language/track policy
levels/NN-*/         Lessons, project spec, rubric, quiz bank and language tracks per level
learner/             YOUR area: profile, progress, projects, reviews (the only folder you edit)
docs/                Guides for learners and contributors
.claude/commands/    Claude Code slash commands
```

## Principles

- **Consistency over perfection.** A little every day beats a lot once a month.
- **Fundamentals first.** AI engineering is the last level for a reason.
- **AI is your mentor, not your ghostwriter.** If you can't explain your code, you haven't passed.
- **Production-ready, not tutorial-ready.** Every level ends with something real.

Read more: [docs/learning-with-ai.md](docs/learning-with-ai.md) · Why this repo exists: [docs/origin-story.md](docs/origin-story.md)

## Contributing

Fixes, new lessons, new language tracks and translations are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

Content is licensed under [CC BY-SA 4.0](LICENSE).
