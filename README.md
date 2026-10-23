# antislop

A tiny Claude Code plugin: always-on antislop rules (~250 tokens per session) plus three on-demand skills.

| Piece | Loads | What it does |
|---|---|---|
| `hooks/rules.md` | Every session start, `/clear` and compaction | Scope, antislop, verify and output rules |
| `/antislop:grilling` | When used (description is in context) | Interviews you about a plan, round by round, until nothing is assumed |
| `/antislop:grill-me` | Only when you type it | Shortcut to `grilling` |
| `/antislop:diagnosing-bugs` | When used (description is in context) | Feedback-loop-first debugging |

## Install

```
/plugin marketplace add doolecg/antislop
/plugin install antislop@doole
```

Restart Claude Code (or run `/reload-plugins`). In T3 Code, restart the app after installing so the Claude provider picks it up.

## Check it works

1. Start a fresh session and run `/context`. You should see the hook's context and three skills, nothing big.
2. Ask: "What are my standing coding rules?" Claude should list them back.
3. Run `/antislop:grill-me` on a small idea.

## Editing the rules

Edit `plugins/antislop/hooks/rules.md`, bump `version` in `plugins/antislop/.claude-plugin/plugin.json`, push, then run `/plugin update antislop`.

Keep the file small: it's paid for every session.

## Per-project rules

Project-specific rules go in that project's own `CLAUDE.md`, not here. For Unity or Godot projects, for example:

```md
- Gameplay feel, physics tuning, shaders, UI layout: I verify manually. Don't write tests for them. Test pure logic only.
```

## Credits

`grilling`, `grill-me` and `diagnosing-bugs` are from [mattpocock/skills](https://github.com/mattpocock/skills) (MIT). See `plugins/antislop/THIRD_PARTY/`.
