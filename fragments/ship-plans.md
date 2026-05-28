## Step 11 — Ship the plans

All plan files are written. Ship them now so they land on their own PR before execution begins.

Call `hv_ship` on the deck with:
- **message**: `planning: {{Deck}}/{{Branch}}`
- **title**: `planning: {{Deck}}/{{Branch}}`

After `hv_ship` completes:
- The planning PR is merged
- The deck has automatically transitioned to a new execution branch
- Record the new branch name — this is the branch where `/loop` will execute tasks

Then continue to the next step (Handoff).
