# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in this project, please report it responsibly.

**Do not open a public GitHub issue for security vulnerabilities.**

Instead, use [GitHub's private vulnerability reporting](https://github.com/henriquesantanati/linkedin-profile-score/security/advisories/new) to submit your report directly. This keeps the details confidential until a fix is available.

Please include:

- A description of the vulnerability
- Steps to reproduce
- Potential impact

You can expect an acknowledgment within 72 hours and a resolution timeline within 7 days.

## Scope

This project is a markdown-based skill (not a running application), so the attack surface is limited. Relevant concerns include:

- Scoring criteria that could be manipulated to produce misleading results
- Instructions that could lead users to expose private data unintentionally
- CSV parsing guidance that could be exploited if used in automated pipelines
