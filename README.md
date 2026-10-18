# AI Agent 多智能体项目

多模型 + 多 Agent 协作项目骨架，国内网络直连可用（豆包 / DeepSeek / Kimi / 通义等），也可按需接入 OpenAI（需代理）。

## 目录结构

```
ai-agent-project/
├── agents/        # 各智能体定义（角色、职责、提示词）
├── models/        # 多模型接入配置（OpenAI 兼容协议）
├── workflows/     # 多 Agent 工作流编排说明
├── .env.example   # API Key 环境变量模板
└── README.md
```

## 快速开始

1. 复制 `.env.example` 为 `.env`，填入各家 API Key
2. 模型接入：`models/` 下按 OpenAI 兼容协议配置（豆包、DeepSeek 均兼容）
3. 智能体编排：推荐用 Dify（开源，可自部署）可视化编排多 Agent，或直接用 LangChain 代码编排

## 部署建议

- 入门最快：Dify 自部署（官方一键脚本 `curl -fsSL https://dify.ai/install.sh | bash`，需 Docker）
- 进阶玩法：LangChain + 本仓库 `models/` 路由配置，代码级多 Agent 协作
