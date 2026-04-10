# 3.1.3: 一致性与风格

- **完成时间：** 20分钟
- **前置条件：** 已理解基础（模块 3.1.2）

**在 Claude Code 中开始本模块：** 运行 `/start-3-1-3` 开始交互式体验。

## 概述

模块 3.1.3 教你编写能获得惊人结果的 prompt，并在多次生成中保持一致性。你将学习 Google 官方的 prompt 黄金法则、如何使用参考图像，以及探索多个方向的技巧。

**关键要点：** 优秀的结果来自清晰的沟通，而非魔法关键词。像向人类设计师简报一样与 Gemini 交流。

## Prompt 黄金法则

Google 发布了针对 Gemini 图像生成的官方指导。这四条法则将改变你的结果。

### 法则 1：编辑，不要重掷

**如果图像已经 80% 正确，请求具体更改而不是重新开始。**

这是最重要的法则。Gemini 是一个思考模型——它保持上下文并理解你的创意方向。当你迭代时，它会在有效的基础上构建。

**不要这样：**

```
[Generate image]
"Not quite right"
[Generate again from scratch]
[Generate again from scratch]
[Generate again from scratch]
```

**这样做：**

```
[Generate image]
"Make the lighting warmer"
"Move the subject to the left"
"Add more contrast"
[Done]
```

**为什么有效：** 每次优化都给 Gemini 更多关于你想要什么的信息。重新开始会丢弃所有这些上下文。

### 法则 2：使用自然语言和完整句子

**像向人类艺术家简报一样与 Gemini 交流，而不是写搜索关键词。**

你可能在网上看到过"标签汤" prompt——逗号分隔的关键词像搜索查询一样。那是过时的方法。Gemini 是一个理解自然语言的思考模型。

**标签汤（过时）：**

```
professional headshot, business attire, confident, studio lighting,
bokeh background, sharp focus, 8k, trending on artstation
```

**自然语言（更好）：**

```
A professional headshot of a confident business executive in a
modern studio setting. Soft, even lighting creates a warm atmosphere.
The background has a subtle blur that keeps focus on the subject.
```

**为什么有效：** 完整句子提供上下文和元素之间的关系。Gemini 理解"创造温暖感的柔和光线"比"柔和光线，温暖"更好。

### 法则 3：具体且描述性强

**定义主体、场景、光线、情绪、纹理和材质。深入细节。**

Gemini 可以处理惊人的细节——远超你的预期。你越具体，输出就越接近你的愿景。

**含糊：**

```
A coffee shop
```

**具体：**

```
A cozy corner coffee shop on a rainy afternoon. Warm Edison bulb
lighting casts golden pools on worn wooden tables. Steam rises from
ceramic mugs. Rain streaks down floor-to-ceiling windows. A few
patrons read books in overstuffed leather armchairs. The walls are
exposed brick with vintage concert posters. Soft jazz plays from
an unseen speaker.
```

**需要考虑的元素：**

- **主体：** 谁/什么是焦点？
- **场景：** 这发生在哪里？
- **光线：** 自然光、人造光、时间、方向、质量
- **情绪：** 情感基调、氛围
- **纹理：** 表面质感、材质
- **颜色：** 色调、对比、温度
- **构图：** 取景、透视、焦点

**专业提示：** 如果你不确定如何添加细节，问 Claude："Help me expand this prompt with more specifics."

### 法则 4：提供上下文

**告诉 Gemini "为什么" 或 "为谁"，让它做出更明智的创意决策。**

上下文塑造创意选择。一张"用于儿童书籍"的肖像与同一主题"用于奢侈品牌活动"看起来完全不同。

**没有上下文：**

```
A lion in a savanna
```

**有上下文：**

```
A lion in a savanna, for a nature documentary title card.
The image should feel majestic and cinematic, capturing the
power and dignity of wildlife.
```

**上下文示例：**

- "for a pitch deck to investors"
- "for a children's educational app"
- "for a premium subscription service landing page"
- "in the style of Apple product marketing"
- "targeting manufacturing operations managers"

**为什么有效：** Gemini 使用上下文对风格、基调、构图和细节级别做出适当的选择。

## 参考图像

参考图像是你实现一致性和风格控制的秘密武器。你可以提供图像让 Gemini 用作视觉输入。

### 参考图像类型

| 类型 | 目的 | 示例 |
|---|---|---|
| **风格参考** | 捕捉视觉美学 | 落地页设计、艺术风格 |
| **主体参考** | 保持角色一致性 | 人物照片、产品照片 |
| **构图参考** | 指导布局和取景 | 线框图、截图 |

### 单一风格参考

提供一张图像来捕捉其视觉风格：

```
Generate a [your subject] in the style of this reference image
```

Gemini 分析参考图像的颜色、光线、构图和艺术手法——然后将该风格应用到你的新主体。

**使用场景：**

- 复现品牌的视觉语言
- 匹配现有活动的美学
- 实现特定的艺术风格

### 多个主体参考

为了保持角色一致性，提供同一主体的多张照片：

```
Generate [prompt] using these reference photos of [subject]
```

**专业提示：** 更多参考照片 = 更好的结果。3-5 张不同角度和光线条件的照片帮助 Gemini 完全理解主体。

**使用场景：**

- 看起来像特定人物的人物画像
- 不同角度的产品照片
- 多张图像中的角色一致性

### 混合搭配

结合风格参考和主体参考：

```
Create [subject from reference A] in the style of [reference B]
```

这让你可以将真实主体放入艺术风格中，或将品牌美学应用到新内容。

**课程中的示例：**

- 风格参考：大胆的篮球落地页
- 主体参考：两只猫的照片（Winter 和 Piper）
- 结果：篮球风格的 "APEX CAT" 落地页，以真实的猫为特色

## 网格：一张图像中的多个视图

网格在单个输出中生成多个相关图像——非常适合角色设定表、产品视图或演示幻灯片。

### 何时使用网格

| 使用场景 | 网格格式 | 示例 |
|---|---|---|
| 角色设计 | 3x3 姿势 | 电子游戏精灵表 |
| 产品视图 | 2x2 角度 | 电商产品照片 |
| 演示文稿 | 2x4 幻灯片 | 教学材料 |
| UI 概念 | 2x3 屏幕 | 应用设计探索 |

### 如何请求网格

明确指定网格结构：

```
Create a 3x3 grid showing [subject] in 9 different poses:
- Row 1: Standing, walking, running
- Row 2: Sitting, jumping, waving
- Row 3: Thinking, pointing, celebrating
```

**关键提示：**

- 指定确切的网格尺寸（3x3、2x4 等）
- 描述每个单元格应包含的内容
- 请求所有单元格的风格一致

### PM 的网格使用场景

- **人物画像表情：** 同一角色展示不同情绪
- **用户旅程阶段：** 每个步骤的视觉呈现
- **功能截图：** 一张图像中的多个应用屏幕
- **演示幻灯片：** 完整的幻灯片可视化

## 变体：探索方向

与其只选择一个方向，不如生成多个变体然后选择最好的。

### 变体工作流

1. **生成 2-3 个变体** 同一概念
2. **审查所有选项** - 它们会有明显不同的诠释
3. **选择你最喜欢的**
4. **在该版本上迭代** 使用模块 3.1.2 中的技术

```
Generate 3 variants of [concept] with different creative interpretations
```

### 何时使用变体

- **不确定风格：** 让 Gemini 展示选项
- **客户演示：** 提供多个方向
- **创意探索：** 看看有什么可能
- **突破瓶颈：** 当你不确定自己想要什么时

### 变体 vs 迭代

| 变体 | 迭代 |
|---|---|
| 探索不同方向 | 优化一个方向 |
| 一次生成多个 | 逐步构建 |
| 选择，然后迭代 | 编辑，不要重掷 |
| 适合：探索 | 适合：优化 |

**最佳实践：** 使用变体找到你的方向，然后切换到迭代来完善它。

## 综合应用

这是一个结合所有技术的完整工作流：

### 步骤 1：编写详细的 Prompt（法则 2、3、4）

```
Create a professional persona portrait for a pitch deck (context).
The subject is Marcus, an operations manager in his mid-40s (subject).
He's in a manufacturing environment, wearing a polo shirt and safety vest (setting).
Confident but approachable expression (mood).
Natural lighting from large warehouse windows (lighting).
```

### 步骤 2：提供参考（如果有的话）

- 实际人物的照片参考，或
- 所需外观的风格参考

### 步骤 3：生成变体（如果正在探索）

```
Generate 3 variants with different compositions
```

### 步骤 4：选择并迭代（法则 1）

```
I like variant 2. Make the lighting warmer and have him
looking slightly to the left.
```

### 步骤 5：最终 Resolution

```
Perfect. Regenerate at 2K resolution for the final version.
```

## 最佳实践

### 应该做的：

- **用完整句子写作** - 自然地沟通
- **具体描述细节** - Gemini 能处理
- **提供上下文** - 解释目的
- **使用参考图像** - 用于风格和主体一致性
- **耐心迭代** - 优化而不是重新开始
- **生成变体** - 当探索方向时

### 不应该做的：

- **不要使用标签汤** - 已经过时
- **不要含糊其辞** - 具体性带来结果
- **不要跳过上下文** - "为什么"很重要
- **不要频繁重新开始** - 编辑有效的部分
- **不要一次做多个更改** - 一次一件事

## 故障排除

### 输出不匹配风格参考

- 参考可能太复杂 - 尝试更简洁的示例
- 要明确："Match the color palette and lighting style of the reference"
- 某些风格比其他风格更难复制

### 角色看起来不一致

- 提供更多参考照片（3-5 张不同角度）
- 具体说明识别特征
- 考虑使用专门的角色会话

### 网格单元格不一致

- 明确请求"consistent style across all cells"
- 描述应保持不变的共享元素
- 为整个网格使用风格参考

### 变体太相似

- 请求"meaningfully different creative interpretations"
- 指定要变化的不同方面："different compositions" 或 "different color palettes"
- 在 prompt 中给 Gemini 更多创作空间

## 快速参考

```
Golden Rules:
 1. Edit, don't re-roll
 2. Natural language, not tag soup
 3. Be specific and descriptive
 4. Provide context ("why" and "for whom")

Reference Images:
 - Style ref → Capture aesthetic
 - Subject ref → Maintain consistency
 - Multiple refs → Better accuracy

Grids:
 - Specify dimensions (3x3, 2x4)
 - Describe each cell
 - Request consistent style

Variants:
 - Generate 2-3 options
 - Pick the best
 - Then iterate
```

## 下一步是什么？

你知道如何编写出色的 prompt 并保持一致性。现在是时候构建一个随时间增值的系统了。

**模块 3.1.4** 教你构建风格数据库——一个可复用的风格库，可以应用到任何项目。你还将学习从网上找到的任何图像中提取风格。

交互式学习路径：输入 `/start-3-1-4`

## 资源

- [Dribbble](https://dribbble.com/) - 设计灵感，搜索要提取的风格
- [Behance](https://www.behance.net/) - 专业作品集，找到可参考的视觉风格
- [Unsplash](https://unsplash.com/) - 免费图库照片，用作参考图像

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=nano-banana-style) 获取更多 PM 构建者内容。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[3.1.2: 理解基础](https://ccforpms.com/nano-banana/understanding-basics) | [3.1.4: 构建风格数据库](https://ccforpms.com/nano-banana/style-database)
