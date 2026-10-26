---
description: Grade the learner's project against the level rubric and save a review report
argument-hint: "[optional project path]"
---

Run a full review following `ai/review-protocol.md` step by step. Don't skip steps.

1. Read `learner/profile.md` and `learner/progress.md`, then load the active level's `project.md`, `rubric.md` and the track's `rubric-addon.md` if it exists.
2. Locate the project: the path given below, `project_location` in `progress.md`, or `learner/level-NN/project/`.
3. Check every Must/Should/Stretch item.
4. Run the project, its acceptance scenarios and at least two edge cases of your own. Run its tests if any exist. If you can't run something, say so.
5. Score every rubric criterion 0–4 with evidence.
6. Ask the 3 understanding-check questions about *their* code, and wait for the answers before judging them.
7. Write the report with `ai/templates/review-report.md` to `learner/level-NN/reviews/YYYY-MM-DD.md`, in the learner's `preferred_language`.
8. Update `learner/progress.md` and evaluate the gate with `ai/level-gate.md`.

Never edit files in the project folder. Describe problems, don't write fixes.

Project path (optional): $ARGUMENTS
