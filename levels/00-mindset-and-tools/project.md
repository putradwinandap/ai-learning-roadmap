# Level 00 project: Hello, Me

Set up your learning environment, write a small interactive program, document it, and publish it with a clean Git history.

**Location:** `learner/level-00/project/` (code + README) and `learner/level-00/notes.md` (plan and reflection).

## Requirements

### Must (all required to pass)

| ID | Requirement |
|---|---|
| L00-M1 | You've onboarded: `learner/profile.md` and `learner/progress.md` exist and are filled in. |
| L00-M2 | A program in `learner/level-00/project/` that **asks for the user's name** and prints a **personalised greeting** that includes at least **one computed detail** (for example, the number of letters in their name, the current day of the week, or a greeting that depends on the time of day). |
| L00-M3 | `learner/level-00/project/README.md` explains what the program does and the **exact commands** to run it, including the required language version. |
| L00-M4 | At least **3 commits** touching `learner/level-00/` with meaningful, imperative messages, **pushed** to your fork on GitHub. |
| L00-M5 | `learner/level-00/notes.md` contains (a) your **weekly study plan** (days, times, durations) and (b) a short **reflection on how you'll use AI** while learning, and what you won't use it for. |

### Should (expected for a good score)

| ID | Requirement |
|---|---|
| L00-S1 | The program handles an **empty name** sensibly (asks again, or uses a friendly default). |
| L00-S2 | A `.gitignore` keeps junk (OS files, editor folders, caches) out of the repo. |
| L00-S3 | Code is formatted with your track's formatter. Names are clear. |

### Stretch (optional)

| ID | Requirement |
|---|---|
| L00-X1 | The name can also be passed as a **command-line argument** (`... run hello Ana`). |
| L00-X2 | The user can choose the greeting language (for example English or Bahasa Indonesia). |
| L00-X3 | You created a GitHub profile README introducing yourself as a learner. |

## Acceptance scenarios

The reviewer will try at least these:

1. Run the program using exactly the commands in your README → it asks for a name.
2. Enter `Ana` → the greeting mentions `Ana` plus a computed detail.
3. Press Enter without typing a name → no crash (S1).
4. `git log --oneline -- learner/level-00` shows ≥ 3 meaningful commits, and they're visible on GitHub.

## Deliverables checklist

- [ ] `learner/profile.md`, `learner/progress.md`
- [ ] `learner/level-00/project/<your program>`
- [ ] `learner/level-00/project/README.md`
- [ ] `learner/level-00/notes.md` with study plan + AI reflection
- [ ] Commits pushed to your fork

When you're done, run `/review-project`.
