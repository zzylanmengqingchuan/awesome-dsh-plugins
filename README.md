# Awesome DSH Plugins 精选

> 面向 DeepSeek Harness（DSH）的**少而精插件清单**：不追求把 GitHub 上所有仓库抄一遍，而是优先收录真正能解决工作流问题、文档清楚、来源可追溯、安装边界说得明白的插件。

[English](README.en.md) · [插件目录](catalog/plugins.json) · [筛选标准](docs/selection-policy.md) · [贡献指南](CONTRIBUTING.md)

## 为什么还要做一个集合？

GitHub 上已经有不少“大而全”的 DSH 插件目录，例如：

- [awesome-dsh-plugin/awesome-dsh-plugin](https://github.com/awesome-dsh-plugin/awesome-dsh-plugin)：大型精选列表；
- [Dominic789654/awesome-deepseek-harness](https://github.com/Dominic789654/awesome-deepseek-harness)：覆盖插件、Skill、MCP、编排器和 UI；
- [0xsline/awesome-deepseek-harness](https://github.com/0xsline/awesome-deepseek-harness)：按生态能力分组的长列表；
- [white0dew/awesome-dsh-plugins](https://github.com/white0dew/awesome-dsh-plugins)：带站点和目录化数据的社区索引。

它们解决的是“尽可能发现更多项目”。本仓库解决的是另一个问题：

> **如果我只有半小时，哪些插件值得先看？安装时会改什么？需要什么版本？有什么坑？**

所以本仓库每个条目都尽量记录：

- 原始 GitHub 仓库和 npm 包；
- 主要用途，而不是营销口号；
- 推荐安装命令和特殊安装方式；
- DSH / Node 兼容性证据；
- 许可证、外部服务、权限和数据写入边界；
- 当前核验等级：本机观察、源码/README 核验，还是仅列入观察名单；
- 已知限制，以及**不适合什么场景**。

## 先装哪几个？

### 第一组：工作台和会话基础设施

| 插件 | 适合解决的问题 | 核验状态 |
|---|---|---|
| [DSH-better-sidebar](https://github.com/omdsh-dev/DSH-better-sidebar) | 文件管理、Markdown/PDF/Office 预览、终端、Git、浏览器、后台任务 | ✅ 本机已安装并使用过 |
| [dsh-attachments](https://github.com/CocoSgt/dsh-attachments) | 在对话中拖拽、粘贴或选择任意文件，并以工作区路径交给 Agent | 📖 源码/README 核验；本机已安装 |
| [dsh-chat-import](https://github.com/Nwflower/dsh-chat-import) | 把 Claude Code、Codex、ChatGPT、Cursor、Gemini 等历史迁入 DSH 并继续对话 | 📖 源码/README 核验 |
| [dsh-session-search-pro](https://github.com/LeslieWylie/dsh-session-search-pro) | 在 DSH 内搜索历史和当前会话 | 📖 源码/README 核验；GitHub 安装 |

### 第二组：开发、验证和自动化

| 插件 | 适合解决的问题 | 核验状态 |
|---|---|---|
| [dsh-plugin-doctor](https://github.com/zoahdev/dsh-plugin-doctor) | 发布插件前检查 manifest、patch、build、pack、全新 profile 安装 | 📖 源码/README 核验 |
| [dsh-agent-teams](https://github.com/NanmiCoder/dsh-agent-teams) | 把一个会话变成队长，管理可续聊的子 Agent、任务依赖和协作状态 | 📖 源码/README 核验 |
| [dsh-plugin-workshop](https://github.com/yyyyukari/dsh-plugin-workshop) | 在 DSH Web UI 内搜索、查看、安装和管理社区插件 | 📖 源码/README 核验 |
- [dsh-version-guard](https://github.com/skyjjgw/dsh-version-guard) — 记录插件版本与 profile 配置快照，在 DSH 无法启动时通过独立恢复页回退到已知可用配置。 源码核验；具体 DSH 版本兼容性待实测。

### 第三组：视觉、用量和技能

| 插件 | 适合解决的问题 | 核验状态 |
|---|---|---|
| [dsh-vision-router](https://github.com/ysr666/dsh-vision-router) | 给文本模型补视觉能力，支持 OCR、定位、裁剪、像素 Diff 和多后端 fallback | 📖 源码/README 核验；安装前需看兼容性 |
| [dsh-token-usage](https://github.com/hashdiana/dsh-token-usage) | 把拥挤的 Token 行变成上下文、输入输出、缓存命中率、TTFT 等可读面板 | 📖 源码/README 核验 |
| [dsh-skills](https://github.com/CocoSgt/dsh-skills) | 汇总项目和 Claude Code 目录中的 Skill，建立 DSH 全局 Skill 库 | 📖 源码/README 核验 |

## 作者自研插件

下面三个插件由本仓库维护者自行开发，并已出现在本机 DSH Web profile 中。这里仍按“本机安装/配置”记录，不把它们扩展成对所有 DSH 版本的兼容保证：

| 插件 | 适合解决的问题 | 核验状态 |
|---|---|---|
| [dsh-session-pin](https://github.com/zzylanmengqingchuan/dsh-session-pin) | 给侧边栏会话置顶，重要对话不会被新会话顶下去 | 🧪 本机安装/配置 |
| [dsh-question-index](https://github.com/zzylanmengqingchuan/dsh-question-index) | 列出当前会话的所有问题，支持搜索、跳转、历史加载和高亮 | 🧪 本机安装/配置 |
| [dsh-session-rename](https://github.com/zzylanmengqingchuan/dsh-session-rename) | 在对话顶部直接修改会话标题，并同步到侧边栏 | 🧪 本机安装/配置 |

这三个插件都明确避开会话模型、标准模式 / Think / Bash、Agent 执行逻辑和原始消息内容；安装前仍应阅读各自 README 与 patch 文件。

## 安装前先看这三件事

1. **确认 DSH 版本和运行 Profile。** DeepSeek Harness 仍处在快速迭代阶段；官方 README 明确提醒存在兼容性破坏变更。桌面端自带 runtime 的用户，还要确认插件装进的是桌面端实际使用的 profile，而不是普通 `~/.dsh`。
2. **优先固定版本或 Git tag。** 不要在重要工作区里盲目追踪 `main`；新插件可能依赖特定的 `0.1.x` runtime、Node.js 或 pnpm。
3. **把第三方插件当作第三方代码。** 安装前阅读 README、`package.json`、`cordis.patch.yml` 和构建脚本；插件可能读取本地会话、写入工作区、调用外部服务或请求凭据。

## 一键安装不是质量证明

`dsh plugin add` 成功只证明包管理器完成了安装，不等于：

- 插件已经被 bundle 激活；
- 当前 runtime 版本兼容；
- UI 挂载点仍然存在；
- 插件功能在你的模型、桌面端或工作区上可用；
- 插件没有不必要的权限或外部网络依赖。

推荐安装后至少做一次：

```sh
# 查看合成配置中是否出现插件层
npx -p @deepseek-ai/dsh dsh --profile web --dump-config

# 启动/重启 DSH Web 后，检查 Settings → Plugins
npx -p @deepseek-ai/dsh dsh web
```

开发者发布插件前，可以额外看 [dsh-plugin-doctor](https://github.com/zoahdev/dsh-plugin-doctor)。

## 核验等级

| 标记 | 含义 |
|---|---|
| ✅ 本机已安装并使用过 | 有本机配置或实际使用证据；只代表特定环境，不代表所有机器可用。 |
| 🧪 本机安装/配置 | 曾出现在本机 profile，但本仓库没有把它写成完整功能实测。 |
| 📖 源码/README 核验 | 已读取原始仓库的 README、manifest 或文档；尚未在本仓库维护者环境中完成安装冒烟。 |
| 👀 观察名单 | 方向有意思，但安装、维护、兼容性或安全信息不足。 |

## 当前边界

- 本仓库不是 DeepSeek 官方项目，也不是安全审计机构；
- “精选”不等于保证，也不替作者承诺维护质量；
- 不收录 API Key、Token、密码、OAuth code 或任何私人配置；
- 不把搜索结果、榜单排名或别人的推荐写成安装成功；
- 每条记录都应保留原始仓库链接，方便读者自行复核；
- DSH 版本变化很快，条目必须带复核日期。

## 参与贡献

欢迎提交插件，但请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。本仓库不追求数量，缺少 README、许可证、安装方式或来源证据的项目，会先进入观察名单，而不是直接放进推荐区。

## License

本仓库目录和文档采用 [MIT License](LICENSE)。各插件仍以其原始仓库许可证为准。
