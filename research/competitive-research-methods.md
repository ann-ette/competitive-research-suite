# Competitive Intelligence: Method, Sourcing, and the Law of Comparison

Topic page. What holds up in competitive research method once the vendor content
marketing is stripped out: how many vendors a buyer actually evaluates, why the
standard CI roster does not match that number, which source types can carry which
claims, and what the substantiation rules require before a comparison ships.

Opened 2026-08-25. Prompted by building [the competitive research protocol](../protocols/04-competitive-research.md),
ahead of a client competitive pass. Deliberately vendor-agnostic: no
competitor of any product is named here.

Tags: `competitive-intelligence` · `research-method` · `advertising-law`

> **Read alongside, do not duplicate:**
> [`study/09-competitive-intelligence.md`](../study/09-competitive-intelligence.md) owns the strategy
> frameworks (Dunford's competitive alternatives, phantom competitors, JTBD
> substitution, win/loss programs, analyst relations, SCIP ethics). This page is
> the evidence underneath it, and it corrects 09 in five places. Amendments are
> listed at the bottom.
> [The competitive research protocol](../protocols/04-competitive-research.md) is the process this page feeds. The protocol
> binds; this page explains why each rule is there.

---

## TL;DR

Buyers decide from a shortlist of three to five names they mostly already knew,
and CI programs track twenty to thirty, so most competitive research budget is
spent on companies that are never in the room. The fix is an inclusion test based
on evidence a buyer considered a name rather than on capability to compete. Every
claim then carries the tier of its best source, because vendor marketing is a
primary source about what a company claims and worthless about what its product
does. And a comparison that names a competitor is lawful and encouraged in the US
under 16 CFR §14.15, at the price of holding substantiation for every element,
including the blank cells.

## Confidence map

**High confidence** (two or more independent sources, or a primary document read
directly)

- The buyer shortlist is small and mostly pre-formed. 6sense and TrustRadius
  agree across different samples, different years, and different methods.
- SWOT-style unprioritized factor lists do not feed downstream decisions.
  Hill and Westbrook is a direct empirical study of fifty firms.
- Comparative advertising naming a competitor is lawful in the US and carries no
  elevated substantiation bar. 16 CFR §14.15 is a primary regulatory text.
- Nominative fair use permits using a competitor's mark to refer to the
  competitor, under the three-part *New Kids* test.
- Review-site composite scores fold in commercial signals, so a Grid position is
  not a capability measurement. G2 publishes its own methodology saying so.

**Medium confidence** (one strong source, or multiple secondary)

- CI teams track twenty to thirty competitors while buyers evaluate about five.
  The tracking figure is Crayon's, a vendor survey with an undisclosed sample
  size. The buyer figure is independent. The mismatch is a mechanism argument
  built from two sources rather than a measured finding.
- The proportion of intelligence coming from win/loss interviews (36%, Crayon
  2026). Same sample-size caveat.
- AI-mediated shortlist formation is rising fast. Directionally consistent across
  G2 and TrustRadius, and both are vendors with a stake in the answer.

**Contested or unresolved**

- The rate at which competitive intelligence decays. No credible non-vendor
  source exists (see "The ninety-day myth" below).
- The share of B2B deals ending in no decision. Ranges from roughly 20% to 60%
  across sources, and the denominators are not the same.
- Whether comparison-table column order affects reader judgment. No study found.

**Explicitly unusable, and why** (recorded so the next pass does not re-find them)

- The widely quoted "48% of buyers cite price as the reason, but only 23% of
  sellers know it" figure, attributed to Primary Intelligence. Could not trace to
  a published report with a stated sample or method. Do not quote.
- "Battlecards go stale in 90 days." Traces only to CI vendor blog content with
  no methodology. Do not quote.

---

## 1. The buyer's set is small, early, and mostly pre-formed

This is the finding that reorganizes everything else.

6sense's 2025 B2B Buyer Experience Report surveyed roughly 4,000 buyers with a
median deal size of $200,000 to $300,000. Buyers carried a median of **3.6
vendors on their Day One list** and evaluated **5.1 in total**. **95% purchased
from a vendor that was on the Day One list.** **85% had prior experience with the
vendor they chose**, and **77% contacted their eventual winner first.**

TrustRadius's 2026 B2B Buying Disconnect (n=1,862) reaches the same shape from a
different sample: **83% shortlisted three or fewer products**, and **79% already
knew the product they bought** before the evaluation started.

Three consequences for method:

**The competitive set is formed before any marketing reaches it.** By the time a
buyer is comparing, the roster is closed and the winner is usually already on it.
Research that optimizes the comparison stage is optimizing the last 5%.

**Familiarity is the dominant variable.** 85% prior experience means the highest
-leverage competitive move is being known early, and the second highest is being
the vendor the buyer contacts first. Neither is a feature question.

**Profiling depth should follow shortlist probability, not capability.** A company
that can do what you do and never appears on a buyer's list gets a WATCHLIST line,
never a full profile.

## 2. The roster arithmetic does not close

Crayon's 2026 State of Competitive Intelligence reports that **80% of CI teams
track thirty or fewer competitors**, most between eleven and thirty, and that
**only 36% of competitive intelligence comes from win/loss interviews**.

Set that beside the 5.1 figure. A CI program holds twenty names. A buyer holds
five. Nothing in a capability-derived roster identifies which five, and the
largest single source that would identify them (asking buyers directly) supplies
roughly a third of the input.

This is a mechanism argument assembled from two independent sources rather than a
measured finding, and it is strong enough to carry a process rule: **build the
roster from evidence that a buyer considered a name, and treat capability to
compete as insufficient.**

The three set members that a capability-derived roster structurally cannot
contain:

- **Do nothing.** Deferred budget, an unresolved decision, the status quo that
  costs nothing to keep.
- **Build in house.** A homegrown tool, a spreadsheet, a script with one
  maintainer.
- **The incumbent with an adjacent module.** A platform already on the buyer's
  contract that ships something in the neighborhood. It wins on procurement.

Dunford's competitive-alternatives framing (*Obviously Awesome*, 2019) makes the
same point from the positioning side: the alternative a customer would use if
your product vanished is frequently not a product.

## 3. Unprioritized factor lists do not reach a decision

Hill and Westbrook studied SWOT use at fifty companies (*Long Range Planning*
30(1), 1997, pp. 46-52). What they found: lists averaging **more than twenty
factors per analysis and often more than forty**, no prioritization within any
list, **no verification of any individual factor**, and **no evidence that any
list was used in a later stage of the strategy process**. Their conclusion was
that the technique should be retired in that form.

The finding generalizes past SWOT to any competitive artifact produced without a
named decision behind it. The failure is structural: an unbounded list has no
stopping rule, no prioritization criterion, and no consumer, so it grows until
effort runs out and then sits.

The process consequence is step 1 of the protocol. Write the decision the research
serves in one sentence before searching, and treat any finding that cannot move it
as out of scope.

## 4. Evidence tiers: what each source type can carry

The core distinction: **a vendor's own site is a primary source about what the
vendor claims and a weak source about what the product does.** Every failure of
competitive accuracy I can find in public comparison content collapses those two.

| Tier | Source | Primary for | Weak for |
|---|---|---|---|
| E1 | Hands-on evaluation, version and config recorded | What the product does | Pricing, roadmap, market position |
| E2 | Independent instrumented benchmark, published method | Performance and scale | Everything else |
| E3 | Vendor docs, API reference, changelog, pricing page | What they ship and commit to | Real cost after negotiation, usability |
| E4 | Review corpora, analyst reports, surveys | Sentiment, direction, volume | Any capability claim |
| E5 | Vendor marketing copy, landing pages, decks | What they claim | Nothing else |
| E6 | Their comparison page about you | Their sales motion | Any fact about either product |

### Why E4 gets discounted specifically

**G2.** The Grid is built from a Satisfaction score and a **Market Presence**
score, and Market Presence is a composite that includes web presence and
**pay-per-click spend**, domain authority, employee count, social following, and
revenue estimates. A vendor that buys more ads moves right on the Grid. Review
volume is also materially shaped by vendor-run review campaigns, which G2 permits
and which are common practice.

**Forrester.** Forrester replaced the Market Presence scoring category with
**Customer Feedback**, effective for Waves published on or after **2024-07-01**.
That is a real methodological improvement, and the customer feedback is still
gathered from **vendor-supplied references**, so a selection effect remains.

Neither of these makes E4 useless. Both make E4 unusable for a factual claim about
a product's capability, which is the only thing people reach for it to do.

### The AI-mediated shortlist, and why E4 is getting more consequential anyway

G2's 2026 Buyer Behavior research reports **AI chatbots at 37%** as a software
discovery source against **review sites at 38%**, and that **51% of buyers now
begin a search with an AI chatbot, up from 29% in April 2025**. TrustRadius's
2026 report puts **analyst reports at 13%** as a source buyers rely on.

Both are vendor-published and directionally consistent. The practical consequence
for competitive method: the corpus a model retrieves from is increasingly the
first surface a buyer sees, which raises the stakes on what public sources say
about a category and lowers the reliability of any single review site as a proxy
for buyer attention.

## 5. Hands-on evaluation is a contract question first

E1 is the strongest tier and frequently the one you cannot have.

- **Salesforce's Master Subscription Agreement** bars competitors from accessing
  the services.
- **Atlassian's Cloud Terms of Service** bar use of the products "for competitive
  analysis."
- **DeWitt clauses**, which prohibit publishing benchmark results without vendor
  approval, remain live in database and enterprise-software licences. The name
  comes from David DeWitt, whose 1983 benchmark of an Oracle product led to a
  contractual response that became an industry pattern.
- **SPEC** and **TPC** both publish fair-use rules governing how their benchmark
  results may be quoted, including required disclosure and comparison conditions.

Meanwhile **SCIP's Code of Ethics** requires accurate disclosure of identity and
organization before all interviews, which forecloses a false-identity signup.

So the two doors close on each other: the contract bars the honest signup, and
ethics bars the dishonest one. The correct handling is to read the terms first,
record the block by name in the record, and let the claim sit at E3.

## 6. Comparison content has case law, and blanks are the expensive part

**16 CFR §14.15** is the FTC's Statement of Policy Regarding Comparative
Advertising. It states the Commission's position that comparative advertising,
**when truthful and non-deceptive, is a source of important information** and
should be encouraged, that industry codes should not restrain the naming of
competitors, and that the **substantiation standard for comparative claims is the
same** as for any other advertising claim, with no higher bar.

That is permissive on naming and strict on proof. What the proof standard means in
practice:

**Lanham Act §43(a)** creates a private right of action for false or misleading
statements of fact about a competitor's product in commercial advertising. The
elements, as stated in *Pizza Hut, Inc. v. Papa John's International, Inc.*, 227
F.3d 489 (5th Cir. 2000): a false or misleading statement of fact about a product;
actual deception or a tendency to deceive a substantial segment of the audience;
materiality, meaning the deception is likely to influence a purchasing decision;
entry into interstate commerce; and injury to the plaintiff. *Pizza Hut* also
draws the line between actionable factual claims and non-actionable puffery, and
found "Better Ingredients. Better Pizza." to be puffery standing alone while
holding that the surrounding factual comparison claims changed the analysis.

**NAD is the practical venue.** BBB National Programs' National Advertising
Division resolves advertiser challenges faster and far more cheaply than
litigation, and its decisions are public. Two recent ones matter for comparison
tables:

- **NAD Case #7304, Deel v. Rippling (decided 2024-08-08).** NAD recommended
  discontinuing comparison-table claims where checkmarks and blank cells implied a
  competitor lacked a feature **without affirmative evidence for the absence**,
  and recommended discontinuing "market leader," "#1 Global HR platform," and
  "Teams prefer Deel over Rippling."
- **NAD, SharkNinja (decided 2024-11-24).** NAD looked past the individual claims
  to the **category boundary itself**, finding the defined comparison set drawn so
  as to make the superiority claim true.

The two together produce the rule that matters: **a blank cell is an affirmative
claim of absence and needs evidence, and the reviewed set is itself a claim that
needs stating.**

**Trademark use.** Using a competitor's mark to refer to the competitor is
nominative fair use under *New Kids on the Block v. News America Publishing, Inc.*,
971 F.2d 302 (9th Cir. 1992): the product is not readily identifiable without the
mark; only as much of the mark is used as is reasonably necessary; and nothing in
the use suggests sponsorship or endorsement.

**Outside the US**, EU **Directive 2006/114/EC** concerning misleading and
comparative advertising permits comparative advertising subject to conditions
including that it compares goods meeting the same needs, compares **material,
relevant, verifiable and representative features** objectively, and does not
discredit or take unfair advantage of a competitor's mark. National
implementations vary and some member states apply it more strictly.

## 7. The ninety-day myth

The claim that competitive intelligence, and battlecards specifically, decay in
about ninety days appears constantly and traces only to CI vendor blog content
with no stated method, no sample, and no measurement of what "stale" means.

Do not quote it. Set refresh cadence from the observable rate of change in each
source instead: a changelog that ships weekly needs a shorter cycle than a pricing
page that moves twice a year, and a funding round is an event rather than a
schedule. That is what the protocol's four-column cadence table exists to record,
and its fourth column ("what would change my mind") is what turns a refresh into a
check rather than a re-read.

## 8. The no-decision number is contested and the denominators differ

09 currently carries "20 to 30% of deals end in no decision." Sources range from
that up to the 40 to 60% figure associated with the JOLT research (Dixon and
McKenna, *The JOLT Effect*, 2022), and the spread is mostly a denominator problem:
some counts are of all opportunities entered, some of qualified opportunities,
some of late-stage forecast deals. JOLT also distinguishes indecision, meaning a
buyer who wants to act and cannot commit, from status-quo preference, which is a
different failure with a different remedy, and summaries collapse the two.

State the range and the reason for the range. Do not pick a point estimate.

---

## What I could not access

- **Crayon's stated sample size and method** for the 2026 State of Competitive
  Intelligence. The report presents percentages without an n in the accessible
  material. Substitute quality: none. Every Crayon figure on this page is
  medium-confidence for that reason.
- **The Primary Intelligence 48% / 23% price-attribution study.** Could not locate
  a published report, sample, or method behind the widely repeated figure.
  Substitute quality: none available. Marked unusable above.
- **Hill and Westbrook 1997 full text.** Read via the abstract and consistent
  secondary summaries of the finding. The factor counts and the "no verification,
  no downstream use" conclusion are attested across summaries; treat the exact
  averages as approximate rather than quoted.
- **Full NAD decision texts.** NAD press releases and case summaries were the
  accessible form. The recommendations quoted above appear in the summaries; the
  full reasoning is behind case-file access.
- **Gartner and Forrester full reports.** Paywalled. Forrester's methodology
  change date is from its public methodology page.

---

## Amendments Owed to `study/09-competitive-intelligence.md`

Recorded here so the wiki edit and its evidence stay linked.

1. Add Hill and Westbrook 1997 as the kill citation on unprioritized factor lists.
2. Add the roster arithmetic (§2) as the reason the inclusion test is evidence-based.
3. Add the Day One shortlist finding (§1) with both sources.
4. Correct the flat "20 to 30% no decision" against the JOLT range and name the
   denominator problem (§8).
5. Flag the Primary Intelligence 48% / 23% figure as untraceable, or cut it.
6. Add how G2's Market Presence score is composed (§4).
7. Add Forrester's 2024-07-01 Customer Feedback change (§4).
8. Add AI-mediated shortlisting as a discovery channel (§4).
9. Extend the SCIP ethics paragraph with the terms-of-service layer (§5), which
   ethics alone does not cover.
10. Add the legal layer (§6): 16 CFR §14.15, Lanham §43(a) elements, NAD as venue,
    nominative fair use.
11. Strip the Klue-shaped maturity model to what survives without buying the tool:
    a named owner, a fixed cadence, intelligence sourced from your own calls
    first, a declared consumer for the output, and one pre-declared KPI.

---

## Related Pages

- A companion page on multi-agent research practice, the agent-execution half of this pass (not in this package)
- [The competitive research protocol](../protocols/04-competitive-research.md) (the binding process)
- [`study/09-competitive-intelligence.md`](../study/09-competitive-intelligence.md) (frameworks)
- [`study/15-competitive-research-execution.md`](../study/15-competitive-research-execution.md) (study companion)
- My own product's competitor doc, the worked in-use example the record schema was generalized from (not in this package)

---

## Bibliography

- [2025 B2B Buyer Experience Report](https://6sense.com/) · 6sense, 2025. Accessed 2026-08-25. [secondary]
  Used for: §1, Day One list of 3.6, 5.1 evaluated, 95% purchase from Day One list, 85% prior experience, 77% contacted winner first. n≈4,000, median deal $200-300K.
- [2026 B2B Buying Disconnect](https://www.trustradius.com/) · TrustRadius, 2026. Accessed 2026-08-25. [secondary]
  Used for: §1, 83% shortlist three or fewer, 79% already knew the product; §4, analyst reports at 13%. n=1,862.
- [State of Competitive Intelligence 2026](https://www.crayon.co/) · Crayon, 2026. Accessed 2026-08-25. [secondary, vendor survey, sample size not disclosed]
  Used for: §2, 80% of CI teams track ≤30 competitors, 36% of intel from win/loss.
- [2026 Buyer Behavior Report](https://www.g2.com/) · G2, 2026. Accessed 2026-08-25. [secondary, vendor]
  Used for: §4, AI chatbots 37% vs review sites 38%, 51% start with a chatbot (29% April 2025).
- G2 Grid scoring methodology (Satisfaction and Market Presence components) · G2. Accessed 2026-08-25. [primary, about G2's own method]
  Used for: §4, Market Presence composition including PPC spend, domain authority, headcount, revenue estimates.
- Forrester Wave methodology (Customer Feedback replaces Market Presence, effective 2024-07-01) · Forrester Research. Accessed 2026-08-25. [primary, about Forrester's own method]
  Used for: §4.
- Hill, T. and Westbrook, R. "SWOT Analysis: It's Time for a Product Recall." *Long Range Planning* 30(1), 1997, pp. 46-52. [primary, abstract plus secondary summaries]
  Used for: §3. Fifty companies, 20+ and often 40+ factors, no prioritization, no verification, no downstream use.
- Dunford, A. *Obviously Awesome: How to Nail Product Positioning*. Ambient Press, 2019. [primary]
  Used for: §2, competitive alternatives including non-product alternatives.
- Dixon, M. and McKenna, T. *The JOLT Effect*. Portfolio, 2022. [primary]
  Used for: §8, the indecision vs status-quo distinction and the higher no-decision range.
- [16 CFR §14.15, Statement of Policy Regarding Comparative Advertising](https://www.ecfr.gov/current/title-16/chapter-I/subchapter-B/part-14/section-14.15) · Federal Trade Commission. Accessed 2026-08-25. [primary]
  Used for: §6, FTC encourages naming competitors; same substantiation standard, no higher bar.
- *Pizza Hut, Inc. v. Papa John's International, Inc.*, 227 F.3d 489 (5th Cir. 2000). [primary]
  Used for: §6, the five Lanham §43(a) elements and the puffery line.
- *New Kids on the Block v. News America Publishing, Inc.*, 971 F.2d 302 (9th Cir. 1992). [primary]
  Used for: §6, the three-part nominative fair use test.
- NAD Case #7304, *Deel v. Rippling*, decided 2024-08-08. BBB National Programs, National Advertising Division. Accessed 2026-08-25 via case summary. [primary, summary only]
  Used for: §6, checkmark-and-blank comparison tables need affirmative evidence for absence; "market leader," "#1 Global HR platform," "Teams prefer Deel over Rippling" recommended discontinued.
- NAD, *SharkNinja*, decided 2024-11-24. BBB National Programs, National Advertising Division. Accessed 2026-08-25 via case summary. [primary, summary only]
  Used for: §6, the defined comparison category itself found gerrymandered.
- [Directive 2006/114/EC concerning misleading and comparative advertising](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32006L0114) · European Parliament and Council, 2006-12-12. Accessed 2026-08-25. [primary]
  Used for: §6, EU conditions on comparative advertising.
- [SCIP Code of Ethics](https://www.scip.org/) · Strategic and Competitive Intelligence Professionals. Accessed 2026-08-25. [primary]
  Used for: §5, accurate identification of self and organization before all interviews.
- Salesforce Master Subscription Agreement; Atlassian Cloud Terms of Service. Accessed 2026-08-25. [primary]
  Used for: §5, competitor-access and competitive-analysis prohibitions.
- SPEC Fair Use Rules; TPC Fair Use Policy. Accessed 2026-08-25. [primary]
  Used for: §5, conditions on quoting benchmark results.

Last updated: 2026-08-25
