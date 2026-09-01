# Competitive Research Protocol

> Read this on "competitive research", "competitive analysis", "who else does this", "build me a competitive set", "battlecard", "comparison page", or when a positioning, pricing, or launch decision needs to know what the buyer is comparing against.

This is the fourth sibling to the [research protocol](02-research.md), the [elicitation protocol](01-research-elicitation.md), and the [options-review protocol](03-options-review.md). Elicitation finds the gaps in a topic. Research sources them. Options review benchmarks a technical decision against the field. This one governs research about **other organizations**, where the subject has a marketing department, a legal team, and an incentive to be misdescribed.

Everything in [the research protocol](02-research.md) still applies: source maps, primary-source priority, cross-verification, the blocked-source protocol, the bibliography entry shape. This file adds what changes when the source is a competitor.

The study-side companion, written for interview fluency rather than for execution, is [`study/15-competitive-research-execution.md`](../study/15-competitive-research-execution.md). The strategy frameworks it draws on live in [`study/09-competitive-intelligence.md`](../study/09-competitive-intelligence.md). This file is the binding process; those two teach and frame.

---

## Why This Exists

Three failures show up every time competitive research is done without a process.

**The set is drawn from capability instead of from evidence.** The list becomes every company that could plausibly solve the problem. Buyers do not work that way. In 6sense's 2025 B2B Buyer Experience Report (n≈4,000 buyers, median deal size $200,000 to $300,000), buyers carried a median of 3.6 vendors on their Day One list, evaluated 5.1 in total, and purchased from the Day One list 95% of the time. 85% had prior experience with the vendor they chose, and 77% contacted their eventual winner first. TrustRadius's 2026 B2B Buying Disconnect (n=1,862) found 83% shortlisted three or fewer products and 79% already knew the product they bought. Research that profiles twenty companies to inform a decision about five has spent its budget on the wrong fifteen.

**The arithmetic does not close.** Crayon's 2026 State of Competitive Intelligence reports that 80% of CI teams track thirty or fewer competitors, most between eleven and thirty, and that only 36% of intelligence comes from win/loss interviews. A buyer holds five names. A CI program holds twenty. The two sets are not the same five, and nothing in a capability-derived roster tells you which of the twenty are in play. This is a mechanism argument rather than a survey result, and it is the reason step 2 below builds the buyer's set before it builds mine.

**The output has no decision attached.** Hill and Westbrook studied SWOT use at fifty companies (*Long Range Planning* 30(1), 1997, pp. 46-52) and found lists averaging more than forty factors, no prioritization, no verification of any item, and no evidence that any list fed a later stage of the strategy process. The artifact was the deliverable. A competitive record with no decision behind it is the same object.

## The Failure It Prevents

- **Marketing copy read as capability.** A vendor's own site is a primary source about what they claim and a weak source about what the product does. Collapsing those two is how a comparison table becomes wrong in public.
- **The absent competitor.** Do-nothing, build-in-house, and the incumbent tool that already ships an adjacent module are usually the largest slices of a lost-deal pie and appear on no vendor roster.
- **Silent staleness.** A record with no `last_verified` date is a claim about the present made from an unknown past.
- **Confident self-review.** Asking a model to check its own competitive draft raises confidence without raising accuracy (Huang et al., ICLR 2024, on the limits of intrinsic self-correction). Verification has to happen in fresh context, against sources, with the draft out of the window.

## When To Run It

- Positioning or repositioning a product, a launch, or a feature set.
- Pricing or packaging work that needs to know what the buyer's alternatives cost.
- Any client engagement that names competitive research as an input.
- Building a comparison page, a battlecard, or sales-facing objection handling.
- A lost deal, or a pattern of them, where the reason is a named alternative.

## When Not To

- A single fact about a single company. That is a lookup, and [the research protocol](02-research.md) covers it.
- Curiosity with no decision behind it. Hill and Westbrook is the warning here.
- When the roster and the axes are already written down, dated inside the cadence window, and nothing has shipped or changed on either side.
- As a substitute for talking to buyers. Every scan below is a proxy for a conversation, and the conversation is better evidence than all of them.

---

## The Protocol

### 1. Name the decision the research serves

One sentence, written down before any search: what changes depending on what I find. "Whether the launch messaging leads with scale across many instances or with depth on one." "Whether to publish a comparison page against X." "Which three objections the sales deck has to answer."

If the sentence cannot be written, stop. The research has no consumer and will produce a forty-factor list.

Write the decision at the top of the set page. Every later artifact inherits it, and any finding that cannot affect it is out of scope no matter how interesting.

### 2. Build the buyer's set before building mine

Two rosters, in this order. The buyer's set comes first so that mine cannot anchor it.

**The inclusion test, binding: a name enters the set only when there is evidence a buyer considered it.** Capability to compete is not evidence. For every entry, name the evidence: a win/loss note, a sales call, a review-site "compared with" listing, a search-query family, a community thread, an RFP.

Three categories that belong in the set and are usually missing:

- **Do nothing.** The status quo, deferred budget, the decision that never resolves.
- **Build in house.** The homegrown dashboard, the spreadsheet, the internal tool with one maintainer.
- **The incumbent with an adjacent module.** A platform the buyer already pays for that ships something in the neighborhood. It wins on procurement rather than on capability, which is why it never appears in a feature-derived roster.

Output three tiers:

| Tier | Meaning |
|---|---|
| EVALUATED | A buyer would plausibly place this on a shortlist of five. Evidence named. |
| WATCHLIST | Real, and not yet showing up in buyer evidence. Recheck at cadence. |
| EXCLUDED | Considered and cut, with the reason written out. |

Write the EXCLUDED tier out in full. It is the record that keeps the next pass from rediscovering the same names, and it is the only place the roster's boundary is visible.

### 3. Declare the axes before looking

Name the comparison axes before opening a competitor's site, and derive them from the buyer's stated decision criteria rather than from my own feature list. Sources for the axes: win/loss notes, the tags buyers use on review sites, the shape of "X vs Y" search queries, the questions that recur on sales calls.

Axes chosen after looking are axes chosen to flatter. The options-review protocol's 2026-08-12 pass is the worked example of the same failure in a different domain: a model comparison ranked on price and latency because those were the two numbers the vendor dashboard published, and character quality, which was half the decision, went unmeasured. **Before comparing, ask whether the axes came from the decision or from whatever the source happened to publish.**

### 4. Source each competitor to a tier

Every capability claim carries an evidence tier. A claim never ships above the tier of its best source.

| Tier | Source | Primary for | Weak for |
|---|---|---|---|
| E1 | Hands-on evaluation in a documented environment, with the version, date, and config recorded | What the product actually does | Pricing, roadmap, market position |
| E2 | Independent instrumented benchmark with a published method and reproducible setup | Performance and scale behavior | Everything else |
| E3 | Vendor docs, API reference, changelog, release notes, pricing page | What they ship and what they commit to | What it is like to use, what it costs at negotiation |
| E4 | Review corpora, analyst reports, third-party surveys | Sentiment and market presence, discounted (see below) | Any capability claim |
| E5 | Vendor marketing copy, landing pages, sales decks, webinars | What they claim | Anything else. Nothing. |
| E6 | Their comparison page about me | Their sales motion and their read of my weaknesses | Any fact about either product |

**An E5-sourced cell reads "they claim."** Not "supports" and not "has." The verb carries the tier.

**Why E4 is discounted, specifically.** G2's Market Presence score folds in web presence and PPC spend, domain authority, employee count, and revenue estimates, so a Grid position moves when a vendor buys ads. Forrester replaced the Market Presence category with Customer Feedback effective 2024-07-01, which is an improvement and still scores vendor-supplied references. Review-site review counts are heavily influenced by vendor-run review campaigns. Use E4 for direction and volume. Never use it for a fact.

**The E6 rule.** A competitor's page about me is worth reading and is never evidence about me or about them. File it as sales-motion intelligence: which of my weaknesses they think will land, which of their strengths they lead with, what they think my buyer cares about. Their claims about my product get corrected against my own product, and their claims about their product get sourced to E3.

**On E1 and the contract problem.** Signing up for a competitor's trial is a contract question before it is an ethics question, and the answer is often no. Salesforce's MSA bars competitors from access. Atlassian's Cloud Terms of Service bar use "for competitive analysis." DeWitt clauses restricting published benchmarks are still live in database EULAs, and SPEC and TPC both publish fair-use rules governing how their results may be quoted. SCIP's code of ethics requires accurate identification, which forbids a false-identity signup; the contract clauses forbid the honest signup too. So: read the terms first, and if E1 is closed, say so in the record and let the claim sit at E3.

### 5. Verify adversarially, in fresh context

The verification pass has one instruction, and it is not "check this."

**Falsify each load-bearing claim in isolation, without reading the draft that produced it.** Take the claim, go looking for the source that contradicts it, and report HELD (could not falsify), BROKEN (falsified, with the counter-source), or UNTESTABLE (no source either way, with the reason).

The isolation is the mechanism. Chain-of-Verification (Dhuliawala et al.) cuts hallucinated entities from 2.95 to 0.68 per response, and the load-bearing part is that verification questions are answered independently of the draft. A verifier who reads the draft first grades the draft.

Mandatory falsification targets: every number, every date, every absence claim, every pricing figure, every scale claim, and every sentence that would embarrass me if it were wrong in public.

### 6. Write the record, then the set page, then the matrix

In that order. The matrix is derived from the records and cannot be written first without inventing cells.

### 7. Set the cadence and the owner, then stop

A record with no refresh date is already decaying. A cadence with no named owner is a hope. Both go on the set page before the pass closes.

**Stop at saturation.** When the last two sources return nothing the set did not already have, stop and say so explicitly. Do not stop before every EVALUATED competitor has at least one E3 source.

---

## The Per-Competitor Record

One file per competitor, at `knowledge-base/Companies/<Name>/competitive-profile.md`. Generalized from the field shape of my own product's competitor doc, which is the working example this schema was lifted from.

**Header**

- Name, and every alias, former name, and product name it ships under
- URL
- First profiled: YYYY-MM-DD
- Last verified: YYYY-MM-DD
- Scan number
- `Part of:` a link to the set page in `knowledge-base/Industries/<Category>/`

**Body**

| Field | Rule |
|---|---|
| What they are | One sentence. If it takes three, the category is unsettled and that is itself the finding. |
| Who they are for | The buyer they sell to, named by role. |
| Scale | Customers, revenue, headcount, funding. Every figure carries a source and a date. |
| Business model and pricing | Named tiers, published prices, the unit of pricing, what triggers a jump. Dated, because pricing pages change silently. |
| Capability facts | Each sentence carries its evidence tier in brackets. |
| What they do not have | Phrased as "as of YYYY-MM-DD, <named source> does not list X", with the link. Never "they lack X." |
| Where they win | The buyer situation where they are the right answer. Written honestly. |
| Where they lose | The buyer situation where they are not. |
| Their story about me | E6. Logged as sales motion. |
| Threat level | Ordinal, with a trigger. See below. |
| Open questions | What I could not determine, and what would settle it. |
| Bibliography | Full entries in [the research protocol](02-research.md) shape, including the `[primary / secondary / opinion]` tag and the `Used for:` line. |

### Threat level

Ordinal only: **LOW · LOW-MED · MED · MED-HIGH · HIGH**.

Every level carries a written escalation trigger and the evidence that would move it. "MED-HIGH. Escalates to HIGH if they ship group-level access scoping or appear in two more lost deals this quarter."

No weighted numeric scoring. A 7.4 out of 10 implies a measurement that does not exist, and the weights are always chosen after the scores. **An ordinal without a trigger is a mood.**

---

## The Capability Matrix

**Rows come from the buyer's decision criteria.** Win/loss notes, review-site tags, "X vs Y" query families, recurring sales-call questions. A matrix built from my own feature list proves I have my own features.

**Every cell carries a qualifier, a date, and the specific tier or version.** "Yes" and a checkmark are the two least defensible cells available. Write "group-level scoping, Enterprise tier only, as of 2026-08" rather than a mark.

**An empty cell is a claim and needs evidence.** NAD case #7304 (Deel v. Rippling, decided 2024-08-08) recommended discontinuing checkmark-and-blank comparison tables where the blanks implied absence without affirmative evidence, along with "market leader," "#1 Global HR platform," and "Teams prefer Deel over Rippling." NAD's SharkNinja decision (2024-11-24) went further and found the category boundary itself gerrymandered. Blanks are the expensive cells.

**Concede the rows I lose.** A matrix where one column wins every row is read as marketing and gets checked line by line, which is exactly what a comparison page cannot survive.

**State the reviewed set and the date beside the table.** "Compared against the four tools that appear on buyer shortlists alongside us, reviewed August 2026." A comparison implies a universe, and an unstated universe is where SharkNinja lost.

**Own product in column one.** This is a scan-anchoring convention rather than a sourced finding: the position-bias literature covers choice sets and ordering effects, and no study I found tests comparison-table column order specifically. Marked UNVERIFIED, kept for consistency.

---

## Where It Gets Filed

The rule that resolves `Companies/` versus `Industries/`:

**A claim about one organization lives in `knowledge-base/Companies/<Name>/`. A claim about the relationship between organizations lives in `knowledge-base/Industries/<Category>/`.**

So the roster, the inclusion test, the buyer-shortlist evidence, and the capability matrix are all relationship claims and live in `Industries/`, citing the `Companies/` pages for every underlying fact. Pricing, scale, and capability are single-organization claims and live in `Companies/`.

Two link obligations, both mandatory:

- Every `Companies/` page carries a `Part of:` line pointing at its set page.
- Every set page carries the roster with links to each `Companies/` page.

**What I decide to do about it never lives in `knowledge-base/`.** Positioning, messaging, the launch plan, the battlecard: those are deliverables and stay with their project. The knowledge base holds the durable finding.

### The Heading

**Inside the knowledge base, `## Bibliography` is the heading.** Full entry shape from [the research protocol](02-research.md), including the `[primary / secondary / opinion]` tag and the `Used for:` line. The older study pages in this package carry a numbered `## Sources` list, which predates the base and was left alone: renaming a heading across a working corpus restamps every page's date and destroys the staleness signal those dates carry.

---

## Monitoring and Refresh

Every set page ends with a cadence table in four columns:

| What | How often | Where | What would change my mind |
|---|---|---|---|

The fourth column is the one that does work. "Pricing page, quarterly, /pricing, a new tier or a change to the pricing unit" tells the next scan what it is looking for. Without it a refresh is a re-read.

**Numbered scans.** Scan 1, Scan 2, Scan 3. Each scan records its date and what it covered.

**Dated in-line amendments, never silent rewrites.** A changed fact gets appended as `**Update YYYY-MM-DD (Scan N):** <what changed, and what it was before>` next to the original claim. Overwriting destroys the record of what I believed and when, which is the only thing that makes a wrong call reviewable later.

**`last_verified` is per competitor, never per document.** A document-level date claims freshness for the least-checked fact on the page.

**One named staleness owner per set page.** A person, on the page.

**On decay rate: no credible non-vendor source exists.** The widely repeated claim that battlecards go stale in ninety days traces only to CI vendor content marketing with no published methodology. Set cadence from the observable rate of change in the source (a changelog that ships weekly needs a shorter cycle than a pricing page that moves twice a year) rather than from a number nobody can source.

---

## Guards

- **Never let E5 pass as E3.** The single most common failure in this work.
- **Never synthesize a number that is not in a source.** "Several days" does not become "48 to 72 hours." "Growing fast" does not become "40% year over year." This is the same rule that [the research protocol](02-research.md) enforces and it breaks more often here, because competitive writing rewards specificity and competitors publish vagueness.
- **Absence claims are the highest-risk claims in the document.** Phrase every one as a statement about a named source on a named date.
- **Log the blocked sources by name.** Gated pricing, a trial I could not lawfully take, an analyst report behind a paywall. Name it, name the claim it was needed for, and rate the substitute strong / weak / none.
- **Do not profile during set definition.** Step 2 answers membership. Anything else is scope creep that spends the budget before the roster exists.
- **A model's own recall about a competitor is not a source.** Model knowledge about company facts is stale by construction and confidently wrong about pricing in particular. Every fact gets fetched.

## The Ethics and Legal Gate

Run before any collection, and again before anything ships externally.

**Collection.** Public sources, accurate self-identification, no pretexting, no false-identity signups, no inducing anyone to breach a confidentiality obligation. SCIP's code requires accurate identification of self and organization. Read the target's terms of service before creating any account, and honor `robots.txt` and rate limits on any automated collection.

**Publication.** Naming a competitor in advertising is lawful and encouraged. 16 CFR §14.15 states the FTC's policy favoring comparative advertising that names competitors, and applies the same substantiation standard to those claims as to any other, with no higher bar. What that standard requires:

- Every comparative claim needs substantiation in hand **before** publication.
- A false or misleading statement of fact about a competitor's product in commercial advertising is actionable under Lanham Act §43(a). The elements are laid out in *Pizza Hut v. Papa John's* (5th Cir. 2000): a false or misleading statement of fact, actual deception or a tendency to deceive, materiality, interstate commerce, and injury.
- NAD is the practical venue. Faster and cheaper than litigation, decisions are public, and a comparison page that would not survive an NAD challenge should not ship.
- Using a competitor's trademark to refer to the competitor is nominative fair use. The test comes from *New Kids on the Block v. News America Publishing* (9th Cir. 1992): the product is not readily identifiable without the mark, only as much of the mark is used as is reasonably necessary, and nothing suggests sponsorship or endorsement.
- Outside the US: EU Directive 2006/114/EC permits comparative advertising under conditions including objective comparison of material, relevant, verifiable, and representative features. Country implementations vary.

**When a claim cannot be substantiated, it does not ship softened. It comes out.**

---

## The Prompts (Copy-Paste)

Written for a long-context single-agent pass and for a multi-agent fan-out; the tool names are generalized. P0 prepends to every one of them.

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

## Log

- 2026-08-25: Protocol created ahead of the client competitive pass that prompted it. Deliberately vendor-agnostic; no competitor named in this file. Research backing the method: [`research/competitive-research-methods.md`](../research/competitive-research-methods.md). The first worked pass ran 2026-08-26 to 2026-08-31.
