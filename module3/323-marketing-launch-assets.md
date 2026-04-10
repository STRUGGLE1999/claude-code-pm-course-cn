# 3.2.3: 营销与发布资产

- **完成时间：** 20分钟
- **前置条件：** 已完成策略与架构视觉（模块 3.2.2）

**在 Claude Code 中开始本模块：** 运行 `/start-3-2-3` 开始交互式体验。

## 概述

模块 3.2.3 用营销和发布资产完善你的产品视觉工具包。应用商店图形、社交广告、发布公告——向世界介绍你产品的视觉素材。

**关键要点：** 营销视觉瞬间传达价值。一张出色的发布图形可以产生段落文字无法达到的兴奋感。

## 场景

TaskFlow Mobile 获得了批准。下个月就要发布。营销需要素材：

1. **应用商店 hero 图** - 用户在商店中看到的特色图形
2. **社交广告创意** - LinkedIn/社交平台的广告素材
3. **发布公告** - "我们来了"时刻的图形

让我们逐一构建。

## 应用商店特色图形

### 它们是什么

特色图形是用户在应用商店中看到的 hero 图像。它们是你产品的第一视觉印象。

### 各平台要求

| 平台 | 尺寸 | 备注 |
|---|---|---|
| **App Store** | 1024×1024（图标），截图多种尺寸 | 专注于应用图标和截图序列 |
| **Play Store** | 1024×500（特色图形） | 宽幅横幅格式 |
| **两者** | 多设备截图 | 展示关键功能 |

### 如何生成

**基础 prompt：**

```
Create an app store feature graphic for [app name].
Show the app on [device], highlighting [key feature/benefit].
Clean, professional style. [dimensions].
```

**示例 - TaskFlow Mobile：**

```
Create an App Store feature graphic for TaskFlow Mobile.
Show the app displayed on a modern iPhone.
The interface shows task management for operations teams.
Professional style suitable for B2B app store listing.
Subtle manufacturing/operations context in background.
16:9 aspect ratio.
```

### 关键元素

| 元素 | 用途 |
|---|---|
| **设备框架** | 展示产品是真实/可触的 |
| **UI 截图** | 演示界面 |
| **上下文** | 暗示使用场景 |
| **简洁背景** | 保持焦点在产品上 |

### 风格技巧

- **B2B 应用：** 专业、简洁、功能性感觉
- **消费者应用：** 活力、情感、生活化焦点
- **企业级：** 可信赖、安全、精致
- **初创公司：** 现代、创新、清新

### 专业提示

- **展示真实价值：** 展示你最好的 UI，不是通用屏幕
- **匹配品牌颜色：** 使用你公司的色调
- **保持简单：** 每张图形一个清晰信息
- **生成变体：** 测试不同方法

## 社交广告创意

### 它们是什么

社交广告创意是设计用来在信息流中让人停下并瞬间传达价值的图像。它们针对信息流性能优化。

### 平台规格

| 平台 | 推荐尺寸 | 备注 |
|---|---|---|
| **LinkedIn** | 1200×627（横版），1080×1080（正方形） | 专业 B2B 受众 |
| **Twitter/X** | 1200×675（横版），1080×1080（正方形） | 快速互动 |
| **Facebook/Instagram** | 1080×1080（正方形），1080×1350（竖版） | 视觉优先平台 |

### 如何生成

**基础 prompt：**

```
Create a social ad for [product].
Message: [key value proposition]
Style: [visual approach]
Include space for headline text.
[dimensions]
```

**示例 - TaskFlow Mobile：**

```
Create a LinkedIn ad for TaskFlow Mobile.
Show a before/after transformation:
- Left side: Overwhelmed operations manager with clipboard, scattered papers
- Right side: Same manager confidently using TaskFlow Mobile

Message: From chaos to clarity. Bold, attention-grabbing style.
Leave space at top for headline text. Square format (1:1).
```

### 广告创意模式

| 模式 | 描述 | 最适合 |
|---|---|---|
| **前后对比** | 问题状态 → 解决方案状态 | 转型故事 |
| **产品 Hero** | 设备/界面居中 | 功能公告 |
| **生活方式** | 用户在上下文中 | 情感连接 |
| **数据/统计** | 带视觉冲击的数字 | 建立可信度 |
| **证言** | 带人物的引言 | 社会证明 |

### 专业提示

- **1 秒内吸引注意：** 图像必须瞬间传达价值
- **留文字空间：** 标题会被添加；不要拥挤图像
- **使用对比：** 在充满内容的信息流中脱颖而出
- **生成多个变体：** A/B 测试是标准做法

## 发布公告图形

### 它们是什么

发布公告图形是"我们来了"的视觉素材。它们出现在博客文章、邮件群发、社交公告、新闻稿——所有你宣布发布的地方。

### 何时使用

- 产品发布日
- 重大功能发布
- 版本更新
- 里程碑公告

### 如何生成

**基础 prompt：**

```
Create a launch announcement graphic for [product].
Concept: "Introducing [product name]"
Feel: [emotional tone]
Professional quality suitable for press release.
16:9 aspect ratio.
```

**示例 - TaskFlow Mobile：**

```
Create a launch announcement graphic for TaskFlow Mobile.
Concept: "Introducing TaskFlow Mobile" energy.
Hero shot of the app - polished, premium feel.
Launch/announcement energy - could be spotlight effect,
subtle motion, or clean reveal aesthetic.
Professional enough for press release, exciting enough for social.
16:9 aspect ratio.
```

### 关键元素

| 元素 | 用途 |
|---|---|
| **产品 hero** | 正在发布的产品 |
| **公告能量** | 兴奋感、新颖感、势头 |
| **文字空间** | "Introducing..." 标题的位置 |
| **品牌对齐** | 公司颜色和风格 |

### 情绪选项

| 情绪 | 视觉方法 |
|---|---|
| **激动人心** | 动态模糊、动态角度、明亮颜色 |
| **高端** | 简洁、极简、精致光线 |
| **创新** | 未来感、科技前沿、大胆 |
| **可信赖** | 稳定、专业、令人安心 |

### 专业提示

- **让它感觉像一个事件：** 这不仅仅是一张普通图形
- **产品居中：** Hero 应该无可争议
- **生成多个版本：** 不同平台需要不同格式
- **考虑文字叠加：** 为标题和日期留空间

## 完整发布素材包

这是一套完整的产品发布素材：

### 应用商店展示

- 特色图形（16:9）
- 5-6 张截图模型
- 应用图标（如需要）

### 社交活动

- LinkedIn 广告创意（正方形 + 横版）
- Twitter/X 卡片图像
- Instagram 帖子 + 故事变体

### 公告包

- 新闻稿 hero 图（16:9）
- 邮件头图
- 博客文章特色图
- 社交公告变体

**总时间：** 完整发布包 30-45 分钟。

## 使用你的风格库

营销受益于一致的视觉识别。

**构建营销专用风格：**

- "Brand Ad Style" - 你公司的视觉语言
- "Launch Energy" - 动态公告感
- "App Store Clean" - 商店列表美学

**然后一致地应用：**

```
Generate LinkedIn ad using style #45 (Brand Ad Style)
Generate announcement using style #52 (Launch Energy)
```

## 最佳实践

### 应该做的：

- **匹配你的品牌** - 使用一致的颜色和风格
- **专注于价值** - 用户得到什么？
- **生成变体** - 营销需要测试
- **平台优先思考** - 针对展示位置优化
- **保持简单** - 每张图形一个信息

### 不应该做的：

- **不要过度拥挤** - 留呼吸空间
- **不要使用通用素材** - 展示你的产品，不是图库图像
- **不要忘记文字空间** - 文案会被添加
- **不要使用微小文字** - 移动信息流很小
- **不要跳过变体** - 一个版本永远不够

## 故障排除

### 广告无法让人停下

- 增加对比度和大胆度
- 尝试更情感化的概念
- 让转型更戏剧化
- 生成完全不同的变体

### 应用商店图形看起来普通

- 展示实际 UI，不是占位屏幕
- 添加暗示使用场景的上下文
- 明确参考你的品牌颜色
- 尝试生活方式方法（产品在使用中）

### 发布公告感觉不激动

- 请求 "launch energy" 或 "announcement moment"
- 添加动态元素（动态模糊、聚光灯）
- 让产品更突出
- 生成不同情绪的变体

## 更大的图景

让我们退后一步看看。

### 你构建了什么

通过 Nano Banana，你组装了一个专业的创意流水线：

**1. 最强大的图像模型**
Gemini 3 Pro 生成逼真图像、转换参考、处理文字叠加，并在多次生成中保持一致性。

**2. 最强大的 AI 助手**
Claude Code 处理所有技术复杂性——API 调用、会话管理、文件保存。你专注于创意方向。

**3. 一个增值系统**
你的风格库随每个项目增长。曾经需要探索的工作现在只需要一条命令："use style #12."

### 差异

大多数人将 AI 图像工具作为新奇事物使用：

- 生成随机图像
- 使用一次
- 重新开始

你拥有专业的流水线：

- 有意图地生成
- 构建可复用风格
- 随时间增值

这就是偶尔使用 AI 和将 AI 作为创意超能力之间的区别。

## 课程完成

恭喜。你已完成 Nano Banana。

从你的第一次"穿着香蕉装的 Carl"生成到用专业营销资产发布产品——你从"这是怎么工作的？"到拥有完整的视觉工具包。

**你现在拥有：**

- 对可用最强大图像模型的理解
- 获得优秀结果的 prompt 原则掌握
- 随时间增值的可复用风格库
- 创建任何 PM 视觉的技能：人物画像、图表、模型、营销

**你的风格库永远属于你。** 继续构建它。每个项目都让它更有价值。

## 下一步是什么？

这是 Nano Banana 的最后一个模块。但你的旅程仍在继续：

**继续构建你的库：**

- 从每个项目保存风格
- 从你欣赏的图像中提取风格
- 与团队分享风格

**应用于实际工作：**

- 演示文稿和展示
- 用户研究工件
- 产品文档
- 营销活动

**保持联系：** 查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=nano-banana-marketing) 获取更多 PM 构建者内容，包括高级技术和新风格库。

**恭喜完成 Nano Banana！**

现在去创造一些精彩的东西吧。

## 资源

- [Hootsuite Social Media Image Sizes](https://blog.hootsuite.com/social-media-image-sizes-guide/) - 所有平台，定期更新
- [Sprout Social Image Guide](https://sproutsocial.com/insights/social-media-image-sizes-guide/) - 全面规格
- [App Store Screenshot Guide](https://splitmetrics.com/blog/app-store-screenshots-aso-guide/) - Apple 要求和最佳实践
- [Google Play Screenshot Guide](https://appradar.com/blog/android-app-screenshot-sizes-and-guidelines-for-google-play) - Android 要求
- [App Screenshot Best Practices](https://www.moburst.com/blog/app-screenshots/) - 设计技巧

---

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。Nano Banana 是 Claude Code for Product Managers 课程的一部分。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[3.2.2: 策略与架构视觉](https://ccforpms.com/nano-banana/strategy-architecture-visuals) | [模块概览](https://ccforpms.com/vibe-coding)
