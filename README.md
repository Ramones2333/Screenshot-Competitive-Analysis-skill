# Screenshot Competitive Analysis Skill

处理多张截图的竞品分析，输出七维对比表、关键洞察和策略建议。

This repository packages the workflow in a way that can be reused across multiple AI tools:

- Codex skill
- Claude Code project command
- Gemini CLI project command
- Generic prompt pack for other AI tools

## What It Does

This skill is designed for screenshot-driven competitor analysis. It is useful when someone provides one or more screenshots and wants:

- 竞品分析
- 页面差异分析
- 样式对比
- 基于截图输出结构化报告
- A report-ready comparison of product UI, ad creatives, detail pages, onboarding flows, and reporting dashboards

The default output is a structured report with:

- 七维对比总表
- 分维度分析
- 关键洞察
- 可执行策略建议

## Repository Structure

```text
.
├── .claude/commands/competitive-analysis.md
├── .gemini/commands/competitive-analysis.toml
├── LICENSE
├── README.md
├── prompts/
│   └── generic-competitive-analysis.md
└── screenshot-competitive-analysis/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
        ├── analysis-rubric.md
        ├── example-prompts.md
        └── report-template.md
```

## Tool Compatibility

### 1. Codex

Install the `screenshot-competitive-analysis` folder into `~/.codex/skills/`, or use the Codex skill installer:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo Ramones2333/Screenshot-Competitive-Analysis-skill \
  --path screenshot-competitive-analysis
```

Then restart Codex.

### 2. Claude Code

Anthropic documents project slash commands under `.claude/commands/`. This repo includes:

- `.claude/commands/competitive-analysis.md`

After cloning the repo, open it in Claude Code and run:

```text
/competitive-analysis
```

You can also pass a focus direction:

```text
/competitive-analysis 重点看转化策略和信息架构
```

Reference: Anthropic’s official Claude Code docs describe project commands in `.claude/commands/`.

### 3. Gemini CLI

Google documents project custom commands under `.gemini/commands/`. This repo includes:

- `.gemini/commands/competitive-analysis.toml`

After opening the repo in Gemini CLI, run:

```text
/competitive-analysis
```

Or with optional focus instructions:

```text
/competitive-analysis focus on pricing and CTA strategy
```

If Gemini CLI does not immediately detect new commands, run `/commands reload`.

Reference: Google’s Gemini CLI documentation describes project commands in `.gemini/commands/`.

### 4. Other AI Tools

For tools that do not support a native skill or command format, use:

- `prompts/generic-competitive-analysis.md`

Paste that prompt into ChatGPT, Cursor, DeepSeek, or other assistants together with the screenshots and any desired focus.

## Best-Fit Use Cases

- Ad creative comparison
- Product detail page benchmarking
- Onboarding flow comparison
- Checkout or lead funnel analysis
- Dashboard/reporting page competitor analysis
- Version A vs Version B screenshot analysis

## Example Requests

- 帮我分析这两张截图，做一个竞品对比。
- 看看这两个商详页在价格锚定和 CTA 上有什么差异。
- 基于这些广告卡片截图，输出一份汇报版竞品分析。
- Compare these two dashboard screenshots and explain which one is better for operators versus managers.

## Notes

- The analysis is evidence-first. Conclusions should be grounded in what is visible in the screenshots.
- When the screenshot quality is poor or the scenario is not aligned, the output should state its assumptions and uncertainty.
- This repository does not depend on any external API or service.

## License

MIT. See [LICENSE](./LICENSE).
