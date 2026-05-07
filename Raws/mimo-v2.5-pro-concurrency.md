---
tags: [ai-model, xiaomi, mimo, concurrency, performance]
provider: xiaomi_tokenPlan
model: mimo-v2.5-pro
test_date: 2026-05-01
---

# mimo-v2.5-pro 并发测试

## 测试环境
- Provider: xiaomi_tokenPlan
- Base URL: https://token-plan-cn.xiaomimimo.com/v1
- Model: mimo-v2.5-pro
- 测试方法：同时发 N 个 chat/completions 请求，每个 max_tokens=5

## 测试结果

| 并发数 | 成功 | 429 | 其它错误 |
|--------|------|-----|----------|
| 5 | 5 | 0 | 0 |
| 10 | 10 | 0 | 0 |
| 15 | 15 | 0 | 0 |
| 20 | 20 | 0 | 0 |
| 30 | 30 | 0 | 0 |
| 50 | 50 | 0 | 0 |

## 结论
- **并发 50 以内无明显限制**，全部成功
- 未测 50+（可能更高也没问题）
- 小米 provider 的并发上限很高，不是 OpenClaw 子代理超时的瓶颈
- 实际瓶颈是 OpenClaw gateway 的并发 spawn 处理能力

## 关联
- [[subagent-concurrency]]
- [[kimi-k2.5-concurrency]]
