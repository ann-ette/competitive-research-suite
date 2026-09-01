# Competitive research execution

Page 09 covers the frameworks: battlecards, win/loss, Dunford's competitive alternatives, analyst relations, the SCIP ethics line. This page covers the execution underneath them. How the set gets drawn, what each source type can carry, how a claim is verified, where the record lives, how it stays current, and what the law requires before a comparison naming a competitor ships. It is the study version of [the competitive research protocol](../protocols/04-competitive-research.md), which is the binding process and wins on any conflict.

Last checked: 2026-08

## Core concepts

The organizing fact is that a buyer's competitive set is small, formed early, and mostly made of names the buyer already knew. In 6sense's 2025 B2B Buyer Experience Report (n≈4,000, median deal $200,000 to $300,000), buyers carried a median of 3.6 vendors on their Day One list, evaluated 5.1 in total, and bought from the Day One list 95% of the time. 85% had prior experience with the winner and 77% contacted that winner first. TrustRadius's 2026 B2B Buying Disconnect (n=1,862) reports 83% shortlisting three or fewer and 79% already knowing the product they bought.

Set that against Crayon's 2026 State of Competitive Intelligence, where 80% of CI teams track thirty or fewer competitors, most between eleven and thirty, and only 36% of intelligence comes from win/loss interviews. A CI program holds twenty names, a buyer holds five, and the roster does not say which five. That arithmetic is the reason execution starts with an inclusion test rather than with a feature comparison.

### The inclusion test

**A name enters the competitive set only when there is evidence a buyer considered it. Capability to compete is not evidence.** For every entry, the evidence gets named: a win/loss note, a sales call, a review-site "compared with" listing, a search query family, a community thread, an RFP.

That test is the operational form of Dunford's phantom-competitor warning on page 09. It also forces in the three set members a capability-derived roster structurally cannot contain: **do nothing**, **build in house**, and **the incumbent with an adjacent module** the buyer already pays for, which wins on procurement rather than on features.

The roster ships in three tiers. EVALUATED, meaning a buyer would plausibly shortlist it, with the evidence named. WATCHLIST, meaning real and not yet showing up in buyer evidence. EXCLUDED, with the reason written out, because the excluded tier is the only place the set's boundary is visible and it is what stops the next pass rediscovering the same names.

The failure this prevents has an old citation. Hill and Westbrook studied SWOT use at fifty companies (*Long Range Planning* 30(1), 1997) and found lists averaging more than twenty factors and often more than forty, with no prioritization, no verification of any individual factor, and no evidence that any list fed a later stage of the strategy process. An unbounded list has no stopping rule and no consumer, so it grows until effort runs out and then sits. The remedy is to write the decision the research serves in one sentence before searching.

### Evidence tiers

The distinction that matters most: **a vendor's own site is a primary source about what that vendor claims and a weak source about what the product does.** Collapsing those two is how a comparison page becomes wrong in public.

| Tier | Source | Primary for | Weak for |
|---|---|---|---|
| E1 | Hands-on evaluation, version and config recorded | What the product does | Pricing, roadmap, market position |
| E2 | Independent instrumented benchmark, published method | Performance and scale | Everything else |
| E3 | Vendor docs, API reference, changelog, pricing page | What they ship and commit to | Real negotiated cost, usability |
| E4 | Review corpora, analyst reports, surveys | Sentiment, direction, volume | Any capability claim |
| E5 | Vendor marketing copy, landing pages, decks | What they claim | Nothing else |
| E6 | Their comparison page about you | Their sales motion | Any fact about either product |

A claim never ships above the tier of its best source, and an E5-sourced cell reads "they claim." The verb carries the tier.

E4 gets discounted for a specific reason rather than a general one. G2's Grid combines a Satisfaction score with a **Market Presence** score, and Market Presence is a composite including web presence and pay-per-click spend, domain authority, employee count, social following, and revenue estimates, so a vendor that buys more ads moves right on the Grid. Forrester replaced its Market Presence category with **Customer Feedback** for Waves published on or after 2024-07-01, which is a genuine improvement and still draws on vendor-supplied references. Page 09 already tells you to read the specific report's legend. This is why.

E4 is also getting more consequential as a corpus even as it stays unusable as a fact. G2's 2026 buyer research puts AI chatbots at 37% as a discovery source against review sites at 38%, with 51% of buyers now starting a search in a chatbot, up from 29% in April 2025. What public sources say about a category increasingly becomes what a model tells the buyer first.

### Hands-on evaluation is a contract question

E1 is the strongest tier and often unavailable, for reasons that have nothing to do with ethics. Salesforce's MSA bars competitors from accessing the services. Atlassian's Cloud Terms of Service bar use "for competitive analysis." DeWitt clauses restricting publication of benchmark results are still live in database and enterprise-software licences, and SPEC and TPC both publish fair-use rules on how their results may be quoted.

Meanwhile the SCIP code on page 09 requires accurate disclosure of identity and organization, which forecloses a false-identity signup. So the contract closes the honest door and ethics closes the dishonest one. The handling is to read the terms first, record the block by name, and let the claim sit at E3.

### Verification is falsification, run in fresh context

Asking a model, or a person, to review their own competitive draft raises confidence without raising accuracy. Huang et al. (ICLR 2024) found intrinsic self-correction, with no external feedback and no oracle label, did not improve reasoning performance and in several settings degraded it.

What works is verification against something outside the draft. Chain-of-Verification (Dhuliawala et al., 2023) cut hallucinated entities from 2.95 to 0.68 per response, and the load-bearing detail sits in its factored variant: **verification questions are answered independently, without the draft in context.** A verifier who reads the draft first grades the draft.

Two practical moves follow. Phrase the instruction as falsification ("find the source that contradicts this") rather than confirmation ("check this"), because the two produce different searches. And make each claim self-contained before verifying it, in the manner of FActScore and SAFE, which decompose long output into atomic facts and revise each into a standalone sentence before scoring. A claim carrying a pronoun cannot be checked alone, which is also why absence claims get written as "as of 2026-08-14, their published pricing page does not list X" rather than "they lack X."

### The record, the matrix, and the threat level

One record per competitor, with a fixed field set: what they are in one sentence, who they are for, scale, business model and pricing with named tiers and dates, capability facts each carrying an evidence tier, what they do not have phrased as a statement about a named source on a named date, where they win, where they lose, their story about you, threat level, open questions, and a bibliography.

**Threat level is ordinal with a written escalation trigger.** LOW through HIGH, and every level says what would move it: "MED-HIGH, escalates to HIGH if they ship group-level access scoping or appear in two more lost deals this quarter." No weighted numeric scoring, because a 7.4 out of 10 implies a measurement that does not exist and the weights always get chosen after the scores. An ordinal without a trigger is a mood.

**Matrix rows come from the buyer's decision criteria**, sourced from win/loss notes, review-site tags, "X vs Y" query families, and recurring sales-call questions. A matrix built from your own feature list proves you have your own features. Every cell carries a qualifier, a date, and the specific tier or version. Concede the rows you lose, because a column that wins every row gets read as marketing and then gets checked line by line.

### Blank cells are the legal exposure

Naming a competitor is lawful and encouraged. **16 CFR §14.15**, the FTC's Statement of Policy Regarding Comparative Advertising, says comparative advertising that is truthful and non-deceptive is a source of important information, that industry codes should not restrain naming competitors, and that the substantiation standard is **the same** as for any other claim, with no higher bar.

The price is holding substantiation for every element before publication, including the elements that are not written down.

**NAD Case #7304, Deel v. Rippling (2024-08-08)** recommended discontinuing comparison-table claims where checkmarks and blanks implied a competitor lacked a feature without affirmative evidence, along with "market leader," "#1 Global HR platform," and "Teams prefer Deel over Rippling." **NAD's SharkNinja decision (2024-11-24)** went past the individual claims to the category boundary itself, finding the comparison set drawn so as to make the superiority claim true. Together: a blank cell is an affirmative claim of absence and needs evidence, and the reviewed set is itself a claim that needs stating beside the table.

If it goes to court instead, **Lanham Act §43(a)** supplies the private right of action, with the elements laid out in *Pizza Hut v. Papa John's*, 227 F.3d 489 (5th Cir. 2000): a false or misleading statement of fact, actual deception or a tendency to deceive, materiality, interstate commerce, and injury. Using the competitor's trademark to refer to the competitor is nominative fair use under *New Kids on the Block v. News America Publishing*, 971 F.2d 302 (9th Cir. 1992), on a three-part test. In the EU, Directive 2006/114/EC permits comparative advertising subject to conditions including objective comparison of material, relevant, verifiable, and representative features.

### Refresh, and the number you should stop quoting

Page 09 is right that staleness is the number-one battlecard failure and right that updates should track competitor moves rather than the calendar. What it should not carry is a decay rate. The claim that competitive intelligence goes stale in about ninety days traces only to CI vendor blog content with no stated method, no sample, and no definition of stale.

Set cadence from the observable rate of change in each source. A changelog that ships weekly needs a shorter cycle than a pricing page that moves twice a year, and a funding round is an event rather than a schedule. The mechanism is a four-column cadence table: what, how often, where, and **what would change my mind**. The fourth column is what turns a refresh into a check rather than a re-read.

Two more rules keep the record honest over time. A changed fact gets appended as a dated in-line amendment (`**Update 2026-08-25 (Scan 3):** pricing moved from per-server to per-core; was per-server at $99`) rather than overwritten, because overwriting destroys the record of what you believed and when. And `last_verified` is per competitor, since a document-level date claims freshness for the least-checked fact on the page.

## How strong teams do it

They write the decision before they search. One sentence saying what changes depending on what the research finds, at the top of the set page, so every later artifact inherits a consumer and anything that cannot move it is out of scope.

They build the buyer's set before their own, and they defend the boundary in writing. The EXCLUDED tier with reasons is the artifact that stops the same twelve names getting re-litigated every quarter.

They tier their sources out loud. The record says which claims came from a docs page and which came from a landing page, so a reader can tell where the confidence is thin without re-doing the research.

They verify by trying to break their own claims, in a separate pass, without the draft in front of them. And they log what they could not access by name, with the claim it was needed for and whether a substitute exists.

They read the target's terms of service before creating any account, and they treat a competitor's comparison page about them as intelligence about that competitor's sales motion rather than as a fact about either product.

## Common mistakes

- **Building the set from capability.** Every company that could solve the problem, rather than every company a buyer actually weighed. The output is a roster of twenty for a decision about five.
- **Reading marketing copy as capability.** An E5 claim written into a comparison table as an E3 fact. The most common way this work becomes wrong in public.
- **Checkmark-and-blank comparison tables.** A blank is an affirmative claim of absence, and NAD has said so.
- **Leaving the reviewed set unstated.** SharkNinja is the case where the category boundary was the problem rather than any individual claim.
- **Absence claims phrased as facts about the company.** "They lack X" ages badly and cannot be verified. "As of this date, this named source does not list X" can.
- **Weighted threat scores.** A composite number implies a measurement nobody took, and the weights get chosen after the scores.
- **Self-review as verification.** Confidence goes up, accuracy does not, and now the errors are underwritten.
- **Silent rewrites during a refresh.** The record of what you believed and when is the only thing that makes a wrong call reviewable later.
- **Quoting the ninety-day decay figure.** No method behind it.

## Worked example

**Valoquent.** Page 09 already runs the positioning half of this: the real first competitor is the status quo, and Yoodli is a contrast rather than a rival. The execution half is what the record looks like once that is settled.

The inclusion test cuts the naive roster hard. Hello History, Text With History, and History Chat AI enter as EVALUATED only if there is evidence a user weighed them, which for a consumer app means App Store "similar apps" surfacing, Reddit threads in the AI-tutoring and AI-companion communities, and search families like "apps to talk to historical figures." Character.ai and Replika are the adjacent-category substitution slice. "Do nothing" and "keep using a generic chatbot" are first-class set members and get their own lines. Yoodli goes to EXCLUDED with the reason written out, which is the phantom-competitor call made once, in a place the next pass will find it.

The evidence tiering changes what can be claimed. Feature lists on a competitor's App Store page are E5, so any capability row reading "they claim." Screenshots and a version-stamped hands-on session on a free tier are E1, subject to reading the terms first. Review counts and star ratings are E4, useful for velocity and sentiment and useless as a capability claim.

The axes come from what users say they are choosing on. Whether the figure is scored, whether it cites anything, whether it is voice or text, whether it is free. Not from Valoquent's own feature list, which would make the visible conversation-quality meter a row that every competitor loses by construction and tell you nothing about the decision.

## Interview fluency

**Terms to know cold:**

- **Inclusion test.** A name enters the competitive set only with evidence a buyer considered it. Capability to compete is not evidence.
- **Day One list.** The vendors a buyer starts with, median 3.6 (6sense 2025). 95% of purchases come from it.
- **EVALUATED / WATCHLIST / EXCLUDED.** The three roster tiers. The excluded tier carries the reason, and it is where the set's boundary lives.
- **Evidence tier (E1 to E6).** The scale from hands-on evaluation down to a competitor's comparison page about you. A claim never ships above the tier of its best source.
- **E5 problem.** Vendor marketing is a primary source about what a vendor claims and a weak source about what the product does.
- **Absence claim.** "As of DATE, NAMED SOURCE does not list X." The highest-risk sentence in a competitive document.
- **Falsification pass.** Verification run in fresh context against sources, with the instruction to break the claim rather than confirm it.
- **Escalation trigger.** The written condition that would move a threat level. An ordinal without one is a mood.
- **Cadence table.** What, how often, where, and what would change my mind. The fourth column is the working one.
- **16 CFR §14.15.** The FTC policy encouraging comparative advertising that names competitors, at the same substantiation standard as any other claim.
- **Lanham §43(a).** The private right of action for false or misleading factual claims about a competitor's product. Elements from *Pizza Hut v. Papa John's*.
- **NAD.** BBB National Programs' National Advertising Division. The fast, public, cheap venue where comparison pages get challenged.
- **Nominative fair use.** Using a competitor's mark to refer to the competitor, under the three-part *New Kids* test.
- **DeWitt clause.** A licence term barring publication of benchmark results without vendor approval.

**Likely questions and talking points:**

*How do you decide who's actually a competitor?* Evidence that a buyer considered them, never capability to compete. Buyers carry about three or four names on day one and buy from that list 95% of the time, so a roster of twenty is mostly companies that were never in the room. I build the buyer's set first from win/loss, search families, review-site comparison surfaces, and community threads, and I force in the three that a feature-derived roster always misses: do nothing, build in house, and the platform they already pay for that ships something adjacent. Everything cut goes into an excluded tier with the reason, so the boundary is visible.

*How do you keep competitive claims defensible?* Every claim carries the tier of its best source, and the biggest failure is letting marketing copy pass as capability. A vendor's site tells me what they claim and almost nothing about what the product does, so an E5-sourced row reads "they claim." Absence claims get the most care, because a blank cell in a comparison table is an affirmative claim that they lack something. NAD told Deel to stop doing exactly that in 2024. I write it as "as of this date, this named source does not list it," with the link.

*Can you publish a comparison page that names a competitor?* Yes, and the FTC actively encourages it. 16 CFR §14.15 says comparative advertising that names competitors is valuable and applies the ordinary substantiation standard, no higher bar. The cost is holding the substantiation before publishing, including for the blanks, and stating the reviewed set beside the table, since SharkNinja was a case where the category boundary itself was the problem. If a claim can't be substantiated it comes out rather than getting softened.

*How do you verify competitive research you or a model produced?* Not by re-reading it. Self-review raises confidence and not accuracy, which Huang et al. showed at ICLR 2024. I run a separate falsification pass in fresh context, without the draft in view, and the instruction is to find the source that contradicts each load-bearing claim. Each claim gets rewritten to stand alone first, so it can be checked without its paragraph. Then it comes back HELD, BROKEN with the counter-source, or UNTESTABLE with the reason.

*How often should competitive intelligence be refreshed?* From the observable rate of change in each source rather than from a fixed interval. I don't quote the ninety-day staleness figure, because it traces to vendor blog content with no method behind it. A changelog that ships weekly gets a tighter cycle than a pricing page that moves twice a year. The cadence table has a column for what would change my mind, which turns the refresh into a check. Changed facts get dated in-line amendments rather than overwrites, and last-verified is per competitor, since a document-level date claims freshness for the least-checked fact on the page.

## Signals to watch

In a daily scan, the items that belong on this page rather than on 09:

- **Advertising-law rulings on comparison content**: new NAD decisions on comparison tables, superiority claims, or gerrymandered categories, and any Lanham §43(a) case turning on a competitive claim.
- **Review-site and analyst methodology changes**: how G2 composes Market Presence, Forrester's scoring categories, anything that changes how a placement should be cited.
- **Buyer-behavior research with a stated n and method**: 6sense, TrustRadius, Gartner buying studies. Shortlist size and discovery-channel mix are the two numbers that move this page.
- **AI-mediated discovery data**: the share of buyers starting in a chatbot, and any research on which sources those systems retrieve from.
- **Terms-of-service changes at major vendors** that bar competitive evaluation, plus any live DeWitt-clause dispute.
- **Verification and hallucination research**: anything that changes how a sourced claim should be checked, especially work on verification in isolation from the draft.

## Sources

1. 2025 B2B Buyer Experience Report. 6sense. https://6sense.com/
2. 2026 B2B Buying Disconnect. TrustRadius. https://www.trustradius.com/
3. State of Competitive Intelligence 2026. Crayon. https://www.crayon.co/
4. 2026 Buyer Behavior Report. G2. https://www.g2.com/
5. Hill, T. and Westbrook, R. "SWOT Analysis: It's Time for a Product Recall." Long Range Planning 30(1), 1997, pp. 46-52.
6. Statement of Policy Regarding Comparative Advertising, 16 CFR §14.15. Federal Trade Commission. https://www.ecfr.gov/current/title-16/chapter-I/subchapter-B/part-14/section-14.15
7. Pizza Hut, Inc. v. Papa John's International, Inc., 227 F.3d 489 (5th Cir. 2000).
8. New Kids on the Block v. News America Publishing, Inc., 971 F.2d 302 (9th Cir. 1992).
9. NAD Case #7304, Deel v. Rippling, decided 2024-08-08. BBB National Programs.
10. NAD, SharkNinja, decided 2024-11-24. BBB National Programs.
11. Directive 2006/114/EC concerning misleading and comparative advertising. European Parliament and Council. https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32006L0114
12. Huang et al. "Large Language Models Cannot Self-Correct Reasoning Yet." ICLR 2024. https://arxiv.org/abs/2310.01798
13. Dhuliawala et al. "Chain-of-Verification Reduces Hallucination in Large Language Models." https://arxiv.org/abs/2309.11495
14. Min et al. "FActScore: Fine-grained Atomic Evaluation of Factual Precision in Long Form Text Generation." EMNLP 2023. https://arxiv.org/abs/2305.14251
15. Wei et al. "Long-form factuality in large language models." https://arxiv.org/abs/2403.18802
16. SCIP Code of Ethics for Competitive and Market Intelligence. SCIP. https://www.scip.org/

## Related

- [Competitive intelligence and analyst relations](09-competitive-intelligence.md)
- Positioning and category design (page 02 of the larger wiki, not in this package)
- Customer and market understanding (page 04 of the larger wiki, not in this package)
- Sales enablement (page 08 of the larger wiki, not in this package)
- PMM career and interview study guide (page 14 of the larger wiki, not in this package)
- [The competitive research protocol](../protocols/04-competitive-research.md) is the binding process this page studies.
- [`research/competitive-research-methods.md`](../research/competitive-research-methods.md) holds the sourced research behind both.
