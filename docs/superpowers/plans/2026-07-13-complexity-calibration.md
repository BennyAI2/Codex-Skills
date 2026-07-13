# Complexity Calibration Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create and install a Codex skill that calibrates engineering rigor and recommends a model switch only when materially beneficial.

**Architecture:** Keep the skill self-contained: `SKILL.md` contains the workflow and guardrails, and generated `agents/openai.yaml` provides UI metadata. It has no runtime dependencies; structural validation occurs before installation.

**Tech Stack:** Markdown, YAML, Python skill-creator utilities, Git.

## Global Constraints

- Create the repository skill at `D:\codex\Custom Skills\Skills\complexity-calibration`.
- Do not select, compare, or redesign technical solutions or architectures.
- Preserve user-selected options and solution-selection skills as the authority for solution choice.
- Stay silent when the current model is appropriate.
- Request a model switch only for a material fit difference and only among models available in the current interface.

---

### Task 1: Create and validate the repository skill

**Files:**
- Create: `D:\codex\Custom Skills\Skills\complexity-calibration\SKILL.md`
- Create: `D:\codex\Custom Skills\Skills\complexity-calibration\agents\openai.yaml`

**Interfaces:**
- Consumes: `D:\codex\Custom Skills\docs\superpowers\specs\2026-07-13-complexity-calibration-design.md`.
- Produces: a discoverable `complexity-calibration` skill with implicit invocation enabled.

- [ ] **Step 1: Initialize the skill directory and generated UI metadata**

Run:

```powershell
python C:\Users\benny\.codex\skills\.system\skill-creator\scripts\init_skill.py complexity-calibration --path 'D:\codex\Custom Skills\Skills' --interface 'display_name=Complexity Calibration' --interface 'short_description=Scale engineering effort to task complexity' --interface 'default_prompt=Use $complexity-calibration to assess the required engineering rigor and model fit before starting this task.'
```

Expected: the skill directory contains `SKILL.md` and `agents\openai.yaml`.

- [ ] **Step 2: Replace the template with the approved workflow**

Use frontmatter containing only `name: complexity-calibration` and a description that triggers on implementation, debugging, refactoring, and planning tasks. Write imperative workflow instructions to classify required engineering effort, select proportionate investigation/planning/testing/review, keep solution choice out of scope, and make model-change prompts only for material mismatches.

- [ ] **Step 3: Validate the skill folder**

Run:

```powershell
python C:\Users\benny\.codex\skills\.system\skill-creator\scripts\quick_validate.py 'D:\codex\Custom Skills\Skills\complexity-calibration'
```

Expected: validation exits with code 0 and no naming or frontmatter errors.

- [ ] **Step 4: Commit the repository skill**

Run `git add Skills/complexity-calibration`, then run `git commit -m "Add complexity calibration skill"`.

Expected: Git records the reusable skill and its interface metadata.

### Task 2: Install and verify the Codex copy

**Files:**
- Create: `C:\Users\benny\.codex\skills\complexity-calibration\SKILL.md`
- Create: `C:\Users\benny\.codex\skills\complexity-calibration\agents\openai.yaml`

**Interfaces:**
- Consumes: the validated repository skill.
- Produces: the installed skill at Codex's automatically discovered local-skills path.

- [ ] **Step 1: Copy the validated source to Codex's skills directory**

Run:

```powershell
Copy-Item -Recurse -Force 'D:\codex\Custom Skills\Skills\complexity-calibration' 'C:\Users\benny\.codex\skills\complexity-calibration'
```

Expected: the installed directory contains the same `SKILL.md` and `agents\openai.yaml`.

- [ ] **Step 2: Validate the installed copy and compare hashes**

Run the validator against `C:\Users\benny\.codex\skills\complexity-calibration`, then compare hashes of the source and installed files with `Get-FileHash` and `Compare-Object`.

Expected: validation exits with code 0 and the comparison produces no output.
