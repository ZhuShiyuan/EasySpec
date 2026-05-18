# Codex Bootstrap Instructions

This repository is an EasySpec distribution package.

When a user gives you this repository URL, automatically install the EasySpec skill and initialize the target project workflow. Do not ask the user to run setup commands.

Do not copy this distribution repository's `README.md`, `LICENSE`, `CODEX.md`, `examples/`, or other repository documentation into the target project. Those files are only for publishing EasySpec itself.

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

In the target project root, create only one EasySpec trigger file:

```text
agent.md
```

This file should tell future agents to use EasySpec and read the `openspec/` directory before planning or changing code. If the target project already has `agent.md`, preserve the existing content and add or update an EasySpec section instead of overwriting the file.

Then create one EasySpec management directory. Keep EasySpec settings, agent notes, memory, project notes, proposals, and archives inside it so the normal project root stays clean.

Ensure these directories exist:

```text
openspec/
openspec/knowledge/changes/
openspec/specs/active/
openspec/specs/archive/
```

Use these starter templates from this repository when creating target project records:

```text
skills/easy-spec/templates/agent.md
skills/easy-spec/templates/settings.md
skills/easy-spec/templates/proposal.md
skills/easy-spec/templates/archive.md
skills/easy-spec/templates/project-summary.md
```

Place `skills/easy-spec/templates/agent.md` at the target project root as `agent.md`, or merge its EasySpec section into an existing `agent.md`. Place `skills/easy-spec/templates/settings.md` inside the target project as `openspec/settings.md`. Use the proposal, archive, and project-summary templates only when creating files under `openspec/`.

Do not create top-level `knowledge/`, `specs/`, `settings.md`, or extra agent files in the target project. Use root `agent.md` plus `openspec/` as the only EasySpec-managed surface.

Do not create EasySpec's own `openspec/`, `knowledge/`, or `specs/` directories inside this distribution repository unless the user is developing EasySpec itself.

## 3. Classify The Target Project

Classify the target project:

- Existing project: meaningful source, tests, docs, config, dependency manifests, or git history already exists.
- New project: empty or nearly empty workspace, or the user says it is new.

For an existing project, ask before broad scanning:

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成 openspec/knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

For a new project, skip broad scanning. Start with the requested task and record durable decisions later.

## 4. Use EasySpec For Coding Tasks

For every non-trivial coding task in the target project:

1. Proposal: write the plan and wait for explicit approval.
2. Apply: follow `skills/easy-spec/references/apply-guidelines.md`.
3. Archive: write the task record under `openspec/knowledge/changes/` and move or copy the proposal to `openspec/specs/archive/`.

Archive means task documentation. Do not close or archive the conversation unless the user explicitly requests that.
