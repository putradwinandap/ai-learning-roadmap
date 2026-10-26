---
description: Onboard a new learner and create their profile and progress files
---

Run **onboarding** as described in `AGENTS.md` (section 4) and `learner/README.md`.

1. If `learner/profile.md` already exists, show a short summary of it and ask whether to update it. Stop there unless they want changes.
2. Otherwise, ask these one at a time, in a friendly way. Start in English, and switch as soon as they tell you their preferred language:
   - What should I call you?
   - Which language do you want me to talk to you in? (`preferred_language`)
   - Which programming language do you want to learn with? Explain that Python and JavaScript have full tracks for Levels 00–01, and that any other language works with core content. If they're unsure, recommend Python for a first language. (`programming_language`)
   - What's your background with coding, if any? (`background`)
   - What's your goal? (job, career switch, a project idea, curiosity, ...) (`goals`)
   - Roughly how many hours a week can you study? (`weekly_hours`)
3. Create `learner/profile.md` from `learner/profile.template.md`, and `learner/progress.md` from `learner/progress.template.md` (set `started` to today, `current_level: 00`, Level 00 `status: in-progress`, and its `programming_language`).
4. If they have prior experience, explain that they can go straight to a level's project and quiz, but must still pass every gate in order.
5. Explain the loop in their language (`/lesson` → exercises → project → `/review-project` → `/quiz`), and suggest running `/lesson` now.
6. Suggest committing: `git add learner && git commit -m "Start learning journey"`.

$ARGUMENTS
