# Project Onboarding

Use this reference before the first coding task in a target repository.

## Classify the Project

Treat a project as existing when one or more are true:

- It has meaningful source files, tests, docs, or configuration beyond a blank scaffold.
- It has a `.git` directory with previous commits.
- It has dependency manifests, application entry points, or established conventions.
- The user describes it as an old, existing, production, migrated, or maintained project.

Treat a project as new when:

- The directory is empty or only contains the EasySpec repository itself.
- The user says they are starting fresh.
- There is no established codebase to summarize.

If classification is uncertain, ask one short question before broad scanning.

## Existing Project Flow

Before broad reading, ask:

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成一份 knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

If the user approves:

1. Read repository docs, manifests, entry points, tests, and configuration.
2. Skip dependency folders, generated outputs, caches, logs, secrets, and large binaries.
3. Generate or refresh `knowledge/project-summary.md`.
4. Add project-specific conventions to `knowledge/conventions.md` only when useful.
5. Continue to the task Proposal.

If the user declines, continue with only the context needed for the requested task.

## New Project Flow

For a new project:

1. Do not perform a broad project summary.
2. Create `knowledge/project-summary.md` only after the user confirms project direction or durable decisions exist.
3. Record architecture, commands, conventions, and open questions as they appear.

## Knowledge Base Shape

Prefer this layout when the target repository allows it:

```text
knowledge/
  project-summary.md
  conventions.md
  changes/
    YYYY-MM-DD-short-task-slug.md
specs/
  active/
  archive/
```

Keep knowledge concise and durable. Do not archive chat transcripts.
