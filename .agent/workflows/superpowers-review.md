---
description: Runs a Superpowers-style review pass with severity levels.
---

# Superpowers Review

All review output MUST be in **English**.

Read and apply the `superpowers-review` skill.

Output:
- Blockers
- Majors
- Minors
- Nits
- Summary + next actions

## Persist (mandatory)
Write the review output to a unique timestamped file:
1. Obtain current timestamp: `YYYY-MM-DDTHHMM`
2. Target path: `.agent/artifacts/reviews/review-YYYY-MM-DDTHHMM.md`

1) Copy the full review markdown output.
2) Run:

```bash
# Example: python .agent/skills/superpowers-workflow/scripts/write_artifact.py --path .agent/artifacts/reviews/review-2026-03-13T1200.md
python .agent/skills/superpowers-workflow/scripts/write_artifact.py --path .agent/artifacts/reviews/review-<TIMESTAMP>.md
```

Provide the review markdown as stdin to the command.

After writing, confirm it exists by listing artifacts/superpowers/.

If you cannot run the command, say so explicitly and instruct the user to copy/paste the review output into artifacts/superpowers/review.md.
Do not implement changes in this workflow. Stop after persistence.
