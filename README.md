# Instruction Compliance
### A post-task quality gate that checks the agent actually did what you asked

---

## Why this exists

You can write the most careful instructions in the world into your system prompt — or your `CLAUDE.md`, or your standing preferences — and the agent will still quietly skip some of them. It isn't malice and it usually isn't a bad model; it's that nothing checks the finished work against everything you asked for.

The failure is familiar. In a long conversation, a requirement mentioned near the top gets buried. A format rule ("make it a table", "keep it under two pages") is acknowledged and then drifts. A negative instruction ("don't include X") slips through because absence is hard to notice. A mid-conversation correction ("actually, change it to Y") gets half-applied. You only find out when you're reading the output — and the natural response, writing *more* rules, doesn't help, because the gap was never in what you wrote. It's that the output was never verified against it.

This skill closes that loop. It's the step that reads your instructions back and confirms each one actually landed.

## What it does

It runs as a final gate after a task — automatically, or whenever you say "verify this" / "did you follow everything". Six phases:

| Phase | What happens |
|---|---|
| **Extract** | Re-reads the entire conversation and pulls out *every* instruction — explicit directives, format requirements, constraints, negative instructions, conditionals, and mid-conversation corrections (latest version wins). |
| **Lessons** | Optionally checks a saved preferences/lessons file for standing patterns that apply to this output. |
| **System** | Checks environment- or project-level standards you've configured (house format, citation rules, delivery location, required boilerplate blocks). |
| **Verify** | Grades each instruction PASS / PARTIAL / FAIL / N/A — **by reading the actual generated file**, not by trusting what it thought it wrote. |
| **Correct** | Auto-fixes every PARTIAL and FAIL, then re-checks the fix. Iterates until clean or flags what it can't resolve. |
| **Report** | Returns a compact report: what was found, what was fixed, what needs your call. |

The design point that matters most: it opens the real output and inspects it. Catching "the thing the agent believed it did but didn't" only works if you look at the artifact, not the memory of making it.

This is a generalized, portable version — no personal paths, employer references, or private standards. Three optional config placeholders at the top of the skill (`<lessons_learned_path>`, `<session_logs_dir>`, `<project_standards>`) let you wire it to your own setup, or leave them unset to skip those checks.

## Get it

**Install:** [`instruction-compliance.skill`](./instruction-compliance.skill)
(or browse the source: [`SKILL.md`](./SKILL.md))

- **Claude apps (claude.ai / desktop):** Settings → Capabilities → Skills → upload the `.skill` file.
- **Claude Code:** unzip into `~/.claude/skills/`.

**Then just ask**, e.g.:

> "Before we finish — verify you followed every instruction in this thread and fix anything you missed."

Questions or ideas for it? Reach out on [LinkedIn](https://www.linkedin.com/in/nevol).

---

*This page and its materials are shared as general guidance, not legal, tax, or financial advice, and no advisor–client relationship is created by using them.*
