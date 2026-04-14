# xiaohongshu-cli

> 小红书 CLI：搜索笔记、阅读、点赞、收藏、评论、发布，QR 码登录

- **来源**: 第三方
- **安装方式**: `uv tool install xiaohongshu-cli` / `pipx install xiaohongshu-cli`
- **官方链接**: [jackwener/xiaohongshu-cli](https://github.com/jackwener/xiaohongshu-cli)
- **语言**: Python
- **Stars**: ~1.6k

---

## 验证状态

| 检查项 | 状态 | 备注 |
|--------|------|------|
| 安装可执行 | ✅ 通过 | `uv tool install xiaohongshu-cli` 成功 |
| 基础命令可运行 | ✅ 通过 | `xhs --help`、`xhs --version` 正常 |
| 实际功能可用 | ⚠️ 待确认 | 需扫码登录或提取浏览器 Cookie 后才能进行写操作 |

> 验证时间: 2026-04-14  
> 验证环境: macOS / python3 3.11.9 / uv 0.11.2

> ⚠️ **重要**：安装后全局命令为 **`xhs`**，与 `xhs-cli`（同作者的另一项目）命令名**冲突**。若同时安装两者，后安装的会覆盖先安装的可执行文件。

---

## 接口说明

```
Usage: xhs [OPTIONS] COMMAND [ARGS]...

  xhs — Xiaohongshu CLI via reverse-engineered API

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
  ...
```

---

## 使用示例

### 示例 1: 浏览推荐流

```bash
xhs feed
```

### 示例 2: 搜索笔记

```bash
xhs search "旅行攻略"
```

### 示例 3: 查看笔记详情

```bash
xhs note <note_id>
```

### 示例 4: 收藏笔记

```bash
xhs favorite <note_id>
```

---

## 实际使用反馈

- **优点**: 功能完整（读/写/社交操作全覆盖）、支持 QR 码登录、支持自动读取浏览器 Cookie
- **限制**: 命令名与 `xhs-cli` 冲突；基于非官方逆向接口，频繁调用可能触发平台风控
- **适用场景**: 小红书内容采集、自动化运营、数据调研

---

## 风险提示

- **风控警告**: 基于非官方 API，高频自动化调用极易触发小红书风控，可能导致账号限流或封禁
- 建议注册小号、控制调用频率、避免在重要账号上使用
