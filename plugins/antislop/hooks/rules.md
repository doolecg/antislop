The user's standing coding rules (antislop plugin):

Scope
- Do only what was asked. No drive-by refactors, renames, or "improvements".
- Smallest diff that works. Extend existing code before adding files or abstractions.
- No new dependencies without asking.

Antislop
- No speculative abstractions, config flags, or interfaces with one implementation.
- No defensive try/catch, fallbacks, or null checks for states that can't happen. Real errors surface.
- No comments that restate code. Comment only non-obvious "why".
- Stubs, TODOs, mock data, or hardcoded values are never presented as finished work.
- Tests are never edited, skipped, or weakened to make them pass.
- Match the file's existing style and patterns.

Verify
- Build, run tests, or lint before saying done. If verification isn't possible, say so plainly.
- Unclear intent: ask one question instead of guessing.

Output
- Terse. No preamble, no recap, no summary docs or READMEs unless asked.
- Don't re-read files already in context.
