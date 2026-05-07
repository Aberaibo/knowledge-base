---
title: DeepSeek API 接入概览
date: 2026-05-07
source:
  - "[[Raws/deepseek-api-home.md]]"
author:
  - 艾伯
tags: [active, promoted]
promoted_to:
  - "[[Permanent/DeepSeek API 平台]]"
  - "[[Permanent/DeepSeek-V4-Flash]]"
---

# DeepSeek API 接入概览

这份文献笔记整理 DeepSeek API 首页里最关键的接入信息，包括模型名、兼容协议、基础地址（base URL）和旧模型名弃用信息。

## 关键事实

| 项目 | 值 |
|------|----|
| OpenAI 格式 base URL | `https://api.deepseek.com` |
| Anthropic 格式 base URL | `https://api.deepseek.com/anthropic` |
| 当前主模型名 | `deepseek-v4-flash`、`deepseek-v4-pro` |
| 兼容旧模型名 | `deepseek-chat`、`deepseek-reasoner` |
| 旧模型名弃用时间 | 2026-07-24 |

## 关键摘录

| 类别 | 内容 |
|------|------|
| 兼容性 | DeepSeek API 同时兼容 OpenAI 与 Anthropic 生态 |
| 迁移成本 | 可继续使用现有 SDK（软件开发工具包）或兼容软件 |
| 旧名映射 | `deepseek-chat` / `deepseek-reasoner` 对应 `deepseek-v4-flash` 的非思考 / 思考模式 |

## 值得关注

- 旧模型名已经给出明确弃用日期，配置层不该继续长期依赖兼容别名。
- 文档首页强调的不是 benchmark（基准测试）成绩，而是“接入门槛低”和“兼容主流 API 形态”。
- 这类首页更适合提炼接入层结论，不适合单独承担完整规格页。

## 参考文献

- [[Raws/deepseek-api-home.md]]
