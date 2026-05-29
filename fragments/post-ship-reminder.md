## Post-ship reminder — print this to the user immediately

After `hv_ship` returns with the planning PR link, output the following block verbatim to the user (fill in the values in angle brackets):

---
{{if eq .PRMode "manual"}}
**Planning shipped — [PR #<N>](<pr-url>)**

Next steps:
1. Merge the PR above
2. Then run `hv_next  deck: "{{.Deck}}"` to transition to the execution branch
3. Then start execution by running:

```
workflow Continue executing tasks in {{.WorkflowFolder}}/{{.Deck}}/<execution-branch>/Orchestrate/ORCH.md. Start by running hv_status then hv_next per deck.md. For each unchecked task: read the task file, do the work, run the matching Test file. On failure write Retro/FIX-NNN.md and retry. On pass check the box. When all boxes are checked write Results/RESULT.md and Retro/LESSONS.md — both BEFORE calling hv_ship — then ship and stop.
```

Replace `<execution-branch>` with the branch the deck transitioned to after the planning ship.
{{else}}
**Planning shipped — [PR #<N>](<pr-url>)**

hv_ship is handling the merge and branch transition automatically (`pr_mode: {{.PRMode}}`).
Once the PR merges and the deck transitions, continue immediately — no manual steps needed. Run:

```
/loop Continue executing tasks in {{.WorkflowFolder}}/{{.Deck}}/<execution-branch>/Orchestrate/ORCH.md. Start by running hv_status then hv_next per deck.md. For each unchecked task: read the task file, do the work, run the matching Test file. On failure write Retro/FIX-NNN.md and retry. On pass check the box. When all boxes are checked write Results/RESULT.md and Retro/LESSONS.md — both BEFORE calling hv_ship — then ship and stop.
```
{{end}}
---

Replace `<execution-branch>` with the branch name the deck transitioned to after the planning ship.
