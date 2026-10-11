# Codex Adapter

Codex 使用仓库根目录的 `AGENTS.md` 作为入口。入口保持轻量，只负责：

- 指向 `USER.md`、`MEMORY.md`、`PROJECTS.md`
- 指向 `skills/shared-memory/SKILL.md`
- 规定隐私、冲突和确认边界

不要把个人事实再复制进 `AGENTS.md`，否则不同 Agent 会产生多份互相漂移的记忆。
