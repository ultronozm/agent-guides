# Working on Paul's Emacs programs: an agent guide

Use this guide for work on Emacs itself and Emacs packages, including patch preparation.  Follow the user's request and the target repository's conventions.  The [catalogue](emacs-programming-catalogue.md) records background evidence; it is not required reading for routine work.

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

- New ERT tests are optional.  Add them when they provide durable regression coverage, especially for non-obvious failure modes.  Prefer concise tests of public behavior; use table-driven boundary cases where they improve readability.  Avoid tests that merely mirror internal helpers.
- Validate proportionally: run `git diff --check` and relevant existing tests when applicable.  Start with the smallest useful batch suite, using `emacs -Q` where practical.  Add manual GUI/live validation for redisplay, mouse, window, overlay, and async behavior; report when it was not possible.
- Document unusual compatibility logic and user-visible migration.  Keep private-helper docstrings concise; explain the "why," not every local arithmetic detail.
- If source code already behaves correctly, prefer a docs-only correction to invented implementation churn.

## Git and live-session discipline

- Keep commits small and focused, with concise ordinary-language subjects.  Keep tests with the implementation they validate.
- Check whether work is unpublished before suggesting rebase/autosquash.  Never rewrite published/shared history without explicit authorization.
- In a running Emacs, preserve unsaved text and the user's chosen buffer/tab/window.  Do not save, kill, move, or redirect another agent's display as a convenient fallback.

## Reproductions and patch preparation

- Record the baseline revision when relevant.  Prefer a minimal, natural trigger over artificial state priming.  Include exact commands or key sequences, relevant errors, and expected versus observed behavior.  Say explicitly whether `emacs -Q` was used.
- Preserve documented API contracts and user-facing error behavior.  Explain the invariant behind a fix, including whether cached and uncached paths behave alike.
- Keep commit subjects short, imperative, and in ordinary language, without a trailing period.  Do not assume a package prefix such as `vc:` is required.
- Keep commit bodies lean: explain the symptom and rationale without repeating the entire investigation.  Follow the repository's wrapping and changelog conventions; include an issue reference when one exists.
- Consider documentation or release notes for user-visible changes, including option migrations and version metadata where the project uses them.
- When a report or patch message is requested, use plain-text-friendly formatting: brief context, minimal reproduction, exact symptom, and a short explanation of the change.  State uncertainty without overstating which commit caused a regression.
- Produce the artifacts the task calls for.  For emailed patches, use the project's submission conventions and check that the exported patch applies cleanly and contains the intended final message.
- Before calling work ready, inspect the diff and its scope, check for unrelated changes, and report the validation actually performed.

## Completion report

Report the behavior changed, files touched, precise validation performed, and remaining limits (especially untested GUI/live behavior).  Do not overstate tests or reproduce a user's private data in logs or commit messages.
