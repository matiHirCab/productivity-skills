---
name: plan-then-review
description: Structured planning and iterative self-review for multi-step, drift-prone, cross-file, or refinement-heavy tasks. Use when Codex should plan before executing, keep a sectioned checklist, periodically compare progress against the original request, and choose the lightest planning mode that still keeps the work aligned.
---

# Plan Then Review

Use this skill to keep complex work aligned without turning routine work into bookkeeping.

## Core Behavior

Follow this loop:

1. Restate the goal in operational terms.
2. Choose the lightest planning mode that is still safe.
3. Create or update a sectioned checklist if the chosen mode requires it.
4. Execute the highest-value next action.
5. Review the result against the original request.
6. Update only the working state needed to continue accurately.
7. Repeat until the definition of done is satisfied.

The original prompt is the source of truth. The plan exists to keep the work aligned, not to create extra ceremony.

## Choose a Mode

Pick exactly one mode before starting:

- `light`: Use for short tasks with 1 to 3 meaningful steps, one subsystem, or low drift risk. Keep the plan in working memory unless the user explicitly wants a file.
- `standard`: Default for normal multi-step or multi-file work. Create `plan-then-review.md` using the standard template in `assets/plan-then-review-standard.md`.
- `full`: Use only for long-running, ambiguous, high-risk, or high-drift tasks. Create `plan-then-review.md` using the full template in `assets/plan-then-review-full.md`.

If unsure, choose `standard`.

## Mode Rules

### Light

- Do not create a planning file by default.
- Keep a compact sectioned checklist in working memory or in the conversation.
- Track only:
  - goal
  - next action
  - open risks or blockers
  - done criteria
- Re-check the original prompt before finalizing.

### Standard

- Create `plan-then-review.md`.
- Required sections:
  - Original Prompt
  - Goal
  - Sectioned Checklist
  - Current Focus
  - Progress Log
  - Review Summary
  - Definition of Done
- Keep entries compact and execution-oriented.

### Full

- Create `plan-then-review.md`.
- Use the expanded template only when the task justifies the overhead.
- Add:
  - Checklist Strategy Reasoning
  - Expanded Review Notes
  - explicit risk tracking
- Keep notes concise even in full mode.

## Checklist Rules

When building a checklist:

- Group tasks by phase, subsystem, or dependency boundary.
- Use section subtitles. Do not use a flat list.
- Write actionable steps, not vague reminders.
- Include at least one review section and one verification section.
- Add items only when they materially affect the work.
- Remove or collapse stale items once they are no longer useful.

## Review Rules

After each meaningful milestone, or whenever scope changes:

1. Compare current output with the original request.
2. Identify missing, weak, unclear, or unverified parts.
3. Choose the next highest-value action.
4. Update the checklist and review state to reflect reality.

Do not re-read every note on every pass unless the task changed significantly. Prefer:

- full original prompt at the start
- goal plus latest review summary during normal execution
- full original prompt again before final verification

## Compaction Rules

Keep the planning artifact small enough to stay useful:

- Keep only the latest 5 progress entries plus a short milestone summary when needed.
- In review notes, keep only:
  - open gaps
  - open risks
  - validation status
  - next highest-value action
- Delete or rewrite stale notes instead of appending endlessly.
- Prefer short factual updates over reflective prose.

## Behavioral Rules

- Do not start with `full` mode unless the task clearly needs it.
- Do not require a file for lightweight work.
- Do not generate checklist-structure reasoning unless the mode requires it.
- Do not generate a separate execution-loop prompt file section.
- Do not mark items complete unless they are actually complete.
- Do not continue tracking sections that no longer help execution.
- Prefer concrete progress over process narration.

## Resources

- Standard template: `assets/plan-then-review-standard.md`
- Full template: `assets/plan-then-review-full.md`
- Example mode selection and plan excerpts: `references/examples.md`

Load only the resource needed for the chosen mode.

## Anti-Patterns

Avoid these failures:

- choosing `full` mode for routine work
- writing static checklists that never change
- letting logs grow without compaction
- reviewing against the checklist instead of the original request
- declaring completion because the checklist looks full
- preserving template sections that add no value to the current task

## Definition of Done

The task is done only when:

- the requested deliverable exists
- the result matches the original request
- major gaps and risks are resolved or explicitly called out
- verification is complete for the chosen mode
- the recorded working state matches reality
