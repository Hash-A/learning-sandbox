---
name: spaced-review
description: Runs a spaced repetition review session from files in reviews/. Identifies cards due for review, quizzes the user, and updates their review interval and next review date.
---

# Spaced Review Skill: Spaced Repetition Engine

This skill turns your `reviews/` folder into an active recall flashcard / quiz runner.

## Workflow

### 1. Identify Due Cards
1. Inspect files in `reviews/` (or a specific `reviews/<topic>.md` if specified by the user).
2. Determine the current date.
3. Scan for cards where `Next Review` <= current date (or cards with no review date recorded yet).
4. Prioritize:
   - Cards in lowest Box / Stage first (Box 1 = highest risk of forgetting).
   - Oldest overdue cards.

### 2. Run Active Recall
1. Present the question / prompt from the card to the user.
   - Do NOT display `Key Insight` or `Common Pitfall`.
2. Await the user's response.
3. Evaluate the answer:
   - **Full Mastery**: If the explanation is swift and accurate:
     - Multiply `Interval Days` by ~2.2 (e.g., 1 -> 3 -> 7 -> 16 -> 35).
     - Increment `Box / Stage` by 1.
     - Set `Last Reviewed` to today, update `Next Review` to `today + Interval Days`.
   - **Partial or Failed**: If the user stumbles, fails, or requires hints:
     - Reset `Interval Days` to 1.
     - Reset `Box / Stage` to 1.
     - Set `Last Reviewed` to today, update `Next Review` to tomorrow.
     - Explain the pitfall and do a quick 30-second follow-up drill.

### 3. Persist State
Update the card metadata in `reviews/<topic>.md` immediately after each card or at the end of the review round.
