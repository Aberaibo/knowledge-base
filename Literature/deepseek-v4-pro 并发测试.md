---
title: deepseek-v4-pro 并发测试
date: 2026-05-07
source: "[[Raws/deepseek-v4-pro 并发测试]]"
author: 艾伯
tags: [ai-model, deepseek, concurrency, promoted]
promoted_to:
  - "[[Permanent/AI 模型并发能力]]"
---

# deepseek-v4-pro 并发测试

> 源：[[Raws/deepseek-v4-pro 并发测试]]

## 测试环境

| 项目 | 值 |
|------|-----|
| Provider | deepseek |
| Model | deepseek-v4-pro |
| Base URL | https://api.deepseek.com |
| 测试方式 | curl 并发请求，max_tokens=5 最小化成本 |
| 测试日期 | 2026-05-07 |

## max_tokens 验证

| 设置值 | HTTP | finish_reason | 结论 |
|--------|------|---------------|------|
| 4096 | 200 | stop | ✅ |
| 8192 | 200 | stop | ✅ |
| 131072 | 200 | stop | ✅ |
| 393216 | 200 | stop | ✅ |

## 并发测试结果

| 并发数 | 200 | 429 | 其它 | 耗时 |
|--------|-----|-----|------|------|
| 5 | 5 | 0 | 0 | 1.1s |
| 10 | 10 | 0 | 0 | 1.8s |
| 15 | 15 | 0 | 0 | 1.3s |
| 20 | 20 | 0 | 0 | 1.4s |
| 30 | 30 | 0 | 0 | 2.6s |
| 50 | 50 | 0 | 0 | 1.9s |

## 关键发现

- deepseek-v4-pro `max_tokens=393216`（384K）API 接受并正常返回
- 50 并发全成功，零 429 限流，未继续往上测
- 与 [[mimo-v2.5-pro]] 和 [[kimi-k2.5]] 的并发表现一致：provider 侧不是并发瓶颈

## 参考文献

- [[Raws/deepseek-v4-pro 并发测试]]
- [[Literature/mimo-v2.5-pro 并发测试]]
- [[Literature/kimi-k2.5 并发测试]]
