---
name: screenshot-competitive-analysis
description: |
  Analyze one or more competitor screenshots and generate structured visual benchmarking reports for product UI, ad creatives, detail pages, onboarding flows, checkout journeys, and campaign assets.

  Use when the user provides screenshots and asks to compare products, analyze differences, benchmark features or UX, infer growth and commercialization strategies, or produce a report-ready competitor analysis from visual evidence.

  Also use when the user asks in Chinese for 竞品分析, 截图对比, 页面差异分析, 广告样式对比, 商详页对标, or 基于截图输出分析报告.

  Prefer this skill for screenshot-driven product analysis and side-by-side comparison. Do not use it for OCR-only extraction, simple translation, pixel-perfect QA, or implementation/code-generation tasks.
metadata:
  short-description: Compare screenshots and output structured competitor analysis reports
effort: medium
---

# Screenshot Competitive Analysis

把这份 skill 当作“基于视觉证据的竞品分析工作流”。目标不是泛泛点评截图，而是把截图中的可见事实整理成可汇报、可复用、可落地的竞品分析结论。

## 适用范围

适合以下输入：

- 多张竞品截图的横向对比
- 同一流程不同产品的多步截图
- 同一产品不同版本、不同样式的前后对比
- 广告卡片、落地页、商详页、首页、下单链路、会员页、活动页等界面分析

以下情况不要强行使用本 skill：

- 用户只是要提取图片文字或翻译图片内容
- 用户只要做视觉还原、前端实现或像素级走查
- 截图信息极少，且无法支撑“竞品分析”结论

## 在 Codex 中如何处理输入

如果用户提供的是本地截图文件：

- 优先逐张查看图片本身，而不是只看文件名
- 保留用户给出的顺序；如果用户未说明顺序，再按文件名、时间或流程线索排序

如果用户提供的是会话里直接附带的图片：

- 把附图本身当作一手证据
- 不要把用户的描述当成唯一事实来源
- 当图片数量超过 2 张时，先建立分组，再开始正式比较

如果用户一次给了很多截图：

- 先按“产品 / 场景 / 流程步骤”分组
- 再判断哪些截图是真正可比的一组
- 不要把不同流程阶段的页面直接拉到同一维度里硬比

如果图上存在看不清的区域：

- 明确标注“文字不可辨认”或“该区域信息不足”
- 不要为了凑结论而臆测按钮文案、价格数字或规则细节

## 核心原则

### 1. 证据先于判断

每个重要结论都要能回到截图中的可见证据，例如：

- 信息层级
- CTA 位置与数量
- 价格展示方式
- 社会认同或稀缺性文案
- 页面结构与流程复杂度

### 2. 区分“看见了什么”与“推断了什么”

输出时尽量区分两层：

- 可见事实：截图里直接能看到的元素和布局
- 推断结论：基于这些元素推断的增长逻辑、商业化策略或体验意图

如果是推断，请用“可能”“倾向于”“更像是在”这类表述控制确定性。

### 3. 场景对齐比维度堆砌更重要

只有在场景对齐时，七维分析才有价值。例如：

- 广告卡片对广告卡片
- 商详页对商详页
- 下单流程第 2 步对下单流程第 2 步

如果场景不对齐，先说明限制，再做“部分对比”。

## 推荐工作流

### Step 1: 识别比较拓扑

先判断用户给的是哪种比较关系：

- 同场景、不同竞品
- 同竞品、不同版本
- 同目标、不同设计策略
- 同流程、多步骤拆解

这一步决定后面应该做“横向比较”“流程比较”还是“策略拆解”。

### Step 2: 建立素材清单

为每张图补充最小识别信息：

- 竞品名称
- 页面/模块名称
- 所属流程阶段
- 主要目标
- 可辨识度与信息完整度

如果名称无法确认，可以暂时用“竞品 A / 竞品 B / 截图 1 / 截图 2”代称，但要保持全文一致。

### Step 3: 提取显性信号

先提取肉眼可见、最稳定的信号：

- 页面结构：单列、多列、瀑布流、卡片、弹层、全屏
- 视觉重心：首屏主卖点、主图、价格、福利、CTA
- 信息密度：一屏内信息多少，是否需要滑动理解
- 交互负担：步骤数、选择项、表单量、弹窗打断
- 转化杠杆：优惠、倒计时、销量、评价、达人、直播、包邮、赠品

### Step 4: 做七维分析

按以下维度整理对比：

- 功能
- 价格
- 用户体验
- 设计风格
- 增长策略
- 商业化模式
- 优劣势

维度判断细则见 [analysis-rubric.md](./references/analysis-rubric.md)。

### Step 5: 提炼关键洞察

洞察不是重复表格，而是回答“为什么它这么设计”与“这对结果意味着什么”。优先提炼：

- 设计差异背后的策略取向
- 不同路径对应的目标人群或场景
- 哪一方更偏转化效率，哪一方更偏信息解释
- 哪些设计可能提升点击、下单、停留或信任

### Step 6: 输出建议

建议要满足三个条件：

- 能被执行，而不是空泛评价
- 明确优先级
- 对应可落地场景

如果用户没要求超长报告，默认输出“标准报告”；模板见 [report-template.md](./references/report-template.md)。

## 缺信息时怎么处理

如果缺失信息不会改变分析方向，直接做并说明假设：

- 未知竞品名称
- 未知准确流程顺序
- 部分区域模糊

如果缺失信息会显著改变结论，再问一个最关键的问题，例如：

- “这几张图是在同一个流程阶段吗？”
- “你更想看广告转化策略，还是页面体验差异？”

除非风险很高，不要连续追问。

## 输出要求

默认输出应包含：

- 对比对象与场景定义
- 关键假设与信息缺口
- 七维对比总表
- 分维度分析
- 3 条以内关键洞察
- 按优先级排序的策略建议

输出时遵守以下规则：

- 先结论，后展开
- 表格尽量简洁，不要写成长段落
- 重要判断给出依据
- 区分高置信度结论和低置信度推断

## 常见触发说法

以下说法应优先触发本 skill：

- “帮我对比这几张竞品截图”
- “分析一下抖音和快手这个页面有什么区别”
- “基于这些广告卡片做个竞品分析”
- “看看这几个商详页的转化策略差异”
- “把这几张截图整理成一份竞品报告”

更多示例提示见 [example-prompts.md](./references/example-prompts.md)。

## 结束前自检

交付前确认：

- 对比对象是否真的可比
- 结论是否来自截图证据，而不是想象
- 是否明确说明了模糊区域和假设
- 是否输出了可执行建议，而不只是优缺点罗列
