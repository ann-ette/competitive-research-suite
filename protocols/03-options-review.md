# Options-Review Protocol

Last reviewed: 2026-07-03 (registered; no check of its method against outside practice is recorded since).

> Read this when choosing or revisiting a load-bearing technology or approach, or when a review said "looks solid" and you want to know whether a better option exists that the review never named.

This is the third sibling to the [research protocol](02-research.md) and the [elicitation protocol](01-research-elicitation.md). Elicitation finds the gaps in a topic. Research sources them. This one benchmarks a **decision** against the field before you commit to it. The other two cover coverage and sourcing and say nothing about decision quality, which is the hole this fills.

---

## Why This Exists

A full, rigorous multi-agent review of a retrieval system I was building (six lanes, every code finding adversarially verified, 35 empirical claims web-checked) missed that the retrieval layer had no lexical/BM25 arm. It sat unflagged for six months. Not because the review was weak, it was strong, but because a review audits what is on the page against itself. BM25's absence was neither a bug nor a doc-drift, so no lane could see it. The catch finally came from a comparative question ("how does BM25 compare to what I'm building"), which forced the alternative into the frame. This protocol turns that lucky question into a repeatable pass.

## The Failure It Prevents

- **Reviews audit conformance and defects.** An un-chosen alternative is neither, so it stays invisible. The more foundational the missing option, the blinder the review, because a foundational omission leaves no seam. Everything compiles and every query returns something.
- **"Optimal" silently collapses to "verify what's here."** "Is this built optimally" and "search whether something better exists" are the same words for different work. Handed a design, a model grades the design.
- **"New research" excludes the classics.** The best option is often decades old (BM25 is thirty years old). Any prompt scoped to "new" or "state-of-the-art" guarantees the boring-but-optimal options get skipped.
- **A well-cited design crowds out the search.** When citations arrive pre-attached to the choice, "verify it's optimal" anchors to grading those citations. Good research on the page suppresses the hunt for absent research.

## When To Run It

- Choosing a load-bearing technology or pattern (retrieval method, storage engine, sync model, crypto scheme, embedder, chunking, classifier).
- Revisiting a choice made early and never re-opened.
- After a correctness/security review, as a separate pass. The two do not substitute for each other.

## When Not To

- Reversible or low-blast-radius choices (a config default, a cheap-to-swap library).
- When the alternatives are already written down with reasons and nothing has changed.
- As a substitute for shipping. This pass is real work; run it on decisions that are expensive to change, or it becomes the kind of busywork that feels productive and isn't.

## The Protocol

1. **Inventory the load-bearing decisions.** List every technology or approach that would be expensive to change later. Output the list first and agree on scope before deep-diving.
2. **Build the frontier first.** For each decision, reconstruct the option space from the field *before* looking at your own choice, so the frontier is not anchored to your design. Name at least four real, specific alternatives, including at least one established/classical option and at least one **complement** that combines with an existing choice rather than replacing it. The BM25 miss was a complement (hybrid = dense + sparse), not a replacement, so complements are where the biggest misses hide.
3. **Compare on named axes.** Place your choice into that space and compare on axes you name up front. "Exact-term / proper-noun / rare-token recall" must be one, since that is exactly what dense retrieval is worst at.
4. **Filter by hard constraints.** Apply the project's non-negotiables (for a local-first product, say: no cloud inference, encryption at rest, personal scale). Flag any option that violates one, but still name it.
5. **Verdict per decision.** KEEP / ADD (complement) / SWITCH, plus the trigger that would change the verdict and the **deciding experiment** (metric + held-out set + pass rule) that settles it empirically.

## Guards

- **Do not restrict to "new" research.** Weigh classical, proven methods at least equally. Recency is not quality.
- **Web-verify every benchmark against its primary source.** Do not cite from memory. Label each claim ESTABLISHED / CONTESTED / INFERENCE / UNVERIFIED. This is load-bearing: fabricated citations recur in model-written briefs.
- **Name the alternatives in the prompt, not after.** Whoever names the rival does the hard part of the optimality check. A bare "is this optimal" collapses; "benchmark against A, B, C on axes X, Y" cannot.
- **Not done until it holds one real verdict.** A beautifully structured protocol run with zero web-verified per-decision verdicts is an intention, not a review. Protocol plus one worked pass, or it doesn't count.

## The Prompt (Copy-Paste)

Fill the four bracketed fields. Run the inventory as its own pass, confirm the decision list, then run the deep-dive **one decision per run** (a single "do all of them" prompt spreads the budget thin and collapses into shallow coverage).

```
ROLE: You are an adversarial systems architect running an OPTIONS review, not a
code review. For each load-bearing decision, find the best available technique
measured against the whole field, including approaches the project did NOT choose.
Assume every current choice is replaceable until you have proven it is the best fit
under my constraints. Steelman the strongest rival to each choice.

HARD RULE. DO NOT COLLAPSE THIS INTO VERIFICATION. Confirming that my current
choices are correct, well-built, or well-cited is EXPLICITLY OUT OF SCOPE and counts
as a failed review. I already have a correctness review. The only acceptable output
is a comparison of each decision against named alternatives that YOU generate. If you
find yourself endorsing my design, you are doing the wrong job.

DO NOT restrict to "new," "recent," or "state-of-the-art" research. The best option
is frequently an established or classical technique that is decades old. Weigh boring,
proven methods at least equally. A 30-year-old method that fits my constraints is a
valid and preferred recommendation. Recency is not quality.

METHOD (in order, do not skip step 2):
1. INVENTORY. Read [CODE PATHS + PRD PATHS]. List every technology/approach selection
   that would be expensive to change later. Output the inventory and stop for my
   confirmation before deep-diving.
2. BUILD THE FRONTIER FIRST. For EACH decision, BEFORE looking at what I chose,
   independently reconstruct the option space from the field. Name at least FOUR real,
   specific alternatives. At least one MUST be classical, and at least one MUST be a
   COMPLEMENT that combines with an existing choice rather than replacing it. Cite a
   primary source for each. Do this without reference to my implementation.
3. COMPARE. Only now place my choice into that space and compare on these axes: [AXES].
   Be concrete about the query class, workload, data scale, or failure mode where each
   rival beats mine. "Exact-term / proper-noun / rare-token recall" must be one axis.
4. FILTER by my hard constraints: [CONSTRAINTS]. Flag violations but still name them.
5. VERDICT per decision: KEEP / ADD (complement) / SWITCH, plus the trigger that would
   change it and the concrete experiment I can run to decide (metric + held-out set +
   pass rule).

EVIDENCE + HONESTY:
- Web-verify every benchmark against its actual source. Do NOT cite from memory. If you
  cannot find the primary source, mark the claim UNVERIFIED and do not lean on it.
- Label every empirical claim ESTABLISHED / CONTESTED / YOUR-INFERENCE.
- When uncertain whether a rival beats mine, say so and name the measurement that would
  resolve it. Do NOT resolve uncertainty by defaulting to my current choice.

OUTPUT: one section per decision, as a table:
Decision | Current choice | Alternatives (named + cited) | Where each rival wins |
Verdict | Deciding experiment | Confidence
```

Example standing fields, filled for a local-first encrypted-vault product (the passes that produced this protocol):

- **[AXES]:** exact-term / proper-noun / rare-token recall, semantic recall, latency, memory footprint, build cost, maintenance burden, local-first fit, behavior at personal-vault scale, failure modes, plus (surfaced by the first worked pass) encryption boundary of the *index*, crash-durability / WAL consistency, single-rowid-space hybrid fusion, single-file backup / portability, and re-index cost on an embedder swap.
- **[CONSTRAINTS]:** local-first (runs on one laptop, no cloud inference, no telemetry, no proxied calls, anything hosted is constraint-violating); encryption-at-rest (ideally inside the SQLCipher DB); corpus scale is a personal vault (hundreds to low-thousands of vectors, plausibly tens-of-thousands); latency is a non-issue at this scale.
- **Priorities, ranked (fill per decision):** e.g. sovereignty + encryption fit > hybrid capability > maintenance simplicity > recall quality > latency. "Best" is undefined until the axes are ranked.

## Worked Passes

Thirteen passes have run under this protocol: twelve on a local-first encrypted-vault product (vector storage, sync, identity synthesis, chunking, embedder, key derivation, migration, deletion, key architecture, key residency, multi-device correctness, corpus ingestion policy) and one on the model choice for a voice product. The full ledger is product-specific and stays with those products. What travels is the shape each pass produced: a frontier built before the incumbent was scored, a comparison on named axes, a verdict of KEEP, ADD, or SWITCH, and a deciding experiment with a metric, a held-out set, and a pass rule.

Two lessons from those passes are general enough to carry.

**A pass can fail on its roster.** One pass built its frontier from a vendor documentation page that listed half the available models; the vendor's own dashboard listed the rest, with measured latency and cost per model. The verdict survived and its basis did not. For availability, latency, or price, capture the surface where the numbers are measured, and treat the docs page as a claim.

**A pass can fail on its axes.** The same pass compared on price and speed because those were the two numbers the source published, and the quality dimension that was half the decision went unmeasured. Before comparing, ask whether the axes came from the decision or from whatever the source happened to publish. If a load-bearing axis cannot be measured at the desk, say so, demote the measured ranking to a probe order, and name the experiment that would measure it.

## Log

- 2026-07-02: Protocol created. First worked pass (vector-storage engine) launched the same day.
- 2026-07-02 to 2026-07-31: twelve passes across six waves closed the load-bearing inventory for the vault product. Two items deliberately deferred behind product requirements that do not yet exist.
- 2026-08-12: first pass on a second product. Two mid-pass corrections, recorded above as the roster lesson and the axes lesson.
