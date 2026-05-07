DeepSeek Tool Calls
来源: https://api-docs.deepseek.com/zh-cn/guides/tool_calls
抓取时间: 2026-05-07

关键点：
- DeepSeek 支持 Tool Calls，可让模型调用外部工具
- 思考模式下也支持 Tool Calls（从 DeepSeek-V3.2 开始）
- strict 模式（Beta）要求：
  - base_url 使用 https://api.deepseek.com/beta
  - tools 里的 function 需要设置 strict: true
  - 服务端会校验 JSON Schema
- strict 模式支持的 JSON Schema 类型包括 object/string/number/integer/boolean/array/enum/anyOf/$ref/$def
- object 类型要求所有属性都在 required 中，且 additionalProperties 为 false
