# Level 00 quiz bank

The AI builds a 10-question quiz from these areas (see [ai/quiz-protocol.md](../../ai/quiz-protocol.md)). Sample questions are examples. Quizzes should vary them.

## 1. Learning method

- Explain the difference between recognition and recall. Why does it matter for programming?
- What is deliberate practice? Name its parts.
- Describe your process when you're stuck on an error.

*Good answer contains:* doing > watching; specific goal, difficulty, feedback, reflection; read the error → expected vs. actual → shrink → search → hint.

## 2. Terminal

- What does `pwd` show? What does `cd ..` do?
- Absolute vs. relative path: give an example of each.
- *Predict:* you're in `/home/ana/code` and run `cd ../notes`. Where are you now?
- Why is `rm` dangerous?

*Good answer contains:* working directory concept; `..` = parent; no recycle bin.

## 3. Git & GitHub

- What's the difference between Git and GitHub?
- Explain working directory → staging → commit.
- *Spot the bug:* someone runs `git commit -m "update"` after `git add .` in a folder with a `.env` file. What are the two problems?
- `origin` vs `upstream` in a fork.
- What makes a good commit message?

*Good answer contains:* Git is local, GitHub is a remote host; snapshot with a message; secrets must never be committed; imperative, specific messages.

## 4. Editor & environment

- Editor vs. runtime vs. compiler.
- Formatter vs. linter.
- Why turn off AI autocomplete for graded projects?

## 5. Learning with AI

- What is the "ghostwriter trap"?
- Turn a bad question into a good one (goal, what you tried, what happened, expected).
- Two ways to verify an AI answer.

## 6. First program

- Identify input, processing and output in a short program.
- *Predict:* (in the learner's language) a program that reads a name and prints `"Hi " + name + "!"`. What does it print for `Bo`?
- *Spot the bug:* a short program with a missing quote or a misspelled variable. What error would you see, and where?
