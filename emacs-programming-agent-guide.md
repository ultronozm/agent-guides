# Working on Paul's Emacs programs: an agent guide

This is a compact operational guide distilled from `emacs-programming-catalogue.md`.  First read the target repository's instructions and contribution rules.  They override this guide.  In particular, `/Users/au710211/work/emacs/AGENTS.md` currently permits analysis only, not LLM-generated contributions, bug reports, or planning.

## Before changing anything

1. Inspect `git status`, the relevant source, tests, documentation, and nearby analogous code.  Identify the public behavior and the actual load/event/rendering boundary.
2. For a defect, make a minimal reproduction or collect concrete live observations.  Say whether a conclusion is source inspection, batch reproduction, or GUI reproduction.
3. State the smallest plausible change.  Do not add a mode, option, serialization format, key map, broad advice, or compatibility layer without a demonstrated need.

## Design rules

- Preserve established defaults.  Keep global modes keyless unless global bindings are the explicit feature; make disruptive behavior opt-in.
- Reuse local patterns and upstream metadata.  Preserve signatures/options/representations when replacing an existing entry.
- Keep dependencies lazy and truthful: do not require a package at top level if it is needed only during one action, but raise the declared minimum version when necessary.
- Optimize for normal supported configurations.  Prefer a clear invariant to elaborate defenses against implausible pathological states.
- Scope side effects narrowly.  Use advice only when necessary, document it, gate private-API advice tightly, and make enable/disable behavior reversible.
- For display code, use compatible units throughout.  Distinguish pixels, display lines, buffer lines, window dimensions, and desired versus attainable placement.
- For streaming UI, retain incomplete fragments until they are safe to render; test chunk boundaries and finalization.

## Tests and docs

- Write concise ERT tests around public behavior.  Use table-driven boundary cases where they improve readability.
- Run `git diff --check` and the focused batch suite before claiming success.  Add manual GUI/live validation for redisplay, mouse, window, overlay, and async behavior.
- Document unusual compatibility logic and user-visible migration.  Keep private-helper docstrings concise; explain the "why," not every local arithmetic detail.
- If source code already behaves correctly, prefer a docs-only correction to invented implementation churn.

## Git and live-session discipline

- Keep commits small and focused, with concise ordinary-language subjects.  Keep tests with the implementation they validate.
- Check whether work is unpublished before suggesting rebase/autosquash.  Never rewrite published/shared history without explicit authorization.
- Treat inspection, review, edit, commit, reload, merge, push, and buffer/window manipulation as separate permissions.
- In a running Emacs, preserve unsaved text and the user's chosen buffer/tab/window.  Do not save, kill, move, or redirect another agent's display as a convenient fallback.

## Completion report

Report the behavior changed, files touched, precise validation performed, and remaining limits (especially untested GUI/live behavior).  Do not overstate tests or reproduce a user's private data in logs or commit messages.
