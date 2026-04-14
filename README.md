# Awesome CLI China

> 国内互联网公司 CLI 工具大全

收录国内主要互联网公司、云厂商、AI 公司提供的官方 CLI 工具，以及 GitHub 上对国内平台 API 实现了 CLI 封装的第三方项目。

### 为什么整理这份 CLI 大全？

**2026 年初，CLI 作为 Agent 基础设施迎来了真正的爆发。**

以 **OpenClaw** 走红和 **Skill** 机制普及为标志，「CLI + Skill」的组合被验证为 Agent 调用外部能力的最短路径：CLI 是肌肉，负责执行；Skill 是神经，让 Agent 在需要时「看见」并调用正确的 CLI。几乎同一时间，飞书、网易云音乐、各大云厂商也纷纷将核心能力封装为 CLI。

这个项目的初衷很简单：**整理国内互联网服务的 CLI 与 Skill 动向，让中文开发者和 Agent 更快地发现、使用这些能力。**

### CLI vs MCP：为什么 Agent 世界重新拥抱 CLI？

2024 年底 Anthropic 推出 MCP 时，业界曾寄予厚望。但进入 2025–2026 年，顶级团队开始用行动投票：

- **OpenClaw** 创始人 Peter Steinberger 明确拒绝 MCP，坚持 "CLI-first"。
- **Perplexity** CTO Denis Yarats 在 2026 年初宣布放弃 MCP，原因是 MCP 消耗了高达 72% 的上下文窗口。
- **微软**在 2026 年 2 月建议用 Playwright CLI 替代 Playwright MCP，实测 token 从 114K 降至 27K，节省 76%。
- **Scalekit 基准测试**：在相同 GitHub 任务中，CLI 成功率 100%，MCP 仅 72%（多因超时）。

| 维度 | MCP | CLI |
|------|-----|-----|
| Token 成本 | 初始化需加载 tool schema，单次可达数万 tokens | 通常仅数百 tokens，差距可达数十倍 |
| 模型熟悉度 | 运行时注入新 schema，增加认知负担 | 训练语料中已大量存在，模型更可靠 |
| 可组合性 | 多工具链需多次调用，由 Agent 管理中间状态 | 通过 Unix pipe 原生组合，一次执行 |
| 生产稳定性 | 连接超时、stdio 失效等问题导致失败率较高 | 直接与系统交互，稳定性经数十年验证 |
| 适用边界 | 适合需要标准化发现、OAuth 治理的企业集成 | 适合快速执行、原型开发和个人自动化 |

#### 他们怎么说

> **Andrej Karpathy**（前 Tesla AI Director、OpenAI 创始成员）：
> "CLIs are super exciting precisely because they are a 'legacy' technology, which means AI agents can natively and easily use them, combine them, interact with them via the entire terminal toolkit."
> — 2026 年 2 月，X（Twitter）

> **Peter Steinberger**（OpenClaw 创始人，现已加入 OpenAI）：
> "Screw MCPs. Every MCP would be better as a CLI. ... The main beauty is that models are really good at calling Unix commands. So if you just add another CLI, that's just another Unix command in the end."
> — Lex Fridman Podcast #491, 2026 年 2 月

> **Garry Tan**（Y Combinator CEO）：
> 称 MCP "honestly just garbage"（占用过多上下文窗口、需要反复手动开关、认证体验差），并说自己当晚花 30 分钟写了一个 100 行的 Playwright CLI 封装，"效果比通过 MCP 接入 Chrome 好 100 倍"。
> — 2026 年 3 月，X（Twitter）

工程共识：**能用 CLI 的，优先用 CLI；MCP 更适合作为企业集成层的标准化协议，而非唯一的执行协议。**

> ⚠️ **风险提示**：部分第三方工具通过非官方接口或逆向工程实现，若被 AI Agent **高频、自动化调用**，可能更容易触发平台的风控策略，导致账号被**限流甚至永久封禁**。我们建议：优先使用官方 CLI；使用第三方工具时，尽量注册小号、控制调用频率、避免在生产环境或重要账号上使用。**后续我们将补充各工具的实测报告与安全使用指南。**

---

## 目录

- [官方提供的工具](#官方提供的工具)
  - [企业协作平台](#企业协作平台)
  - [小程序官方 CLI](#小程序官方-cli)
  - [云计算与存储平台](#云计算与存储平台)
  - [AI 开发工具](#ai-开发工具)
- [第三方提供的工具](#第三方提供的工具)
  - [内容社区](#内容社区)
    - [内容平台](#内容平台)
    - [视频](#视频)
  - [微信及公众号](#微信及公众号)
  - [音乐与娱乐](#音乐与娱乐)
  - [效率工具](#效率工具)
- [其他待补充项](#其他待补充项)
  - [关联开源项目](#关联开源项目)

---

## 官方提供的工具

### 企业协作平台

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| 飞书 | [larksuite/cli](https://github.com/larksuite/cli) | ~7.7k | `lark-cli` | 飞书官方 CLI，200+ 命令覆盖 IM/文档/多维表格/日历/邮件/任务/会议等 14 个业务域 | [✅ 详情](tools/official/enterprise/lark/README.md) | 需登录 |
| 企业微信 | [WecomTeam/wecom-cli](https://github.com/WecomTeam/wecom-cli) | ~1.7k | `wecom-cli` | 腾讯官方：通讯录/任务/会议/消息/日程/文档/智能表，支持 AI Agent | ⏳ | — |
| 钉钉 | [DingTalk-Real-AI/dingtalk-workspace-cli](https://github.com/DingTalk-Real-AI/dingtalk-workspace-cli) | ~1.5k | `dws` | 钉钉官方开源 CLI，86 条命令覆盖联系人/日历/待办/审批/打卡/AI 表格等 | ⏳ | — |

### 小程序官方 CLI

> 含微信、支付宝、抖音、快手、京东等官方小程序开发工具。

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| 微信 | [官方文档](https://developers.weixin.qq.com/miniprogram/dev/devtools/ci.html) | — | `miniprogram-ci` | 上传、预览、代码包管理 | [✅ 详情](tools/official/miniprogram/miniprogram-ci/README.md) | — |
| 支付宝 | [官方文档](https://opendocs.alipay.com/mini/02q29z) | — | `minidev` | 上传、预览、沙箱调试 | [✅ 详情](tools/official/miniprogram/minidev/README.md) | — |
| 抖音 | [官方文档](https://developer.open-douyin.com/docs/resource/zh-CN/mini-app/develop/developer-instrument/development-assistance/ide-cli) | — | `tt-ide-cli` | 上传、预览 | ⏳ | — |
| 快手 | [官方文档](https://mp.kuaishou.com/docs/develop/guide/ci.html) | — | `ks-miniprogram-ci` | 上传、预览 | ⏳ | — |
| 京东 | [官方文档](https://mp-docs.jd.com/doc/dev/guide/0000001270) | — | `jdmp-cli` | 上传、预览 | ⏳ | — |
| 钉钉 | [官方文档](https://open.dingtalk.com/document/orgapp/dingtalk-cli) | — | `dingtalk-design-cli` | 小程序开发调试工具 | ⏳ | — |

### 云计算与存储平台

| 厂商 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| 七牛云 | [qiniu/qshell](https://github.com/qiniu/qshell) | ~1k | `qshell` | 文件上传/下载/管理、CDN 管理、音视频处理 | [✅ 详情](tools/official/cloud/qshell/README.md) | 需七牛云 AK/SK |
| 阿里云 | [aliyun/aliyun-cli](https://github.com/aliyun/aliyun-cli) | ~940 | `aliyun` | 通用云平台 CLI，Apache 2.0 | [✅ 详情](tools/official/cloud/aliyun/README.md) | 需阿里云 AccessKey |
| 又拍云 | [upyun/upx](https://github.com/upyun/upx) | ~200 | `upx` | 文件上传/下载/管理，支持 Mac/Linux/Windows | [✅ 详情](tools/official/cloud/upx/README.md) | 需又拍云 operator 密码 |
| 腾讯云 | [TencentCloud/tencentcloud-cli](https://github.com/TencentCloud/tencentcloud-cli) | ~117 | `tccli` | 通用云平台 CLI，Apache 2.0 | [✅ 详情](tools/official/cloud/tccli/README.md) | 需腾讯云 SecretId/Key |
| UCloud | [ucloud/ucloud-cli](https://github.com/ucloud/ucloud-cli) | ~97 | `ucloud` | 通用云平台 CLI，Apache 2.0 | ⏳ | — |
| 京东云 | [jdcloud-api/jdcloud-cli](https://github.com/jdcloud-api/jdcloud-cli) | ~86 | `jdc` | 通用云平台 CLI，Apache 2.0 | [✅ 详情](tools/official/cloud/jdc/README.md) | 需京东云 AK/SK |
| 火山引擎 | [volcengine/volcengine-cli](https://github.com/volcengine/volcengine-cli) | ~30 | `ve` | 通用云平台 CLI，Apache 2.0 | ⏳ | — |
| 华为云 | [官方文档](https://support.huaweicloud.com/hcli/index.html) | — | `hcloud` | 通用云平台 CLI，闭源 | ⏳ | — |
| 百度智能云 | [baidubce/bce-cmd](https://github.com/baidubce/bce-cmd) | ~1 | `bcecmd` | 通用云平台 CLI，开源 | ⏳ | — |
| 天翼云 | [官方文档](https://www.ctyun.cn/document/10261471/11057592) | — | 日志服务 CLI | 日志服务专项 CLI，闭源 | ⏳ | — |

> 联通云、移动云目前均未发现官方通用 CLI 工具。天翼云仅有日志服务专项 CLI。

### AI 开发工具

| 公司 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| 阿里通义千问 | [QwenLM/qwen-code](https://github.com/QwenLM/qwen-code) | ~20.7k | `qwen` | AI 编程 Agent，fork 自 Gemini CLI，支持 MCP、IDE 集成 | [✅ 详情](tools/official/ai/qwen-code/README.md) | 需通义 API Key |
| Moonshot (Kimi) | [MoonshotAI/kimi-cli](https://github.com/MoonshotAI/kimi-cli) | ~7.8k | `kimi-cli` | AI 编程 Agent，代码编辑/Shell/Web 搜索/MCP，支持 VS Code / Zed / JetBrains | [✅ 详情](tools/official/ai/kimi-cli/README.md) | 需 Moonshot API Key |
| MiniMax | [MiniMax-AI/cli](https://github.com/MiniMax-AI/cli) | — | `mmx-cli` | AI 平台 CLI，全模态：文本/图像/视频/语音/音乐生成 | [✅ 详情](tools/official/ai/mmx-cli/README.md) | 需 MiniMax API Key |
| 百度千帆 | [baidubce/bce-qianfan-sdk](https://github.com/baidubce/bce-qianfan-sdk) | — | `qianfan` | AI 平台 CLI，chat/completion/txt2img、数据集、训练、评估 | [✅ 详情](tools/official/ai/qianfan/README.md) | 需千帆 AK/SK 或 App Key |
| 讯飞星火 | [iflytek/spark-ai-cli](https://github.com/iflytek/spark-ai-cli) | — | `aispark` | AI 平台 CLI，终端与星火大模型交互 | ⏳ | — |
| 智谱 AI | [zai-org/zai-coding-plugins](https://github.com/zai-org/zai-coding-plugins) | — | `@z_ai/coding-helper` | GLM Coding Plan 配置向导 | ⏳ | — |

> DeepSeek、字节豆包、阶跃星辰、零一万物、商汤、旷视、百川智能 — 均未发布官方 CLI 工具。

---

## 第三方提供的工具

### 内容社区

#### 内容平台

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| 小红书 | [JoeanAmier/XHS-Downloader](https://github.com/JoeanAmier/XHS-Downloader) | ~10.8k | `XHS-Downloader` | 小红书链接提取/作品采集/下载，支持 TUI/API/MCP 模式 | ⏳ | — |
| 小红书 | [jackwener/xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli) | ~1.6k | `xhs-cli` | 搜索笔记、阅读、点赞、收藏、评论、发布，QR 码登录 | [✅ 详情](tools/third-party/content/xiaohongshu-cli/README.md) | API 版（HTTP + 签名/指纹伪装） |
| 小红书 | [jackwener/xhs-cli](https://github.com/jackwener/xhs-cli) | ~439 | `xhs-cli` | 搜索、阅读、点赞、收藏、评论，Chrome Cookie 提取 | [✅ 详情](tools/third-party/content/xhs-cli/README.md) | 浏览器版（camoufox + `window.__INITIAL_STATE__`） |

#### 视频

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| B站/优酷/爱奇艺/搜狐/网易等 | [soimort/you-get](https://github.com/soimort/you-get) | ~56.8k | `you-get` | 多平台视频/音频/图片下载 | [✅ 详情](tools/third-party/video/you-get/README.md) | 部分站点需 cookies |
| B站/微博/优酷/抖音等 | [iawia002/lux](https://github.com/iawia002/lux) | ~25k | `lux` | 多平台视频下载 CLI | ⏳ | — |
| 抖音/TikTok/B站/快手 | [Evil0ctal/Douyin_TikTok_Download_API](https://github.com/Evil0ctal/Douyin_TikTok_Download_API) | ~15k | `Douyin_TikTok_Download_API` | 无水印视频批量下载 | ⏳ | — |

> 掘金、CSDN 目前未发现 Star > 50 的 CLI 工具。豆瓣仅有 FM 播放器（见音乐分类）。

### 微信及公众号

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| 微信/企微/WhatsApp | [wechaty/wechaty](https://github.com/wechaty/wechaty) | ~22.7k | `wechaty` | 跨平台聊天机器人 RPA SDK，微信/企微/WhatsApp | [✅ 详情](tools/third-party/wechat/wechaty/README.md) | 需 Puppet Provider / Token |
| 微信 | [sunnyyoung/WeChatTweak](https://github.com/sunnyyoung/WeChatTweak) | ~13.6k | `WeChatTweak` | macOS 微信增强：防撤回、多开、免认证登录 | ⏳ | — |
| 微信公众号 | [doocs/md](https://github.com/doocs/md) | ~12.3k | `md-cli` | Markdown 转微信公众号文章、自定义主题、AI 助手 | [✅ 详情](tools/third-party/wechat/md-cli/README.md) | 启动本地 Web 服务 |
| 微信 | [LingDong-/wechit](https://github.com/LingDong-/wechit) | ~102 | `wechit` | 终端版微信：收发消息、图片 ASCII 渲染 | ⏳ | — |
| 微信 | [goorockey/node-wechat-terminal](https://github.com/goorockey/node-wechat-terminal) | ~99 | `node-wechat-terminal` | 终端微信客户端：联系人/消息/群聊 | ⏳ | — |

> `wechaty` 提供 CLI 辅助命令，但核心 Bot 功能仍需配合 SDK 代码调用。

### 音乐与娱乐

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| 网易云音乐 | [darknessomi/musicbox](https://github.com/darknessomi/musicbox) | ~9.8k | `musicbox` | 命令行音乐播放器：排行榜/搜索/歌单/登录/DJ/歌词 (已归档) | [✅ 详情](tools/third-party/music/musicbox/README.md) | 需登录；项目已归档，部分 API 可能失效 |
| 网易云/QQ/酷狗/酷我/咪咕等 | [CharlesPikachu/musicdl](https://github.com/CharlesPikachu/musicdl) | ~4k | `musicdl` | 轻量级无损音乐下载器，支持数十个音乐平台 | [✅ 详情](tools/third-party/music/musicdl/README.md) | 部分平台需 cookies |
| 豆瓣FM | [guo-yu/douban.fm](https://github.com/guo-yu/douban.fm) | ~1.6k | `douban.fm` | 命令行豆瓣FM播放器，红心/歌词/离线 | ⏳ | — |
| 豆瓣FM | [taizilongxu/douban.fm](https://github.com/taizilongxu/douban.fm) | ~784 | `douban.fm` | 终端豆瓣FM播放器，依赖 mplayer | ⏳ | — |

> QQ 音乐、酷狗、酷我目前未发现独立 CLI 播放器项目（Star > 50）。`musicdl` 已覆盖这些平台的下载功能。

### 效率工具

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| 翻译 | [afc163/fanyi](https://github.com/afc163/fanyi) | ~1.5k | `fanyi` | 中英翻译 CLI，集成 iciba + DeepSeek AI | [✅ 详情](tools/third-party/internet/fanyi/README.md) | DeepSeek 需 API Key |
| 搜索 | [Aas-ee/open-webSearch](https://github.com/Aas-ee/open-webSearch) | ~976 | `open-webSearch` | 多引擎搜索（Bing/Baidu/DuckDuckGo），CLI / HTTP / MCP 三模式 | [✅ 详情](tools/third-party/internet/open-websearch/README.md) | 需先启动 daemon `serve` |
| 语雀 | [vannvan/yuque-tools](https://github.com/vannvan/yuque-tools) | ~542 | `ytool` | 语雀知识库+团队资源批量导出/备份（无需 Token） | [✅ 详情](tools/third-party/other/yuque-tools/README.md) | — |
| Gitee | [hex2dec/gitee-cli](https://github.com/hex2dec/gitee-cli) | ~2 | `gitee` | 仿 gh CLI，支持 repo/issue/PR 操作 | ⏳ | — |
| 多平台桥接 | [chenhg5/cc-connect](https://github.com/chenhg5/cc-connect) | — | `cc-connect` | 桥接 Claude Code/Cursor/Gemini CLI 到飞书/钉钉/企微/Slack | ⏳ | — |

---

## 其他待补充项

以下公司/平台的 CLI 工具调研尚未完成，欢迎贡献：

- [ ] 携程

> 美团、饿了么、滴滴、大众点评、闲鱼、拼多多、高德地图经搜索确认目前均无 Star > 50 的 CLI 工具。

### 关联开源项目

| 项目 | Stars | 说明 | 链接 |
|------|-------|------|------|
| awesome-mcp-servers | ~40k | 最全 MCP Server 列表，含大量国内平台相关项目 | [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) |
| awesome-shell | ~36k | Shell 脚本工具、框架与指南聚合 | [alebcay/awesome-shell](https://github.com/alebcay/awesome-shell) |
| awesome-cli-apps | ~16k | 全球最大 CLI 应用精选列表 | [agarrharr/awesome-cli-apps](https://github.com/agarrharr/awesome-cli-apps) |
| terminals-are-sexy | ~5.6k | 终端框架、插件与美化资源汇总 | [k4m4/terminals-are-sexy](https://github.com/k4m4/terminals-are-sexy) |
| Awesome-MCP-ZH | — | 中文 MCP 资源精选 | [yzfly/awesome-mcp-zh](https://github.com/yzfly/awesome-mcp-zh) |

---

## 贡献

欢迎提交 PR 补充遗漏的 CLI 工具！请确保：

- 项目必须是 **CLI 工具**（命令行可直接调用），纯 MCP Server 不收录
- 对 MCP 实现了 CLI 封装层的项目可以收录
- 提供准确的 GitHub 链接或官方文档链接
- 注明是官方还是第三方项目
- 如有认证要求或使用注意，请在备注中说明

## License

[CC0 1.0 Universal](LICENSE)
