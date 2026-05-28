## Step 8 — Write `Test/NNNN-TEST.md` for each task

```markdown
# Test <NNNN> — <Phase Name>

## TC-001 — <what is verified>
<Command or action to run.>
Pass: <exact expected output or condition.>
Fail: <what a failure looks like.>

## TC-002 — <what is verified>
...
```

Each TC must be independently runnable and produce an unambiguous pass or fail.
Prefer `grep`, `dotnet build`, `hv_status`, or a direct DB query over manual inspection.
