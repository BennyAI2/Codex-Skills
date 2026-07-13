# Complexity Calibration Skill Design

## Purpose

Provide a brief initial calibration for engineering tasks so Codex applies a proportionate level of implementation rigor and recommends a more suitable available model only when that would materially improve cost, speed, or reliability.

## Scope

The skill applies before implementation, debugging, refactoring, and planning work. It assesses:

- implementation complexity, uncertainty, risk, and required expertise;
- the proportionate level of investigation, planning, testing, and review; and
- fit between the task and the currently selected model.

It does not select, compare, or redesign technical solutions and architectures. Existing solution-selection skills remain responsible for that decision.

## Behavior

1. Classify the task as routine, moderate, or high-complexity based on the engineering work required, not the apparent importance of the request.
2. Match the execution process to that classification. Routine work should use focused inspection, a targeted implementation, and proportionate verification. Higher-complexity work can justify deeper investigation, design, staged validation, or specialist expertise.
3. Assess the current model against the required reasoning depth, repository breadth, ambiguity, and risk.
4. Continue without a user-facing note when the current model is suitable.
5. Before task execution, briefly ask the user to switch models only when an available smaller or larger model is materially better suited. Recommendations must be conditional on models available in the current interface; Terra and Luna are examples of lighter options, not hard-coded capability claims.

## Boundaries

- Do not use model changes as an automatic response to any task size.
- Do not interrupt for marginal savings or speculative model comparisons.
- Do not downgrade the rigor required for safety-sensitive, destructive, production, security, or irreversible actions.
- Do not replace task-specific skills, solution-selection workflows, or user authority.

## Validation

Validate the skill metadata and folder structure. Forward-test with representative routine, moderate, and high-complexity tasks to confirm that it stays silent for an appropriate current model and pauses only for a material model-fit change.
