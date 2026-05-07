DeepSeek API 首页
来源: https://api-docs.deepseek.com/zh-cn/
抓取时间: 2026-05-07

DeepSeek API 使用与 OpenAI/Anthropic 兼容的 API 格式，通过修改配置，可以使用 OpenAI/Anthropic SDK 来访问 DeepSeek API。

关键参数：
- base_url (OpenAI): https://api.deepseek.com
- base_url (Anthropic): https://api.deepseek.com/anthropic
- model: deepseek-v4-flash / deepseek-v4-pro
- 兼容旧模型名: deepseek-chat / deepseek-reasoner（将于 2026-07-24 弃用）

说明：
- deepseek-chat 与 deepseek-reasoner 为兼容别名，分别对应 deepseek-v4-flash 的非思考与思考模式。
- DeepSeek API 已接入多种 Agent 工具，可用 OpenAI API 格式访问 chat/completions。
