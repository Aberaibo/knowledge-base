---
categories: text
types: [article]
topics:
  - "[[AI 模型知识库]]"
  - "[[DeepSeek-V4-Pro]]"
  - "[[DeepSeek-V4-Flash]]"
title: DeepSeek API 平台
summary: DeepSeek API 平台的核心价值是同时兼容 OpenAI 与 Anthropic 两套主流接口：OpenAI 格式走 https://api.deepseek.com，Anthropic 格式走 https://api.deepseek.com/anthropic，并且已经给出 deepseek-chat 与 deepseek-reasoner 向 v4 模型名迁移的弃用时间点。
date: 2026-05-07
source:
  - "[[Literature/DeepSeek API 接入概览]]"
  - "[[Literature/DeepSeek Anthropic 兼容接口]]"
author:
  - 艾伯
tags: [active]
---

# DeepSeek API 平台

[[DeepSeek API 平台]] 这页关心的是接入层，而不是模型能力吹风。对项目来说，它的意义在于：DeepSeek 不是另起一套奇怪协议，而是尽量贴住 OpenAI（应用程序接口）和 Anthropic（应用程序接口）生态。

## 我的判断

如果后面要把 DeepSeek 纳入 AI 模型知识库的候选模型池，它最值钱的不是一句“模型很强”，而是迁移成本低。现有依赖 OpenAI 或 Anthropic SDK（软件开发工具包）的系统，只要改 base URL（基础地址）和模型名，就能较快接进去。

## 怎么用

| 接入方向 | 地址 / 动作 |
|----------|-------------|
| OpenAI 兼容流 | `https://api.deepseek.com` |
| Anthropic 兼容流 | `https://api.deepseek.com/anthropic` |
| 配置迁移 | 尽快从 `deepseek-chat` / `deepseek-reasoner` 切到 `deepseek-v4-flash` / `deepseek-v4-pro` |

## 横向比较

| 维度 | OpenAI 兼容流 | Anthropic 兼容流 |
|------|---------------|------------------|
| base URL | `https://api.deepseek.com` | `https://api.deepseek.com/anthropic` |
| 主要价值 | 接现有 OpenAI 生态 | 接现有 Anthropic 生态 |
| 注意点 | 旧模型名迁移 | 字段兼容不是全量等价 |

## 参考文献

- [[Literature/DeepSeek API 接入概览]]
- [[Literature/DeepSeek Anthropic 兼容接口]]
