---
name: fix
description: Fix the waste opsen found in the current repository, such as GitHub Actions runs a newer push made obsolete, jobs without timeouts, schedules on inactive repositories and CircleCI workflows that keep failing. Use when the user asks to fix opsen findings or cut CI spend here.
---

1. Work out this repository's `owner/name` from `git remote get-url origin`.
2. Call the opsen MCP tool `fix_prompts` with `repo` set to it.
3. If it returns no fixes, say so and stop.
4. For each fix, largest `monthly_usd` first: follow its `prompt` exactly. Change only what it describes, keep formatting, and run the checks it names (YAML validity, `actionlint` if installed, `circleci config validate` for CircleCI).
5. Put each fix on its own branch and open one pull request per fix, using the title the prompt gives. Mention the monthly saving in the description.
6. Finish with a table of the pull requests and what each saves a month.
