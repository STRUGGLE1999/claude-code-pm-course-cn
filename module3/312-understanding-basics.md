# 3.1.2: 理解基础

- **完成时间：** 15分钟
- **前置条件：** 已设置 API key（模块 3.1.1）

**在 Claude Code 中开始本模块：** 运行 `/start-3-1-2` 开始交互式体验。

## 概述

模块 3.1.2 教你图像生成的机制——系统如何工作以及你可以控制什么。你将理解 `generate()` 函数，了解 aspect ratio 和 resolution，并掌握迭代的艺术。

**关键要点：** 你不需要记住参数或编写代码。用自然语言描述你想要的内容，Claude 会选择合理的默认值。但了解什么是可能的有助于你获得更好的结果。

## 生成如何工作

当你要求 Claude 生成图像时：

1. **你描述** 你想要的内容（用自然语言）
2. **Claude 翻译** 你的请求为 API 参数
3. **`generate()` 函数** 将请求发送到 Gemini
4. **Gemini 生成** 图像（10-15 秒）
5. **图像保存** 到你的 `outputs/` 文件夹
6. **Claude 告诉你** 在哪里找到它

你永远不需要直接接触 API。Claude 处理一切。

## `generate()` 函数

所有图像生成都通过 `image_gen.py` 进行。以下是关键参数：

| 参数 | 控制内容 | 默认值 |
|---|---|---|
| `prompt` | 你对图像的描述 | 必需 |
| `reference_images` | 用作视觉输入的照片 | 无 |
| `aspect_ratio` | 输出图像的形状 | 1:1 |
| `resolution` | 输出的大小/质量 | 1K |

### 两种工作方式

**选项 1：让 Claude 决定**

```
Generate a professional headshot of a product manager
```

Claude 选择合理的默认值（头像用 1:1，草稿用 1K）。

**选项 2：指定你想要的**

```
Generate a professional headshot, 16:9 aspect ratio, 2K resolution
```

Claude 会遵循你的明确要求。

两种方法都很有效。从选项 1 开始，需要时再具体指定。

## Aspect Ratios

Aspect ratio 是图像的形状。根据使用场景选择。

| 比例 | 形状 | 最佳用途 |
|---|---|---|
| **1:1** | 正方形 | 头像、Instagram 帖子、图标 |
| **16:9** | 宽幅横版 | 演示文稿、YouTube 缩略图、hero 图像 |
| **9:16** | 高幅竖版 | Instagram/TikTok 故事、手机壁纸 |
| **4:5** | 高矩形 | Instagram 信息流帖子 |
| **3:2** | 经典照片 | 传统摄影比例 |
| **4:3** | 标准 | 旧式演示文稿、平板电脑 |
| **21:9** | 超宽 | 电影感、横幅 |

### 快速参考

- **演示文稿幻灯片？** → 16:9
- **社交媒体帖子？** → 1:1 或 4:5
- **手机模型？** → 9:16
- **网站 hero 图？** → 16:9 或 21:9
- **头像？** → 1:1

## Resolution

Resolution 决定大小和细节级别。它不影响创意质量——只影响像素尺寸。

| Resolution | 尺寸 | 生成时间 | 最佳用途 |
|---|---|---|---|
| **1K** | 1024px | 约 20 秒 | 草稿、迭代、探索 |
| **2K** | 2048px | 约 30 秒 | 最终输出、演示文稿 |
| **4K** | 4096px | 约 45 秒 | 打印、大屏幕显示 |

### Resolution 策略

**迭代时使用 1K。** 它更快，费用相同，让你更快探索。

**最终版本使用 2K。** 一旦你对创意方向满意，用更高 resolution 重新生成。

**仅在打印时使用 4K。** 除非你要大规模打印，否则 4K 有些过度。

## 迭代：核心工作流

迭代是图像生成中最重要的概念。与其希望一次就成功，不如逐步优化。

### 为什么迭代有效

Gemini 是一个"思考模型"——它在对话中保持上下文。当你说"让它更蓝"，它知道"它"指的是什么以及你之前讨论过的内容。

**单次尝试方法（令人沮丧）：**

```
Generate the perfect image → Hope it's right → Start over if not
```

**迭代方法（有效）：**

```
Generate first draft → "Add more contrast" → "Move the text higher" → "Perfect"
```

### 如何迭代

Claude 生成图像后，只需请求更改：

- "让背景更暗"
- "添加微妙的阴影"
- "把文字改成 'Launch Day'"
- "让它感觉更专业"
- "尝试更暖的色调"

Claude 继续与 Gemini 的会话，你的更改会基于之前的图像进行。

### 何时重新开始

有时迭代不是正确的选择：

- **重大方向改变** → 用 `new_session()` 重新开始
- **完全不同的主题** → 重新开始
- **想探索替代方案** → 生成变体（在 3.1.3 中介绍）

告诉 Claude "start a new session" 或 "let's try something completely different"，它会重新开始。

## 会话详解

一个 **session** 是与 Gemini 保持上下文的对话。它的工作方式如下：

**在会话内：**

- Gemini 记住之前的生成
- 你可以引用"这张图像"或"它"
- 编辑基于之前的版本
- "思考签名"保留推理过程

**会话之间：**

- 全新开始
- 不记得之前的工作
- 适合新项目或方向

### 会话管理

Claude 自动处理会话，但你可以控制它们：

| 你想要什么 | 该说什么 |
|---|---|
| 继续优化 | 直接描述更改 |
| 重新开始 | "Start a new session" |
| 检查状态 | "What's the current session?" |

**专业提示：** 会话最适合线性优化。如果你想探索多个方向，使用变体（在 3.1.3 中介绍）。

## 实际示例

### 示例 1：演示文稿图形

**你：** "Create a hero image for a presentation about AI productivity"

**Claude 生成** 一张 1:1 的图像，resolution 为 1K。

**你：** "Make it 16:9 for my slides"

**Claude 用正确的 aspect ratio 重新生成。**

**你：** "Add text that says 'AI for PMs'"

**Claude 添加文字叠加。**

**你：** "This is perfect, regenerate at 2K"

**Claude 生成最终的高 resolution 版本。**

### 示例 2：快速探索

**你：** "Generate a user persona portrait - corporate vibe"

**Claude 生成第一版。**

**你：** "Try a more casual look"

**Claude 优化风格。**

**你：** "Actually let's start fresh - try illustrated style instead"

**Claude 开始新会话并生成插画版本。**

## 最佳实践

### 应该做的：

- **从 1K resolution 开始** 以加快迭代速度
- **具体说明更改** - "让天空更橙" 比 "改进它" 更好
- **当你没有强烈偏好时让 Claude 选择默认值**
- **增量构建** - 小更改更可预测

### 不应该做的：

- **不要从 4K 开始** - 你会浪费时间在即将更改的图像上
- **不要一次做多个更改** - 一次迭代一件事
- **不要含糊其辞** - "让它更好" 让 Claude 无从下手
- **不要放弃好的图像** - 迭代而不是重新开始

## 故障排除

### 更改没有被应用

- 确保你具体说明了要更改什么
- 尝试重新表述："change the background color to navy blue" 而不是 "different background"
- 会话可能已混乱 - 重新开始

### Aspect ratio 看起来不对

- 确认你请求了正确的比例（16:9 vs 9:16 是常见的混淆）
- 某些构图在某些比例下效果更好 - Claude 可能会建议替代方案

### 图像质量看起来低

- 检查 resolution - 你可能在使用 1K（这对草稿来说没问题）
- 对于最终输出，明确请求 2K resolution

### 生成速度慢

- 4K 大约需要 45 秒，感觉慢但这是正常的
- 网络不好会增加延迟
- API 高负载可能导致延迟

## 快速参考卡

```
Aspect Ratios:
 1:1 → Square (profiles, icons)
 16:9 → Landscape (presentations)
 9:16 → Portrait (stories, mobile)
 4:5 → Tall (Instagram feed)

Resolution:
 1K → Fast drafts
 2K → Final outputs
 4K → Print only

Workflow:
 1. Generate at 1K
 2. Iterate until happy
 3. Regenerate at 2K for final
```

## 下一步是什么？

你了解了机制。现在是时候学习艺术了。

**模块 3.1.3** 教你 prompt 的黄金法则——如何写出能获得惊人结果的描述。你还将学习参考图像和生成变体。

交互式学习路径：输入 `/start-3-1-3`

## 资源

- [Gemini Image Generation Documentation](https://ai.google.dev/gemini-api/docs/image-generation) - 参数、aspect ratio、resolution 选项
- [Gemini 3 Developer Guide](https://ai.google.dev/gemini-api/docs/gemini-3) - 思考签名、多轮会话

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=nano-banana-basics) 获取更多 PM 构建者内容。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[3.1.1: 欢迎与首次生成](https://ccforpms.com/nano-banana/welcome-first-generation) | [3.1.3: 一致性与风格](https://ccforpms.com/nano-banana/consistency-style)
