# wechaty

> 跨平台聊天机器人 RPA SDK，支持微信/企微/WhatsApp

- **来源**: 第三方
- **安装方式**: `npm install wechaty`
- **官方链接**: [wechaty/wechaty](https://github.com/wechaty/wechaty)
- **语言**: TypeScript / Node.js
- **Stars**: ~22.7k

---

## 验证状态

| 检查项 | 状态 | 备注 |
|--------|------|------|
| 安装可执行 | ✅ 通过 | `npm install -g wechaty` 成功 |
| 基础命令可运行 | ⚠️ 部分通过 | 全局 `wechaty` 命令未自动注入 PATH，建议用 `npx wechaty` 调用 |
| 实际功能可用 | ⚠️ 待确认 | 需配置 Puppet Provider 和 Token 后才能运行 Bot |

> 验证时间: 2026-04-14  
> 验证环境: macOS / node v22.14.0

---

## 接口说明

```
wechaty <subcommand>
> Wechaty CLI Utility

where <subcommand> can be one of:

- friday      - Contact Friday BOT and talk to him!
- gateway     - Publish your DIY token as a Wechaty Puppet Service
- provider    - Manage Wechaty Puppet Provider (WPP)
- service     - Manage Wechaty Puppet Service (WPS)
- token       - Generate & Discover TOKEN for Wechaty

For more help, try running `wechaty <subcommand> --help`
```

---

## 使用示例

### 示例 1: 查看版本

```bash
npx wechaty --version
```

**输出示例**:

```
1.20.2
```

### 示例 2: 查看 Token 帮助

```bash
npx wechaty token --help
```

### 示例 3: 生成 Token

```bash
npx wechaty token generate
```

---

## 实际使用反馈

- **优点**: 生态成熟、跨平台（微信/企微/WhatsApp 等）、提供 CLI 辅助工具（token/provider/service 管理）
- **限制**: 核心 Bot 功能仍需编写代码调用 SDK；运行 Bot 需要 Puppet Provider（部分收费）；全局安装后命令未自动注入 PATH
- **适用场景**: 聊天机器人开发、客服自动化、社群管理

---

## 风险提示

- 使用微信 Bot 存在封号风险，建议用小号测试
- 部分 Puppet Provider 是商业服务，使用时请注意资费
