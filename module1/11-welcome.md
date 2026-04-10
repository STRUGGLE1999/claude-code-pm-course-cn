# 1.1: 欢迎来到 TaskFlow

- **完成时间：** 20 分钟
- **前置条件：** 已安装 Claude Code

**在 Claude Code 中开始本模块：** 运行 `/start-1-1` 启动交互式体验。

## ▶️ 如何开始的提醒

⚠️ **如果你还没有克隆仓库：** 请先返回 [Module 0.2: Start Claude Code & Clone the Course](https://ccforpms.com/getting-started/start-and-clone)。你需要将课程文件下载到电脑上才能继续。

**有两种方式在 Claude Code 中启动本课程：**

### 方式一：在文件管理器中找到它

导航到你的 Documents 文件夹，找到 `claude-code-pm-course` 文件夹。然后右键点击并选择"在文件夹中打开新终端"。

它会看起来像这样：

然后输入 `claude` 并按回车键。

### 方式二：从终端打开

在终端中输入以下命令：

```
cd ~/Documents/claude-code-pm-course
claude
```

这会导航到你的课程文件夹并直接在其中打开 Claude Code。

**无论哪种方式，你都会到达同一个地方。然后，开始本模块：**

**在 Claude Code 中开始本模块：** 运行 `/start-1-1` 启动交互式体验。

这就是你开始每个模块的方式！

## 📖 概述

本模块介绍 TaskFlow（你的虚拟公司）并解释课程结构。

**关键要点：** 这是一个实践性课程，你将使用 Claude Code 完成真正的 PM 工作。

## 🎓 课程如何运作

### 两个部分

**1. 交互式模块（你现在正在做的）**

- 使用 Claude Code 完成模块
- 每个模块以斜杠命令开始：`/start-1-1`、`/start-1-2` 等
- Claude 逐步引导你完成练习
- 你实际完成工作（而不只是阅读）
- 为 TaskFlow 完成真正的 PM 任务

**2. 参考指南（你现在正在阅读的）**

- 每个模块的综合独立指南
- 可以在网站上阅读，无需使用 Claude Code
- 需要深入解释时使用
- 非常适合后续复习和参考

### 课程结构

- **Module 1: Fundamentals** - 核心概念和工作流程
- **Module 2: Advanced** - 真正的 PM 工作（PRD、数据分析、策略）

## 🏢 什么是 TaskFlow？

### 公司概述

**TaskFlow** 是为本课程创建的虚拟项目管理 SaaS 公司。可以理解为 **Asana 与 Jira 的结合，专为远程优先团队打造。**

**公司详情：**

- **成立时间：** 2021 年
- **阶段：** B 轮创业公司
- **融资：** 已筹集 $20M
- **团队规模：** 50 名员工（15 名工程师、5 名产品、10 名设计、20 名 GTM）
- **指标：** $2.5M ARR，10,000 活跃用户，快速增长

**你的角色：** 高级产品经理

- 负责激活和引导流程
- 向 CEO（Sarah Chen）汇报
- 与 CTO（Mike Rodriguez）和设计主管（Alex Kim）密切合作

**使命：** 赋能远程团队实现无缝协作

**产品：** 项目管理工具，结合任务管理、团队协作和异步优先功能，专为远程团队设计

**核心差异化：** 比 Asana 更简单，比 Linear 更跨职能，专为异步工作打造

### 👥 用户画像

- **Sarah - 企业管理员：** 大型公司的 IT 负责人，关注安全、合规和成本控制
- **Mike - IC 工程师：** 软件工程师，追求快速工具、GitHub 集成和最小干扰
- **Alex - 团队负责人：** 工程经理，关注团队可见性、工作负载平衡和进度追踪

## 📂 课程文件结构

当你在 TaskFlow 课程中工作时，你会看到：

```
claude-code-pm-course/
├── company-context/
│   ├── COMPANY.md - 公司概述和你的角色
│   ├── PRODUCT.md - TaskFlow 的功能
│   ├── PERSONAS.md - 3 个用户画像
│   └── COMPETITIVE.md - 竞争格局
├── lesson-modules/
│   ├── 1.1-welcome/ - 你现在的位置！
│   │   ├── CLAUDE.md (Claude 的教学脚本)
│   │   └── REFERENCE_GUIDE.md (本文件)
│   ├── 1.2-visualizing-files/
│   ├── 1.3-reading-files/
│   └── [更多模块...]
├── your-work/
│   └── [你将在练习中创建的文件]
└── CLAUDE.md - 项目记忆（在 Obsidian 中可见）
```

**注意：** `.claude/` 文件夹（用于命令、agents、设置）存在但是隐藏的。你将在后续模块中使用它。

## ⏱️ 时间投入

**每个模块：** 15-30 分钟 **每个级别：** 2-4 小时 **完整课程：** 20-30 小时

**但是：** 你可以按照自己的节奏进行！

- 一次完成一个模块
- 在级别之间休息
- 随时回来（进度会保存）

### 你将看到什么

在整个课程中，你会看到 Claude 运行如下命令：

```
⏺ Read(company-context/COMPANY.md)  ⎿ Read 45 lines  ⏺ Bash(ls -la company-context/)  ⎿ Listed 4 files
```

**不用担心理解这些！** 它们是 Claude 在后台工作。你只需专注于 PM 工作。

### 权限提示

有时，你会看到提示询问：是否允许此命令？

**只需点击：** 是，不再询问

这让 Claude 可以顺畅工作，无需每次都请求许可。

## 📋 最佳实践

**应该做：**

- 按顺序完成模块
- 实际完成练习
- 需要时休息

**不应该做：**

- 跳过模块
- 匆忙完成
- 对自己感到沮丧

## ❓ 常见问题

**我需要安装什么吗？** 只需要 Obsidian（Module 1.2），它是免费的。

**我可以跳过模块吗？** 不推荐。每个模块都建立在前一个模块的基础上。

**完整课程需要多长时间？** 总共 15-25 小时，按你自己的节奏进行。

**这适合非技术 PM 吗？** 是的！不需要编程。

**我可以用于实际工作吗？** 当然可以。完成 Module 1 后，你可以将这些模式应用到你的实际 PM 工作中。

## ✨ 你准备好了！

你现在了解了：

- TaskFlow（公司）
- 3 个用户画像
- 课程结构
- 预期内容

**欢迎来到课程！** 🚀

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。如果你对本模块或整个课程有任何反馈，请给我留言！我正在为 PM 构建者建立一个新闻通讯和社区，请查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=welcome)。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[0.2: Download & Start](https://ccforpms.com/getting-started/start-and-clone) | [1.2: Visualizing Files](https://ccforpms.com/fundamentals/visualizing-files)
