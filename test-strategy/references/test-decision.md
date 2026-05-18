# Test Decision

Use this reference before implementation when a change is not obviously trivial.

## Decision Inputs

- Change description.
- Known acceptance criteria.
- Files or modules likely affected.
- Existing test stack and runnable commands discovered from the repository.
- Known risks, unknowns, and constraints.

If one missing fact would materially change the strategy, ask for or discover that fact first.

## Output Shape

```md
## Test Decision

- Scenario:
- Risk:
- Automated tests:
- Recommended test type:
- Primary evidence:
- Reason:

## Test Boundary

- System under test:
- Responsibility covered by this test:
- Responsibilities explicitly not covered:
- Real public entry:
- Allowed mocks:
- Forbidden mocks:

## Required Verification

- Targeted command:
- Manual check:

## Focus Areas

- Boundary Conditions:
- Error Conditions:
- Negative Tests:
```

Only add these sections when needed:

```md
## Test Bootstrap

- Project type:
- Package manager/build tool:
- Existing test stack:
- Missing capability:
- Recommended dependency:
- Config files to add or update:
- First test to create:
- First verification command:
- Risks/notes:
- Conclusion:

## Strategy Override

- Default recommendation:
- Actual choice:
- Reason:
- Substitute verification:
- Remaining risk:
- Evidence gap:

## Automated Test Waiver

- Change type:
- Risk level:
- Existing coverage:
- Verification still required:
```

## Rules

- Prefer existing test tools and commands.
- Do not invent scripts, framework commands, or CI jobs.
- If behavior changes, include at least one boundary, error, or negative case unless there is a clear reason none applies.
- Use the lowest-cost evidence that proves the behavior.
