# Emacs programming

Use this guide for work on Emacs lisp.

## Design

- Prefer a direct command or user binding to a new mode, option, or configuration layer.  Keep global modes keyless unless global bindings are the feature.  Avoid defenses against implausible configurations that obscure the normal case.
- Load optional dependencies at the point of use; declare the minimum version actually required.  Preserve upstream signatures and metadata when replacing entries.
- Keep advice narrow, reversible, and justified, especially around private APIs.  Preserve the user's live buffers, unsaved edits, windows, and selected tab; use the requesting session's identity rather than whichever tab is selected.
- For display code, distinguish pixels, display lines, and buffer lines.  Test attainable window placement near buffer boundaries, not just a helper's ideal answer.  For streaming UI, retain incomplete fragments and test chunk boundaries and finalization.

## Investigation and tests

- Reproduce defects with a natural minimal trigger.  Distinguish source inspection, batch reproduction, and GUI observation; say whether `emacs -Q` was used.  Isolate the core package before blaming extensions.
- New ERT tests should earn their maintenance cost.  Prefer compact public-behavior tests, with tables for boundary cases; avoid tests that mirror helper implementations.  Batch tests alone do not establish redisplay, mouse, overlay, or asynchronous behavior.
- Run relevant existing tests and `git diff --check`; add focused live checks for interactive changes.  If the implementation already behaves correctly, make a documentation correction rather than inventing code changes.

## Patches

Explain unusual compatibility logic and migration, without narrating obvious implementation details.  Keep commit subjects short and ordinary; do not assume a prefix such as `vc:` is required.  Keep regression tests with the fix and commit bodies focused on the symptom and rationale.

Patch reports should give the baseline, exact reproduction, expected and observed behavior, and validation actually performed.  Follow the project's patch and changelog conventions; check exported patches apply cleanly.  State untested GUI behavior explicitly.
