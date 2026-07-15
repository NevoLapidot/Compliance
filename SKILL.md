---
name: instruction-compliance
description: >-
  Post-task quality gate that verifies ALL user instructions were followed and
  any saved lessons/preferences were applied. Extracts every instruction from
  chat history, checks each against actual output, auto-corrects gaps, and
  reports what was fixed.
  MANDATORY TRIGGERS: verify output, check compliance, instruction check, did
  you follow all instructions, quality check, verify my output, compliance
  check, end of task.
  Auto-triggers at end of every substantive task. Use for: extracting
  instructions, verifying compliance, detecting contradictions, auto-correcting
  outputs, checking saved preferences.
---

# Instruction Compliance Checker

A quality gate that ensures Claude actually did what the user asked — every format, every requirement, every constraint. No silent omissions.

## Why This Exists

Claude sometimes misses specific instructions buried in long conversations, or forgets a format requirement mentioned early on, or doesn't apply a lesson it should have learned from prior sessions. This skill solves that by systematically extracting every instruction and checking each one against the actual output. It catches drift, omissions, and half-followed directions before the user has to.

## Configuration

This skill references a few optional, environment-specific paths and standards. Set these once for your setup, or leave them unset to skip the related checks:

- `<lessons_learned_path>` — a central file where recurring preferences/patterns are recorded (e.g. `~/notes/_system/lessons_learned.md`). If you don't keep one, skip Phase 2.
- `<session_logs_dir>` — a directory where per-session logs are stored, if you use session logging. If you don't, skip the related check in Phase 3.
- `<project_standards>` — any project- or organization-specific format, citation, or domain standards the output must follow (e.g. a house style guide, a regulatory citation format, a document template). If none apply, skip that check in Phase 3.

Wherever these placeholders appear below, substitute your own values or remove the check.

## When This Runs

Two modes:

1. **Automatic** — At the end of every substantive task. If Claude produced deliverables (files, analyses, reports), this runs as a final quality gate.
2. **Manual** — When the user says things like "verify output", "check compliance", "did you follow everything", "quality check".

---

## The Compliance Check Process

### Phase 1: Extract Instructions

Go through the ENTIRE conversation history — every user message, from the first to the most recent — and extract all instructions. An "instruction" is anything the user said that implies a requirement for the output.

**What counts as an instruction:**

- **Explicit directives**: "Make it a table", "Include a disclaimer", "Use the official reference numbers"
- **Format requirements**: "Put it in a spreadsheet", "Use the template from last time", "Bold the headers"
- **Constraints**: "Only these categories", "No more than 2 pages", "Don't include X"
- **Implicit expectations**: If the user said "like last time" — check prior session logs or context for what "last time" looked like
- **Corrections mid-conversation**: "Actually, change X to Y" — the LATEST version of any instruction takes precedence
- **Conditional instructions**: "If X, then do Y" — verify the condition and whether Y was applied
- **Negative instructions**: "Don't include Z", "Skip the intro" — verify Z is truly absent
- **Referenced standards**: "Follow the house format" — check the relevant standard/reference for what that means

**Organize into a checklist:**

```
## Instruction Extraction — {Task Name}

### Task-Specific Instructions
| # | Instruction | Source | Type | Priority |
|---|-------------|--------|------|----------|
| 1 | {instruction text} | {User message / turn reference} | Format/Content/Constraint/Correction | Must/Should |

### Contradictions Detected
| Instruction A | Instruction B | Resolution |
|---------------|---------------|------------|
| {earlier instruction} | {later instruction} | {Ask user / Use latest} |
```

**Contradiction handling**: If the later instruction clearly supersedes the earlier one (e.g., "Actually, make it 3 columns not 5"), apply the later one and note it. If genuinely ambiguous, STOP and ask the user which one takes precedence. Do not guess.

### Phase 2: Check Lessons Learned

If you maintain a central lessons/preferences file, read it:

```
<lessons_learned_path>
```

If it doesn't exist, skip this phase and note it in the report.

If it exists, scan for lessons relevant to the current task. A lesson is relevant if:
- It mentions a preference that applies to the current output type (document formatting, table structure, tone)
- It describes a workflow pattern the user expects
- It contains domain-specific context relevant to the work
- Its category matches the current work (OUTPUT_PREFERENCE, WORKFLOW, DOMAIN_CONTEXT, COMMUNICATION, TOOL_USAGE)

Add relevant lessons to the checklist as additional requirements with source marked as "Lessons Learned".

**Also scan individual session logs** if the central file is thin. Look at recent session folders in `<session_logs_dir>` for log files that contain "Lessons Learned" or "Patterns Reinforced" sections.

### Phase 3: Check System Preferences

Users often have system-level or environment-level preferences. Check the ones that apply to your setup:

1. **Session logging** — If you use session logging, verify a log file was written to `<session_logs_dir>` following your naming convention, plus copies of generated files.
2. **Project / domain standards** — When the work involves specialized content, verify against `<project_standards>`, e.g.:
   - Correct identifiers and reference numbers
   - Citation integrity (no invented references)
   - Any required research or verification steps
   - A clear separation of facts vs. assumptions vs. analysis (no "black box" conclusions)
   - A hallucination red-flag checklist
3. **File delivery** — Verify final outputs were delivered to the expected location, with working links.
4. **Formatting preferences** — e.g. natural prose over bullet lists in conversation, minimal formatting unless requested.
5. **Additional required blocks** — If your workflow requires any standard block to be appended to certain output types (for example, a validity/assumptions statement on any output containing a judgment, recommendation, decision, or approval), verify it is present and complete. If it's missing, add it before continuing.

Add applicable system preferences to the checklist with source marked as "System Preferences".

### Phase 4: Verify Compliance

Go through each item in the checklist and verify it against the actual output.

**For each instruction:**

1. **Locate the output** — Which file, message, or artifact addresses this instruction?
2. **Check compliance** — Does the output fully satisfy the instruction?
3. **Grade it**:
   - `PASS` — Fully met
   - `PARTIAL` — Partially met (explain what's missing)
   - `FAIL` — Not met at all
   - `N/A` — Not applicable to the current output

**For file-based outputs**, actually READ the generated file to verify — do not rely on memory of what was written. Use the right tools:
- `.docx` → python-docx or markitdown to extract and check content
- `.xlsx` → openpyxl to read and verify structure/content
- `.pptx` → python-pptx to check slides
- `.pdf` → appropriate PDF reader
- `.md` / `.html` → Read directly

This is critical. The whole point of this skill is to catch things Claude thought it did but didn't. Reading the actual file is the only way to know for sure.

### Phase 5: Auto-Correct

For any instruction graded `PARTIAL` or `FAIL`:

1. **Assess fixability** — Can Claude fix this without changing the user's intent? Most format/content issues can be fixed. Ambiguous or intent-changing corrections should be asked about first.
2. **Fix it** — Regenerate or edit the output to comply with the instruction.
3. **Log the correction** — Record exactly what was changed, which instruction it addresses, and which file was modified.

After corrections, **re-run Phase 4 on the corrected items** to verify they now pass. This is not optional — sometimes a fix introduces a new issue or doesn't fully resolve the original one.

Keep iterating until all items are `PASS` or `N/A`. If after 3 correction attempts an item still fails, flag it for the user with an explanation of what's preventing compliance.

### Phase 6: Report

Present the compliance report. Concise but complete:

```markdown
## Compliance Report

**Task**: {description}
**Instructions Found**: {N total}
**From Lessons Learned**: {N additional}
**From System Preferences**: {N additional}

### Results Summary
| Status | Count |
|--------|-------|
| PASS | {X} |
| PARTIAL → Fixed | {Y} |
| FAIL → Fixed | {Z} |
| N/A | {W} |
| Asked User | {V} |

### Corrections Made
| # | Instruction | Issue | Fix Applied |
|---|-------------|-------|-------------|
| 1 | {instruction} | {what was wrong} | {what was fixed} |

### Contradictions Resolved
| Conflict | Resolution |
|----------|------------|
| {description} | {how resolved} |

### Lessons Learned Applied
| Lesson | Applied? | Notes |
|--------|----------|-------|
| {lesson} | Yes/No/N/A | {detail} |

**Verdict**: {ALL PASS / CORRECTIONS APPLIED / NEEDS USER INPUT}
```

---

## Handling Edge Cases

### Very Long Conversations
If the conversation is extremely long, prioritize:
1. Instructions from the MOST RECENT user messages (they may override earlier ones)
2. Instructions that were repeated (signal high importance)
3. Format/structural requirements (objectively verifiable)
4. Content requirements (what to include/exclude)

### Multi-File Outputs
Check each file against its relevant instructions. Some instructions are global ("use formal tone"), others target specific files ("the spreadsheet should have 3 tabs"). Map each instruction to the file(s) it applies to.

### No Files Produced
If the task was conversational (no files generated), verify:
- Was the response format correct?
- Were all parts of the question answered?
- Were negative instructions followed ("don't mention X")?
- Was the right level of detail provided?

### Instructions from Other Skills
If another skill was invoked, that skill's own output requirements also count as instructions. Read the relevant SKILL.md and verify its structural expectations were met.

### Contradictions Between Task Instructions and System Preferences
Task-specific instructions from the user always take precedence over system preferences. If the user says "just give me bullet points" in a task, that overrides the general system preference for prose. Note the override in the report.

---

## Integration with Session Logging

If you run a session-logging step, this skill should run BEFORE it, so the compliance report can be captured in the session log:

```markdown
## Instruction Compliance Check
- **Instructions Verified**: {N}
- **All Passed**: {Yes/No}
- **Corrections Applied**: {N}
- **Details**: [see compliance report]
```

---

## Quick Reference

```
INSTRUCTION COMPLIANCE FLOW
============================
1. EXTRACT  --> Scan full chat, pull every instruction
2. LESSONS  --> Read lessons file (if any), find relevant ones
3. SYSTEM   --> Check system/project preferences apply
4. VERIFY   --> Grade each instruction (PASS/PARTIAL/FAIL)
5. CORRECT  --> Auto-fix failures, re-verify
6. REPORT   --> Show what was found, fixed, flagged
7. ITERATE  --> If still non-compliant, keep fixing until clean
```
