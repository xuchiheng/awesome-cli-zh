# wecom-cli

> 企业微信官方 CLI，覆盖通讯录/待办/会议/消息/日程/文档/智能表，支持 AI Agent

- **来源**: 官方（腾讯）
- **安装方式**: `npm install -g @wecom/cli`
- **官方链接**: [WecomTeam/wecom-cli](https://github.com/WecomTeam/wecom-cli)
- **语言**: TypeScript / Node.js
- **Stars**: ~1.7k

---

## 验证状态

| 检查项 | 状态 | 备注 |
|--------|------|------|
| 安装可执行 | ✅ 通过 | `npm install -g @wecom/cli` 成功 |
| 基础命令可运行 | ✅ 通过 | `npx wecom-cli --version`、`npx wecom-cli --help` 正常 |
| Skill 安装 | ✅ 通过 | `npx skills add WecomTeam/wecom-cli -y -g` 成功 |
| 初始化配置 | ❌ 失败 | 尝试扫码登录成功获取 Bot ID/Secret，但凭证验证失败（已知 Bug #24，错误码 853000/40058） |
| 实际功能可用 | ❌ 未验证 | 因初始化失败，暂无法验证实际接口 |

> 验证时间: 2026-04-14  
> 验证环境: macOS / node v22.14.0

---

## 首次使用：配置与初始化

### 1. 安装 CLI 和 Skill

```bash
npm install -g @wecom/cli
npx skills add WecomTeam/wecom-cli -y -g
```

### 2. 初始化配置

```bash
npx wecom-cli init
```

按提示选择扫码接入或手动输入 **Bot ID** 和 **Secret**。

> **注意**：
> - 目前仅对 **10 人及以下规模的企业**开放使用
> - **已知问题**：v0.1.5 中扫码或手动输入后，可能出现「企业微信机器人凭证验证失败」（GitHub [#24](https://github.com/WecomTeam/wecom-cli/issues/24)），错误码 `853000`（签名错误）或 `40058`（请求参数非法），暂无法完成初始化

---

## 接口说明

```
Usage: wecom-cli <COMMAND>

Commands:
  init      初始化企业微信机器人配置
  contact   通讯录 — 成员查询和搜索
  doc       文档 — 文档/智能表格创建和管理
  meeting   会议 — 创建/管理/查询视频会议
  msg       消息 — 聊天列表、发送/接收消息、媒体下载
  schedule  日程 — 日程增删改查和可用性查询
  todo      待办事项 — 创建/查询/编辑待办项

Options:
  -h, --help     Print help
  -V, --version  Print version
```

---

## 使用示例

### 示例 1: 查看版本

```bash
npx wecom-cli --version
```

**输出**:

```
wecom-cli 0.1.5
```

### 示例 2: 获取通讯录成员列表

```bash
npx wecom-cli contact get_userlist '{}'
```

### 示例 3: 查询会议列表

```bash
npx wecom-cli meeting list '{"start_time": 1700000000, "end_time": 1700086400}'
```

### 示例 4: 发送文本消息

```bash
npx wecom-cli msg send_text '{"touser": "UserID", "content": "Hello from CLI"}'
```

---

## 实际使用反馈

- **优点**: 官方维护、覆盖企业微信 7 大核心业务域、内置 Agent Skills、与 Claude Code / OpenClaw 等工具集成友好
- **限制**: 目前仅对小规模企业（≤10 人）开放；全局命令 `wecom-cli` 可能需要通过 `npx wecom-cli` 调用
- **适用场景**: 企业微信自动化运维、通讯录管理、会议/日程/待办集成、企业内部工作流

---

## 风险提示

- 需要企业微信机器人凭证（Bot ID / Secret），请妥善保管
- 部分操作涉及企业敏感数据，建议遵循最小权限原则配置机器人权限
- 目前处于早期版本（v0.1.x），接口和命令可能随版本迭代调整
