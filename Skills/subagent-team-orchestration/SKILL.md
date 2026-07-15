---
name: subagent-team-orchestration
description: Coordinate durable specialist subagent teams for multi-part project work. Use only after the user chooses a subagent-driven workflow over a linear workflow, or explicitly asks to form an agent team. Require approval of the proposed fixed team before implementation, keep the thread agent as coordinator, and require approval before adding a specialist later.
---

# Subagent Team Orchestration

Use a stable, communicating team rather than creating a new isolated subagent for every task. The thread agent is the head coordinator: it owns project direction, integration, user communication, and all team-composition decisions.

## Form the initial team

Before spawning implementation agents:

1. Analyze the project requirements, workstreams, dependencies, risks, and expected handoffs.
2. Choose the smallest fixed set of specialized roles that covers the work. Give each role a durable responsibility, clear boundary, expected deliverables, and coordination partners.
3. Present the team to the user for approval. Do not begin subagent implementation until the user approves it.

Use a concise proposal such as:

| Role | Owns | Coordinates with |
| --- | --- | --- |
| Project coordinator | Plan, sequencing, integration, user updates | Every role |
| Backend specialist | APIs, data, service logic | Frontend and QA |
| Frontend specialist | UI, client integration | Backend and QA |
| QA specialist | Verification strategy and regression checks | Every implementation role |

Adapt the roles to the project; do not propose generic roles that have no concrete responsibility. Prefer fewer agents with complementary ownership over a large roster or one agent per ticket.

## Anchor the goal and verification

Before implementation, state the user-visible goal, definition of done, and a small verification matrix. Assign each acceptance criterion one primary owner and one primary check. Implementation roles verify their scoped work; assign integration verification to one approved role rather than asking every agent to repeat it.

Require handoffs to report only the outcome, evidence, affected interfaces, and one next action. The coordinator closes a criterion once its assigned evidence passes. Reopen it only when a relevant change or new evidence invalidates that result.

## Coordinate the approved team

After approval, create only the approved roles. Maintain a shared, current view of:

- the project goal, constraints, and acceptance criteria;
- ownership, interfaces, dependencies, and handoffs;
- decisions, discoveries, blockers, and verification results.

Route relevant findings between specialists promptly, either through direct agent messages or the coordinator. Ask agents to report changes that affect another role before that work is integrated. Reassign work inside the approved team when its existing expertise covers it; do not create a new agent merely because the next task is different.

Keep coordination active: sequence dependent work, reconcile conflicting recommendations, verify integrated results, and give the user coherent project-level updates rather than a set of disconnected agent reports.

At each material handoff, re-state the goal, completed acceptance evidence, and the single next action that advances the goal. Stop or redirect work that no longer serves an open acceptance criterion. Do not create parallel self-review, re-testing, or research loops without a concrete new discriminator, failed check, or changed dependency.

## Preserve a Git record

When the project directory is a Git repository, make the team’s work understandable from Git as well as from chat:

1. Inspect the repository status before work and preserve unrelated user changes.
2. Maintain a clear record of completed work with focused commits, meaningful commit messages, and appropriate branches or pull requests when the project workflow uses them.
3. Ensure commits identify the user-visible change and, when useful, the specialist role or workstream that produced it. Do not bundle unrelated work into one commit.
4. Include relevant verification results in the commit, pull request, or coordinator handoff so the user can trace what changed and how it was checked.

The coordinator owns this record. Do not stage, commit, push, or rewrite unrelated changes, and do not publish externally without the user’s authorization.

## Add a specialist only with approval

When a later need falls materially outside the approved team’s expertise, pause before adding anyone. Explain:

- why the current team cannot responsibly cover the work;
- the proposed specialist’s defined role and deliverables;
- how it will coordinate with the existing team; and
- the cost, risk, or delay avoided by adding it.

Ask for the user’s approval, then add the specialist only after approval. If the need can be handled by an existing role, proceed with that role instead.

## Boundaries

- Do not use this workflow when the user chose or needs a linear workflow.
- Do not treat user approval of subagent-driven work as approval for external, irreversible, or scope-expanding actions.
- Do not let specialist agents independently expand the team without coordinator and user approval.
- Keep the team roster and responsibilities visible in substantive project updates when they change.
- Do not use more verification than the agreed acceptance criteria require; the coordinator decides when the evidence is sufficient to close the work.
