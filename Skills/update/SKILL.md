---
name: update
description: Provide an explicit project-health checkpoint for long-running single-agent or approved multi-agent work. Use only when the user explicitly invokes $update (or an equivalent manual command). Report grounded progress, completion estimate, current work, blockers, and signs of overthinking, overengineering, or disproportionate delay. Apply one bounded corrective action when evidence supports it; require user approval before rewriting plans or scope.
---

# Update

Run only on explicit user invocation. Do not invoke automatically, schedule repeated self-checks, or treat this as permission to expand scope.

## Gather current evidence

Inspect only the evidence needed to understand the current state:

- original user goal, acceptance criteria, and approved plan;
- completed work, current work, blockers, and verification evidence;
- relevant repository or worktree state;
- for an approved agent team, each role's latest outcome, active task, and pending handoff.

Do not invent activity, progress, or agent state that cannot be observed.

## Report project health

Start with a concise status report:

| Item | Report |
| --- | --- |
| Goal | Original user-visible outcome and current scope |
| Completion | Estimated percentage plus confidence range and evidence basis |
| Completed | Material outcomes and accepted verification |
| In progress | One current action per active role or agent |
| Blocker | Concrete blocker, or "None" |
| Health | On track, at risk, or stalled |
| Next action | The single action most likely to advance the goal |

Estimate completion from accepted acceptance criteria and remaining work. Use ranges when uncertainty is meaningful, such as `65% complete (50-75% confidence)`. Do not use precise percentages as a substitute for evidence.

## Diagnose drift

Compare current activity with the original goal and acceptance criteria.

Flag a concern only when evidence supports it:

- **Overthinking:** repeated analysis, planning, or verification without a new discriminator or changed evidence.
- **Overengineering:** proposed work, abstraction, agents, tests, or infrastructure beyond the requested outcome or proportionate risk.
- **Disproportionate delay:** limited progress on a bounded task despite no material blocker.

State the specific evidence, impact, and recommended correction. If no concern is found, say so and continue the approved path.

## Correct course once

When a concern is found, use the narrowest applicable existing skill:

- Use `complexity-calibration` to reassess execution mode, model fit, and verification budget.
- Use `approval-decision-quality` only for a real authority or preference boundary.
- Use `subagent-team-orchestration` only through the approved team; do not create agents or expand the roster.
- Use `debug-loop-recovery` only when its failed-attempt threshold is met.
- Use targeted multi-query web research when an external, version-sensitive, or poorly understood issue is the actual blocker.

If one isolated, reversible, in-scope issue is holding up the task, make one minimal corrective change and run its primary verification.

If the evidence calls for a material plan rewrite, scope change, new team role, external action, or irreversible change, present the revised recommendation and wait for user approval before continuing.

Do not repeat this self-analysis in the same invocation unless the corrective action produces materially new evidence.

## Maintain shared status

If the project has a maintained visual plan page, update it only for a material health change, completed milestone, blocker, or approved correction. The status page observes work; it must not trigger additional research or verification.

## Finish

End with the current status, the completion estimate, what changed during this checkpoint, and the next action. Preserve user control over scope, budget, public communication, production changes, and destructive actions.
