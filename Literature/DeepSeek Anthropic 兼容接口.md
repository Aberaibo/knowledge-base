---
title: DeepSeek Anthropic 兼容接口
date: 2026-05-07
source:
  - "[[Raws/deepseek-anthropic-api.md]]"
author:
  - 艾伯
tags: [active, promoted]
promoted_to:
  - "[[Permanent/DeepSeek API 平台]]"
---

# DeepSeek Anthropic 兼容接口

这份文献笔记整理 DeepSeek Anthropic 兼容接口的 base URL 和字段支持情况，重点不是有没有兼容，而是兼容到什么粒度。

## 关键事实

| 项目 | 状态 |
|------|------|
| Anthropic 兼容 base URL | `https://api.deepseek.com/anthropic` |
| `text` | 支持 |
| `thinking` | 支持 |
| `tool_use` / `tool_result` | 支持 |
| `image` / `document` / `search_result` | 不支持 |
| `cache_control` / `citations` / `is_error` | 忽略 |

## 关键摘录

| 类别 | 内容 |
|------|------|
| 接口方向 | DeepSeek 明确新增了 Anthropic API 兼容支持 |
| 支持重点 | 文本、思考、工具调用主链路可用 |
| 兼容边界 | 富内容和部分服务端工具类型没有跟齐 |

## 值得关注

- 这不是“换个 base URL 就完全等价”的兼容，而是字段级兼容。
- 对旧项目迁移来说，最危险的误判是只看 URL 一样，不看字段差异。
- 适合在平台页里做兼容边界总结，而不是重复写接入示例。

## 参考文献

- [[Raws/deepseek-anthropic-api.md]]
