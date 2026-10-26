# learner/: your workspace

This is the **only folder you edit** in your fork. Everything else (levels, AI rules, docs) comes from the upstream repo, and keeping your work in here means updates merge without conflicts.

## What goes here

```text
learner/
├── profile.md            # Who you are, which languages you use (created by /start)
├── progress.md           # Your status per level (updated by the AI after reviews and quizzes)
└── level-NN/
    ├── project/          # YOUR code for the level's project (the AI never edits this)
    ├── notes.md          # Your own notes (optional)
    ├── reviews/          # Review reports written by the AI
    └── quizzes/          # Quiz reports written by the AI
```

Use two digits for the level folder: `level-00`, `level-01`, ... `level-09`.

## Onboarding

Run `/start` (Claude Code) or say "Start onboarding" in any AI tool. The AI asks you a few questions and creates `profile.md` and `progress.md` from the templates here:

- [`profile.template.md`](profile.template.md)
- [`progress.template.md`](progress.template.md)

You can also copy the templates yourself and fill them in.

## Bigger projects

From Level 05 on, projects can get large. You may keep them in a separate repository. Set `project_location` in `progress.md` to its local path (for example `../my-fullstack-app`) and link the GitHub repo, so the AI knows where to look.

## Commit often

Your commit history is part of your learning record, and Level 00 grades it. Commit after each lesson, each meaningful project step, and each review.
