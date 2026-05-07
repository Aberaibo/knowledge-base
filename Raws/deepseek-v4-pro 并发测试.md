---
title: deepseek-v4-pro 并发测试
date: 2026-05-07
types: [fleeting]
source: "实测：session 752e58f0, 脚本 quick-ke"
author: 艾伯
tags: [ai-model, deepseek, concurrency, benchmark]
---

# DeepSeek V4 Pro 并发测试

## 测试环境
- Provider: deepseek
- Model: deepseek-v4-pro
- Base URL: https://api.deepseek.com
- 测试方式: curl 并发请求，max_tokens=5 最小化成本
- 测试日期: 2026-05-07

## max_tokens 验证

| 设置值 | HTTP | finish_reason | 结论 |
|--------|------|---------------|------|
| 4096 | 200 | stop | ✅ |
| 8192 | 200 | stop | ✅ |
| 131072 | 200 | stop | ✅ |
| 393216 | 200 | stop | ✅ |

结论：`max_tokens=393216`（384K）API 接受并正常返回。

## 并发测试结果

| 并发数 | 200 | 429 | 其它 | 耗时 |
|--------|-----|-----|------|------|
| 5 | 5 | 0 | 0 | 1.1s |
| 10 | 10 | 0 | 0 | 1.8s |
| 15 | 15 | 0 | 0 | 1.3s |
| 20 | 20 | 0 | 0 | 1.4s |
| 30 | 30 | 0 | 0 | 2.6s |
| 50 | 50 | 0 | 0 | 1.9s |

结论：50 并发全成功，零 429（限流），未继续往上测。
