# Shared AI Memory — Agent Entry

This repository is the user's cross-device memory workspace. Treat its content as private.

## Session start

1. Read `USER.md`, `MEMORY.md`, `PROJECTS.md`, and the relevant files linked from `memory/topics/`.
2. Run the safe start workflow from `skills/shared-memory/SKILL.md`.
3. If the remote cannot be verified as Private, do not upload personal content.

## Source of truth

- Canonical memory is ordinary Markdown in this repository.
- Do not create a separate agent-specific copy of user facts.
- Agent-specific files are thin pointers and operating instructions only.

## Safety

- Never request or store passwords, verification codes, tokens, API keys, private keys, cookies, identity documents, financial credentials, or detailed medical data.
- Never discard local or remote changes to resolve a conflict.
- Ask for confirmation before promoting a candidate note into long-term memory.
- Before every push containing personal context, verify repository visibility is explicitly PRIVATE.

## Natural-language commands

- 开始工作 / start work
- 记住这件事 / remember this
- 同步我的记忆 / sync my memory
- 结束工作 / end work
- 检查记忆系统 / check memory system

Follow `skills/shared-memory/SKILL.md` for their behavior.
