{{if eq .PRMode "await_merge"}}
## PR merge — await_merge mode

hv_ship is polling GitHub until all open PRs are merged. Once all PRs are
merged it will automatically transition all repos to the next branch — you
do not need to run hv_next manually. Monitor the terminal for poll status.
{{else if eq .PRMode "auto_merge"}}
## PR merge — auto_merge mode

PRs have been queued for auto-merge on GitHub. hv_ship will detect the merges
and transition all repos to the next branch automatically. No manual action
required — watch for the transition confirmation in the terminal.
{{else}}
## PR merge — manual mode

Merge your PRs manually in GitHub, then run:

```
hv next
```

This transitions all repos to the next branch based on origin/main.
{{end}}
