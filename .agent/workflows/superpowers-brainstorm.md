---
description: Superpowers brainstorm. Produces goal/constraints/risks/options/recommendation/acceptance criteria.
---

# Superpowers Brainstorm

## Task
Brainstorm for this task (exactly as provided by the user):
**{{input}}**

If `{{input}}` is empty or missing, ask the user to restate the task in one sentence and STOP.

## Acceptance criteria

## Persist (mandatory)
Write the brainstorm output to a unique timestamped file:
1. Obtain current timestamp: `YYYY-MM-DDTHHMM`
2. Target path: `.agent/artifacts/brainstorms/plan-YYYY-MM-DDTHHMM-brainstorm.md`

```bash
# Example: python .agent/skills/superpowers-workflow/scripts/write_artifact.py --path .agent/artifacts/brainstorms/plan-2026-03-13T1200-brainstorm.md
python .agent/skills/superpowers-workflow/scripts/write_artifact.py --path .agent/artifacts/brainstorms/plan-<TIMESTAMP>-brainstorm.md
```

Provide the brainstorm markdown as stdin to the command.

After writing, confirm it exists by listing artifacts/superpowers/.

If you cannot run the command, say so explicitly and instruct the user to copy/paste the brainstorm output into artifacts/superpowers/brainstorm.md.
Do not implement changes in this workflow. Stop after persistence.