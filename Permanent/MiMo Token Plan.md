---
categories: text
types: [article]
topics:
  - "[[AI 模型知识库]]"
  - "[[MiMo-V2.5-Pro]]"
  - "[[MiMo-V2.5]]"
title: MiMo Token Plan
summary: MiMo Token Plan 记录了 MiMo-V2.5 与 MiMo-V2.5-Pro 的按量计费规则，包括 256K 与 1M 上下文两档价格、缓存命中价格，以及 mimo-v2.5-pro 在超过 256K 上下文后成本翻倍这一关键成本分界线。
date: 2026-05-07
source:
  - "[[Literature/MiMo Token Plan]]"
author:
  - 艾伯
tags: [active]
---

# MiMo Token Plan

[[MiMo Token Plan]] 关心的不是模型能不能做，而是做一次要花多少钱。对长上下文和多子代理场景，这页很关键。

## 我的判断

真正该盯住的是 256K 上下文这条分界线。尤其是 [[MiMo-V2.5-Pro]]，超过 256K 后输入、缓存命中和输出价格都会翻倍，长会话如果不控上下文，成本会突然抬头。

## 怎么用

| 场景 | 看法 |
|------|------|
| 估算短任务 | 先看 256K 以内单价 |
| 估算长任务 | 按 1M 档位算 |
| 比较模型 | [[MiMo-V2.5]] 更便宜，[[MiMo-V2.5-Pro]] 更贵 |
| 设计系统 | 长会话要主动控上下文长度 |

## 横向比较

| 模型 | 上下文 | 输入 | 缓存命中 | 输出 |
|------|--------|------|----------|------|
| [[MiMo-V2.5-Pro]] | ≤256K | $1.00/M | $0.20/M | $3.00/M |
| [[MiMo-V2.5-Pro]] | ≤1M | $2.00/M | $0.40/M | $6.00/M |
| [[MiMo-V2.5]] | ≤256K | $0.40/M | $0.08/M | $2.00/M |
| [[MiMo-V2.5]] | ≤1M | $0.80/M | $0.16/M | $4.00/M |

## 参考文献

- [[Literature/MiMo Token Plan]]
- [[MiMo-V2.5-Pro]]
- [[MiMo-V2.5]]
