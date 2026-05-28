## Step 1 — Create the plan folder

Create the folder:

```
{{.WorkflowPlanningFolder}}/{{.Deck}}/{{.Branch}}/
```

## Step 2 — Write `PLAN.md`

Write `{{.WorkflowPlanningFolder}}/{{.Deck}}/{{.Branch}}/PLAN.md` using the requirements at the end of this prompt.

```markdown
# Plan: <title derived from requirements>

## Objective
<One paragraph: what problem is being solved and what the end state looks like.>

## Background
<Context the implementer needs: prior art, constraints, related systems, why this change is needed now.>

## Design
<Technical approach: data model changes, API shape, key algorithms, config changes.
Be specific enough that an implementer can start without asking questions.>

## Implementation phases

Each phase maps to one TASK file during execution. Keep phases independent and testable.

| Phase | Title     | Description                         |
|-------|-----------|-------------------------------------|
| 0000  | Setup     | hv_status + hv_init/hv_next         |
| 0001  | <phase 1> | <what this phase delivers>          |

## Open questions

<Decisions not yet made. List them so reviewers can resolve before execution.
Remove this section if there are none.>
```

## Step 3 — Ship the plan

```
hv_ship  deck: "{{.Deck}}"
         message: "plan: <title>"
         title:   "plan: <title>"
```
