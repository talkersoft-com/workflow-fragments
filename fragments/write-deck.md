## Step 3 — Write `deck.md`

```markdown
# Deck: {{Deck}}

## Deck name
`{{Deck}}`

## Repos with code changes
| Repo | What changes |
|------|-------------|
| `<repo-name>` | <brief description> |

Repos not listed will be on the feature branch but skipped by hv_ship.

## Branch
`{{Branch}}`

## Initialize (Task 0000)
`‌``
hv_status  deck: "{{Deck}}"
hv_init    deck: "{{Deck}}"
`‌``
If already provisioned on a prior feature branch with all PRs merged:
`‌``
hv_status  deck: "{{Deck}}"
hv_next    deck: "{{Deck}}"
`‌``

## Ship
`‌``
hv_ship  deck: "{{Deck}}"
         message: "<commit message>"
         title:   "<PR title>"
`‌``
```
