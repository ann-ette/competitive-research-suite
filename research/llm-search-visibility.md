# Whether a product shows up in LLM answers, and whether that can be influenced or measured

Topic page. What holds up on generative engine optimization (GEO) and answer
engine optimization (AEO) once the vendor content marketing is stripped out: what
the one real academic study actually tested and on what, what is measurable from
your own analytics and server logs, what is not measurable because the systems are
non-deterministic, and which controls a site genuinely has versus which are
asserted by tool vendors.

Opened 2026-08-26. Prompted by [the launch campaign protocol](../protocols/05-launch-campaign.md) answer-engine step.

Tags: `llm-search-visibility` · `geo-aeo` · `measurement-method` · `research-method`

---

## TL;DR

The published tactics do not work and the measurement is harder than anyone
selling it admits. The one well-known GEO paper ran a gpt-3.5-turbo prompt over
five Google results, and its gains concentrate in already-low-ranked sources while
the top-ranked source on average lost visibility. The direct replication at
NeurIPS 2025 found most of those tactics ineffective or negative, found ordinary
ranking work more effective, and found the whole thing congests toward zero-sum as
adoption rises. Meanwhile the same query at temperature 0 flips its answer for 9%
to 27% of queries inside five minutes, so a single-run visibility check is noise
and a defensible number needs 7 to 8 repetitions and a two-to-four-week window.

The controls are also not the ones in circulation. robots.txt does not govern
answer-time fetches for OpenAI, Perplexity or Google, and Anthropic is the lone
documented exception. Google-Extended does not cover AI Overviews. No provider
reads llms.txt and no AI crawler even probes for it. Structured data officially
does nothing here.

And the prize is small: Pew measured clicks on a link inside an AI summary at 1%
of visits. This is a consideration surface, and resourcing it as an acquisition
channel is the error to avoid.

## Confidence map

**High confidence** (primary document read in full, or two independent sources)

- What the GEO paper tested and what it did not. Read the v3 PDF in full,
  including the appendix that reveals the Perplexity run used file uploads rather
  than retrieval.
- The rank interaction (gains at rank 5, losses at rank 1). Table 2 of the paper.
- Non-determinism magnitudes. Kirsten et al. (Findings of ACL 2026) and Schulte et
  al. (2026) are independent samples reaching compatible conclusions, and He
  (2025) supplies the mechanism.
- Provider crawler taxonomy and the robots.txt carve-out for user-triggered
  fetches. Read in each provider's own documentation, and the wording is close to
  verbatim across three of them.
- Google-Extended's documented scope, and the separate Search Console control that
  actually covers AI Overviews.
- The Pew click-through figures. Primary page read directly, method and n stated.

**Medium confidence** (one strong source, or a strong source read only in part)

- C-SEO Bench's specific counts. The abstract's qualitative claim is first-hand;
  the 3-of-54 figure is read through Martinez (2026).
- E-GEO. Abstract only, and the paper's own framing and the survey's reading of it
  disagree in tone. Both recorded.
- Search Console generative AI reports. Title and 2026-06-03 date confirmed from
  Google's blog feed; the article body would not load, so the widely reported
  specifics are trade-press only and are flagged as unverified in §4.2.

**Contested or unresolved**

- Whether any GEO intervention has a durable causal effect on discoverability.
  Martinez (2026) surveys 45 studies and says no. That is a single-author preprint,
  so it carries survey weight rather than experimental weight.
- The Pew result itself, which Google publicly disputes on methodology while
  publishing no counter-figures.
- Whether Reddit is a lever. True on Google surfaces, close to false on the OpenAI
  surfaces in Kirsten et al. The common vendor claim does not survive being split
  by engine.

**Explicitly unusable, recorded so the next pass does not re-find it**

- Two widely circulated quotes on llms.txt: a John Mueller Reddit comment about
  server logs, and a Gary Illyes statement at Search Central Live APAC. Both appear
  only in SEO-vendor retellings. The documented Google position in §7.4 is the
  citable substitute.
- Vendor AI-referral-volume studies generally. See the note at the end of §5.

---

## 1. The GEO paper: what Aggarwal et al. actually tested

**Citation.** Pranjal Aggarwal (IIT Delhi), Vishvak Murahari, Tanmay Rajpurohit,
Ashwin Kalyan, Karthik Narasimhan, Ameet Deshpande. "GEO: Generative Engine
Optimization." KDD '24, Barcelona, 2024-08-25 to 2024-08-29. DOI
10.1145/3637528.3671900. arXiv:2311.09735, v1 2023-11-16, v3 2024-06-28. I read
the v3 PDF directly, all twelve pages including appendices.

### The setup is a simulation, not a commercial engine

This is the single most important fact about the paper and the one most often
dropped in summaries. The main experiment is not run against ChatGPT, Google AI
Overviews, or Bing. It is a two-step reconstruction of a generative engine
(Aggarwal et al. 2024, §3.1):

1. Fetch the **top 5 sources from the Google search engine** for the query.
2. Generate the answer with **gpt-3.5-turbo**, temperature **0.7**, using a fixed
   prompt (reproduced in the paper as Listing 1) that instructs inline citation.

They sample 5 responses per query and run the whole experiment on **5 random
seeds**, reporting the average. So the "generative engine" under test is a
gpt-3.5-turbo prompt over five Google results, chosen because it mimics what
BingChat and Perplexity were doing at the time.

### GEO-bench

10,000 queries, split 8K train / 1K validation / 1K test, drawn from nine sources
(Aggarwal et al. 2024, §3.2): MS MARCO, ORCAS-1, Natural Questions, AllSouls
(Oxford essay questions), LIMA, Davinci-Debate, Perplexity.ai Discover, the ELI5
subreddit, and GPT-4-generated queries. 25 domains. The distribution is held at
roughly **80% informational, 10% transactional, 10% navigational**. Every query is
augmented with the cleaned text of the top 5 Google results. Tagging into seven
categories was done by prompting GPT-4, and the paper itself says those tags "can
be noisy and should not be considered carefully" (Appendix B.2).

### The two visibility metrics they invented

Neither metric is a traffic metric, a ranking metric, or a business metric. Both
are properties of the generated answer text.

- **Position-Adjusted Word Count** (Imp_pwc, equation 3). The share of answer
  words attributable to a citation, weighted by an exponentially decaying function
  of where the sentence falls in the response: each sentence contributes
  `|s| · e^(−pos(s)/|s|)`. Words split equally when a sentence cites multiple
  sources. Justified by reference to power-law click-through by rank in
  traditional search, not by any measurement of reading behavior in a generated
  answer.
- **Subjective Impression.** Seven sub-scores (relevance, influence, uniqueness,
  subjective position, subjective count, likelihood of the user clicking,
  diversity of material) produced by **G-Eval with GPT-3.5 as judge**, then
  normalized to share the mean and variance of Position-Adjusted Word Count.

So "visibility" in this paper means: how many words of a model-written answer are
attributable to your page, position-weighted, plus a GPT-3.5 judge's opinion of
how prominent your page felt. "Likelihood of the user clicking" is an LLM's guess,
not a click.

### What moved, and by how much

Table 1, absolute impression on the GEO-bench test split. Baseline (no
optimization) is **19.3** on both overall Position-Adjusted Word Count and the
Subjective Impression average.

| Method | PAWC overall | Subjective Impression avg |
|---|---|---|
| No optimization (baseline) | 19.3 | 19.3 |
| **Keyword Stuffing** | **17.7** | 20.2 |
| Unique Words | 20.5 | 20.4 |
| Easy-to-Understand | 22.0 | 20.5 |
| Authoritative | 21.3 | 22.9 |
| Technical Terms | 22.7 | 21.4 |
| Fluency Optimization | 24.7 | 21.9 |
| Cite Sources | 24.6 | 21.9 |
| Statistics Addition | 25.2 | 23.7 |
| **Quotation Addition** | **27.2** | **24.7** |

The headline "up to 40%" is Quotation Addition against baseline on
Position-Adjusted Word Count: 27.2 / 19.3, which the paper states as **41% on
Position-Adjusted Word Count and 28% on Subjective Impression** for the best
methods.

What failed: **Keyword Stuffing scored below the do-nothing baseline** (17.7 vs
19.3). That is the paper's most transferable finding and it is a negative one.
Authoritative tone produced "no significant improvement" on the objective metric,
which the authors read as the engine being robust to persuasive framing.

### The rank interaction, which is the finding nobody quotes

Table 2 breaks relative visibility change out by the source's existing rank in the
Google SERP. Cite Sources moved a rank-5 site **+115.1%** and moved a rank-1 site
**−30.3%**. Quotation Addition at rank 5: **+99.7%**. Statistics Addition at rank
5: **+97.9%**. The gains concentrate almost entirely in already-low-ranked
sources, and the top-ranked source on average lost visibility. If you are already
the answer, these interventions can cost you.

### The one real-engine experiment, and its caveat

Appendix C.1 and Table 7: they re-ran on **Perplexity.ai**, on a **200-sample
subset** of the test split. Baseline 24.1 PAWC / 24.7 SI. Quotation Addition 29.1
PAWC (+22%). Statistics Addition 33.9 SI (+37%). Keyword Stuffing 21.9 PAWC,
about 10% worse than baseline.

The caveat is stated in the paper and it is large: **Perplexity does not let you
specify source URLs, so they uploaded the source text as file uploads.** That
tests whether the model prefers your text once your text is already in the
context. It does not test retrieval, indexing, crawling, or whether Perplexity
would have found you at all.

### What the paper explicitly does not establish

From §9, Limitations, plus what follows from the setup:

- **It does not measure traffic, clicks, conversions, or revenue.** No outcome
  variable in the paper is a human behavior.
- **It does not evaluate effects on search rankings.** The authors say so
  directly, and note only that the edits are textual rather than to backlinks or
  domain metadata, so they are "less likely to affect search engine rankings."
- **It does not test durability.** The authors say methods "may need to adapt over
  time as GEs evolve."
- **It does not test any 2026 production system.** gpt-3.5-turbo over five Google
  results, plus a Perplexity file-upload run on 200 examples.
- **It does not test what happens when everyone does it.** §5.2 gestures at
  simultaneous optimization but the measurement is still one source per query.

## 2. Follow-up, replication, and critique

The follow-up literature is small, recent, and mostly negative. That is the
headline of this section.

### C-SEO Bench: most of the tactics do not work, and they congest

Puerto, Gubri, Green, Oh and Yun, "C-SEO Bench: Does Conversational SEO Work?",
NeurIPS 2025 Datasets and Benchmarks Track, arXiv:2506.11097 (v1 2025-06-06, v3
2025-10-20).

This is the direct replication attempt and it is the most important source on this
page after the original. It tests **9 C-SEO methods** (7 from prior work including
the GEO methods, plus 2 new ones) across **two tasks** (question answering and
product recommendation) and **six domains** (web, news, debate; retail, video
games, books), **1,921 queries**, and, critically, at **varying adoption rates**
rather than the single-actor setup the original used.

The abstract states the finding plainly: "most current C-SEO methods are not only
largely ineffective but also frequently have a negative impact on document
ranking, which is opposite to what is expected. Instead, traditional SEO
strategies, those aiming to improve the ranking of the source in the LLM context,
are significantly more effective." And: "as we increase the number of C-SEO
adopters, the overall gains decrease, depicting a congested and zero-sum nature of
the problem."

Martinez (2026), surveying the field, reports the count from this benchmark as
**only 3 of 54 method-by-domain combinations significantly positive, and none
positive in question answering**. I read that count in the survey rather than in
the benchmark paper itself, so treat the 3-of-54 figure as second-hand and the
abstract's qualitative statement as first-hand.

The zero-sum result is the structurally important one. Impression share in a
generated answer sums to one. If every source in a category applies the same
technique, the technique redistributes nothing.

### E-GEO: heuristics fail, optimized prompts do better, and the two readings differ

Bagga, Farias, Korkotashvili, Peng and Wu, "E-GEO: A Testbed for Generative Engine
Optimization in E-Commerce", arXiv:2511.20867, submitted 2025-11-25, revised
2026-07-14. **13,747 multi-sentence consumer product queries**, each paired with
10 retrieved Amazon listings, 5 generative engines, 7 LLM rewriters, and
**15 hand-crafted rewriting heuristics.**

The two available readings do not agree in tone and I am recording both.

- The paper's own abstract is optimistic: optimized prompts substantially
  outperform heuristic baselines, and it claims "a stable, domain-agnostic
  pattern, suggesting the existence of a 'universally effective' GEO strategy,"
  validated against adversarial testing.
- Martinez (2026), reading the same paper, extracts that **10 of the 15 initial
  heuristics were neutral or negative** and treats the positive result as
  belonging to machine-optimized prompts rather than to any human-legible tactic.

Both are true and they point the same way for a practitioner: the published
tactic lists do not work; what worked was a search procedure over rewrites,
inside a fixed retrieved set of 10 listings. That last clause is the same
conditionality as the original GEO paper. It is not a discoverability result.

### The critical survey

Martinez, O. "Optimizing Visibility in Generative Engines: A Critical Survey of
Generative Engine Optimization (2023-2026)", arXiv:2607.14035, 2026-07-15.
Reviews **45 studies** from 2023-11-16 to 2026-07-14. Its conclusion is that no
reviewed technique has a "stable, longitudinal, cross-platform causal effect on
organic discoverability or downstream behavior," while conceding that content
already retrieved into the context can change its own citation pattern.

That is the honest summary of the whole literature, and it is a single-author
preprint, so it carries survey weight rather than experimental weight. I read the
survey's HTML directly and verified its citations to Puerto, Kirsten, Grossman,
Schulte, Liu and Nestaas against the underlying papers.

### The adversarial line

Nestaas, Debenedetti and Tramèr, "Adversarial Search Engine Optimization for Large
Language Models", ICLR 2025. Establishes preference-manipulation attacks: text
inserted into a retrieved document can push an LLM toward recommending it. Read
via abstract and the survey, not in full. It matters here mostly as the boundary
case: the reliable ways to move an LLM's answer are the adversarial ones, and
those are exactly the ones a real company cannot ship.

## 3. Non-determinism as a measurement problem

This governs whether anything above can be measured at all, so it goes before the
measurement section.

### The systems are non-deterministic at the model layer, even at temperature 0

He, H., "Defeating Nondeterminism in LLM Inference", Thinking Machines Lab, 2025.
Running **1,000 completions of the same prompt at temperature 0** against
Qwen3-235B-A22B-Instruct-2507 produced **80 unique completions**. They were
identical for 102 tokens and diverged at token 103: 992 continued one way, 8 the
other.

The cause he identifies is not the usual "floating point plus concurrency"
folklore. It is that inference kernels are **not batch-invariant**: the numerical
result of the same computation depends on the batch size it was executed in, and
**batch size on a production endpoint depends on other people's traffic**. So the
answer you get depends in part on server load at the moment you asked. That is a
property of hosted inference, not a knob you can turn off from outside.

Yuan et al., "Understanding and Mitigating Numerical Sources of Nondeterminism in
LLM Inference", arXiv:2506.09501 (v1 2025-06-11, v2 2025-10-24), measures the same
effect academically: under greedy decoding at bfloat16,
DeepSeek-R1-Distill-Qwen-7B showed **up to 9% variation in accuracy and a
9,000-token difference in response length** purely from changing GPU count, GPU
type and batch size. Same model, same prompt, same temperature. Abstract read
directly; full text not read.

### The systems are also non-deterministic at the retrieval layer, which is worse

Kirsten, Große Perdekamp, Wu, Upadhyay, Gummadi and Zafar, "Characterizing Web
Search in The Age of Generative AI", Findings of ACL 2026, pp. 10827-10848, DOI
10.18653/v1/2026.findings-acl.526, preprint arXiv:2510.11560 (v1 2025-10-13, v2
2026-05-31).

Method: **4,706 queries** across six datasets (MS MARCO, WildChat, AllSides,
regulatory actions, science queries, Amazon product terms), run in the **United
States and Germany**, English only, collected in **July/August and September 2025**
so a two-month re-run is possible. Compared Google organic against five generative
systems from three providers: Google AI Overviews, Gemini 2.5 Flash, GPT-4o
Search, GPT-4o with search tool, and Perplexity Sonar. **Temperature set to 0.**

Three findings that between them decide the measurement question:

1. **Repeating the same query within five minutes, at temperature 0, changes the
   overall decision for 9% to 27% of queries.** Per system: GPT-Tool 9%,
   Gemini 15%, GPT-Search 16%, AI Overviews 17%, Perplexity Sonar 27%.
2. **Across a two-month gap, link-set Jaccard overlap is 45% for Google organic,
   40% for Gemini, and 18% for AI Overviews.** So roughly four fifths of the
   AI Overview's cited links turned over in two months.
3. **More than 40% of AI Overview links are not in the organic top 10**, and
   overlap stays below 60% even against the top 100. Ranking in classic search
   does not deliver you into the AI answer, and being in the AI answer does not
   mean you ranked.

### How many runs it takes before a number means anything

Schulte, Bleeker and Kaufmann, "Don't Measure Once: Measuring Visibility in AI
Search (GEO)", arXiv:2604.07585, 2026-04-08. 19 pages, 7 figures, 17 tables.

Method: **32 prompts** (8 per campaign, 4 campaigns), 32 to 51 brands per
vertical, four engines (ChatGPT, Gemini, Google AI Mode, Perplexity), observed
**2026-01-24 to 2026-03-20**, plus a simultaneous-run collection of up to
**10 repetitions per prompt** over 2026-03-21 to 2026-03-25.

- Day-to-day **source-set overlap averaged 0.336 to 0.423 Jaccard**, by vertical.
- To get standard error on a per-brand detection rate below 0.10 takes **n = 7
  runs (95% CI ±0.158)**; below 0.08 takes **n = 8 runs (95% CI ±0.121)**. Source
  coverage needs at least 8.
- Over time, SE falls below 0.10 at **10 days** and below 0.05 at **24 days**, so
  they recommend rolling aggregation over **two to four weeks**.
- **57.8% of ChatGPT runs returned zero citations**, because web search did not
  activate. In more than half of runs there was no retrieval event to measure.

The practical consequence: a single-run "does the model mention us" check is
noise. Even at 8 repetitions the confidence interval on a detection rate is
roughly ±12 points. Any vendor dashboard reporting a share-of-voice figure to one
decimal place from a daily single run is reporting a number narrower than its own
error bar.

### What this rules out

- Any before-and-after comparison on a single prompt. The run-to-run variance
  swamps a realistic intervention effect.
- Attributing a change in visibility to something you did, absent a control set of
  prompts measured on the same days. Model updates, index refreshes and traffic
  load all move the number for free.
- Treating a competitor's visibility score as a stable fact. Same problem.

## 4. What is actually measurable in practice

Four instruments exist. Each measures a different thing and none of them measures
"are we the answer."

### 4.1 Referral traffic in analytics

**Google Analytics 4 now has a first-party AI channel.** Per Google's own
"Default channel group" documentation, there is an **AI Assistant** channel whose
rule is: "The medium exactly matches 'ai-assistant'. The medium is set to
'ai-assistant' and the campaign is set to '(ai-assistant)' if the referrer matches
a list of AI Assistants." No configuration needed.

The same official page carries the caveat that matters most: the channel
**"excludes Google's AI Overviews and AI Mode."** Clicks out of an AI Overview
arrive as ordinary Google organic. So the one surface with by far the most query
volume is the one this channel cannot isolate.

**What referral data can tell you:** how many sessions arrived from a click in a
chat interface where the referrer header survived, and what they did next. This
is a real, clean, first-party conversion-linked number and it is the only one on
this page that touches revenue.

**What it cannot tell you:**
- Anything about answers where nobody clicked, which is most of them.
- Traffic from AI mobile apps and in-app webviews, which frequently arrive with no
  referrer and land in Direct.
- AI Overviews and AI Mode, excluded by definition above.
- Whether you were mentioned without being linked. Mention without citation is
  invisible to every analytics instrument.

The structural point: referral traffic measures the **click-through tail** of LLM
visibility, and the whole premise of an answer engine is to remove the click. A
low number is consistent with both "we are invisible" and "we are the answer and
nobody needed to leave."

### 4.2 Google Search Console generative AI reports

Google announced "Search Generative AI performance reports in Search Console" on
**2026-06-03** on the Search Central blog: "dedicated reports for Search and
Discover, to help you understand your site's visibility within generative AI
features on Search." I confirmed the title and the 2026-06-03 date from Google's
own blog feed. **I could not open the article body** through my fetch tooling, so
the widely reported specifics (impressions only with no clicks, data starting
2026-05-18 with no backfill, an initial UK-only rollout tied to a UK Competition
and Markets Authority requirement) come from SEO trade press and I am not treating
them as established. Verify against the official post before relying on any of
them.

If those specifics hold, this is nonetheless the single most valuable instrument
that exists, because it is first-party, census-level rather than sampled, and not
subject to prompt-panel selection bias. It is also Google-only.

### 4.3 Server-log separation of crawler types

See §7 for the provider-documented user agents. The method is sound in principle:
your own logs are ground truth about who fetched what and when, and the providers
document distinct agents for training-corpus collection, search-index building,
and answer-time retrieval on behalf of a live user prompt. Filtering the
answer-time agents gives you a proxy for "a user asked something and the system
went and read this page."

**What it can tell you:** which pages get fetched at answer time, at what rate,
and whether that rate changed after you shipped something.

**What it cannot tell you:** whether the fetch produced a citation, whether the
answer was favorable, or who asked. A fetch is not an impression. User agents are
also trivially spoofable, so a log line is evidence of a claim about identity, not
proof of it; reverse-DNS or published IP ranges are the only real verification and
not every provider publishes them.

### 4.4 Prompt panels and share of voice

This is what every GEO tool sells: a fixed list of prompts, run on a schedule
against several engines, counting how often your brand appears and which sources
get cited.

Schulte et al. (2026) is the only source I found that establishes what this method
costs to do correctly, and the answer is: **more than any vendor dashboard is
doing.** At least 7 to 8 repetitions per prompt for a per-brand detection rate
with standard error under 0.10, at least 8 for source coverage, and rolling
aggregation over 2 to 4 weeks. Their day-to-day source-set Jaccard of 0.34 to 0.42
is the reason.

**What a prompt panel can tell you, done properly:** a distribution, with error
bars, of how often a fixed prompt set surfaces you on a fixed engine set from a
fixed locale over a fixed window. Directional change over weeks, if the panel and
the method are frozen.

**What it cannot tell you:**
- What real buyers actually type. There is no prompt-volume dataset equivalent to
  keyword volume. The prompt list is an assumption, and it is the largest single
  source of error in the whole method.
- Anything personalized. Memory, account history, location and A/B assignment all
  move the answer, and a panel runs from clean sessions.
- Anything causal. Without a held-out control set of prompts measured on the same
  days, a change is not attributable to your intervention.

### 4.5 Citation tracking

Counting which domains get cited in answers to your prompt set. Same measurement
regime as 4.4, same error bars, plus one extra failure mode documented in the
literature: citations are frequently wrong. Liu, Zhang and Liang, "Evaluating
Verifiability in Generative Search Engines", Findings of EMNLP 2023, audited four
generative search engines (Bing Chat, NeevaAI, Perplexity.ai, YouChat) and found
**only 51.5% of generated sentences fully supported by their citations, and only
74.5% of citations supporting the sentence they were attached to.** Being cited
does not mean your content was used, and your content being used does not mean you
were cited.

## 5. Volume and click-through: how much traffic these surfaces really send

### The Pew measurement, which is the best non-commercial number available

Pew Research Center, "Google users are less likely to click on links when an AI
summary appears in the results", 2025-07-22. Read the primary page directly.

Method: **900 U.S. adults** from KnowledgePanel Digital, an online panel whose
members consent to install a browsing-tracking app. Browsing data collected
**2025-03-01 to 2025-03-31**; the corresponding search results were collected
2025-04-07 to 2025-04-17. The dataset holds **68,879 unique Google searches**, of
which **12,593 produced an AI summary**.

The figures, verbatim:

- **18%** of all Google searches in the study generated an AI summary.
- Users who encountered an AI summary clicked a traditional search result in **8%
  of visits**. Those who did not encounter one clicked **15% of the time**, which
  Pew describes as "nearly twice as often."
- Clicking a link **inside** the AI summary happened in **1% of all visits**.
- Sessions ended on **26%** of pages carrying an AI summary, against **16%** of
  pages with only traditional results.

Stated caveat, in Pew's own words: "Due to technical limitations in our ability to
identify AI-generated summaries on other search engines, this analysis includes
only Google searches."

**Google disputed the study publicly**, characterizing it as using "a flawed
methodology and skewed queryset that is not representative of Search traffic." I
am recording the dispute because it is real and because Google has the census data
nobody else does. Google did not publish counter-figures, so the dispute is an
assertion against a measurement with a stated method and n.

### What the 1% figure actually means for a launch

This is the number that should govern expectations, and it is worth stating
plainly: **being cited in an AI summary is worth close to no traffic.** One percent
of visits produced a click on a cited source. A launch strategy whose success
condition is referral traffic from answer surfaces is optimizing for the thinnest
tail available.

That does not make the surface worthless. It makes it a **brand and consideration
surface rather than an acquisition channel**, and it should be resourced and
measured as one. The buyer who reads an answer naming you and then searches your
name directly is invisible to every instrument in §4, and is the realistic
mechanism by which this matters.

### What I deliberately did not source here

Vendor studies of AI referral volume (Similarweb, Semrush, Ahrefs, Cloudflare
crawl-to-referral ratios) circulate widely and each vendor sells into this
category. I did not run them down, and a figure from one of them does not belong
in a plan. The Pew study plus the GA4 channel in §4.1 are enough to size the
question, and both are first-party or independent.

## 6. What LLM answers actually cite

The reliable finding here is a negative one: **the cited set is not the organic
set, and it is not the same set across engines.** Everything else is softer.

### Non-commercial measurements

**Kirsten et al. (Findings of ACL 2026), 4,706 queries, US and Germany.**
- More than **40% of AI Overview links are not in the organic top 10**; overlap
  stays below 60% against the top 100.
- Domain popularity is similar across surfaces: **38%** of Google organic domains
  are in the Tranco top 1K, against **34%** for AI Overviews and **35%** for the
  GPT search tool. So AI answers are not systematically more or less
  head-concentrated than organic.
- Composition differs sharply. Google organic returns **up to 33% social media and
  forum sources** on some datasets; the GPT models are **close to zero** on social
  media, reaching only 5 to 7% on the products dataset. The GPT models "rely
  heavily on Corporate Entities and Encyclopedias."
- Link counts differ by an order of magnitude: median **0** links per query for
  the GPT search tool (mean 0.4), median **9** for AI Overviews (mean 8.6), fixed
  10 for organic.

That third bullet cuts directly against a common vendor claim that Reddit is the
dominant lever for LLM visibility. It may be true of Google surfaces, which
license Reddit content; it is not true of the OpenAI surfaces in this measurement.

**Grossman et al. (SIGIR 2026), arXiv:2604.27790, 11,500 real user queries**,
comparing Google organic, Gemini and AI Overviews. AI Overviews were generated for
**51.5% of representative real-user queries**. Retrieved source sets overlapped at
**under 0.2 average Jaccard similarity** between systems. Google organic skewed
toward government and educational sites; the generative surfaces retrieved
**Google-owned content at significantly higher rates**. Sites blocking Google's AI
crawler saw substantially reduced retrieval in AI Overviews. And AI Overviews were
"less consistent when processing two runs of the same query, and less robust to
minor query edits."

**Li and Sinnamon (2024)**, *Proceedings of the Association for Information Science
and Technology* 61(1), 205-217, DOI 10.1002/pra2.1021, audited 1,008 responses
across Bing Chat and Perplexity and found **26% domain overlap** between them. I
could not access this paper directly (Wiley returned 403); the figures are read
via Martinez (2026) and are second-hand.

### The practical reading

Three independent groups, three different samples, one conclusion: **there is no
single "AI citation set."** Visibility is indexed by engine, surface, locale and
week. A share-of-voice number that averages across engines is averaging across
populations that share roughly a fifth of their sources.

## 7. Controls a site actually has

Everything in this section is from provider documentation I or my research agent
fetched and confirmed. Where a claim is only asserted by an SEO vendor, it is
labelled as such and does not carry a fact.

### 7.1 The three-way split every provider now documents

Every major provider separates **training-corpus collection**, **search-index
building**, and **answer-time fetching on behalf of a live user prompt** into
different agents. That split is what makes server-log separation possible.

| Provider | Training | Search index | Answer-time / user-triggered |
|---|---|---|---|
| OpenAI | `GPTBot` | `OAI-SearchBot` | `ChatGPT-User` (plus `OAI-AdsBot` for ad safety) |
| Anthropic | `ClaudeBot` | `Claude-SearchBot` | `Claude-User` |
| Google | `Google-Extended` (control token only) | `Googlebot` | `Google-Agent`, `Google-GeminiNotebook`, other user-triggered fetchers |
| Perplexity | none, explicitly | `PerplexityBot` | `Perplexity-User` |
| Microsoft / Bing | `bingbot` (one agent, controlled by page tags) | `bingbot` | `bingbot` |
| Common Crawl | `CCBot` | n/a | n/a |

Sources: OpenAI's bots page (developers.openai.com/api/docs/bots); Anthropic's
support article 8896518, last updated 2026-04-07; Google's crawler overview and
user-triggered-fetchers pages (updated 2026-06-12 and 2026-08-19); Perplexity's
docs.perplexity.ai/guides/bots; Common Crawl's ccbot page.

Two provider-specific facts worth holding:

- **Perplexity states it does not crawl for training at all.** PerplexityBot "is
  not used to crawl content for AI foundation models."
- **Microsoft ships no separate Copilot crawler.** Copilot and Bing Chat ride the
  bingbot index, so the control surface is page-level meta tags, not a robots.txt
  token. Per Microsoft's own 2023-09-22 webmaster blog post: `NOARCHIVE` content
  "will not be included in Bing Chat answers" and will not be used for training;
  `NOCACHE` content may appear in answers but only as URL, title and snippet, and
  only those elements may be used in training. Both leave normal Bing results
  unaffected.

### 7.2 robots.txt works for crawling and does not work for answer-time fetches

This is the single most consequential thing on this page for anyone writing a
robots.txt.

Three of the five major providers document, in their own words, that their
user-triggered fetcher ignores robots.txt:

- **OpenAI, on ChatGPT-User:** "Because these actions are initiated by a user,
  robots.txt rules may not apply."
- **Perplexity, on Perplexity-User:** "Since a user requested the fetch, this
  fetcher generally ignores robots.txt rules."
- **Google, on all user-triggered fetchers:** "Because the fetch was requested by
  a user, these fetchers generally ignore robots.txt rules."

**Anthropic is the exception**, and it is worth naming because it is the only one.
Its documentation states "Anthropic's Bots respect 'do not crawl' signals by
honoring industry standard directives in robots.txt" and gives `Disallow: /`
examples for all three tokens **including Claude-User**, with no user-initiated
carve-out.

Consequence: a robots.txt block is a decision about the training corpus and the
search index. It is not a decision about whether a model reads your page when a
user asks about you. If the goal is to be in the answer, blocking the search-index
agents (`OAI-SearchBot`, `PerplexityBot`, `Claude-SearchBot`, `Googlebot`) is the
move that actually removes you, and OpenAI and Perplexity both explicitly
recommend allowing theirs.

Grossman et al. (SIGIR 2026) measured the corresponding effect on the Google side:
sites blocking Google's AI crawler saw substantially reduced retrieval in AI
Overviews.

### 7.3 Google-Extended does not do what nearly everyone says it does

Google's own wording, from the common-crawlers page:

> "Google-Extended is a standalone product token that web publishers can use to
> manage whether content Google crawls from their sites may be used for training
> future generations of Gemini models that power Gemini Apps and Vertex AI API for
> Gemini and for grounding in Gemini Apps and Grounding with Google Search on
> Vertex AI."

> "Google-Extended does not impact a site's inclusion in Google Search nor is it
> used as a ranking signal in Google Search."

> "Google-Extended doesn't have a separate HTTP request user agent string.
> Crawling is done with existing Google user agent strings; the robots.txt
> user-agent token is used in a control capacity."

So: it covers Gemini training and Vertex/Gemini Apps grounding. **Its documented
scope does not include AI Overviews or AI Mode**, and because it has no user-agent
string, you cannot see it in your logs. It is a control token, not a crawler.

**What does control AI Overviews and AI Mode** is a separate and newer Search
Console setting, "Search generative AI control"
(support.google.com/webmasters/answer/16908024), which covers AI Overviews, AI
Mode, and generative AI in Discover, "isn't used as a ranking or inclusion signal
affecting other parts of Search," takes 1 to 2 days to apply, and leaves your
content still powering Google Search generally. This is a real, official,
first-party lever and it did not exist in most of the advice written about this
topic.

Page-level snippet controls (`nosnippet`, `data-nosnippet`, `max-snippet`,
`noindex`) also apply, per Google's "AI features and your website" page (updated
2025-12-10).

### 7.4 llms.txt: nobody has committed to it, and the crawlers do not fetch it

This is the most misreported item in the category, so the sourcing is exhaustive.

**What it is.** A proposal by Jeremy Howard of Answer.AI, published
**2024-09-03** at answer.ai/posts/2024-09-03-llmstxt.html, with a spec at
llmstxt.org (v2, published 2024-09-03, modified 2026-08-10) and a repo at
github.com/AnswerDotAI/llms-txt. The original post makes **no claim of provider
support.**

**Has any major provider committed to honoring it? No.** Google has denied it in
documentation, and the other four have said nothing either way.

Google's AI optimization guide (developers.google.com/search/docs/fundamentals/
ai-optimization-guide, updated **2026-07-10**), verbatim: **"You don't need to
create new machine readable files, AI text files, markup, or Markdown to appear in
Google Search."** The AI-features page (updated 2025-12-10) says the same thing
about markup.

John Mueller of Google, on Bluesky, **2025-06-17**: **"FWIW no AI system currently
uses llms.txt."** (bsky.app/profile/johnmu.com/post/3lrshm4gggs2v, post text and
timestamp pulled from the Bluesky public API.) In a later thread on
**2025-11-23** he added: "If those creating and running these systems knew they
could create better responses from sites with specific file formats, I expect they
would be very vocal about that. AI companies aren't really known for being shy."

**Two widely circulated quotes I could not verify and am not treating as
sourced:** a Mueller Reddit comment to the effect that server logs show AI
services do not even check for the file, and a Gary Illyes statement at Search
Central Live APAC (Bangkok, around 2025-07-23) that Google "does not support
llms.txt and has no plans to." Both appear only in SEO-vendor retellings. The
documented Google position above is the citable substitute for both.

**OpenAI, Anthropic, Perplexity and Microsoft:** no public statement found, for or
against. That is absence of commitment, not a documented denial.

**The log evidence.** Ahrefs published a study on **2026-06-15**
(ahrefs.com/blog/llmstxt-study/) using 137,210 domains in its own analytics
product with traffic in May 2026, checking each root for an llms.txt returning
HTTP 200 and classifying requests by user agent. **Ahrefs sells SEO tooling and
has a commercial interest in this category.** With that discount applied, the
findings:

- **97% of llms.txt files received zero requests** in May 2026.
- 96% of requests to llms.txt files came from bots, and **77% of those bots were
  not AI tools at all** (SEO audit tools 21.7%, unknown 14.9%, general crawlers
  13.1%, tech profiling 11.6%). AI categories combined were 19.5%.
- The load-bearing one: **"Zero requests came from AI bots for llms.txt files that
  don't exist."** No AI crawler probes for the file. A crawler that wanted the
  file would ask for it whether or not it was there.

Independently, Cloudflare's "agent readiness" post (**2026-04-17**, modified
2026-07-15) states: "By default, we only check whether the site correctly handles
Markdown content negotiation, and do not check for llms.txt." Cloudflare sells bot
management and is commercially interested, but declining to score llms.txt in a
product built to score agent-readiness is a signal against, not for.

**Publishing one is not evidence of consumption.** OpenAI publishes
developers.openai.com/llms.txt and Anthropic publishes
platform.claude.com/docs/llms.txt. Both are the automatic default output of their
documentation platform (Mintlify), not a statement of policy. Google's
developers.google.com/llms.txt returns 404.

**Verdict:** llms.txt costs almost nothing to publish and there is currently no
evidence any provider reads it. Treat any vendor claiming it improves AI
visibility as making an unsubstantiated claim.

### 7.5 Structured data: officially, it does nothing for AI answers

Google states this twice, in two separate official pages:

- AI optimization guide (updated 2026-07-10): **"Structured data isn't required
  for generative AI search, and there's no special schema.org markup you need to
  add."**
- AI features and your website (updated 2025-12-10): **"There's also no special
  schema.org structured data that you need to add."**

No official documentation from Google, OpenAI, Anthropic, Perplexity or Microsoft
claims schema.org markup influences an AI answer surface. Every such claim
encountered came from SEO vendors. Structured data remains worth doing for classic
rich results; that is a different justification and should be stated as one.

### 7.6 Verification of who actually fetched you

User agents are strings and anyone can send one. Perplexity, Common Crawl and
Google publish IP or reverse-DNS registries for verification
(perplexity.com/perplexitybot.json, perplexity.com/perplexity-user.json,
index.commoncrawl.org/ccbot.json). Common Crawl's own page warns about spoofed
CCBot user agents. If a log-based measurement is going to carry weight, it needs
IP verification, not string matching.

## What I could not access

- **The Search Console generative AI reports blog post body.** Title and
  2026-06-03 date confirmed from Google's own blog feed; the article itself would
  not retrieve. Needed for: §4.2, the reporting specifics (impressions without
  clicks, the data start date, the rollout scope). Substitute quality: weak, since
  the only accounts are SEO trade press. This is the largest actionable gap on the
  page, because if that instrument works as described it is better than everything
  else in §4 combined.
- **Li and Sinnamon (2024)**, *Proceedings of the Association for Information
  Science and Technology* 61(1), 205-217, DOI 10.1002/pra2.1021. Wiley returned
  403. Needed for: §6, the 26% cross-engine domain overlap over 1,008 responses.
  Read through Martinez (2026) only, so treat as second-hand.
- **C-SEO Bench full text.** Abstract and method read directly; the per-domain
  result table was not. Needed for: the 3-of-54 count in §2, which is therefore
  carried second-hand.
- **E-GEO full text.** Abstract only. Needed for: reconciling the paper's own
  optimistic framing against the survey's reading of it. Both are recorded rather
  than resolved.
- **Nestaas et al. (ICLR 2025) full text.** Abstract and survey description only.
  Used only for the boundary claim in §2.
- **Yuan et al. (2025) full text.** Abstract only. The 9% accuracy variation and
  9,000-token length figures come from the abstract.
- **Vendor referral-volume studies, deliberately not run down.** Similarweb,
  Semrush, Ahrefs and Cloudflare all publish on AI referral traffic and all sell
  into the category. Substitute quality: strong, since Pew and the GA4 channel
  cover the question first-party. Recorded as a choice rather than a gap.

**One structural note on access.** Everything genuinely load-bearing on this page
came from a provider's own documentation or an open preprint. The paywalled
material was consistently the least useful, which is the opposite of the usual
pattern and worth knowing before the next pass spends effort on it.

## Related Pages

- [The launch campaign protocol](../protocols/05-launch-campaign.md), step 6, "The LLM answer surface is a
  citation problem." This page is the sourcing behind it. Everything step 6 asserts
  survives contact with the evidence; it can now carry specific numbers instead of
  reasoning, and §3 here supplies the "unstable across runs" figure it needs.
- [`competitive-research-methods.md`](competitive-research-methods.md)
  for the E1 to E6 evidence tiers used to discount vendor sources here.
- A separate page on grounded answering over a personal corpus (not in this package)
  for the citation-fidelity literature this page touches at §4.5.

## Bibliography

### Peer-reviewed and preprint

- [GEO: Generative Engine Optimization](https://arxiv.org/abs/2311.09735) · Aggarwal, P., Murahari, V., Rajpurohit, T., Kalyan, A., Narasimhan, K., Deshpande, A. KDD '24 (ACM SIGKDD), 2024-08-25. DOI [10.1145/3637528.3671900](https://doi.org/10.1145/3637528.3671900). Accessed 2026-08-26. [primary, read in full]
  Used for: §1 in full. GEO-bench construction, both visibility metrics, all nine methods and their scores, the rank interaction, the Perplexity run, the limitations section.
- [C-SEO Bench: Does Conversational SEO Work?](https://arxiv.org/abs/2506.11097) · Puerto, H., Gubri, M., Green, T., Oh, S.J., Yun, S. NeurIPS 2025 Datasets and Benchmarks Track, 2025-06-06 (v3 2025-10-20). [Proceedings copy](https://proceedings.neurips.cc/paper_files/paper/2025/hash/27aa3aeff0f8460a7b43d30fa6c5c032-Abstract-Datasets_and_Benchmarks_Track.html). Accessed 2026-08-26. [primary, abstract and method read directly]
  Used for: §2. 9 methods, 2 tasks, 6 domains, 1,921 queries, multi-actor protocol; methods largely ineffective and often negative; traditional SEO more effective; congested zero-sum dynamics under adoption.
- [E-GEO: A Testbed for Generative Engine Optimization in E-Commerce](https://arxiv.org/abs/2511.20867) · Bagga, P.S., Farias, V.F., Korkotashvili, T., Peng, T., Wu, Y. 2025-11-25, revised 2026-07-14. Accessed 2026-08-26. [primary, abstract only]
  Used for: §2. 13,747 queries, 10 listings each, 5 engines, 7 rewriters, 15 heuristics; optimized prompts beat heuristics.
- [Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023-2026)](https://arxiv.org/abs/2607.14035) · Martinez, O. arXiv preprint, 2026-07-15. Accessed 2026-08-26. [secondary, survey, single author, not peer reviewed]
  Used for: §2 framing and the 45-study scope; the 3-of-54 C-SEO Bench count; the 10-of-15 E-GEO heuristic count; the Li and Sinnamon figures. Every underlying paper it cites that I used was verified against the original except Li and Sinnamon.
- [Adversarial Search Engine Optimization for Large Language Models](https://openreview.net/forum?id=hkdqxN3c7t) · Nestaas, F., Debenedetti, E., Tramèr, F. ICLR 2025. Accessed 2026-08-26. [primary, abstract only]
  Used for: §2, preference-manipulation attacks as the boundary case.
- [Characterizing Web Search in The Age of Generative AI](https://aclanthology.org/2026.findings-acl.526/) · Kirsten, E., Große Perdekamp, J., Wu, Q., Upadhyay, M., Gummadi, K.P., Zafar, M.B. Findings of ACL 2026, pp. 10827-10848. DOI 10.18653/v1/2026.findings-acl.526. Preprint [arXiv:2510.11560](https://arxiv.org/abs/2510.11560), v1 2025-10-13, v2 2026-05-31. Accessed 2026-08-26. [primary, v2 full text read]
  Used for: §3 and §6. 4,706 queries, US and Germany, five generative systems from three providers, temperature 0; 9-27% decision flips on five-minute repeat; two-month link overlap 45% organic / 40% Gemini / 18% AI Overviews; >40% of AIO links outside organic top 10; Tranco and source-type distribution; link counts per query.
- [How Generative AI Disrupts Search: An Empirical Study of Google Search, Gemini, and AI Overviews](https://arxiv.org/abs/2604.27790) · Grossman, R., Liu, S., Chen, M.K., Smith, M., Borcea, C., Chen, Y. SIGIR 2026, preprint 2026-04-30. Accessed 2026-08-26. [primary, abstract and findings read]
  Used for: §6. 11,500 queries; AI Overviews shown for 51.5% of real-user queries; <0.2 average Jaccard between systems; Google-owned content over-retrieved; AI-crawler blocking reduces retrieval; lower run-to-run consistency.
- [Don't Measure Once: Measuring Visibility in AI Search (GEO)](https://arxiv.org/abs/2604.07585) · Schulte, J., Bleeker, M., Kaufmann, P. arXiv preprint, 2026-04-08. Accessed 2026-08-26. [primary, full text read; note the authors work in the GEO tooling space, so treat the recommendation to buy measurement as interested and the measured variance as the usable part]
  Used for: §3 and §4.4. 32 prompts, 4 engines, 2026-01-24 to 2026-03-20 plus 10-repetition burst; day-to-day source Jaccard 0.336-0.423; n=7 for SE<0.10 and n=8 for SE<0.08; 10-day and 24-day window thresholds; 57.8% of ChatGPT runs returned zero citations.
- [Evaluating Verifiability in Generative Search Engines](https://arxiv.org/abs/2304.09848) · Liu, N.F., Zhang, T., Liang, P. Findings of EMNLP 2023, pp. 7001-7025. DOI 10.18653/v1/2023.findings-emnlp.467. Accessed 2026-08-26. [primary, abstract read]
  Used for: §4.5. Four engines audited; 51.5% of sentences fully supported; 74.5% of citations support their sentence.
- Li, A. and Sinnamon, L. "Generative AI search engines as arbiters of public knowledge: An audit of bias and authority." *Proceedings of the Association for Information Science and Technology* 61(1), 2024, pp. 205-217. DOI 10.1002/pra2.1021. [primary, NOT ACCESSED, Wiley returned 403]
  Used for: §6, the 26% domain overlap across Bing Chat and Perplexity over 1,008 responses. Read via Martinez (2026) only.
- [Defeating Nondeterminism in LLM Inference](https://thinkingmachines.ai/blog/defeating-nondeterminism-in-llm-inference/) · He, H. Thinking Machines Lab, September 2025. Accessed 2026-08-26. [primary, lab engineering post, read in full]
  Used for: §3. 1,000 completions at temperature 0 producing 80 unique outputs, divergence at token 103; batch non-invariance and server load as the mechanism.
- [Understanding and Mitigating Numerical Sources of Nondeterminism in LLM Inference](https://arxiv.org/abs/2506.09501) · Yuan, J., Li, H., Ding, X., Xie, W., Li, Y.-J., Zhao, W., Wan, K., Shi, J., Hu, X., Liu, Z. arXiv preprint, 2025-06-11 (v2 2025-10-24). Accessed 2026-08-26. [primary, abstract only]
  Used for: §3. Up to 9% accuracy variation and 9,000-token length difference at greedy decoding from GPU count, GPU type and batch size alone.

### Click-through and volume

- [Google users are less likely to click on links when an AI summary appears in the results](https://www.pewresearch.org/short-reads/2025/07/22/google-users-are-less-likely-to-click-on-links-when-an-ai-summary-appears-in-the-results/) · Pew Research Center, 2025-07-22. Accessed 2026-08-26. [primary, read in full]
  Used for: §5. 900 U.S. adults on KnowledgePanel Digital with a browsing tracker; March 2025 browsing data; 68,879 unique Google searches of which 12,593 produced an AI summary; 18% of searches generating a summary; 8% versus 15% click-through on traditional results; 1% clicking a link inside the summary; 26% versus 16% session-end rate; the Google-only scope caveat.
- [Google disputes Pew study showing AI Overviews reduce clicks by half](https://ppc.land/google-disputes-pew-study-showing-ai-overviews-reduce-clicks-by-half/) · PPC Land, 2025-07. Accessed 2026-08-26. [secondary]
  Used for: §5, Google's public characterization of the study as using "a flawed methodology and skewed queryset that is not representative of Search traffic." Recorded as a dispute; Google published no counter-figures.

### Provider primary sources

- [Default channel group](https://support.google.com/analytics/answer/9756891) · Google Analytics Help. Accessed 2026-08-26. [primary, Google documenting its own product]
  Used for: §4.1. AI Assistant channel rule (medium exactly matches `ai-assistant`, campaign `(ai-assistant)`, assigned when the referrer matches a list of AI assistants), and the explicit exclusion of Google's AI Overviews and AI Mode.
- [Introducing Search Generative AI performance reports in Search Console](https://developers.google.com/search/blog/2026/06/gen-ai-performance-reports) · Google Search Central Blog, 2026-06-03. Accessed 2026-08-26 via the [blog feed](https://developers.google.com/search/blog/feed.xml). [primary, title, date and summary confirmed; article body not retrievable through my tooling]
  Used for: §4.2.
- [OpenAI bots](https://developers.openai.com/api/docs/bots) · OpenAI. Accessed 2026-08-26. [primary]
  Used for: §7.1, §7.2. GPTBot / OAI-SearchBot / ChatGPT-User / OAI-AdsBot purposes and full UA strings; "Because these actions are initiated by a user, robots.txt rules may not apply."
- [Does Anthropic crawl data from the web, and how can site owners block the crawler?](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) · Anthropic, last updated 2026-04-07. Accessed 2026-08-26. [primary]
  Used for: §7.1, §7.2. ClaudeBot / Claude-User / Claude-SearchBot purposes; robots.txt honored including for Claude-User. Note: `anthropic-ai` and `claude-web`, which circulate in robots.txt boilerplate, do not appear in current official Anthropic documentation.
- [Google crawlers overview](https://developers.google.com/search/docs/crawling-indexing/overview-google-crawlers) · Google, updated 2026-06-12; [common crawlers](https://developers.google.com/search/docs/crawling-indexing/google-common-crawlers), updated 2026-07-14; [user-triggered fetchers](https://developers.google.com/search/docs/crawling-indexing/google-user-triggered-fetchers), updated 2026-08-19; [Google-Agent](https://developers.google.com/crawling/docs/crawlers-fetchers/google-agent), updated 2026-08-19. Accessed 2026-08-26. [primary]
  Used for: §7.1, §7.2, §7.3. The three crawler classes; "Because the fetch was requested by a user, these fetchers generally ignore robots.txt rules"; the full Google-Extended scope wording. Note the standalone `.../crawling-indexing/google-extended` URL 404s; the content lives under the `#google-extended` anchor on the common-crawlers page.
- [Search generative AI control](https://support.google.com/webmasters/answer/16908024) · Google Search Console Help. Accessed 2026-08-26. [primary]
  Used for: §7.3. Opt-out covering AI Overviews, AI Mode and generative AI in Discover; not a ranking or inclusion signal elsewhere in Search; 1-2 day application.
- [AI features and your website](https://developers.google.com/search/docs/appearance/ai-features) · Google, updated 2025-12-10; [AI optimization guide](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide) · Google, updated 2026-07-10. Accessed 2026-08-26. [primary]
  Used for: §7.4, §7.5. "You don't need to create new machine readable files, AI text files, markup, or Markdown to appear in Google Search"; "Structured data isn't required for generative AI search, and there's no special schema.org markup you need to add"; nosnippet / data-nosnippet / max-snippet / noindex as the page-level controls.
- [PerplexityBot and Perplexity-User](https://docs.perplexity.ai/guides/bots) · Perplexity. Accessed 2026-08-26. [primary]
  Used for: §7.1, §7.2, §7.6. Full UA strings; "not used to crawl content for AI foundation models"; "Since a user requested the fetch, this fetcher generally ignores robots.txt rules"; the published IP registries.
- [Announcing new options for webmasters to control usage of their content in Bing Chat](https://blogs.bing.com/webmaster/september-2023/Announcing-new-options-for-webmasters-to-control-usage-of-their-content-in-Bing-Chat) · Fabrice Canel, Microsoft Bing, 2023-09-22. Accessed 2026-08-26. [primary]
  Used for: §7.1. NOCACHE and NOARCHIVE semantics for Bing Chat answers and for training; both leave classic Bing results unaffected.
- [CCBot](https://commoncrawl.org/ccbot) and [FAQ](https://commoncrawl.org/faq) · Common Crawl. Accessed 2026-08-26. [primary]
  Used for: §7.1, §7.6. UA string, robots.txt and Crawl-delay compliance, the ccbot.json IP registry, and the warning about spoofed CCBot agents.

### llms.txt

- [The /llms.txt file](https://www.answer.ai/posts/2024-09-03-llmstxt.html) · Jeremy Howard, Answer.AI, 2024-09-03; spec at [llmstxt.org](https://llmstxt.org/) (v2, published 2024-09-03, modified 2026-08-10); repo [AnswerDotAI/llms-txt](https://github.com/AnswerDotAI/llms-txt). Accessed 2026-08-26. [primary, the proposal itself]
  Used for: §7.4 origin. The proposal claims no provider support.
- [John Mueller, Bluesky, 2025-06-17](https://bsky.app/profile/johnmu.com/post/3lrshm4gggs2v) · "FWIW no AI system currently uses llms.txt." Post text and timestamp verified via the Bluesky public API. Accessed 2026-08-26. [primary, individual statement from a Google Search Advocate, not Google policy]
  Used for: §7.4. Companion thread [2025-11-23](https://bsky.app/profile/johnmu.com/post/3m6ddo3ywo22p) used for the "AI companies aren't really known for being shy" line.
- [Are AI bots reading llms.txt? We analyzed 137,210 domains](https://ahrefs.com/blog/llmstxt-study/) · Louise Linehan with Xibeijia Guan, Ahrefs, 2026-06-15. Accessed 2026-08-26. [opinion / vendor study, SEO tooling vendor with a direct commercial interest; method and n stated, which is more than most]
  Used for: §7.4. 137,210 domains with May 2026 traffic; 97% of llms.txt files got zero requests; 96% of requests from bots; 77% of those bots not AI tools; zero AI-bot requests for non-existent llms.txt files.
- [Agent readiness](https://blog.cloudflare.com/agent-readiness/) · Cloudflare, 2026-04-17 (modified 2026-07-15). Accessed 2026-08-26. [opinion / vendor, CDN and bot-management vendor with a commercial interest]
  Used for: §7.4. "we only check whether the site correctly handles Markdown content negotiation, and do not check for llms.txt."
- [developers.openai.com/llms.txt](https://developers.openai.com/llms.txt) and [platform.claude.com/docs/llms.txt](https://platform.claude.com/docs/llms.txt) · accessed 2026-08-26. [primary, as artifacts]
  Used for: §7.4, that both providers publish one as automatic documentation-platform output. Google's `developers.google.com/llms.txt` returns 404.

Last updated: 2026-08-26
