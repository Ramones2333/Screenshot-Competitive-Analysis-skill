---
description: Analyze screenshots and produce a structured competitor analysis report
argument-hint: [optional focus direction]
---

Use the following project guidance as the operating framework:

@screenshot-competitive-analysis/SKILL.md

If you need more detailed criteria or output structure, also use:

- @screenshot-competitive-analysis/references/analysis-rubric.md
- @screenshot-competitive-analysis/references/report-template.md
- @screenshot-competitive-analysis/references/example-prompts.md

Task:

- Analyze the screenshots already attached or added to the current Claude Code context.
- If the user supplied extra focus instructions, prioritize them: $ARGUMENTS
- Ground important conclusions in visible evidence from the screenshots.
- Separate visible facts from higher-level inferences.
- If the scenarios are not aligned, say so explicitly before comparing.
- If the image is blurry or incomplete, mark uncertainty instead of guessing.

Output:

- Start with 2 to 4 high-signal conclusions.
- Then provide a structured competitor analysis.
- Include a concise comparison table when appropriate.
- End with actionable recommendations.
