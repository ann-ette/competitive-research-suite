# Launch Campaign Protocol

Last reviewed: 2026-08-26 (the sourced naming and answer-engine passes; four passes are still owed, listed under Evidence status).

> Read this on "launch plan", "campaign", "how should we announce this", "what do we call it", "GTM plan for the release", or when something has shipped and nobody has written down what the launch is supposed to change.

This is the fifth sibling to the [research protocol](02-research.md), the [elicitation protocol](01-research-elicitation.md), the [options-review protocol](03-options-review.md), and the [competitive research protocol](04-competitive-research.md). Elicitation finds the gaps in a topic. Research sources them. Options review benchmarks a technical decision against the field. Competitive research governs claims about other organizations. This one governs the campaign: what the launch is for, what it gets called, which surfaces carry it, and how anyone would know afterward whether it worked.

The competitive protocol is an input here. A launch that has not run its step 2 is positioning against a set nobody verified, and every message in the campaign inherits that.

Vendor-agnostic by design. No client and no product is named in this file. The worked pass that prompted it is recorded in the Log at the bottom.

Study-side companions, written for fluency rather than for execution: [`study/16-campaigns-and-channels.md`](../study/16-campaigns-and-channels.md), [`17-naming.md`](../study/17-naming.md), [`18-developer-marketing.md`](../study/18-developer-marketing.md). This file is the binding process; those three teach and frame.

---

## Evidence status, read this before quoting anything below

This protocol mixes sourced findings with reasoning I have not yet sourced, and the difference is marked in place. Anything tagged **[reasoning]** is my argument from mechanism and has no study behind it. Anything tagged with a citation has a page in [`research/`](../research/) holding the sources.

| Section | Status |
|---|---|
| Step 1, launch tiers | [reasoning] |
| Step 2, the launch thesis | [reasoning], borrows the decision-sentence discipline from the competitive protocol |
| Step 3, the naming gate | **Split.** The legal half is sourced to primary law and settled. The behavioral half rests on consumer lab studies that do not transfer, and the first question in the step (does this need a name at all) has **no evidence base at all**. Marked in place. [`research/product-naming.md`](../research/product-naming.md) |
| Step 4, surface map | [reasoning] on decay ordering. Owed: website conversion research |
| Step 5, measurement | Partly sourced. Owed: email and SEO measurement baselines |
| Step 6, the LLM answer surface | Sourced, and the evidence is largely negative. [`research/llm-search-visibility.md`](../research/llm-search-visibility.md) |
| Step 7, developer marketing | Thin. Draws on a developer-marketing and audience-mapping research pass held outside this package |
| The legal gate | Sourced, inherited from the competitive protocol |

**Owed, and named so the debt is visible:** sourced passes on website conversion, SEO as a practice, email, and developer marketing as its own discipline. Each is currently reasoning. A research page is owed for any research pass, and these four have not had one.

---

## Why This Exists

Three failures show up every time a launch is planned without a process.

**The plan is a channel list.** It opens as a table of channels with a date beside each one, and every launch gets the same table regardless of what shipped. A bugfix draws a press push; a capability that changes who the product is for draws a changelog line. The tier was never decided, so effort distributed itself by habit.

**The name ships before anyone checks whether it can be owned or found.** A coined name enters the world with no search volume attached to it and a trademark position nobody screened. Renaming afterward costs the docs, the URLs, the inbound links, and whatever recognition accumulated in between, which is why the check belongs before the surfaces are built rather than after the first objection arrives.

**Measurement is assembled afterward from whatever the tools happen to report.** This is the same failure the competitive protocol names in its step 3, where comparison axes get chosen after looking and therefore get chosen to flatter. A launch measured by whatever the analytics dashboard publishes will be judged a success by whichever number moved.

## The Failure It Prevents

- **Reach counted as effect.** Impressions, followers, and post engagement are cheap to move and describe the platform's behavior more than the buyer's. A campaign that reports them has usually not been able to find anything else.
- **The surface that decays treated the same as the surface that accrues.** A social post is spent in days. A docs page, a comparison page, and a well-named concept keep working, and they are what an answer engine reads months later.
- **Positioning invented at campaign time.** Messaging written during a launch, under a date, against no verified competitive set, becomes the product's public claim by accident.
- **A launch with no stop condition.** Without a written kill criterion, an underperforming campaign gets extended rather than ended, because ending it requires someone to say it failed.

## When To Run It

- Any launch above tier 3 (see step 1).
- A new name for anything the buyer will type, search, or say out loud.
- A campaign that crosses more than one surface, since single-surface work rarely needs this much structure.
- A repositioning, where the campaign is the mechanism the new position travels on.
- Any client engagement that names launch or campaign planning as a deliverable.

## When Not To

- A changelog entry. Ship it and move on.
- A single social post with no downstream ask.
- A campaign already planned inside its review window with nothing changed on either side.
- As a substitute for talking to buyers. Every step below is a proxy for a conversation.

---

## The Protocol

### 1. Tier the launch before planning anything

Decide the tier from what changes for the buyer. Internal effort is the wrong input, and it is the input that gets used, because the team that built the thing knows exactly how hard it was and does not know how much it matters. **[reasoning]**

| Tier | What changed for the buyer | What it earns |
|---|---|---|
| 1 | A new reason to consider the product at all. A new buyer, a new category, or a new job the product now does. | Full campaign. Naming gate, positioning refresh, every surface, a measurement plan, a named owner. |
| 2 | A material capability an existing buyer will change behavior over, or evaluate a renewal on. | Owned surfaces plus one earned push. Naming gate if it needs a name. Measurement on the owned surfaces. |
| 3 | An improvement an existing user notices and nobody switches over. | Docs, changelog, one post. No naming gate, no campaign. |

Write the tier and the one-sentence reason at the top of the campaign page. The tier is the budget, and a tier chosen after the work is a rationalization.

**Tier inflation is the default failure.** Everything feels like a tier 1 from inside the build. The check: name the buyer who is not currently considering the product and say what this makes them do. If that sentence cannot be written, it is a tier 2.

### 2. Write the launch thesis in one sentence

Before any surface, any name, and any channel: **who changes their mind, from what to what, and on what proof.**

"A team lead who currently believes this only helps one person changes their mind when they see it report across the whole team, proved by the team view in the product tour."

If the sentence cannot be written, stop. The launch has no consumer and will produce a channel list. This is the same gate the competitive protocol puts at its step 1, for the same reason: everything downstream inherits it, and any asset that does not serve it is out of scope no matter how good it is.

Three parts, each of which fails in its own way:

- **Who.** A role, with the situation they are in. "Developers" is not a who.
- **From what to what.** Both ends stated. A thesis that names only the destination is describing a feature.
- **On what proof.** The artifact that does the convincing. If the proof is the messaging, there is no proof.

### 3. The naming gate

Runs before any surface is built. A rename after launch costs the docs, the URLs, the inbound links, and the recognition accumulated in between.

Three questions in order, and the first one is usually answered wrong.

**Does this need a name at all? [reasoning, and the evidence base is empty]** There is no empirical study on this question in a B2B or software context. None comparing named against unnamed capabilities on adoption, recall, pricing power, or sales-cycle length. The marketing literature studies brands at company or consumer-product level; the software-engineering literature studies naming as identifier readability. The case in the middle, a commercial feature name inside a product a committee buys, is unstudied.

So the default here is argument rather than finding, and it should be stated as one: a name is a claim that the thing is a distinct object worth holding in memory, it carries a maintenance cost forever, and the fallback is the descriptive phrase buyers already use.

**If it needs one, what kind?** The strength spectrum from *Abercrombie & Fitch v. Hunting World*, 537 F.2d 4 (2d Cir. 1976) runs generic, descriptive, suggestive, arbitrary, fanciful. Legal protectability increases along it while immediate comprehension decreases, and the choice is which cost to pay.

Three things from the opinion and the statute that the practitioner summaries drop:

- **The category decides.** SAFARI was held generic for safari hats and jackets and valid at the same time for boots, luggage, tents and tobacco. A name that is arbitrary for a database is descriptive for a search product, so clearance is per-class and a clean result in one class says nothing about another.
- **Genericness is a one-way door.** Secondary meaning can rescue a merely descriptive mark and cannot rescue a generic one.
- **The §2(f) escape hatch is weaker than it reads.** 15 U.S.C. §1052(f) lets the Director accept five years of "substantially exclusive and continuous use" as prima facie evidence of acquired distinctiveness. A feature name built from the category's own words is precisely the case where substantially exclusive use does not exist, because competitors are using the same words for the same reason. It is also five years after launch, so it is not a launch-day asset.

**Can it be owned, and can it be found?** Clearance in the classes that matter, domain and handle availability, collision with existing names, and a check on what buyers currently type. **The discoverability half of this is unmeasured**, and I would rather say so than cite the argument as a finding: no study compares named against descriptive capabilities on search performance. What exists is a developer complaining on the Docker rename PR that "everybody will have to filter a lot of search rubbish about musician, moby dick, moby explorer", a third party building an "AWS in Plain English" decoder for a catalog of "50 plus opaquely named services", and Google shipping a pronunciation guide inside the Kubernetes launch post. Three artifacts, all consistent with the argument, none of them a measurement.

**What the behavioral literature actually supports, and where it stops.** Pronounceability moves fast low-information judgments (Alter and Oppenheimer 2006, PNAS), and the effect decayed to non-significance past about a week, with η² of 0.01 in their ticker study. Sound symbolism moves attribute judgments (Yorkston and Menon 2004, JCR), and **the effect vanished when participants were told the name was a test name rather than a real one**. Every one of these studies used undergraduates judging fictitious consumer goods in one shot. A technical buyer reading a launch post about a newly coined name, knowing it is a marketing name, with full attention, is close to the exact cell where the effect disappeared. Treat naming psychology as unestablished in this setting, in either direction.

**The one finding that does bear on the decision.** Landgraf, Luffarelli and Stamatogiannakis (2026, *Journal of Business Research*) find coined names raise more on Kickstarter and that the advantage **attenuates when compelling information behind the name is absent**. A coined name is a container. That argues for coining one only for a capability with a real story attached, and against coining one for an increment, which is the same line step 1 draws between tiers.

**The practical resolution, marked as reasoning.** Ship the name and the descriptive phrase together every time, until the name carries alone. The observable stopping condition: it appears in search queries and in third-party writing without the descriptor attached.

**If a rename is on the table.** The two documented cases split on one variable. Microsoft's Azure AD to Entra ID rename (2023-07-11) explicitly froze login URLs, APIs, PowerShell cmdlets and libraries and moved only the marketing surface. Docker's Moby rename moved the namespace developers had already taken a dependency on, with one sentence of explanation, and the project's tracker still carries an open request to reverse it. **A rename survives when the technical namespace does not move.** Two cases, so this is a hypothesis with evidence rather than a finding.

Full sourcing is in [`research/product-naming.md`](../research/product-naming.md), including a rejected-sources list. Method and interview framing are in [`study/17-naming.md`](../study/17-naming.md). **This protocol stays vendor-agnostic and names nothing; a live naming question is its own pass.**

### 4. Map the surfaces before the channel plan

The usual owned / earned / paid split describes who controls the surface and hides the property that governs sequencing, which is how fast it decays. **[reasoning]**

| Surface | Decays in | What it is good for |
|---|---|---|
| Social post | Days | Reach into an existing audience. Spent on publication. |
| Paid | The length of the spend | Volume against a hypothesis already validated somewhere cheaper |
| Email to a list I own | One send, plus a small tail | The highest-intent audience available, and the one most easily burned |
| Press and earned coverage | Weeks, then a permanent citable artifact | Third-party credibility, which is the one thing owned surfaces cannot manufacture |
| Website and landing page | Months to years | The only surface I control end to end, and the destination every other surface points at |
| Docs and reference | Years | The developer buyer's actual evaluation surface. See step 7. |
| A named concept in third-party writing | Indefinite | Compounds, and is what answer engines read later |

**Order the work by decay rate, slowest first.** The surfaces that accrue have to exist before the surfaces that decay point at them, and the common failure is a launch-day post pointing at a page written the night before.

**Every launch needs one destination that survives the campaign.** If the campaign ends and nothing durable was created, the spend bought attention and stored none of it.

Owed: a sourced pass on website conversion. Everything in this step about the landing page is currently reasoning.

### 5. Declare the measurement before the campaign

Name the metric, the baseline, the window, and the result that would make me stop. All four before launch. A metric chosen afterward is chosen to flatter, and the analytics dashboard will always offer one that moved.

Per surface, one metric that reflects the buyer rather than the platform:

- **Reach metrics are diagnostics.** Impressions and engagement tell me whether distribution worked, which is worth knowing and sits one full step short of the launch's purpose. They belong in their own labeled row.
- **The outcome metric has to connect to the thesis in step 2.** If the thesis says a platform engineer changes their mind, the metric is something only a convinced platform engineer does.
- **Baseline first.** A number with no before is a number.
- **Write the kill criterion.** "If the landing page holds under X% conversion after N qualified sessions, the page is wrong and I rewrite it rather than buy more traffic." Without this, underperformance extends the campaign.

**Attribution is worse than the tools imply, and the honest version says so.** Any launch that runs on more than one surface at once cannot cleanly assign credit, and a dashboard that assigns it anyway is applying a model somebody chose. State the model in use and its known bias rather than reporting its output as measurement.

Owed: sourced baselines for email and for SEO as a practice. Both are currently reasoning.

### 6. The LLM answer surface is a citation problem

When a buyer asks a model about the problem instead of searching for it, the question is whether the product is in the answer, and the mechanism is citation.

This step is sourced, and the evidence is more negative than the category's own literature implies. Sourcing in [`research/llm-search-visibility.md`](../research/llm-search-visibility.md).

**Size the prize first.** Pew Research Center (2025-07-22) tracked 900 U.S. adults with a browsing tracker across 68,879 Google searches in March 2025, of which 12,593 produced an AI summary. Users clicked a traditional result in 8% of visits with a summary present against 15% without, and **clicked a link inside the summary in 1% of visits**. Google disputes the methodology and has published no counter-figures. Treat this as a consideration and brand surface. Resourcing it as an acquisition channel is the error to avoid, and the realistic mechanism by which it matters is a buyer reading an answer that names you and then searching your name, which no instrument below can see.

**The published tactics mostly do not work.** Aggarwal et al. (KDD 2024) is the paper everyone cites, and its main experiment is gpt-3.5-turbo at temperature 0.7 over the top five Google results, with visibility defined as position-weighted word share of the generated answer plus a GPT-3.5 judge's opinion. No human behavior is measured anywhere in it. The direct replication, Puerto et al. (C-SEO Bench, NeurIPS 2025 Datasets and Benchmarks), tested nine methods across two tasks, six domains and 1,921 queries at varying adoption rates and found most of them ineffective and frequently negative on ranking, with ordinary work to improve rank into the context more effective, and gains decreasing as adopters increase. Martinez (2026) surveys 45 studies and finds no technique with a stable cross-platform causal effect on discoverability.

Two specifics worth carrying into any plan:

- **Keyword stuffing scored below doing nothing** in the original paper, 17.7 against a 19.3 baseline.
- **The gains concentrate in already-low-ranked sources and the top-ranked source lost visibility on average.** Cite Sources moved a rank-5 source +115.1% and a rank-1 source −30.3%. If you are already the answer, these interventions can cost you.

**Measurement is harder than any dashboard admits.** Kirsten et al. (Findings of ACL 2026), 4,706 queries across the US and Germany at temperature 0, found that repeating the same query within five minutes changes the overall decision for 9% to 27% of queries depending on the system. Over two months, link-set overlap was 45% for Google organic and 18% for AI Overviews. Schulte et al. (2026) put the cost of measuring this properly at **7 to 8 repetitions per prompt** for a per-brand detection rate with standard error under 0.10, and rolling aggregation over **two to four weeks**; in their data 57.8% of ChatGPT runs returned zero citations because web search never activated.

So: a single-run check is noise, a before-and-after on one prompt is uninterpretable, and any attribution of a change to something you did requires a held-out control set of prompts measured on the same days. A vendor reporting share of voice to one decimal place from a daily single run is reporting a number narrower than its own error bar.

**Know which controls are real.** Most of the advice in circulation is wrong on the specifics:

- **robots.txt does not govern answer-time fetches.** OpenAI, Perplexity and Google each document, in their own words, that their user-triggered fetcher generally ignores it. Anthropic is the documented exception and honors it including for `Claude-User`. A robots.txt block is a decision about the training corpus and the search index.
- **Google-Extended does not cover AI Overviews or AI Mode.** Its documented scope is Gemini training and grounding, and it has no user-agent string at all. The lever that does cover AI Overviews is a separate Search Console setting.
- **No provider reads llms.txt.** No major provider has committed to it, and log analysis found zero requests from AI bots for llms.txt files that do not exist, meaning no crawler even probes for it. A vendor claiming it improves visibility is making an unsubstantiated claim.
- **Structured data officially does nothing here.** Google states in two separate official pages that no schema.org markup is needed for generative search. It remains worth doing for classic rich results, which is a different justification and should be stated as one.

**The document is the lever, with a caveat.** Answer engines cite documents, so the work is making the document that answers the question exist, be readable, and be fetchable. What survives the evidence is the ordinary part: rank into the retrieved set. The tactics layered on top of that are the part that failed replication.

**Treat every vendor in this category as E5** under the competitive protocol's tier table: primary about what they claim, and worthless about what works.

### 7. When the buyer is a developer, the weight moves

The campaign structure above holds. What changes is where the effort lands inside it.

- **Docs are the evaluation surface.** A developer evaluating a tool reads the reference and tries it. Marketing pages get skimmed on the way to the docs, and a docs page that cannot answer the evaluation question is the actual conversion failure.
- **The proof in the step 2 thesis has to be runnable.** A claim a developer can check in ten minutes beats a claim they have to take.
- **Promotion draws down credibility.** Developer audiences have a low tolerance for the campaign being visible as a campaign, which constrains the earned and paid rows in step 4 more than it constrains the owned ones.

This step is the thinnest in the file. A developer-marketing and audience-mapping research pass held outside this package is the best sourced material available here until the owed pass runs; [`study/18-developer-marketing.md`](../study/18-developer-marketing.md) carries its findings.

### 8. Set the review date and the owner, then stop

A campaign with no review date runs until someone notices. Both go on the campaign page before the plan closes.

**Write the retirement rule for every asset.** A landing page for a launch that ended is a page that now misrepresents the product.

---

## The Campaign Record

One file per campaign, with the project it serves rather than in the knowledge base.

| Field | Rule |
|---|---|
| Tier and why | From step 1. One sentence. |
| Launch thesis | From step 2. Who, from what to what, on what proof. |
| Competitive set | A link to the set page. If none exists, that is a blocker rather than a note. |
| Name decision | Named or not named, the kind chosen, and the clearance checks that ran with their dates. |
| Surface map | Every surface, its owner, its date, and its decay class. |
| Measurement plan | Metric, baseline, window, kill criterion. Written before launch. |
| What I decided not to do | The channels and assets considered and cut, with reasons. |
| Review date and owner | A date and a person. |
| Post-launch amendment | Dated, appended, never a rewrite of the plan. |

**The last row is the one that makes the record worth keeping.** A plan silently edited to match what happened teaches nothing.

---

## Where It Gets Filed

**A campaign plan is a deliverable and stays with its project.** The knowledge base holds durable findings, and a launch plan is a decision about one product at one time.

What does go to the knowledge base: any research the campaign generated. Audience findings, channel benchmarks, a measured result worth carrying forward, the naming clearance evidence. Running a web search means a page is owed, and the campaign deliverable does not discharge it.

Split by the competitive protocol's test: a claim about one organization goes to `Companies/`, a claim about the relationship between organizations goes to `Industries/`. `## Bibliography` is the heading inside the base.

### The Boundary with Channel Execution

Execution for social, paid, answer-engine work, and the content pipeline belongs to whoever runs the channels, and a campaign that stops at the edge of a channel is not a campaign. The resolution: **this file owns the decision, the channel playbook owns the execution.** Whether social carries the launch, and what it has to accomplish, is a step 4 question and lives here. What gets posted, when, in what format, on which account, lives there.

---

## Guards

- **Never let a channel list stand in for a plan.** If the document opens with channels, steps 1 and 2 did not happen.
- **Never ship a name that has not cleared step 3.** The check is cheap before launch and expensive after.
- **Never report a reach metric as an outcome.** State it as a diagnostic, in its own row, labeled.
- **Never write positioning during a launch.** Positioning that first appears under a deadline has not been tested against anything.
- **Never claim an attribution number without naming the model that produced it.**
- **A campaign that cannot name what it decided not to do has not made a decision.**
- **Do not let the tier drift upward after the work starts.** Re-tiering is legitimate and gets written down with its date and reason.

## The Legal Gate

Run before anything ships externally. The competitive protocol carries the full version and it governs here without modification.

The parts that bite hardest in campaign work:

- **Every comparative claim needs substantiation in hand before publication.** 16 CFR §14.15 states the FTC's policy favoring comparative advertising that names competitors and applies the same substantiation standard to those claims as to any other.
- **A false or misleading statement of fact about a competitor's product in commercial advertising is actionable under Lanham Act §43(a).** Elements in *Pizza Hut v. Papa John's* (5th Cir. 2000).
- **Using a competitor's trademark to refer to the competitor is nominative fair use**, under the test in *New Kids on the Block v. News America Publishing* (9th Cir. 1992).
- **Naming is a trademark question before it is a creative one.** Clearance in the relevant classes runs before commitment, and the strength spectrum in step 3 is what determines whether there is anything to clear.
- **When a claim cannot be substantiated, it does not ship softened. It comes out.**

---

## Log

- 2026-08-26: Protocol created as the fifth methodology sibling. Vendor-agnostic; no client or product named. Written alongside study pages 16, 17, and 18 and two sourced research passes ([product naming](../research/product-naming.md) and [LLM search visibility](../research/llm-search-visibility.md)). Four areas are marked as reasoning with the sourced pass owed: website conversion, SEO as a practice, email, and developer marketing.
