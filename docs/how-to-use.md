# How to use this repo

## 1. Get your own copy (fork)

1. Sign in to GitHub and click **Fork** on this repository's page.
2. Clone **your fork**:
   ```bash
   git clone https://github.com/<your-username>/ai-learning-roadmap.git
   cd ai-learning-roadmap
   ```
3. Connect the original repo as `upstream`, so you can get new lessons later:
   ```bash
   git remote add upstream https://github.com/putradwinandap/ai-learning-roadmap.git
   ```

> Want your progress private? GitHub forks of public repos are public. Instead, create a new **private** repo, then `git clone` this one, `git remote rename origin upstream`, add your private repo as `origin`, and `git push -u origin main`.

## 2. Open it in an AI coding assistant

| Tool | How it picks up the rules |
|---|---|
| Claude Code | Reads `CLAUDE.md`, which imports `AGENTS.md`. Slash commands in `.claude/commands/` |
| Cursor, Codex, Windsurf, Aider, ... | Read `AGENTS.md` automatically (or add it as a rule/context file) |
| GitHub Copilot | Reads `.github/copilot-instructions.md` |
| Any chat-based AI | Paste `AGENTS.md` at the start of the conversation and share files as needed |

## 3. Onboard

Run `/start` (Claude Code) or say **"Start onboarding"**. Answer the questions. The AI creates:

- `learner/profile.md`: your name, languages, goals, available time
- `learner/progress.md`: your status per level

Commit them:

```bash
git add learner
git commit -m "Start learning journey"
git push
```

## 4. The learning loop

For each level:

```text
/lesson ─► exercises ─► build the project ─► /review-project ─► fix ─► /quiz ─► next level
   ▲                         │
   └──────── /hint ◄─────────┘
```

| Step | What you do | What the AI does |
|---|---|---|
| Learn | `/lesson` | Teaches the next lesson in small chunks, gives an exercise, checks understanding |
| Practise | Do the exercises yourself | Explains, compares with your attempt afterwards |
| Build | Write the project in `learner/level-NN/project/` | Gives hints on request, never the solution |
| Review | `/review-project` | Runs your project, scores the rubric, asks you to explain your code, saves a report |
| Quiz | `/quiz` | 10 questions, one at a time, saves a report |
| Level up | Pass the [gate](../ai/level-gate.md) | Updates `progress.md` and congratulates you |

Check where you stand any time with `/progress`.

## 5. Daily routine (suggestion)

1. `git pull` (in case you worked on another machine).
2. `/progress` to see your next step.
3. Work 45–90 minutes.
4. Write 3–5 bullets in `learner/level-NN/notes.md`.
5. Commit and push.

## 6. Getting curriculum updates

```bash
git fetch upstream
git merge upstream/main
git push
```

Because you only edit `learner/`, this merges without conflicts. New lessons, tracks and translations show up automatically.

## 7. Optional: track tasks with GitHub Issues

Use the **Level progress** issue template in your fork (Issues → New issue) to get a checklist per level, and close it when you pass. Add a GitHub Project board for a kanban view.

## FAQ

**Can I skip levels?** You can go straight to a level's project and quiz if you already know the material, but levels are passed in order.

**Can I change programming language?** Yes, per level. Tell the AI, and it records it in `progress.md`.

**The AI wrote code for my project anyway. What now?** Don't use it. Delete it and tell the AI to follow `AGENTS.md`. You'll be asked to explain your code in the review anyway.

**I found a mistake in a lesson.** Please open an issue or PR upstream. See [CONTRIBUTING.md](../CONTRIBUTING.md).
