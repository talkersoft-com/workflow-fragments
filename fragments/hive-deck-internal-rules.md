## hive-deck internal rules

These rules apply when the workflow is making changes to hive-deck itself
(Go source, TypeScript MCP source, config, or schema).

- **Rebuild Go binary after any Go source change** — run `make install` or
  `CGO_ENABLED=0 go build ./... && go install ./cmd/hv/` from the repo root.
- **Rebuild TypeScript dist after any `mcp/src/` change** — run `cd mcp && npm run build`.
- **Restart the MCP server after rebuilding** — instruct the user to run `/mcp`
  to reload the running server with the new binary or dist.
- **See `toolkit/`** for reusable MCP call patterns (hive-deck, database, dotnet).

**Do not skip rebuilds.** Shipping code changes without rebuilding means the running
MCP still executes the old binary and the user will see no change in behaviour.
