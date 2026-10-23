# antislop

A lean Claude Code plugin: always-on antislop rules (about 300 tokens per session) plus on-demand process skills condensed from [superpowers](https://github.com/obra/superpowers) and [mattpocock/skills](https://github.com/mattpocock/skills). Whole pack is about 15 KB; the originals it replaces are over 300 KB.

| Piece | Loads | What it does |
|---|---|---|
| `hooks/rules.md` | Every session start, `/clear`, compaction | Scope, antislop, bug, verify and output rules |
| `0-antislop` | On use | Slop filter for prose and UI: banned words, patterns and visual ornament |
| `1-qa` | On use, or `/antislop:1-qa` | Round-by-round interview until nothing in a plan is assumed |
| `2-plan` | On use | Spec plus task-by-task plan with exact files, signatures and checks, antislop-pruned |
| `3-build` | On use | Implement the plan, spec or ticket: test-first per task, typecheck often, full suite once, antislop diff per task |
| `4-testing` | On use | Red-green at agreed seams, one slice per cycle |
| `5-bug` | On use | Feedback loop first, then reproduce, hypothesise, instrument, fix, clean up |
| `6-check` | On use | No "done" without running the proving command this turn |
| `7-review` | On use | Two-axis review (standards, spec) and how to take review feedback |
| `8-autoagents` | On use | Task cards, frontier dispatch, verify every report |
| `9-push` | On use | Close a branch: verify, merge or PR, clean up |

Skills are numbered in workflow order. Only the descriptions sit in context until one is used.

## Install

```
/plugin marketplace add doolecg/antislop
/plugin install antislop@doole
```

Restart Claude Code (or `/reload-plugins`). In T3 Code, restart the app so the Claude provider picks it up.

## Check it works

1. Fresh session, `/context`: the hook's text and ten small skills.
2. Ask "What are my standing coding rules?" and get them back.
3. `/antislop:1-qa` on a small idea.

## Editing

Rules: `plugins/antislop/hooks/rules.md`. Skills: `plugins/antislop/skills/<name>/SKILL.md`. Bump `version` in `plugins/antislop/.claude-plugin/plugin.json`, push, `/plugin update antislop`. Keep the rules file small: it's paid for every session.

Project-specific rules belong in that project's `CLAUDE.md`, not here.

## Credits

Condensed from obra/superpowers and mattpocock/skills, both MIT. Details in `plugins/antislop/THIRD_PARTY/NOTICE.md`.
