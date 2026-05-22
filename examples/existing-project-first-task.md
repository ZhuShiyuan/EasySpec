# 已有项目的第一个任务

用户：

```text
请使用 EasySpec，帮我给这个老项目增加登录表单校验。
```

Codex 应该先问：

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成 easyspec/knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

如果用户同意，Codex 先总结项目，再为登录校验任务写 proposal，并等待用户确认后才修改代码。
