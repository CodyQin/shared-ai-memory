# 中国大陆访问与镜像

## 先讲清楚两者关系

Git 是版本管理方式；GitHub 与 Gitee 是两个相互独立的 Git 仓库托管平台，不是同一家公司，也不是从属关系。

本项目把 GitHub 作为主发布源，并把同一份公开空模板同步到 Gitee，方便中国大陆访问。观众只需要选择一个能稳定访问的平台，不需要两个账号都注册。个人记忆只放在自己选择的平台上的另一个 Private 仓库。

## 原则

GitHub 是主仓库和首选体验，但不能假设每位用户都能稳定访问。项目可以维护两个内容一致的入口：

1. GitHub 主仓库：开发、Issue 和上游版本
2. Gitee 公共镜像：中国大陆下载、克隆、阅读提示词

Gitee 镜像：`https://gitee.com/codyqin17/shared-ai-memory`

公开的是同一套空模板，不同步任何用户的个人记忆。

## 两种安装路径

### 非技术用户

不需要打开仓库找文件。直接复制项目首页或视频置顶评论中的统一提示词；其中已经包含：

- GitHub：`https://github.com/CodyQin/shared-ai-memory`
- Gitee：`https://gitee.com/codyqin17/shared-ai-memory`

Agent 会先测试哪个入口可访问。GitHub 不可达时，它应直接读取 Gitee 的 `prompts/INSTALL_GITEE.md`。用户只在 Gitee 官方网页完成登录；若自动创建仓库不可用，只手动点击一次“新建 Private 仓库”。后续本地 Git、文件和设备接入仍由 Agent 完成。

### 技术用户

- 从 Gitee clone 模板。
- 在 Gitee 或其他可访问的 Git 服务创建 Private 个人仓库。
- 复用同一套 Markdown、Agent adapters 与 shared-memory Skill。

## 为什么不能承诺百分之百零操作

GitHub CLI 提供相对成熟的官方浏览器授权和仓库自动化流程；Gitee 的安全登录、账号状态与 Agent 工具支持可能不同。为了避免用户把 Token、密码或验证码交给 Agent，国内版宁愿保留一次官方网页建仓步骤，也不以安全换“零点击”。

## 镜像维护

- GitHub 为上游事实来源。
- 每次更新后同步 Gitee 镜像，并检查 README、提示词、ZIP 下载和文件编码。
- 不要让两个公共仓库分别接受不一致的功能修改；变更先进入 GitHub 主线，再同步镜像。
- 国内安装提示词不得暗示 Gitee 与 GitHub 的自动化能力完全相同。
