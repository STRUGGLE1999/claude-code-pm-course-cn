# 3.2.2: 策略与架构视觉

- **完成时间：** 20分钟
- **前置条件：** 已完成用户与产品视觉（模块 3.2.1）

**在 Claude Code 中开始本模块：** 运行 `/start-3-2-2` 开始交互式体验。

## 概述

模块 3.2.2 教你为不同利益相关者受众创建策略和架构视觉素材。CTO 想了解技术架构。CEO 想看优先级。董事会想看路线图。不同受众，不同视觉。

**关键要点：** 策略视觉将复杂想法转化为即时清晰。正确的图表可以在几秒钟内完成 10 分钟解释无法做到的事情。

## 场景

你的 TaskFlow Mobile 演示成功了。现在你有后续会议：

1. **CTO 会议** - "它如何与我们现有系统集成？"
2. **CEO 会议** - "我们先构建什么，为什么？"
3. **董事会会议** - "3 个季度的路线图是什么？"

每种需要不同类型的视觉素材。

## 系统架构图

### 它们是什么

系统架构图展示组件如何连接——服务、数据库、API、外部集成。它们回答"技术系统如何工作？"

### 何时使用

- 与工程团队的技术深入讨论
- CTO/工程副总裁演示
- 安全和合规审查
- 集成规划讨论

### 如何生成

**基础 prompt：**

```
Create a system architecture diagram showing [system].
Components: [list components]. Show data flow between them.
Clean technical style, suitable for [audience]. 16:9 aspect ratio.
```

**示例 - TaskFlow Mobile：**

```
Create a system architecture diagram for TaskFlow Mobile.

Components:
- TaskFlow Mobile app (the new thing)
- TaskFlow Backend API (existing)
- PostgreSQL database
- Redis cache
- Firebase (push notifications)
- Mixpanel (analytics)

Show data flow arrows between components.
Clean technical style suitable for CTO review. 16:9 aspect ratio.
```

### 关键元素

| 元素 | 用途 |
|---|---|
| **方框/节点** | 代表服务、数据库、应用 |
| **箭头** | 展示数据流和关系 |
| **标签** | 识别每个组件 |
| **分组** | 聚类相关组件 |
| **颜色** | 区分类型（新增 vs 现有，内部 vs 外部） |

### 风格选项

| 风格 | 最适合 |
|---|---|
| **简洁/极简** | 高管演示 |
| **技术/详细** | 工程评审 |
| **彩色/品牌化** | 外部文档 |
| **手绘** | 白板/工作坊感 |

### 专业提示

- **突出新内容：** 使用颜色或边框区分新组件
- **显示边界：** 分组内部 vs 外部，或按团队归属
- **保持可读：** 每张图最多 5-10 个组件；需要时拆分
- **添加图例：** 如果有意义地使用颜色或形状

## 优先级矩阵

### 它们是什么

2x2 矩阵在两个维度上绘制项目——通常是影响力 vs 工作量，或价值 vs 复杂度。它们可视化优先级决策。

### 何时使用

- 功能优先级讨论
- 高管策略会议
- 规划会议
- 利益相关者对齐

### 经典 2x2

最常见：**影响力 vs 工作量**

```
High Impact │ Major │ Quick
            │ Projects │ Wins
────────────┼─────────────┼──────────
Low Impact  │ Avoid │ Fill-ins
            │       │
            └─────────────┴──────────
            High Effort   Low Effort
```

| 象限 | 含义 | 行动 |
|---|---|---|
| **Quick Wins** | 高影响力，低工作量 | 优先做 |
| **Major Projects** | 高影响力，高工作量 | 仔细规划 |
| **Fill-ins** | 低影响力，低工作量 | 有时间时做 |
| **Avoid** | 低影响力，高工作量 | 不要做 |

### 如何生成

**基础 prompt：**

```
Create a 2x2 prioritization matrix.
X-axis: [dimension 1] (Low → High)
Y-axis: [dimension 2] (Low → High)

Quadrant labels: [list quadrants]

Plot these items:
- [Item 1]: [quadrant]
- [Item 2]: [quadrant]
...

Clean corporate style for executive presentation. 16:9 or 1:1.
```

**示例 - TaskFlow Mobile 功能：**

```
Create a 2x2 prioritization matrix for TaskFlow Mobile features.

X-axis: Effort (Low → High)
Y-axis: Impact (Low → High)

Quadrants: Quick Wins (top-right), Major Projects (top-left),
Fill-ins (bottom-right), Avoid (bottom-left)

Plot these features:
Quick Wins:
- Push notifications for task updates
- Offline task viewing

Major Projects:
- Real-time sync across devices
- Team chat integration

Fill-ins:
- Custom themes
- Widget support

Avoid:
- Voice command support
- AR task visualization

Clean corporate style for CEO presentation. Square format.
```

### 其他矩阵类型

| 矩阵 | 维度 | 使用场景 |
|---|---|---|
| **艾森豪威尔** | 紧急 × 重要 | 任务管理 |
| **风险** | 概率 × 影响 | 风险评估 |
| **RICE** | Reach × Impact × Confidence × Effort | 功能评分 |
| **BCG** | 市场增长 × 市场份额 | 投资组合策略 |

### 专业提示

- **明确象限标签：** 不要假设 Gemini 知道你的术语
- **清晰绘制项目：** 列出每个项目属于哪里
- **保持平衡：** 每个象限 3-5 个项目看起来最好
- **使用你的风格库：** 保存你喜欢的矩阵风格以便复用

## 产品路线图

### 它们是什么

产品路线图展示随时间规划的工作——通常按季度或月份。它们回答"计划是什么，什么时候？"

### 何时使用

- 董事会演示
- 年度规划审查
- 团队对齐
- 外部利益相关者更新

### 路线图结构

| 结构 | 最适合 |
|---|---|
| **时间线** | 清晰的时间顺序视图 |
| **泳道** | 多个并行轨道 |
| **现在/下一步/以后** | 灵活，无日期 |
| **里程碑** | 关键交付物焦点 |

### 如何生成

**基础 prompt：**

```
Create a product roadmap for [product].

Timeline: [time period]

[Period 1]: [Theme]
- [Item 1]
- [Item 2]

[Period 2]: [Theme]
- [Item 1]
- [Item 2]

...

Professional style for [audience]. 16:9 aspect ratio.
```

**示例 - TaskFlow Mobile：**

```
Create a product roadmap for TaskFlow Mobile over 3 quarters.

Q1 - MVP Launch:
- Core task management
- Push notifications
- Offline viewing

Q2 - Team Features:
- Real-time sync
- Team chat integration
- Shared task lists

Q3 - Enterprise:
- Admin controls
- SSO integration
- Advanced analytics

Professional style suitable for board presentation.
Show clear progression from MVP to enterprise-ready.
16:9 aspect ratio.
```

### 关键元素

| 元素 | 用途 |
|---|---|
| **时间标记** | 季度、月份或冲刺 |
| **主题** | 为每个阶段命名 |
| **功能** | 具体交付物 |
| **里程碑** | 关键日期或成就 |
| **进度** | 当前状态（可选） |

### 专业提示

- **讲述故事：** 每个阶段应该逻辑上构建在前一个阶段上
- **使用主题：** "MVP" → "增长" → "规模化" 比功能列表更清晰
- **不要过度详细：** 路线图是战略性的，不是冲刺计划
- **匹配受众：** 董事会看主题；工程看功能

## 针对特定利益相关者的技巧

### 对于 CTO/工程团队

- **关注：** 集成点、数据流、技术依赖
- **包含：** 现有系统、API、数据库
- **风格：** 技术性但可读；不过于复杂
- **级别：** 架构层面，不是实现细节

### 对于 CEO/领导层

- **关注：** 战略决策、优先级理由
- **包含：** 权衡、你不会做的事情
- **风格：** 简洁、极简、高层
- **级别：** 业务影响，不是技术细节

### 对于董事会

- **关注：** 时间线、里程碑、战略方向
- **包含：** 阶段、关键交付物、业务成果
- **风格：** 专业、精美、自信
- **级别：** 季度级别，不是周级别

## 使用你的风格库

策略视觉极大地受益于一致的风格。

**保存你的常用风格：**

- "Executive Architecture" - 简洁的技术图表
- "Corporate Matrix" - 专业的 2x2
- "Board Roadmap" - 精美的时间线视觉

**然后复用：**

```
Generate system architecture using style #34
Generate prioritization matrix using style #5
Generate roadmap using style #88
```

利益相关者材料的一致性看起来很专业。

## 示例：完整的利益相关者包

### CTO 演示包

**素材：** 系统架构图
**信息：** "这是它如何与我们现有基础设施集成"

### CEO 演示包

**素材：** 2x2 优先级矩阵
**信息：** "这是我们优先构建什么以及为什么"

### 董事会演示包

**素材：** 3 季度路线图
**信息：** "这是从 MVP 到企业的路径"

**总时间：** 所有三种素材 15-20 分钟。

## 最佳实践

### 应该做的：

- **风格匹配受众** - 工程师用技术风格，高管用简洁风格
- **讲述清晰的故事** - 每个视觉应该有一个主要信息
- **使用一致的风格** - 利用你的风格库
- **保持简单** - 复杂性扼杀理解
- **迭代** - 初稿很少是最终版本

### 不应该做的：

- **不要过度复杂** - 每个视觉最多 5-10 个元素
- **不要混合隐喻** - 选择一种视觉方法并坚持
- **不要跳过标签** - 一切都应该清晰识别
- **不要随意使用行话** - 匹配受众的词汇

## 故障排除

### 架构图太杂乱

- 只保留核心组件
- 拆分为多张图（前端、后端、集成）
- 请求 "high-level overview, not detailed architecture"

### 矩阵项目重叠

- 减少每个象限的项目（3-5 个最理想）
- 请求 "items clearly positioned, not overlapping"
- 使用更大的格式（16:9 而不是 1:1）

### 路线图不显示进展

- 明确描述叙事："MVP → Growth → Scale"
- 使用视觉进展（从左到右，从小到大）
- 请求 "show clear evolution from phase to phase"

## 下一步是什么？

你已经为内部利益相关者创建了视觉素材。现在是时候面向外部受众了。

**模块 3.2.3** 涵盖营销和发布素材——应用商店图形、社交广告和发布公告。

交互式学习路径：输入 `/start-3-2-3`

## 资源

- [SlideModel](https://slidemodel.com/) - 框架和图表模板，截图并克隆风格
- [Miro Architecture Diagrams](https://miro.com/diagramming/architecture-diagram-examples/) - 示例和模板
- [Lucidchart Architecture Guide](https://www.lucidchart.com/blog/how-to-draw-architectural-diagrams) - 5 种架构图类型
- [EdrawMax Templates](https://www.edrawmax.com/templates/tag/system-architecture/) - 免费系统架构模板

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=nano-banana-strategy) 获取更多 PM 构建者内容。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[3.2.1: 用户与产品视觉](https://ccforpms.com/nano-banana/users-product-visuals) | [3.2.3: 营销与发布资产](https://ccforpms.com/nano-banana/marketing-launch-assets)
