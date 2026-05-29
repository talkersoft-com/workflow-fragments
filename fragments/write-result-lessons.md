## Step 10 — Write `Results/RESULT.md` and `Retro/LESSONS.md` BEFORE hv_ship

`hv_ship` commits everything it finds — these files must exist before the ship call
or they land on the next branch and miss the PR.

### `Results/RESULT.md`

```markdown
# Result: {{.Deck}}/{{.Branch}}

## Outcome
SHIPPED | PARTIAL | FAILED

## Branch
`{{.Branch}}`

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

## Step 11 — Call hv_ship and report to the user

After writing Results and Retro, call `hv_ship`. When it returns, **print the
following block verbatim to the user** (fill in all values from the hv_ship output):

---

**Shipped — [PR #<N>](<pr-url>) on `{{.Branch}}`**
**Next branch: `<next-branch>`** ← the branch the deck auto-transitioned to after merge

To begin the next task on `<next-branch>`, run:
```
hv_status  deck: "{{.Deck}}"
```

---

The hv_ship output contains a line like `Next branch: <name>` — extract that value
and include it above. If hv_ship does not print a next branch (e.g. manual PR mode),
write "transition pending — run hv_next after PR is merged" instead.

### `Retro/LESSONS.md`

```markdown
# Lessons: {{.Deck}}/{{.Branch}}

## What would have helped
<Numbered list. Be specific — name the missing MCP method, the doc that should
exist, the task instruction that was ambiguous, or the test that gave a false
positive. If nothing went wrong, write a single line saying so.>

## Fix files written
- FIX-001: <one-line summary>
- FIX-002: <one-line summary>
```
