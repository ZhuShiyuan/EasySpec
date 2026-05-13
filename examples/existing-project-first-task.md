# Existing Project First Task

User:

```text
请使用 EasySpec，帮我给这个老项目增加登录表单校验。
```

Codex should first ask:

```text
这是一个已有项目。要不要我先阅读并整理项目结构、技术栈、运行命令和关键约定，生成 knowledge/project-summary.md，之后再进入本次任务的 Proposal？
```

If the user approves, Codex summarizes the project first. Then it writes a proposal for login validation and waits for confirmation before editing code.
