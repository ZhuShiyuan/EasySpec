# EasySpec 设置

## 工作流

- 非简单代码任务使用 Proposal -> Apply -> Archive。
- 对已有项目做全量扫描前先询问用户。
- 新项目默认不做全量项目扫描，除非用户要求。
- EasySpec 管理的文件都放在 `easyspec/`。
- 项目根目录只保留 `agent.md` 作为 EasySpec 触发文件。

## 路径

- 当前 proposal：`easyspec/specs/active/`
- 已归档 proposal：`easyspec/specs/archive/`
- 项目摘要：`easyspec/knowledge/project-summary.md`
- 变更记录：`easyspec/knowledge/changes/`
- 项目约定：`easyspec/knowledge/conventions.md`

## Apply 规则

- 说明关键假设。
- 保持修改最小且范围明确。
- 匹配项目现有风格。
- 避免无关重构和格式化 churn。
- 可行时运行相关验证。
