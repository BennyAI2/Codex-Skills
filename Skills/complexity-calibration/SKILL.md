---
name: complexity-calibration
description: Assess the proportionate engineering rigor, execution mode, expertise, and model capability before starting a user task. Use as the initial routing decision before drafting a plan or offering execution options for implementation, debugging, refactoring, planning, and other execution work. Prevent overengineering, unnecessary agent coordination, and unnecessary model cost; ask about a model switch only when another available model is materially better suited.
---

# Complexity Calibration

Calibrate the execution effort and model fit before taking task actions. Optimize for sufficient capability, not maximum capability.

## Calibrate Quietly

Assess four dimensions from the request and immediately available context:

- **Scope:** number of files, systems, and dependent steps likely involved.
- **Uncertainty:** clarity of the task, existing patterns, and unknowns that must be resolved.
- **Risk:** reversibility, production impact, security, data loss, compliance, and user harm.
- **Expertise:** depth of domain knowledge, debugging judgment, or architectural reasoning required.

Classify the required engineering effort:

| Level | Typical work | Proportionate execution |
| --- | --- | --- |
| Routine | Clear, isolated, reversible task with a known pattern | Focused inspection, targeted change, and direct verification |
| Moderate | Several related files, meaningful diagnosis, or integration work | Inspect relevant context, make a bounded plan, and run focused tests or checks |
| High | Ambiguous, high-risk, cross-system, security-sensitive, or irreversible work | Perform deeper investigation, use deliberate planning, and apply staged validation and review |

Do not add process merely because a task sounds important. Do not reduce safeguards required by risk.

## Choose execution mode before planning

Make the execution decision immediately after calibration and before drafting a plan, proposing agents, or asking how to proceed.

- **Inline execution:** Default to one focused agent when the work is bounded, one coherent workstream can inspect, change, and verify it, and coordination would add more cost than confidence.
- **Subagent team:** Recommend a fixed specialist team only when distinct, independently valuable workstreams or specialist expertise outweigh the coordination cost. If the user has not selected team work, ask only for the authority needed to form that team; do not present it as an equal alternative to a clearly better inline path.

Treat execution mode as a costed delivery decision, not a technical solution choice. Apply `approval-decision-quality`: state and use a dominant route with its rationale; ask only when the execution trade-offs are genuinely comparable or the user must authorize the team.

## State a useful execution profile

When calibration materially affects time, cost, reliability, execution mode, model/reasoning level, or the user asks for that assessment, state a short recommendation before the implementation plan:

- complexity level and the dominant reason;
- recommended execution mode and why it is proportionate;
- bounded verification approach; and
- model/reasoning recommendation when a meaningful, available alternative exists.

Do not defer a material execution or model recommendation until the user asks. Keep this profile silent when the current mode and model are plainly sufficient and no material saving or reliability difference exists.

## Set a verification budget

Before implementation, define the smallest evidence needed to show the requested outcome is complete. For each acceptance criterion, name one primary check and, in team work, one owner.

Run the least costly check that can establish the criterion. When that evidence passes, treat the criterion as closed. Re-run or broaden verification only when a relevant code, configuration, scope, environment, or dependency change invalidates the evidence, or when the result exposes a concrete new risk.

Do not repeat independent checks merely for reassurance, and do not turn every uncertainty into a second investigation. Re-anchor work to the requested outcome after each material result; stop when the agreed acceptance evidence is complete.

## Keep Solution Choice Out of Scope

Judge only the engineering rigor and model capability needed to carry out the task. Do not select, compare, or redesign technical solutions or architectures. Respect the user's selected option and any solution-selection skill as the authority for that decision.

## Check Model Fit

Compare the required effort with the currently selected model after calibration and execution routing:

1. Continue without mentioning models when the current model is sufficient.
2. Recommend a lighter available model only when the work is routine and the expected saving is material without reducing reliability.
3. Recommend a stronger available model only when the work needs materially deeper reasoning, broader context handling, specialist expertise, or stronger risk management.
4. Do not make a model recommendation for marginal differences, preferences, or speculative savings.
5. Name a model only when it is shown as available in the current interface or user-provided context. Treat Terra and Luna as examples, not fixed capability tiers.

When a material mismatch exists, pause before execution and ask concisely:

> This task needs **[lighter/stronger]** reasoning because **[task-specific reason]**. Switching to **[available model]** would be a better fit. Would you like to switch before I continue?

If availability or comparative capability is unknown, retain the current model and continue without a recommendation.

## Scale the Work

Use the classification to limit execution overhead:

- For routine work, avoid broad reconnaissance, elaborate design documents, speculative abstractions, and full-suite validation unless risk or repository policy requires them.
- For moderate work, investigate only the components that can affect the task and verify the changed behavior plus direct integrations.
- For high-complexity work, make the needed risk controls explicit and seek user direction where authority or scope is genuinely missing.

Recalibrate if new evidence materially changes scope, uncertainty, risk, or expertise requirements.
