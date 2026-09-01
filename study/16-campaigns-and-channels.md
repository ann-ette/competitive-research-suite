# Campaigns and channels

Page 06 covers launch tiering and the cross-functional management around it. Page 10 covers PMM's role in demand and the handoff. This page covers the campaign underneath both: how a launch gets tiered from what changed for the buyer, how the thesis sentence is written, how surfaces get sequenced, what measurement can be declared in advance, and what attribution can and cannot carry. It is the study version of [the launch campaign protocol](../protocols/05-launch-campaign.md), which is the binding process and wins on any conflict.

The execution layer for social, paid, and the content pipeline belongs to a separate channel playbook. This page holds the decision about whether a channel carries the launch and what it has to accomplish. What gets posted, when, in what format, on which account, lives there.

Last checked: 2026-08

**Evidence note, read first.** Large parts of this page are argument from mechanism with no study behind them, and they are marked **[reasoning]** in place. Campaign practice is one of the least-sourced areas in this wiki, because the published material is dominated by vendor content marketing with a commercial interest in the answer. The answer-engine section is the exception and is fully sourced. Sourced passes on website conversion, SEO as a practice, email, and developer marketing are owed. Where a number appears below it carries its source, and where no number appears, that is the finding.

## Core concepts

### Tier from what changed for the buyer

Page 06 already establishes launch tiering. The addition here is the input to the tier, which is where the decision usually goes wrong. **[reasoning]**

Effort is the input teams reach for, because the people planning the launch built the thing and know exactly how hard it was. Difficulty and importance are unrelated quantities, and a tier set from difficulty distributes the budget by how the work felt.

The input that works is what changed for the buyer. Tier 1 means a new reason to consider the product at all: a new buyer, a new category, or a new job the product now does. Tier 2 means a material capability an existing buyer will change behavior over, or evaluate a renewal on. Tier 3 means an improvement an existing user notices and nobody switches over.

**The check against tier inflation:** name the buyer who is not currently considering the product and say what this makes them do. Everything feels like a tier 1 from inside the build, and that sentence is the cheapest available test.

### The launch thesis

One sentence, before any surface, any name, and any channel: **who changes their mind, from what to what, and on what proof.**

This is the same discipline the competitive protocol puts at its step 1 and page 15 describes, and it exists for the same reason. Hill and Westbrook studied SWOT use at fifty companies (*Long Range Planning* 30(1), 1997, pp. 46-52) and found lists averaging more than forty factors with no prioritization, no verification, and no evidence any list fed a later stage of the strategy process. An artifact with no consumer grows until effort runs out and then sits. A campaign plan with no thesis is that artifact with channels in it.

Three parts, each of which fails on its own:

- **Who.** A role with the situation they are in. "Developers" names no situation and no decision.
- **From what to what.** Both ends stated. A thesis naming only the destination is describing a feature.
- **On what proof.** The artifact doing the convincing. If the proof is the messaging, there is no proof.

### Surfaces sort by decay rate

Owned, earned, and paid describes who controls the surface. The property that governs sequencing is how fast the surface decays, and that split cuts across all three. **[reasoning]**

A social post is spent on publication. A paid campaign lasts as long as the spend. A docs page, a landing page, and a named concept in third-party writing keep working for months or years, and they are what an answer engine reads later.

**Order the work slowest-decaying first.** The surfaces that accrue have to exist before the surfaces that decay point at them. The recognizable failure is a launch-day post pointing at a page written the night before.

**Every launch needs one destination that survives it.** A campaign that ends with nothing durable created bought attention and stored none of it.

### Measurement gets declared before, or it gets chosen to flatter

Metric, baseline, window, and the result that would make you stop. All four written before launch.

The mechanism is the same one page 15 describes for comparison axes. Axes chosen after looking are chosen to flatter, and an analytics dashboard will always offer a number that moved. Declaring in advance is what makes the result capable of being negative.

**Reach metrics are diagnostics.** Impressions, engagement, and follower change describe the platform's distribution behavior. They belong in a labeled row of their own, and they answer a different question from the one the launch was for.

**The kill criterion is the part that gets skipped.** Without a written stop condition, an underperforming campaign gets extended, because ending it requires someone to say out loud that it failed.

### Attribution is worse than the tools imply

Any campaign running on more than one surface at once cannot cleanly assign credit, and every dashboard that assigns it anyway is applying a model somebody chose: last touch, first touch, linear, time decay, or a vendor's proprietary blend. **[reasoning]**

The honest handling is to name the model in use and its known bias beside the number. Last-touch attribution systematically over-credits the final surface, which is usually paid search or a direct visit, and systematically under-credits whatever created the intent. Reporting its output as measurement launders a modeling choice into a fact.

### The answer-engine surface is a citation problem

When a buyer asks a model about the problem instead of searching for it, the question is whether the product appears in the answer. G2's 2026 buyer research puts 51% of buyers starting a search in a chatbot, up from 29% in April 2025, with AI chatbots at 37% as a discovery source against review sites at 38%.

Page 13 covers this as a PMM shift and the GTM wiki holds the deeper execution treatment. What belongs here is the campaign-planning version, and the evidence is more negative than the category's own literature implies.

**Size the prize before resourcing it.** Pew Research Center (2025-07-22) tracked 900 U.S. adults with a browsing tracker across 68,879 Google searches in March 2025, 12,593 of which produced an AI summary. Users clicked a traditional result in 8% of visits when a summary was present against 15% when it was not, and clicked a link inside the summary in **1% of visits**. Google disputes the methodology and has published no counter-figures. This is a consideration surface. Planning it as an acquisition channel is the mistake.

**The published tactics mostly failed replication.** Aggarwal et al. (KDD 2024) is the paper the category rests on, and its main experiment is gpt-3.5-turbo over the top five Google results, with visibility defined as position-weighted word share of the generated answer. No human behavior is measured in it. Puerto et al. (C-SEO Bench, NeurIPS 2025) tested nine methods across six domains and 1,921 queries at varying adoption rates and found most ineffective and often negative, with ordinary ranking work more effective and gains shrinking as adopters increase. Two specifics worth carrying: keyword stuffing scored **below** the do-nothing baseline, and the gains concentrate in already-low-ranked sources while the top-ranked source lost visibility on average. If you are already the answer, these interventions can cost you.

**Measurement costs more than any dashboard spends.** Kirsten et al. (Findings of ACL 2026) found that repeating the same query within five minutes at temperature 0 changes the overall decision for 9% to 27% of queries. Schulte et al. (2026) put a defensible per-brand detection rate at 7 to 8 repetitions per prompt with rolling aggregation over two to four weeks, and found 57.8% of ChatGPT runs returned zero citations because search never activated. A single-run check is noise, and a vendor reporting share of voice to one decimal place from a daily run is reporting a number narrower than its own error bar.

**Most of the circulating advice about controls is wrong.** robots.txt does not govern answer-time fetches for OpenAI, Perplexity or Google, all three of which document that their user-triggered fetcher ignores it, with Anthropic the documented exception. Google-Extended does not cover AI Overviews. No provider reads llms.txt, and log analysis found zero AI-bot requests for llms.txt files that do not exist, meaning no crawler even probes for it. Google states in two official pages that no schema.org markup is needed for generative search.

Treat GEO and SEO vendor content as E5 on the evidence tier table from page 15: primary about what they claim and worthless about what works. Sourcing for all of the above is in [`research/llm-search-visibility.md`](../research/llm-search-visibility.md).

## How strong teams do it

They tier the launch before planning it, from buyer change, and they write the tier and its one-sentence reason at the top of the plan so the budget has a stated basis.

They write the thesis sentence first and let it kill assets. An asset that cannot be traced to who changes their mind, from what to what, is out of scope no matter how good it is.

They build the durable surface before the loud one. The docs page, the landing page, and the reference material exist before launch day, and the posts point at them.

They declare measurement in advance, including the number that would make them stop, and they report reach separately from outcome with the labels intact.

They say which attribution model produced any number they quote, and they say what it over-credits.

They write down what they decided not to do. The cut channels with reasons are what stop the same six being re-argued at the next launch.

## Common mistakes

- **Opening the plan with a channel table.** If channels come first, the tier and the thesis were never decided and the campaign is running on habit.
- **Tiering from internal effort.** Difficulty and importance are unrelated, and the team that built the thing cannot feel the difference.
- **Reach reported as outcome.** Impressions are cheap to move and describe the platform. A campaign reporting them has usually failed to find anything else.
- **The launch-day post pointing at a page written the night before.** Decay order inverted.
- **Positioning written during the launch.** Messaging that first appears under a deadline has been tested against nothing, and it becomes the product's public claim by accident.
- **Attribution quoted without its model.** A modeling choice reported as a measurement.
- **No kill criterion.** Underperformance extends the campaign instead of ending it.
- **A landing page for a launch that ended.** Every asset needs a retirement rule, or the site slowly starts misdescribing the product.
- **Quoting GEO vendor numbers.** Commercial interest in the answer, no published method.

## Worked example

**Valoquent.** The app shipped to the iOS App Store on 2026-05-11 and Android 2.0.1 on 2026-05-20, and the visible conversation-quality meter is the differentiator page 09 and page 15 both turn on.

The tier question is the interesting one. Internally the meter was the hardest thing in the build, which argues tier 1 by effort. The buyer-change test asks who is not currently considering an app for talking to historical figures and what the meter makes them do, and the honest answer names a distinct buyer: someone who wants feedback on how they think, who would not have looked at a historical-conversation app at all. That is a tier 1 on the correct input, and it happens to agree with the effort read. When those two disagree, the buyer read wins.

The thesis sentence: a person who believes AI conversation apps are entertainment changes their mind when they see a score for the quality of their own reasoning, proved by the meter running live in a thirty-second clip. Both ends stated, and the proof is a thing rather than a claim.

Decay ordering puts the App Store listing, the site, and the meter explanation first, because those are the surfaces still working in month six. The SIGGRAPH 2026 Appy Hour selection and the solo-authored ACM publication are the earned row, and they are the highest-value assets in the campaign precisely because a third party issued them and they stay citable indefinitely.

Measurement declared in advance would have to be something only a convinced person does, which for this product is completing a scored conversation and returning for a second. Installs are the diagnostic. The kill criterion sits on the gap between the two.

## Interview fluency

**Terms to know cold:**

- **Launch tier.** The size of the launch, set by what changed for the buyer. Tier 1 is a new reason to consider the product at all, tier 3 is an improvement nobody switches over.
- **Tier inflation.** Everything reading as a tier 1 from inside the build. The test is naming the buyer who is not currently considering the product.
- **Launch thesis.** One sentence: who changes their mind, from what to what, on what proof.
- **Decay rate.** How long a surface keeps working after publication. The property that determines sequencing, and the one owned/earned/paid does not expose.
- **Durable destination.** The one asset that outlives the campaign. A launch without one stored nothing.
- **Kill criterion.** The written result that ends the campaign. Without it, underperformance extends it.
- **Diagnostic versus outcome metric.** Reach tells you distribution worked. The outcome metric is something only a convinced buyer does.
- **Attribution model.** Last touch, first touch, linear, time decay. A choice, with a known bias, that gets reported as a measurement.
- **AEO / GEO.** Optimizing to be cited in an answer engine's response. Citation is the mechanism, and vendor claims here sit at E5.
- **Retirement rule.** What happens to each asset when the launch ends.

**Likely questions and talking points:**

*How do you decide how big a launch should be?* By what changed for the buyer, and I say that specifically because the input teams actually use is internal effort. The people planning the launch built the thing and know exactly how hard it was, and difficulty tells you nothing about importance. So the test I run is to name the buyer who is not currently considering us and say what this release makes them do. If I can write that sentence it is a tier 1 and it earns a full campaign. If I cannot, it is a tier 2 and it gets the owned surfaces and one earned push. That check is cheap and it is the only thing I have found that survives the enthusiasm in the room.

*How do you plan a launch across channels?* I sequence by decay rate before I think about channels at all. Owned, earned, and paid tells me who controls the surface and hides the thing I need, which is how long each surface keeps working. A post is spent the day it goes up. A docs page and a landing page are still doing the job in month six, and they are what gets cited when someone asks a model about the problem later. So the durable surfaces get built first and the loud ones point at them. The failure I am designing against is the launch-day post pointing at a page written the night before.

*How do you measure a launch?* I write the metric, the baseline, the window, and the result that would make me stop, all four before anything ships. The reason is the same one that governs competitive analysis: anything chosen after you look gets chosen to flatter, and an analytics dashboard will always hand you a number that moved. I keep reach in its own labeled row as a diagnostic, because impressions describe the platform's distribution rather than the buyer's decision. And I name the attribution model beside any number that came out of one, along with what it over-credits, since last touch systematically flatters whatever the buyer touched last and starves whatever created the intent.

*Where does AI search fit into a launch?* I would size it before resourcing it. Pew tracked 900 people across nearly 69,000 Google searches and found that when an AI summary appeared, people clicked a link inside that summary in one percent of visits. So it is a consideration surface, and planning it as an acquisition channel is the error. On tactics I would be blunt: the GEO paper everyone cites ran gpt-3.5-turbo over five Google results and measured word share of the generated answer, not a single human behavior, and the direct replication at NeurIPS last year found most of those methods ineffective or negative and found the whole thing goes zero-sum as adoption rises. The finding I would actually act on is that the gains concentrated in low-ranked sources while the top-ranked source lost visibility, so if you are already the answer these tactics can cost you. And measurement is expensive: the same query at temperature zero flips its answer for nine to twenty-seven percent of queries within five minutes, so you need seven or eight repetitions and a multi-week window before a number means anything. Most of what is sold here is vendor content with a commercial interest and no published method.

*What do you do when a campaign underperforms?* Whatever the kill criterion said, which is why it gets written down in advance. Without it the conversation becomes whether to admit failure, and the default answer to that is always to extend. I would also separate two failures that look identical in the numbers: distribution that did not reach anyone, and a message that reached people and did not move them. Reach metrics tell those apart, which is the job they are actually good for.

## Signals to watch

In a daily scan, the items that belong on this page rather than on 06 or 10:

- **Buyer-behavior research with a stated n and method** on discovery channels and shortlist formation. 6sense, TrustRadius, G2, Gartner. Discovery-channel mix is the number that moves this page.
- **Referral-traffic data from answer engines** with a disclosed method, especially from parties without a product to sell in the category.
- **Attribution methodology work**, including anything on incrementality testing and geo holdouts that would let a real causal claim replace a modeling assumption.
- **Platform distribution changes**: reach mechanics, link penalties, and feed-ranking changes that alter what a channel can carry.
- **Launch postmortems with numbers attached.** Rare and worth more than any framework.
- **Advertising-law rulings on comparative claims**, which govern what a campaign may say about a competitor. Page 15 tracks these too.

## Sources

1. Hill, T. and Westbrook, R. "SWOT Analysis: It's Time for a Product Recall." Long Range Planning 30(1), 1997, pp. 46-52.
2. 2026 Buyer Behavior Report. G2. https://www.g2.com/
3. 2025 B2B Buyer Experience Report. 6sense. https://6sense.com/
4. 2026 B2B Buying Disconnect. TrustRadius. https://www.trustradius.com/
5. Google users are less likely to click on links when an AI summary appears in the results. Pew Research Center, 2025-07-22. https://www.pewresearch.org/short-reads/2025/07/22/google-users-are-less-likely-to-click-on-links-when-an-ai-summary-appears-in-the-results/
6. Aggarwal, P. et al. "GEO: Generative Engine Optimization." KDD 2024. https://arxiv.org/abs/2311.09735
7. Puerto, H. et al. "C-SEO Bench: Does Conversational SEO Work?" NeurIPS 2025 Datasets and Benchmarks Track. https://arxiv.org/abs/2506.11097
8. Kirsten, E. et al. "Characterizing Web Search in The Age of Generative AI." Findings of ACL 2026. https://aclanthology.org/2026.findings-acl.526/
9. Schulte, J., Bleeker, M. and Kaufmann, P. "Don't Measure Once: Measuring Visibility in AI Search (GEO)." 2026-04-08. https://arxiv.org/abs/2604.07585
10. Martinez, O. "Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023-2026)." 2026-07-15. https://arxiv.org/abs/2607.14035

**On the shape of this list.** The answer-engine section is now properly sourced and its evidence is largely negative, which is the useful part. The rest of the page is thin because the published literature on campaign execution is dominated by vendor content marketing with a commercial interest in its own conclusions, and the sourced passes on website conversion, SEO, email, and developer marketing are still owed. Sections marked [reasoning] have no study behind them and should be presented that way. Full sourcing for the answer-engine material, including the provider documentation on crawlers, robots.txt and llms.txt, is in [`research/llm-search-visibility.md`](../research/llm-search-visibility.md).

## Related

- Launches (page 06 of the larger wiki, not in this package)
- Content and demand generation (page 10 of the larger wiki, not in this package)
- Metrics and impact (page 11 of the larger wiki, not in this package)
- AI and the future of PMM (page 13 of the larger wiki, not in this package)
- [Competitive research execution](15-competitive-research-execution.md)
- [Naming](17-naming.md)
- [Developer marketing](18-developer-marketing.md)
- [The launch campaign protocol](../protocols/05-launch-campaign.md) is the binding process this page studies.
- A separate channel playbook holds the execution layer for social, paid, AEO, and the content pipeline.
