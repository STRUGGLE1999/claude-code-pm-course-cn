# 1.3: 你的第一个 PM 任务

- **完成时间：** 30 分钟
- **前置条件：** 完成 Modules 1.1 和 1.2

**在 Claude Code 中开始本模块：** 运行 `/start-1-3` 启动交互式体验。

## 概述

Module 1.3 教你使用 Claude Code 完成真正的 PM 工作：处理会议笔记、综合研究、分析视觉内容，以及创建可复用模板。这是理论变实践的地方。

**关键要点：** Claude Code 是一个文件感知、视觉能力的助手，每周可以为你节省 2-3 小时的常规 PM 文档工作。

## 核心能力

本模块涵盖五项基本技能：

| 能力 | 你将学到什么 |
|---|---|
| **文件读写** | 使用 `@` 引用文件、阅读多个文档、创建/编辑文件 |
| **内容分析** | 将笔记转化为行动项、综合研究、提取模式 |
| **图片粘贴** | 使用 Ctrl+V 直接将截图粘贴到终端（所有平台） |
| **视觉分析** | 获取 mockup 反馈、分析竞争对手、审查数据可视化 |
| **输出样式** | 为重复出现的文档类型创建可复用的格式化模板 |

## @ 符号 - 文件引用系统

`@` 符号告诉 Claude 要读取、分析或引用哪些文件。

### 基本语法

```
读取 @meeting-notes.txt 并总结行动项
```

```
比较 @competitor-a.md 和 @competitor-b.md
```

```
分析 @research/interviews/user-01.txt
```

### 支持的文件类型

| 格式 | 扩展名 | 常见用途 |
|---|---|---|
| Markdown | `.md` | PRD、文档、笔记 |
| Text | `.txt` | 会议笔记、原始数据 |
| CSV | `.csv` | 调查结果、指标 |
| JSON | `.json` | API 响应、结构化数据 |
| PDF | `.pdf` | 研究论文、报告 |
| Images | `.png`, `.jpg`, `.gif` | 截图、mockup |

### 处理多个文件

**批量处理文件：**

```
读取 /meetings/ 中的所有文件并提取行动项
```

**交叉引用文档：**

```
读取 @prd.md 和 @user-research.md。
识别 PRD 中没有解决用户痛点的差距。
```

**从多个来源综合：**

```
读取 /interviews/ 中的所有文件并创建 @research-synthesis.md，包含：
- 前 5 个痛点
- 常见功能请求
- 用户画像
```

## 粘贴图片 - 关键键盘快捷键

### 通用命令：Ctrl+V

**重要：在所有平台上使用 Ctrl+V，包括 Mac**

| 平台 | 正确 | 错误 |
|---|---|---|
| Mac | **Ctrl+V** | Command+V |
| Windows | **Ctrl+V** | - |
| Linux | **Ctrl+V** | - |

**为什么 Mac 不同？** 在终端中，`Ctrl+V` 在所有操作系统中是通用的。`Command+V` 是 Mac 的 GUI 粘贴，在终端环境中不起作用。

### 如何粘贴图片

1. **复制图片到剪贴板**

    - 截图：`Cmd+Shift+4`（Mac）或 `Win+Shift+S`（Windows）
    - 从浏览器/Figma 复制：`Cmd+C`（Mac）或 `Ctrl+C`（Windows）

2. **粘贴到 Claude Code**

    - 在终端中按 **Ctrl+V**
    - 图片出现在对话中

3. **请求分析**

```
分析这个 mockup 并提供：
- PM 视角的 UX 反馈
- 技术挑战
- 无障碍问题
- 缺失的用户流程元素
```

### 你可以粘贴什么

| 类别 | 示例 |
|---|---|
| **设计与产品** | Figma mockup、线框图、用户旅程 |
| **数据与分析** | 仪表板截图、图表、指标 |
| **竞争研究** | 竞争对手截图、定价页面 |
| **协作** | 白板照片、会议图示 |
| **技术** | 错误消息、架构图 |

## 内容转换

PM 的核心技能是将相同信息传达给不同受众。

### 沟通矩阵

| 受众 | 格式 | 语气 | 重点 |
|---|---|---|---|
| 工程团队 | Slack | 随意、技术性 | 实现细节 |
| 利益相关者 | Email | 专业、战略性 | 业务成果 |
| 客户 | 发布说明 | 友好、以价值为导向 | 交付的价值 |
| 文档 | Notion 文档 | 全面、结构化 | 完整参考 |
| 高管 | 简报 | 简洁、以指标为导向 | 影响和下一步 |

### 示例：多格式沟通

```
读取 @sprint-planning-notes.txt 并创建：
1. @slack-update.md - 随意的团队公告
2. @stakeholder-email.md - 专业的高管摘要
3. @notion-doc.md - 完整的参考文档
```

## 输出样式 - 可复用模板

输出样式是格式化模板，可以消除重复的格式化说明。

### 创建输出样式

**方法 1：定义格式**

```
创建输出样式 Executive Briefing，包含：
- 最多 3 段
- 第 1 段：发生了什么（成果、指标）
- 第 2 段：为什么重要（业务影响）
- 第 3 段：下一步是什么（前瞻性）
- 使用要点列出指标
- 无术语，主动语态
```

**方法 2：展示示例**

```
创建输出样式 User Story，格式如下：

**作为** [画像]
**我想要** [能力]
**以便** [收益]

**验收标准：**
- 给定 [上下文]
  当 [操作]
  那么 [结果]
```

### 使用输出样式

```
将 @meeting-notes.txt 转换为 Executive Briefing 样式
```

```
将 @sprint-work.md 格式化为 Weekly Update 样式
```

### PM 必备输出样式

用这些格式建立你的样式库：

1. **Executive Briefing** - 3 段式战略摘要

2. **User Story** - 作为/我想要/以便格式，带验收标准

3. **Linear/Jira Issue** - 标题、描述、验收标准、优先级、估算

4. **Weekly Update** - 已完成/进行中/阻塞/下周

5. **Release Notes** - 面向客户、以价值为导向

6. **PRD Section** - 问题/解决方案/指标/故事

7. **Slack Announcement** - 随意、emoji 友好

8. **Stakeholder Email** - 专业、上下文丰富

## 真实世界的 PM 工作流程

### 会议处理（每周）

**没有 Claude Code：** 35 分钟

- 回顾笔记：10 分钟
- 提取行动项：15 分钟
- 按负责人组织：5 分钟
- 格式化分发：5 分钟

**有 Claude Code：** 2 分钟

```
处理 /meetings/today/ 中的所有文件并创建 @action-items-summary.md，包含：
- 按负责人组织的行动项表格
- 优先级和截止日期
- 按会议来源分组
```

**节省时间：** 33 分钟/周 = 2.75 小时/月

### 用户研究综合

**没有 Claude Code：** 2 小时 40 分钟

- 阅读 8 份访谈记录：60 分钟
- 高亮主题：30 分钟
- 提取引用：20 分钟
- 组织发现：20 分钟
- 撰写综合报告：30 分钟

**有 Claude Code：** 5 分钟

```
读取 /user-interviews/ 中的所有文件并创建 @research-synthesis.md，包含：
- 前 5 个痛点（3 位以上用户提及）
- 每个发现的支持性引用
- 按频率排名的功能请求
- 基于真实数据的精细化画像
- 建议的下一步
```

**节省时间：** 每个研究周期 2.5 小时

### 利益相关者沟通

**没有 Claude Code：** 45 分钟

- 起草 Slack 消息：10 分钟
- 撰写利益相关者邮件：15 分钟
- 创建 Notion 文档：15 分钟
- 确保一致性：5 分钟

**有 Claude Code：** 3 分钟

```
读取 @product-sync-notes.md 并创建三种格式：

1. Slack Update - 随意、emoji 友好、庆祝胜利
2. Stakeholder Email - 业务成果、指标、风险
3. Notion Document - 完整参考，包含依赖关系
```

**节省时间：** 42 分钟/sprint = 1.4 小时/月

## 最佳实践

### 应该做：

**明确使用 @ 引用**

```
好：读取 @user-research.md 并总结痛点
更好：读取 @user-research.md 并创建 @pain-points-summary.md
```

**请求结构化输出**

```
创建表格，包含：行动项 | 负责人 | 截止日期 | 优先级
```

**提供分析上下文**

```
我们正在为 Q2 在功能 A 和 B 之间做决定。
读取 @user-research.md 并推荐哪个能解决更关键的痛点。
```

**组合多个操作**

```
读取所有 /interviews/，综合发现，创建 @executive-summary.md 和 @detailed-insights.md
```

**逐步建立输出样式库**

- 遇到重复需求时创建样式
- 不要一次性创建所有样式

### 不应该做：

**忘记 @ 符号**

```
差：总结 meeting-notes.txt
好：总结 @meeting-notes.txt
```

**在 Mac 上使用 Command+V**

- 图片始终使用 Ctrl+V（所有平台）

**期望 Claude 记住未保存的工作**

- 用文件名保存文件以便后续引用

**粘贴敏感信息**

- 先从截图中删除机密数据

**创建过于复杂的样式**

- 保持简单和专注
- 更好的做法：10 个简单样式而不是 1 个复杂样式

## 故障排除

**Command+V 在 Mac 上不起作用**

- 解决方法：改用 **Ctrl+V**
- 原因：终端在所有平台上使用 Ctrl 快捷键

**Claude 找不到引用的文件**

- 检查文件名拼写（区分大小写）
- 验证文件路径：`/meetings/ 中有哪些文件？`
- 问 Claude：`@meeting-notes.txt 存在吗？`

**图片已粘贴但没有分析**

- 验证图片出现在对话中
- 尝试不同格式（.png 或 .jpg）
- 检查大小（保持在 10MB 以下）
- 用 Ctrl+V 重新粘贴

**输出样式格式不正确**

- 展示所需格式的具体示例
- 明确说明结构
- 迭代测试和优化
- 从简单开始，逐步增加复杂性

**文件已创建但在 Obsidian 中不可见**

- 刷新 Obsidian
- 检查是否不在隐藏的 .claude/ 文件夹中
- 在 Finder/Explorer 中查看
- 问 Claude：`你把文件保存在哪里了？`

## 下一步是什么？

**Module 1.4: Agents for Parallel Work**

学习克隆 Claude 进行同时任务：

- 并行处理 10 份会议笔记
- 同时研究 5 个竞争对手
- 构建多 agent 工作流程
- 在 30 分钟内完成 5 小时的工作

交互式轨道：输入 `/start-1-4`

## 快速参考

**基本命令：**

- `@filename` - 引用文件
- `Ctrl+V` - 粘贴图片（所有平台）
- `读取 @file 并创建 @output` - 基本工作流程

**文件操作：**

```
单个：@meeting-notes.txt
多个：@file1.txt, @file2.txt, @file3.txt
文件夹：/meetings/ 中的所有文件
```

**内容转换：**

```
将 @source.txt 转换为：
1. @casual-slack.md - 团队友好
2. @formal-email.md - 利益相关者适当
3. @comprehensive-doc.md - 完整参考
```

**输出样式：**

```
创建：创建输出样式 [名称]，规则：[格式]
使用：将 @content.txt 格式化为 [名称] 样式
```

**图片分析：**

1. 复制图片（Cmd+Shift+4 / Win+Shift+S）
2. 用 Ctrl+V 粘贴
3. 请求分析

## 资源

在交互式模块（`/start-1-3`）中练习这些工作流程，为文件引用、图片粘贴和输出样式建立肌肉记忆。

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。如果你对本模块或整个课程有任何反馈，请给我留言！我正在为 PM 构建者建立一个新闻通讯和社区，请查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=first-tasks)。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[1.2: Visualizing Files](https://ccforpms.com/fundamentals/visualizing-files) | [1.4: Agents](https://ccforpms.com/fundamentals/agents)
