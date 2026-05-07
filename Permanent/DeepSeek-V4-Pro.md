---
categories: text
types: [article]
topics:
  - "[[AI 模型知识库]]"
  - "[[DeepSeek API 平台]]"
  - "[[DeepSeek 定价与规格]]"
title: DeepSeek-V4-Pro
summary: DeepSeek-V4-Pro 是 DeepSeek 当前公开的高价位主力模型，支持 1M 上下文、384K 最大输出、JSON Output、Tool Calls 和思考模式；截至 2026-05-07，官网当前有效价格是 2.5 折后的 3 元输入 / 6 元输出每百万 tokens，而不是页面同时显示的 12 / 24 元原价。
date: 2026-05-07
source:
  - "[[Literature/DeepSeek 模型与价格]]"
  - "[[Literature/DeepSeek 思考模式]]"
  - "[[Literature/DeepSeek Tool Calls]]"
author:
  - 艾伯
tags: [active]
---

# DeepSeek-V4-Pro

[[DeepSeek-V4-Pro]] 是 DeepSeek 当前公开的高规格主力型号。它最容易被读错的不是规格，而是官网价格：页面同一格里同时显示折后价和原价，当前有效价要按 2.5 折后的 3 / 6 元来读，不是按 12 / 24 元来读。

## 我的判断

仅从现有官网资料看，[[DeepSeek-V4-Pro]] 的核心问题不再是“当前价格离谱”，而是“折后进入可比区间后，到底值不值得当主力”。也就是说，后续争议的重点应该从“看错价格”切回“质量、并发、真实 Agent 场景表现配不配这个价”。

## 怎么用

| 需求 | 是否适合 |
|------|----------|
| DeepSeek 高规格主力 | 适合关注 |
| thinking / JSON / Tool Calls | 支持 |
| 折扣期候选评估 | 值得继续测 |

## 横向比较

### 当前有效价格（人民币 / 百万 tokens）

| 项目 | DeepSeek-V4-Pro | [[DeepSeek-V4-Flash]] |
|------|------------------|-----------------------|
| 缓存命中输入 | 0.025 元 | 0.02 元 |
| 未命中输入 | 3 元 | 1 元 |
| 输出 | 6 元 | 2 元 |

### 防误读：Pro 页面同时展示的两组价格

| 项目 | 当前折后价 | 原价 |
|------|------------|------|
| 缓存命中输入 | 0.025 元 | 0.1 元 |
| 未命中输入 | 3 元 | 12 元 |
| 输出 | 6 元 | 24 元 |

### 折扣有效期

| 页面 | 到期时间 | 含义 |
|------|----------|------|
| 中文页 | 北京时间 2026-05-31 23:59 | 当前 2.5 折到这个时间点为止 |
| 英文页 | UTC 2026-05-31 15:59 | 与中文页是同一个截止时刻 |

## 参考文献

- [[Literature/DeepSeek 模型与价格]]
- [[Literature/DeepSeek 思考模式]]
- [[Literature/DeepSeek Tool Calls]]
