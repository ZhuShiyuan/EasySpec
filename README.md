# EasySpec

EasySpec 是给 Codex 新用户使用的轻量规范包。用户只需要把这个仓库的 GitHub URL 发给 Codex，Codex 就应当自动安装 `easy-spec` skill，并在目标项目里完成工作流初始化。

Codex 看到这个仓库后，会自动完成：

- 安装或更新 `easy-spec` skill。
- 在目标项目中启用 Proposal -> Apply -> Archive 工作流。
- 在目标项目根目录创建统一的 `easyspec/` 管理文件夹。
- 按目标项目是新项目还是已有项目选择初始化方式。
- 在写代码前先写 proposal，等用户确认后再 apply。
- Apply 阶段遵守谨慎编码规范：简单、局部、可验证、不做无关重构。
- 完成后记录修改内容、验证结果和后续事项，并归档到目标项目知识库。

## 使用效果

### 已有项目

Codex 会先询问是否阅读并整理整个项目：

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成 easyspec/knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

如果用户同意，Codex 会先生成项目知识库；如果用户不同意，则只读取当前任务所需的最小上下文。

### 新项目

Codex 不做全量项目扫描，直接从用户的第一个任务进入 Proposal。项目约定、命令、架构决策会在后续任务中逐步记录。

## 工作流

### 1. Proposal

Codex 先写清楚目标、假设、范围、非目标、步骤、验证方式、风险和归档位置。用户明确确认后才进入 Apply。

### 2. Apply

Codex 按 `skills/easy-spec/references/apply-guidelines.md` 执行：

- 明确假设，不隐藏不确定性。
- 写最少代码解决问题。
- 只改和任务直接相关的文件。
- 匹配项目现有风格。
- 尽可能运行验证。

### 3. Archive

执行完成后，Codex 在目标项目的 `easyspec/` 文件夹中记录：

```text
easyspec/knowledge/changes/YYYY-MM-DD-short-task-slug.md
easyspec/specs/archive/YYYY-MM-DD-short-task-slug/
```

必要时同步更新：

```text
easyspec/knowledge/project-summary.md
```

## 仓库结构

```text
CODEX.md                          # Codex 读取此仓库时的自动 bootstrap 指令
skills/easy-spec/                 # 可安装的 Codex skill
skills/easy-spec/SKILL.md         # 工作流入口
skills/easy-spec/references/      # onboarding、proposal、apply 规范
templates/                        # 可复制到目标项目的模板
examples/                         # 新项目和已有项目的预期交互示例
```

## 发布前检查

- 创建 GitHub remote 后再 push。
- 当前项目使用 MIT License。
- 在 Windows PowerShell 下验证 skill 时，建议设置 `$env:PYTHONUTF8='1'` 后再运行 skill validator。

## License

MIT
