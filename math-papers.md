# Mathematics writing and revision

Follow the current task and the paper's conventions.  The revision guidance below gives defaults for judgment, not a ban on useful explanation or natural generality.

## Source conventions

Use double spaces after sentences.

Use commas like in normal English.  Use American spelling.

Prefer "Let" or "Write" over "Put".

Use "Let ... be" to introduce a universal quantifier.  Use "Let ... denote" or "Denote by ...", etc., to introduce notation.  Distinguish definitions ":=" from identities "=".

Put spaces and braces between TeX symbols the same way that I do when I write papers; see ~/doit/ for plenty of examples.  For example, use "\mathcal{A}" over "\mathcal A", "\hat{\varphi}" over "\hat\varphi"; for measures, put spaces after the "d", e.g., "\int f(x) \, d x".

Use the paper's existing macros and follow nearby spacing.  Avoid unrelated reformatting.

Try to keep indentation like what AUCTeX does.

## Writing and revision

- **Read in order.**  Introduce objects, notation, hypotheses, and their mathematical meaning before use.  A previously mentioned name is insufficient if the reader still cannot understand the integral or proposition.  Put shared setup before the statements that need it, and no earlier than needed.
- **Check flow, not just signposts.**  Read whole sections linearly after editing: each sentence should follow from the preceding discussion and have a purpose the reader can recognize immediately.  Close deferred arguments explicitly.
- **Let motivation carry forward.**  Once the section introduction explains the purpose, subsections can begin directly with the mathematics.  Remove overlapping previews rather than adding motivation to every paragraph.  Keep a local explanation only when it resolves a new question; identify the actual term or assertion rather than referring vaguely to “the cancellation” or “the bound”.
- **Organize around the argument.**  Make the reduction of the main problem intelligible before explaining how to estimate its output.  Before a technical lemma, state the goal, the standard qualitative input, and the extra control still needed.  Keep a construction and its useful properties together, organized around its elementary operations and the decisive identity they produce.  Once that identity is established, finish routine averaging, smoothness, and discretization arguments together, without a second layer of auxiliary notation.  Give sections short, familiar titles that accurately describe their contents.
- **State what later sections need.**  Export existence, identities, regularity, and bounds in the appropriate norms, with their dependencies.  Move internal choices into proofs when applications only need these properties.  Applications should cite the result rather than reconstruct the construction.  Extract a calculation used by two proofs rather than making one cite a detail buried in the other; later statements may collect inherited properties, but their proofs should cite those inputs and concentrate on the new calculation.
- **Use the natural model first.**  State an input where its groups and characters are simplest; transport it to the application inside the proof.  Define an object by its direct formula on its natural domain rather than by parallel descriptions of its restrictions.
- **Simplify the mathematics first.**  Try a simpler choice of vectors, a weaker sufficient estimate, or a common argument before polishing elaborate machinery.  Compare shortcuts against all required conclusions, not just one bound.  Judge the total cost across the paper.  A proposed simplification still needs proof.
- **Make each sentence earn its place.**  Remove repeated setup, redundant reformulations, unused facts, gratuitous qualifications, and commentary about the writing process.  Do not manufacture warnings about issues already resolved by the context, such as uniformity or dependence caveats already encoded by the hypotheses, norms, or asymptotic conventions; express any additional dependence in the estimate itself.  Make a correction without announcing it or describing the convention just implemented.  Keep a short reminder when it makes a formula readable.
- **Match precision to the level.**  In introductions, section overviews, and strategy summaries, convey the idea.  Leave normalizations, auxiliary parameters, and exceptional cases to the formal statements and proofs unless the idea cannot be understood without them; for example, “amplification gives a saving” need not say what the saving is normalized by.  When reviewing such prose, distinguish a materially misleading claim from harmless shorthand, and preserve the latter.
- **Be concise and checkable.**  In proofs, prefer a short sentence or explicit identity showing the missing inference, normalization, or source of a factor.  Explain a step where it is used.  Do not replace an actual proof with “standard”, a list of claims, or specialist shorthand.  Equally, do not expand familiar facts into a textbook digression.
- **Check hypotheses before changing them.**  Trace every downstream use.  Distinguish what is needed to define an object, prove an identity, obtain a uniform bound, or apply a theorem.  Avoid artificial exceptional cases; retain natural generality when it simplifies the statement.
- **Get quantifiers and bounds right.**  Respect the paper's meaning of “fixed”.  Keep parameters variable when a later error must tend to zero with them.  Specify necessary ranges and bounded families.  Choose conductor/height exponents before arbitrary decay orders when required.  Do not confuse fixed-rank assertions with uniformity in rank, or qualitative continuity with a uniform estimate.
- **Cite the input actually used.**  Verify the theorem, page, hypotheses, normalization, and strength.  Prefer a precise existing reference, including an earlier paper of Paul's, to a new proof of standard material.  State the exact input and explain its application; do not cite a nearby but irrelevant fact.
- **Spend notation sparingly.**  Avoid aliases used once, parallel names for the same object, and unnecessary subscripts or decoration.  Keep parallel roles and argument order consistent.  Suppress local place subscripts only after declaring the local setting.  Name or number displays for a subsequent reference, not merely because they are displayed.
- **Revise with a mathematical reader in mind.**  Make the main contribution clear and calibrate explanations to the audience.  Settle the sequence of statements before undertaking a large proof expansion.  Preserve useful author wording and substantive comments; distinguish Paul's decisions from a coauthor's suggestions or an agent's critique.  Propagate accepted changes and save in the requested Git state.
- **Match the source.**  Follow the source conventions above: spacing, punctuation, “Let”/“Write”, braced TeX, spaced differentials, `:=` versus `=`, existing macros, and AUCTeX indentation.  Avoid unrelated reformatting.

Final pass: read the statements without proofs, then check the proofs and downstream uses of the changes.  Compile, check references and typesetting, and report any unresolved mathematical issue precisely.

## Supporting evidence

The [revision catalogue](~/dotfiles/agents/reference/math-revision-catalogue.md) records the examples and qualifications behind these defaults.  Consult it when a preference needs interpretation; it is not an additional routine checklist.
