# 3.1.1: 欢迎与首次生成

- **完成时间：** 10分钟
- **前置条件：** 已下载 Nano Banana 文件（模块 3.0）

**在 Claude Code 中开始本模块：** 运行 `/start-3-1-1` 开始交互式体验。

## 概述

模块 3.1.1 带你从零开始生成第一张 AI 图像。你将设置 Gemini API key、配置计费，并观看 Claude 将一张参考照片变成神奇的作品。

**关键要点：** 设置是一次性过程。一旦配置好 API key，你就可以用简单的自然语言请求生成图像——Claude 会处理所有技术复杂性。

## 什么是 Gemini 3 Pro？

**Gemini 3 Pro**（代号 "Nano Banana Pro"）是 Google 最先进的图像生成模型。它可以：

- 从文本描述生成逼真的图像
- 在保留身份特征的同时转换参考照片
- 在图像上添加准确的文字叠加
- 在多次生成中创建一致的角色
- 理解并复制复杂的视觉风格

与消费级应用不同，直接访问 API 可以让你获得：

- **更宽松的内容政策**（例如，使用真人作为参考）
- **完全的参数控制**（aspect ratio、resolution 等）
- **基于会话的迭代**（逐步优化图像）
- **更低的成本**（约 $0.10/张 vs 订阅应用）

## 设置你的 API Key

### 步骤 1：从 Google AI Studio 获取 Key

1. 访问 [Google AI Studio](https://aistudio.google.com/)
2. 使用你的 Google 账户登录
3. 接受服务条款（如果是首次）
4. 点击左侧边栏的 **"Get API Key"**
5. 点击右上角的 **"Create API key"** 生成新 key
6. 为你的 key 命名（任意名称），选择 "Default Gemini Project"
7. 在控制面板中点击该 key
8. 复制 key - 它以 `AIza...` 开头

保管好这个 key。你将在步骤 3 中将其粘贴到 `.env` 文件中。

### 步骤 2：设置计费

Gemini 3 Pro 需要计费账户。别担心——它是按使用量付费的，非常实惠。

1. 在 Google AI Studio 中，进入 **Get API key**（左侧边栏底部）
2. 在 "Quota tier" 列下，点击 **Set up billing**
3. 按提示添加付款方式

**费用说明：**

- 每次图像生成约 $0.10
- 整个课程总费用不到 $5
- 无月度订阅——只为使用量付费
- 这笔钱付给 **Google**，不是 Carl（很遗憾）

### 步骤 3：配置你的 API Key

只需告诉 Claude 你的 API key，它会帮你设置好一切：

"我的 Gemini API key 是 AIzaYourKeyHere - 请把它添加到我的 .env 文件中"

Claude 会创建 `.env` 文件并安全地存储你的 key。

**想手动操作？** 复制 `.env.example` 为 `.env` 并添加你的 key：`GEMINI_API_KEY=YourKeyHere`

## 你的首次生成

设置完成后，你就可以开始生成了。在交互式模块中，Claude 使用一张参考照片创建一个有趣的欢迎图像——展示模型转换真实照片的能力。

**幕后发生了什么：**

1. 你描述想要的内容
2. Claude 调用 `image_gen.py` 中的 `generate()` 函数
3. 该函数将你的请求发送到 Gemini 的 API
4. 生成的图像保存到 `outputs/` 文件夹
5. Claude 告诉你在哪里找到它

**生成时间：** 每张图像约 10-15 秒。

## Claude 为你处理什么

当通过 Claude Code 生成图像时，你不需要担心：

| 你负责 | Claude 负责 |
|---|---|
| 描述你想要的内容 | API 调用和身份验证 |
| 选择风格 | 会话管理 |
| 提供反馈 | 文件保存和命名 |
| 审查输出 | 参数优化 |

这就是将 Gemini 与 Claude Code 结合使用的威力。你专注于创意方向；Claude 负责实现。

## `image_gen.py` 模块

所有图像生成都通过一个预构建的 Python 模块 `image_gen.py` 运行。你不需要编写任何代码——Claude 会代表你使用它。

**关键函数：**

- `generate()` - 创建或优化图像
- `new_session()` - 重新开始（清除对话历史）
- `session_info()` - 检查当前会话状态

**你将在模块 3.1.2 中了解更多关于这些函数的内容。**

## 输出结构

生成的图像保存到 nano-banana 目录中的 `outputs/` 文件夹：

```
nano-banana/
├── outputs/
│   ├── image_001.png
│   ├── image_002.png
│   └── ...
├── image_gen.py
├── .env
└── ...
```

图像按顺序编号。Claude 会告诉你每张生成图像的确切路径，这样你可以在 Finder（Mac）或资源管理器（Windows）中打开它。

## 故障排除

### "API key not found" 或身份验证错误

- 确认你的 `.env` 文件存在（不是 `.env.example`）
- 检查 key 是否正确粘贴，没有多余空格
- 确保 key 以 `AIza` 开头

### "Billing not enabled" 错误

- 返回 Google AI Studio → Settings → Plan information
- 确认已设置计费并关联了付款方式
- 计费激活可能需要几分钟

### 生成失败或超时

- 检查你的网络连接
- Gemini 可能正在经历高负载——等待一分钟后重试
- 如果错误持续，尝试开始新会话：告诉 Claude "Start a new session"

### 找不到生成的图像

- 图像保存到 `outputs/` 文件夹
- Claude 会在每次生成后提供确切路径
- 打开 Finder（Mac）或资源管理器（Windows）并导航到该文件夹

## 最佳实践

**保护你的 API key：**

- 永远不要将 `.env` 提交到 git（默认已在 `.gitignore` 中）
- 不要公开分享你的 API key
- 如果 key 泄露，可以在 Google AI Studio 中重新生成

**在适当的查看器中查看输出：**

- 终端无法显示图像——始终打开文件
- 使用预览（Mac）、照片（Windows）或任何图像查看器
- 为获得最佳体验，工作时保持 `outputs/` 文件夹打开

## 接下来你将学到什么

模块 3.1.1 帮你完成设置。模块 3.1 的其余部分教你有效使用图像生成：

- **3.1.2: 理解基础** - 参数、aspect ratio、resolution、迭代
- **3.1.3: 一致性与风格** - prompt 黄金法则、参考图像、变体
- **3.1.4: 构建风格数据库** - 创建可复用的风格库

然后模块 3.2 将这些技能应用于真正的 PM 工作：人物画像、图表、模型和营销素材。

## 下一步是什么？

你已经设置完成并生成了第一张图像。现在是时候了解系统如何工作了。

**模块 3.1.2** 教你关于 `generate()` 函数、可用参数以及如何迭代优化图像。

交互式学习路径：输入 `/start-3-1-2`

## 资源

- [Google AI Studio](https://aistudio.google.com/) - 获取你的 API key 并管理计费
- [Gemini Image Generation Documentation](https://ai.google.dev/gemini-api/docs/image-generation) - 官方 API 参考

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=nano-banana-welcome) 获取更多 PM 构建者内容。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[3.0: 设置与下载](https://ccforpms.com/nano-banana/setup) | [3.1.2: 理解基础](https://ccforpms.com/nano-banana/understanding-basics)
