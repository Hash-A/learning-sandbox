---
name: curriculum
description: Scaffolds a progressive learning roadmap into curricula/<topic>.md through an interactive baseline assessment. Use when the user wants to define a new learning target or plan a topic.
---

# Curriculum Skill: Learning Roadmap Architect

This skill guides the creation of a focused, progressive curriculum for any subject, ensuring clear learning goals and dependency ordering.

## Workflow

### 1. Intake & Goal Definition
1. Elicit or extract:
   - The topic name and target depth (e.g., surface familiarity vs production-grade mastery).
   - The concrete end-state objective: What should the user be able to build, explain from first principles, or debug when finished?
   - Any reference materials, papers, official documentation, or code repositories.

### 2. Baseline Probe (Diagnostic Calibration)
Ask 2–3 brief diagnostic questions to identify where the user currently stands:
- Have they used or encountered this concept before?
- Do they understand the foundational prerequisites (e.g., memory models, network primitives, concurrency models)?
- Mark confirmed prerequisites with `[x]` and gaps with `[ ]`.

### 3. Progressive Milestone Decomposition
Structure the curriculum into 3–5 sequential milestones ordered by cognitive dependency:
- **Milestone 1: Core Intuition & Invariants** (The governing mental model and non-negotiable rules).
- **Milestone 2: Mechanics & State Transitions** (Algorithms, lifecycles, and step-by-step operations).
- **Milestone 3: Edge Cases, Failures & Degradation** (Boundary conditions, crash scenarios, race conditions).
- **Milestone 4: Trade-offs & Real-World Alternatives** (Performance profiles, architectural compromises, comparison with alternatives).

### 4. File Generation & Review
1. Save the result to `curricula/<topic>.md` with active checkboxes (`- [ ]`).
2. Present the drafted outline to the user.
3. Invite the user to add, reorder, or prune any milestones before launching the first practice drill.
