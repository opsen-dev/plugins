---
name: spend
description: Summarise engineering spend and waste from opsen for this workspace. Use when the user asks for the opsen numbers, the monthly bill, or what to cut first.
---

Call `opsen_summary`, then `spend_by_source`. Reply with:

- Total monthly spend and what is paid for and not used, with the share.
- The three largest findings, each with its monthly cost and the one-line fix.
- Any budget that is near or over, from `budgets`.

Keep it to what fits on one screen. Link the report URL.
