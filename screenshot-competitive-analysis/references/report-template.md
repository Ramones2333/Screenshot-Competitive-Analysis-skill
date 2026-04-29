# HTML Report Templates

默认使用“标准 HTML 报告”。只有当用户明确要求极简版或汇报版时，再切换其他模板。

最终交付优先保存为 `.html` 文件并提供预览链接或文件路径，不要在聊天里直接粘贴整段长 HTML。只有在无法写文件、无法提供链接，或用户明确要求内联 HTML 时，才直接输出 HTML 源码。

## 标准 HTML 报告

```html
<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>竞品分析报告：{{竞品 A}} vs {{竞品 B}}</title>
  <style>
    :root {
      color-scheme: light;
      --text: #1f2933;
      --muted: #637083;
      --line: #d8dee8;
      --surface: #ffffff;
      --soft: #f4f7fb;
      --accent: #0f6b63;
      --accent-soft: #e5f4f2;
      --risk: #9b341f;
    }

    body {
      margin: 0;
      background: #f7f8fa;
      color: var(--text);
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      line-height: 1.6;
    }

    article {
      max-width: 1120px;
      margin: 0 auto;
      padding: 40px 24px 56px;
    }

    header, section {
      background: var(--surface);
      border: 1px solid var(--line);
      border-radius: 8px;
      margin-bottom: 18px;
      padding: 24px;
    }

    h1, h2, h3 {
      margin: 0 0 14px;
      line-height: 1.25;
    }

    h1 {
      font-size: 30px;
    }

    h2 {
      font-size: 21px;
      border-bottom: 1px solid var(--line);
      padding-bottom: 10px;
    }

    h3 {
      font-size: 17px;
      color: var(--accent);
    }

    p, ul, ol {
      margin: 0 0 12px;
    }

    .meta {
      color: var(--muted);
      margin-bottom: 0;
    }

    .summary {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 12px;
      margin: 16px 0 0;
      padding: 0;
      list-style: none;
    }

    .summary li, .insight, .recommendation {
      background: var(--soft);
      border-left: 4px solid var(--accent);
      border-radius: 6px;
      padding: 14px 16px;
    }

    .info-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 12px;
    }

    .info-grid div {
      background: var(--soft);
      border-radius: 6px;
      padding: 12px 14px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 12px;
      font-size: 14px;
    }

    th, td {
      border: 1px solid var(--line);
      padding: 10px 12px;
      text-align: left;
      vertical-align: top;
    }

    th {
      background: var(--accent-soft);
    }

    .dimension {
      border-top: 1px solid var(--line);
      padding-top: 16px;
      margin-top: 16px;
    }

    .confidence {
      display: inline-block;
      border-radius: 999px;
      background: var(--accent-soft);
      color: var(--accent);
      font-size: 12px;
      padding: 2px 8px;
      margin-left: 8px;
    }

    .risk {
      color: var(--risk);
      font-weight: 600;
    }
  </style>
</head>
<body>
  <article>
    <header>
      <h1>竞品分析报告：{{竞品 A}} vs {{竞品 B}}</h1>
      <p class="meta">分析场景：{{场景}} · 素材范围：{{截图数量/页面范围}}</p>
      <ul class="summary">
        <li><strong>核心判断 1：</strong>{{可见证据支持的结论}}</li>
        <li><strong>核心判断 2：</strong>{{可见证据支持的结论}}</li>
        <li><strong>核心判断 3：</strong>{{可见证据支持的结论}}</li>
      </ul>
    </header>

    <section aria-labelledby="context">
      <h2 id="context">基础信息</h2>
      <div class="info-grid">
        <div><strong>对比对象</strong><br>{{竞品 A}}、{{竞品 B}}</div>
        <div><strong>页面/流程阶段</strong><br>{{页面或流程名称}}</div>
        <div><strong>关键假设</strong><br>{{分析所依赖的假设}}</div>
        <div><strong>信息缺口</strong><br>{{模糊、缺失或不可辨认的信息}}</div>
      </div>
    </section>

    <section aria-labelledby="comparison">
      <h2 id="comparison">七维对比总表</h2>
      <table>
        <thead>
          <tr>
            <th>维度</th>
            <th>竞品 A</th>
            <th>竞品 B</th>
            <th>判断</th>
            <th>置信度</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>功能</td><td></td><td></td><td></td><td>高/中/低</td></tr>
          <tr><td>价格</td><td></td><td></td><td></td><td>高/中/低</td></tr>
          <tr><td>用户体验</td><td></td><td></td><td></td><td>高/中/低</td></tr>
          <tr><td>设计风格</td><td></td><td></td><td></td><td>高/中/低</td></tr>
          <tr><td>增长策略</td><td></td><td></td><td></td><td>高/中/低</td></tr>
          <tr><td>商业化模式</td><td></td><td></td><td></td><td>高/中/低</td></tr>
          <tr><td>优劣势</td><td></td><td></td><td></td><td>高/中/低</td></tr>
        </tbody>
      </table>
    </section>

    <section aria-labelledby="dimensions">
      <h2 id="dimensions">分维度分析</h2>

      <div class="dimension">
        <h3>1. 功能 <span class="confidence">置信度：高/中/低</span></h3>
        <p><strong>可见事实：</strong>{{截图中直接可见的功能、入口、组件}}</p>
        <p><strong>推断：</strong>{{基于可见事实的策略判断}}</p>
        <p><strong>对业务的意义：</strong>{{对转化、留存、效率或信任的影响}}</p>
      </div>

      <div class="dimension">
        <h3>2. 价格 <span class="confidence">置信度：高/中/低</span></h3>
        <p><strong>可见事实：</strong>{{价格、优惠、会员价、划线价等可见信息}}</p>
        <p><strong>推断：</strong>{{价格锚定或促销策略}}</p>
        <p><strong>对业务的意义：</strong>{{对购买动机和理解成本的影响}}</p>
      </div>

      <div class="dimension">
        <h3>3. 用户体验 <span class="confidence">置信度：高/中/低</span></h3>
        <p><strong>可见事实：</strong>{{路径长度、CTA、表单、弹窗、默认项等}}</p>
        <p><strong>推断：</strong>{{体验取向和可能的流失点}}</p>
        <p><strong>对业务的意义：</strong>{{对效率、决策和完成率的影响}}</p>
      </div>

      <div class="dimension">
        <h3>4. 设计风格 <span class="confidence">置信度：高/中/低</span></h3>
        <p><strong>可见事实：</strong>{{色彩、信息密度、视觉层级、图文比例}}</p>
        <p><strong>推断：</strong>{{品牌感、促销感、专业感或社区感取向}}</p>
        <p><strong>对业务的意义：</strong>{{对信任、注意力和品牌感知的影响}}</p>
      </div>

      <div class="dimension">
        <h3>5. 增长策略 <span class="confidence">置信度：高/中/低</span></h3>
        <p><strong>可见事实：</strong>{{倒计时、稀缺性、社会认同、分享、返利等信号}}</p>
        <p><strong>推断：</strong>{{转化、裂变、内容种草或复购策略}}</p>
        <p><strong>对业务的意义：</strong>{{对点击、下单、传播或留存的影响}}</p>
      </div>

      <div class="dimension">
        <h3>6. 商业化模式 <span class="confidence">置信度：高/中/低</span></h3>
        <p><strong>可见事实：</strong>{{会员、广告、套餐、达人合作、高客单推荐等痕迹}}</p>
        <p><strong>推断：</strong>{{收入逻辑或平台取舍}}</p>
        <p><strong>对业务的意义：</strong>{{对变现效率和用户体验的影响}}</p>
      </div>

      <div class="dimension">
        <h3>7. 优劣势 <span class="confidence">置信度：高/中/低</span></h3>
        <p><strong>竞品 A 优点：</strong>{{为什么有效}}</p>
        <p><strong>竞品 A 风险：</strong>{{成本或副作用}}</p>
        <p><strong>竞品 B 优点：</strong>{{为什么有效}}</p>
        <p><strong>竞品 B 风险：</strong>{{成本或副作用}}</p>
      </div>
    </section>

    <section aria-labelledby="insights">
      <h2 id="insights">关键洞察</h2>
      <div class="insight">
        <h3>洞察 1：{{标题}}</h3>
        <p><strong>差异表现：</strong>{{两方在截图中的主要差异}}</p>
        <p><strong>背后逻辑：</strong>{{设计或商业策略推断}}</p>
        <p><strong>适用场景：</strong>{{最适合借鉴或规避的场景}}</p>
      </div>
      <div class="insight">
        <h3>洞察 2：{{标题}}</h3>
        <p><strong>差异表现：</strong></p>
        <p><strong>背后逻辑：</strong></p>
        <p><strong>适用场景：</strong></p>
      </div>
      <div class="insight">
        <h3>洞察 3：{{标题}}</h3>
        <p><strong>差异表现：</strong></p>
        <p><strong>背后逻辑：</strong></p>
        <p><strong>适用场景：</strong></p>
      </div>
    </section>

    <section aria-labelledby="recommendations">
      <h2 id="recommendations">策略建议</h2>
      <table>
        <thead>
          <tr>
            <th>优先级</th>
            <th>建议</th>
            <th>预期收益</th>
            <th>适用条件</th>
            <th>风险</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>P0</td><td></td><td></td><td></td><td class="risk"></td></tr>
          <tr><td>P1</td><td></td><td></td><td></td><td class="risk"></td></tr>
          <tr><td>P2</td><td></td><td></td><td></td><td class="risk"></td></tr>
        </tbody>
      </table>
    </section>
  </article>
</body>
</html>
```

## 极简 HTML 版

适合用户只想快速得到差异判断。

```html
<article class="competitive-analysis quick">
  <h1>快速对比结论</h1>
  <ul>
    <li><strong>最大差异：</strong>{{结论}}</li>
    <li><strong>谁更偏转化：</strong>{{结论与证据}}</li>
    <li><strong>谁更偏信息解释：</strong>{{结论与证据}}</li>
    <li><strong>最值得借鉴的点：</strong>{{建议}}</li>
    <li><strong>最大风险点：</strong>{{风险}}</li>
  </ul>
</article>
```

## 汇报 HTML 版

适合需要直接贴进周报或汇报材料。

```html
<article class="competitive-analysis one-page">
  <h1>一页式竞品结论</h1>
  <section>
    <h2>对比场景</h2>
    <p>{{场景与对象}}</p>
  </section>
  <section>
    <h2>结论摘要</h2>
    <ol>
      <li>{{核心结论 1}}</li>
      <li>{{核心结论 2}}</li>
      <li>{{核心结论 3}}</li>
    </ol>
  </section>
  <section>
    <h2>关键差异</h2>
    <table>
      <thead>
        <tr><th>差异点</th><th>竞品 A</th><th>竞品 B</th><th>启示</th></tr>
      </thead>
      <tbody>
        <tr><td></td><td></td><td></td><td></td></tr>
      </tbody>
    </table>
  </section>
  <section>
    <h2>机会点与建议动作</h2>
    <p>{{机会点}}</p>
    <p>{{建议动作}}</p>
  </section>
</article>
```
