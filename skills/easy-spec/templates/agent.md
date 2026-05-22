## EasySpec Agent 入口

本项目使用 EasySpec。

规划或修改代码前：

1. 读取 `easyspec/settings.md`。
2. 如果存在，读取 `easyspec/knowledge/project-summary.md`。
3. 读取 `easyspec/knowledge/changes/` 下相关的近期记录。
4. 检查 `easyspec/specs/active/` 中是否已有当前 proposal。

对于非简单代码任务，遵守 Proposal -> Apply -> Archive：

1. Proposal：把计划写到 `easyspec/specs/active/YYYY-MM-DD-short-task-slug/proposal.md`，等待用户确认。
2. Apply：只执行已确认、范围明确的修改。
3. Archive：把 proposal 移动或复制到 `easyspec/specs/archive/`，并把结果记录到 `easyspec/knowledge/changes/`。

不要把 EasySpec 记忆、项目说明、spec 或归档文件放在项目根目录。
