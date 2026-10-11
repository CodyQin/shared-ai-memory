---
name: shared-memory
description: Safely maintain and synchronize the user's Markdown-based memory across devices and AI agents. Use when the user says 开始工作, 记住这件事, 同步我的记忆, 结束工作, 检查记忆系统, or asks to read/update their shared context.
---

# Shared Memory

Use `USER.md`, `MEMORY.md`, `PROJECTS.md`, `memory/inbox/`, and `memory/topics/` as the neutral source of truth. Agent-specific entry files must not duplicate personal facts.

## Absolute safety rules

1. Treat the repository as private personal data.
2. Before any push that contains personal context, use an authenticated official GitHub interface to verify the remote repository visibility is exactly `PRIVATE`. If it is public, internal, unknown, or unverifiable, stop before uploading.
3. Never request or store passwords, one-time codes, access tokens, API keys, private keys, cookies, identity documents, financial credentials, detailed medical records, or unrelated third-party private information.
4. Never use force push, hard reset, destructive checkout, or deletion to solve synchronization problems.
5. Never overwrite an existing directory or file without showing the effect and receiving user approval.
6. A suspected secret must be redacted in output. If it may have entered history, tell the user to revoke/rotate it first; deleting the current file is not sufficient.

## Start work

When the user says “开始工作” or equivalent:

1. Inspect the worktree before pulling.
2. If there are local changes, preserve them and explain the safe plan. Do not stash or commit unrelated work without consent.
3. Fetch and integrate remote changes using a non-destructive workflow.
4. If a conflict appears, keep both sides and explain the disagreement in plain language.
5. Read `USER.md`, `MEMORY.md`, `PROJECTS.md`, and only the topic files relevant to the request.
6. Summarize useful context in at most five bullets; do not echo sensitive content unnecessarily.

## Remember this

When the user says “记住这件事” or equivalent:

1. Decide whether the information will remain useful across sessions. Temporary chatter and one-off details should not become long-term memory.
2. Propose a short candidate containing the fact, its source/date, and why it matters.
3. Remove unnecessary identifying or sensitive detail.
4. Ask the user to confirm the candidate.
5. After confirmation, append it to a new timestamped file under `memory/inbox/<device-id>/`. Do not let two devices edit the same inbox file.
6. During consolidation, update the appropriate topic file and its one-line link in `MEMORY.md`; avoid duplicate or contradictory entries.

Suggested candidate format:

```markdown
---
date: YYYY-MM-DD
device: anonymous-device-id
status: candidate
---

- Fact:
- Why it matters:
- Source: user-confirmed
```

## Sync my memory

When the user says “同步我的记忆” or equivalent:

1. Inspect local changes and pull remote changes safely.
2. Resolve independent append-only notes automatically only when no meaning is changed. Ask the user about contradictory facts.
3. Scan the exact files to be committed for common credential and private-key patterns. Do not print full matches.
4. Verify the GitHub repository is explicitly PRIVATE.
5. Show a plain-language summary of what will be synchronized.
6. Commit with a concise message and push normally.
7. Verify the remote contains the commit and report any remaining local or unpushed changes.

## End work

When the user says “结束工作” or equivalent:

1. Summarize decisions, progress, open questions, and next action.
2. Present durable facts as candidate memories for approval.
3. After approval, update the appropriate files and run the sync workflow.
4. Report exactly what was remembered and whether remote synchronization succeeded.

## Check memory system

When the user says “检查记忆系统” or equivalent, report with `✅`, `⚠️`, and `❌`:

- official GitHub authentication
- correct remote URL
- remote visibility is explicitly PRIVATE
- branch and upstream state
- local changes and unpushed commits
- merge conflicts
- required files and folders
- current agent entry file
- likely credential patterns, without showing secret values
- each device uses a separate append-only inbox directory

Diagnose first. Ask before making any material or destructive repair.

## Conflict policy

- Pull before editing shared summaries.
- Prefer new timestamped inbox files over multiple devices editing one journal.
- Never decide silently between conflicting personal facts.
- Preserve both versions, explain the difference, and ask which is current.
- After consolidation, retain enough provenance to understand when and why a fact changed.
