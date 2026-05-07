---
title: DeepSeek Tool Calls
date: 2026-05-07
source:
  - "[[Raws/deepseek-tool-calls.md]]"
author:
  - 艾伯
tags: [active, promoted]
promoted_to:
  - "[[Permanent/DeepSeek-V4-Pro]]"
---

# DeepSeek Tool Calls

这份文献笔记整理 DeepSeek 的工具调用能力与 strict（严格）模式约束，重点是接入要求和 Schema（数据结构约束）边界。

## 关键事实

| 项目 | 内容 |
|------|------|
| 普通 Tool Calls | 支持 |
| thinking 模式 Tool Calls | 支持（从 DeepSeek-V3.2 开始） |
| strict 模式 base URL | `https://api.deepseek.com/beta` |
| strict 模式 function 要求 | `strict: true` |
| Schema 额外要求 | `additionalProperties: false`、对象属性需进入 `required` |

## 关键摘录

| 类别 | 内容 |
|------|------|
| strict 目标 | 保证 function 输出严格符合 JSON Schema |
| 支持类型 | object / string / number / integer / boolean / array / enum / anyOf / `$ref` / `$def` |
| 接入含义 | 不是只开开关，还要把工具声明写规整 |

## 值得关注

- strict 模式提升的是结构稳定性，不是模型智力本身。
- 对工具调用链来说，Schema（数据结构定义）如果写松了，strict 模式也救不了接入质量。
- 适合和 thinking 模式一起看，因为这两者在 Agent（智能体）场景下通常同时出现。

## 参考文献

- [[Raws/deepseek-tool-calls.md]]
