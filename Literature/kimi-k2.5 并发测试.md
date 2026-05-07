---
title: kimi-k2.5 并发测试
date: 2026-05-07
source:
  - "[[Raws/kimi-k2.5-concurrency.md]]"
author:
  - 艾伯
tags: [active, promoted]
promoted_to:
  - "[[Permanent/AI 模型并发能力]]"
  - "[[Permanent/kimi-k2.5]]"
---

# kimi-k2.5 并发测试

这份文献笔记记录 kimi-k2.5 在 moonshot provider 下的并发测试结果，重点是看 429（限流或过载错误）是否构成明确瓶颈。

## 关键事实

| 项目 | 值 |
|------|----|
| Provider | moonshot |
| Base URL | `https://api.moonshot.cn/v1` |
| Model | `kimi-k2.5` |
| 测试方法 | 同时发 N 个 chat/completions 请求，每个 `max_tokens=5` |

## 关键摘录

| 并发数 | 成功 | 429 | 其它错误 |
|--------|------|-----|----------|
| 5 | 5 | 0 | 0 |
| 10 | 9 | 1 | 0 |
| 15 | 14 | 1 | 0 |
| 20 | 19 | 1 | 0 |
| 30 | 30 | 0 | 0 |
| 50 | 50 | 0 | 0 |

## 值得关注

- 10 到 20 并发时偶发 429，但 30 到 50 并发又恢复全成功，更像服务端抖动而不是硬上限。
- 错误类型是 `engine_overloaded`，不是典型的硬限流文案。
- 适合和 MiMo 并发测试放在同一页比较，而不是单独得出过强结论。

## 参考文献

- [[Raws/kimi-k2.5-concurrency.md]]
