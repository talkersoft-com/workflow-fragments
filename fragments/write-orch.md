## Step 4 — Write `Orchestrate/ORCH.md`

```markdown
# Orchestration: {{.Deck}}/{{.Branch}}

## Objective
<One paragraph describing what done looks like.>

## Inputs
Read these before Task 0000:
- `../init.md`
- `../deck.md`
- `../../common/toolkit/hive-deck.md`
- <additional design docs>

## Task list
Check the box when the task is implemented AND its test passes.

- [ ] `Tasks/0000-TASK.md` — **Phase 0**: hv_status + hv_init/hv_next
- [ ] `Tasks/0001-TASK.md` — **Phase 1**: <description>
- [ ] `Tasks/0002-TASK.md` — **Phase 2**: <description>
...
- [ ] `Tasks/NNNN-TASK.md` — **Final phase**: write Results + Retro/LESSONS, then hv_ship

## Execution steps
1. Read all inputs above before starting Task 0000
2. For each unchecked task in order:
   a. Read the task file
   b. Do the work
   c. Run the matching Test file
   d. On failure: write `Retro/FIX-NNN.md`, apply fix, re-run test
   e. On pass: check the box, move to the next task
3. When every box is checked, the workflow is complete

## Autonomous execution
{{if eq .Agent "claude"}}
To start execution, type the following command (do not copy-paste):

    workflow execute

⚠️  DO NOT COPY PASTE — type this command manually. The `workflow` keyword only works when typed directly into the prompt.
{{end}}
{{if eq .Agent "codex"}}
```
/loop Continue executing tasks in {{.ExecFolder}}/{{.Deck}}/{{.Branch}}/Orchestrate/ORCH.md. Start by running hv_status then hv_init (or hv_next) per deck.md. For each unchecked task: read the task file, do the work, run the matching Test file. On failure write Retro/FIX-NNN.md and retry. On pass check the box. When all boxes are checked write Results/RESULT.md and Retro/LESSONS.md — both BEFORE calling hv_ship — then ship and stop.
```
{{end}}

## Improvisation policy
- One FIX file per distinct failure, numbered sequentially (FIX-001, FIX-002, ...)
- Never silently retry — write the FIX file first, then apply the fix
- If a failure cannot be recovered after two attempts: stop and surface to operator

## End-of-workflow outputs (write BEFORE hv_ship)
- `Results/RESULT.md`
- `Retro/LESSONS.md`
```
