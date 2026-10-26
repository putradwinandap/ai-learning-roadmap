# Contributing

Thanks for helping make this curriculum better. Contributions of every size are welcome: typo fixes, clearer explanations, new lessons, language tracks and translations.

## Ways to contribute

| Contribution | Where | Guide |
|---|---|---|
| Fix a mistake or unclear explanation | any lesson | open a PR directly |
| Write a full lesson for Levels 02–09 | `levels/NN-*/lessons/` | below |
| Add a programming-language track | `levels/NN-*/tracks/<language>/` | [docs/adding-a-track.md](docs/adding-a-track.md) |
| Translate content | next to the English file | [docs/translating.md](docs/translating.md) |
| Improve AI rules | `AGENTS.md`, `ai/` | below |
| Suggest a change to a project or rubric | issue first | below |

## Writing a lesson

Follow the pattern used in Levels 00–01:

```markdown
# NN: Title

> Syntax: [Python](...) · [JavaScript](...)   ← only when tracks exist

## Why this matters
## Key ideas
## Exercise
## Check your understanding
## Further reading (optional)
```

- Teach **concepts** in the core lesson with pseudocode or short neutral examples. Language specifics belong in tracks.
- One idea per section. Short paragraphs. Tables for comparisons.
- Exercises must **not** be the level's project or part of it.
- "Check your understanding" questions feed `/lesson` and should be answerable from the lesson.
- When a level gets its first full lesson files, update the level `README.md` lesson table and keep `lessons/README.md` as an index, or remove it.

## Projects and rubrics

Projects and rubrics define what "passing" means, so changes need discussion. **Open an issue first.** Keep these stable:

- IDs (`LNN-M*`, `LNN-S*`, `LNN-X*`, `LNN-R*`). Never renumber existing IDs, because learners' review reports reference them. Add new ones at the end.
- The 0–4 scale and the gate in [ai/level-gate.md](ai/level-gate.md).

## AI rules

`AGENTS.md` and `ai/` shape how every learner's AI behaves. When changing them:

- Keep them tool-agnostic. Tool-specific notes go in `CLAUDE.md`, `.claude/commands/` or `.github/copilot-instructions.md`.
- Never weaken the core protections: no project solutions, rubric-based grading, the understanding check, honest gating.
- Test your change: run an onboarding, a `/hint` and a `/review-project` on a sample project, and describe the result in your PR.

## Editing the curriculum with an AI assistant

`AGENTS.md` tells the AI it is a mentor for a learner. When you're contributing instead, start your session with something like: *"I'm a contributor editing the curriculum, not a learner. Follow CONTRIBUTING.md."*

## Pull requests

- One topic per PR. Describe what changed and why.
- Check that relative links work.
- Write in clear, simple English. Many readers are non-native speakers.
- By contributing, you agree that your contribution is licensed under [CC BY-SA 4.0](LICENSE).
