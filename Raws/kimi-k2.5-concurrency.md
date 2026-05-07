---
tags: [ai-model, moonshot, kimi, concurrency, performance]
provider: moonshot
model: kimi-k2.5
test_date: 2026-05-01
---

# kimi-k2.5 并发测试

## 测试环境
- Provider: moonshot
- Base URL: https://api.moonshot.cn/v1
- Model: kimi-k2.5
- 测试方法：同时发 N 个 chat/completions 请求，每个 max_tokens=5

## 测试结果

| 并发数 | 成功 | 429 | 其它错误 |
|--------|------|-----|----------|
| 5 | 5 | 0 | 0 |
| 10 | 9 | 1 | 0 |
| 15 | 14 | 1 | 0 |
| 20 | 19 | 1 | 0 |
| 30 | 30 | 0 | 0 |
| 50 | 50 | 0 | 0 |

## 结论
- 并发 10-20 时偶尔 429（"engine_overloaded"），不是 rate limit 而是服务端负载波动
- **并发 30-50 反而全成功**，说明 429 是偶发的，不是硬性并发限制
- moonshot 的并发能力足够支撑 OpenClaw 子代理场景
- 429 错误信息：`{"error":{"message":"The engine is currently overloaded, please try again later","type":"engine_overloaded"}}`

## 关联
- [[subagent-concurrency]]
- [[mimo-v2.5-pro-concurrency]]
