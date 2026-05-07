---
model: mimo-v2.5
vendor: Xiaomi
series: MiMo-V2.5
released: 2026-04-23
---

# MiMo-V2.5

> 小米全模态感知 + Agent 模型，MiMo-V2-Omni 升级版。

## 核心规格

| 参数 | 值 |
|------|-----|
| contextWindow | 1,048,576 (1M) |
| maxTokens | 131,072 |
| 推理能力 | ✅ |
| 多模态 | ✅ (图像 / 视频 / 音频 / 文本) |
| API 协议 | OpenAI 兼容 / Anthropic |

## 定价

| 上下文范围 | 输入 | 输入(缓存命中) | 输出 |
|-----------|------|---------------|------|
| 256K 以内 | $0.40/M | $0.08/M | $2.00/M |
| 1M 以内 | $0.80/M | $0.16/M | $4.00/M |

## 能力
- 原生全模态感知：图像、视频、音频、文本统一处理
- 原生 Agent 执行能力：浏览、理解、推理、操作
- 日常任务表现比肩 [[mimo-v2.5-pro]]
- 性能与效率的 Pareto 前沿

## 本地配置
- Provider: `xiaomi_tokenPlan`
- Model ID: `mimo-v2.5`
- Alias: `mimo`
- Base URL: `https://token-plan-cn.xiaomimimo.com/v1`

## 配置变更记录
- 2026-04-24: contextWindow 从 262,144 (256K) 修正为 1,048,576 (1M)，maxTokens 从 32,000 修正为 131,072（来源：官方 API 文档）

## 来源
- 官方文档: `https://platform.xiaomimimo.com/docs/updates/model`
- 调查时间: 2026-04-24

## 相关
- [[mimo-v2.5-pro]] — 同系列推理旗舰
- [[mimo-v2-omni]] — 前代
- [[mimo-token-plan]] — 定价详情
- [[MOC]]
