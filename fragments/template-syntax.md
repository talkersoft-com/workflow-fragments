## Fragment template syntax

Fragments are Go templates (text/template). Use dot-prefixed fields:

| Field | Type | Description |
|-------|------|-------------|
| {{.Deck}} | string | Deck name |
| {{.Branch}} | string | Current branch |
| {{.DeckRoot}} | string | Workspace root path |
| {{.ExecFolder}} | string | Execution workflow folder |
| {{.PlanFolder}} | string | Planning workflow folder |
| {{.PRMode}} | string | Ship PR mode: auto_merge, await_merge, manual |
| {{.OpenBrowser}} | bool | Whether ship opens PRs in browser |
| {{.DeleteBranchOnMerge}} | bool | Whether branches are deleted after merge |

### Conditional example

```
{{if eq .PRMode "await_merge"}}
hv_ship will poll until all PRs are merged then auto-transition.
{{else}}
Merge PRs manually then run hv_next.
{{end}}
```
