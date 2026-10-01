# The Prompts

Every prompt the five protocols carry, gathered in one place so they can be pasted without opening the protocol. The protocols are canonical; this file is generated from them at cut time and says the same thing.

Tool names are generalized. "Single-agent" means one model with a large context window and web access. "Multi-agent fan-out" means an orchestrator that spawns workers with separate contexts and a verifier arm; the worker counts in the prompts are the ones I used, and they are a starting point. Where a prompt says "read the protocol," give the model the protocol file.

---

## Competitive Research

From [the competitive research protocol](../protocols/04-competitive-research.md).

### P0 · Preamble

```
Do not ask clarifying questions. Every decision you would ask about is
answered below or is yours to make and record. Begin immediately.
Read the competitive research protocol before your first tool call and
follow it. Where this prompt and the protocol disagree, the protocol wins
and you note the conflict in your output.
```

### P1 · Single-Agent, Single-Shot Deep Read on One Competitor

A million-token context window makes the temptation to load everything, and a loaded window degrades in the middle. This caps volume deliberately, states the question at the top and at the bottom, and puts the highest-value sources at the extremes.

```
[P0]

ROLE: You are profiling ONE company for a competitive record. One company.
If you find yourself writing about a second, stop and note it as a
set-boundary question instead.

TARGET: <name> · <url>
DECISION THIS SERVES: <the decision from step 1 of the protocol>

CORPUS: I have placed the pricing page, the docs index, the changelog,
the last four release notes, and the two most recent third-party reviews
in this message. Read all of it before writing. Do not search for more
until you have. Then run at most 12 targeted searches to close named gaps.

OUTPUT: the per-competitor record schema from the protocol, every field,
in order. Every capability sentence carries an evidence tier E1 to E6 in
brackets. Every absence claim reads "as of <date>, <source> does not list X"
with a link. Threat level is an ordinal with a written escalation trigger.

HARD RULES:
- Never let E5 pass as E3. Marketing copy tells you what they claim.
- Do not synthesize a number that is not in a source. "Several days" never
  becomes "48 to 72 hours."
- End with "What I could not access" and list every blocked source, what
  claim it was needed for, and whether a substitute exists.
- No em dashes.

Restate the target and the decision in your first line, then begin.
```

### P2 · Multi-Agent Fan-Out, Set Discovery

The orchestrator picks its own worker count, so the count is named in the prompt. Each slice gets an objective, an output format, its named sources, and its boundary.

```
[P0]

TASK: Define the competitive set for <product> as the BUYER holds it.
Do not derive it from the product's own feature list or from who the
team assumes competes.

Spawn exactly six agents in one message, one slice each, and give each one
an objective, an output format, its named sources, and its boundary:

1. Win/loss and sales evidence: <paths or "none available, say so">
2. Search demand: "alternatives to <product>", "<product> vs", and the
   equivalents for every name found. Report query families. Volumes are
   out of scope and unreliable at this stage.
3. Review-site comparison surfaces: who is listed as compared-with, in
   which categories, at what review velocity.
4. Community threads: HN via hn.algolia.com, Reddit, vendor forums.
   Fixed query set, log every hit with its date, count by quarter.
5. The non-vendor alternatives: do nothing, build in house, and the
   incumbent tool that already has an adjacent module. These are
   first-class members of the set.
6. Adjacent-category substitution: what solves the same job from a
   different category.

Then synthesize ONE roster with three tiers: EVALUATED (a buyer would
plausibly put this on a shortlist of five), WATCHLIST, and EXCLUDED with
the reason for exclusion written out.

INCLUSION TEST, binding: a name enters the set only if there is evidence a
buyer considered it. Capability to compete is not evidence. Name the
evidence for every EVALUATED entry.

Do not profile anyone. Set membership only.
```

### P3 · Multi-Agent Evidence Sweep

Split along an 8-worker / 4-verifier grain. The verifier brief is a falsification brief, per step 5.

```
[P0]

TASK: Evidence sweep on the EVALUATED set from the roster at <path>.

WORKER SLICES, one competitor per worker where the set allows, otherwise
one surface per worker across the set:
pricing and packaging (with Wayback CDX diff, collapse=digest, id_ raw
captures) · docs and API surface · changelog and shipping cadence ·
trust centre and subprocessors · hiring signal from the ATS board ·
review corpus with velocity and the three-star text · community mentions ·
their comparison page about us (E6, logged as sales-motion intelligence).

Every worker returns claims in the record schema with evidence tiers and
full bibliography entries. No worker writes prose.

VERIFIER BRIEF, and this is different from review: your job is to FALSIFY,
not to confirm. Take each load-bearing claim in isolation, without reading
the draft that produced it, and try to find the source that contradicts it.
Report every claim you could not falsify as HELD, every one you could as
BROKEN with the counter-source, and every one you could not test as
UNTESTABLE with the reason.

STOP RULE: stop when the last two workers return nothing the set did not
already have. Report saturation explicitly. Do not continue past sufficiency
and do not stop before a competitor has at least one E3 source.
```

### P4 · The Chained Series

Seven stages, one per turn, each ending in a written artifact the next stage reads. Do not compress two stages into one turn.

| Stage | Turn produces | Reads |
|---|---|---|
| S1 | The decision sentence, written to the set page | The brief |
| S2 | The three-tier roster with evidence per entry | S1, plus P2 |
| S3 | The declared axes, with the source of each | S1 and S2 |
| S4 | Per-competitor records | S2 and S3, plus P1 or P3 |
| S5 | Falsification report: HELD / BROKEN / UNTESTABLE | S4's claims, in fresh context, without S4's prose |
| S6 | Capability matrix and set page | S3, S4, S5 |
| S7 | Cadence table and named owner | S6 |

The written handoff is the point. MAST, the multi-agent failure taxonomy built from 1,600 annotated traces, puts step repetition at 17.14% and reasoning-action mismatch at 13.98% as two of the largest failure modes. A stage that has to read the previous stage's file cannot silently redo it, and a stage whose output is a file cannot claim work it did not do.

---

## Options Review

From [the options-review protocol](../protocols/03-options-review.md). Run the inventory as its own pass, confirm the decision list, then run the deep dive one decision per run.

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

---

## Research Elicitation

From [the research elicitation protocol](../protocols/01-research-elicitation.md).

```
Topic: <X>

Step 1. List every sub-topic, dimension, and question someone needs answered
to fully understand <X>, with the probability that each appears in a
standard treatment of <X>. Do not answer them. Just enumerate. Then list
ten more, each under 0.10. Then critique your own list for gaps and add
what's missing.

Step 2. Use these perspectives: <the four to six found in related
articles on X>. For each item, answer across these axes: definition/
mechanism/application/critique; from each of those perspectives; what it
is and what it is not; exceptions, failure modes, and contraindications;
the case for and against; origins, consensus, and what's contested.

Step 3. Now tell me what you left out, what an expert would call
oversimplified, and what questions about <X> I have not asked. Give these
as a list with probabilities, including some under 0.10.

Flag every point where you are uncertain or where your answer is thin.
```

Send Step 4 as its own message once the model has answered Steps 1 to 3, and run those steps with no file attached, no project files, and web search off. If the outside list reaches the model before it writes its map, it builds the map from the list and the check comes back empty.

```
Step 4. Here is an outside list of what a standard treatment of <X>
covers: <paste a review's sections or a textbook's contents>. For each
item, name the entry in your map that covers it, or write "missing".
Then answer Step 2 for each missing item.
```
