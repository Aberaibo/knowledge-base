---
categories: [text]
types: [essay]
topics:
  - obsidian
  - git
  - plugins
title: Obsidian Git 插件：从零建仓配置
summary: Windows 桌面端 Obsidian Git 插件的克隆配置教程，一行 git clone 拿仓库，装插件开自动同步，不需要在插件里配 token。
date: 2026-05-08
source:
  - "[[Literature/Obsidian Git 插件配置]]"
author: 艾伯
tags: [active]
---

# Obsidian Git 插件：从零建仓配置

你的 vault 已经在 GitHub 上了（比如 `Aberaibo/knowledge-base`），现在只需要在新电脑上拉下来、让 Obsidian 自动同步。

## 一步：克隆仓库

用 Git Bash 把 vault 拉到本地：

```bash
git clone https://github.com/你的用户名/仓库名.git
```

克隆下来的文件夹就是一个完整的 Obsidian vault。

## 二步：用 Obsidian 打开

Obsidian → 打开其他仓库 → 打开本地仓库 → 选刚才克隆的文件夹。

## 三步：装 Obsidian Git 插件

设置 → 第三方插件 → 关闭安全模式 → 浏览 → 搜 `Obsidian Git`（Vinzent03）→ 安装并启用。

## 四步：开自动同步

插件设置里只改两个开关：

| 设置 | 值 | 效果 |
|------|-----|------|
| **Auto pull on startup** | 开 | 每次打开 Obsidian 自动 git pull |
| **Auto commit-and-sync interval** | 30 | 每 30 分钟自动 commit + pull + push |

不需要配 remote、不需要填 username、不需要填 token。插件直接用你系统 git 的认证——Windows 上 `git config --global credential.helper manager-core` 在你第一次在 Git Bash 里 push 输过密码后就记住了。

## 五步：加 .gitignore

`Ctrl+P` → `Edit .gitignore`，跳过不需要同步的文件：

```
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/cache
.trash/
.DS_Store
```

## 日常

配完就不用管了：
- 打开 Obsidian → 自动拉最新版
- 边写笔记 → 每 30 分钟自动备份到 GitHub
- 想手动同步 → `Ctrl+P` → `Commit-and-sync`

## 避坑

1. 移动端别用（isomorphic-git 不稳定，不支持大仓库）
2. 多设备同时编辑同一文件 → 可能冲突，打开 Pull on startup before commit
3. 不需要在插件里配 token——身份认证走系统 git，不是你该操心的事
4. **国内网络直连 GitHub 443 被墙** → 设 git 代理：`git config --global http.proxy http://127.0.0.1:端口`，常见端口 Clash 7890 / V2Ray 10809
5. **代理通后报 RPC failed / Connection reset** → `git config --global http.postBuffer 524288000`；仍不稳则补 `git config --global http.lowSpeedLimit 0` 和 `git config --global http.lowSpeedTime 999999`

## 参考文献

- [[Literature/Obsidian Git 插件配置]]
- https://github.com/Vinzent03/obsidian-git
