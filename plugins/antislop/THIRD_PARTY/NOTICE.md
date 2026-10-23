# Third-party sources

Skills in this plugin are condensed from two MIT-licensed repos. Nothing is copied verbatim beyond `grilling`, `grill-me` and the HITL script; the rest is rewritten and merged for size.

## mattpocock/skills
https://github.com/mattpocock/skills, commit `5beb35b040e3de97e54fa9e386d7e42d15c295c2`. Licence: `mattpocock-skills-LICENSE`.
- `grilling`, `grill-me`: copied (grill-me repointed at `antislop:grilling`).
- `diagnosing-bugs`: condensed; `scripts/hitl-loop.template.sh` copied.
- `tdd`: seams, anti-patterns, one-slice rule.
- `reviewing`: two-axis review and smell baseline.
- `subagents`: frontier/task-graph execution.

## obra/superpowers
https://github.com/obra/superpowers, commit `2ce8aa15d05bd57213e6f746f953aafb7ded7a8b`. Licence: `superpowers-LICENSE`.
- `tdd`: red-green cycle, delete-code-written-first rule.
- `verifying`: verification-before-completion.
- `diagnosing-bugs`: root-cause-first, two-strikes rule.
- `planning`: writing-plans and executing-plans.
- `reviewing`: receiving-code-review.
- `subagents`: dispatching-parallel-agents, subagent-driven-development.
- `finishing`: finishing-a-development-branch.
