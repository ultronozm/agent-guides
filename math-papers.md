# Mathematics writing and revision

Use these defaults where the paper's conventions do not settle the question.

## Source style

Use double spaces after sentences, American spelling, and AUCTeX-style indentation.  Prefer “Let” or “Write” to “Put”; use “Let ... be” for quantification and “Let ... denote” for notation.  Distinguish `:=` from `=`.  Preserve existing macros and nearby formatting; otherwise prefer braced symbols (`\mathcal{A}`, `\hat{\varphi}`) and spaced differentials (`\int f(x) \, d x`).

## Writing

- Prefer a short correction to a new paragraph.  Remove repeated previews and caveats already implied by the hypotheses or norms.  Keep useful reminders, examples, and tables.
- In overviews, explain the idea; put technical conditions in statements and proofs unless their omission would mislead.  Check prose against the proof: preserving control is not gaining a saving.
- Read using only preceding text and declared prerequisites before consulting private notes.  Identify explanations you supplied yourself; an expert's ability to repair the argument mentally does not establish readability.
- Keep a construction and its properties together.  State what applications need, including uniformity and norm bounds; leave internal choices in proofs.  State objects in their natural model before transporting them to an application.
- Show the missing inference with a short identity where it is used.  Prefer a suitable reference to a textbook digression.  Try a weaker sufficient estimate or common argument before polishing machinery.
- Extract reused calculations; keep transparent constructions inline when a quantified lemma would obscure them.  Avoid one-use aliases and number displays for later reference.

## Revisions

Settle the sequence of statements before expanding proofs.  Test a broad rewrite on one representative passage with a difficult transition.  Map every old conclusion and needed estimate to its new location or justified removal, including companion documents.

Before dropping an assumption, distinguish its uses in definitions, identities, bounds, and applications.  Keep varying parameters variable: fixed-rank bounds need not be uniform in rank, and `O(1)` does not supply a small constant for absorption.  A Lean mismatch requires investigation rather than silently changing the paper.

Keep editorial explanations and review records outside the manuscript.  Tie findings to the revision read and recheck affected findings after changes.  Retain unresolved draft markers.

Treat a coauthor comment and reply as a thread: remove both with the resolving edit, preserving unshared replies and unresolved notes.  Group comments by root cause and number decisions for the author.  When findings are requested through the manuscript, use its comment macros.

Read changed statements without proofs before checking the arguments.  Inspect rendered pages with neighboring prose when displays, tables, figures, page breaks, or new overfull boxes are involved.
