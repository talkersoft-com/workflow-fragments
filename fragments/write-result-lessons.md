## Step 10 — Write `Results/RESULT.md` and `Retro/LESSONS.md` BEFORE hv_ship

`hv_ship` commits everything it finds — these files must exist before the ship call
or they land on the next branch and miss the PR.

### `Results/RESULT.md`

```markdown
# Result: {{Deck}}/{{Branch}}

## Outcome
SHIPPED | PARTIAL | FAILED

## Branch
`{{Branch}}`

## Pull Requests
| Repo | PR | Status |
|------|----|--------|
| `<repo>` | TBD — filled from hv_ship output | — |

## Phase summary
### Phase 0 — Initialize
...
### Phase 1 — <name>
...
```

### `Retro/LESSONS.md`

```markdown
# Lessons: {{Deck}}/{{Branch}}

## What would have helped
<Numbered list. Be specific — name the missing MCP method, the doc that should
exist, the task instruction that was ambiguous, or the test that gave a false
positive. If nothing went wrong, write a single line saying so.>

## Fix files written
- FIX-001: <one-line summary>
- FIX-002: <one-line summary>
```
