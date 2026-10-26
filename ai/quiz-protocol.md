# Quiz protocol

Use this for `/quiz` or "quiz me". A quiz checks that the learner understands the level's **concepts**, not just that their project works.

## 1. Build the quiz

- Read `levels/NN-*/quiz-bank.md`. It lists concept areas, sample questions and what a good answer contains.
- Write **10 questions** that cover every concept area at least once. Don't copy the sample questions word for word. Vary them so the quiz can be retaken.
- Mix question types:
  - **Explain** (≈4): "In your own words, what is ...? When would you use it?"
  - **Predict** (≈3): show a short snippet *in the learner's programming language* and ask what it prints or does.
  - **Spot the bug** (≈2): a short snippet with one bug. Ask what's wrong and why.
  - **Apply** (≈1): a small scenario. "How would you approach ...?" Plain-language answers are fine.
- Write the quiz in the learner's `preferred_language`. Code stays in the programming language.

## 2. Run it

- Ask **one question at a time** and wait for the answer. Don't reveal correct answers until the quiz is over.
- Don't give hints during the quiz. If the learner says "I don't know", record it and move on.
- The learner should answer without looking things up. You can't enforce this, but say it once at the start.

## 3. Grade it

Each question is worth 0, 0.5 or 1 point:
- **1**: correct and shows understanding.
- **0.5**: partly right, or right with a notable misconception.
- **0**: wrong, or no answer.

Judge understanding, not wording. A short correct answer gets 1 point. A long answer that's vague gets 0.5 at most.

**Pass mark: 7 / 10 (70%).**

## 4. Report

After the last question:
1. Show the score and, for each question, the correct idea plus feedback on their answer.
2. List the concept areas that need review, with links to the lessons.
3. Save the report to `learner/level-NN/quizzes/YYYY-MM-DD.md` using [`templates/quiz-report.md`](templates/quiz-report.md).
4. Update `quiz_score` for the level in `learner/progress.md` with the best score so far.

## Retakes

- Allowed at any time, but suggest reviewing the weak areas first.
- Always generate a fresh set of questions.
