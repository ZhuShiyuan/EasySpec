---
name: easy-spec
description: Enforce a lightweight Codex coding workflow with Proposal, Apply, and Archive phases. Use when a user asks Codex to follow EasySpec, spec-first development, proposal/apply/archive, project knowledge base maintenance, or task archiving for coding changes in a new or existing repository.
---

# Easy Spec

## Overview

Easy Spec keeps coding work explicit and recoverable: agree on a proposal, implement under tight apply-stage coding rules, then archive what changed into project knowledge.

Archive means writing a task record. It does not mean closing the conversation.

## Load These References

- Read `references/apply-guidelines.md` before entering Apply.
- Read `references/project-onboarding.md` when deciding whether a target project is new or existing.
- Use `references/spec-template.md` when creating a proposal file.
- Use `templates/` when initializing `agent.md`, `openspec/settings.md`, proposals, archive records, and project summaries.

## Phase 0: Project Onboarding

Before the first coding task in a target repository:

1. Classify the target as new or existing.
2. If it is an existing project, ask whether to read and summarize the project before changing code.
3. Ensure the target project root has only one EasySpec trigger file: `agent.md`.
4. Ensure all other EasySpec-managed files live under the target project's `openspec/` directory.
5. If approved, create or refresh the project knowledge base under `openspec/knowledge/`.
6. If it is a new project, skip the broad project scan and create lightweight notes only as decisions emerge.

Use the onboarding reference for exact boundaries and skip lists.

## Phase 1: Proposal

For every non-trivial coding task, start in Proposal.

Proposal may include read-only exploration, but no code edits.

Write or present a proposal with:

- Goal and user-visible outcome.
- Assumptions and open questions.
- Scope and non-goals.
- Planned steps.
- Files or modules likely to change.
- Verification plan.
- Risks and rollback notes.
- Archive destination.

If the repository has `openspec/specs/active/`, write the proposal to:

```text
openspec/specs/active/YYYY-MM-DD-short-task-slug/proposal.md
```

Wait for explicit user approval before entering Apply. Clear approval can be phrased as "confirm", "approved", "go ahead", "进入 apply", "确认执行", or equivalent.

For tiny read-only answers or trivial one-line edits, ask whether the user wants the full EasySpec ceremony or a compact proposal.

## Phase 2: Apply

Before editing files, read `references/apply-guidelines.md`.

During Apply:

- Follow the accepted proposal.
- Keep changes surgical and scoped.
- Use the repository's existing patterns.
- Update the user when making edits.
- Run the planned verification, or explain why a check cannot run.
- If the plan must change, pause and update the proposal before continuing.

## Phase 3: Archive

After Apply is complete, archive the task:

1. Record the final result, changed files, commands run, verification result, and follow-ups.
2. Write the record under `openspec/knowledge/changes/YYYY-MM-DD-short-task-slug.md` when available.
3. Move or copy the active proposal into `openspec/specs/archive/YYYY-MM-DD-short-task-slug/`.
4. Update `openspec/knowledge/project-summary.md` only when durable project knowledge changed.
5. End the response with a concise summary and verification status.
