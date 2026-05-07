---
categories: text
types: [essay]
topics:
  - "[[AI 模型知识库]]"
  - "[[MiMo-V2.5-Pro]]"
  - "[[kimi-k2.5]]"
  - "[[DeepSeek-V4-Pro]]"
title: AI 模型并发能力
summary: 汇总 mimo-v2.5-pro、kimi-k2.5、deepseek-v4-pro 三个模型的并发测试结果：三者 50 并发内均全部成功，偶发 429 更像瞬时抖动而非硬上限。provider 并发不是当前 OpenClaw 子代理超时的主瓶颈。deepseek-v4-pro max_tokens=393216（384K）API 接受。
date: 2026-05-07
source:
  - "[[Literature/mimo-v2.5-pro 并发测试]]"
  - "[[Literature/kimi-k2.5 并发测试]]"
  - "[[Literature/deepseek-v4-pro 并发测试]]"
author:
  - 艾伯
tags: [active]
---

# AI 模型并发能力

这页把两份并发测试拉到同一张表里看，目的是判断 provider（模型服务商）会不会成为系统瓶颈，而不是单独夸某个模型数字好看。

## 我的判断

从现有结果看，provider 并发不是主要矛盾。[[mimo-v2.5-pro]] 在 50 并发内全成功，[[kimi-k2.5]] 只有少量偶发 429，而且 30 到 50 并发又恢复全成功，更像服务端瞬时抖动，不像硬上限。真正更像瓶颈的是上层系统的 spawn（子任务拉起）处理能力。

## 怎么用

| 场景 | 用法 |
|------|------|
| 设计子代理并发 | 先别急着把锅甩给 provider |
| 遇到 429 | 先区分偶发抖动和稳定硬上限 |
| 判断系统瓶颈 | 要把框架层和 provider 层拆开看 |

## 横向比较

| 模型 | Provider | 50 并发表现 | 主要观察 |
|------|----------|--------------|----------|
| [[mimo-v2.5-pro]] | xiaomi_tokenPlan | 全成功 | provider 侧无明显瓶颈 |
| [[kimi-k2.5]] | moonshot | 基本全成功 | 10~20 并发偶发 429，更像抖动 |
| [[DeepSeek-V4-Pro]] | deepseek | 全成功 | 50 并发零 429，max_tokens=384K 可用 |

## 参考文献

- [[Literature/mimo-v2.5-pro 并发测试]]
- [[Literature/kimi-k2.5 并发测试]]
- [[Literature/deepseek-v4-pro 并发测试]]
