# Examples

## Mode Selection

Choose `light` when the task is short and low-risk.

Example:
"Rename a function, update one test, and verify the import path."

Choose `standard` for typical multi-step engineering work.

Example:
"Add a new CLI flag, update parsing, wire it into execution, and document the change."

Choose `full` only when ambiguity, drift risk, or breadth is high.

Example:
"Refactor a multi-file workflow, reconcile conflicting requirements, and iterate until quality issues are resolved."

## Standard Plan Excerpt

```md
## Goal
Add the new CLI flag and keep default behavior unchanged.

## Sectioned Checklist

### 1. Understanding and Scope
- [x] Identify the new flag behavior
- [x] Confirm unchanged default path

### 2. Execution
- [ ] Update argument parsing
- [ ] Wire flag into runtime behavior

### 3. Review and Verification
- [ ] Compare result against original prompt
- [ ] Run targeted validation

## Review Summary
- Open gaps: runtime wiring not complete
- Open risks: help text may drift from actual behavior
- Validation status: parsing checked, end-to-end not yet verified
- Next highest-value action: connect parsed flag to execution path
```

## Full Plan Excerpt

```md
## Checklist Strategy Reasoning

### Why this structure
The task spans discovery, implementation, and repeated verification across multiple files.

### Risk Areas
- Scope misunderstanding: conflicting expectations across related modules
- Missing context or dependencies: implicit shared helpers
- Quality or completeness risk: partial refactor that leaves old paths active

## Expanded Review Notes

### Open Gaps
- Legacy path still bypasses the new workflow in one module

### Open Risks
- Verification does not yet cover fallback behavior

### Validation Status
- Confirmed: main path uses the new workflow
- Not yet validated: fallback path and error handling

### Next Highest-Value Action
- Action: verify fallback behavior and remove the remaining legacy path
- Why now: this is the main unresolved correctness risk
```
