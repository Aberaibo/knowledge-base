---
title: obsidian-git 国内连接 GitHub 报错
date: 2026-05-08
types: [fleeting]
source: "实测：2026-05-08 Windows 桌面端 Obsidian Git 插件 Auto pull on startup 报错"
author: 艾伯
tags: [obsidian, git, troubleshooting, network]
---

# obsidian-git 插件连接 GitHub 报错

## 现象

开启 Auto pull on startup 后，Obsidian 启动时报错：

```
fatal: unable to access 'https://github.com/...git/':
Failed to connect to github.com port 443 after 21121 ms:
Could not connect to server
```

## 根因

国内网络直连 GitHub 443 端口被阻，Obsidian Git 插件的 git 请求到不了 github.com。

## 解决方案

设置 git 全局代理（Git Bash 中执行）：

```
git config --global http.proxy http://127.0.0.1:代理端口
git config --global https.proxy http://127.0.0.1:代理端口
```

验证：`git ls-remote https://github.com/用户名/仓库名.git`

如果不知道代理端口：Clash 默认 7890，V2Ray 默认 10809，SSR 默认 1080。TUN 模式（虚拟网卡）无需额外设置。

备选方案：装 Obsidian Global Proxy 插件，适用于插件不用系统 git 而自己发 HTTP 请求的情况。

## 进阶报错：RPC failed / Connection reset

配置代理后可能出现传输中断：

```
error: RPC failed; curl 28 Recv failure: Connection was reset
fatal: expected 'acknowledgments'
```

根因：代理传输大块数据时超时，git 默认 1MB 缓冲区不够。

解决：
```
git config --global http.postBuffer 524288000
```

加强版：
```
git config --global http.lowSpeedLimit 0
git config --global http.lowSpeedTime 999999
```

## 进阶报错：合并冲突（Conflicts）

自动 pull 时远端历史被 force push 改写，本地报：

```
You have conflicts in 3 files
```

根因：远端 commit 历史被改写（force push / amend），本地和远端分叉。

解决（Git Bash 中 cd 到 vault 文件夹）：
```
git fetch origin
git reset --hard origin/master
```

⚠️ `git reset --hard` 会丢弃本地修改，执行前确认没有未备份的新笔记。

如果远端想合并多个提交再推（减少分叉概率）：
```
git rebase -i HEAD~N   # N=要合并的 commit 数
# 编辑器里把第 2 行起 pick → squash，保存
# 合并提交消息，保存退出
git push --force origin master
```
