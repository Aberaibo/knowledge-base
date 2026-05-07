---
title: obsidian-git 连接 GitHub 报错
date: 2026-05-08
source: "[[Raws/obsidian-git 连接 GitHub 报错]]"
author: 艾伯
tags: [obsidian, git, troubleshooting, network, promoted]
promoted_to:
  - "[[Permanent/Obsidian Git 插件：从零建仓配置]]"
---

# obsidian-git 插件连接 GitHub 报错

> 源：[[Raws/obsidian-git 连接 GitHub 报错]] | 实测 2026-05-08

## 关键事实

**现象**: Auto pull on startup 报 `Failed to connect to github.com port 443`。

**根因**: 国内直连 GitHub 443 被墙。

**解决**: `git config --global http.proxy http://127.0.0.1:端口` + `https.proxy` 同样设置。

**验证**: `git ls-remote https://github.com/用户名/仓库名.git` 能通就行。

**备选**: Obsidian Global Proxy 插件（适用于插件不读 git 全局配置的情况）。

**进阶报错**: 配代理后出现 `RPC failed; curl 28 Recv failure: Connection was reset` → `git config --global http.postBuffer 524288000`；仍不稳补 `http.lowSpeedLimit 0` + `http.lowSpeedTime 999999`
- **conflicts 冲突**: 远端被 force push → `git fetch origin && git reset --hard origin/master`
- **合并多个提交**: `git rebase -i HEAD~N` squash → `git push --force`

## 参考文献

- [[Raws/obsidian-git 连接 GitHub 报错]]
