# LinkedIn Profile Score

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Latest Release](https://img.shields.io/github/v/release/henriquesantanati/linkedin-profile-score)](https://github.com/henriquesantanati/linkedin-profile-score/releases)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)

> Scoring criteria inspired by [Nicole Barra's guide on LinkedIn profile optimization](https://www.linkedin.com/pulse/optimizing-your-linkedin-profile-international-guide-nicole-barra--ujebf/).

A skill that audits your LinkedIn profile and produces a score with actionable recommendations to improve recruiter visibility and hiring chances. Analyzes your exported LinkedIn data (native CSV format) against recruiter search behavior, keyword optimization best practices, and credibility signals. Produces a 0-100 score with per-section breakdown and specific fixes ranked by impact.

## How It Works

1. Export your LinkedIn data (Settings → Data Privacy → Download your data)
2. Select "Download larger data archive" and wait for the email (24-72h)
3. Unzip the downloaded file
4. Point this skill at the unzipped folder containing the CSV files
5. Receive your score, section-by-section analysis, and prioritized improvements

The skill reads LinkedIn's native CSV export directly.

## Installation

### Claude Code

Clone this repository and register it as a skill:

```bash
git clone https://github.com/henriquesantanati/linkedin-profile-score.git
```

Then in Claude Code, add the skill path to your project configuration.

### Claude.ai (Projects)

1. Download this repository as a ZIP
2. In your Claude Project, upload `SKILL.md` as a project file
3. Optionally upload `references/scoring_rubric.md` and `references/manual_checklist.md` for more detailed analysis

### Other LLMs

Upload `SKILL.md` along with `references/scoring_rubric.md` and `references/manual_checklist.md` as context. Then provide your LinkedIn CSV export files and ask for a profile audit.

## What Gets Analyzed

**14 automated sections** scored from your exported data:
- Headline, About section, Experience (titles, descriptions, duration), Skills, Recommendations, Connections, Activity, Location, Contact Info, Name, Education, Certifications

**6 manual checklist items** for things that can't be verified from the export:
- Custom URL, Profile Photo, Cover Photo, Featured Section, Open to Work settings, Privacy/Visibility

## Output

- Overall score (0-100) with letter grade
- Per-section scores (only sections needing improvement are detailed)
- Full action plan: what is wrong, what to change, and step-by-step instructions for every fix
- Keyword gap analysis woven into each recommendation (if you specify a target role)
- Manual checklist with navigation paths and instructions for items that cannot be verified from the export

See [assets/sample_report.md](assets/sample_report.md) for an example output.

## Disclaimer

This tool generates recommendations based on general LinkedIn optimization best practices and recruiter search behavior patterns. These are suggestions, not rules. You know your industry, your audience, and your career better than any automated analysis can. Use your own judgment about which recommendations to apply and which to ignore.

For example, the tool might flag a term as too niche when it's actually well-known in your field, or suggest removing something that differentiates you. Treat the output as a starting point for reflection, not a checklist to follow blindly.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to submit improvements to scoring criteria, output format, or CSV compatibility.

## License

MIT — see [LICENSE](LICENSE) for details.
