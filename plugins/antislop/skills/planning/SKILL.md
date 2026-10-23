---
name: planning
description: Write and execute an implementation plan for multi-step work. Use when a task spans several files or tasks, or the user asks for a plan.
---

Settle the design first (use `grilling` if anything is still assumed). Then write the plan, then execute it task by task.

## Writing

Header: feature, goal, global constraints (test command, style rules, what is out of scope).

Each task:
- Files: create / modify (with line ranges) / test, exact paths.
- Consumes / Produces: exact names and signatures other tasks rely on.
- Steps, each small and checkable:
  1. write the failing test (name + assertions)
  2. run it, expect failure
  3. implement (exact signature, where)
  4. run tests, expect pass
  5. commit
- Verification: the command and the output that means success.

Sizing: a task fits one fresh context. Split by responsibility, not layer; follow the codebase's existing file patterns. Self-review the plan: every Consumes has a Produces, no step says "handle appropriately" or similar hand-waving.

## Executing

Work tasks in order unless independent (then see `subagents`). Per task: run the steps, compare every expected output to real output, and run `verifying` before marking done. If the code is wrong, use `diagnosing-bugs`. If the plan is wrong (contradicts the code or spec), stop and say so; don't improvise around it. Keep a short ledger of deviations.

Finish with a whole-change review (`reviewing`), then `finishing`.
