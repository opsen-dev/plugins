---
name: opsen
description: Use when the user asks what their engineering tools, CI minutes, GitHub seats, Copilot or coding agents cost, what is wasted, whether a budget is at risk, or how much a pull request costs. Reads the opsen MCP server.
---

opsen audits a company's engineering spend every week and prices what is paid for and not used. Its MCP server reads the latest audit and changes nothing.

1. Start with `opsen_summary` for the totals and the largest findings.
2. For a question about one source (Copilot, Actions, GitLab, Jira, JetBrains, CircleCI, Cursor), call `list_findings` with that `category`, or `spend_by_source` for the breakdown.
3. For people, seats or workflows behind a finding, call `get_finding` with its id.
4. For budgets, call `budgets`. For cost per engineer or per pull request, call `cost_per_pull_request`.

Report money as opsen gives it: monthly USD, with the basis line when someone asks how a figure was reached. Link to the report URL from `opsen_summary` for anything that needs an owner to approve.
