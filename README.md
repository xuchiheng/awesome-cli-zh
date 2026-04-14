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
- [第三方提供的工具](#第三方提供的工具)
  - [浏览器模拟 / HTML 抓取](#浏览器模拟--html-抓取)
  - [逆向 API / 非官方协议](#逆向-api--非官方协议)
- [其他待补充项](#其他待补充项)
  - [关联开源项目](#关联开源项目)

> 更多分类（小程序官方 CLI、云计算与存储平台、AI 开发工具、音乐与娱乐、效率工具）详见 [Todo.md](Todo.md)。

---

## 官方提供的工具

### 企业协作平台

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 备注 |
|------|------|-------|---------|------|------|
| 飞书 | [larksuite/cli](https://github.com/larksuite/cli) | ~7.7k | [`lark-cli`](tools/official/enterprise/lark/README.md) | 飞书官方 CLI，200+ 命令覆盖 IM/文档/多维表格/日历/邮件/任务/会议等 14 个业务域 | 需登录 |
| 企业微信 | [WecomTeam/wecom-cli](https://github.com/WecomTeam/wecom-cli) | ~1.7k | [`wecom-cli`](tools/official/enterprise/wecom/README.md) | 腾讯官方：通讯录/任务/会议/消息/日程/文档/智能表，支持 AI Agent | 需机器人凭证（≤10人企业），否则会提示初始化失败 |
| 钉钉 | [DingTalk-Real-AI/dingtalk-workspace-cli](https://github.com/DingTalk-Real-AI/dingtalk-workspace-cli) | ~1.5k | [`dws`](tools/official/enterprise/dingtalk/README.md) | 钉钉官方开源 CLI，86 条命令覆盖联系人/日历/待办/审批/打卡/AI 表格等 | 需组织开启 CLI 数据访问权限（共创阶段） |

## 第三方提供的工具

### 浏览器模拟 / HTML 抓取

> 通过浏览器自动化或网页解析实现，非官方但相对可控，仍有一定风控风险。

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 备注 |
|------|------|-------|---------|------|------|
| B站/优酷/爱奇艺/搜狐/网易等 | [soimort/you-get](https://github.com/soimort/you-get) | ~56.8k | [`you-get`](tools/third-party/video/you-get/README.md) | 多平台视频/音频/图片下载 | 网页解析，部分站点需 cookies |
| B站/微博/优酷/抖音等 | [iawia002/lux](https://github.com/iawia002/lux) | ~25k | ⏳ | 多平台视频下载 CLI | 网页解析 |
| 综合 | [jackwener/OpenCLI](https://github.com/jackwener/OpenCLI) | ~15.7k | [`opencli`](tools/third-party/general/opencli/README.md) | 87+ 网站适配器、浏览器自动化、Electron App 控制、CLI Hub | 需安装 Browser Bridge 扩展 |
| 小红书 | [jackwener/xhs-cli](https://github.com/jackwener/xhs-cli) | ~439 | [`xhs-cli`](tools/third-party/content/xhs-cli/README.md) | 搜索、阅读、点赞、收藏、评论，Chrome Cookie 提取 | 基于浏览器模拟，命令为 `xhs`，与 `xiaohongshu-cli` 冲突 |
| 微信 | [LingDong-/wechit](https://github.com/LingDong-/wechit) | ~102 | ⏳ | 终端版微信：收发消息、图片 ASCII 渲染 | 基于 Selenium 控制 Chrome |

### 逆向 API / 非官方协议

> 通过逆向 API、非官方协议或客户端 Patch 实现，存在更高的风控与合规风险，建议优先使用官方 CLI。

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 备注 |
|------|------|-------|---------|------|------|
| 微信/企微/WhatsApp | [wechaty/wechaty](https://github.com/wechaty/wechaty) | ~22.7k | [`wechaty`](tools/third-party/wechat/wechaty/README.md) | 跨平台聊天机器人 RPA SDK，微信/企微/WhatsApp | 非官方协议，需 Puppet Provider / Token |
| B站 | [nilaoda/BBDown](https://github.com/nilaoda/BBDown) | ~13.7k | [`bbdown`](tools/third-party/video/bbdown/README.md) | B站视频下载（4K/弹幕/字幕/杜比视界）| 调用 TV/App/Intl 端解析接口 |
| 微信 | [sunnyyoung/WeChatTweak](https://github.com/sunnyyoung/WeChatTweak) | ~13.6k | ⏳ | macOS 微信增强：防撤回、多开、免认证登录 | 客户端 Patch |
| 小红书 | [JoeanAmier/XHS-Downloader](https://github.com/JoeanAmier/XHS-Downloader) | ~10.8k | ⏳ | 小红书链接提取/作品采集/下载，支持 TUI/API/MCP 模式 | Cookie 提取，非官方接口 |
| 小红书 | [jackwener/xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli) | ~1.6k | [`xhs-cli`](tools/third-party/content/xiaohongshu-cli/README.md) | 搜索笔记、阅读、点赞、收藏、评论、发布，QR 码登录 | 逆向 API，命令为 `xhs`，与 `xhs-cli` 冲突 |
| B站 | [public-clis/bilibili-cli](https://github.com/public-clis/bilibili-cli) | ~665 | [`bilibili-cli`](tools/third-party/video/bilibili-cli/README.md) | 视频搜索、UP主数据、弹幕、点赞投币 | 逆向 API |
| 微信 | [goorockey/node-wechat-terminal](https://github.com/goorockey/node-wechat-terminal) | ~99 | ⏳ | 终端微信客户端：联系人/消息/群聊 | 非官方网页版协议 |
| 微博 | [jackwener/weibo-cli](https://github.com/jackwener/weibo-cli) | ~63 | [`weibo-cli`](tools/third-party/content/weibo-cli/README.md) | 热搜、搜索、时间线、评论、转发 | 逆向 API |

---

## 其他待补充项

以下平台已有官方 API、SDK、MCP Server 或开源解析库，但社区尚无成熟的 CLI 封装，欢迎贡献：

- [ ] **饿了么** — [饿了么商家开放平台](https://open.shop.ele.me/)（外卖订单/配送 API）
- [ ] **滴滴出行** — [滴滴开放平台](http://developer.xiaojukeji.com/doc/)（打车/代驾 SDK），亦有 didi-ride-skill MCP
- [ ] **携程** — [携程开放平台](http://u.ctrip.com/union/help/Termsofuse.aspx)（酒店/机票/火车票 API）
- [ ] **同程** — [同程旅行开放平台](https://union.ly.com/)（旅游 API），亦有 MCP Server
- [ ] **去哪儿** — [去哪儿开放平台](http://open.qunar.com/)（机票/酒店/火车票 API，需申请）
- [ ] **猫眼** — 美团系 API（暂无公开独立开放平台）
- [ ] **淘票票** — [淘宝开放平台](https://open.taobao.com/) 电影票 API
- [ ] **大麦网** — [阿里开放平台](https://open.alitrip.com/) 大麦票务云分销 API
- [ ] **顺丰** — [顺丰开放平台](https://open.sf-express.com/)（快递/电子面单 API）
- [ ] **菜鸟** — [菜鸟开放平台](https://open.cainiao.com/)（物流轨迹/云打印 API）
- [ ] **货拉拉** — 暂无公开开放平台链接

已有开源解析服务或 SDK，可被封装为 CLI 的项目：

- [ ] **抖音/TikTok/B站/快手**：[Douyin_TikTok_Download_API](https://github.com/Evil0ctal/Douyin_TikTok_Download_API) (~15k ⭐)
- [ ] **微信**：[wechat-ilink-client](https://github.com/photon-hq/wechat-ilink-client) (~37 ⭐) — 逆向自 `@tencent-weixin/openclaw-weixin`

> 美团、大众点评、闲鱼、拼多多、高德地图经搜索确认目前均无 Star > 50 的 CLI 工具。

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
