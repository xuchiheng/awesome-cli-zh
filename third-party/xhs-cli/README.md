# xhs-cli

> 小红书 CLI：搜索、阅读、点赞、收藏、评论，Chrome Cookie 提取

- **来源**: 第三方
- **安装方式**: `uv tool install xhs-cli` / `pipx install xhs-cli`
- **官方链接**: [jackwener/xhs-cli](https://github.com/jackwener/xhs-cli)
- **语言**: Python
- **Stars**: ~439

---

## 验证状态

| 检查项 | 状态 | 备注 |
|--------|------|------|
| 安装可执行 | ✅ 通过 | `uv tool install xhs-cli` 成功 |
| 基础命令可运行 | ✅ 通过 | `xhs --help` 正常 |
| 实际功能可用 | ⚠️ 待确认 | 与 `xiaohongshu-cli` 命令名冲突，同时安装会被覆盖 |

> 验证时间: 2026-04-14  
> 验证环境: macOS / python3 3.11.9 / uv 0.11.2

> ⚠️ **重要**：`xhs-cli` 安装后的全局命令也是 **`xhs`**，与同作者的 `xiaohongshu-cli` **命令名冲突**。不建议同时安装两者。

---

## 接口说明

```
Usage: xhs [OPTIONS] COMMAND [ARGS]...

  xhs — Xiaohongshu CLI via reverse-engineered API 📕

Options:
  --version             Show the version and exit.
  -v, --verbose         Enable debug logging
  --cookie-source TEXT  Browser to read cookies from
                        (auto = try all installed browsers)  [default: auto]
  --help                Show this message and exit.

Commands:
  comment         Post a comment on a note.
  comments        View comments on a note by ID, URL, or short index.
  delete          Delete a note.
  delete-comment  Delete a comment you posted.
  favorite        Favorite (bookmark) a note.
  favorites       List favorited (bookmarked) notes.
  feed            Browse the recommendation feed.
  follow          Follow a user.
```

---

## 使用示例

### 示例 1: 浏览推荐流

```bash
xhs feed
```

### 示例 2: 搜索笔记

```bash
xhs search "美食探店"
```

---

## 实际使用反馈

- **优点**: 轻量版小红书 CLI，支持浏览器 Cookie 自动提取
- **限制**: 功能与 `xiaohongshu-cli` 高度重叠，且两者命令名相同；Star 数较低，维护活跃度可能不如前者
- **适用场景**: 简单的内容浏览和采集任务

---

## 风险提示

- **风控警告**: 基于非官方 API，高频自动化调用可能导致账号限流或封禁
- 与 `xiaohongshu-cli` 命令冲突，建议根据功能需求二选一安装
