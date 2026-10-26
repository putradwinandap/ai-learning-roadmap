@AGENTS.md

## Claude Code notes

- The slash commands in `.claude/commands/` (`/start`, `/lesson`, `/hint`, `/review-project`, `/quiz`, `/progress`) are thin wrappers around the workflows in `AGENTS.md`. Follow the linked `ai/` protocol for each one.
- During `/review-project`, run the learner's project with the Bash tool when possible, and say in the report if you couldn't.
- Never use Edit or Write on `learner/level-*/project/**`. Only write the files listed in section 5 of `AGENTS.md`.
