---
name: test-strategy
description: Use when implementing features, fixing bugs, refactoring, changing requirements, deciding whether automated tests are required, planning test coverage, writing or updating tests, or verifying completed code changes across any project.
---

# Test Strategy

Use this skill to decide what testing evidence is needed before, during, and after a code change. Prefer the project's existing test stack and scripts. Do not assume a language, framework, package manager, or command until the repository has been checked.

Core rule:

```text
Every change needs verification.
High-risk changes need automated tests.
Low-risk changes may waive automated tests, but not verification evidence.
```

## Workflow

1. Discover the test environment.
   - Check project manifests, test files, CI config, and documented commands.
   - Examples: `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `pom.xml`, `build.gradle`, `.github/workflows`, existing `*.spec.*`, `*_test.*`, or `test/` directories.
   - Use existing commands first. Do not invent commands or introduce new test tools unless the existing stack cannot cover a real risk.

2. Make a test decision before non-trivial implementation.
   - Classify the scenario: `feature`, `bugfix`, `requirement-change`, `refactor`, `cross-module`, `ui-copy`, `docs-config`.
   - Classify risk: `P0`, `P1`, `P2`, `P3`.
   - Decide automated testing: `required`, `recommended`, or `not required`.
   - For the decision template, read `references/test-decision.md`.

3. Choose the lowest sufficient evidence.
   - Prefer the narrowest stable test that proves the behavior.
   - Do not use E2E when unit, component, integration, or contract tests can prove the risk more directly.
   - Do not test private implementation details, framework behavior, or meaningless snapshots.

4. Plan tests when the change is more than trivial.
   - Required for high-risk work, bugfixes, requirement changes, cross-module work, public contracts, persistence, security, concurrency, or when the user asks for tests.
   - For the plan template, read `references/test-plan.md`.

5. Implement or update tests with quality guardrails.
   - When writing or reviewing unit tests, read `references/unit-test-practices.md`.
   - For bugfixes with an automatable reproduction, create or update a regression test before or alongside the fix.

6. Verify with real evidence before claiming completion.
   - Run targeted checks first, then broader checks only when needed.
   - Record commands, pass/fail/not-run status, and meaningful output.
   - Do not claim completion from code reading, memory, or intent.
   - For the evidence template, read `references/verify-result.md`.

## Risk Rules

Automated tests are `required` for:

- Automatable bugfixes.
- Security, authentication, authorization, privacy, or permission changes.
- Persistence, import/export, file write/delete/overwrite, or irreversible user actions.
- Public API, shared component contract, schema, or migration changes.
- Cross-module, cross-service, frontend/backend, network, filesystem, or external-boundary behavior.
- Retry, concurrency, idempotency, async job, state machine, or core business rule changes.
- Explicit user requests for tests.

Automated tests are usually `recommended` for:

- Form validation, state changes, filtering/sorting, and ordinary component interaction.
- Medium-risk refactors.
- Existing behavior that can get low-cost regression protection.

Automated tests may be `not required` for:

- Pure copy, static style, comments, docs, formatting, and low-risk metadata.
- Behavior already directly covered by existing tests.

When waiving automated tests, still provide a waiver reason and a concrete verification path.

## Test Layer Selection

- `unit`: pure logic, formatting, parsing, validation, calculations, reducers, business rules.
- `component`: user-visible component behavior, inputs, events, conditional rendering, accessibility states.
- `integration`: collaboration across page/module/store/router/API mock/storage/permission boundaries.
- `contract`: request/response shape, schema, public API, shared boundary expectations.
- `e2e`: critical user journeys when lower layers cannot prove the risk.
- `manual`: visual quality, real devices, external unstable dependencies, or experiential checks.

Guardrails:

- Do not duplicate the same assertion across many layers.
- Cross-boundary behavior cannot be proven only with unit tests.
- Integration tests should mock external boundaries, not the system under test.
- If an integration test needs many internal mocks, narrow the boundary.

## Scenario References

- For bug root-cause analysis and regression strategy, read `references/bugfix-root-cause.md`.
- For requirement changes, refactors, or cross-module test impact, read `references/change-impact.md`.
- For test decisions, read `references/test-decision.md`.
- For full test planning, read `references/test-plan.md`.
- For completion evidence, read `references/verify-result.md`.
- For unit test code quality, read `references/unit-test-practices.md`.
