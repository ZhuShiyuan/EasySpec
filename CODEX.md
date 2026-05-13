# Codex Bootstrap Instructions

This repository is an EasySpec distribution package.

When a user gives you this repository URL, automatically install the EasySpec skill and initialize the target project workflow. Do not ask the user to run setup commands.

## 1. Install Or Update The Skill

Install the skill by copying:

```text
skills/easy-spec
```

to:

```text
$CODEX_HOME/skills/easy-spec
```

If `$CODEX_HOME` is unset, use:

```text
~/.codex/skills/easy-spec
```

If an existing `easy-spec` skill is already installed:

1. If it is identical, leave it in place.
2. If it differs, create a timestamped backup next to it, then replace it with this repository's `skills/easy-spec`.
3. Tell the user what was installed or updated after the copy completes.

The skill enforces:

1. Proposal before code changes.
2. Apply only after explicit user approval.
3. Archive of the final task record and durable project knowledge.

## 2. Initialize The Target Project Workflow

After installation, identify the target project. If the target project is not obvious from the current working directory or the user's wording, ask one short question to identify it.

In the target project, ensure these directories exist:

```text
knowledge/changes/
specs/active/
specs/archive/
```

Use these starter templates from this repository when creating target project records:

```text
templates/proposal.md
templates/archive.md
templates/project-summary.md
```

Do not create EasySpec's own `knowledge/` or `specs/` directories inside this distribution repository unless the user is developing EasySpec itself.

## 3. Classify The Target Project

Classify the target project:

- Existing project: meaningful source, tests, docs, config, dependency manifests, or git history already exists.
- New project: empty or nearly empty workspace, or the user says it is new.

For an existing project, ask before broad scanning:

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成 knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

For a new project, skip broad scanning. Start with the requested task and record durable decisions later.

## 4. Use EasySpec For Coding Tasks

For every non-trivial coding task in the target project:

1. Proposal: write the plan and wait for explicit approval.
2. Apply: follow `skills/easy-spec/references/apply-guidelines.md`.
3. Archive: write the task record under `knowledge/changes/` and move or copy the proposal to `specs/archive/`.

Archive means task documentation. Do not close or archive the conversation unless the user explicitly requests that.
