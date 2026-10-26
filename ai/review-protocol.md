# Review protocol

Use this for `/review-project` or "review my project". A review is the main way a learner proves they've mastered a level, so be thorough, fair and specific.

## 0. Before you start

- Read `learner/profile.md` and `learner/progress.md`. Note the active level and the `programming_language` used for this level.
- Load `levels/NN-*/project.md`, `levels/NN-*/rubric.md` and, if present, `levels/NN-*/tracks/<language>/rubric-addon.md`.
- Find the project: `learner/level-NN/project/`, or the `project_location` in `progress.md` (for example, a separate repo the learner cloned next to this one).
- If you can't find the project, ask for it. Don't guess.

## 1. Check the deliverables

Go through every item in `project.md`:

- **Must** (`LNN-M*`): required to pass. Mark each ✅ met / ⚠️ partial / ❌ missing.
- **Should** (`LNN-S*`): expected. Missing ones lower rubric scores but don't block the gate on their own.
- **Stretch** (`LNN-X*`): optional. Mention them only to praise.

## 2. Run it

- If you can execute code, run the project exactly as its README says. Try the acceptance scenarios from `project.md`, plus at least two edge cases of your own (empty input, invalid input, missing file, ...).
- Run its tests and linter if the level or track requires them.
- If you can't execute code, say so explicitly in the report and review by reading. Never claim something runs without running it.

## 3. Score the rubric

Score every criterion in `rubric.md` (and `rubric-addon.md`) on this scale:

| Score | Meaning |
|---|---|
| 0 | Missing, or not attempted. |
| 1 | Attempted, but mostly broken or misunderstood. |
| 2 | Partly works. Clear gaps against the "meets" description. |
| 3 | **Meets** the description for this level. |
| 4 | **Exceeds** it: noticeably cleaner, more robust or more thoughtful than required. |

Rules:
- Each score needs **evidence**: `file:line`, a command and its output, or a short quote.
- Judge against *this level's* expectations. Don't penalise a Level 01 project for lacking things taught in Level 06.
- Judge idioms against the learner's programming language. A `for` loop is fine in Python, but it's not idiomatic to write a Java-style getter for everything.
- Be consistent: the same code gets the same score regardless of how nicely the learner asks.

## 4. Understanding check

Pick **3** specific parts of *their* code (a function, a decision, a tricky line) and ask the learner to explain them in their own words: what it does, why they wrote it that way, and what would happen if X changed.

- Ask the questions, **wait for answers**, then judge each one: ✅ clear / ⚠️ shaky / ❌ can't explain.
- Passing needs at least 2 ✅ and no ❌.
- If the learner can't explain code they submitted, treat it as a sign it wasn't written by them. Score `understanding_check` as failed, explain why kindly, and suggest they rebuild that part themselves.

## 5. Write the report

Save it to `learner/level-NN/reviews/YYYY-MM-DD.md` using [`templates/review-report.md`](templates/review-report.md). If a review already exists for that date, add `-2`, `-3`, ... to the filename. Write the report in the learner's `preferred_language`. Keep IDs (`L01-R3`) unchanged.

The report must include:
- Deliverables checklist (Must/Should/Stretch).
- Rubric table with score + evidence per criterion, and the average.
- **Strengths**: 2–4 specific things done well.
- **Must fix**: everything blocking the gate, in priority order. Describe the problem, not the solution code.
- **Suggestions**: non-blocking improvements and what to research.
- Understanding check questions, answers and verdicts.
- Gate verdict (see [`level-gate.md`](level-gate.md)).

## 6. Update progress

In `learner/progress.md`, update the level's `status`, `last_review`, `rubric_average` and `understanding_check`. If the gate passes once the quiz is also done, follow the "Passing a level" steps in [`level-gate.md`](level-gate.md).

## 7. Re-reviews

After the learner fixes things, run a full new review (new report file). Focus on the previous "Must fix" items, but re-score every criterion, because fixes can break other things.
