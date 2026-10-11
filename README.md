# Shared AI Memory

让不同电脑、不同系统、不同 AI Agent，共享同一份由你掌控的长期记忆。

> 你不用学习 Git，也不用进入仓库寻找文件。复制下面整段话，直接发给一款能够操作本机文件和终端的 Agent。

## 一键使用：只复制这一段

```text
请直接在这台电脑上帮我搭建一套跨电脑、跨系统、跨 AI Agent 的共享记忆。不要只给我教程，请实际完成。

这里有两个内容相同的公开模板入口：
GitHub：https://github.com/CodyQin/shared-ai-memory
Gitee（中国大陆镜像）：https://gitee.com/codyqin17/shared-ai-memory

请先测试你能稳定访问哪个入口：能访问 GitHub 就读取并执行其中的 prompts/INSTALL.md；GitHub 不可达就读取并执行 Gitee 中的 prompts/INSTALL_GITEE.md。不要让我自己打开仓库找文件，也不要让我手动输入 Git 命令。

请为我的个人记忆另外创建一个 Private 仓库，绝不能把个人内容写回上面的公开模板。除官方登录、授权、系统权限和重大修改确认外，其余步骤尽量由你完成。不要向我索取或保存密码、验证码、Token、API Key、私钥或 Cookie；每次写入和推送前都要确认个人仓库为 Private。

完成后，请生成一段已经填好私人仓库地址的“第二台设备接入提示词”，并完成自检。现在先用不超过 6 句话说明计划，然后开始执行。
```

如果你的 Agent 无法操作电脑、文件或终端，它只能解释方案，不能替你完成安装。Codex、Claude Code、OpenClaw 一类本地 Agent 更适合执行这段提示词。

## Agent 会替你做什么

1. 自动判断 GitHub 或 Gitee 哪个入口可用。
2. 检查需要的工具和当前电脑环境。
3. 引导你只在官方页面完成登录或授权。
4. 另外创建一个 **Private** 个人记忆仓库。
5. 用普通 Markdown 建立用户背景、项目进度和长期记忆。
6. 接入当前 Agent，并生成第二台电脑可直接复制的接入提示词。
7. 检查隐私、仓库可见性、冲突和同步状态。

你不需要自己创建目录、拼接链接或输入 Git 命令。

## Git、GitHub、Gitee 分别是什么

- **Git**：记录文件变化和版本历史的工具。
- **GitHub**：托管 Git 仓库的国际平台，也是本项目的主发布源。
- **Gitee**：另一个独立的 Git 仓库托管平台；本项目用它提供中国大陆镜像。

GitHub 与 Gitee 不是同一家公司，也不是从属关系。这里的两个公开仓库内容相同，观众选择一个能稳定访问的平台即可，不需要同时注册两个账号。个人记忆只放进自己选择的平台上的另一个 Private 仓库。

## 为什么这里选择 GitHub / Gitee，而不是普通文档

Notion、飞书和 Obsidian 都能保存内容，但这个问题更在意：不同本地 Agent 能否稳定读写同一批开放文件、同步到不同电脑，并看见每一次修改。

Git 仓库正好提供：

- 普通 Markdown 文件，不依赖某个 AI 厂商；
- 跨电脑同步；
- 精确的修改历史和恢复线索；
- Public 模板与 Private 个人内容分离；
- Agent 原生熟悉的项目结构。

## 这套记忆保存什么

| 文件/目录 | 用途 |
|---|---|
| `USER.md` | 稳定的个人偏好与背景 |
| `MEMORY.md` | 长期记忆索引，不保存原始聊天堆积 |
| `PROJECTS.md` | 当前项目、决定、阻塞和下一步 |
| `memory/inbox/` | 每台设备先写候选记忆，降低冲突 |
| `memory/topics/` | 经用户确认后整理的主题记忆 |
| `skills/shared-memory/SKILL.md` | Agent 的同步与隐私规则 |
| `AGENTS.md` / `CLAUDE.md` | 不同 Agent 指向同一套事实来源 |

## 日常只需要这样说

- “开始工作”——先同步，再概括当前项目。
- “记住这件事：……”——先生成候选记忆，确认后保存。
- “同步我的记忆”——检查隐私与 Private 状态后同步。
- “结束工作”——总结决定、进度和下一步，再同步。
- “检查记忆系统”——检查登录、冲突、隐私和未同步内容。

## 隐私红线

公开仓库只是空模板。你的内容必须存进另一个 **Private** 仓库。以下内容不要写入任何 Git 历史：

- 密码、API Key、Token、验证码、私钥；
- 身份证件、完整住址、银行和税务资料；
- 未经脱敏的医疗、法律、雇佣或第三方隐私；
- 任何你不希望长期保留和被其他 Agent 读取的信息。

Private 不等于保险箱。如果秘密曾被提交，单纯删除当前文件无法清除历史，应立即轮换秘密并单独清理历史。

## 其他入口

- 一键提示词纯文本版：[`COPY_TO_YOUR_AGENT.md`](COPY_TO_YOUR_AGENT.md)
- GitHub 完整安装规则：[`prompts/INSTALL.md`](prompts/INSTALL.md)
- Gitee 完整安装规则：[`prompts/INSTALL_GITEE.md`](prompts/INSTALL_GITEE.md)
- 第二台设备：[`prompts/ADD_DEVICE.md`](prompts/ADD_DEVICE.md)
- 故障检查：[`prompts/DOCTOR.md`](prompts/DOCTOR.md)

## 许可证

模板按 MIT License 发布。你写入个人 Private 仓库的内容仍归你所有。
