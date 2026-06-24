🔭 Discovering meaningful problems worth solving.

Set up a recurring Codex automation called ProdResearch.

Every weekday, review the following subreddits.

Vertical Industry Subreddits

- r/medlabprofessionals
- r/surveying
- r/wastewater
- r/sterileprocessing
- r/GIS
- r/fleetmanagement
- r/paralegal
- r/propertymanagement
- r/occupationaltherapy
- r/physicaltherapy
- r/pharmacy
- r/radiology
- r/sysadmin
- r/networking
- r/msp
- r/k12sysadmin
- r/homelab
- r/accounting
- r/bookkeeping
- r/logistics

Software Pain / Technical Operations Subreddits

- r/devops
- r/dataengineering
- r/BusinessIntelligence
- r/analytics
- r/PowerBI

Large Business Communities

- r/smallbusiness
- r/Entrepreneur
- r/freelance
- r/selfhosted

Additional High-Signal Communities

- r/healthIT
- r/labrats
- r/civilengineering
- r/Construction
- r/AskEngineers

Research Objective

Identify recurring workflow pain, operational bottlenecks, compliance burdens, documentation burdens, repetitive work, manual processes, labor shortages, coordination problems, reporting requirements, or expensive inefficiencies that could become long-term, sustainable software businesses.

The goal is not startup trends, AI hype, consumer apps, or quick-profit opportunities.

The goal is to discover businesses that:

- Solve real problems.
- Produce measurable value.
- Improve important industries.
- Have identifiable buyers.
- Could remain valuable for 10+ years.
- Are not dependent on unrealistic assumptions or speculative technology.

Research Guidelines

Strongly prioritize problems where users currently rely on:

- Excel
- Google Sheets
- Email
- PDFs
- Paper forms
- Phone calls
- Copy/paste between systems
- Manual data entry
- Manual reporting
- Tribal knowledge
- Homegrown scripts

Treat these as high-signal indicators.

Prefer workflows involving:

- Compliance
- Auditing
- Traceability
- Documentation
- Reporting
- Quality control
- Regulatory requirements
- Operational risk
- Workflow coordination
- Asset tracking
- Inventory management
- Scheduling
- Procurement
- Data reconciliation

Prioritize workflows over feature requests.

The ideal opportunity is a high-frequency workflow performed repeatedly by many professionals.

Avoid reporting feature requests for existing software unless they reveal a broader workflow problem.

Evidence Requirements

Do not create an idea from a single complaint.

Require one or more of:

- Multiple users describing the same problem.
- Multiple threads describing the same problem.
- Repeated discussion of the workflow over time.
- Clear evidence that the problem consumes meaningful time, money, or effort.

If evidence is weak, mark the idea as Weak Evidence.

Business Requirements

Do not report problems unless there is evidence that:

1. The problem occurs repeatedly.
2. The problem consumes meaningful time, money, or creates risk.
3. A budget owner exists who could reasonably purchase software.

Do not recommend:

- Generic chatbots.
- Generic AI assistants.
- Generic workflow copilots.
- “Uber for X” ideas.
- Marketplace ideas without evidence of marketplace failure.

Only report opportunities with a clearly defined workflow and measurable business value.

Favor:

- Operational software over social software.
- Recurring workflows over one-time workflows.
- Industries with budgets over industries with enthusiasm.
- Evidence over creativity.
- Boring businesses with strong economics over exciting businesses with weak economics.

Idea Deduplication

Before creating a new idea:

- Search existing ideas.
- Merge duplicate ideas.
- Update evidence counts when new supporting evidence is found.
- Prefer strengthening existing ideas over creating near-duplicates.

Data Quality Requirements

- Respect source terms and platform policies.
- Avoid private, gated, or login-only communities.
- Do not store personal identifiers.
- Link every idea back to supporting source material.
- Label weak evidence rather than overstating confidence.
- Prefer direct evidence over speculation.

Repository Workflow

This automation operates against a git repository.

Repository structure:

/
├── findings/
├── ideas/
└── README.md

Findings Directory

Purpose:

Maintain immutable daily research reports.

For each automation run:

1. Create or update:
   findings/YYYY-MM-DD.md
2. The file must contain:
   - Date
   - Research scope
   - Newly discovered opportunities
   - Updated opportunities
   - Idea Discovery Table
   - Top 5 opportunities
   - Supporting links
   - Weak evidence findings
3. Never modify historical findings files from previous dates.
4. If the file already exists for the current day, update it.

Ideas Directory

Maintain:

ideas/business-ideas.md

Purpose:

Maintain a living catalog of validated opportunities.

When new evidence is discovered:

- Add new opportunities.
- Update existing opportunities.
- Strengthen evidence when appropriate.
- Merge duplicates.
- Preserve existing identifiers whenever possible.

Do not create duplicate opportunities when evidence supports an existing entry.

Pull Request Workflow

For each automation run:

1. Create a branch:
   prodresearch/YYYY-MM-DD
2. Commit only:
   - findings/YYYY-MM-DD.md
   - ideas/business-ideas.md
3. Create a pull request.

Title:

ProdResearch findings for YYYY-MM-DD

Body:

## Summary

- New opportunities discovered:
- Existing opportunities updated:
- Duplicates merged:
- Weak evidence opportunities:
- Total opportunities tracked:

## Top Opportunities

List the top 5 opportunities by Opportunity Score.

## Files

- findings/YYYY-MM-DD.md
- ideas/business-ideas.md

If no qualified opportunities are found:

- Still create findings/YYYY-MM-DD.md
- Still create a pull request
- Clearly state:

No qualified opportunities discovered today.

Repository Safety Rules

Do not modify:

- Application code
- Build files
- Dependencies
- Configuration files
- Infrastructure files
- Documentation unrelated to research

This automation may only modify:

- findings/\*
- ideas/\*

Output Format

Purpose:

Track potential software business opportunities discovered from Reddit, forums, interviews, customer conversations, and industry research.

Each row represents a single business opportunity.

Columns

Column Type Description

# Integer Unique sequential identifier.

Idea String Short descriptive name.
User String Primary user experiencing the problem.
Problem String Concise description of the pain point.
Current Solution String How users solve it today.
Buyer String Likely purchaser of the solution.
Pain Integer (1-10) Severity of the problem.
Pay Integer (1-10) Estimated willingness to pay.
Frequency Integer (1-10) How frequently the workflow occurs.
Founder Advantage Integer (1-10) Existing expertise, network, credibility, or distribution advantage.
Opportunity Score Decimal Weighted opportunity score.
Why Now String Why the opportunity is more viable today than in the past.
Moat String Potential long-term defensibility.
Evidence String Summary of supporting evidence.
Link String URL to the primary supporting thread.

Scoring

Calculate:

Opportunity Score =
(Pain × 0.4)

- (Pay × 0.3)
- (Frequency × 0.2)
- (Founder Advantage × 0.1)

Sort all opportunities by Opportunity Score descending.

Output Example

# Idea User Problem Current Solution Buyer Pain Pay Frequency Founder Advantage Opportunity Score Why Now Moat Evidence Link

1 QC Assistant CLS Manual QC review Excel Lab Director 8 7 9 10 8.0 Staffing shortages increase workload while modern integrations make automation feasible. Historical QC data and lab integrations. Multiple lab professionals report spending 1-2 hours daily reviewing QC failures manually. https://reddit.com/…

Additional Analysis

For the top 5 opportunities each day, include:

- One-sentence business thesis.
- Why existing solutions are insufficient.
- Estimated customer type.
- Estimated annual contract value (ACV) range.
- Key implementation risks.
- Key reasons the opportunity may fail.

Favor evidence over intuition.

Favor validated workflow pain over novel ideas.

Favor durable businesses over trends.
