# Tacit Knowledge: People Analytics
# PatternOS | Andy Styx
# Last updated: 2026-04-12
#
# PURPOSE: This file captures expertise I use automatically that an AI agent has no access to.
# It is not a process guide. It is compressed pattern recognition built from years of doing this work.
#
# HOW TO MAINTAIN: When an AI gives a wrong or incomplete answer on a people analytics task,
# write down what it missed. The file builds itself from failures, not from a blank page.

---

## Domain Context

People analytics sits at the intersection of HR, finance, data engineering, and organizational behavior.
The data is messy, politically sensitive, and structurally misleading if you don't know where to look.
Most people analytics work fails not because of bad analysis but because of bad data assumptions
that experienced practitioners would never make.

My specific depth: workforce data modeling, HR data infrastructure, RIF execution, HRIS systems
(Workday primary), people metrics, org design analytics, and AI-assisted HR tooling.

---

## Data Instincts (what I check before I can explain why)

**Headcount**
- Never trust a headcount number without knowing the as-of date and population filter
- Worker type matters before anything else: employee vs contractor vs contingent vs intern — these are almost never cleanly separated in source systems
- Active status definitions vary by system — Workday "active" is not the same as payroll "active"
- Always check for worker-position fan-out before aggregating — one worker can hold multiple positions
- Rehires create duplicate records in most HRIS systems — check for them before any tenure analysis
- Terminated workers stay in the system — always confirm your population filter is correct
- Global headcount requires knowing which legal entities are included — acquisitions often live in separate instances

**Org hierarchy**
- Never trust org hierarchy data without validating against payroll — managers get changed in HRIS without HR knowing
- Span of control calculations break when managers have matrix reports vs direct reports vs dotted-line reports
- Hierarchy depth changes with every reorg — time-series org analysis requires snapshotting, not live data
- "Manager" in HRIS often means HR manager, not the person the employee actually reports to
- Skip-level relationships are almost never captured cleanly

**Attrition**
- Always clarify: voluntary vs involuntary vs total attrition — they tell completely different stories
- Regrettable vs non-regrettable attrition is subjective and almost never captured in data — treat it as qualitative
- Denominator definition changes attrition rate significantly: beginning headcount vs average headcount vs ending headcount
- Annualized attrition on small populations is statistically meaningless — flag sample size always
- New hire attrition (< 90 days, < 1 year) should always be separated from overall attrition

**Compensation**
- Base salary vs total cash vs total compensation are three different numbers — never mix them
- Equity is almost never in HRIS — it lives in a separate cap table or equity management system
- Pay equity analysis requires job architecture (grades, levels, families) — without it you're comparing noise
- Geographic pay adjustments make cross-location comp comparisons meaningless without normalization
- Bonus targets vs bonus actuals are different fields that get confused constantly

**Tenure**
- Continuous service date vs adjusted service date vs hire date are three different things
- Acquisitions reset tenure in most systems — acquired employees look like new hires
- Leaves of absence affect tenure calculations differently by system and by country

---

## Edge Cases (what breaks that a beginner wouldn't anticipate)

- **The reorg lag problem:** HRIS org changes trail real organizational changes by weeks or months. Any analysis done during or just after a reorg is suspect until the data catches up.
- **The acquisition data gap:** Acquired company data is almost never clean on day one. Assume 6-12 months before it's trustworthy in the parent system.
- **The performance data problem:** Performance ratings are calibrated, not raw — comparing ratings across orgs or time periods without knowing the calibration process is meaningless.
- **The global data problem:** Employment law varies by country. What's capturable in the US (race, gender self-ID) may be illegal to store in Europe. Global people analytics requires knowing what you legally can and cannot analyze by geography.
- **The survey-HRIS join problem:** Engagement survey data almost never joins cleanly to HRIS data. Employee IDs change, names change, emails change. Always validate match rates before trusting merged datasets.
- **The date field trap:** Workday has 15+ date fields per worker. Using the wrong one silently corrupts any time-based analysis.
- **The position vs person confusion:** In Workday and most modern HRIS, positions exist independently of people. A position can be filled, unfilled, or frozen. Headcount can mean position count or worker count — always clarify.
- **The manager-as-employee problem:** When a manager leaves, their direct reports temporarily have no manager in the system. This creates orphaned org trees that break hierarchy queries.

---

## Stakeholder Knowledge (who reacts how to what)

**HRBPs**
- Think in terms of individual cases and narratives, not population statistics
- Attrition data makes them defensive if their org is highlighted negatively — lead with context before numbers
- Want to know "who" not "how many"
- Distrust dashboards they didn't ask for
- Most useful when you bring them a question, not an answer

**HR Leadership**
- Want benchmarks — always ask "compared to what?" before they do
- Sensitive to anything that implies HR itself is the problem
- Will share people analytics output with the CEO — assume everything you build for them is executive-facing
- Prefer story over methodology

**Finance**
- Trust numbers more than HR does — but will immediately challenge methodology if the number surprises them
- Headcount is a cost center line item to them — they care about FTE cost, not engagement
- Want to reconcile your headcount to their headcount — they will always be different and you need to know why
- Respect precision — vague ranges make them distrust the whole analysis

**Legal / Compliance**
- Will kill an analysis if they think it creates legal exposure — especially anything touching protected classes
- Need to be involved before RIF analysis is shared widely, not after
- Are not trying to block the work — they're trying to protect the company — treat them as partners

**Executive / C-suite**
- Want one number with confidence, not a range with caveats
- Will act on a dashboard they don't fully understand — build in guardrails
- Reframe everything as business impact — "17% attrition in engineering" lands better as "we lost X engineers last year at an average replacement cost of $Y"

---

## Metrics I Trust vs Metrics I Don't

**Trust with context:**
- Headcount (with population definition)
- Offer acceptance rate (with source channel breakdown)
- Time to fill (with req type breakdown)
- Regrettable attrition (if there's a clean capture mechanism)
- Internal mobility rate

**Use carefully:**
- Engagement scores (survey methodology and participation rate matter enormously)
- Performance distribution (calibration process determines meaning)
- Span of control (definition of "report" varies)
- Cost per hire (what's included varies widely)

**Almost always misleading without heavy qualification:**
- "Culture" metrics
- Manager effectiveness scores (self-report bias, recency bias)
- Productivity metrics from activity data (Slack messages, emails, meetings)
- Any metric produced from a survey with < 70% response rate

---

## RIF / Reduction in Force (specialized domain)

This is high-stakes, legally sensitive, and operationally complex. I have executed RIF work at Meta and Atlassian.

- **Legal review before data work** — the selection methodology must be reviewed by legal before analysis begins, not after
- **Adverse impact analysis is not optional** — any RIF touching protected classes needs disparate impact analysis run and reviewed
- **The list is not the list until it's the list** — impacted employee lists change until the moment of execution; version control everything
- **Workday load sequencing matters** — terminations need to load in the right order or downstream payroll and benefits systems break
- **Payroll cutoff timing is a hard constraint** — everything has to be loaded before payroll runs or people get paid incorrectly
- **Communications and system changes must be coordinated** — employees should not be able to see their termination in Workday before the conversation happens
- **Single point of failure risk is real** — RIF execution with one person who knows the full process is a liability; document everything

---

## Star Schema / People Core Data Model

My canonical approach to people analytics infrastructure. This is the model I've built or advocated for at every employer.

**Core entities:**
- `dim_worker` — the person, slowly changing dimension (Type 2)
- `dim_position` — the role/seat, independent of who fills it
- `dim_org` — organizational hierarchy snapshot
- `dim_date` — standard date dimension
- `fact_worker_position` — the relationship between worker and position over time
- `ref_*` — reference tables for job families, grades, locations, etc.

**Why this matters:**
- Most HRIS reporting is entity-confused — it mixes worker and position data without making the distinction explicit
- A star schema forces you to make data model decisions that surface business rule ambiguities early
- Downstream self-service analytics is only possible if the model is clean and documented

**Common pushback and responses:**
- "We use data mesh" — data mesh is a distribution architecture, not a modeling philosophy; star schema still applies within domains
- "Workday has its own reporting" — Workday reports are not a substitute for a governed analytical layer; they're a data source
- "This takes too long" — a bad model takes longer because you rebuild it every time a question changes

---

## What Good People Analytics Actually Looks Like

- A business leader changes a decision because of something you showed them
- A process gets automated because you modeled it correctly
- A question that took 3 weeks to answer takes 3 minutes next time
- The data is trusted enough that people argue about the implication, not the number

**What it doesn't look like:**
- A dashboard that gets built and never opened
- An insight that gets presented and then ignored
- A metric that exists because someone asked for it once in 2019
- Analysis that confirms what leadership already believed

---

## Open Questions / Still Learning

- How to make people analytics genuinely predictive rather than descriptive at scale
- Best governance model for AI-generated people insights in regulated environments
- How to handle synthetic data generation for people analytics testing without creating legal exposure
- Skill inference from unstructured data — what actually works vs what is demos

---

## Capture Log (append when AI misses something)

*Format: date | what the AI got wrong | what the correct answer is*

- 2026-04-12 | AI assumed headcount = worker count without asking about position fills | Always clarify worker vs position before any headcount query
