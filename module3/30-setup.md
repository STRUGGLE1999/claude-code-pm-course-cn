# 3.0: 设置与下载

- **完成时间：** 5分钟
- **前置条件：** 已安装 Claude Code，拥有 Google 账户

## 什么是 Nano Banana？

Nano Banana 教你使用 **Gemini 3 Pro Preview**（代号 "Nano Banana Pro"）生成专业图像——这是 Google 最先进的图像生成模型。但这不仅仅是一门关于提示图像生成器的课程。

**这是一门 Claude Code 课程。**

你将学习构建一个完整的图像生成工作流，其中 Claude Code 会：

- **运行你的生成任务** - 直接从终端执行图像请求
- **批量生成多张图像** - 并行生成变体和迭代版本
- **管理你的文件** - 组织输出、智能命名、跟踪版本
- **构建你的风格库** - 创建和维护可复用的风格定义
- **与你一起迭代** - 通过对话优化 prompt、调整参数、改进结果

课程结束时，你将能够创建：

- **人物肖像** 和生活场景照
- **用户旅程图** 和用户流程可视化
- **线框图** 和设备模型
- **架构图** 和策略框架
- **营销素材** 和发布图形

**关键洞察：** 你不仅仅是在学习生成图像——你正在构建一个由 Claude Code 驱动的专业创意流水线，它会随着时间推移不断增值。工作流的重要性不亚于输出结果。

## 开始之前

**你需要：**

- 已安装并能正常运行的 Claude Code
- 一个 Google 账户
- 用于 Google Cloud 计费的付款方式

**关于费用：** Gemini 3 Pro 每张图像收费约 $0.10。整个课程总费用不到 $5。Claude 会在第一个模块中引导你设置计费。

## 下载并开始

**打开终端并运行：**

```
cd ~/Documents && \
curl -L https://github.com/carlvellotti/claude-code-pm-course/releases/latest/download/complete-course.zip -o claude-code-pm-course.zip && \
unzip claude-code-pm-course.zip -d claude-code-pm-course && \
cd claude-code-pm-course && \
claude "/start-3-1-1"
```

**这个命令会：**

1. 导航到你的 Documents 文件夹
2. 下载完整的课程资料（包含 Nano Banana）
3. 解压到 `claude-code-pm-course`
4. 进入该文件夹
5. 启动 Claude Code
6. 进入第一课

## 替代方案：手动下载

如果上面的命令不起作用：

1. 从 [最新发布页面](https://github.com/carlvellotti/claude-code-pm-course/releases/latest) 下载 zip 文件
2. 解压到你的 Documents 文件夹
3. 打开终端并运行：

```
cd ~/Documents/claude-code-pm-course && claude
```

4. 输入 `/start-3-1-1` 开始

## 你将学到什么

**模块 3.1：图像生成入门**

- 3.1.1: 欢迎与首次生成 - 设置 API key 并生成你的第一张图像
- 3.1.2: 理解基础 - 参数、aspect ratio、resolution、迭代
- 3.1.3: 一致性与风格 - prompt 黄金法则、参考图像、变体
- 3.1.4: 构建风格数据库 - 创建可复用的风格库

**模块 3.2：PM 应用场景**

- 3.2.1: 用户与产品视觉 - 人物画像、用户旅程图、线框图、模型
- 3.2.2: 策略与架构 - 图表、矩阵、路线图
- 3.2.3: 营销与发布素材 - 应用商店图形、广告、公告

## 故障排除

### curl 或 unzip 未找到

**Mac：** 在终端中运行 `xcode-select --install` 安装命令行工具。

**Windows：** 从发布页面（链接见上方）手动下载 zip 文件，解压后进入文件夹并运行 `claude`。

### 下载失败

尝试从 [发布页面](https://github.com/carlvellotti/claude-code-pm-course/releases/latest) 手动下载并解压到你的 Documents 文件夹。

### Claude Code 无法识别 /start 命令

确保你在 `claude-code-pm-course` 文件夹内运行 Claude Code。斜杠命令只有在 Claude 能访问模块文件时才能工作。

## 下一步是什么？

当 Claude Code 在 `claude-code-pm-course` 文件夹内运行后：

**输入：** `/start-3-1-1`

Claude 将引导你：

- 获取 Gemini API key
- 设置计费
- 生成你的第一张 AI 图像

整个设置大约需要 5 分钟，你很快就能拥有第一张 AI 生成的图像。

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。Nano Banana 是 Claude Code for Product Managers 课程的一部分。查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=nano-banana-setup) 获取更多 PM 构建者内容。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[2.3: 产品策略](https://ccforpms.com/advanced/product-strategy) | [3.1.1: 欢迎与首次生成](https://ccforpms.com/nano-banana/welcome-first-generation)
