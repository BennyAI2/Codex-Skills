---
name: complexity-calibration
description: Assess the proportionate engineering rigor, expertise, and model capability before starting a user task. Use as the initial reflection phase for implementation, debugging, refactoring, planning, and other execution work to prevent overengineering and unnecessary model cost. Stay silent when the current model fits; before acting, ask the user to switch only when another available model is materially better suited.
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

## Keep Solution Choice Out of Scope

Judge only the engineering rigor and model capability needed to carry out the task. Do not select, compare, or redesign technical solutions or architectures. Respect the user's selected option and any solution-selection skill as the authority for that decision.

## Check Model Fit

Compare the required effort with the currently selected model only after calibration:

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
