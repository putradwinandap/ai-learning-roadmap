# 03: Git and GitHub

## Why this matters

**Git** records the history of your code, so you can see what changed, undo mistakes and work with others. **GitHub** hosts Git repositories online. Every professional team uses version control. Here you'll also use it to submit and track your learning.

## Key ideas

### Git vs. GitHub

- **Git** is a program on your computer. It works offline.
- **GitHub** is a website that stores copies of Git repositories ("remotes") and adds collaboration: pull requests, issues, reviews.

### The three areas

```text
working directory  --git add-->  staging area  --git commit-->  repository (history)
   (your files)                  (next snapshot)                (saved snapshots)
```

A **commit** is a snapshot of your project with a message explaining *why* it changed.

### First-time setup

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
```

Use the same email as your GitHub account.

### The everyday loop

```bash
git status                     # what changed? (run this ALL the time)
git add hello.py               # stage a specific file
git add .                      # stage everything in this folder (check status first!)
git commit -m "Add greeting by time of day"
git log --oneline              # see history
git diff                       # see unstaged changes
git push                       # send commits to GitHub
git pull                       # get commits from GitHub
```

### Good commit messages

- One logical change per commit.
- Imperative mood, like a command: "Add input validation", not "added stuff".
- Short summary (≤ 72 characters). Add a blank line and details if needed.

| ❌ Bad | ✅ Good |
|---|---|
| `update` | `Add README with run instructions` |
| `fix` | `Handle empty name input` |
| `asdf` | `Ask for name before printing greeting` |

### `.gitignore`

A `.gitignore` file lists files Git should never track: secrets, dependencies, build output, OS junk.

```gitignore
.DS_Store
Thumbs.db
__pycache__/
node_modules/
.env
```

**Never commit passwords, API keys or `.env` files.** Anything pushed to GitHub should be considered public forever.

### Forks and upstream

You **forked** this curriculum, so you have your own copy on GitHub. To get updates from the original:

```bash
git remote add upstream https://github.com/putradwinandap/ai-learning-roadmap.git   # once
git fetch upstream
git merge upstream/main
```

You only edit `learner/`, so these merges won't conflict.

### Undoing things (safely)

```bash
git restore file.py            # discard unstaged changes to a file
git restore --staged file.py   # unstage, but keep the changes
git commit --amend             # fix the last commit message (only before pushing)
```

## Exercise

1. Configure Git with your name and email.
2. Clone your fork of this repo (if you haven't yet) and add the `upstream` remote.
3. Create `learner/level-00/notes.md` with your notes from lessons 01–02. Commit it with a good message and push.
4. Open your fork on GitHub and find your commit.

## Check your understanding

1. What's the difference between `git add` and `git commit`?
2. Rewrite this commit message to be useful: `changes`.
3. Why must `.env` files never be committed?
4. What's the difference between `origin` and `upstream` in your fork?

## Further reading

- [Pro Git book (free)](https://git-scm.com/book/en/v2), chapters 1–3
- [GitHub Skills: Introduction to GitHub](https://github.com/skills/introduction-to-github)
- [How to write a Git commit message](https://cbea.ms/git-commit/)
