## Key rules

- **Results and Retro/LESSONS are written BEFORE `hv_ship`** — not after
- **FIX files are written before retrying** — never silently re-run a failed test
- **Task 0000 is always hv_status + hv_init/hv_next** — never skip it
- **Always use MCP tools for all hive deck operations** — `hv_status`, `hv_init`, `hv_next`, `hv_ship`. Never use raw `git` to commit, push, or open PRs for repos in the deck.
- **Repos outside the deck cannot be shipped via `hv_ship`** — if a workflow targets a repo not listed in the deck YAML, deck.md must include a `## Manual steps` section with explicit git instructions for that repo. Never silently fall back to raw git without documenting it.
- **Rebuild MCP artifacts after any MCP code change** — see `@rebuild-mcp-artifacts`. Always rebuild Go binary and/or TypeScript dist, then instruct the user to restart the MCP server via `/mcp`.
- **See `toolkit/`** for reusable MCP call patterns (hive-deck, database, dotnet)
- **This scaffold was generated for deck `{{.Deck}}` on branch `{{.Branch}}`**
- **Workflow folder:** `{{.ExecFolder}}/{{.Deck}}/{{.Branch}}`

## Handoff — STOP after planning

All plan files are now written. **Do not run `/loop`, do not execute any tasks, do not begin Task 0000.**

Report to the user:
1. Every file that was created (workflow folder path, init.md, deck.md, ORCH.md, task files, test files)
2. The branch name and deck
3. The exact `/loop` command from `ORCH.md` so they can copy-paste it to begin execution

Then wait. Execution starts only when the user runs `/loop` themselves.
