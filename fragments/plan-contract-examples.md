## Contract and data model examples

Every plan that changes a data model, CLI contract, or payload shape must include
concrete before/after examples. Do not describe the change in prose only — show it.

### Data model changes
Show the struct or schema before and after:

```go
// Before
type ClaudeSettings struct {
    Enabled        bool  `yaml:"enabled"`
    ForceOverwrite *bool `yaml:"force_overwrite"`
}

// After
type ClaudeSettings struct {
    Enabled bool   `yaml:"enabled"`
    Mode    string `yaml:"mode"` // "overwrite" | "skip" | "merge"
}
```

### CLI contract changes
Show the command signature before and after:

```
# Before
hv workflow <deck> <name>

# After
hv workflow [plan] <deck> [name]
```

### JSON payload / MCP tool changes
Show the input shape before and after:

```json
// Before
{ "op": "workflow", "deck": "cloud-manager", "name": "create-workflow" }

// After
{ "op": "workflow_run", "deck": "cloud-manager", "name": "db-migration" }
// name is now optional — omit for base-only
```

### YAML config changes
Show the config key before and after with example values:

```yaml
# Before
force_overwrite: true

# After
mode: overwrite   # "overwrite" | "skip" | "merge"
```

If the plan has no contract or data model changes, omit this section entirely.
