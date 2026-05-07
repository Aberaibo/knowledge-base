---
title: DeepSeek 思考模式
date: 2026-05-07
source:
  - "[[Raws/deepseek-thinking-mode.md]]"
author:
  - 艾伯
tags: [active, promoted]
promoted_to:
  - "[[Permanent/DeepSeek-V4-Flash]]"
  - "[[Permanent/DeepSeek-V4-Pro]]"
---

# DeepSeek 思考模式

这份文献笔记整理 DeepSeek thinking（思考）模式的开关、强度控制和上下文拼接规则，重点是 reasoning_content（思考链内容）在多轮对话里的处理方式。

## 关键事实

| 项目 | 内容 |
|------|------|
| 默认 thinking 开关 | enabled |
| effort 可选值 | `high` / `max` |
| `low` / `medium` | 映射到 `high` |
| `xhigh` | 映射到 `max` |
| 无工具调用时 | 后续轮次可不回传 `reasoning_content` |
| 有工具调用时 | 后续轮次必须回传 `reasoning_content`，否则 400 |
| 在 thinking 模式下不生效 | `temperature`、`top_p`、`presence_penalty`、`frequency_penalty` |

## 关键摘录

| 类别 | 内容 |
|------|------|
| OpenAI 格式开关 | `{"thinking": {"type": "enabled/disabled"}}` |
| OpenAI 格式强度 | `reasoning_effort: "high/max"` |
| Anthropic 格式强度 | `output_config: {"effort": "high/max"}` |

## 值得关注

- 真正容易踩坑的不是“怎么开 thinking”，而是“工具调用后要不要回传 reasoning_content”。
- 文档明确把 400 错误与 reasoning_content 回传失败绑在一起，这是高价值接入细节。
- 这类规则很适合被提炼进 Permanent 规格页，而不是埋在样例代码里。

## 参考文献

- [[Raws/deepseek-thinking-mode.md]]
