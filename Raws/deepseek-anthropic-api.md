DeepSeek Anthropic 兼容接口
来源: https://api-docs.deepseek.com/zh-cn/guides/anthropic_api
抓取时间: 2026-05-07

关键点：
- DeepSeek 新增对 Anthropic API 格式的支持
- base_url: https://api.deepseek.com/anthropic
- 支持 text、thinking、tool_use、tool_result 等主要字段
- image/document/search_result/redacted_thinking/server_tool_use/web_search_tool_result/code_execution_tool_result/mcp 相关类型未支持或忽略
- cache_control、citations、is_error 等若干字段被忽略
