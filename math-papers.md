# Mathematics writing and revision

Use these defaults where the paper's conventions do not settle the question.

## Source style

Use double spaces after sentences, American spelling, and AUCTeX-style indentation.  Prefer “Let” or “Write” to “Put”; use “Let ... be” for quantification and “Let ... denote” for notation.  Distinguish `:=` from `=`.  Preserve existing macros and nearby formatting; otherwise prefer braced symbols (`\mathcal{A}`, `\hat{\varphi}`) and spaced differentials (`\int f(x) \, d x`).

## Exposition

- Make the smallest useful edit.  Preserve good author wording.  Remove repeated setup, previews, and editorial commentary; do not add caveats already implied by the hypotheses or norms.
- Explain the idea in introductions and overviews; leave technical conditions to statements and proofs unless omitting them would mislead.  Keep useful reminders, examples, and tables.  Concision should not obscure the contribution or its significance.
- Read a passage using only preceding text and declared prerequisites, before consulting private notes.  Record where you had to supply an explanation yourself: being able to repair the argument mentally does not mean the text explains it.
- Organize around the argument's destination.  Keep a construction and its useful properties together.  State what later applications need, including uniformity and norm bounds; leave internal choices in the proof.  For deferred proofs, give a usable statement and an exact proof location in matching notation.
- Explain the missing inference where it occurs, preferably with a short identity or calculation.  Avoid both “standard” as a substitute for proof and textbook explanations of familiar facts.  Check explanatory prose as well as formulas: a step that preserves control must not be described as gaining a saving.
- Simplify the mathematics before polishing machinery.  Try a weaker sufficient estimate or common argument.  Extract a lemma when it is reused or separates a substantial idea; keep a transparent construction inline when a quantified lemma would make it harder to read.
- Spend notation sparingly.  Avoid one-use aliases, keep parallel roles consistent, and number displays for later reference.  Through changes of model or normalization, explain how the current objects represent the original ones.  State objects in their natural model before transporting them to an application.

## Mathematical changes

- Never silently change a claim, hypothesis, quantifier, normalization, or constant dependence.  Supply a proof or source, check downstream uses, and report the change outside the manuscript.  A mismatch with a Lean formalization is evidence to investigate, not authority to alter the paper.
- Distinguish assumptions needed for definitions, identities, bounds, and applications.  Keep varying parameters variable; “for each fixed rank” is not uniformity in rank, and `O(1)` does not supply a small constant for absorption.
- Cite the precise input actually used, checking its hypotheses and normalization.  Prefer a suitable existing reference to a new proof of standard material.  When adapting material, record its source and substantive changes.
- Keep uncertainty visible until resolved.  Do not delete a draft marker merely because the surrounding prose now reads smoothly.

## Larger revisions and review

Settle the sequence of statements before expanding proofs; write the final introduction after the body stabilizes.  Test a proposed rewrite on one representative passage, including a difficult transition, before applying it throughout.  Map every old conclusion and needed intermediate estimate to its new location or justified removal, including uses in companion documents.

A request to review asks for findings unless edits are also requested.  Tie findings to the revision read and recheck them after relevant changes.  Prioritize unanswered coauthor questions, altered claims and their downstream uses, and citation accuracy before style.  Keep review records outside the manuscript and distinguish mathematical checks from readability and typesetting checks.

Treat a coauthor comment and its reply as a thread: remove both with the edit that resolves it, preserving unshared replies and unresolved notes.  Group comments by root cause before addressing them; number decisions that need the author.  Check that replies answer the actual question and agree with earlier parts of the paper.  When findings are requested for the coauthor through the manuscript, use its existing comment macros.

## Referee rounds and verification

Keep the submitted PDF and an annotated `submitted/<journal>/<date>` tag as the revision baseline.  Key referee-response commits by item (`R<n>:`), use `xr-hyper` references in response letters, and build highlighted changes with `latexdiff` against the tag.

Read changed statements without proofs, then check proofs and downstream uses.  Compile and check references; inspect rendered pages and neighboring prose when displays, tables, figures, page breaks, or new overfull boxes are involved.  Report unresolved mathematics and skipped checks.  At submission, check venue-required statements, private URLs, coauthor sign-off, and that the archived PDF is the one sent.
