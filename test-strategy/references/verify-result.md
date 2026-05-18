# Verify Result

Use this reference before claiming a code change is complete.

## Verification Order

1. Run targeted commands from the test decision or canonical test plan.
2. Run expanded commands only when targeted evidence is insufficient.
3. Run full commands only when the plan calls for them or the blast radius justifies it.
4. Use recent trustworthy CI or terminal output when available.
5. Mark commands as `not run` when they cannot be executed and explain why.

Do not fabricate manual checks. If nobody performed a manual check, mark it as `not run`, `not needed`, or `not provided`.

## Output Shape

```md
## Verification Evidence

Checked commands:

- `command`: pass | fail | not run
  - Evidence: ...

Manual checks:

- `check`: pass | fail | not needed | not run
  - Evidence: ...

Acceptance criteria:

- [x] ...
- [ ] ...

Boundary/error coverage:

- Boundary Conditions: pass | fail | not covered | not provided
- Error Conditions: pass | fail | not covered | not provided
- Negative Tests: pass | fail | not covered | not provided
- Evidence: ...

Completion conclusion:

- Complete | Not complete | Inconclusive

Remaining risks:

- ...

Next actions:

- ...
```

## Rules

- No real execution evidence means no completion claim.
- New warnings introduced by the change are failures unless explicitly accepted.
- Existing warnings may be recorded as remaining risk, but do not ignore them silently.
- If verification fails, switch to debugging or fix work before finalizing.
