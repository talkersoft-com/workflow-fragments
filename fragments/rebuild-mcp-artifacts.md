## Rebuild MCP artifacts after any MCP changes

After completing any task that modifies code in an MCP server (Go source, TypeScript source, config, or schema), rebuild all artifacts for that MCP before moving to the next task.

**For each MCP that was changed:**

1. **Go binary** (if Go source changed):
   ```bash
   cd <deck-workspace>/<mcp-repo> && CGO_ENABLED=0 go build ./... && CGO_ENABLED=0 go install ./cmd/hv/
   ```

2. **TypeScript/Node dist** (if `mcp/src/` changed):
   ```bash
   cd <deck-workspace>/<mcp-repo>/mcp && npm run build
   ```

3. **Restart the MCP server** — the running MCP process must be restarted to pick up the new binary or dist. Instruct the user:
   > "Restart the MCP via `/mcp` to pick up the new build."

**Do not skip this step.** Shipping code changes without rebuilding means the running MCP still executes the old binary, and the user will observe no change in behavior until the server is restarted with the new artifacts.
