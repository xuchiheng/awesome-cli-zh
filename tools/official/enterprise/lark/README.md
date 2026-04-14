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
| 基础命令可运行 | ⚠️ 部分通过 | 全局 `lark` 命令未自动加入 PATH，可执行文件实际为 `lark-cli`，可用 `npx lark-cli` 调用 |
| 实际功能可用 | ⚠️ 待确认 | 需飞书应用凭证或用户授权 |

> 验证时间: 2026-04-14  
> 验证环境: macOS / node v22.14.0

> ⚠️ **注意**：README 中标注的 CLI 名称为 `lark`，但全局安装后实际可执行文件名为 **`lark-cli`**。

---

## 接口说明

```
lark-cli — Lark/Feishu CLI tool.

USAGE:
    lark-cli <command> [subcommand] [method] [options]
    lark-cli api <method> <path> [--params <json>] [--data <json>]
    lark-cli schema <service.resource.method> [--format pretty]

EXAMPLES:
    # View upcoming events
    lark-cli calendar +agenda

    # List calendar events
    lark-cli calendar events instance_view --params '{"calendar_id":"primary",...}'

    # Search users
    lark-cli contact +search-user --query "John"

    # Generic API call
    lark-cli api GET /open-apis/calendar/v4/calendars

lark-cli version 1.0.10
```

---

## 使用示例

### 示例 1: 查看版本

```bash
npx lark-cli --version
```

**输出示例**:

```
lark-cli version 1.0.10
```

### 示例 2: 搜索用户

```bash
npx lark-cli contact +search-user --query "张三"
```

### 示例 3: 通用 API 调用

```bash
npx lark-cli api GET /open-apis/calendar/v4/calendars
```

---

## 实际使用反馈

- **优点**: 官方维护、命令覆盖飞书 14 个业务域、支持直接调用 OpenAPI 和 schema 查询
- **限制**: 命令名与包名不一致（包 `@larksuite/cli`，命令 `lark-cli`）；需先完成应用授权或用户登录
- **适用场景**: 飞书自动化运维、日历/文档/通讯录管理、企业工作流集成

---

## 风险提示

- 调用飞书 OpenAPI 需要应用 ID 和应用密钥（App ID / App Secret），请妥善保管
- 部分操作涉及企业敏感数据，建议遵循最小权限原则配置应用权限
