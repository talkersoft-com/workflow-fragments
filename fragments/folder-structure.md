## Step 1 — Create the folder structure

Create the workflow folder at `{{.ExecFolder}}/{{.Deck}}/{{.Branch}}/`:

```
{{.ExecFolder}}/{{.Deck}}/{{.Branch}}/
  init.md
  deck.md
  Orchestrate/
  Tasks/
  Test/
  Retro/
  Results/
```

`Retro/`, `Results/` start empty — the AI populates them at runtime.
