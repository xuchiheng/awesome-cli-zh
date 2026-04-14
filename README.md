# Awesome CLI China

> 国内互联网公司 CLI 工具大全

收录国内主要互联网公司、云厂商、AI 公司提供的官方 CLI 工具，以及 GitHub 上对国内平台 API 实现了 CLI 封装的第三方项目。

---

## 目录

- [官方提供的工具](#官方提供的工具)
  - [企业协作平台](#企业协作平台)
  - [云计算平台](#云计算平台)
  - [AI 编程 Agent CLI](#ai-编程-agent-cli)
  - [云存储工具](#云存储工具)
  - [小程序开发工具](#小程序开发工具)
  - [AI 平台 CLI](#ai-平台-cli)
- [第三方提供的工具](#第三方提供的工具)
  - [社交与内容平台](#社交与内容平台)
  - [音乐与娱乐](#音乐与娱乐)
  - [生活服务](#生活服务)
  - [知识与社区](#知识与社区)
  - [云存储工具](#云存储工具-1)
  - [翻译工具](#翻译工具)
  - [搜索工具](#搜索工具)
  - [微信生态](#微信生态)
  - [开发工具](#开发工具)
  - [聚合资源](#聚合资源)
- [其他待补充项](#其他待补充项)

---

## 官方提供的工具

### 企业协作平台

| 平台 | CLI 名称 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|------|---------|---------|-------|------|------|------|
| 飞书 | `lark` (官方) | `npm install -g @larksuite/cli` | ~7.7k | Go | 飞书官方 CLI，200+ 命令覆盖 IM/文档/多维表格/日历/邮件/任务/会议等 14 个业务域 | [larksuite/cli](https://github.com/larksuite/cli) |
| 企业微信 | `wecom-cli` (官方) | `npm install -g @wecom/cli` | ~1.7k | Rust | 腾讯官方：通讯录/任务/会议/消息/日程/文档/智能表，支持 AI Agent | [WecomTeam/wecom-cli](https://github.com/WecomTeam/wecom-cli) |

### 云计算平台

| 厂商 | CLI 名称 | 安装方式 | 语言 | Stars | 开源 | 链接 |
|------|---------|---------|------|-------|------|------|
| 阿里云 | `aliyun` | `brew install aliyun-cli` | Go | ~940 | Apache 2.0 | [aliyun/aliyun-cli](https://github.com/aliyun/aliyun-cli) |
| 腾讯云 | `tccli` | `pip install tccli` | Python | ~117 | Apache 2.0 | [TencentCloud/tencentcloud-cli](https://github.com/TencentCloud/tencentcloud-cli) |
| 华为云 | `hcloud` (KooCLI) | curl 脚本安装 | — | — | 闭源 | [官方文档](https://support.huaweicloud.com/hcli/index.html) |
| 百度智能云 | `bcecmd` | 下载二进制 | Go | ~1 | 开源 | [baidubce/bce-cmd](https://github.com/baidubce/bce-cmd) |
| 京东云 | `jdc` | `pip install -U jdcloud_cli` | Python | ~86 | Apache 2.0 | [jdcloud-api/jdcloud-cli](https://github.com/jdcloud-api/jdcloud-cli) |
| 火山引擎 | `ve` | 下载二进制 | Go | ~30 | Apache 2.0 | [volcengine/volcengine-cli](https://github.com/volcengine/volcengine-cli) |
| UCloud | `ucloud` | `brew install ucloud` | Go | ~97 | Apache 2.0 | [ucloud/ucloud-cli](https://github.com/ucloud/ucloud-cli) |
| 天翼云 | 日志服务 CLI | 参考官方文档 | — | — | 闭源 | [官方文档](https://www.ctyun.cn/document/10261471/11057592) |

> 联通云、移动云目前均未发现官方通用 CLI 工具。天翼云仅有日志服务专项 CLI。

### AI 编程 Agent CLI

终端内运行的 AI 编程助手，可读写代码、执行 Shell、自主规划任务。

| 公司 | CLI 名称 | 安装方式 | Stars | 功能 | 链接 |
|------|---------|---------|-------|------|------|
| 阿里通义千问 | `qwen-code` | `npm install -g @qwen-code/qwen-code@latest` / `brew install qwen-code` | ~20.7k | fork 自 Gemini CLI，支持 MCP、IDE 集成 | [QwenLM/qwen-code](https://github.com/QwenLM/qwen-code) |
| Moonshot (Kimi) | `kimi-cli` | `pip install kimi-cli` | ~7.8k | 代码编辑/Shell/Web 搜索/MCP，支持 VS Code / Zed / JetBrains | [MoonshotAI/kimi-cli](https://github.com/MoonshotAI/kimi-cli) |

### 云存储工具

| 厂商 | CLI 名称 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|------|---------|---------|-------|------|------|------|
| 七牛云 | `qshell` | 下载二进制 | ~1k | Go | 文件上传/下载/管理、CDN 管理、音视频处理 | [qiniu/qshell](https://github.com/qiniu/qshell) |
| 又拍云 | `upx` | `go install` / Scoop / Docker | ~200 | Go | 文件上传/下载/管理，支持 Mac/Linux/Windows | [upyun/upx](https://github.com/upyun/upx) |

### 小程序开发工具

| 平台 | CLI 名称 | 安装方式 | 功能 | 链接 |
|------|---------|---------|------|------|
| 微信 | `miniprogram-ci` | `npm install miniprogram-ci` | 上传、预览、代码包管理 | [官方文档](https://developers.weixin.qq.com/miniprogram/dev/devtools/ci.html) |
| 支付宝 | `minidev` | `npm install -g minidev` | 上传、预览、沙箱调试 | [官方文档](https://opendocs.alipay.com/mini/02q29z) |
| 抖音 | `tt-ide-cli` | `npm install -g tt-ide-cli` | 上传、预览 | [官方文档](https://developer.open-douyin.com/docs/resource/zh-CN/mini-app/develop/developer-instrument/development-assistance/ide-cli) |
| 钉钉 | `dingtalk-design-cli` | `npm install dingtalk-design-cli -g` | 开发调试工具 | [官方文档](https://open.dingtalk.com/document/orgapp/dingtalk-cli) |
| 快手 | `ks-miniprogram-ci` | `npm install ks-miniprogram-ci` | 上传、预览 | [官方文档](https://mp.kuaishou.com/docs/develop/guide/ci.html) |
| 京东 | `jdmp-cli` | `npm install -g @jd/jdmp-cli` | 上传、预览 | [官方文档](https://mp-docs.jd.com/doc/dev/guide/0000001270) |

### AI 平台 CLI

调用 AI 模型 API 的命令行工具（非编程 Agent 类）。

| 公司 | CLI 名称 | 安装方式 | 功能 | 链接 |
|------|---------|---------|------|------|
| MiniMax | `mmx-cli` | `npm install -g mmx-cli` | 全模态：文本/图像/视频/语音/音乐生成 | [MiniMax-AI/cli](https://github.com/MiniMax-AI/cli) |
| 百度千帆 | `qianfan` | `pip install qianfan` | chat/completion/txt2img、数据集、训练、评估 | [baidubce/bce-qianfan-sdk](https://github.com/baidubce/bce-qianfan-sdk) |
| 讯飞星火 | `aispark` | 脚本安装 | 终端与星火大模型交互 | [iflytek/spark-ai-cli](https://github.com/iflytek/spark-ai-cli) |
| 智谱 AI | `@z_ai/coding-helper` | `npx @z_ai/coding-helper` | GLM Coding Plan 配置向导 | [zai-org/zai-coding-plugins](https://github.com/zai-org/zai-coding-plugins) |

> DeepSeek、字节豆包、阶跃星辰、零一万物、商汤、旷视、百川智能 — 均未发布官方 CLI 工具。

---

## 第三方提供的工具

### 社交与内容平台

#### 视频下载与上传

| 覆盖平台 | 项目名 | 安装方式 | Stars | 功能 | 链接 |
|---------|--------|---------|-------|------|------|
| B站/优酷/爱奇艺/搜狐/网易等 | `you-get` | `pip install you-get` / `brew install you-get` | ~56.8k | Python 多平台视频/音频/图片下载 | [soimort/you-get](https://github.com/soimort/you-get) |
| B站/微博/优酷/抖音等 | `lux` | `brew install lux` | ~25k | Go 多平台视频下载 CLI | [iawia002/lux](https://github.com/iawia002/lux) |
| 抖音/TikTok/B站/快手 | Douyin_TikTok_Download_API | Docker / pip | ~15k | 无水印视频批量下载 | [Evil0ctal/Douyin_TikTok_Download_API](https://github.com/Evil0ctal/Douyin_TikTok_Download_API) |
| 小红书 | XHS-Downloader | pip / Docker / 下载可执行文件 | ~10.8k | 小红书链接提取/作品采集/下载，支持 TUI/API/MCP 模式 | [JoeanAmier/XHS-Downloader](https://github.com/JoeanAmier/XHS-Downloader) |
| 抖音/小红书/B站/快手/视频号 | social-auto-upload | pip + Playwright | ~9k | 一键自动上传视频到多平台 | [dreammis/social-auto-upload](https://github.com/dreammis/social-auto-upload) |

#### 小红书

| 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|--------|---------|-------|------|------|------|
| `xiaohongshu-cli` | `uv tool install xiaohongshu-cli` / `pipx install xiaohongshu-cli` | ~1.6k | Python | 搜索笔记、阅读、点赞、收藏、评论、发布，QR 码登录 | [jackwener/xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli) |
| `xhs-cli` | `uv tool install xhs-cli` / `pipx install xhs-cli` | ~439 | Python | 搜索、阅读、点赞、收藏、评论，Chrome Cookie 提取 | [jackwener/xhs-cli](https://github.com/jackwener/xhs-cli) |

### 音乐与娱乐

| 平台 | 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|------|--------|---------|-------|------|------|------|
| 网易云音乐 | `musicbox` | `pip3 install NetEase-MusicBox` / `brew install musicbox` | ~9.8k | Python | 命令行音乐播放器：排行榜/搜索/歌单/登录/DJ/歌词 (已归档) | [darknessomi/musicbox](https://github.com/darknessomi/musicbox) |
| 网易云/QQ/酷狗/酷我/咪咕等 | `musicdl` | `pip install musicdl` | ~4k | Python | 轻量级无损音乐下载器，支持数十个音乐平台 | [CharlesPikachu/musicdl](https://github.com/CharlesPikachu/musicdl) |
| 网易云音乐 | `ncm` | `python3 setup.py install` | ~585 | Python | 网易云音乐下载器，完整 ID3 元数据 | [codezjx/netease-cloud-music-dl](https://github.com/codezjx/netease-cloud-music-dl) |
| 网易云音乐 | `netease-music-tui` | AUR / 下载二进制 / `cargo build` | ~431 | Rust | 终端 TUI 客户端，支持 Windows | [betta-cyber/netease-music-tui](https://github.com/betta-cyber/netease-music-tui) |
| 豆瓣FM | `douban.fm` | `npm install douban.fm -g` | ~1.6k | Node.js | 命令行豆瓣FM播放器，红心/歌词/离线 | [guo-yu/douban.fm](https://github.com/guo-yu/douban.fm) |
| 豆瓣FM | `douban.fm` (Python) | `pip install douban.fm` | ~784 | Python | 终端豆瓣FM播放器，依赖 mplayer | [taizilongxu/douban.fm](https://github.com/taizilongxu/douban.fm) |

> QQ 音乐、酷狗、酷我目前未发现独立 CLI 播放器项目（Star > 50）。`musicdl` 已覆盖这些平台的下载功能。

### 生活服务

| 平台 | 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|------|--------|---------|-------|------|------|------|
| 12306 火车票 | `py12306` | pip + Docker | ~14.9k | Python | 12306 购票助手，支持集群/多账号/多任务 | [pjialin/py12306](https://github.com/pjialin/py12306) |
| 12306 火车票 | `12306-cli` | `npm i -g 12306-cli` | ~54 | Node.js | 命令行查询火车票（因接口变更暂不可用） | [lpgray/12306-cli](https://github.com/lpgray/12306-cli) |

> 美团、饿了么、滴滴、大众点评、闲鱼、拼多多、高德地图均未发现 Star > 50 的 CLI 工具。

### 知识与社区

| 平台 | 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|------|--------|---------|-------|------|------|------|
| 知乎 | `zhihuhelp` | 下载安装包 | ~954 | TypeScript | 知乎内容导出为 EPUB 电子书（用户回答/收藏/话题/专栏） | [YaoZeyuan/zhihuhelp](https://github.com/YaoZeyuan/zhihuhelp) |
| 语雀 | `yuque-tools` | npm / 下载可执行文件 | ~542 | TypeScript | 语雀知识库+团队资源批量导出/备份（无需 Token） | [vannvan/yuque-tools](https://github.com/vannvan/yuque-tools) |

> 掘金、CSDN 目前未发现 Star > 50 的 CLI 工具。豆瓣仅有 FM 播放器（见音乐分类）。

### 云存储工具

| 厂商 | CLI 名称 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|------|---------|---------|-------|------|------|------|
| 蓝奏云 | LanZouCloud-CMD | pip / 下载安装包 | ~526 | Python | 无限制上传/下载，文件夹管理，分享链接 | [zaxtyson/LanZouCloud-CMD](https://github.com/zaxtyson/LanZouCloud-CMD) |

### 翻译工具

| 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|--------|---------|-------|------|------|------|
| `fanyi` | `npm i fanyi -g` | ~1.5k | Node.js | 中英翻译 CLI，集成 iciba + DeepSeek AI | [afc163/fanyi](https://github.com/afc163/fanyi) |

### 搜索工具

| 项目名 | 安装方式 | Stars | 功能 | 链接 |
|--------|---------|-------|------|------|
| open-webSearch | `npm run search:cli` | ~976 | 多引擎搜索（Bing/Baidu/DuckDuckGo），提供 CLI / HTTP / MCP 三种模式 | [Aas-ee/open-webSearch](https://github.com/Aas-ee/open-webSearch) |

### 微信生态

#### 客户端工具

| 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|--------|---------|-------|------|------|------|
| WeChatTweak | `brew install sunnyyoung/tap/wechattweak` | ~13.6k | Swift | macOS 微信增强：防撤回、多开、免认证登录 | [sunnyyoung/WeChatTweak](https://github.com/sunnyyoung/WeChatTweak) |
| wechit | `python wechit.py` | ~102 | Python | 终端版微信：收发消息、图片 ASCII 渲染 | [LingDong-/wechit](https://github.com/LingDong-/wechit) |
| node-wechat-terminal | `npm install -g node-wechat-terminal` | ~99 | Node.js | 终端微信客户端：联系人/消息/群聊 | [goorockey/node-wechat-terminal](https://github.com/goorockey/node-wechat-terminal) |

#### 公众号工具

| 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|--------|---------|-------|------|------|------|
| `md-cli` (doocs/md) | `npm i -g @doocs/md-cli` | ~12.3k | Vue | Markdown 转微信公众号文章、自定义主题、AI 助手 | [doocs/md](https://github.com/doocs/md) |

#### Bot 框架（含 CLI 能力）

| 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|--------|---------|-------|------|------|------|
| ItChat | `pip install itchat` | ~26.6k | Python | 微信个人号 API，终端 QR 码登录，自称"命令行微信" | [littlecodersh/ItChat](https://github.com/littlecodersh/ItChat) |
| wechaty | `npm install wechaty` | ~22.7k | TypeScript | 跨平台聊天机器人 RPA SDK，微信/企微/WhatsApp | [wechaty/wechaty](https://github.com/wechaty/wechaty) |
| WeChatFerry | `pip install wcferry` | ~6.5k | C++ | 微信 Hook 框架，可接入 DeepSeek/ChatGPT 等大模型 | [lich0821/WeChatFerry](https://github.com/lich0821/WeChatFerry) |

> ItChat、wechaty、WeChatFerry 本质上是 SDK/库，但在微信 Bot 生态中不可忽视，很多 CLI 工具基于它们构建。

### 开发工具

> 包含代码托管、数据采集等面向开发者的工具。

| 平台/覆盖 | 项目名 | 安装方式 | Stars | 语言 | 功能 | 链接 |
|----------|--------|---------|-------|------|------|------|
| Gitee | `gitee` | 下载二进制 / `cargo build` | ~2 | Rust | 仿 gh CLI，支持 repo/issue/PR 操作 | [hex2dec/gitee-cli](https://github.com/hex2dec/gitee-cli) |
| 微博 | weibo-crawler | pip | ~4.1k | Python | 微博内容/图片/视频爬取 | [dataabc/weibo-crawler](https://github.com/dataabc/weibo-crawler) |
| B站 | bilibili-api | pip | ~3.4k | Python | 完整 B站 API 封装（视频/番剧/用户/直播） | [Nemo2011/bilibili-api](https://github.com/Nemo2011/bilibili-api) |

> Coding (腾讯) 目前未发现独立 CLI 工具，其 DevOps 功能通过腾讯云 CLI (`tccli`) 调用。

### 聚合资源

| 项目 | Stars | 说明 | 链接 |
|------|-------|------|------|
| awesome-mcp-servers | ~40k | 最全 MCP Server 列表，含大量国内平台相关项目 | [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) |
| Awesome-MCP-ZH | — | 中文 MCP 资源精选 | [yzfly/awesome-mcp-zh](https://github.com/yzfly/awesome-mcp-zh) |

---

## 其他待补充项

以下公司/平台的 CLI 工具调研尚未完成，欢迎贡献：

- [ ] 携程

> 美团、饿了么、滴滴、大众点评、闲鱼、拼多多、高德地图经搜索确认目前均无 Star > 50 的 CLI 工具。

---

## 贡献

欢迎提交 PR 补充遗漏的 CLI 工具！请确保：

- 项目必须是 **CLI 工具**（命令行可直接调用），纯 MCP Server 不收录
- 对 MCP 实现了 CLI 封装层的项目可以收录
- 提供准确的 GitHub 链接或官方文档链接
- 注明是官方还是第三方项目
- 标注安装方式

## License

[CC0 1.0 Universal](LICENSE)
