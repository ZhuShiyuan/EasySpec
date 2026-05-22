---
name: easy-spec
description: "为 Codex 执行轻量 Proposal、Apply、Archive 编码工作流。适用于用户要求使用 EasySpec、spec-first development、proposal/apply/archive、项目知识库维护，或为新项目/已有项目归档代码任务。"
---

# Easy Spec

## 概览

EasySpec 让代码修改过程更明确、可追溯：先和用户确认 proposal，再在严格的 apply 规范下实现，最后把变更记录进项目知识库。

Archive 指写入任务记录，不是关闭当前对话。

## 需要读取的资料

- 进入 Apply 前，读取 `references/apply-guidelines.md`。
- 判断目标项目是新项目还是已有项目时，读取 `references/project-onboarding.md`。
- 创建 proposal 时，参考 `references/spec-template.md`。
- 初始化 `agent.md`、`easyspec/settings.md`、proposal、归档记录和项目摘要时，使用 `templates/`。

## 阶段 0：项目初始化

目标项目第一次使用 EasySpec 前：

1. 判断目标项目是新项目还是已有项目。
2. 如果是已有项目，先询问是否需要在改代码前阅读并总结项目。
3. 确保目标项目根目录只有一个 EasySpec 触发文件：`agent.md`。
4. 确保其他 EasySpec 管理文件都在目标项目的 `easyspec/` 目录下。
5. 如果用户同意整理已有项目，创建或刷新 `easyspec/knowledge/` 下的项目知识库。
6. 如果是新项目，跳过全量项目扫描，只在产生稳定决策后逐步记录轻量笔记。

具体边界和跳过规则见项目初始化参考。

## 阶段 1：Proposal

每个非简单代码任务都从 Proposal 开始。

Proposal 阶段可以做只读探索，但不要修改代码。

Proposal 应包含：

- 目标和用户可见结果。
- 假设和待确认问题。
- 范围和非目标。
- 执行步骤。
- 预计会修改的文件或模块。
- 验证计划。
- 风险和回退说明。
- 归档位置。

如果目标项目已有 `easyspec/specs/active/`，把 proposal 写到：

```text
easyspec/specs/active/YYYY-MM-DD-short-task-slug/proposal.md
```

等待用户明确确认后再进入 Apply。确认可以是“confirm”、“approved”、“go ahead”、“进入 apply”、“确认执行”等同义表达。

对于只读回答或非常小的一行修改，先询问用户是要完整 EasySpec 流程，还是使用简化 proposal。

## 阶段 2：Apply

编辑文件前，读取 `references/apply-guidelines.md`。

Apply 阶段：

- 遵守已确认的 proposal。
- 保持修改局部、克制。
- 使用项目现有模式。
- 修改文件前向用户说明要做什么。
- 运行计划中的验证；如果不能运行，说明原因。
- 如果计划需要改变，先暂停并更新 proposal，再继续。

## 阶段 3：Archive

Apply 完成后归档任务：

1. 记录最终结果、修改文件、运行过的命令、验证结果和后续事项。
2. 如果可用，把记录写到 `easyspec/knowledge/changes/YYYY-MM-DD-short-task-slug.md`。
3. 把当前 proposal 移动或复制到 `easyspec/specs/archive/YYYY-MM-DD-short-task-slug/`。
4. 只有在长期项目知识发生变化时，才更新 `easyspec/knowledge/project-summary.md`。
5. 最终回复要简洁说明改了什么和验证状态。
