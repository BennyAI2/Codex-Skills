---
name: visual-plan
description: Turn a complex or review-sensitive implementation direction into a concise, native Codex visual plan using Markdown, Mermaid, file maps, and targeted wireframes. Use when the user asks for a visual plan or when moderate/high-risk multi-file, architecture, data-flow, workflow, or UI work needs human alignment before implementation. Skip trivial, unambiguous changes.
---

# Visual Plan

Create a scannable review artifact that makes the implementation direction easier to understand than prose alone. Keep it native to the current Codex context: use Markdown, Mermaid, tables, and local artifacts only when requested. Do not require a hosted plan service, MCP connector, external account, or upload.

## Decide whether to plan visually

Run the complexity calibration first. Use a visual plan when the work is moderate or high complexity, the user requests one, or a diagram, file map, or wireframe would materially improve a decision. Skip it for routine, well-specified, reversible changes.

Inspect the relevant repository files and constraints before drafting. Ground the plan in real paths, symbols, contracts, and existing patterns; distinguish verified facts from assumptions.

## Respect the existing decision flow

- Let `approval-decision-quality` decide whether a user choice or approval is genuinely needed. A visual plan must not turn an already-authorized, dominant path into needless approval friction.
- If a material architecture, scope, budget, public, irreversible, or user-preference decision remains, present it clearly with the recommended default and wait for the required direction before implementation.
- If the user selected subagent-driven work, use only the approved team from `subagent-team-orchestration`. Do not spawn an exploratory or review subagent outside that team; have the coordinator or an existing approved role perform the review.
- If debugging is stalled, let `debug-loop-recovery` establish evidence before visualizing a new fix direction.

## Build the plan

Keep planning read-only. Include only sections that make the direction clearer:

1. **Outcome and scope:** user-visible result, non-goals, assumptions, and acceptance criteria.
2. **Approach:** the recommended path and why it fits existing code.
3. **Visuals:** use a Mermaid flow, sequence, state, or component diagram only when it clarifies a material relationship. Use a compact text wireframe for UI states when a picture materially helps.
4. **Impact map:** files, symbols, contracts, data changes, and dependencies to reuse or modify.
5. **Execution and verification:** ordered implementation steps, targeted checks, risks, and rollback considerations.
6. **Open decisions:** only unresolved choices that need the user's authority; include a recommendation for each.

Prefer one clear path over a menu of equal-looking options. Keep diagrams readable and omit visual decoration that does not improve a decision.

## Present and continue

Present the plan in the current task by default. Write a plan file only when the user asks to preserve it in the project, and follow that repository’s conventions.

When the plan exposes a real approval boundary, ask for the specific decision and wait. Otherwise state the plan, proceed with the authorized work, and keep the plan current if scope materially changes.

Before implementation, re-check the plan against the requested outcome, repository evidence, and applicable safety boundaries. Do not publish, deploy, or make other externally consequential changes merely because the plan describes them.
