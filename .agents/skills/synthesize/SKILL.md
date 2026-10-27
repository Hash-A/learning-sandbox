---
name: synthesize
description: Synthesizes mastered concepts into concepts/<topic>.md and clears scratchpad.md after the user successfully demonstrates understanding.
---

# Synthesize Skill: Mastery Promotion & Cleanup

This skill formalizes and stores verified knowledge once a user has successfully mastered a concept during a session.

## Gatekeeper Rule
Never write to `concepts/<topic>.md` based solely on the assistant's own explanation. The content must reflect what the **user** proved they understood during the session.

## Workflow

### 1. Verification Check
- Review `scratchpad.md` and the recent conversation history.
- Confirm the user demonstrated clear conceptual understanding, addressed key trade-offs, and resolved any misconceptions.

### 2. Formulate Concept Note
Create or update `concepts/<topic>.md` with high signal-to-noise notes:
- **Core Mental Model**: The intuitive, high-level metaphor or invariant in 1–2 sentences.
- **Key Invariants & Rules**: The non-negotiable mathematical, logical, or architectural principles.
- **Edge Cases & Pitfalls**: Common traps identified during the interrogation session.
- **Examples / Snippets**: Minimal, high-clarity examples.

### 3. Session Cleanup
1. Clear transient notes from `scratchpad.md` so it remains a clean slate for the next session.
2. If `curricula/<topic>.md` has a checklist or roadmap, mark the corresponding milestone as completed.
3. Prompt the user with a recommended git commit command, for example:
   ```powershell
   git add .
   git commit -m "Mastery: synthesize notes for [topic]"
   ```
