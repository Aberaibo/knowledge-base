---
title: Obsidian Git 插件配置
date: 2026-05-08
source: "[[Raws/Obsidian Git 插件配置]]"
author: 艾伯
tags: [obsidian, git, plugins, promoted]
promoted_to:
  - "[[Permanent/Obsidian Git 插件：从零建仓配置]]"
---

# Obsidian Git 插件：克隆配置

> 源：[[Raws/Obsidian Git 插件配置]] | 基于官方 README (2026-05)

## 关键事实

**适用场景**: Windows 桌面端，vault 已在 GitHub 上，在新电脑上克隆后自动同步。

**四步配置**:
1. `git clone` 拉仓库到本地
2. Obsidian 打开克隆的文件夹
3. 装 Obsidian Git 插件
4. 开两个开关：Auto pull on startup + Auto commit-and-sync interval (30 分钟)

**不需要做的事**: 配 remote、填 token、填 username。认证走系统 git（Windows 上用 credential.helper manager-core），跟插件无关。

**.gitignore 建议**: `.obsidian/workspace.json`, `.obsidian/cache`, `.trash/`, `.DS_Store`

## 值得注意的点

- 插件认证走系统 git，不需要在插件设置里填任何凭据
- 桌面端稳定，移动端不可靠
- 多设备同时编辑用 Pull on startup before commit 防冲突
- 改了文件名导致大量文件变动时，手动 Commit-and-sync 一次，别等定时器

## 参考文献

- [[Raws/Obsidian Git 插件配置]]
- https://github.com/Vinzent03/obsidian-git
