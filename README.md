# Claude Code 产品经理教程（中文版）

![课程封面](images/hero.png)

## 项目简介

这是 [ccforpms.com](https://ccforpms.com/) 网站的完整中文翻译版本。原网站由 Carl Vellotti 创建的免费 Claude Code 教程，专门面向产品经理。

### 原网站特点

- **在 Claude Code 中学习 Claude Code！** 这个免费课程通过实际操作教授 AI 驱动的产品管理 - 没有视频，没有文档，只有 Claude Code 内部的真实 PM 工作
- 你将安装它，克隆此仓库，然后输入 `/start-1-1` 开始学习
- Claude 会交互式地引导你完成每个模块
- 你通过处理真实文件来学习

### 适用人群

**产品经理** - 想要学习使用 LLM 进行工作的最强大方式的人。

Claude Code 不是一个聊天机器人。它是一个直接与你的文件和计算机一起工作的 AI：

- 读取你的用户研究，编辑 PRD，分析数据
- 并行运行 10 个实例同时处理 10 个文件
- 跨越每个会话记住关于你产品的上下文
- 分析你粘贴的截图和模型
- 在与团队分享工作之前，作为自定义 AI 审阅者（工程师、高管、UX）

这是 AI 集成到你的实际工作流程中，而不是作为聊天窗口附加的。

**你不需要编码或终端经验。** 如果你可以用简单的英语描述你想要什么，就可以使用 Claude Code。

### 你将学到什么

**核心 Claude Code 能力：**

- **文件操作：** 直接从终端读取、写入和编辑文档
- **并行代理：** 同时启动多个 Claude 实例处理文件
- **自定义子代理：** 为不同视角创建专门的审阅者
- **项目记忆：** 使用 CLAUDE.md 维护持久的上下文
- **@-mentions：** 引用文件和文件夹为 Claude 提供完整上下文
- **图像分析：** 粘贴截图和模型以获得即时反馈

**应用于真实 PM 工作：**

- 处理会议记录并提取行动项
- 从多个来源综合用户研究
- 使用多视角反馈编写 PRD
- 分析产品数据并运行实验
- 开发竞争策略并创建演示文稿

### 课程结构

| 模块 | 内容 |
|------|------|
| **模块 0：入门指南** | 安装 Claude Code 并克隆课程仓库 |
| **模块 1：基础知识** | 通过 TaskFlow 的实践练习掌握文件操作、代理、子代理和项目记忆 |
| **模块 2：高级 PM 工作** | 使用模块 1 学到的所有内容编写 PRD、分析数据、制定产品策略 |
| **模块 3：Nano Banana** | 使用 Gemini 3 Pro 生成专业图像 |
| **模块 4：Vibe Coding** | 从零构建真实的 Web 应用并部署到互联网 |

### 你将实际做什么

**模块 1.2：** 设置可视化工作区（Obsidian 或 VS Code）用于分屏工作流 - 观看文件出现和实时更新

**模块 1.3：** 处理真实会议记录，分析用户研究截图，创建可重用模板

**模块 1.4：** 启动 10 个并行代理同时处理 10 个会议（5 分钟而不是 50 分钟）

**模块 1.5：** 构建专门的子代理（工程师、高管、用户研究员）以获得多视角反馈

**模块 2.1：** 使用苏格拉底式提问、并行方法和子代理审阅，为 AI 功能编写完整的 PRD

**模块 2.2：** 分析产品漏斗，估算功能影响，并在真实数据集上运行 A/B 测试分析

**模块 2.3：** 并行研究竞争对手，使用魔鬼代言人做出战略选择，创建高管演示文稿

### 前置要求

- Claude Pro 或 Max 订阅（$20/月）- [在此注册](https://claude.ai/)
- Mac、Windows 或 Linux 电脑
- 基础 PM 经验（知道什么是 PRD）
- 10-12 小时完成课程
- 愿意通过实践学习

**不需要编码经验。不需要终端经验。** 如果你能够进行对话，就可以使用 Claude Code。

### 开始学习

**👉 [下载课程材料](https://github.com/carlvellotti/claude-code-pm-course/releases/latest/download/complete-course.zip)** - 获取完整课程（最新版本：v1.0.0）

**👉 [安装指南](./module0/01-installation.md)** - 15 分钟内安装 Claude Code

**👉 [开始课程](./module0/02-start-and-clone.md)** - 下载材料并开始

使用 **侧边栏** 浏览所有模块。使用 [搜索页面](./appendix/search-guide.md) 快速查找特定主题。

---

## 关于本课程

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。

- 如果你对本模块或整个课程有任何反馈，请给我留言！
- 我正在为 PM 构建者建立通讯和社区，请查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=homepage)

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

---

## 项目结构

```
claude-code-pm-course-cn/
├── README.md                   # 本文件
├── images/                      # 图片资源
│   └── hero.png
├── homepage/                 # 首页内容
│   └── README.md
├── module0/                   # 模块0：入门指南
│   ├── 00-introduction.md
│   ├── 01-installation.md
│   └── 02-start-and-clone.md
├── module1/                   # 模块1：基础知识
│   ├── 11-welcome.md
│   ├── 12-visualizing-files.md
│   ├── 13-first-tasks.md
│   ├── 14-agents.md
│   ├── 15-custom-subagents.md
│   ├── 16-project-memory.md
│   └── 17-claude-code-navigation.md
├── module2/                   # 模块2：高级 PM 工作
│   ├── 21-write-prd.md
│   ├── 22-analyze-data.md
│   └── 23-product-strategy.md
├── module3/                   # 模块3：Nano Banana
│   ├── 30-setup.md
│   ├── 311-welcome-first-generation.md
│   ├── 312-understanding-basics.md
│   ├── 313-consistency-style.md
│   ├── 314-style-database.md
│   ├── 321-users-product-visuals.md
│   ├── 322-strategy-architecture-visuals.md
│   └── 323-marketing-launch-assets.md
├── module4/                   # 模块4：Vibe Coding
│   ├── overview.md
│   ├── 41-setup.md
│   ├── 42-plan.md
│   ├── 43-build-iterate.md
│   ├── 44-github.md
│   └── 45-go-live.md
└── appendix/                  # 附录
    ├── cowork-guide.md
    ├── taskflow-company-overview.md
    ├── taskflow-product-overview.md
    ├── taskflow-user-personas.md
    └── search-guide.md
```

---

*本翻译项目仅供学习交流使用，版权归原作者所有。*
