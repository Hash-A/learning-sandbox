---
name: drill
description: Active recall interrogation and micro-testing on a topic or curriculum. Use when the user asks to drill, quiz, test, or practice a topic.
---

# Drill Skill: Active Interrogation Protocol

This skill guides an interactive, high-retention practice session on a specific subject or topic.

## Workflow

### 1. Scope & Calibration
1. Identify the topic requested by the user.
2. Check if a corresponding file exists in `curricula/<topic>.md` or `concepts/<topic>.md`.
   - If `curricula/<topic>.md` exists, review its learning objectives and prioritize unmastered areas.
   - If `concepts/<topic>.md` exists, check existing mastery notes to avoid redundant entry-level questions.
3. Ask **1–2 quick diagnostic questions** to establish the user's current baseline.

### 2. Tiered Interrogation Loop
Progress through the following levels:
- **Level 1 (Intuition & Invariants)**: Ask for the core "why" and governing rules in the user's own words.
- **Level 2 (Application & Mechanics)**: Present a scenario, small snippet, or architectural puzzle to solve.
- **Level 3 (Edge Cases & Failure Modes)**: Ask where the concept breaks down or what happens under boundary conditions.
- **Level 4 (Comparison & Trade-offs)**: Ask how this compares to alternative techniques/approaches.

### 3. Handling Mistakes
- When the user gives an incorrect or incomplete answer:
  - Do not give the direct answer.
  - Isolate the faulty premise: *"You assumed X, but consider what happens when Y..."*
  - Record the flawed point in `scratchpad.md` under an active working heading.
  - If the user fails after 2 attempts, log a review card directly into `reviews/<topic>.md` using the spaced repetition schema.

### 4. Transitioning
When the user successfully defends their reasoning across the tiers, suggest running the **synthesize** skill to promote their learnings to `concepts/<topic>.md`.
