# CONSTITUTION

## PURPOSE

Narrowband exists to discover and preserve evidence for durable software business opportunities in operationally important industries.

The project favors boring, high-frequency, high-value workflows over novelty. The repository should help a reader understand which problems are real, who experiences them, who could buy a solution, how painful the workflow is, and why the opportunity could support a long-lived software business.

## PRINCIPLES

- Evidence over creativity. Do not invent an opportunity from a single complaint or a clever product angle.
- Workflows over features. Prefer recurring jobs, compliance processes, reporting loops, reconciliations, coordination burdens, and documentation requirements over isolated software feature requests.
- Buyers over enthusiasm. Every validated opportunity needs a plausible budget owner.
- Durable value over trends. Avoid ideas that depend on hype, unrealistic technology assumptions, or short-lived arbitrage.
- Clarity over volume. A small catalog of well-supported opportunities is better than a large catalog of weak guesses.
- Source fidelity. Preserve source terms, link supporting material, and distinguish direct evidence from inference.
- Privacy by default. Do not store personal identifiers, private community content, gated material, or unnecessary user-level details.
- Minimalism by default. Add process, structure, or implementation only when it makes the research corpus clearer, safer, or easier to maintain.

## PROJECT MODEL

Narrowband has three primary surfaces:

- `findings/`: immutable daily research reports. A findings file records what was reviewed, what was discovered, what was updated, top opportunities, supporting links, and weak evidence.
- `ideas/business-ideas.md`: the living opportunity catalog. It is deduplicated, evidence-backed, and sorted by Opportunity Score descending.
- `public/`: a read-only static GitHub Pages publication surface for the current corpus and project links.
- `docs/`: the development and research contract. `docs/CONSTITUTION.md` is canonical; `docs/agents/*` routes agent behavior; `docs/references/*` stores durable cross-feature references and imported rulesets.

The repository currently has no application runtime, no dependency manifest, no database, and no server-side production code. Future implementation must not pretend otherwise. Until application code exists, validation is documentation validation, static site artifact validation, evidence validation, formatting checks, link/source review, and git diff review.

## ARCHITECTURAL PATTERNS AND CONVENTIONS

### Repository Architecture

- Keep research artifacts and process docs separate.
- Keep the static publication artifact under `public/` backend-free and derived from committed corpus facts.
- Treat `findings/YYYY-MM-DD.md` as append/update-for-day only; never rewrite historical findings from previous dates.
- Treat `ideas/business-ideas.md` as a living, sorted table of current best opportunities.
- Keep repo-wide process in `docs/CONSTITUTION.md`, `docs/agents/*`, and `docs/references/*`.
- Keep feature-scoped work under `docs/specs/<feature>/SPEC.md` when a future feature needs formal planning.
- Keep `AGENTS.md`, `CLAUDE.md`, and `.github/copilot-instructions.md` short routing tables, not monolithic manuals.

### Research Artifact Pattern

Every daily findings file should include:

- Date.
- Research scope.
- Newly discovered opportunities.
- Updated opportunities.
- Idea Discovery Table.
- Top 5 opportunities.
- Supporting links.
- Weak evidence findings.

Every idea row should include:

- `#`
- `Idea`
- `User`
- `Problem`
- `Current Solution`
- `Buyer`
- `Pain`
- `Pay`
- `Frequency`
- `Founder Advantage`
- `Opportunity Score`
- `Why Now`
- `Moat`
- `Evidence`
- `Link`

### Scoring Pattern

Calculate Opportunity Score as:

```text
(Pain x 0.4) + (Pay x 0.3) + (Frequency x 0.2) + (Founder Advantage x 0.1)
```

Sort `ideas/business-ideas.md` by Opportunity Score descending. Preserve stable identifiers whenever possible. If a score changes, update the sorted order and evidence summary together.

### Deduplication Pattern

- Search existing ideas before creating a new row.
- Strengthen an existing idea when new evidence supports the same workflow.
- Merge duplicates at the workflow level, not by exact wording.
- Preserve existing identifiers unless a merge requires a documented renumbering.
- Do not create separate ideas for narrow feature requests when they reveal the same underlying workflow.

### Evidence Pattern

Strong evidence requires one or more of:

- Multiple users describing the same workflow pain.
- Multiple threads describing the same workflow pain.
- Repeated discussion of the workflow over time.
- Clear evidence that the workflow consumes meaningful time, money, or operational attention.
- Clear evidence that the workflow creates compliance, audit, safety, financial, or coordination risk.

Weak evidence must be labeled. Weak evidence can remain in daily findings, but it should not be promoted into the living catalog until the buyer, recurrence, and business value are clear.

## CODE STYLE AND NAMING CONVENTIONS

The current repository is documentation-first. Future code must follow these baseline rules:

- Prefer explicit, idiomatic code over clever abstractions.
- Avoid premature generalization.
- Keep modules small and purpose-specific.
- Prefer structured parsers and data models over ad hoc string manipulation when the standard toolchain makes that practical.
- Name files and functions after the workflow or domain concept they serve.
- Keep implementation files around 300 lines or less when splitting improves clarity and ownership.
- Do not apply the 300-line guideline to documentation files, `docs/**`, `.kit/**`, or `.kit.yaml`.
- Comments should explain non-obvious decisions, not restate the code.
- Do not introduce a dependency unless it removes meaningful maintenance burden or provides a proven domain primitive.

Research artifact naming:

- Daily findings: `findings/YYYY-MM-DD.md`.
- Living catalog: `ideas/business-ideas.md`.
- Feature specs: `docs/specs/<numeric-slug>/SPEC.md` when Kit-managed feature work is needed.
- Project progress summary: `docs/PROJECT_PROGRESS_SUMMARY.md`.

## DEPENDENCIES AND TOOLING

Current durable tooling:

- Git and GitHub for source control and pull request delivery.
- Kit-managed repo configuration in `.kit.yaml`.
- Markdown as the canonical artifact format.
- GitHub Actions Pages for publishing the committed static `public/` artifact.
- Public web sources for research evidence.
- `rg` for repository search.
- `git diff --check` for whitespace and patch sanity.

Current imported Kit rulesets:

- `github-pr-delivery`
- `kit-capabilities-usage`
- `safety-guardrails`
- `work-lane-gating`

There are currently no runtime dependencies, package manager dependencies, databases, services, queues, or application frameworks.

## NON-NEGOTIABLE CONSTRAINTS

### Kit-Managed Baseline Rules

<!-- BEGIN KIT-MANAGED BASELINE RULES -->
- Treat `docs/CONSTITUTION.md` as the canonical project contract.
- Keep `AGENTS.md`, `CLAUDE.md`, and `.github/copilot-instructions.md` aligned with the repo-local docs tree.
- Prefer implementation/source code files around 300 lines or less when splitting improves clarity and ownership.
- Do not apply the code-file size guideline to documentation files, all `docs/**`, all `.kit/**`, or `.kit.yaml`.
- Do not split or rewrite docs, generated state, or Kit config artifacts solely because they exceed 300 lines.
<!-- END KIT-MANAGED BASELINE RULES -->

### Research Constraints

- Do not use private, gated, or login-only communities as source material.
- Do not store personal identifiers.
- Link every cataloged idea to supporting source material.
- Do not overstate weak evidence.
- Do not report an opportunity unless recurrence, meaningful cost/risk, and a plausible buyer are present.
- Do not recommend generic chatbots, generic copilots, generic AI assistants, "Uber for X", or marketplace ideas without evidence of marketplace failure.
- Do not treat startup trends, AI hype, or consumer novelty as sufficient evidence.

### Repository Constraints

- Only modify `findings/*`, `ideas/*`, `README.md`, `docs/**`, and agent routing docs when the task is research or process documentation.
- Do not modify application code, build files, dependencies, configuration, infrastructure, or unrelated docs during research-only runs.
- If application code is added later, research automation still must not modify code or runtime configuration.
- Historical findings files from previous dates are immutable.
- If `findings/YYYY-MM-DD.md` already exists for the current date, update that file instead of creating a second file.
- `PROJECT_PROGRESS_SUMMARY.md` must reflect the highest completed artifact per feature at all times. In this repo, the canonical path is `docs/PROJECT_PROGRESS_SUMMARY.md`.

## WORKFLOW CLASSIFICATION

Classify before acting.

### Spec-Driven (Formal)

Use for new product features, substantial architecture, workflow automation, data model changes, or behavior that needs durable acceptance criteria.

Canonical artifact:

- `docs/specs/<feature>/SPEC.md`

Required sections should cover requirements, assumptions, acceptance criteria, implementation plan, task checklist, validation map, reflection, delivery, and evidence. Feature front matter must keep `workflow_version`, `phase`, references, relationships, and skills current.

### Ad Hoc (Lightweight)

Use for contained docs changes, small research updates, reviews, typo fixes, and narrow maintenance.

Workflow:

1. Understand.
2. Edit the minimum relevant files.
3. Verify formatting, evidence, and diff scope.

Do not create feature specs for routine research updates or standalone documentation edits.

### PR Delivery

This is a Kit-managed repository. Before any issue, branch, staging, commit, push, or PR mutation, load the repo-local delivery rules and resolve the delivery contract. Repo-local rules outrank global GitHub defaults.

Documentation-only work must not be forced into a branch or PR workflow unless the user explicitly asks for delivery.

## IMPLEMENTATION STRATEGY

### Near Term

- Keep the repository as a clean research corpus.
- Improve the repeatability of daily research runs.
- Strengthen existing ideas before adding near-duplicates.
- Keep the top opportunities grounded in direct evidence and buyer clarity.
- Fill durable references only when knowledge becomes stable enough to reuse.

### Medium Term

- Add lightweight validation helpers only if manual table maintenance becomes error-prone.
- Consider scripts for score calculation, table sorting, duplicate detection, and link checking.
- Keep generated or automated changes deterministic and reviewable.
- Add tests only when code exists or when validation scripts become part of the workflow.

### Long Term Vision

Narrowband should become a high-signal map of operational software opportunities across overlooked industries. It should make it easy to answer:

- What recurring workflow is painful?
- Who performs it?
- What do they use today?
- Why is the current solution insufficient?
- Who can buy software for it?
- How often does the workflow happen?
- What measurable value could a product create?
- Why could the business remain useful for 10 or more years?

If the project later grows into software, that software should serve the research process first: evidence intake, deduplication, scoring, source review, opportunity tracking, and progress reporting.

## PROJECT GOALS

- Build a durable catalog of validated, evidence-backed software business opportunities.
- Keep source material traceable and reviewable.
- Identify workflows with measurable business value and plausible buyers.
- Favor operational, compliance, audit, reporting, documentation, reconciliation, coordination, inventory, scheduling, procurement, and asset-tracking workflows.
- Maintain a repeatable research process that can run every weekday without degrading evidence quality.
- Preserve a clean historical record of what was found on each day.

## NON-GOALS

- This is not a consumer startup idea list.
- This is not an AI trend tracker.
- This is not a growth-hacking, quick-profit, or marketplace-ideation repo.
- This is not a place for private or gated community scraping.
- This is not a generic chatbot idea generator.
- This is not currently an application runtime or deployable product.
- This is not a replacement for source review; every idea still needs supporting evidence.

## VALIDATION EXPECTATIONS

For documentation/research changes:

- Confirm changed files are within the requested scope.
- Run `git diff --check` or equivalent whitespace validation.
- For static site changes, confirm `public/index.html`, `public/assets/styles.css`, `public/CNAME`, and `public/.nojekyll` are present and internally consistent.
- Review tables for expected columns and sort order.
- Verify source links are present for cataloged opportunities.
- Confirm weak evidence is labeled.
- Confirm no secrets, private identifiers, or gated content were added.

For future code changes:

- Add focused tests proportional to risk.
- Run the smallest relevant checks first, then broader checks when shared behavior changes.
- State skipped validation clearly.
- Never claim tests passed unless they ran.

## DEFINITIONS

- Opportunity: A potential software business that solves a recurring, costly workflow for an identifiable buyer.
- Workflow pain: A repeated operational process that consumes time, money, attention, or creates risk.
- Strong evidence: Repeated source-backed evidence that a workflow pain recurs and has business value.
- Weak evidence: A plausible signal that lacks enough recurrence, cost, buyer clarity, or independent support.
- Buyer: The role or organization with budget authority to purchase or approve software.
- Current solution: The tools, workarounds, or manual processes users rely on today.
- Founder Advantage: Existing expertise, network, credibility, distribution, or unfair access relevant to the opportunity.
- Daily findings: The immutable dated research report for one automation run.
- Living catalog: The deduplicated, sorted opportunity table in `ideas/business-ideas.md`.
