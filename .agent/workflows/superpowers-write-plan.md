---
description: Superpowers plan gate. Writes a small-step plan with files + verification. Must ask for approval before coding.
---

# Superpowers Write Plan (Gate)

All plan output MUST be in **English**.

## Task
Plan for this task (exactly as provided by the user):
**{{input}}**

If `{{input}}` is empty or missing, ask the user to restate the task in one sentence and STOP.

## Rules
- DO NOT edit code.
- You may read files to understand context, but produce the plan and then stop.
- Plan steps must be small (2–10 minutes each) and include verification commands.

## Output format (use exactly)
## Goal
## Assumptions
## Plan
(Each step must include: Files, Change, Verify)
## Risks & mitigations
## Rollback plan

## Persist (mandatory)
Write the plan output to a unique timestamped file:
1. Obtain current timestamp: `YYYY-MM-DDTHHMM`
2. Target path: `.agent/artifacts/plans/plan-YYYY-MM-DDTHHMM.md`

Create the folder if needed.
After writing, confirm it exists by listing `.agent/artifacts/plans/`.

## Approval
Ask:
**Approve this plan? Reply APPROVED if it looks good.**

If the user replies APPROVED:
- Do NOT implement yet.
- Reply: **"Plan approved. Run `/execute-plan` to begin implementation."**

## Persist (mandatory)
After generating the plan content above, you MUST write it to disk:

1) Copy the full plan markdown output.
2) Run:

```bash
# Example: python .agent/skills/superpowers-workflow/scripts/write_artifact.py --path .agent/artifacts/plans/plan-2026-03-13T1200.md
python .agent/skills/superpowers-workflow/scripts/write_artifact.py --path .agent/artifacts/plans/plan-<TIMESTAMP>.md
```

Provide the plan markdown as stdin to the command.

After writing, confirm it exists by listing artifacts/superpowers/.

If you cannot run the command, say so explicitly and instruct the user to copy/paste the plan output into the timestamped plan file.
Do not implement changes in this workflow. Stop after persistence.
