# Scoring Rubric

Detailed criteria for each of the 15 automated sections. Each section is scored 1-10, using the anchors below as reference points (1-2 = poor, 3-4 = weak, 5-6 = average, 7-8 = good, 9-10 = excellent).

---

## 1. Headline (Weight: 15%)

**Source:** Profile.csv (title/headline field)

The headline is the primary ranking factor in LinkedIn search. Recruiters see it in search results before clicking into a profile.

| Score | Criteria |
|-------|----------|
| 5 | Contains target role title + 2-3 key technical skills + industry/domain. Under 120 chars. No emojis or clichés. |
| 4 | Has role title + skills but missing industry context or slightly too generic. |
| 3 | Just a job title with company name (LinkedIn default format). |
| 2 | Vague, uses internal company title, or cluttered with too many buzzwords/acronyms. |
| 1 | Contains emojis, personal info ("Father of two"), motivational quotes, or is the default LinkedIn-generated headline. |

**What to flag:**
- Default format "[Title] at [Company]" without customization
- Emojis or special characters
- Personal information unrelated to professional expertise
- Self-assigned seniority labels like "Junior" or "Mid-level" (these limit opportunities)
- Excessive length (over 120 chars becomes unreadable in search results)

**Good examples:**
- "Full-Stack Engineer | Node.js & React | SaaS"
- "Senior Data Engineer | Spark, Airflow, dbt | FinTech"
- "Platform Engineer | Kubernetes & AWS | Building Developer Platforms"

**Bad examples:**
- "Software Developer at Acme Corp"
- "☕ Passionate coder | Father | Problem solver ⚡"
- "SWE | JS | TS | React | Next | Node | Mongo | AWS | GCP | Docker | K8s"


## 2. Skills (Weight: 13%)

**Source:** Skills.csv

Skills are keywords that recruiters use as search filters. They should appear consistently across the About, Experience, and Skills sections to create keyword density. Hard skills matter most.

| Score | Criteria |
|-------|----------|
| 5 | 10-15 relevant hard skills, aligned with target role, prioritized correctly. Skills echo keywords in About and Experience sections. Few or no soft skills listed. |
| 4 | Good hard skills present but slightly too many or includes some irrelevant ones. |
| 3 | Mix of hard and soft skills without clear prioritization. 5-9 total skills. |
| 2 | Dominated by soft skills, or very few skills listed (under 5). Irrelevant skills prominent. |
| 1 | No skills, or only generic ones ("Microsoft Office", "Communication", "Teamwork"). |

**What to flag:**
- Soft skills taking up space (Leadership, Communication, Teamwork belong in About section)
- Generic skills that add no signal ("Programming", "Computers", "Problem Solving")
- Outdated technologies prominently listed
- Fewer than 10 skills total
- Skills not matching what's described in experience
- Skills not reinforced in the About or Experience sections (keyword consistency matters)

**Hard skills recruiters filter by (examples for tech):**
- Languages: Python, Java, TypeScript, Go, Rust
- Frameworks: React, Node.js, Spring Boot, Django
- Infrastructure: AWS, Kubernetes, Docker, Terraform
- Data: PostgreSQL, MongoDB, Apache Kafka, Spark
- Practices: CI/CD, Microservices, System Design


## 3. Experience Descriptions (Weight: 12%)

**Source:** Positions.csv (description fields)

Descriptions should demonstrate impact through accomplishments, not list responsibilities.

| Score | Criteria |
|-------|----------|
| 5 | 3-5 bullet points per role focusing on impact. Includes metrics (percentages, numbers, scale). Uses action verbs. Readable and concise. |
| 4 | Shows accomplishments with some metrics, but could be more specific or better structured. |
| 3 | Mix of responsibilities and accomplishments. Some roles have good descriptions, others are thin. |
| 2 | Mostly lists responsibilities ("Responsible for...", "Worked on..."). No metrics. |
| 1 | Empty descriptions, single vague lines, or walls of text with no structure. |

**What to flag:**
- Empty description fields
- Responsibility-focused language ("Responsible for", "Duties included", "Worked on")
- No quantifiable metrics anywhere
- Walls of text without bullet points or line breaks
- Repeating skills that belong in the Skills section
- Descriptions that read like a job posting rather than personal accomplishments

**Good example:**
- Led migration of monolithic application to microservices architecture serving 2M daily users
- Reduced deployment time from 2 hours to 15 minutes through CI/CD pipeline redesign
- Cut infrastructure costs by 35% via right-sizing and spot instance adoption

**Bad example:**
"Worked on backend development. Did code reviews. Fixed bugs."


## 4. About Section (Weight: 10%)

**Source:** Profile.csv (summary/about field)

The About section is an elevator pitch. It should be concise, scannable, and keyword-rich.

| Score | Criteria |
|-------|----------|
| 5 | Structured (opening + skills + highlights + goals + CTA). 150-250 words. Includes keywords naturally. Professional yet engaging tone. |
| 4 | Good content but missing one element (no CTA, no goals, or slightly too long). |
| 3 | Present but either too generic, too long (wall of text), or missing clear structure. |
| 2 | Very short (1-2 sentences), overly personal, or reads like a cover letter template. |
| 1 | Empty or contains only "I like coding" type content. |

**What to flag:**
- Empty About section
- No line breaks (wall of text)
- Starts with "I am a..." (passive opening)
- No mention of key technical skills (missed SEO opportunity)
- Too personal without professional substance
- Over 500 words (recruiters skim)
- Uses LinkedIn text formatters that make keywords unsearchable

**Suggested structure:**
1. Opening statement (who you are, what you do)
2. Key skills and expertise (2-3 lines — hard skills belong here as keywords)
3. Experience highlights (1-2 standout achievements)
4. Soft skills woven naturally into narrative (e.g., "I lead cross-functional teams" rather than listing "Leadership")
5. Career goals (what you're looking for)
6. Call to action (invite to connect)


## 5. Experience Titles (Weight: 8%)

**Source:** Positions.csv (job title fields)

Recruiters use title filters extensively. Titles must match how the industry searches for roles, not internal company naming.

| Score | Criteria |
|-------|----------|
| 5 | All titles are industry-standard, recognizable, and include meaningful seniority (Senior, Staff, Lead) where applicable. |
| 4 | Most titles are clear, one or two could be more standard. |
| 3 | Mix of clear and unclear titles. Some internal jargon present. |
| 2 | Multiple titles use internal company nomenclature or vague terms. |
| 1 | Titles are creative/informal ("Code Wizard", "Ninja") or incomprehensible outside the company. |

**What to flag:**
- Creative titles (Ninja, Wizard, Rockstar, Guru)
- Overly specific internal titles ("Software Development Engineer II" could be "Software Engineer" for most contexts)
- Self-limiting labels ("Junior Developer" when the work is clearly mid-level)
- Inconsistent naming across roles (mixing "Developer", "Engineer", "Programmer" without reason)

**Industry-standard titles recruiters search for:**
- Software Engineer (not Programmer, Developer)
- Full-Stack Engineer
- Backend/Frontend Engineer
- Data Engineer / Data Scientist
- DevOps Engineer / Platform Engineer / SRE
- Engineering Manager


## 6. Connections (Weight: 8%)

**Source:** Connections.csv (count the entries)

Network size directly affects profile visibility and search reach. LinkedIn's algorithm surfaces profiles with larger networks more frequently. 500+ is the credibility threshold.

| Score | Criteria |
|-------|----------|
| 5 | 500+ connections. |
| 4 | 300-499 connections. |
| 3 | 150-299 connections. |
| 2 | 50-149 connections. |
| 1 | Under 50 connections. |

**What to flag:**
- Under 500 (the threshold where LinkedIn shows "500+" instead of the exact number)
- Note: quality cannot be fully assessed from the export, but count is a baseline signal
- A small network limits how often the profile appears in recruiter searches


## 7. Experience Duration (Weight: 5%)

**Source:** Positions.csv (date fields)

Recruiters assess career stability and progression through duration patterns.

| Score | Criteria |
|-------|----------|
| 5 | Clear progression, roles with 2+ years, month/year format, no unexplained gaps. |
| 4 | Mostly stable with one short stint that has context (layoff, acquisition). |
| 3 | Some short stints without explanation, or year-only format used. |
| 2 | Multiple roles under 1 year with no context. Gaps present without explanation. |
| 1 | Frequent job hopping (many roles under 6 months), large unexplained gaps, or missing dates. |

**What to flag:**
- Year-only dates (should be month/year for precision)
- Multiple roles under 12 months without explanation
- Gaps longer than 3 months without context
- Many overlapping roles making the timeline confusing
- Freelance gigs listed individually instead of grouped


## 8. Activity (Weight: 5%)

**Source:** Shares.csv or Posts.csv

Regular activity signals engagement and boosts algorithmic visibility.

| Score | Criteria |
|-------|----------|
| 5 | Posts or shares at least weekly. Content is professional and industry-relevant. |
| 4 | Posts 2-3 times per month. Mostly professional content. |
| 3 | Posts occasionally (monthly or less). Some professional engagement. |
| 2 | Very rare activity (a few posts per year). |
| 1 | No posts at all, or last activity was over 6 months ago. |

**What to flag:**
- No posts in the last 6 months
- Activity that's purely reactions/likes with no original content
- Content unrelated to professional expertise
- Note: engagement quality matters but is hard to assess from export alone


## 9. Interests (Weight: 4%)

**Source:** Company Follows.csv + Member_Follows.csv

Following relevant companies, influencers, and groups signals intent to LinkedIn's algorithm and creates additional keyword surface area on your profile.

| Score | Criteria |
|-------|----------|
| 5 | Follows 10+ companies and thought leaders relevant to target role/industry. Groups joined align with career goals. |
| 4 | Follows several relevant companies and people. Some alignment with career direction. |
| 3 | Follows some companies but no clear pattern. Mix of relevant and random. |
| 2 | Very few interests, or mostly irrelevant (entertainment, unrelated industries). |
| 1 | No interests/follows visible, or only follows personal connections' companies. |

**What to flag:**
- Not following target companies (the ones you'd want to work at)
- Not following industry thought leaders or publications
- No group memberships in professional communities
- Following only your current employer

**Recommendation approach:**
- Follow 10-15 companies in your target industry
- Follow 5-10 thought leaders who post about your domain
- Join 3-5 professional groups (even if you don't post in them)
- This signals to recruiters AND the algorithm what you're interested in

**Note:** LinkedIn's CSV export may not always include full interest data. If unavailable, inform the user this section exists and suggest they review it manually.


## 10. Profile Language (Weight: 4%)

**Source:** Languages.csv + Profile.csv (content language)

The profile must be written in the language of your target job market. A profile in Portuguese targeting US roles, or in English targeting the French market, creates friction for recruiters.

| Score | Criteria |
|-------|----------|
| 5 | Profile language matches target market. All sections consistently in one language. No mixed-language content. |
| 4 | Correct language but minor inconsistencies (one role description in a different language due to local company). |
| 3 | Mostly correct but About or Headline has phrases in another language. |
| 2 | Profile is in a different language than the target market, or significantly mixed between languages. |
| 1 | Profile language actively mismatches target market (e.g., entire profile in native language while targeting English-speaking roles). |

**What to flag:**
- Profile written in a language different from the target market
- Mixed languages across sections without a clear reason
- LinkedIn profile language setting not matching the content language
- Note: multi-language profiles (LinkedIn allows secondary languages) can be a solution for people targeting multiple markets

**Recommendation approach:**
- If targeting English-speaking markets: entire profile in English, including all role descriptions
- If targeting a local market: use the local language
- If targeting both: use LinkedIn's multi-language profile feature to maintain separate versions
- Past roles at companies in other countries: still describe in the target language


## 11. Location (Weight: 4%)

**Source:** Profile.csv (location field)

Location affects search filters. Must align with where you actually want to work.

| Score | Criteria |
|-------|----------|
| 5 | Location matches target job market. Clear city or country. |
| 4 | Location is set but slightly broad (country-level when city would help). |
| 3 | Location is set but doesn't clearly align with target market. |
| 2 | Location set to a place where the user doesn't live or have work authorization, creating confusion. |
| 1 | No location set, or set to a misleading location. |

**What to flag:**
- Setting location to US/Europe when based elsewhere without a visa (for non-remote roles)
- For remote roles: location should be where you're physically based
- Missing location entirely


## 12. Contact Information (Weight: 4%)

**Source:** Profile.csv (contact fields) + Email Addresses.csv

Recruiters need a way to reach you outside LinkedIn.

| Score | Criteria |
|-------|----------|
| 5 | Email + at least one additional link (GitHub, portfolio, personal site). All current. |
| 4 | Email present and current. No additional links. |
| 3 | Email present but no other contact info. |
| 2 | Only LinkedIn default contact (no email shared). |
| 1 | No contact information at all, or outdated/invalid info. |

**What to flag:**
- No email address shared
- Dead links to portfolios or websites
- Full home address posted (privacy concern)
- Missing GitHub/portfolio for engineering roles


## 13. Certifications (Weight: 3%)

**Source:** Certifications.csv

Certifications provide additional keyword surface area and signal ongoing learning. Their absence is not a problem — treat this as an optimization opportunity, not a deficit.

| Score | Criteria |
|-------|----------|
| 5 | 1-3 relevant, recent certifications from recognized institutions (AWS, Google Cloud, etc.) that reinforce target role keywords. |
| 4 | Relevant certifications present (4-6 is fine) but slightly dated or not perfectly aligned with current direction. |
| 3 | No certifications present (neutral — no keyword benefit, nothing harmful). |
| 2.5 | Mix of relevant and irrelevant certifications, or from unknown institutions. |
| 2 | Only outdated or irrelevant certifications that add no keyword value. |
| 1 | Flooded with low-value credentials ("HTML Basics", "Introduction to...") that dilute credibility. |

**What to flag:**
- Expired certifications still listed prominently
- Certifications from unknown or low-credibility institutions
- Too many certifications (7+) diluting the signal
- Certifications that contradict career direction

**Important:** Do NOT penalize the absence of certifications. A score of 3 is the floor for someone with no certifications — it means "neutral, no keyword benefit captured here but nothing wrong either." Only score below 3 if certifications are present but harmful (irrelevant, expired, low-value). Frame recommendations as: "Adding a relevant certification here would give you extra keyword surface for [skill]" rather than "You're missing certifications."


## 14. Education (Weight: 3%)

**Source:** Education.csv

Education provides context and can boost credibility, especially early-career. For experienced professionals, it matters far less than experience and skills.

| Score | Criteria |
|-------|----------|
| 5 | Degree listed with institution (linked), field of study, graduation year. Relevant coursework or honors if notable. |
| 4 | Complete information but missing some detail (no honors, no field specificity). |
| 3 | Degree listed but institution not linked, or information is incomplete. |
| 2 | Minimal information (just school name, no degree details). |
| 1 | Empty, or includes irrelevant education (primary/secondary school). |

**What to flag:**
- Primary or secondary school listed (remove these)
- Missing institution links
- Incomplete degrees listed without context
- Missing field of study

**Note:** For professionals with 10+ years of experience, education is context, not a differentiator. Don't over-emphasize improvements here if the experience section is strong.


## 15. Name (Weight: 2%)

**Source:** Profile.csv (name field)

Name should be professional, findable, and clean.

| Score | Criteria |
|-------|----------|
| 5 | First and last name only. Proper capitalization. Clean and professional. |
| 4 | Name is clear but includes a credential or minor addition (e.g., "MBA" or "PhD"). |
| 3 | Name has unnecessary middle names or initials making it harder to find. |
| 2 | Includes nicknames, emojis, or excessive formatting. |
| 1 | ALL CAPS, all lowercase, contains special characters, or uses a nickname as primary name. |

**What to flag:**
- Emojis anywhere in the name
- ALL CAPS or all lowercase
- Nicknames as primary identifier
- Excessive titles or credentials in the name field (these belong in headline)
- Multiple middle/last names when a simpler version would be more findable
