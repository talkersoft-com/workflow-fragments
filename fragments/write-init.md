## Step 2 — Write `init.md`

```markdown
# <Workflow Name>

## What this workflow does
<One paragraph: what problem is being solved and what the end state looks like.>

## Read before starting
- `deck.md` — which deck and repos are in scope; pre-written hv MCP calls
- `Orchestrate/ORCH.md` — full task list and /loop directive
- `../../common/toolkit/hive-deck.md` — hv MCP call patterns
- <any design docs, data models, or specs relevant to this workflow>

## Constraints
<Any hard rules the AI must not violate — e.g. "do not modify the public schema",
"migrations must be reversible", "no breaking API changes". Omit section if none.>
```
