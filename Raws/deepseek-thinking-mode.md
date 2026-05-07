DeepSeek 思考模式
来源: https://api-docs.deepseek.com/zh-cn/guides/thinking_mode
抓取时间: 2026-05-07

关键点：
- 思考模式开关（OpenAI 格式）：{"thinking": {"type": "enabled/disabled"}}
- 思考强度（OpenAI 格式）：{"reasoning_effort": "high/max"}
- Anthropic 格式：{"output_config": {"effort": "high/max"}}
- 默认 thinking 为 enabled
- 普通请求默认 effort=high；部分复杂 Agent 请求会自动用 max
- low/medium 会映射到 high，xhigh 会映射到 max

限制：
- thinking 模式下，temperature、top_p、presence_penalty、frequency_penalty 不生效
- reasoning_content 与 content 同级返回
- 无工具调用时，后续轮次可不回传 reasoning_content；有工具调用时，后续所有请求必须回传，否则 API 返回 400
