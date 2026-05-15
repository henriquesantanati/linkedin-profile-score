# Contributing

Thanks for your interest in improving this skill. Here is how to contribute.

## How This Works

This is a Claude skill (not a traditional software project). The "code" is structured markdown that instructs an LLM how to analyze LinkedIn profiles. Changes to scoring criteria, recommendations, or output format all happen in these files:

- `SKILL.md` — main workflow and output format
- `references/scoring_rubric.md` — per-section scoring criteria (1-5 scale)
- `references/manual_checklist.md` — 7 items users check manually
- `assets/sample_report.md` — example output for calibration

## What to Contribute

**Scoring improvements:** If a scoring criterion is too strict, too lenient, or misses something recruiters care about, open an issue or PR with your reasoning.

**New sections:** If LinkedIn adds new profile features worth scoring, propose them with a weight justification.

**Output format:** If something in the report is unclear or not actionable enough, suggest a fix. Every recommendation must include exact steps the user can follow.

**CSV format changes:** LinkedIn occasionally changes export file names or column headers. If you notice a mismatch, report it.

## How to Submit Changes

1. Fork the repository
2. Create a branch: `git checkout -b improvement/your-change`
3. Make your changes
4. Test with a real LinkedIn CSV export if possible
5. Open a pull request with a clear description of what changed and why

## Guidelines

- Every recommendation in the output must be actionable (specific text to write, exact navigation path on LinkedIn).
- Scoring criteria should be based on how recruiters actually use LinkedIn (search filters, keyword matching, ATS behavior), not personal preference.
- Keep the tone direct. No filler words, no clapping for things that are already good.
- The skill should work with any LLM that supports markdown instructions (Claude, GPT, Gemini, etc.).

## Reporting Issues

Open a GitHub issue for:
- Scoring criteria that produce unfair results
- LinkedIn CSV format changes that break parsing
- Recommendations that are outdated (LinkedIn UI changes)
- Missing sections that recruiters now care about
