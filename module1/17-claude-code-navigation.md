# 1.7: Claude Code 导航

- **完成时间：** 15-20 分钟
- **前置条件：** 完成 Modules 1.1-1.6

**在 Claude Code 中开始本模块：** 运行 `/start-1-7` 启动交互式体验。

## 📖 概述

Module 1.7 涵盖最后的导航要点：输入模式、分析深度控制和工作流程加速。这些技能区分普通用户和高级用户。

**你将学到什么：**

1. **输入模式** - Edit、auto-accept 和 plan mode

2. **Think 关键词** - 控制分析深度（think/think harder/ultrathink）

3. **—dangerously-skip-permissions** - 关键的工作流程加速器

**关键要点：** 掌握何时使用每种模式，按需调整分析深度，并消除工作流程中的摩擦。

## 🎛️ 三种输入模式

Claude Code 有三种控制工作流程执行的输入模式：

| 模式 | 行为 | 最适合 | 切换方法 |
|---|---|---|---|
| **Edit**（默认） | 显示差异，等待批准 | 关键文件、学习、安全 | 按 Shift+Tab |
| **Auto-Accept** | 立即应用更改 | 简单任务、可信操作 | 按 Shift+Tab |
| **Plan** | 首先创建带待办事项的结构化计划 | 多步骤工作流程、复杂研究 | 按 Shift+Tab |

**切换：** 随时按 **Shift+Tab** 循环切换模式。

### Edit Mode（默认）

在应用之前显示每个文件更改。你审查并批准每个更改。

**用于：**

- 处理关键文件
- 学习 Claude 如何处理任务
- 需要控制和审查

### Auto-Accept Mode

自动应用更改而不询问。快速且自主。

**用于：**

- 任务直接明了且清晰
- 信任 Claude 正确执行
- 想要速度而非审查

### Plan Mode

在执行之前创建带自动生成待办列表的结构化计划。预先查看策略。

**用于：**

- 复杂、多步骤工作流程（3+ 不同步骤）
- 想要在执行前查看策略
- 研究 → 综合 → 交付物工作流程
- 多个 agents 需要协调

**示例待办列表：**

```
☐ 研究 TaskFlow 的主要竞争对手
☐ 启动并行 agents 分析 AI 功能
☐ 将发现综合为竞争分析
☐ 创建响应策略文档
```

当 Claude 工作时：

```
✓ 研究 TaskFlow 的主要竞争对手
→ 启动并行 agents 分析 AI 功能
☐ 将发现综合为竞争分析
☐ 创建响应策略文档
```

## 🎯 模式选择指南

| 任务 | 推荐模式 | 原因 |
|---|---|---|
| 研究 5 个竞争对手并创建策略 | Plan Mode | 复杂、多步骤、受益于可见性 |
| 添加深色模式切换 | Auto-Accept/Edit | 简单、单步任务 |
| 修复 README 中的拼写错误 | Auto-Accept/Edit | 简单、低风险 |
| 从粗略笔记创建 PRD | Plan Mode | 多步骤：研究 → 大纲 → 草稿 |
| 分析 CSV 文件 | Auto-Accept | 直接的分析 |
| 多来源研究综合 | Plan Mode | 复杂：agents → 综合 |

**快速决策树：**

1. 复杂多步骤工作流程？ → **Plan Mode**

2. 直接明了且低风险？ → **Auto-Accept**

3. 否则 → **Edit Mode**（最安全）

## 💡 Think 控制关键词

在 Claude 响应之前调整分析深度：

| 关键词 | 深度 | 何时使用 |
|---|---|---|
| `think about X` | 正常 | 大多数任务 |
| `think harder about X` | 更深 | 复杂决策 |
| `ultrathink about X` | 最大 | 非常困难的问题（显示为彩虹！） |

**示例：**

配合 plan mode：

```
Think harder about 竞争威胁，然后研究竞争对手的 AI 功能
并创建响应策略
```

配合任何模式：

```
Ultrathink about 我们应该自建还是购买这个功能
```

**专业提示：** Think 关键词在所有输入模式中都有效，在 plan mode 中对复杂策略工作特别有用。

## ⚡ Dangerously Skip Permissions

### 标志

```
claude --dangerously-skip-permissions
```

**它的作用：** 跳过所有权限提示。Claude 执行命令无需批准。

**转变：**

| 没有标志 | 有标志 |
|---|---|
| 我可以写入 user-story-1.md 吗？ → 是
我可以写入 user-story-2.md 吗？ → 是
我可以写入 user-story-3.md 吗？ → 是
[对每个文件重复...] | [立即创建所有 5 个文件]
完成！ |

### 为什么值得

**权衡：**

- **风险：** 没有安全网，命令立即执行
- **回报：** 纯粹的流程状态，快 10 倍，真正的工作流程速度

### Carl 的强烈建议

**使用它** 一旦你完成了 Level 1 并信任 Claude Code。速度提升是值得的。

**创建 shell 别名：**

```
alias cc="claude --dangerously-skip-permissions"
```

然后只需输入 `cc` 以快速模式启动 Claude Code。

**何时使用：**

- 完成了 Level 1
- 信任 Claude Code
- 在安全环境中工作
- 想要专业速度

**何时避免：**

- 生产代码
- 不确定 Claude 会做什么
- 学习新项目

## 🛑 停止执行

**随时按 Esc** 停止 Claude 执行。

**发生什么：**

- 执行立即停止
- 目前创建的文件保留
- 可以审查并决定下一步

**专业提示：** 在 plan mode 中，一旦你看到了价值就按 Esc，然后在准备好时审查文件。

## 💡 最佳实践

**应该做：**

- 对多步骤工作流程使用 plan mode（3+ 步骤）
- 根据任务复杂性切换模式
- 对复杂决策使用 think 关键词进行更深入的分析

**不应该做：**

- 对简单任务使用 plan mode（过度）
- 一直停留在一种模式（要灵活）
- 忘记 Esc 可以停止执行

**工作流程发展：**

- **第 1 周：** 所有事情都用 Edit mode（学习 Claude 如何工作）
- **第 2 周：** 简单任务用 Auto-accept
- **第 3 周：** 复杂工作流程用 Plan mode
- **第 4 周：** 根据任务自然切换模式

## ❓ 常见问题

**我应该何时使用 plan mode vs 直接让 Claude 做？**

当任务有 3+ 个不同步骤或涉及研究 → 综合 → 交付物时使用 plan mode。对于简单、明显的任务跳过。

**我可以在 Claude 执行之前编辑计划吗？**

可以！要求调整："添加一个步骤来..."或"删除 X 部分"都很有效。

**我应该总是使用 —dangerously-skip-permissions 吗？**

当你信任 Claude 且速度重要时使用。避免用于生产代码或学习新项目时。

**Think 关键词在所有模式中都有效吗？**

是的！它们在 edit、auto-accept 和 plan modes 中调整分析深度。

## 🎉 下一步是什么？

### Level 1 完成

**恭喜！** 你已经掌握了 Level 1：基础的全部内容。

**获得的技能：**

- ✅ 文件操作（读、写、编辑、引用）
- ✅ 使用可视化工作空间实时可视化
- ✅ PM 文档处理
- ✅ 用于克隆自己的并行 agents
- ✅ 专业化 sub-agent 团队
- ✅ 永久项目记忆（CLAUDE.md）
- ✅ 工作流程模式选择
- ✅ 分析深度控制
- ✅ 无摩擦流程状态工作

**节省时间：每周 10-15 小时**

### Level 2：真正的 PM 工作流程

准备好每周节省 20+ 小时了吗？Level 2 教授日常 PM 工作流程。

**Module 2.1: Write a PRD**

- 将粗略想法转化为完整 PRD
- 研究 agents 和苏格拉底式精炼

**Module 2.2: Analyze Product Data & Build Dashboards**

- 处理大型数据集（CSV、调查）
- 多来源研究综合

**Module 2.3: Build Product Strategy & Roadmap**

- 大规模竞争研究
- 战略综合和路线图创建

**开始 Level 2：**

```
/start-2-1
```

**庆祝这个成就！** 你已经建立了 Claude Code 精通的完整基础。🎓

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。如果你对本模块或整个课程有任何反馈，请给我留言！我正在为 PM 构建者建立一个新闻通讯和社区，请查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=claude-code-navigation)。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[1.6: Project Memory](https://ccforpms.com/fundamentals/project-memory) | [2.1: Write a PRD](https://ccforpms.com/advanced/write-prd)
