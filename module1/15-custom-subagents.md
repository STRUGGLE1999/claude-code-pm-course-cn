# 1.5: 自定义 Sub-Agents

- **完成时间：** 20-25 分钟
- **前置条件：** 完成 Module 1.4（Agents for Parallel Work）

**在 Claude Code 中开始本模块：** 运行 `/start-1-5` 启动交互式体验。

## 📖 概述

Module 1.5 教你如何创建自定义 sub-agents - 具有独特个性、专业知识和视觉标识的永久 AI 团队成员。与你在 Module 1.4 中学到的临时 agents 不同，自定义 sub-agents 是你可以随时调用的可复用专家。

**关键要点：** 自定义 sub-agents 将 Claude Code 从单个助手转变为完整的专业化团队。不需要每次告诉 Claude"表现得像个工程师"，而是构建一个具有个性、专业知识和视觉区分（颜色和 emoji！）的真正 Engineer sub-agent，你可以反复调用。

## 🎭 什么是自定义 Sub-Agents？

### 核心概念

自定义 sub-agents 是存储在项目 `.claude/agents/` 文件夹中的预配置 AI 人设。每个 sub-agent 拥有：

- **带 emoji 的名称**（在终端中视觉显示！）
- **颜色编码**（紫色、蓝色、绿色、红色等）
- **人设定义**（背景、专业知识、沟通风格）
- **专业化知识**（他们擅长什么）

可以把它们想象成永远可用且从不忘记上下文的永久团队成员。

### 自定义 Sub-Agents vs 临时 Agents

理解区别至关重要：

**临时 Agents（Module 1.4）：**

- 为特定任务即时创建
- 一次性工作的临时工
- 示例：创建 10 个 agents 来总结这些会议笔记
- 用例：相似任务的并行处理

**自定义 Sub-Agents（Module 1.5）：**

- 你反复调用的预构建人设
- 具有专业知识的永久团队成员
- 示例：👨‍💻 Engineer，审查这个技术规格
- 用例：你需要定期获得的专业化视角

**何时使用哪种：**

| 场景 | 使用这个 |
|---|---|
| 同时处理 20 份会议笔记 | 临时 agents（并行工作者） |
| 每周获取技术规格反馈 | 自定义 sub-agent（Engineer） |
| 一次研究 5 个竞争对手 | 临时 agents（一次性研究） |
| 定期将更新转换为高管摘要 | 自定义 sub-agent（Executive） |
| 并行分析 50 个用户访谈 | 临时 agents（批量处理） |
| 反复获取设计的 UX 视角 | 自定义 sub-agent（User Researcher） |

**关键区别：** 临时 agents 用于并行执行多项任务。自定义 sub-agents 用于获取你反复需要的专业化视角。

## 🗂️ 设置指南：访问 .claude/agents/ 文件夹

自定义 sub-agents 存放在隐藏的 `.claude/agents/` 文件夹中。

### 在 Mac 上

在 Finder 中按 **Cmd+Shift+.** 显示隐藏文件，然后导航到你的项目文件夹并打开 `.claude/agents/`

### 在 Windows 上

在文件资源管理器中，点击 **查看** 选项卡 → 勾选 **隐藏的项目**，然后导航到你的项目文件夹并打开 `.claude/agents/`

**注意：** Obsidian 无法显示隐藏文件夹。使用 Finder/Explorer 或 VS Code 编辑 `.claude/` 文件。

## 📄 Sub-Agent 文件结构

每个 sub-agent 是一个简单的 markdown 文件，包含三个部分：

### Sub-Agent 文件结构解析

```
# [Emoji] [名称]

## Color
[颜色名称]

## Persona
[背景、专业知识、沟通风格 - 2-3 段]

## Expertise
- [技能 1]
- [技能 2]
- [技能 3]
- [等等]
```

### 示例：Engineer Sub-Agent

```
# 👨‍💻 Engineer

## Color
purple

## Persona
You are an experienced software engineer with 10+ years at top tech companies
(Google, Meta, startups). You think deeply about technical architecture,
scalability, performance, and implementation details.

When analyzing features or specs, you provide:
- Technical feasibility assessment
- Implementation complexity estimates
- Potential challenges and edge cases
- Performance and scalability considerations
- Concrete, specific recommendations

Your communication style:
- Direct and pragmatic
- Focus on whats technically possible vs ideal
- Flag risks early
- Suggest alternatives when something wont work
- Balance perfectionism with shipping

You help PMs write better technical specs by spotting gaps, ambiguities,
and technical challenges they might miss.

## Expertise
- System architecture and design patterns
- API design and database schema
- Performance optimization and scalability
- Technical feasibility assessment
- Spotting edge cases and error states
- Implementation complexity estimation
```

**关键元素：**

- **Emoji & 名称：** 调用时出现在终端中
- **颜色：** 视觉区分（purple、blue、green、red、yellow、cyan、magenta）
- **人设：** 2-4 段描述背景、专业知识和沟通风格
- **专业知识：** 具体技能的项目符号列表

## 🛠️ 创建你的第一个 Sub-Agent

让我们从头创建一个 QA Tester sub-agent。

### 步骤 1：导航到 .claude/agents/ 文件夹

使用上述方法在 Finder/Explorer 中打开你项目的 `.claude/agents/` 文件夹。

### 步骤 2：创建新文件

创建一个名为：`qa-tester.md` 的新文件

**命名约定：**

- 使用小写
- 使用连字符代替空格
- 以 `.md` 结尾
- 示例：`data-analyst.md`、`tech-writer.md`、`growth-pm.md`

### 步骤 3：编写人设

复制此模板并自定义：

```
# 🔍 QA Tester

## Color
red

## Persona
You are a meticulous QA professional with 8+ years of experience testing enterprise
software at companies like Microsoft, Atlassian, and fast-growing startups. You think
comprehensively about edge cases, error states, and user error scenarios that others
miss.

When reviewing features or user stories, you provide:
- Comprehensive test case generation
- Edge case identification (the weird scenarios no one thinks about)
- Error state analysis (what happens when things go wrong)
- Accessibility and usability testing considerations
- Cross-browser and cross-platform compatibility concerns

Your communication style:
- Thorough and detail-oriented
- Constructively critical (you spot problems early)
- Organized (you categorize issues by severity)
- Practical (you suggest solutions, not just problems)
- User-advocate (you think like end users making mistakes)

You help PMs ship higher quality products by catching issues before they reach users.

## Expertise
- Test case generation and test plan creation
- Edge case and error state identification
- Acceptance criteria validation
- User error scenario analysis
- Regression testing strategy
- Accessibility testing (WCAG compliance)
- Cross-browser and device compatibility
- Load and performance testing considerations
```

### 步骤 4：保存并测试

保存文件，然后在 Claude Code 中测试：

```
# 启动 Claude Code
claude

# 调用你的新 sub-agent
🔍 QA Tester，审查 @user-stories.md 中的这些用户故事，识别
潜在的边缘情况和缺失的测试场景
```

你应该看到带有 QA emoji 的红色输出！

**提示：** 在 Claude Code 中随时运行 `/agents` 查看你配置的所有 sub-agents。

## 👥 预构建的 Sub-Agents

**👨‍💻 Engineer（紫色）**

- 技术可行性审查
- 实现复杂度估算
- 架构反馈

**💼 Executive（蓝色）**

- 将更新转换为高管摘要
- 利益相关者沟通
- 战略业务框架

**👤 User Researcher（绿色）**

- 分析用户访谈
- 识别痛点和模式
- 综合定性研究

## 💼 真实世界 PM 示例

**Engineer 用于技术规格：**

```
👨‍💻 Engineer，审查 @dashboard-prd.md 并识别技术挑战、
性能影响和实现复杂度
```

**Executive 用于利益相关者沟通：**

```
💼 Executive，将 @sprint-update.md 转换为 3 点高管摘要，
聚焦业务影响和指标
```

**User Researcher 用于访谈分析：**

```
👤 User Researcher，分析 /interviews 中的所有文件并识别
前 3 个痛点，附带支持性引用
```

## 🎯 其他 PM Sub-Agent 想法

- **📊 Data Analyst** - A/B 测试、指标、统计分析
- **✍️ Technical Writer** - 文档、帮助文章、发布说明
- **🎯 Marketing PM** - 定位、市场进入策略、发布规划
- **🎨 UX Designer** - 用户流程、设计反馈、无障碍审查
- **🧪 Growth PM** - 实验、引导流程、留存策略
- **🛡️ Security Expert** - GDPR、SOC2、合规、数据隐私
- **🎤 Customer Success** - 引导、采用、流失分析

## 💡 最佳实践

**人设设计：**

- 给出具体的背景和专业知识（不是通用的"你很有帮助"）
- 定义清晰的沟通风格
- 用 2-4 段让他们感觉像真实的人

**何时创建自定义 Sub-Agents：**

- 你每周或更频繁地需要相同的视角
- 用于你反复使用的专业化知识
- 构建一致的团队工作流程

## 🐛 故障排除

**看不到 .claude/ 文件夹？**

- Mac：在 Finder 中按 Cmd+Shift+.
- Windows：在文件资源管理器中启用"隐藏的项目"

**Sub-agent 没有响应？**

- 包含 emoji：`👨‍💻 Engineer，审查这个`
- 检查文件是否在 `.claude/agents/` 中并以 `.md` 结尾
- 重启 Claude（`exit` 然后 `claude`）

**调用多个 sub-agents：**

```
👨‍💻 Engineer，审查 @spec.md 的技术可行性。
然后 🔍 QA Tester，审查它的测试覆盖率。
```

## 📚 资源

- [Awesome Claude Code Sub-Agents](https://github.com/VoltAgent/awesome-claude-code-subagents) - 社区 sub-agent 模板集合
- [Sub-Agent Examples](https://github.com/wshobson/agents) - 真实世界的 agent 配置
- [SubAgents.cc](https://www.subagents.cc/) - Sub-agent 模板生成器

## 🚀 下一步是什么？

你现在知道如何创建自定义 sub-agents - 可以反复调用的具有专业化知识的永久团队成员。

**Module 1.6：** 学习 **Project Memory with CLAUDE.md** - 给 Claude 关于你的产品、团队和偏好的永久上下文。

交互式轨道：输入 `/start-1-6`

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。如果你对本模块或整个课程有任何反馈，请给我留言！我正在为 PM 构建者建立一个新闻通讯和社区，请查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=custom-subagents)。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[1.4: Agents](https://ccforpms.com/fundamentals/agents) | [1.6: Project Memory](https://ccforpms.com/fundamentals/project-memory)
