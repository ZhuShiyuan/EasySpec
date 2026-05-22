# Codex Bootstrap 指令

这个仓库是 EasySpec 的分发包。

当用户把这个仓库 URL 发给你时，请自动安装 EasySpec skill，并初始化目标项目的工作流。不要要求用户手动运行安装命令。

不要把这个分发仓库里的 `README.md`、`README.en.md`、`LICENSE`、`CODEX.md`、`examples/` 或其他仓库说明文档复制到目标项目里。这些文件只用于发布 EasySpec 本身。

## 1. 安装或更新 Skill

把这个目录复制到 Codex skills 目录：

```text
skills/easy-spec
```

目标位置：

```text
$CODEX_HOME/skills/easy-spec
```

如果 `$CODEX_HOME` 为空，使用：

```text
~/.codex/skills/easy-spec
```

如果已经安装过 `easy-spec`：

1. 内容完全相同则保持不变。
2. 内容不同则先在旁边创建带时间戳的备份，再用本仓库的 `skills/easy-spec` 替换。
3. 安装或更新完成后，告诉用户发生了什么。

这个 skill 会执行：

1. 修改代码前先写 Proposal。
2. 用户明确确认后才进入 Apply。
3. 完成后把任务记录和长期项目记忆 Archive。

## 2. 初始化目标项目工作流

安装后，先识别目标项目。如果当前工作目录或用户表达里看不出目标项目，问一个简短问题确认。

在目标项目根目录只创建或更新一个 EasySpec 触发文件：

```text
agent.md
```

这个文件用于提醒后续 agent 使用 EasySpec，并在规划或改代码前读取 `easyspec/`。如果目标项目已经有 `agent.md`，保留原内容，只新增或更新 EasySpec 小节，不要覆盖整个文件。

然后创建一个 EasySpec 管理目录。所有 EasySpec 设定、agent 备注、记忆、项目说明、proposal 和归档都放在里面，让项目根目录保持干净。

确保这些目录存在：

```text
easyspec/
easyspec/knowledge/changes/
easyspec/specs/active/
easyspec/specs/archive/
```

创建目标项目记录时，使用 skill 内部模板：

```text
skills/easy-spec/templates/agent.md
skills/easy-spec/templates/settings.md
skills/easy-spec/templates/proposal.md
skills/easy-spec/templates/archive.md
skills/easy-spec/templates/project-summary.md
```

把 `skills/easy-spec/templates/agent.md` 放到目标项目根目录并命名为 `agent.md`，或合并进已有 `agent.md` 的 EasySpec 小节。把 `skills/easy-spec/templates/settings.md` 放到目标项目的 `easyspec/settings.md`。proposal、archive、project-summary 模板只用于创建 `easyspec/` 下的文件。

不要在目标项目根目录创建顶层 `knowledge/`、`specs/`、`settings.md` 或额外 agent 文件。EasySpec 在目标项目里只使用根目录 `agent.md` 和 `easyspec/`。

除非用户正在开发 EasySpec 本身，否则不要在这个分发仓库里创建 `easyspec/`、`knowledge/` 或 `specs/`。

## 3. 判断目标项目类型

判断目标项目是已有项目还是新项目：

- 已有项目：已经有有意义的源码、测试、文档、配置、依赖清单或 git 历史。
- 新项目：空目录、接近空目录，或用户明确说这是新项目。

如果是已有项目，在全量阅读前先问：

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成 easyspec/knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

如果是新项目，跳过全量扫描，直接从当前任务开始，并在之后逐步记录长期决策。

## 4. 执行代码任务

目标项目里的每个非简单代码任务都按以下流程执行：

1. Proposal：写计划，等待用户明确确认。
2. Apply：遵守 `skills/easy-spec/references/apply-guidelines.md`。
3. Archive：把任务记录写入 `easyspec/knowledge/changes/`，并把 proposal 移动或复制到 `easyspec/specs/archive/`。

Archive 指任务文档归档，不代表关闭或归档当前对话；除非用户明确要求，不要结束对话。
