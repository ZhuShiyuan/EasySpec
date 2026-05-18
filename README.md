# EasySpec

中文 | [English](README.en.md)

EasySpec 是一个给 Codex 新用户使用的轻量工作流规范包。把这个仓库的 GitHub 链接交给 Codex 后，Codex 会自动安装 `easy-spec` skill，并在目标项目里建立一个干净的 spec 工作流。

它的目标很简单：让 Codex 在写代码前先和你确认方案，写代码时遵守清晰的工程约束，写完后把这次修改记录下来，方便后续继续协作。

## 它会做什么

Codex 读取这个仓库后，会自动完成这些事：

- 安装或更新 `easy-spec` skill。
- 不把本仓库的 `README.md` 复制到你的项目里，避免和你自己的 README 冲突。
- 在你的项目根目录创建或更新一个 `agent.md` 入口文件。
- 把 EasySpec 的设定、记忆、proposal 和归档统一放进 `openspec/`。
- 对每个非简单代码任务使用 `Proposal -> Apply -> Archive` 工作流。

## 怎么使用

把这个仓库链接发给 Codex：

```text
请读取并启用这个 EasySpec 仓库：https://github.com/ZhuShiyuan/EasySpec
```

之后你可以正常提出任务。Codex 会先判断你的项目是新项目还是已有项目。

## 新项目和已有项目

如果是已有项目，Codex 会先询问是否要阅读并整理项目：

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成 openspec/knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

如果你同意，Codex 会先生成项目知识库；如果你不同意，它只读取当前任务需要的最小上下文。

如果是新项目，Codex 不会做全量项目扫描，而是直接进入当前任务的 Proposal。项目约定、命令和架构决策会在后续任务中逐步写入 `openspec/`。

## 工作流

### Proposal

Codex 先写清楚目标、假设、范围、非目标、执行步骤、验证方式和归档位置。你确认后才进入 Apply。

### Apply

Codex 按 EasySpec 的 apply 规范执行：

- 明确假设，不隐藏不确定性。
- 只写解决当前问题所需的代码。
- 不做无关重构和格式化清理。
- 匹配项目现有风格。
- 尽可能运行验证。

### Archive

任务完成后，Codex 会把本次修改记录到 `openspec/`，包括改了什么、运行了哪些验证、还有什么后续事项。

## 安装后项目里会多什么

EasySpec 只会在你的项目里管理这些文件：

```text
agent.md
openspec/
  settings.md
  knowledge/
  specs/
```

`agent.md` 是根目录里的触发入口，用来提醒后续 agent 读取 EasySpec 设定。

`openspec/` 是 EasySpec 的工作区，用来保存项目记忆、任务 proposal 和归档记录。

## 这个仓库里有什么

```text
CODEX.md
skills/easy-spec/
examples/
```

`CODEX.md` 是 Codex 读取这个仓库时使用的自动安装说明。

`skills/easy-spec/` 是真正会安装到 Codex 的 skill，里面包含工作流说明、apply 规范和初始化模板。

`examples/` 是行为示例，用来说明 EasySpec 在新项目和已有项目中的预期表现。它不会被复制到你的项目里。

## License

MIT
