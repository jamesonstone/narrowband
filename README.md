<div align="center">

<h1>📡 Narrowband</h1>

<p><strong>Tune into boring problems worth solving.</strong></p>
<p>Evidence-first research for durable operational software businesses.</p>

</div>

Narrowband is a research repository for discovering durable software business opportunities in important, operationally messy industries. It is intentionally evidence-first: the repo stores immutable daily research findings, a living catalog of validated ideas, and the development rules that keep future work grounded in real workflow pain instead of hype.

## What This Repository Does

- Captures daily research reports in `findings/YYYY-MM-DD.md`.
- Maintains a deduplicated opportunity catalog in `ideas/business-ideas.md`.
- Scores opportunities using the shared Pain, Pay, Frequency, and Founder Advantage formula.
- Preserves source links and evidence summaries for each opportunity.
- Separates strong opportunities from weak evidence so speculation does not become roadmap.
- Defines the recurring ProdResearch automation prompt in `PROMPT.md`.
- Keeps repo-local development rules under `docs/`, with `docs/CONSTITUTION.md` as the canonical project contract.

## Repository Layout

```text
.
|-- findings/                  # Immutable daily research reports
|-- ideas/                     # Living catalog of validated business ideas
|-- docs/
|   |-- CONSTITUTION.md        # Project contract and development rules
|   |-- PROJECT_PROGRESS_SUMMARY.md
|   |-- agents/                # Agent workflow routing and guardrails
|   `-- references/            # Durable repo-wide references and rulesets
|-- AGENTS.md                  # Agent routing entrypoint
|-- CLAUDE.md                  # Claude routing entrypoint
|-- PROMPT.md                  # ProdResearch automation prompt
`-- .github/copilot-instructions.md
```

## Automation Prompt

[`PROMPT.md`](PROMPT.md) is the canonical brief for the ProdResearch automation. It defines the subreddit scope, research objective, evidence requirements, deduplication rules, repository workflow, PR expectations, and output format for recurring research runs.

## Core Workflow

1. Research public, non-gated sources for repeated workflow pain.
2. Require evidence that the problem is recurring, costly, and has a plausible buyer.
3. Add or update the daily findings report for the current date.
4. Merge duplicate ideas into the existing catalog instead of creating near-duplicates.
5. Sort `ideas/business-ideas.md` by Opportunity Score descending.
6. Keep weak evidence labeled until repeated support is found.

## Opportunity Scoring

```text
Opportunity Score =
(Pain x 0.4)
+ (Pay x 0.3)
+ (Frequency x 0.2)
+ (Founder Advantage x 0.1)
```

## Current State

This repository currently has no application runtime, package manifest, or production code. Its functional surface is the research corpus and the process documentation that governs how that corpus grows.

The initial catalog is seeded from the 2026-06-24 ProdResearch run and tracks opportunities such as month-end close reconciliation, rehab therapy documentation, logistics invoice/POD reconciliation, lab inventory, and IT asset/license lifecycle tracking.

## Development Contract

Before changing the project, read `AGENTS.md`, then use `docs/agents/README.md` to load only the docs needed for the current decision. `docs/CONSTITUTION.md` is the source of truth for goals, non-goals, constraints, research standards, and future implementation rules.
