# opsen plugins

opsen for coding agents. Ask what your engineering stack costs and wastes, and fix the waste in the repository you are in, from Claude Code, Cursor or Codex.

You need an opsen API key: [opsen.dev](https://opsen.dev), **Settings → API keys and MCP**.

## Claude Code

```text
/plugin marketplace add opsen-dev/plugins
/plugin install opsen@opsen
```

Claude Code asks for your key and keeps it in your system keychain. Then:

- `/opsen:fix` makes every fix opsen has for this repository, one pull request each.
- `/opsen:spend` summarises spend, waste and budgets.
- Ask anything about spend; the `opsen` skill knows when to call the server.

## Codex

```bash
codex plugin marketplace add opsen-dev/plugins
export OPSEN_API_KEY=opsen_sk_...
```

Then install **opsen** from `/plugins`.

## Cursor

Use **Add opsen to Cursor** in opsen settings, or add the server to `.cursor/mcp.json`:

```json
{"mcpServers": {"opsen": {"url": "https://opsen.dev/mcp", "headers": {"Authorization": "Bearer ${env:OPSEN_API_KEY}"}}}}
```

The plugin in `plugins/opsen` also carries a Cursor rule and the same skills for team marketplaces (**Import from Repo**).

## What the server offers

| Tool | Returns |
| --- | --- |
| `opsen_summary` | Monthly spend, what is not used, the largest findings |
| `list_findings` | Every finding with its cost, basis and fix |
| `get_finding` | One finding with its people, seats or workflows |
| `fix_prompts` | Fixable waste in code with a ready prompt each, for one repository |
| `spend_by_source` | Spend and waste per source and platform |
| `budgets` | Each budget against this month's spend |
| `cost_per_pull_request` | Claude Code spend per engineer and per merged pull request |

The server reads your latest audit and changes nothing. Every call is in your workspace's audit log. Reference: [opsen.dev/docs/mcp](https://opsen.dev/docs/mcp).
