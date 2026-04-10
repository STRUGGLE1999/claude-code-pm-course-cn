# 2.1: 编写 PRD

- **完成时间：** 45-60 分钟

- **前置要求：** 模块 1.4 (Agents)，模块 1.5 (Custom Sub-Agents)

**在 Claude Code 中开始本模块：** 运行 `/start-2-1` 启动交互式体验。

## 概述

模块 2.1 教你如何将 AI 作为思考伙伴，更快地编写更好的 PRD。你将通过 @-mentions 整合模板、公司背景和用户研究，并行生成多种战略方案，并在与团队分享之前获得多视角反馈。

**核心要点：** AI 的价值在于帮助你更好地思考，而不是替你完成所有思考。最好的 PRD 结合了人类的判断力与 AI 处理完整上下文、生成选项和提供多元视角的能力。

## 传统方法 vs AI 协作方法

| 传统方法 | AI 协作方法 |
|---|---|
| 打开空白文档 | 通过 @-mentions 提供完整上下文 |
| 独自编写 PRD | 使用苏格拉底式提问来厘清思路 |
| 分享给团队 | 生成多种战略方案 |
| 获得反馈 | 先从 sub-agents 获取反馈 |
| 修改 | 在任何人看到之前先完善 |
| 重复 | 分享更强的初稿 |

**区别在于：** 你永远不是从零开始，而且在第一次评审之前就已经解决了潜在问题。

## 四大核心技巧

### 1. 通过 @-Mentions 提供完整上下文

一次性向 Claude 提供所有相关信息。

**可以 @-mention 的内容：**

- **公司背景** - 产品策略、客户洞察、业务指标

- **用户研究** - 访谈记录、调研结果、痛点

- **模板** - 你偏好的 PRD 结构

- **方法论** - 如苏格拉底式提问等框架

- **相关文档** - 之前的 PRD、竞品分析、路线图

**示例：**

```
Help me write a PRD for [feature] using:
@company-context.md - product and customer context
@user-research/pain-points.md - insights from 20 interviews
@prd-template.md - our standard PRD structure
@methods/socratic-questioning.md - framework for clear thinking
```

### 2. 苏格拉底式提问厘清思路

在写作之前，使用结构化提问来厘清模糊的想法。

**关键问题类别：**

| 类别 | 问题 |
|---|---|
| **问题清晰度** | 这解决了什么具体的用户痛点？
谁最强烈地感受到这个问题？
不解决这个问题的代价是什么？ |
| **方案验证** | 为什么这是正确的解决方案？
你考虑过哪些替代方案？
最简单的版本是什么？ |
| **成功标准** | 我们如何衡量成功？
什么表明失败？
我们在推动什么指标，提升多少？ |
| **约束条件** | 存在哪些技术风险？
我们不做什么？
如果时间减半，我们会砍掉什么？ |
| **战略契合** | 为什么现在就要构建这个？
这如何契合我们更广泛的战略？
这如何影响竞争地位？ |

**专业提示：** 选择 3-5 个最相关的问题。质量胜于数量。

### 3. 生成多种战略方案

让 Claude 针对同一功能生成 3 种不同的战略方案。比较、选择最好的，或结合各方案要素。

**示例：AI 语音聊天 + 待办事项列表功能**

| 方案 | 主要界面 | 使用场景 | 成功指标 |
|---|---|---|---|
| **聊天优先** | AI 对话 | 移动时快速记录 | 通过语音创建任务的百分比 |
| **列表优先** | 传统待办列表 | 对现有工作流程的免手操作更新 | 语音功能的 DAU |
| **平衡型** | 两者并重 | 根据场景灵活切换 | 用户满意度 + 采用率 |

**使用 agents 并行生成：**

```
Spin up 3 agents to generate 3 PRD drafts in parallel:
- Agent 1: Chat-first approach
- Agent 2: List-first approach
- Agent 3: Balanced approach
```

这展示了并行处理在 PM 工作中的威力。

### 4. 通过 Sub-Agents 获取多视角反馈

在与真正的团队分享之前，获得多元反馈。

**三个关键视角：**

| Sub-Agent | 关注领域 |
|---|---|
| **👨‍💻 工程师** | 技术可行性、实现复杂度、风险、依赖关系、时间估算 |
| **💼 高管** | 业务价值、战略契合、资源合理性、竞争定位、ROI |
| **👤 用户研究员** | 用户需求匹配、可用性问题、边缘案例、采用障碍、指标有效性 |

**示例：**

```
Get reviews from all three sub-agents and consolidate feedback:
- @.claude/agents/engineer.md - technical review
- @.claude/agents/executive.md - business review
- @.claude/agents/user-researcher.md - UX review
```

## 真实案例

**上下文设置：**

```
I'm writing a PRD for smart meeting summaries. Help me think through this using:
@company-context.md
@user-research/calendar-pain-points.md
@prd-template.md
@methods/socratic-questioning.md
```

**厘清思路：**

```
Ask me 5 key questions about this feature using the Socratic framework:
- Problem clarity
- Why this solution
- Success metrics
- Technical constraints
- Strategic timing
```

**生成方案：**

```
Generate 3 strategic approaches:
1. Calendar-native (summaries appear in calendar app)
2. Email-first (summaries delivered via email)
3. Standalone app (dedicated meeting hub)

For each: problem framing, solution, success metrics
```

**获取反馈：**

```
👨‍💻 Engineer, review @smart-summaries-prd.md for technical feasibility.
Then 💼 Executive, review for business value and strategic fit.
Then 👤 User Researcher, review for user needs alignment.
```

## 最佳实践

**应该做：**

- 从完整上下文开始（@-mention 公司文档、研究、模板）

- 使用苏格拉底式提问来厘清模糊的想法

- 生成 2-3 种战略方案，不要只采用第一个想法

- 在与真实团队分享之前先获取 sub-agent 反馈

- 自己主导流程 - AI 提供选项，你来决策

**不应该做：**

- 让 AI 替你写（你们是协作，不是外包）

- 跳过思考环节（问题存在的目的是磨砺你的判断力）

- 接受初稿（始终生成替代方案进行比较）

- 忽略 sub-agent 反馈（经常能发现重要问题）

- 孤立工作（使用完整上下文）

**专业提示：**

| 提示 | 好处 |
|---|---|
| 创建方法论库 | 可复用的框架（Socratic、JTBD、RICE）适用于任何 PRD |
| 维护模板库 | 针对功能、重新设计、实验的不同模板 |
| 保存优秀的 agent prompts | 复用能提供有价值反馈的角色设定 |
| 使用检查点 | 保存每个版本（v1、v2、v3）以参考替代方案 |
| 记录推理过程 | 记录为什么选择这个方案而非其他 |

## 问题排查

**AI 生成的 PRD 感觉很泛泛**

原因：上下文不足或 AI 自主性过高

解决方法：

- 提供更具体的公司上下文（@-mention 详细文档）

- 使用苏格拉底式提问注入你的思考

- 说"帮我思考"而不是"帮我写一个 PRD"

- 添加研究中的具体例子和用户原话

**Sub-agent 反馈浮于表面**

原因：Agent 角色不够具体，或 PRD 缺乏深度

解决方法：

- 增强 sub-agent 角色，加入具体关注点（API 速率限制、可扩展性）

- 为 agents 提供更多上下文（@-mention 技术/策略文档）

- 要求特定类型的反馈："聚焦技术风险"

- 确保 PRD 草稿有足够细节可供评审

**流程耗时太长**

原因：步骤太多，或没有使用并行化

解决方法：

- 不是每次都需要所有 3 种方案 - 一种可能就够了

- 使用 agents 并行生成草稿（而非顺序）

- 如果你已经很清楚，可以跳过苏格拉底式提问

- 不是每个 PRD 都需要 sub-agent 评审 - 用于高风险功能

**难以追踪版本**

原因：文件命名或版本管理不当

解决方法：

- 清晰命名：`feature-prd-v1.md`、`feature-prd-v2-chat-first.md`、`feature-prd-final.md`

- 添加日期：`feature-prd-2025-01-15.md`

- 在 PRD 中保留变更日志部分

- 使用 git commits 追踪演进

- 将旧版本归档到 `drafts/` 文件夹

## 下一步

你现在了解了如何与 AI 协作编写更好的 PRD：通过 @-mentions 提供完整上下文，使用苏格拉底式提问厘清思路，用 agents 生成多种战略方案，并通过 sub-agents 获取多视角反馈。

**模块 2.2：** 学习 **数据驱动决策** - 使用数据驱动产品决策，从发现漏斗问题到估算功能影响再到分析 A/B 测试。

交互式学习：输入 `/start-2-2`

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。如果你对本模块或整个课程有任何反馈，请联系我！我正在为 PM 创造者建立一个通讯和社区，欢迎查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=write-prd)。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[1.7: Claude Code Navigation](https://ccforpms.com/fundamentals/claude-code-navigation) [2.2: Analyze Data](https://ccforpms.com/advanced/analyze-data)
