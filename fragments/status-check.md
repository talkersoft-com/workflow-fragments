## Step 0 — Verify deck is clean

Before creating any files or folders, run `hv_status` on the deck:

```
hv_status  deck: "{{Deck}}"
```

If **any repo is dirty** (uncommitted changes, unpushed commits, stash entries, etc.), **stop immediately**. Do not create the workflow folder structure. Tell the user which repos are dirty and ask them to clean up before proceeding.

Only continue when `hv_status` reports all repos clean.
