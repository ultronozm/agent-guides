# Lean proofs

Use this guide for Lean/mathlib proof development and simplification.

## Isolate the difficulty

Work in a `scratch/` directory inside the package.  Use unnamed `example`s with the relevant imports and locally restated definitions; importing the whole target file can hide dependencies.  Reduce to the smallest failing example, then add lets, coercions, and actual types until it matches the real goal.  Compare the failing example with the closest working one.

Use `extract_goal` when available.  For instance failures, try `#synth` on the exact instance and `trace.Meta.synthInstance` to find the missing dependency.  Follow the file and line reported by Lean rather than assuming the error belongs to the requested file.

If tactics obscure the mathematics, write the argument first, then translate it into a short `calc` with separate lemmas for the difficult steps.  Temporary `sorry`s belong to exploration, not the finished proof.

## Simplify after it works

- Use `simp?` to obtain an explicit `simp only [...]` list.  Replacing `simp only` with broad `simp` is not a simplification.
- Extract helpers when reused or independently interesting.  Inline one-line API wrappers and short single-use steps; avoid packaging several properties into a tuple just to unpack them later.
- Prefer existing structural APIs to specialized copies: restrict results with `.mono`, transfer formulas with `Set.EqOn` and `.congr`, and use the appropriate `ContDiffOn` result instead of chains of ad hoc regularity helpers.
- Keep useful algebraic identities or integrability facts shared across branches.  Choose generality that simplifies callers rather than introducing extra parameters for their own sake.

## Iterate locally

Use `lake env lean path/to/File.lean` for single-file iterations; use `lake build` for changes across files or imports.  Keep scratch examples when moving the working proof back.  Audit imports by removing one and compiling; avoid umbrella `import Mathlib` when narrower imports suffice.

For slow elaboration, isolate the expensive step, narrow simplification, and split long tactic blocks.  If a heartbeat increase is still necessary, make it local to the lemma.
