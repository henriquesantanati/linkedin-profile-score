---
name: linkedin-profile-score
description: "Audit and score a LinkedIn profile from its native CSV data export. Analyzes profile sections for recruiter visibility, keyword optimization, and credibility. Use when the user provides a folder of CSV files from a LinkedIn data export and wants to optimize their profile for job searching. Triggers on: audit my LinkedIn, review my profile, LinkedIn optimization, profile score, score my profile, LinkedIn audit, optimize my LinkedIn, LinkedIn CSV. Do NOT use for writing LinkedIn posts, managing connections, job application tracking, or general career coaching."
---

# LinkedIn Profile Score

Analyze a LinkedIn profile from its native CSV data export and produce a comprehensive score with actionable recommendations to improve recruiter visibility and hiring chances.

## Prerequisites

This skill requires the user's LinkedIn data exported as CSV files (the default format LinkedIn provides).

**How to get the data:**
1. Go to LinkedIn → Settings → Data Privacy → Get a copy of your data
2. Select "Download larger data archive" and request the archive
3. Wait for the email (usually 24-72h)
4. Download and unzip the ZIP file
5. Provide the path to the unzipped folder

**Expected CSV files** (read all that exist in the export folder):

| File | Content |
|------|---------|
| `Profile.csv` | Name, headline, location, summary, industry |
| `Positions.csv` | Work history (title, company, description, dates) |
| `Skills.csv` | Listed skills |
| `Recommendations Received.csv` | Recommendations from others |
| `Connections.csv` | Network connections |
| `Shares.csv` or `Posts.csv` | Posts and activity |
| `Certifications.csv` | Licenses and certifications |
| `Education.csv` | Educational background |
| `Email Addresses.csv` | Contact email(s) |

Note: LinkedIn occasionally changes file names between export versions. If a file is not found by exact name, look for partial matches (e.g., a file containing "position" or "experience" in its name). Adapt to whatever CSV files are present.

## Workflow

### Step 1: Locate Input

Ask the user for the path to their unzipped LinkedIn data export folder. List the CSV files found and confirm which ones are available before proceeding.

### Step 2: Read Profile Data

Read all available CSV files. Parse them as standard CSV (comma-delimited, with headers in the first row). Track which files are present and which are missing. Missing files mean those sections receive no score (not zero, just excluded from the weighted calculation and weights redistributed proportionally).

### Step 3: Automated Analysis

Analyze 14 sections using the criteria in `references/scoring_rubric.md`. For each section:
- Assign a score from 1 to 5
- Identify specific issues found
- Write one concrete recommendation (what to change and why)

If the user specified a target role, incorporate keyword gap analysis directly into each section's recommendation. When suggesting a rewritten headline, About section, or experience bullet, include the missing keywords naturally. Do not create a separate keywords section — the fixes should already contain the right keywords.

The 14 sections and their weights:

| Section | Weight | Source File |
|---------|--------|-------------|
| Headline | 15% | Profile.csv |
| Experience Titles | 8% | Positions.csv |
| Experience Descriptions | 12% | Positions.csv |
| Experience Duration | 5% | Positions.csv |
| Skills | 12% | Skills.csv |
| About | 10% | Profile.csv |
| Recommendations | 8% | Recommendations Received.csv |
| Connections | 5% | Connections.csv |
| Activity | 5% | Shares.csv / Posts.csv |
| Location | 4% | Profile.csv |
| Contact Info | 4% | Profile.csv + Email Addresses.csv |
| Name | 3% | Profile.csv |
| Education | 5% | Education.csv |
| Certifications | 4% | Certifications.csv |

### Step 4: Manual Checklist

Present 6 items that cannot be verified from the data export. These are things the user needs to check themselves. For each item, explain:
1. Where to find it (exact navigation path in LinkedIn)
2. What to look for
3. What the recommendation is if it needs fixing

Read `references/manual_checklist.md` for the full checklist with context. Do NOT present these as yes/no results — you cannot verify them. Present them as a clear guide the user should follow after fixing the automated issues.

### Step 5: Calculate Score and Generate Report

**Score formula:**
- Weighted average of section scores (using weights from Step 3), normalized to 0-100 scale
- Only scored from sections where data is available

**Grade thresholds:**
- A (90-100): Profile is optimized for recruiter visibility.
- B (75-89): A few targeted improvements will make a difference.
- C (60-74): Several sections need attention.
- D (45-59): Significant optimization needed.
- F (0-44): Needs overhaul across most sections.

**Report format:**

```markdown
# 🎯 LinkedIn Profile Score

## [XX]/100 — Grade [X]

[1-2 direct sentences: what the score means and what is holding it back.]

**Fix priority:** [Section1] → [Section2] → [Section3]... (ordered from highest impact to lowest)

---

## Scores

| Section | Score | |
|---------|-------|---|
| [Section] | X/10 | 🔴 |

Color indicators: 🔴 (1-5), 🟡 (6-7), 🟢 (8-10). Only sections needing improvement are listed individually. Sections scoring 9-10 are grouped at the bottom as:

✅ **All good:** [Section (score), Section (score), ...]

---

## What to Fix

For EVERY section that scored below 9, provide:

### 🔴 [Section Name] (X/10)

**Problem:** [What is wrong, specifically. Quote their actual content if relevant.]

**Recommendation:** [Exactly what to change. Provide the rewritten text or specific action.]

**Steps:**
1. [Step-by-step instructions to make the change on LinkedIn]

Use 🔴 for scores 1-5, 🟡 for scores 6-7 in the section headers. Separate each section with ---.

---

## Manual Checks

These 6 items cannot be verified from your data export. Check each one:

### 1. [Item Name]
**Where:** [Exact LinkedIn navigation path]
**What to look for:** [What a good state looks like]
**If it needs fixing:** [Specific steps to fix]
```

See `assets/sample_report.md` for a complete example output.

## Important Notes

- Never fabricate issues. If a section is good, score it high and move on.
- Be specific. "Improve your headline" is useless. Provide the rewritten headline.
- Every recommendation must include the exact steps to implement it on LinkedIn.
- The report is an action plan, not an assessment. The user should be able to go through it top to bottom and fix everything in one sitting.

## Credits

Scoring criteria inspired by Nicole Barra's guide on LinkedIn profile optimization.
