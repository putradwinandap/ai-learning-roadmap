---
description: Quiz the learner on the active level's concepts and save the result
argument-hint: "[optional level number]"
---

Follow `ai/quiz-protocol.md`.

1. Read `learner/profile.md` and `learner/progress.md`. Use the active level, or the level given below.
2. Build 10 fresh questions from that level's `quiz-bank.md`, covering every concept area, in the learner's `preferred_language`. Code snippets go in their `programming_language`.
3. Ask one question at a time. No hints, no answers until the end.
4. Grade (1 / 0.5 / 0), show the score and feedback, and list the lessons to review.
5. Save the report with `ai/templates/quiz-report.md` to `learner/level-NN/quizzes/YYYY-MM-DD.md`, and update `quiz_score` in `progress.md` if it's the best attempt.
6. Check the gate with `ai/level-gate.md` and tell the learner what's left.

Level (optional): $ARGUMENTS
