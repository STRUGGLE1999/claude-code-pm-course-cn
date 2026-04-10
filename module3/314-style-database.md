# 3.1.4: 构建风格数据库

- **完成时间：** 20分钟
- **前置条件：** 已完成一致性与风格（模块 3.1.3）

**在 Claude Code 中开始本模块：** 运行 `/start-3-1-4` 开始交互式体验。

## 概述

模块 3.1.4 教你图像生成的元技能：构建一个随每个项目增值的个人创意工具包。与其每次从零开始，你将构建一个经过验证的风格库，可以即时应用。

**关键要点：** 这不仅仅是关于生成图像——而是关于构建一个增值系统。你保存的每个风格都让未来的工作更快更好。

## 元技能

大多数人将 AI 图像工具作为一次性新奇事物使用：

- 生成某样东西
- 使用一次
- 忘记它
- 下次重新开始

高级用户做不同的事情：

- 生成某样东西
- **保存成功的 prompt**
- 跨项目复用
- **随时间构建库**

这种差异会显著累积。几个月后，你拥有一个涵盖各种场景的经过验证的风格库——人物画像、图表、演示文稿、营销。一条命令："use style #12" 就完成了。

## 你的风格库

Nano Banana 模块包含 `style-library.html`——一个可视化你风格收藏的本地 HTML 文件。

### 库中有什么

每个风格条目包含：

| 字段 | 用途 |
|---|---|
| **索引号** | 快速引用（"use style #02"） |
| **缩略图** | 视觉预览 |
| **名称** | 描述性标题 |
| **类别** | 过滤和组织 |
| **标签** | 可搜索的关键词 |
| **Prompt** | 完整的 prompt 文本 |
| **示例用途** | 何时使用此风格 |

### 使用库

**应用风格：**

```
Generate [your subject] using style #5
```

Claude 查找风格，检索 prompt，并将其应用到你的主体。

**浏览风格：** 在浏览器中打开 `style-library.html`。使用过滤按钮探索类别。

### 类别

库将风格组织成类别：

| 类别 | 包含内容 |
|---|---|
| **Framework** | 2x2 矩阵、金字塔、韦恩图 |
| **Flow** | 流程图、用户旅程图、流程图 |
| **Architecture** | 系统图、组织架构图、层次结构 |
| **Mockup** | 线框图、设备框架、UI 概念 |
| **Persona** | 肖像、生活场景照、头像 |
| **Marketing** | 广告、公告、社交图形 |
| **Artistic** | 插画、摄影风格、复古外观 |

## 扩展库的三种方法

### 方法 1：边做边存

最简单的方法——每当你创建喜欢的东西，保存它。

**工作流：**

1. 生成一张你满意的图像
2. 告诉 Claude："Add this style to my library"
3. Claude 用新条目更新 `style-library.html`
4. 该风格现在可供将来使用

**示例：**

```
You: Generate a minimalist journey map with soft colors
[Claude generates image]

You: I love this style. Add it to my library.

Claude: Done! Added as style #15 "Minimalist Journey Map"
in the Flow category.
```

**最适合：** 捕捉你自己的成功实验。

### 方法 2：从网上收集

优秀的 prompt 无处不在——社交媒体、教程、prompt 数据库。当你找到一个，测试它，然后保存。

**工作流：**

1. 在网上找到一个有前景的 prompt
2. 测试它："Generate [subject] using this prompt: [paste prompt]"
3. 如果效果好，告诉 Claude 保存它
4. 现在它成为你永久库的一部分

**示例：**

```
You: I found this prompt online - test it with a coffee shop:
"Make a photo that is perfectly isometric. It is not a miniature,
it is a captured photo that just happened to be perfectly isometric."

[Claude generates isometric coffee shop]

You: Great! Save this as "Perfect Isometric Photo"

Claude: Added as style #16 in 3D/Isometric category.
```

**最适合：** 策划社区中最好的 prompt。

### 方法 3：从任何图像提取

这是强力招数。看到喜欢的图像？提取其风格为文本，然后随时重现。

**工作原理：**

1. 提供图像（文件路径或 URL）
2. Claude 运行风格提取模块
3. 模块分析：颜色、光线、构图、纹理、情绪、效果
4. 返回详细的自然语言描述
5. 你现在可以仅从文本重现该风格

**工作流：**

```
You: Extract the style from this image: [path to image]

Claude: [Runs style_extract.py]

Here's the extracted style:
"Warm analog photography aesthetic with slight film grain.
Golden hour lighting creates soft shadows. Muted earth tones
with desaturated greens and warm highlights. Candid composition
with slight motion blur suggesting authentic moments..."

You: Generate a portrait using that extracted style

[Claude applies the style to a new subject]

You: Perfect. Save this to my library.
```

**最适合：**

- 从 Pinterest、Instagram 或设计灵感中捕捉风格
- 重现你欣赏的竞争对手或品牌的风格
- 从单张参考图像构建风格

### 风格提取模块

`style_extract.py` 模块使用 Gemini 的图像理解能力分析任何图像并描述其视觉风格。

**它捕捉什么：**

- 色调和温度
- 光线质量和方向
- 构图和取景
- 纹理和材质
- 情绪和氛围
- 排版（如果存在）
- 特殊效果或处理

**为什么有效：** Gemini 3 Pro 具有卓越的图像理解能力。它可以表达难以手动描述的视觉特质。

## 管理你的库

### 添加风格

当你告诉 Claude 保存风格时，它会：

1. 分配下一个可用的 ID 号
2. 创建描述性名称
3. 选择适当的类别
4. 添加相关标签
5. 保存缩略图
6. 更新 `style-library.html`

### 自定义库

风格库只是一个 HTML 文件——你可以自定义它：

- **添加列：** "Ask Claude to add a 'difficulty' column"
- **更改布局：** "Reorganize the library by category"
- **添加搜索：** "Add a search bar to the library"
- **修改设计：** "Make the library dark mode"

这是你的工具包。塑造它以适应你的工作流。

### 标签和过滤

标签帮助你快速找到风格。按类别的规范标签：

| 类别 | 可用标签 |
|---|---|
| Framework | 2x2-matrix, pyramid, venn, canvas, concentric, triangle |
| Flow | process, journey-map, flowchart, steps, sequence |
| Architecture | hierarchy, hub-spoke, system-diagram, org-chart, tree |
| Mockup | wireframe, device-frame, ui-concept, landing-page, mobile, desktop |
| Persona | portrait, lifestyle, headshot, context, illustrated, scene |
| Marketing | ad, social, announcement, banner, hero |
| Artistic | flat-illustration, hand-drawn, watercolor, photography, retro, minimalist, bold-graphic, 3d-render |

使用 `style-library.html` 中的过滤按钮按类别浏览。

## 复利效应

这就是为什么这很重要：

**第 1 周：** 你有 5 个风格

- 基本覆盖常见需求

**第 1 个月：** 你有 15 个风格

- 为你的工作形成模式
- 开始有"首选"风格

**第 3 个月：** 你有 30+ 个风格

- 全面覆盖
- 很少需要从零创建
- "Use style #23" 成为你工作流

**第 1 年：** 你有 50+ 个经过实战检验的风格

- 专业级库
- 每个风格在多个项目中验证过
- 几分钟完成过去需要几小时的工作

这就是复利效应。每个项目都让你的库更有价值。

## 工作流示例

### 示例 1：一致的品牌视觉

**场景：** 你的公司有特定的视觉风格需要保持。

**解决方案：**

1. 收集 3-5 张符合品牌的图像
2. 从你最好的示例中提取风格
3. 保存为 "Company Brand Style"
4. 应用到所有未来的图形

```
Generate a feature announcement using style #8 (Company Brand)
```

### 示例 2：快速探索

**场景：** 你需要 10 张用户人物画像，全部一致。

**解决方案：**

1. 浏览你的库查找人物画像风格
2. 选择一个符合项目基调的
3. 使用相同的风格号生成所有 10 张

```
Generate Sarah Chen portrait using style #12
Generate Marcus Johnson portrait using style #12
Generate Priya Patel portrait using style #12
...
```

### 示例 3：重现灵感

**场景：** 你的 CEO 分享了一张他们喜欢的竞争对手图表。

**解决方案：**

1. 从竞争对手的图像中提取风格
2. 保存到你的库（使用适当的名称）
3. 应用到你自己的内容

```
Extract the style from this diagram: [competitor's image]
Generate our product roadmap using that style
Save this as "Executive Diagram Style"
```

## 最佳实践

### 应该做的：

- **频繁保存风格** - 如果你喜欢它，保存它
- **使用描述性名称** - "Warm Portrait" 比 "Style 7" 更好
- **彻底打标签** - 帮助未来的你找到东西
- **积极提取** - 看到好的？抓住它
- **定期审查** - 删除未使用的风格

### 不应该做的：

- **不要囤积平庸的风格** - 质量胜于数量
- **不要忘记保存** - 立即捕捉成功
- **不要过度分类** - 保持简单
- **不要忽略提取的风格** - 它们通常是最好的

## 故障排除

### 风格库无法打开

- 确保你在浏览器中打开 `style-library.html`（不是文本编辑器）
- 尝试右键点击 → 打开方式 → 你的浏览器

### 新风格没有出现

- 刷新浏览器（Cmd+R / Ctrl+R）
- 检查 Claude 是否确认了保存

### 提取的风格不匹配原始图像

- 某些视觉效果难以用文本描述
- 尝试从更简单的示例中提取
- 结合参考图像以获得更好的结果

### 找不到合适的风格

- 使用类别过滤器
- 尝试按标签搜索
- 问 Claude："Which styles work for [your use case]?"

## 快速参考

```
Three Methods to Grow Your Library:
 1. Save as you go → Good work? Save it.
 2. Collect from online → Test, then save.
 3. Extract from images → The power move.

Using Styles:
 "Generate [subject] using style #X"
 "Apply style #Y to this"
 "Which styles work for journey maps?"

Managing Styles:
 "Add this to my library"
 "Save this as [name]"
 "Show me all persona styles"
```

## 下一步是什么？

你已完成模块 3.1——图像生成入门。你了解了机制、prompt 原则，以及如何构建增值系统。

**模块 3.2** 将这些技能应用于真正的 PM 任务。你将创建人物画像、用户旅程图、线框图、架构图和营销素材。

交互式学习路径：输入 `/start-3-2-1`

## 资源

- [Dribbble](https://dribbble.com/) - 设计灵感，找到要添加到库中的风格
- [Behance](https://www.behance.net/) - 创意作品集，从专业作品中提取风格
- [Pinterest](https://www.pinterest.com/) - 视觉发现，策划风格灵感板

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=nano-banana-database) 获取更多 PM 构建者内容。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[3.1.3: 一致性与风格](https://ccforpms.com/nano-banana/consistency-style) | [3.2.1: 用户与产品视觉](https://ccforpms.com/nano-banana/users-product-visuals)
