# Emacs programming

Use this guide for work on Emacs lisp.

- Prefer a direct command or user binding to another mode or configuration layer.  Keep global modes keyless unless global bindings are the feature.  Avoid elaborate defenses against implausible configurations.
- Load optional dependencies at the point of use.  Preserve upstream signatures and metadata when replacing entries.
- Gate private-API advice narrowly and make it reversible.  Preserve live buffers, unsaved edits, and window arrangements; use the requesting session's identity rather than the selected tab.
- Distinguish pixels, display lines, and buffer lines.  Test attainable window placement near buffer boundaries, not only a helper's ideal answer.  For streaming UI, test incomplete fragments, chunk boundaries, and finalization.
- Isolate the core package before blaming extensions.  Distinguish source inspection, batch reproduction, and GUI observation; say whether `emacs -Q` was used.
- New ERT tests should earn their maintenance cost.  Prefer compact public-behavior tests over tests mirroring helpers.  Batch tests alone do not establish interactive display behavior.
- If the implementation already behaves correctly, fix the documentation without inventing code changes.  Explain unusual compatibility logic without narrating obvious arithmetic.
- Keep commit messages short and ordinary; do not assume a prefix such as `vc:` is required.
