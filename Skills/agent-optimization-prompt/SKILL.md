---
name: agent-optimization-prompt
description: Create, audit, modernize, and validate Codex agent prompts, sub-agent briefs, AGENTS.md files, and SKILL.md instructions. Use when reducing prompt bloat, removing duplicated or conflicting instructions, migrating older agent guidance, designing a lean sub-agent brief, or reviewing prompt quality while preserving required behavior and safety boundaries.
---

# Agent Optimization Prompt

Optimize agent instructions for clear outcomes, concrete constraints, and maintainable behavior. Treat brevity as a means to clarity, not an independent goal.

## Select the mode

- **Audit:** Assess an existing prompt without changing it.
- **Optimize:** Produce a complete replacement that preserves intended behavior.
- **Migrate:** Update older prompting patterns while retaining valid project-specific instructions.
- **Create:** Write a new agent or sub-agent brief from a task and its operating context.
- **Validate:** Check a proposed prompt for ambiguity, gaps, conflict, and unnecessary instruction load.

Use the narrowest mode that fulfills the request. Read the target files and relevant project guidance before judging their contents.

## Audit workflow

1. Extract the objective, inputs, outputs, constraints, authority boundaries, required tools/files, and completion conditions.
2. Group overlapping rules and identify conflicts, ambiguity, stale assumptions, and instructions that cannot be verified or followed.
3. Classify each instruction as essential, useful context, redundant, obsolete, or harmful.
4. Retain requirements that protect safety, correctness, privacy, user consent, repository conventions, or externally visible behavior—even if they add length.
5. Replace behavioral coaching and repeated reminders with specific outcomes, constraints, and acceptance criteria where doing so preserves behavior.

## Authoring rules

- State the objective and successful result early.
- Specify only context the agent cannot reliably infer from the task or repository.
- Define observable completion criteria and essential boundaries.
- Name files, tools, APIs, or commands only when they are truly required.
- Put durable project rules in the appropriate project instruction file; keep task-local details in the task prompt.
- Prefer one authoritative rule over repeated versions of the same rule.
- Write direct, imperative instructions.
- Keep related constraints together and order the workflow only when the order matters.

Do not use generic encouragement such as "think carefully," "be thorough," or "take a deep breath" as a substitute for requirements. Do not request hidden reasoning. Do not claim compatibility with a particular model version unless it is evidenced by applicable official guidance.

## Sub-agent briefs

For a sub-agent, include only:

1. **Objective:** the bounded result to deliver.
2. **Scope:** files, systems, and exclusions.
3. **Constraints:** safety, authority, compatibility, and non-negotiable requirements.
4. **Evidence:** the tests, inspection, or artifacts required to support the result.
5. **Handoff:** the concise result format and any unresolved decisions.

Give enough context to act independently, but do not leak a preferred diagnosis or solution into an investigative task. Preserve the user's approval boundaries; a lean brief must not authorize external, destructive, paid, or material scope-changing actions that the user did not authorize.

## Output format

For an audit or migration, provide:

1. **Assessment:** objective, material strengths, risks, and any behavior that must be preserved.
2. **Optimized prompt:** a complete, ready-to-use replacement unless the user requested recommendations only.
3. **Change summary:** what was removed, consolidated, clarified, or added, with the reason.
4. **Validation notes:** remaining ambiguity, assumptions, and recommended checks.

For a new prompt, provide the ready-to-use prompt and a short note on the included boundaries and acceptance criteria.

## Completion check

Before finishing, confirm that the result has one clear objective, no duplicated or contradictory rules, explicit success criteria, and no loss of required safety or project-specific behavior. Do not invent token-saving estimates; quantify only when a real before-and-after measurement is available.
