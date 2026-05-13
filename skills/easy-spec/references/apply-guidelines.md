# Apply Guidelines

These rules govern the Apply phase. They are adapted from the user-provided `CODEX.md`.

## 1. Think Before Coding

Do not assume silently.

- State important assumptions before implementing.
- Ask a clarifying question when a wrong assumption would be costly.
- Present meaningful interpretations when multiple plausible readings exist.
- Surface tradeoffs when speed, scope, compatibility, or maintainability conflict.
- Push back gently when the requested approach is more complex or risky than needed.

## 2. Simplicity First

Write the minimum code that solves the approved proposal.

- Do not add features beyond what was approved.
- Do not introduce abstractions for single-use code.
- Do not add configurability or extension points unless the proposal requires them.
- Do not add elaborate handling for impossible or irrelevant scenarios.
- If the implementation becomes much larger than the problem warrants, simplify before continuing.

Use this check: a senior engineer should be able to see why each changed line exists.

## 3. Surgical Changes

Touch only what the task requires.

- Match the existing project style.
- Avoid opportunistic refactors, formatting churn, comment rewrites, and adjacent cleanup.
- Remove imports, variables, functions, files, or test data made unused by your own change.
- Leave pre-existing dead code alone unless the user explicitly asks to remove it.
- Mention unrelated issues when useful, but do not fix them inside the current task.

Every changed line should trace back to the accepted proposal.

## 4. Goal-Driven Execution

Turn work into verifiable goals and loop until checked.

- For a bug fix, prefer a test or reproduction that fails before the fix and passes after.
- For validation changes, cover representative invalid and valid inputs.
- For refactors, preserve behavior and run relevant tests before and after when practical.
- For multi-step tasks, keep a brief plan with a verification step for each milestone.
- If tests cannot run, explain what was not verified and why.

Example:

```text
1. Reproduce the issue -> verify: failing test or observed error
2. Implement the smallest fix -> verify: targeted test passes
3. Check nearby behavior -> verify: relevant suite or manual smoke test passes
```

## 5. Completion Bar

The Apply phase is complete only when:

- The implementation matches the accepted proposal or the proposal has been explicitly updated.
- The planned verification has run, or the limitation is documented.
- No unrelated user changes were reverted.
- The archive record can compare the actual result against the proposal.
