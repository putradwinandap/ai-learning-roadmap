# Level gate

A learner passes a level only when **all** of these are true:

| # | Condition | Source |
|---|---|---|
| 1 | Every **Must** item (`LNN-M*`) in `project.md` is ✅ met. | Latest review |
| 2 | Rubric **average ≥ 3.0**, counting core criteria plus track add-on criteria. | Latest review |
| 3 | **No criterion scored below 2.** | Latest review |
| 4 | **Understanding check passed**: at least 2 ✅ and no ❌. | Latest review |
| 5 | **Quiz ≥ 70%** (best attempt). | Quiz reports |

Lessons don't need to be marked done to pass. Someone who already knows the material can go straight to the project and the quiz. Recommend the lessons anyway when a review or quiz shows gaps.

## Statuses in `progress.md`

| Status | Meaning |
|---|---|
| `not-started` | Nothing done yet. |
| `in-progress` | Doing lessons or building the project. |
| `in-review` | At least one review done, gate not passed yet. |
| `passed` | All gate conditions met. |

## Passing a level

When the gate passes:
1. Set the level's `status: passed` and `passed_on: YYYY-MM-DD`.
2. Set `current_level` to the next level and its `status: in-progress`.
3. Ask the learner whether they want to keep the same `programming_language` for the next level, and record it.
4. Congratulate them specifically: name what they now can do that they couldn't before.
5. Suggest a commit: `git add learner && git commit -m "Pass level NN"`.

## `/progress` output

Show:
- Current level and status.
- Lessons done / total.
- Gate checklist with ✅ / ❌ for each of the 5 conditions, plus the numbers.
- The single most useful next step.
