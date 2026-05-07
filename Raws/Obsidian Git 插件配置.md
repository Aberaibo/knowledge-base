---
title: Obsidian Git 插件配置
date: 2026-05-08
types: [fleeting]
source: "https://github.com/Vinzent03/obsidian-git"
author: 艾伯
tags: [obsidian, git, plugins, tutorial]
---

# Obsidian Git 插件：克隆配置

基于官方 README（2026-05），针对 Windows 桌面端的简洁流程。

## 前提
- Windows 桌面端，Git 已装
- Vault 已在 GitHub 上

## 四步配置

1. Git Bash 克隆: `git clone https://github.com/用户名/仓库名.git`
2. Obsidian 打开克隆的文件夹
3. 装 Obsidian Git 插件（Vinzent03）
4. 开两个开关:
   - Auto pull on startup: 开
   - Auto commit-and-sync interval: 30 分钟

## 不需要做的事
- 不需要配 remote（clone 自动带了）
- 不需要填 token/username（认证走系统 git，Windows credential.helper 记住的）

## .gitignore
```
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/cache
.trash/
.DS_Store
```

## 日常
- 打开 Obsidian → 自动 pull
- 每 30 分钟 → 自动 commit+pull+push
- 手动同步 → Ctrl+P → Commit-and-sync
