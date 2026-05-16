# Test Plan

Use this reference for features, bugfixes, requirement changes, high-risk work, or any change where the testing approach needs to be explicit before implementation.

## Output Shape

```md
## Test Plan

- Scenario:
- Risk:

### Test Boundary

- System under test:
- Responsibilities covered:
- Responsibilities not covered:
- Real public entry:
- Allowed mocks:
- Forbidden mocks:

### Bugfix Context

- Observed behavior: not applicable unless bugfix
- Expected behavior: not applicable unless bugfix
- Minimal reproduction steps: not applicable unless bugfix
- Root-cause hypothesis: not applicable unless bugfix
- Expected failing behavior before fix: not applicable unless bugfix

### Acceptance Criteria

- [ ] ...

### Required Tests

- Unit:
- Component:
- Integration:
- Contract:
- E2E:
- Manual:

### Strategy Rationale

- Why these layers:
- Why not higher/lower layers:

### Boundary Conditions

- ...

### Error Conditions

- ...

### Negative Tests

- ...

### Recovery Behavior

- ...

### Not Covered

- ...

### Test Files To Add Or Update

- `path`: purpose

### Verification Commands

- Targeted:
  - `...`
- Expanded:
  - `...`
- Full:
  - `...`
```

Then append a canonical plan for later verification:

```md
## Canonical Test Plan

- Scenario:
  - ...
- Acceptance Criteria:
  - [ ] ...
- Boundary Conditions:
  - ...
- Error Conditions:
  - ...
- Negative Tests:
  - ...
- Recovery Behavior:
  - ...
- Not Covered:
  - ...
- Verification Commands:
  - Targeted:
    - `...`
  - Expanded:
    - `...`
  - Full:
    - `...`
- Manual Checks:
  - ...
```

For bugfixes, also include:

```md
- Reproduction Steps:
  - ...
- Root Cause Hypothesis:
  - ...
- Regression Expectation Before Fix:
  - ...
```

## Rules

- Use `not provided` instead of omitting unknown fields.
- A bugfix that can be automated should include a regression test.
- If planning an integration test, define the parent entry point, current responsibility, and what child components/utilities are outside the test's responsibility.
- Keep the plan risk-matched. Avoid large low-value test suites.
