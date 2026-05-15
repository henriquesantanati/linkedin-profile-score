# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.0] - 2026-05-15

### Changed
- **Breaking:** Scoring methodology overhauled based on expert feedback from Nicole Barra (original inspiration for this tool)
- Recommendations moved from automated scoring (8%) to manual checklist — social proof matters but is less impactful than keywords and discoverability
- Skills weight increased from 12% to 13% with emphasis on keyword consistency across sections
- Connections weight increased from 5% to 8% — network size directly affects search visibility
- Certifications weight reduced from 4% to 3%; absence is no longer penalized (floor score is 3, not 1)
- Education weight reduced from 5% to 3% — less relevant for experienced professionals
- Name weight reduced from 3% to 2%
- Open to Work moved to #1 position in manual checklist (was #5) with highest point bonus (+3)

### Added
- Interests section (4% weight) — following relevant companies/influencers signals intent to the algorithm
- Profile Language section (4% weight) — profile must match target market language
- Tier-based priority framework informed by recruiter search behavior

### Removed
- Recommendations as an automated scored section (moved to manual checklist as optional improvement)

Total automated sections: now 15 (was 14 in v1.x). Manual checklist: now 7 items (was 6).

## [1.2.0] - 2026-05-15 (earlier same day)

### Added
- CHANGELOG.md in Keep a Changelog format
- SECURITY.md with responsible disclosure process
- SUPPORT.md clarifying where to get help vs file bugs
- .gitignore for OS and editor artifacts
- README badges (license, latest release, contributions welcome)
- README contributing section
- Semantic version tags for all prior releases (v1.0.0, v1.1.0)

## [1.1.0] - 2026-05-14

### Added
- Disclaimer section in README clarifying recommendations are suggestions, not rules
- CONTRIBUTING.md with scope definition and submission process
- CODE_OF_CONDUCT.md (Contributor Covenant 2.1)
- Issue templates for bug reports and feature requests
- Pull request template

## [1.0.0] - 2026-05-12

### Added
- Initial release of LinkedIn Profile Score skill
- 14-section automated scoring from LinkedIn CSV export
- 6-item manual checklist for non-exportable profile elements
- Scoring rubric with weighted formula (0-100 scale)
- Sample report output
- Support for Claude Code, Claude.ai Projects, and other LLMs

[2.0.0]: https://github.com/henriquesantanati/linkedin-profile-score/compare/v1.2.0...v2.0.0
[1.2.0]: https://github.com/henriquesantanati/linkedin-profile-score/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/henriquesantanati/linkedin-profile-score/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/henriquesantanati/linkedin-profile-score/releases/tag/v1.0.0
