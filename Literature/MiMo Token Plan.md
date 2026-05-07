---
title: MiMo Token Plan
date: 2026-05-07
source:
  - "[[Raws/mimo-token-plan.md]]"
author:
  - 艾伯
tags: [active, promoted]
promoted_to:
  - "[[Permanent/MiMo Token Plan]]"
---

# MiMo Token Plan

这份文献笔记整理 MiMo 平台的按量计费方案，重点是把 MiMo-V2.5 与 MiMo-V2.5-Pro 的两档上下文价格拉平比较。

## 关键事实

| 模型 | 上下文 | 输入 | 缓存命中 | 输出 |
|------|--------|------|----------|------|
| mimo-v2.5-pro | ≤256K | $1.00/M | $0.20/M | $3.00/M |
| mimo-v2.5-pro | ≤1M | $2.00/M | $0.40/M | $6.00/M |
| mimo-v2.5 | ≤256K | $0.40/M | $0.08/M | $2.00/M |
| mimo-v2.5 | ≤1M | $0.80/M | $0.16/M | $4.00/M |

## 关键摘录

| 规则 | 内容 |
|------|------|
| mimo-v2.5 | 1 Token = 1 Credit |
| mimo-v2.5-pro | 1 Token = 2 Credits |
| 其它 | 夜间调用享 8 折，连续包月低至 7 折 |
| 说明 | 不再区分 256K / 1M 的 Credit 倍率，但美元定价仍按上下文档位区分 |

## 值得关注

- MiMo 的真正成本分界点还是 256K，不是宣传文案里的“1M 上下文”。
- Pro 档位比基础版更贵，而且过 256K 后还会继续上一个台阶。
- 这页适合做成本资料页，不适合承担模型能力判断。

## 参考文献

- [[Raws/mimo-token-plan.md]]
