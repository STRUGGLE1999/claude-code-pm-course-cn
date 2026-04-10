# 3.2.1: 用户与产品视觉

- **完成时间：** 25分钟
- **前置条件：** 已完成模块 3.1（已构建风格数据库）

**在 Claude Code 中开始本模块：** 运行 `/start-3-2-1` 开始交互式体验。

## 概述

模块 3.2.1 将你的图像生成技能应用于真正的 PM 交付物。你将创建产品演示所需的视觉素材：人物画像、用户旅程图、线框图、设备模型和 hero 图像。

**关键要点：** 这些技术适用于任何演示或展示。一旦你能生成这五种素材类型，你几乎可以视觉化传达任何产品故事。

## 场景

在整个模块 3.2 中，你是 TaskFlow（课程的虚构 B2B SaaS 公司）的 PM。你正在演示 **TaskFlow Mobile**——一款面向制造业运营经理的新移动应用。

你的演示文稿需要：

1. **人物画像** - "我们在为谁构建？"
2. **用户旅程图** - "我们要解决什么问题？"
3. **线框图** - "解决方案长什么样？"
4. **设备模型** - "拿在手里的感觉如何？"
5. **Hero 图像** - "愿景是什么？"

让我们逐一构建。

## 人物画像

### 它们是什么

人物画像为你的目标用户赋予面孔。它们让抽象的用户群体感觉真实，帮助利益相关者与你为之构建的人产生共鸣。

### 何时使用

- 演示文稿中的"谁"幻灯片
- 用户研究报告
- PRD 人物画像部分
- 团队对齐文档

### 如何生成

**基础 prompt：**

```
Create a persona portrait of [name], a [role] at [company type].
[Age range], [key characteristics]. Professional but approachable.
For a pitch deck.
```

**示例 - Marcus Chen：**

```
Create a persona portrait of Marcus Chen, an operations manager
at a manufacturing plant. Mid-40s, practical, confident but
approachable expression. Wearing work-appropriate attire -
polo shirt, maybe a safety vest. Natural lighting.
For a pitch deck to leadership.
```

### 风格选项

| 风格 | 最适合 | Prompt 示例添加 |
|---|---|---|
| **照片级真实** | 高管演示 | "Photorealistic, professional headshot quality" |
| **插画风格** | 友好/随意场合 | "Illustrated in a modern flat style" |
| **风格化** | 品牌特定需求 | 参考你的风格库 |

### 专业提示

- **添加上下文线索：** 包含环境提示（工厂车间、办公室等）
- **匹配基调：** 高管演示 = 更正式；团队 wiki = 更随意
- **保持一致：** 如果你有多个画像，对所有使用相同风格

## 用户旅程图

### 它们是什么

用户旅程图可视化用户随时间的体验——过程中的步骤、触点、痛点和情绪。

### 何时使用

- 问题定义幻灯片
- 用户研究发现
- 解决方案框架
- 利益相关者对齐

### 如何生成

**基础 prompt：**

```
Create a journey map showing [user]'s [process/workflow].
Stages: [list stages]. Show pain points at each stage.
Clean, presentation-ready, 16:9 aspect ratio.
```

**示例 - Marcus 的早晨：**

```
Create a journey map showing an operations manager's morning workflow.
Stages: Arrive (6am) → Review backlog → Morning standup → Floor walk → Handoff prep.
Show pain points: scattered information, manual tracking, delayed updates.
Clean visual style suitable for a pitch deck. 16:9 aspect ratio.
```

### 风格选项

| 风格 | 最适合 |
|---|---|
| **极简** | 高管演示 |
| **手绘** | 工作坊/协作感 |
| **信息图** | 营销/外部使用 |
| **详细** | 深入演示 |

### 专业提示

- **包含情绪：** 每个阶段的开心/沮丧表情增加冲击力
- **突出痛点：** 红色区域或图标吸引注意力到问题
- **保持可扫描：** 最多 5-7 个阶段；细节放在支持文档中

## 线框图转换

### 它是什么

将粗糙草图转换为精美的线框图。这非常适合将会议白板草图变成演示就绪的版本。

### 何时使用

- 头脑风暴会议后
- 早期设计评审
- 快速概念验证
- 当你没有设计师可用时

### 如何生成

**基础 prompt：**

```
Transform this hand-drawn sketch into a clean, polished wireframe.
Keep the same layout and elements. Professional quality with
clean lines and consistent spacing.
```

提供你的粗糙草图作为参考图像。

**示例：**

```
Transform this hand-drawn wireframe into a polished mobile app wireframe.
Preserve the layout: header with greeting, task list, shift overview,
bottom navigation. Clean, professional, grayscale with good typography.
Mobile aspect ratio (9:16).
```

### 草图中应包含什么

即使是粗糙草图也应显示：

- 整体布局结构
- 关键 UI 元素（标题、按钮、列表）
- 内容层次
- 导航模式

Gemini 会清理视觉效果，同时保留你的布局决策。

### 专业提示

- **保持草图清晰：** Gemini 需要理解你的意图
- **标注元素：** 在草图中写文字，让 Gemini 知道什么放在哪里
- **指定保真度：** "Low-fi wireframe" vs "high-fidelity mockup"

## 设备模型

### 它们是什么

设备模型将你的线框图或截图放入手机/笔记本电脑框架中。它们让数字产品感觉真实可触。

### 何时使用

- 应用商店预览图
- 演示文稿产品幻灯片
- 营销材料
- 社交媒体公告

### 如何生成

**基础 prompt：**

```
Place this wireframe into a [device] mockup.
Clean background, slight shadow for depth.
Professional, presentation-ready.
```

提供你的线框图作为参考图像。

**示例：**

```
Put this mobile wireframe into an iPhone 15 Pro mockup.
Clean white background with subtle shadow.
Slight 3D angle to show depth. Professional quality.
```

### 设备选项

| 设备 | 最适合 |
|---|---|
| **iPhone** | 移动应用演示 |
| **Android** | 跨平台或 Android 优先 |
| **MacBook** | Web 应用、仪表板 |
| **iPad** | 平板体验 |
| **多设备** | 响应式设计展示 |

### 专业提示

- **匹配上下文：** iPhone 用于消费者，MacBook 用于企业
- **使用当前设备：** 最新型号感觉更高端
- **考虑角度：** 平面用于清晰，倾斜用于动感
- **添加上下文：** 手持设备增加真实感

## 生活场景照

### 它们是什么

生活场景照展示你的产品在真实世界中的使用。它们是销售愿景的"hero 图像"——一个人在其自然环境中使用你的产品。

### 何时使用

- 演示文稿封面
- 落地页
- 营销 hero 图像
- 社交媒体公告

### 如何生成

**基础 prompt：**

```
A [persona] using [product] in [environment].
[Specific details about context]. Natural lighting.
Composition suitable for [use case].
```

**示例：**

```
Marcus, an operations manager in his mid-40s, using TaskFlow Mobile
on the factory floor. He's holding his phone confidently, reviewing
task updates. Manufacturing environment in the background - equipment,
workers, industrial setting. Natural lighting from warehouse windows.
Composition works as a pitch deck hero image.
```

### 构图技巧

| 元素 | 指导 |
|---|---|
| **主体位置** | 三分法；如需要为文字叠加留空间 |
| **背景** | 相关但不分散注意力；增加上下文 |
| **光线** | 自然光通常感觉更真实 |
| **表情** | 应匹配故事（自信、专注、满意） |

### 专业提示

- **使用画像一致性：** 在所有图像中生成相同的 "Marcus"
- **匹配环境：** 办公室用于 B2B SaaS，家用于消费者应用
- **留文字空间：** 如果是 hero 图像，为标题留空间
- **生成变体：** 尝试不同构图并选择最好的

## 完整演示文稿示例

以下是所有五种素材如何为 TaskFlow Mobile 演示协同工作：

### 幻灯片 1：Hero

**素材：** Marcus 在工厂车间使用 TaskFlow Mobile 的生活场景照
**故事：** "这是我们正在构建的未来"

### 幻灯片 2：用户

**素材：** Marcus Chen 的人物画像
**故事：** "认识 Marcus——我们的目标用户"

### 幻灯片 3：问题

**素材：** Marcus 混乱早晨的用户旅程图
**故事：** "他当前的工作流是破碎的"

### 幻灯片 4：解决方案

**素材：** TaskFlow Mobile 的精美线框图
**故事：** "这是我们正在构建的"

### 幻灯片 5：愿景

**素材：** 设备模型（带有线框图的 iPhone）
**故事：** "口袋中的任务管理"

**总时间：** 所有五种素材 15-20 分钟。

## 使用你的风格库

还记得模块 3.1.4 中的风格库吗？它在这里大放异彩。

**保持一致性：**

```
Generate Marcus persona portrait using style #12
Generate journey map using style #15
```

**探索选项：**

```
Show me all persona styles in my library
Generate Marcus using style #12, #15, and #18 as variants
```

你构建的风格越多，这变得越快。

## 最佳实践

### 应该做的：

- **在演示文稿中匹配风格** - 一致性看起来专业
- **使用 TaskFlow 上下文** - 或你真实公司的上下文
- **先用 1K 生成** - 迭代，然后最终版本用 2K
- **保存好的风格** - 添加到你的库中
- **生成变体** - 特别是对于 hero 图像

### 不应该做的：

- **不要混合差异很大的风格** - 看起来不专业
- **不要跳过迭代** - 初稿很少是最终版本
- **不要过度细化线框图** - 它们应该感觉像线框图
- **不要忘记上下文** - 告诉 Claude 它是做什么用的

## 故障排除

### 画像不匹配描述

- 更具体地描述年龄、表情、着装
- 提供你想要的"类型"的参考图像
- 尝试："NOT a stock photo feeling, more natural and authentic"

### 用户旅程图太复杂

- 减少到最多 5-6 个阶段
- 请求 "simplified, high-level view"
- 将详细的旅程保存到单独的深入幻灯片

### 线框图看起来太精美

- 明确请求 "low-fidelity wireframe"
- 请求 "grayscale only, no polish"
- 指定 "sketch-like, not final design"

### 设备模型看起来假

- 请求 "photorealistic device frame"
- 添加上下文："slight shadow and reflection"
- 尝试不同角度

## 下一步是什么？

你已掌握用户和产品视觉。接下来：用于利益相关者会议的策略和架构图。

**模块 3.2.2** 涵盖系统架构图、优先级矩阵和产品路线图——CTO、CEO 和董事会会议的视觉素材。

交互式学习路径：输入 `/start-3-2-2`

## 资源

- [Figma Journey Map Template](https://www.figma.com/community/file/1167700722702284382/journey-map-template) - 免费模板参考
- [UXPressia Templates](https://uxpressia.com/templates) - 用户旅程图和人物画像模板
- [Journey Map Examples](https://www.uxtweak.com/user-journey-map/examples/) - 不同风格的灵感
- [Smashing Magazine: Journey Map Templates](https://www.smashingmagazine.com/2024/07/customer-journey-maps-figma-miro-templates/) - 精选合集

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=nano-banana-users) 获取更多 PM 构建者内容。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[3.1.4: 构建风格数据库](https://ccforpms.com/nano-banana/style-database) | [3.2.2: 策略与架构视觉](https://ccforpms.com/nano-banana/strategy-architecture-visuals)
