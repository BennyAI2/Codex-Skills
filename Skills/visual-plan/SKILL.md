---
name: visual-plan
description: Turn a complex or review-sensitive implementation direction into a concise, native Codex visual plan or maintained local HTML plan page with diagrams, file maps, and targeted wireframes. Use when the user asks for a visual plan, visual HTML plan page, or when an ongoing moderate/high-risk project needs human alignment and a clear visual record of progress. Skip trivial, unambiguous changes.
---

# Visual Plan

Create a scannable review artifact that makes the implementation direction easier to understand than prose alone. For an ongoing project, prefer a standalone local HTML plan page when it will remain useful as the project progresses. Keep it native to the current Codex context: use self-contained HTML/CSS, Markdown, Mermaid, tables, and local artifacts as appropriate. Do not require a hosted plan service, MCP connector, external account, or upload.

## Decide whether to plan visually

Run the complexity calibration first. Use a visual plan when the work is moderate or high complexity, the user requests one, or a diagram, file map, or wireframe would materially improve a decision. Skip it for routine, well-specified, reversible changes.

Inspect the relevant repository files and constraints before drafting. Ground the plan in real paths, symbols, contracts, and existing patterns; distinguish verified facts from assumptions.

## Respect the existing decision flow

- Let `approval-decision-quality` decide whether a user choice or approval is genuinely needed. A visual plan must not turn an already-authorized, dominant path into needless approval friction.
- If a material architecture, scope, budget, public, irreversible, or user-preference decision remains, present it clearly with the recommended default and wait for the required direction before implementation.
- In a linear workflow, the coordinator owns the visual plan and keeps it current. If the user selected subagent-driven work, use only the approved team from `subagent-team-orchestration`. Include a visual-plan steward in the proposed initial team when a persistent HTML plan needs dedicated design and maintenance; otherwise the coordinator owns it. Do not spawn an exploratory, review, or visual-plan agent outside the approved team. If a dedicated steward becomes necessary later, request the user's approval before adding that role.
- If debugging is stalled, let `debug-loop-recovery` establish evidence before visualizing a new fix direction.

## Build the plan

Keep planning read-only except for the plan artifact itself. Include only sections that make the direction clearer:

1. **Outcome and scope:** user-visible result, non-goals, assumptions, and acceptance criteria.
2. **Approach:** the recommended path and why it fits existing code.
3. **Visuals:** use a Mermaid flow, sequence, state, component diagram, or targeted HTML wireframe only when it clarifies a material relationship. For a persistent HTML page, use a responsive, self-contained layout with clear project status, diagrams, file-impact cards, open decisions, and progress milestones.
4. **Impact map:** files, symbols, contracts, data changes, and dependencies to reuse or modify.
5. **Execution and verification:** ordered implementation steps, targeted checks, risks, and rollback considerations.
6. **Open decisions:** only unresolved choices that need the user's authority; include a recommendation for each.

Prefer one clear path over a menu of equal-looking options. Keep diagrams readable and omit visual decoration that does not improve a decision.

## Present and continue

Present the plan in the current task by default. Create a local HTML plan page when the user asks for one, or when an ongoing multi-stage project needs a maintained visual review surface. Follow the project's plan-file convention; if none exists, propose an appropriate local path before adding one. Do not host or share the page unless the user authorizes it.

For a maintained page, update it after every material scope decision, completed milestone, integration result, verification finding, or blocker. Keep the current state, next milestone, open decisions, and evidence links accurate so it remains useful to the user and the approved team throughout the project.

When the plan exposes a real approval boundary, ask for the specific decision and wait. Otherwise state the plan, proceed with the authorized work, and keep the plan current if scope materially changes.

Before implementation, re-check the plan against the requested outcome, repository evidence, and applicable safety boundaries. Do not publish, deploy, or make other externally consequential changes merely because the plan describes them.
