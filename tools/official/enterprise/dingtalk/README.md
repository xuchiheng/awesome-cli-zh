# dws

> 钉钉官方 CLI（DingTalk Workspace CLI），86+ 命令覆盖联系人/日历/待办/审批/打卡/AI 表格等，为 AI Agent 设计

- **来源**: 官方（钉钉）
- **安装方式**:
  - `curl -fsSL https://raw.githubusercontent.com/DingTalk-Real-AI/dingtalk-workspace-cli/main/scripts/install.sh | sh`
  - 或 `npm install -g dingtalk-workspace-cli`
- **官方链接**: [DingTalk-Real-AI/dingtalk-workspace-cli](https://github.com/DingTalk-Real-AI/dingtalk-workspace-cli)
- **中文文档**: [README_zh.md](https://github.com/DingTalk-Real-AI/dingtalk-workspace-cli/blob/main/README_zh.md)
- **参考手册**: [Reference](https://github.com/DingTalk-Real-AI/dingtalk-workspace-cli/blob/main/docs/reference.md)
- **语言**: Go
- **Stars**: ~1.5k

---

## 验证状态

| 检查项 | 状态 | 备注 |
|--------|------|------|
| 安装可执行 | ✅ 通过 | `npm install -g dingtalk-workspace-cli` 成功 |
| 基础命令可运行 | ✅ 通过 | `npx dws --version`、`npx dws --help` 正常 |
| 登录授权 | ⚠️ 部分通过 | Device Flow 扫码授权成功，但组织需开启 CLI 数据访问权限 |
| 实际功能可用 | ❌ 未验证 | 因组织权限未开启，暂无法调用业务接口 |

> 验证时间: 2026-04-14  
> 验证环境: macOS / node v22.14.0

> **注意**：npm 安装后，若 `dws` 未加入 PATH，建议使用 `npx dws` 调用。

---

## 首次使用：配置与登录

### 1. 安装 CLI

```bash
# 方式一：官方脚本（推荐，安装原生二进制）
curl -fsSL https://raw.githubusercontent.com/DingTalk-Real-AI/dingtalk-workspace-cli/main/scripts/install.sh | sh

# 方式二：npm
npm install -g dingtalk-workspace-cli
```

### 2. 登录授权

```bash
# 自动唤起浏览器（本地有图形界面）
npx dws auth login

# 设备流（无浏览器环境 / SSH / CI）
npx dws auth login --device
```

执行 `--device` 后会输出授权码和链接，在浏览器中打开并扫码/确认授权。

> **前提条件**：企业管理员需在钉钉开放平台开启「CLI 数据访问权限」，否则登录会提示「该组织尚未开启 CLI 数据访问权限」。
>
> 管理员操作入口：[https://open-dev.dingtalk.com/fe/old#/developerSettings](https://open-dev.dingtalk.com/fe/old#/developerSettings)

### 3. 自建应用模式（CI/CD、ISV）

```bash
npx dws auth login --client-id <your-app-key> --client-secret <your-app-secret>
```

需先在钉钉开放平台创建应用，安全设置中添加重定向 URL：`http://127.0.0.1,https://login.dingtalk.com`。

---

## 接口说明

```
dws — DingTalk Workspace on the command line, built for humans and AI agents.

USAGE:
  dws <service> [command] [flags]

DISCOVERED SERVICES:
  aitable     AI 表格操作
  attendance  考勤打卡 / 排班 / 统计
  calendar    日历日程 / 会议室 / 闲忙
  chat        群聊 / 会话 / 群组管理
  contact     通讯录 / 用户 / 部门
  devdoc      开放平台文档搜索
  ding        DING 消息 / 发送 / 撤回
  oa          OA 审批 / 同意 / 拒绝 / 撤销
  report      日志 / 模版 / 统计
  todo        待办任务管理
  workbench   工作台应用查询

GLOBAL FLAGS:
  -y, --yes          跳过确认提示（AI Agent 模式）
      --dry-run      预览操作内容，不实际执行
  -f, --format       输出格式: json|table|raw (默认 json)
      --jq string    jq 表达式过滤输出
      --mock         使用 Mock 数据（开发调试）
```

---

## 使用示例

### 示例 1: 查看版本

```bash
npx dws --version
```

### 示例 2: 搜索联系人

```bash
npx dws contact user search --keyword "张三"
```

### 示例 3: 查看日历日程

```bash
npx dws calendar event list
```

### 示例 4: 创建待办

```bash
npx dws todo task create --title "季度汇报" --executors "<your-userId>" --yes
```

### 示例 5: Schema 动态发现

```bash
# 查看所有可用产品
npx dws schema --jq '.products[] | {id, tool_count: (.tools | length)}'

# 查看 AI 表格查询接口的参数规范
npx dws schema aitable.query_records --jq '.tool.parameters'
```

---

## 实际使用反馈

- **优点**: 官方维护、Go 原生二进制无依赖、104 个标准化命令覆盖 7 大产品线、内置 Agent Skills、支持 Schema 动态发现、安全设计完善（AES-256-GCM、Domain Allowlist、Dry-run）
- **限制**: 目前处于「共创阶段」，需企业管理员授权才能使用；npm 安装的 `dws` 可能不在 PATH 中
- **适用场景**: 钉钉自动化运维、OA 审批、考勤管理、待办/日程集成、企业工作流

---

## 风险提示

- 访问钉钉企业数据需管理员开启 CLI 数据访问权限，并经过 OAuth 设备流授权
- 所有 API 调用均通过钉钉开放平台鉴权和审计，企业管理员可追踪完整调用日志
- 高频自动化调用可能触发平台限流，建议在批量操作时控制频率
