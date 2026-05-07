---
title: mimo-v2.5-pro 并发测试
date: 2026-05-07
source:
  - "[[Raws/mimo-v2.5-pro-concurrency.md]]"
author:
  - 艾伯
tags: [active, promoted]
promoted_to:
  - "[[Permanent/AI 模型并发能力]]"
---

# mimo-v2.5-pro 并发测试

这份文献笔记记录 mimo-v2.5-pro 在小米 provider 下的并发测试结果，重点是看 provider 侧会不会成为 OpenClaw 子代理的瓶颈。

## 关键事实

| 项目 | 值 |
|------|----|
| Provider | xiaomi_tokenPlan |
| Base URL | `https://token-plan-cn.xiaomimimo.com/v1` |
| Model | `mimo-v2.5-pro` |
| 测试方法 | 同时发 N 个 chat/completions 请求，每个 `max_tokens=5` |

## 关键摘录

| 并发数 | 成功 | 429 | 其它错误 |
|--------|------|-----|----------|
| 5 | 5 | 0 | 0 |
| 10 | 10 | 0 | 0 |
| 15 | 15 | 0 | 0 |
| 20 | 20 | 0 | 0 |
| 30 | 30 | 0 | 0 |
| 50 | 50 | 0 | 0 |

## 值得关注

- 50 并发内没有明显 provider 侧限制。
- 这说明当前子代理超时问题更像框架层瓶颈，而不是模型服务本身不行。
- 这页天然适合和 kimi 的测试结果并排放进同一张总表。

## 参考文献

- [[Raws/mimo-v2.5-pro-concurrency.md]]
