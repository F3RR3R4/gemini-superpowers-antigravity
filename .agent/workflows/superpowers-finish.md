---
description: Finalize work: verification, summary, follow-ups, manual validation steps.
---

# Superpowers Finish

Read and apply the `superpowers-finish` skill.

Output:
## Verification (commands + results if possible)
## Summary of changes
## Follow-ups (if needed)
## Manual validation steps (if applicable)

## Persist (mandatory)
Write the finish output to a unique timestamped file:
1. Obtain current timestamp: `YYYY-MM-DDTHHMM`
2. Target path: `.agent/artifacts/executions/execution-YYYY-MM-DDTHHMM-finish.md`

1) Copy the full finish markdown output.
2) Run:

```bash
# Example: python .agent/skills/superpowers-workflow/scripts/write_artifact.py --path .agent/artifacts/executions/execution-2026-03-13T1200-finish.md
python .agent/skills/superpowers-workflow/scripts/write_artifact.py --path .agent/artifacts/executions/execution-<TIMESTAMP>-finish.md
```

Provide the finish markdown as stdin to the command.

After writing, confirm it exists by listing artifacts/superpowers/.

If you cannot run the command, say so explicitly and instruct the user to copy/paste the finish output into artifacts/superpowers/finish.md.
Do not implement changes in this workflow. Stop after persistence.
