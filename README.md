# Codex Skills

A small collection of reusable custom skills for Codex. Each folder in [`Skills/`](Skills/) contains one skill and its `SKILL.md` instructions.

## Skill index

| Skill | Purpose |
| --- | --- |
| [`approval-decision-quality`](Skills/approval-decision-quality/SKILL.md) | Helps Codex decide whether it can safely proceed with the clearly best option or needs the user's decision or authority. |
| [`debug-loop-recovery`](Skills/debug-loop-recovery/SKILL.md) | Breaks unproductive debugging loops with an evidence ledger, focused research, and a deliberately testable next fix. |

## Before publishing updates

1. Add or update the appropriate `Skills/<skill-name>/SKILL.md` file.
2. Update the table above whenever a skill is added, removed, renamed, or its purpose materially changes.
3. Review every `SKILL.md` for private information before committing. Remove or replace personal names, email addresses, usernames, credentials, API keys, access tokens, local machine paths, account IDs, private URLs, customer or employer information, and internal project details unless they are intentionally public and necessary.
4. Check the staged changes and commit only the reviewed files.

The skill instructions should use generic placeholders such as `<USER_EMAIL>`, `<PROJECT_PATH>`, and `<API_KEY>` where an example needs sensitive-looking data.
