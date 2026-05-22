# 项目初始化

目标项目第一次执行代码任务前使用本参考。

## 判断项目类型

满足以下任意条件时，按已有项目处理：

- 已经有有意义的源码、测试、文档或配置，而不只是空脚手架。
- 有 `.git` 目录和既有提交历史。
- 有依赖清单、应用入口或明确的项目约定。
- 用户描述它是老项目、已有项目、生产项目、迁移项目或维护中的项目。

满足以下条件时，按新项目处理：

- 目录为空，或只包含 EasySpec 分发仓库本身。
- 用户明确说这是新项目。
- 没有需要总结的既有代码库。

如果无法判断，先问一个简短问题，不要直接全量扫描。

## 已有项目流程

全量阅读前先问：

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成一份 easyspec/knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

如果用户同意：

1. 阅读仓库文档、依赖清单、入口文件、测试和配置。
2. 跳过依赖目录、生成产物、缓存、日志、密钥和大型二进制文件。
3. 创建或刷新 `easyspec/knowledge/project-summary.md`。
4. 只有在有价值时，才把项目约定写入 `easyspec/knowledge/conventions.md`。
5. 然后进入当前任务的 Proposal。

如果用户拒绝，只读取当前任务所需的最小上下文。

## 新项目流程

对于新项目：

1. 不做全量项目总结。
2. 只有在用户确认项目方向或出现长期决策后，才创建 `easyspec/knowledge/project-summary.md`。
3. 随任务推进逐步记录架构、命令、约定和开放问题。

## 知识库结构

目标项目允许时，优先使用：

```text
agent.md
easyspec/
  settings.md
  knowledge/
    project-summary.md
    conventions.md
    changes/
      YYYY-MM-DD-short-task-slug.md
  specs/
    active/
    archive/
```

知识库要简洁、稳定、可复用。不要保存聊天记录全文。
