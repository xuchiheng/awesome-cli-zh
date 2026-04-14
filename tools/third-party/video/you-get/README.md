# you-get

> 多平台视频/音频/图片下载器（B站/优酷/爱奇艺/搜狐/网易等）

- **来源**: 第三方
- **安装方式**: `pip install you-get` / `brew install you-get`
- **官方链接**: [soimort/you-get](https://github.com/soimort/you-get)
- **语言**: Python
- **Stars**: ~56.8k

---

## 验证状态

| 检查项 | 状态 | 备注 |
|--------|------|------|
| 安装可执行 | ✅ 通过 | `pip3 install you-get` 成功 |
| 基础命令可运行 | ✅ 通过 | `--help`、`--version` 正常 |
| 实际功能可用 | ⚠️ 待确认 | 部分站点可能因反爬或网络问题解析失败 |

> 验证时间: 2026-04-14  
> 验证环境: macOS / python3 3.11.9

---

## 接口说明

```
you-get: version 0.4.1743, a tiny downloader that scrapes the web.
usage: you-get [OPTION]... URL...

A tiny downloader that scrapes the web

options:
  -V, --version         Print version and exit
  -h, --help            Print this help message and exit

Dry-run options:
  (no actual downloading)
  -i, --info            Print extracted information
  -u, --url             Print extracted information with URLs
  --json                Print extracted URLs in JSON format

Download options:
  -n, --no-merge        Do not merge video parts
  --no-caption          Do not download captions
  --post, --postfix     Postfix downloaded files with unique identifiers
  --pre PREFIX          Prefix downloaded files with string
  -f, --force           Force overwriting existing files
  -F STREAM_ID          Set video format to STREAM_ID
  -O FILE               Set output filename
  -o DIR                Set output directory
  -p, --player PLAYER   Stream extracted URL to a PLAYER
  -c COOKIES_FILE       Load cookies.txt or cookies.sqlite
```

---

## 使用示例

### 示例 1: 仅查看视频信息（不下载）

```bash
you-get -i "https://www.bilibili.com/video/BV1GJ411x7h7"
```

**输出示例**:

```
you-get: [error] oops, something went wrong.
you-get: don't panic, c'est la vie. please try the following steps:
you-get:   (1) Rule out any network problem.
you-get:   (2) Make sure you-get is up-to-date.
you-get:   (3) Check if the issue is already known, on
you-get:         https://github.com/soimort/you-get/wiki/Known-Bugs
you-get:         https://github.com/soimort/you-get/issues
you-get:   (4) Run the command with '--debug' option,
you-get:       and report this issue with the full output.
```

> 注：示例 URL 可能因视频不存在、地区限制或反爬策略导致解析失败。建议换用当前有效的视频链接重试。

### 示例 2: 下载视频

```bash
you-get "https://www.bilibili.com/video/BVxxxxx"
```

---

## 实际使用反馈

- **优点**: 支持站点极多、纯命令行、可配合 cookies 下载会员内容
- **限制**: 视频平台反爬策略频繁更新，遇到解析失败需升级到最新版或配合 cookies
- **适用场景**: 批量下载、脚本自动化、离线备份公开视频

---

## 风险提示

- 下载受版权保护的内容可能违反平台用户协议和当地法律法规
- 部分平台需要携带登录 cookies，注意 Cookie 安全
