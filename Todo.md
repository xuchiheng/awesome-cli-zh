# 待整理/待维护的 CLI 工具

以下分类暂不放在主 README，以降低维护成本。如有重要更新或 Star 显著增长，可再移回主文档。

---

## 官方提供的工具

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

### 电商

> 淘宝、京东、拼多多、抖音电商、小红书电商、唯品会、苏宁易购等平台的 CLI 工具调研。

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| — | — | — | — | — | — | 待补充 |

### 游戏

> 腾讯游戏、网易游戏、米哈游、Steam 国服、TapTap 等平台的 CLI 工具调研。

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| — | — | — | — | — | — | 待补充 |

### 股票 / 证券

> 同花顺、东方财富、雪球、富途、老虎证券、中信证券、华泰证券等平台的 CLI 工具调研。

| 平台 | 链接 | Stars | CLI 名称 | 功能 | 验证状态 | 备注 |
|------|------|-------|---------|------|----------|------|
| — | — | — | — | — | — | 待补充 |
