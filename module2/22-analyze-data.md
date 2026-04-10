# 2.2: 数据分析

- **完成时间：** 60-75 分钟

- **前置要求：** 模块 2.1（编写 PRD），对 CSV 文件和产品指标有基本了解

**在 Claude Code 中开始本模块：** 运行 `/start-2-2` 启动交互式体验。

## 概述

模块 2.2 教授数据驱动功能开发的完整 PM 工作流程：通过数据分析发现问题、在构建前估算业务影响、分析实验结果以做出发布/终止决策。

**核心要点：** 永远不要止步于顶层指标 - 始终按目标客户细分，检查质量而非数量，寻找能预测长期成功的领先指标。

## 三阶段工作流程

| 阶段 | 目的 | 产出物 |
|---|---|---|
| **发现** | 用数据发现问题（漏斗 + 调研） | 包含定量和定性证据的 `problem-analysis.md` |
| **影响估算** | 构建 ROI 模型以论证工程投入 | 包含 3 种场景的 `impact-estimate.md` 和 `roi-scenarios.md` |
| **实验分析** | 分析 A/B 测试结果，超越顶层指标 | 包含发布/迭代/终止建议的 `experiment-readout.md` |

## 影响估算框架

### 公式

```
Impact = Users Affected × Current Action Rate × Expected Lift × Value per Action
```

### 组成要素

**受影响用户 (Users Affected)**

- 有多少用户会看到这个功能？

- 考虑逐步发布（不总是 100%）

- 示例：5,000 注册/月 × 70% 看到功能 = 3,500 受影响用户

**当前行动率 (Current Action Rate)**

- 当前有多少百分比会执行期望的操作？

- 从分析工具获取（Mixpanel、Amplitude）

- 示例：45% 激活率（4,500 人中有 2,025 完成首个任务）

**预期提升 (Expected Lift)**

- 功能会将比率提升多少？

- 来源：你发布过的类似功能、竞品基准、用户研究、专家判断

- 示例：调研显示 60% 流失是因为"需要示例"。保守估计挽回 30% → 预估 13pp 提升（45% → 58%）

**单次行动价值 (Value per Action)**

- 每个增量行动值多少钱？

- 激活：LTV × 转化率

- 留存：延长 LTV

- 病毒传播：邀请接受率 × 激活率 × 转化率 × LTV

- 示例：激活用户 → 60% 转化 × $12/月 × 24 个月 = $172.80 LTV/激活

### 三场景方法

始终用悲观、现实和乐观三种场景来模拟不确定性：

| 场景 | 采用率 | 提升 | 使用场景 |
|---|---|---|---|
| **悲观**（第 20 百分位） | 30% | 45% → 50% | 最低预期影响 |
| **现实**（第 50 百分位） | 70% | 45% → 58% | 最可能的情况 |
| **乐观**（第 80 百分位） | 90% | 45% → 62% + 留存提升 | 最佳情况 |

**向领导层展示所有三种场景**，让他们了解结果范围并做出明智的决策。

## 实验分析框架

### 分析层次

**1. 顶层指标**

```
Calculate overall activation rates for control and treatment
```

- 快速了解整体影响

- 不足以做出决策

**2. 统计显著性**

```
Calculate statistical significance between control and treatment groups
```

- p < 0.05：统计显著（随机概率 < 5%）

- 95% CI：合理效应量范围

- 宽 CI = 高不确定性，即使 p < 0.05

**3. 细分分析**

```
Segment the experiment results by company_size and calculate activation rates for each segment
```

- 功能对不同用户类型效果不同

- 顶层平均值可能掩盖细分群体的成功

- 决策前始终按目标客户细分

**4. 质量指标**

```
Among activated users, calculate week 1 retention for both cohorts
```

- 激活率 = 多少用户激活了

- 留存率 = 这些是否是优质激活

- 检查：首周留存、参与度指标、长期留存

**5. 领先指标**

```
Compare template usage and invite rates between cohorts
```

- 功能采用：用户是否使用了新功能？

- 病毒指标：用户是否邀请了队友？

- 参与深度：用户是否使用了高级功能？

- 领先指标预测未来成功

## Claude Code 数据分析

### Claude 能做什么

**直接读取 CSV 文件：**

```
Read activation-funnel-q4.csv and calculate drop-off rates at each step
```

**瞬间处理数千行数据：**

```
Analyze the 8,000 rows in onboarding-experiment-results.csv and segment
activation rates by company size
```

**构建 ROI 模型：**

```
Build an impact estimation model using the framework in
impact-estimation-framework.md
```

**运行统计分析：**

```
Calculate statistical significance between control and treatment groups
with p-values and confidence intervals
```

**交叉引用数据源：**

```
Analyze funnel data from activation-funnel-q4.csv and correlate with
user feedback from user-survey-responses.csv
```

### 示例 CSV 结构

**漏斗数据 (activation-funnel-q4.csv)：**

```
step,users_entered,users_completed,completion_rate,median_time_to_complete
Signup,10000,10000,1.0,0
First Task Created,10000,7200,0.72,18
First Task Completed,7200,2880,0.40,45
Invite Sent,2880,1440,0.50,24
```

**实验数据 (onboarding-experiment-results.csv)：**

```
user_id,cohort,company_size,completed_first_task,invited_teammate,tasks_completed_week_1
control_user_0001,control,5-20,True,False,4
control_user_0002,control,5-20,False,False,0
treatment_user_0001,treatment,5-20,True,True,8
```

Claude 读取这些数据并以格式化表格呈现洞察。

## 真实案例

### 发现：激活率停滞

**情况：** 激活率在 45% 停滞了 6 个月。

**分析工作流程：**

1. `Read activation-funnel-q4.csv and find the biggest drop-off` → 任务完成环节流失 60%

2. `Analyze user-survey-responses.csv and extract top complaints` → 需要示例/模板

3. 交叉引用：流失与调研反馈相关

4. 综合：创建包含定量和定性证据的 `problem-analysis.md`

**结果：** 有数据支撑的清晰问题陈述，准备好与利益相关者对齐。

### 影响估算：论证引导式新手引导

**情况：** 提议 $100k 功能（4 个工程月）。工程团队持怀疑态度，领导层要求 ROI。

**分析工作流程：**

1. `Analyze taskflow-usage-data-q4.csv to calculate current activation rate` → 45% 基线

2. 根据调研数据估算提升（60% 需要示例 → 保守估计挽回 30% → 13pp 提升）

3. `Build complete ROI model with baseline, projections, and business impact`

4. `Generate pessimistic, realistic, and optimistic scenarios`

**结果：** 3 年 9.4x ROI（现实情况），即使在悲观情况下也有 2.6x。项目获批。

### 实验分析：揭示隐藏的成功

**情况：** 顶层显示 45% → 48%（+2.6pp，p=0.04）。团队感到失望。

**分析工作流程：**

1. 检查顶层 → 微小 +2.6pp

2. `Segment results by company_size` → 小团队：+11.4pp（巨大！），企业：-3.5pp（负面）

3. `Among activated users, calculate week 1 retention` → 实验组：78% vs 对照组：60%

4. `Compare template usage and invite rates` → 模板使用高 3.2 倍，邀请率 35% vs 12%

**结果：** 看起来失败的实验对目标细分群体是巨大成功。发布给小团队，排除企业用户。

## 最佳实践

### 分析方法

**应该做：**

- 构建前始终用数据验证假设

- 每个估算都创建三种场景（承认不确定性）

- 按目标客户细分（顶层可能掩盖成功）

- 检查质量指标（留存 > 激活数量）

- 寻找预测长期成功的领先指标

- 交叉引用定量 + 定性数据

**不应该做：**

- 止步于顶层指标而不细分

- 使用单点估算（使用范围和场景）

- 假设 100% 采用（考虑逐步发布）

- 忽略负面细分群体（从发布中排除他们）

- 在检查细分和质量之前终止实验

- 过度优化提升估算（保持保守）

### 提升估算来源

**从最佳到最差：**

1. **你的历史数据** - 过去实验是最好的预测器

2. **用户研究** - 调研显示 60% 流失是因为 X → 修复 X 挽回 Y%

3. **竞品基准** - 类似功能的行业标准

4. **专家判断** - 工程/设计/PM 团队的估算

### 专业提示

**建立提升估算库** 追踪每个功能的预估 vs 实际提升。5-10 个功能后，你的估算会准确很多。

**先展示令人失望的消息** 先展示微小的顶层结果，再揭示细分群体的成功。教会利益相关者始终深入挖掘。

**自动化分析脚本** 保存漏斗分析、细分和 ROI 建模的 prompts。跨功能复用。

## 使用 CSV 数据

### 常见数据来源

| 平台 | 导出类型 |
|---|---|
| Mixpanel, Amplitude | 使用事件、漏斗 |
| Optimizely, LaunchDarkly | A/B 测试结果 |
| Qualtrics, SurveyMonkey | 调研回复 |
| Google Analytics | 流量/转化数据 |

**Claude Code 可以直接读取 CSV、TSV 和 JSON。**

### 查看 CSV 文件

**选项：**

- **Excel 或 Google Sheets** - 最适合可视化探索数据

- **VS Code** - 适合查看原始结构

- **让 Claude 读取** - Claude 以清晰的 markdown 表格格式呈现数据

**推荐：** 让 Claude 读取和分析 CSV，以格式化表格呈现结果。仅在需要验证特定数据点时查看原始 CSV。

## 问题排查

**Claude 无法读取我的 CSV 文件**

- 用 `ls` 或文件浏览器检查文件路径

- 使用正确的相对路径（如 `data/experiment-results.csv`）

- 验证文件扩展名是 `.csv` 而非 `.CSV`（某些系统区分大小写）

**结果与我在 Excel 中看到的不匹配**

- 让 Claude 逐步展示计算过程

- 验证 Claude 使用的是正确的列

- 询问：`Explain how you calculated activation rate from this CSV`

**统计显著性看起来不对**

- 检查样本量：可靠测试需要每组约 400+ 用户

- 记住：`p<0.05` 意味着"随机概率小于 5%"，不是"5% 误差"

- 宽置信区间 = 高不确定性，即使 `p<0.05`

**细分分析显示冲突结果**

- 这不是 bug - 这是洞察！

- 功能通常对目标细分群体有效，对其他群体无效

- 解决方案：发布给获胜的细分群体，排除失败的细分群体

## 关键术语

| 术语 | 定义 |
|---|---|
| **激活率 (Activation Rate)** | 完成关键操作的注册用户百分比 |
| **置信区间 (Confidence Interval)** | 真实效应量的合理值范围（如 95% CI: [0.1%, 5.1%]） |
| **漏斗分析 (Funnel Analysis)** | 追踪用户通过连续步骤以识别流失点 |
| **领先指标 (Leading Indicator)** | 预测未来成功的早期指标（如邀请率预测留存） |
| **提升 (Lift)** | 指标的改善（如激活率 45% → 58% = +13pp 提升） |
| **LTV (Lifetime Value)** | 客户整个生命周期产生的总收入 |
| **p-value** | 观察到的效应由随机因素导致的概率（`p<0.05` = 统计显著） |
| **ROI** | 产生的收入或价值除以成本（如 9.4x ROI） |
| **细分 (Segment)** | 按共同特征分组的用户子集（如公司规模、角色） |
| **顶层指标 (Topline Metric)** | 细分前的整体平均指标 |

## 下一步

你现在了解了如何分析漏斗和调研数据、构建包含场景分析的 ROI 模型，以及使用 Claude Code 作为数据分析伙伴超越顶层指标分析 A/B 测试。

**模块 2.3：** 学习 **竞品研究与战略分析** - 使用并行 agents 进行快速竞品研究并应用战略框架。

交互式学习：输入 `/start-2-3`

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。如果你对本模块或整个课程有任何反馈，请联系我！我正在为 PM 创造者建立一个通讯和社区，欢迎查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=analyze-data)。

**源代码仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[2.1: Write a PRD](https://ccforpms.com/advanced/write-prd) [2.3: Product Strategy](https://ccforpms.com/advanced/product-strategy)
