---
AIGC:
    Label: "1"
    ContentProducer: 001191440300708461136T1XGW3
    ProduceID: 4205c06d69a9166a22c69ec543032024_77bdffffcad611f18e0e52540064ee0f
    ReservedCode1: Q6xXh95nsoivjqbjAaJ12R1X4Gn6EpMKxLezcoglyLzOofF72tlJKyTbtzsmi7/QQPBRVvhM0PgIuRupFtdfRudaKYi8riNTOjHN4PFS8XsLB1427HzYMjEZd5jcqxxhIKSpQ1EKB9mO/r9QY5TrF2Z7Uokp4CWNCOoFJDR4n5QBycUFJpILVG/dWQc=
    ContentPropagator: 001191440300708461136T1XGW3
    PropagateID: 4205c06d69a9166a22c69ec543032024_77bdffffcad611f18e0e52540064ee0f
    ReservedCode2: Q6xXh95nsoivjqbjAaJ12R1X4Gn6EpMKxLezcoglyLzOofF72tlJKyTbtzsmi7/QQPBRVvhM0PgIuRupFtdfRudaKYi8riNTOjHN4PFS8XsLB1427HzYMjEZd5jcqxxhIKSpQ1EKB9mO/r9QY5TrF2Z7Uokp4CWNCOoFJDR4n5QBycUFJpILVG/dWQc=
---

# workflows/ — 多 Agent 工作流

## 示例：代码开发流水线

```
用户需求
  └─> [Coder Agent] 生成代码（DeepSeek）
        └─> [Reviewer Agent] 审查代码（豆包，独立视角）
              ├─ 通过 → 交付
              └─ 有问题 → 打回 Coder 修改（最多 3 轮）
                    └─> 再次审查
```

## 编排工具

- **Dify（推荐入门）**：图形化拖拽编排上述流程，自带多模型管理，国内可直连部署
  - 部署：`curl -fsSL https://dify.ai/install.sh | bash`（需先安装 Docker）
- **LangChain（进阶）**：代码级编排，支持复杂多 Agent 协作、工具调用

## 设计原则

1. 每个 Agent 职责单一，独立定义在 `agents/`
2. 模型按 `models/` 路由选择，故障自动降级
3. 关键环节至少两个不同模型交叉验证，降低单一模型误差
*（内容由AI生成，仅供参考）*
