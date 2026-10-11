# Shared AI Memory

让不同电脑、不同系统、不同 AI Agent，共享同一份由你掌控的长期记忆。

> 个人记忆仓库必须设为 **Private**；这个公开仓库只提供空模板、安装提示词与通用 Agent 规则。

## 它解决什么问题

你在 Windows 上用 Codex，在 Mac 上用 Claude Code，偶尔还用 OpenClaw。每个 Agent 都像第一次认识你：不知道你的偏好、项目进度和之前做过的决定。

Shared AI Memory 把这些可迁移的上下文保存为普通 Markdown 文件，再使用 GitHub 私有仓库在设备之间同步。Agent 可以读取同一套内容，但你的记忆不被锁在某一个 AI 产品里。

```text
Windows + Codex ─┐
Mac + Claude Code ├─ Agent 适配层 ─ 私有 GitHub 仓库 ─ Markdown 记忆
其他 Agent ──────┘
```

## 给普通用户：只复制一句话

1. 打开你已经能操作本机文件和终端的 AI Agent。
2. 把 [`prompts/INSTALL.md`](prompts/INSTALL.md) 的完整内容发给它。
3. Agent 会解释即将做什么，并在需要登录 GitHub 时打开官方授权页面。
4. 你只需完成官方登录/授权；Git、仓库、目录、适配文件和首次同步都由 Agent 处理。
5. 在第二台电脑，把安装结束时生成的“接入提示词”发给另一款 Agent。

用户不需要理解 Git 命令，也不需要手动创建仓库。

## 设计原则

- **跨 Agent**：核心记忆使用普通 Markdown，不依赖某个厂商的专有格式。
- **默认私密**：个人记忆仓库必须为 Private；模板仓库才可以公开。
- **先确认再记忆**：Agent 只能提出“候选记忆”，经用户确认后才写入长期记忆。
- **版本可追溯**：每次同步都有历史，误改后可以恢复。
- **低冲突**：各设备先写自己的 inbox 日志，再由 Agent 整理进核心文件。
- **不保存秘密**：密码、Token、验证码、证件、财务和医疗敏感信息都不得进入仓库。

## 仓库结构

| 文件/目录 | 用途 |
|---|---|
| `USER.md` | 稳定的个人偏好与背景 |
| `MEMORY.md` | 长期记忆索引，不堆原始聊天 |
| `PROJECTS.md` | 当前项目、状态、下一步 |
| `memory/inbox/` | 各设备追加的候选记忆 |
| `memory/topics/` | 按主题整理的长期记忆 |
| `skills/shared-memory/SKILL.md` | Agent 的日常同步规则 |
| `AGENTS.md` / `CLAUDE.md` | 不同 Agent 的入口适配 |
| `prompts/` | 安装、新设备接入、修复提示词 |

## 日常怎么说

- “开始工作”——拉取最新记忆、检查冲突并概括当前项目。
- “记住这件事：……”——生成候选记忆，先让你确认。
- “同步我的记忆”——安全检查后提交并推送。
- “结束工作”——总结本次变化、候选记忆和下一步，再同步。
- “检查记忆系统”——检查登录、私有性、远端、冲突和未同步内容。

## 支持范围

首版为具备本地文件与终端能力的 Agent 优化，例如 Codex、Claude Code 和 OpenClaw 类工具。纯网页聊天产品通常不能直接操作本地仓库，可通过其 GitHub 连接能力读取，或手动提供相关 Markdown；这不等于把网页产品自身的“内置记忆”自动合并进来。

## 隐私红线

在首次写入个人信息和每次推送前，Agent 都必须重新确认目标仓库是 Private。不要把以下内容写入版本历史：

- 密码、API Key、访问令牌、验证码、私钥
- 身份证件、完整住址、银行和税务资料
- 未经脱敏的医疗、法律或雇佣敏感材料
- 不希望永久留在 Git 历史中的第三方信息

如果秘密曾经提交，单纯删除文件并不能从 Git 历史中清除它；应立即撤销/轮换秘密，并按照 GitHub 官方流程清理历史。

## 在线说明页

仓库根目录的 [`index.html`](index.html) 提供安装入口，也可以通过 GitHub Pages 发布为固定网址。

无法稳定访问 GitHub 时，参阅 [`CHINA_ACCESS.md`](CHINA_ACCESS.md) 和 [`prompts/INSTALL_GITEE.md`](prompts/INSTALL_GITEE.md)。

## 许可证

代码与模板按 MIT License 发布。你写入个人私有仓库的内容仍归你所有。
