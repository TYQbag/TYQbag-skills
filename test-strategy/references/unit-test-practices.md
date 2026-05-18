# Unit Test Practices

Use this reference when writing, updating, or reviewing unit tests.

## What To Test

- Public behavior and stable contracts.
- Pure logic, validation, parsing, formatting, calculations, reducers, permission rules, state machines, and data mapping.
- Boundary values, invalid inputs, error paths, and negative cases.
- A bug's minimal reproduction when adding a regression test.

## What Not To Test

- Private implementation details.
- Internal state variable names or private function call order.
- Framework behavior.
- Trivial getters/setters or pass-through wrappers.
- Snapshots that only lock incidental structure.
- Tests that exist only to raise coverage numbers.

## Structure

- Use Arrange / Act / Assert or an equivalent clear pattern.
- Keep one test focused on one behavior.
- Name tests by the business behavior they protect, not by implementation mechanics.
- Prefer table-driven tests for pure functions with many input/output cases.
- Keep fixtures minimal and meaningful.

## Mocking

- Mock external boundaries: network, database, filesystem, clock, random values, third-party services, browser/device capabilities.
- Do not mock the system under test.
- Avoid mocking internal collaborators just to simplify assertions.
- Keep mocks behaviorally realistic enough to fail when the contract breaks.

## Assertions

- Assert observable outcomes.
- Use precise assertions for important behavior and looser assertions for irrelevant details.
- Avoid assertions that depend on incidental ordering, CSS class names, DOM structure, or private calls unless those are the contract.
- For async code, wait for observable completion. Do not rely on fixed sleeps.

## Regression Tests

- A regression test should fail before the fix and pass after the fix.
- Keep the failing scenario minimal.
- Preserve the real trigger condition when possible.
- Do not weaken existing assertions to make the fix easier.

## Maintainability

- Remove duplicated setup into small helpers only when it improves readability.
- Do not hide important behavior in clever factories.
- Fix flaky tests by removing nondeterminism, not by adding arbitrary timeouts.
- When a test becomes hard to write, reassess the unit boundary before adding more mocks.
