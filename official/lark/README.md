# lark-cli

> 飞书官方 CLI，200+ 命令覆盖 IM/文档/多维表格/日历/邮件/任务/会议等 14 个业务域

- **来源**: 官方（飞书）
- **安装方式**: `npm install -g @larksuite/cli`
- **官方链接**: [larksuite/cli](https://github.com/larksuite/cli)
- **语言**: Go
- **Stars**: ~7.7k

---

## 验证状态

| 检查项 | 状态 | 备注 |
|--------|------|------|
| 安装可执行 | ✅ 通过 | `npm install -g @larksuite/cli` 成功 |
| 基础命令可运行 | ✅ 通过 | `npx lark-cli --version`、`npx lark-cli --help` 正常 |
| 登录授权 | ✅ 通过 | Device Flow 登录成功，token 有效 |
| 搜索用户 | ✅ 通过 | `contact +search-user` 正常返回 |
| 查看日程 | ✅ 通过 | `calendar +agenda` 正常 |
| 搜索群聊 | ✅ 通过 | `im +chat-search` 正常返回 |
| 查看任务 | ✅ 通过 | `task +get-my-tasks` 正常返回 |

> 验证时间: 2026-04-14  
> 验证环境: macOS / node v22.14.0

> **注意**：包名为 `@larksuite/cli`，全局安装后实际可执行文件名为 `lark-cli`，建议通过 `npx lark-cli` 调用。

---

## 首次使用：配置与登录

### 1. 初始化应用配置

```bash
npx lark-cli config init --new --brand feishu
```

执行后会输出一个二维码和一个配置链接（如 `https://open.feishu.cn/page/cli?user_code=XXXX`）。在浏览器中打开链接，登录飞书开放平台，创建或选择应用，完成配置后 CLI 会自动继续。

### 2. 用户授权登录

配置完成后，执行登录获取用户授权：

```bash
# 方式一：交互式（阻塞，自动弹出链接）
npx lark-cli auth login --recommend

# 方式二：非交互式（适合自动化/Agent）
npx lark-cli auth login --recommend --no-wait --json
# 拿到 verification_url 后在浏览器打开授权
# 然后执行：
npx lark-cli auth login --device-code <device_code>
```

### 3. 检查登录状态

```bash
npx lark-cli auth status
npx lark-cli doctor
```

---

## 接口说明

```
lark-cli — Lark/Feishu CLI tool.

USAGE:
    lark-cli <command> [subcommand] [method] [options]
    lark-cli api <method> <path> [--params <json>] [--data <json>]
    lark-cli schema <service.resource.method> [--format pretty]

FLAGS:
    --params <json>       URL/query parameters JSON
    --data <json>         request body JSON (POST/PATCH/PUT/DELETE)
    --as <type>           identity type: user | bot | auto (default: auto)
    --format <fmt>        output format: json (default) | ndjson | table | csv | pretty
    --page-all            automatically paginate through all pages
    --jq <expr>           jq expression to filter JSON output
    --dry-run             print request without executing
```

---

## 使用示例

### 示例 1: 查看版本

```bash
npx lark-cli --version
```

**输出**:

```
lark-cli version 1.0.10
```

### 示例 2: 搜索用户

```bash
npx lark-cli contact +search-user --query "张三" --format pretty
```

### 示例 3: 查看日程

```bash
npx lark-cli calendar +agenda --format pretty
```

### 示例 4: 搜索群聊

```bash
npx lark-cli im +chat-search --query "项目组" --format pretty
```

### 示例 5: 查看我的任务

```bash
npx lark-cli task +get-my-tasks --format pretty
```

### 示例 6: 通用 API 调用

```bash
npx lark-cli api GET /open-apis/calendar/v4/calendars
```

### 示例 7: 查看 API Schema

```bash
npx lark-cli schema calendar.calendar.list
```

---

## 实际使用反馈

- **优点**: 官方维护、命令覆盖飞书 14 个业务域、支持直接调用 OpenAPI 和 schema 查询、内置 Agent Skills
- **限制**: 命令名与包名不一致（包 `@larksuite/cli`，命令 `lark-cli`）；部分接口需要额外申请 scope
- **适用场景**: 飞书自动化运维、日历/文档/通讯录管理、企业工作流集成

---

## 风险提示

- 调用飞书 OpenAPI 需要应用 ID 和应用密钥（App ID / App Secret），请妥善保管
- 部分操作涉及企业敏感数据，建议遵循最小权限原则配置应用权限
- 高频调用可能触发平台限流，建议在自动化场景中控制调用频率
