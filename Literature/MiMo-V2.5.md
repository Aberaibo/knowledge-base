---
title: MiMo-V2.5
date: 2026-05-07
source:
  - "[[Raws/mimo-v2.5.md]]"
author:
  - 艾伯
tags: [active, promoted]
promoted_to:
  - "[[Permanent/MiMo-V2.5]]"
---

# MiMo-V2.5

这份文献笔记整理 MiMo-V2.5 的规格、定价、能力说明和配置变更记录。

## 关键事实

| 参数 | 值 |
|------|----|
| 上下文窗口 | 1,048,576（1M） |
| 最大输出 | 131,072 |
| 推理能力 | ✅ |
| 多模态 | ✅（图像 / 视频 / 音频 / 文本） |
| API 协议 | OpenAI 兼容 / Anthropic |
| Provider | `xiaomi_tokenPlan` |
| Alias | `mimo` |
| Base URL | `https://token-plan-cn.xiaomimimo.com/v1` |

## 关键摘录

| 类别 | 内容 |
|------|------|
| 能力 | 原生全模态感知 |
| 能力 | 原生 Agent 执行能力 |
| 相对定位 | 日常任务表现比肩 [[mimo-v2.5-pro]] |
| 配置修正 | 2026-04-24：`contextWindow` 从 256K 修正为 1M，`maxTokens` 从 32,000 修正为 131,072 |

## 值得关注

- 这页的高价值信息不只是规格，还有“配置曾被修正”的历史记录。
- 相比 Pro，这页更偏多模态和通用 Agent 场景。
- 适合晋升为规格页，但判断层应和定价页、平台页联动着看。

## 参考文献

- [[Raws/mimo-v2.5.md]]
