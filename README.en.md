# EasySpec

[中文](README.md) | English

EasySpec is a lightweight workflow package for new Codex users. Give this GitHub repository URL to Codex, and Codex can install the `easy-spec` skill and initialize a clean spec workflow in your target project.

The goal is simple: Codex should agree on a plan before writing code, follow clear engineering constraints while applying changes, and record what changed so future work has useful context.

## What It Does

After Codex reads this repository, it should:

- Install or update the `easy-spec` skill.
- Avoid copying this repository's `README.md` into your project, so it does not conflict with your own README.
- Create or update one root-level `agent.md` entry file in your project.
- Keep EasySpec settings, memory, proposals, and archives inside `openspec/`.
- Use a `Proposal -> Apply -> Archive` workflow for non-trivial coding tasks.

## How To Use

Send this repository URL to Codex:

```text
Please read and enable this EasySpec repository: https://github.com/ZhuShiyuan/EasySpec
```

Then ask for work normally. Codex should first decide whether your target project is new or existing.

## New vs Existing Projects

For an existing project, Codex should ask before broad scanning:

```text
This looks like an existing project. Should I first read and summarize the project structure, tech stack, run commands, and key conventions into openspec/knowledge/project-summary.md before entering Proposal for this task?
```

If you approve, Codex creates a project knowledge base first. If you decline, it reads only the minimum context needed for the current task.

For a new project, Codex skips broad project scanning and starts with the current task's Proposal. Project conventions, commands, and architecture decisions are recorded into `openspec/` over time.

## Workflow

### Proposal

Codex writes the goal, assumptions, scope, non-goals, planned steps, verification plan, risks, and archive location. It waits for your confirmation before entering Apply.

### Apply

Codex follows the EasySpec apply rules:

- State assumptions clearly.
- Write only the code needed for the current task.
- Avoid unrelated refactors and formatting churn.
- Match the existing project style.
- Run relevant verification when practical.

### Archive

After the task is complete, Codex records what changed, what verification ran, and any follow-ups inside `openspec/`.

## What Gets Added To Your Project

EasySpec manages only these files in your target project:

```text
agent.md
openspec/
  settings.md
  knowledge/
  specs/
```

`agent.md` is the root-level trigger file that tells future agents to read the EasySpec settings.

`openspec/` is the EasySpec workspace for project memory, task proposals, and archive records.

## Repository Structure

```text
CODEX.md
skills/easy-spec/
examples/
```

`CODEX.md` contains the bootstrap instructions Codex reads when it sees this repository.

`skills/easy-spec/` is the installable Codex skill. It contains the workflow instructions, apply guidelines, and initialization templates.

`examples/` contains behavior examples for new and existing projects. It is not copied into your project.

## License

MIT
