---
AIGC:
    Label: "1"
    ContentProducer: 001191440300708461136T1XGW3
    ProduceID: 4205c06d69a9166a22c69ec543032024_76fce41ccad611f18e0e52540064ee0f
    ReservedCode1: SMBFoZ4k6pSzzyXkW+RzVgCXd7aMUWlYnNzOZ7B4SOVBtZE1i40ldfh0ucES4gGuWhTWQ3Vo6dPZ83tiAqkh9HAqzD4x5j27NjG7YNqT2kNcTxE35iFs3QR0PRkz17j6OhgVr76L2JE9Vgdzyz9VbU+ctCT8dvJnzbPugnsKkzfmjaQY6zOXnttXtNw=
    ContentPropagator: 001191440300708461136T1XGW3
    PropagateID: 4205c06d69a9166a22c69ec543032024_76fce41ccad611f18e0e52540064ee0f
    ReservedCode2: SMBFoZ4k6pSzzyXkW+RzVgCXd7aMUWlYnNzOZ7B4SOVBtZE1i40ldfh0ucES4gGuWhTWQ3Vo6dPZ83tiAqkh9HAqzD4x5j27NjG7YNqT2kNcTxE35iFs3QR0PRkz17j6OhgVr76L2JE9Vgdzyz9VbU+ctCT8dvJnzbPugnsKkzfmjaQY6zOXnttXtNw=
---

# models/ — 多模型接入

本项目所有模型均走 **OpenAI 兼容协议**，因此豆包、DeepSeek、Kimi、通义、OpenAI 的接入代码完全统一，仅切换 base_url 与 api_key。

## 接入清单

| 供应商 | Base URL | 备注 |
|---|---|---|
| 豆包（火山方舟） | `https://ark.cn-beijing.volces.com/api/v3` | 国内直连 |
| DeepSeek | `https://api.deepseek.com` | 国内直连 |
| Kimi | `https://api.moonshot.cn/v1` | 国内直连 |
| 通义千问 | `https://dashscope.aliyuncs.com/compatible-mode/v1` | 国内直连 |
| OpenAI | `https://api.openai.com/v1` | 需代理 / 中转 |

## 路由策略建议

- 代码生成 → DeepSeek（能力强、便宜）
- 长文本 / 文档 → Kimi
- 日常对话 / 办公 → 豆包
- 代码审查（第二视角）→ 豆包或 Kimi
- 主模型故障时自动降级到备用模型（互相兜底）

## 配置方式

参考 `config.example.yaml`；在 Dify 中则在「模型供应商」页面添加各供应商并填入 API Key 即可，无需改代码。
*（内容由AI生成，仅供参考）*
