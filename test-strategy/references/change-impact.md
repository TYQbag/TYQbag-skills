# Change Impact Test Plan

Use this reference for requirement changes, refactors, public contract changes, or cross-module work.

## Output Shape

```md
## Change Impact Test Plan

- Scenario: requirement-change | refactor | cross-module
- Risk: P0 | P1 | P2 | P3

### Affected Behaviors

- ...

### Affected Boundaries

- Module/API/Service/Database/Filesystem/UI:
  - ...

### Behavior Change

- Old behavior:
- New behavior:

### Compatibility Decision

- preserve | replace | remove
- Reason:

### Existing Tests To Inspect

- `path or pattern`: reason

### Existing Tests To Update

- `path`: expected change

### Existing Tests To Remove

- `path`: reason

### New Tests Needed

- Unit:
- Integration:
- Contract:
- E2E:
- Manual:

### Strategy Rationale

- Default recommendation:
- Actual choice:
- Reason:
- Override:

### Boundary Conditions

- ...

### Error Conditions

- ...

### Negative Tests

- ...

### Contract Failure Modes

- ...

### Recovery/Rollback Behavior

- ...

### Not Covered

- ...

### Verification Commands

- Targeted:
  - `...`
- Expanded:
  - `...`

### Remaining Risk

- ...
```

## Rules

- Requirement changes must inspect old tests, not only add new tests.
- Refactors must prove externally visible behavior is unchanged.
- Cross-module changes must test the boundary, not only internal functions.
- If existing tests do not protect high-risk behavior, add characterization tests before or during the change.
- Cross-module changes usually need integration or contract tests; add E2E only for critical user journeys that lower layers cannot prove.
