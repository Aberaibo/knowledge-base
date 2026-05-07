---
model: mimo-v2.5-pro
vendor: Xiaomi
series: MiMo-V2.5
released: 2026-04-23
---

# MiMo-V2.5-Pro

> 小米旗舰推理 Agent 模型，MiMo-V2-Pro 升级版。

## 核心规格

| 参数 | 值 |
|------|-----|
| 总参数 | 1T (1 万亿) |
| 激活参数 | 42B |
| contextWindow | 1,048,576 (1M) |
| maxTokens | 131,072 |
| 推理能力 | ✅ |
| 多模态 | ❌ (纯文本) |
| API 协议 | OpenAI 兼容 |

## 定价

| 上下文范围 | 输入 | 输入(缓存命中) | 输出 |
|-----------|------|---------------|------|
| 256K 以内 | $1.00/M | $0.20/M | $3.00/M |
| 1M 以内 | $2.00/M | $0.40/M | $6.00/M |

## 基准测试
- Claw-Eval 75.7（全球前三）
- Agent 性能媲美 Claude Opus 4.6
- API 成本约为竞品 20%

## 本地配置
- Provider: `xiaomi_tokenPlan`
- Model ID: `mimo-v2.5-pro`
- Alias: `mimop`
- Base URL: `https://token-plan-cn.xiaomimimo.com/v1`
- API 协议: `openai-completions`（OpenAI 口）/ `anthropic-messages`（Anthropic 口）

## 来源
- 官方文档: `https://platform.xiaomimimo.com/docs/updates/model`
- 调查时间: 2026-04-24

## 相关
- [[mimo-v2.5]] — 同系列全模态版本
- [[mimo-v2-pro]] — 前代
- [[mimo-token-plan]] — 定价详情
- [[MOC]]
