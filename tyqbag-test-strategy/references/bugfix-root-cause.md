# Bugfix Root Cause And Regression Strategy

Use this reference for bug reports, failing tests, unexpected behavior, or defects found during verification.

## Investigation Discipline

Do not treat the failing line, visible exception, or last changed code as the root cause by default. Separate:

- Symptom.
- Trigger condition.
- Confirmed facts.
- Assumptions.
- Candidate causes.
- Evidence needed to confirm or reject each cause.
- Root cause versus contributing factor.
- Fix that addresses the root cause versus a temporary mitigation.

## Output Shape

```md
## Bug Analysis

### Symptom

- ...

### Known Facts

- ...

### Candidate Root Causes

- ...

### Investigation Path

- ...

### Most Likely Root Cause

- ...

### Fix Strategy

- ...

### Regression Verification

- Automatable reproduction:
- Regression test to add/update:
- Targeted verification command:
- Related flows to check:
```

## Regression Rules

- If the bug can be reproduced automatically, add or update a regression test.
- Prefer the smallest test that fails before the fix and passes after the fix.
- If the bug happens across module boundaries, use integration or contract testing rather than only unit testing internals.
- If the bug is visual, device-specific, or depends on an unstable external service, document a manual verification path and remaining risk.
- Do not weaken assertions, skip tests, or add timeouts just to make tests pass.
