---
categories: text
types: [article]
topics:
  - "[[AI 模型知识库]]"
  - "[[DeepSeek API 平台]]"
  - "[[DeepSeek 定价与规格]]"
title: DeepSeek-V4-Flash
summary: DeepSeek-V4-Flash 是 DeepSeek 当前公开的主力模型之一，支持 1M 上下文、384K 最大输出、JSON Output、Tool Calls，以及非思考与思考两种模式；它同时承接了旧模型名 deepseek-chat 与 deepseek-reasoner 的兼容映射。
date: 2026-05-07
source:
  - "[[Literature/DeepSeek API 接入概览]]"
  - "[[Literature/DeepSeek 模型与价格]]"
  - "[[Literature/DeepSeek 思考模式]]"
author:
  - 艾伯
tags: [active]
---

# DeepSeek-V4-Flash

[[DeepSeek-V4-Flash]] 是目前 DeepSeek 文档里最像“默认主力通用款”的型号。它既是 v4 正式模型名，又承接了旧时代的 `deepseek-chat` / `deepseek-reasoner` 兼容映射。

## 我的判断

这类模型页最关键的信息不是“它支持 thinking”，而是它把两种模式都塞进同一个模型名体系里了。也就是说，DeepSeek 把“模型选择”和“思考开关”拆开了，而不是像旧名字那样一名一态。

## 怎么用

| 需求 | 是否适合 |
|------|----------|
| 通用接入 | 适合 |
| 大上下文 | 适合 |
| JSON / Tool Calls | 支持 |
| 低成本候选 | 比 Pro 更友好 |

## 横向比较

| 维度 | DeepSeek-V4-Flash | [[DeepSeek-V4-Pro]] |
|------|-------------------|---------------------|
| 模式 | 非思考 / 思考都支持 | 非思考 / 思考都支持 |
| 上下文 | 1M | 1M |
| 最大输出 | 384K | 384K |
| 价格 | 更低 | 更高 |
| 当前定位 | 默认主力通用款 | 高价位旗舰候选 |

## 参考文献

- [[Literature/DeepSeek API 接入概览]]
- [[Literature/DeepSeek 模型与价格]]
- [[Literature/DeepSeek 思考模式]]
