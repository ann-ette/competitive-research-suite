# Research Protocol

Last reviewed: 2026-09-30 (first pass against outside practice: intelligence analysis, evidence grading, search reporting, fact checking, and measurements of model-written citations).

> Read this first on "deep research", "do a deep dive on X", "research X for me", or any request for sourced answers on a topic.

This is the workflow for any sourced research. It applies to product work, client work, writing, and personal study alike.

> **Upstream phase.** For coverage-heavy topics, run the [elicitation protocol](01-research-elicitation.md) first: exhaust what the model already holds, map the topic, and find the thin spots. Then this workflow sources the gaps instead of re-deriving what's known. That sweep is the input to step 2 (the source map).
>
> **When the subject is another organization**, [the competitive research protocol](04-competitive-research.md) layers on top of this one. Everything here still applies; that file adds what changes when the source has a marketing department: evidence tiers E1 to E6, the buyer's-set inclusion test, falsification in fresh context, the per-competitor record schema, refresh cadence, and the collection-and-publication legal gate.

---

## Receipts Are the Default

**Anything researched ships with links back to its sources. Every time, without being asked.** A claim a reader cannot trace is a claim they have to take on trust.

What that means in practice:

- **Every factual claim carries an inline link to the source that produced it**, in the body where the claim is read. A source named in prose with the URL only in a list at the bottom still makes the reader hunt.
- **Every research page ends in a `## Bibliography`** in the entry shape below, with a tier tag and an access date on each entry. This holds even when the page fetched nothing itself.
- **A page that reasons over other pages links to those pages beside each claim, and still lists the underlying originals.** The reader gets to the primary source in one hop rather than two. In my own knowledge base, a synthesis page that collected nothing itself carries a full bibliography naming which sibling page fetched each source and on what date.
- **A carried-forward access date is labelled as carried**, since it records when somebody else fetched the page rather than when this one did. Re-check the load-bearing few at source and mark those separately.
- **A claim with no linkable source says so in the text.** "I did not look this up," or "carried from an earlier recap, not re-fetched," beats a bare assertion.
- **Each citation supports the sentence it sits beside.** A working, on-topic link is the normal case even when the claim is unsupported, so checking that a link opens finds almost nothing. For every load-bearing citation, reopen the source and find the passage that says what the sentence says. Resolve every arXiv id and DOI and match its title, since a real id attached to the wrong paper reads as fine. When a model drafted the page, run this check in a fresh context that does not hold the draft.

**Existing pages get amended when next touched, with no migration sweep.** A sweep restamps every `last_updated` date and destroys the staleness signal.

## When This Fires
- Phrase triggers: "deep research", "deep dive", "research this", "find sources on", "what do we know about", "look into X for me"
- Auto-fires for any question where the right answer requires citations, not just reasoning.
- Does NOT fire for quick lookups ("what year did X ship") unless the answer is contested or load-bearing.

## Workflow

1. **Confirm scope before searching.** One sentence back to whoever asked: "Reading this as: [restated question]. Time-bounded to [horizon]? Geography? Adjacent topics in or out?" Skip this only if the ask is unambiguous.
2. **Build a source map first.** Before opening anything, list intended source categories (academic / industry / primary / news / opinion). For anything substantial (>30 min of work) show the map and let the asker redirect. A claim that something is absent ("no source found," "nothing published on X") names the searches behind it and the date they ran, since a negative from one search path is weak evidence.
3. **Prioritize primary sources.** Company filings, official docs, original research papers, press releases from the source. Secondary sources are for synthesis, not for load-bearing claims.
4. **Cross-verify load-bearing claims.** Never trust a single source for a number, date, or causal claim that the final artifact will rest on. Two independent sources minimum. **Independent means separate origins:** trace each source back to where the claim started, and count sources that rest on one press release, paper, dataset, or vendor post as one. Then run one search phrased to find the source that **contradicts** the claim, because a search for confirmation finds confirmation.
5. **Bibliography grows as I go, not at the end.** Every source I open gets logged immediately, even if I end up not using it. The "rejected" pile is itself useful evidence.
6. **Synthesize with inline citations.** Answer up top, citations inline, full bibliography at the bottom.
7. **Flag what I couldn't access.** Blocked sources get called out by name in the deliverable, not silently dropped. See blocked-source protocol below.

## Preferred Sources by Type

| Type | Go-to | Avoid |
|------|-------|-------|
| Academic | Google Scholar, arXiv, PubMed, SSRN, JSTOR | Predatory journals, citation farms |
| AI / ML research | arXiv, Anthropic / OpenAI / DeepMind blogs, individual researcher pages | Twitter takes about papers without the paper itself |
| Industry / market | Original company reports, S-1s and 10-Ks, Gartner / Forrester (if accessible), CB Insights | Aggregator listicles, "top 10" SEO content |
| News | Original reporting (NYT, WSJ, FT, Reuters, Bloomberg, sector-specific) | Reuters aggregators of aggregators, Yahoo reprints |
| Tech / product | Hacker News comments (for context, not citations), GitHub issues, official changelogs, conference talks | Medium SEO posts, AI-generated explainers |
| Therapy / psychology | APA, peer-reviewed journals, primary-source books (Bowlby, Bowen, etc.), licensed-clinician writing | Instagram therapists, BetterHelp content marketing |
| Legal / regulatory | Primary statutes, agency rulings, court opinions | Law-firm marketing summaries (unless used as a starting point only) |

**Hard exclusions:** AI-generated SEO content, content farms, "X explained in 5 minutes" YouTube without a credentialed source, paraphrased aggregators of original reporting.

**Two checks before leaning on a source:**
- **An unfamiliar source gets read laterally.** Leave the page and see what independent sources say about who runs it before trusting what it says about itself. Official-looking logos, domains, and polish are what fool careful readers.
- **A load-bearing paper gets its status recorded.** Say whether it is peer reviewed or a preprint (anything only on arXiv is a preprint), and check it has not been retracted: Crossref has published the Retraction Watch database openly since 2023, and the publisher's page carries any notice.

## Blocked-Source Protocol

If a high-value source is paywalled, login-walled, geo-blocked, or otherwise inaccessible, first look for an open copy of the same work: PubMed Central or Europe PMC, arXiv, the author's or institution's page. An open copy of the same text is the same source, so taking it is no substitution. Unpaywall requires an email in every request, so it gets the shared support address or nothing, never a person's own. If no open copy exists:

1. **Stop. Do not silently substitute** a weaker source. Silent substitution is the failure mode this protocol exists to prevent.
2. **Say exactly what's blocked and why it matters.** Format: *"Blocked: [source]. Needed for: [specific claim or section]. Substitute quality: [strong / weak / none available]."*
3. **Offer the access options, in this order:**
   - Open it in a signed-in browser session the model can read (works for login-walled sources where an account exists).
   - Download the PDF and drop it in the relevant folder.
   - Paste the relevant excerpt.
   - Approve moving on without it (and I flag the gap in the deliverable).
4. **Never paraphrase a source I haven't actually read.** If I only saw the abstract, the citation says "abstract only."

## Bibliography Format

**Entry shape:**
```
- [Title](url) · Author(s), Publication, YYYY-MM-DD. Accessed YYYY-MM-DD. [primary / secondary / opinion]
  Used for: [which claim or section]
```

In my setup a daily sync reads this shape: the tier tag, `Accessed`, `Used for:`, "carried from," and "rejected" or "not used" for the set-aside pile. A change to the shape needs the sync changed with it.

**Where the bibliography lives.** Two places, and only two. A searchable union across every project, and the per-deliverable record: sources at the bottom of the post, page, or report itself, in the entry shape above, so they ship with the artifact. A third copy in between only drifts. My union is one JSON file that fills itself: once a day a script copies in every source a knowledge-base page's `## Bibliography` cites, so a research session writes the page's bibliography and adds nothing anywhere else. A spreadsheet does the same job with a manual paste.

## Where Research Output Lives

**All of it goes to one knowledge base, whatever prompted it.** Client work, competitive work, product research, a blog post's background reading: same base, one page per company or topic, so the same company does not get researched twice under two filing systems.

Two things are NOT research and do not move there:
- **Pipeline and project state.** Status, tier, next action, outreach logs. Those stay in their tracker.
- **The deliverable itself.** A blog post, a report, a brief stays with its own project, and its bibliography ships with it (see the deliverable format below). What lands in the knowledge base is the durable finding.

Pages are split by kind:

- **Company-specific findings** → `knowledge-base/Companies/<Company Name>/` (company profile, product profile, pricing, capability).
- **Industry or topic findings** → `knowledge-base/Industries/<Industry or Topic Name>/` (market landscape, competitive set, audience map, GTM benchmarks).
- **The test that resolves the two** (from [the competitive research protocol](04-competitive-research.md)): **a claim about one organization is a `Companies/` claim; a claim about the relationship between organizations is an `Industries/` claim.** So pricing, scale, and capability go to Companies, while a roster, a comparison, a shortlist finding, or a capability matrix goes to Industries and cites the Companies pages for every underlying fact. Every Companies page carries a `Part of:` line to its set page; every set page carries the roster with links back.
- **`## Bibliography` is the heading** inside the base, in the entry shape above.
- Each page is self-contained: title, 2-3 tags, a 2-3 sentence summary, a confidence map, body with inline citations, a page-level Bibliography, a "Related pages" cross-reference line, and a "Last updated" date.

## Research Runs Write Straight to Disk

**A research page goes to its knowledge-base folder the moment it's finished, and its downloaded sources go to `source-library/` under the same path.** A session scratchpad can be temporary (mine is emptied by macOS on restart), and a multi-agent workflow's journal keeps each agent's summary and the path it wrote, while the page itself exists only where it was written. On 2026-09-23 a two-workflow run on practice verticals wrote all 18 pages (1.8 MB) and 691 MB of sources only to its scratchpad. The first workflow had already been interrupted once that day, and the pages survived because the Mac happened not to restart.

- **Pages.** Write each to `knowledge-base/Industries/<Topic>/` or `Companies/<Name>/` as soon as its agent finishes, with a `**Status:** draft` line in the header block while it still owes a pass (a source check, an integration step). Delete the line when the page is done, so a page without it reads as finished, as every older page is.
- **Sources.** Fetch PDFs, HTML and extracted text straight into `source-library/Industries/<Topic>/` (or `Companies/<Name>/`), mirroring the page folder. `source-library/` is gitignored, so hundreds of megabytes stay out of git history and still survive a restart. A copy made at the end of a run protects nothing from a restart during it.
- **The scratchpad** holds working files: scripts, partial extracts, check output, page parts before assembly.
- **A workflow script takes both folders as arguments and refuses to start without them.** The launching session lists the knowledge base first and reuses an existing folder when one fits, since a name worked out from the topic can land beside a near-duplicate. It passes absolute paths, and every agent prompt names the exact file that agent writes. When a path contains a space, an agent quotes it in every shell command.

```js
const KB = args && args.kbDir, SRC = args && args.sourceDir
if (!KB || !SRC) throw new Error('research workflow needs args.kbDir and args.sourceDir as absolute paths')
```

- **Before closing,** list any markdown in the session's scratchpad with no copy in the knowledge base. Mine is a short script that a pre-commit hook also runs.

## Deliverable Format

Default structure for any deep-research output:

```
# [Topic]

## TL;DR
[2-3 sentence answer. The thing that was actually asked.]

## Confidence map
- High confidence: [claim] (why: e.g. two independent primary sources that agree)
- Medium confidence: [claim] (why it falls short: one study, vendor-run, abstract only, a different population, small sample)
- Contested / unresolved: [conflicting sources, flag both sides]
- My reasoning, unsourced: [inferences, also marked where they are read in the body]

## [Body sections with inline citations]

## What I couldn't access
[Blocked sources, what they would have changed, what to do about it]

## Bibliography
[Full entries]
```

Skip sections that don't apply. Don't pad.

**Each confidence level names its reason.** A count of sources is a start. What lowers confidence is a source's quality, whether the sources agree, and whether they measured this question or a neighboring one, so the map says which applies.

## Anti-Patterns (Do Not Do)

- Don't aggregate from secondary sources without checking the primary.
- Don't pad the deliverable with adjacent-but-irrelevant context to look thorough.
- Don't hedge with "seems," "may," "could" when a take was asked for. Confidence flags are how I express uncertainty, not weasel words.
- Don't silently skip blocked sources.
- Don't write a wall of prose when a table or list would serve.
- Don't violate the house voice rules (no em dashes, no space-hyphen-space, sentence case in prose, no AI tells, fewer words).

## Research Grounding (2026-09-30)

The first check of this protocol against outside practice. Sources were read at abstract or summary level unless marked.

**What changed the protocol.**
- Liu, Zhang & Liang (2023), Evaluating Verifiability in Generative Search Engines, Findings of EMNLP. Only 74.5% of citations supported the sentence they were attached to. https://arxiv.org/abs/2304.09848
- Onweller et al. (2026), Cited but Not Verified. Across 14 models, links worked over 94% of the time and the cited claims held 39 to 77% of the time. Why the check is on support. https://arxiv.org/abs/2605.06635
- Venkit et al. (2025), DeepTRACE. Deep-research systems leave a large fraction of their statements unsupported by their own listed sources. https://arxiv.org/abs/2509.04499
- Walters & Wilder (2023), Scientific Reports 13:14045. 18% of GPT-4's citations were fabricated, and 24% of its real ones carried substantive errors. Why ids get resolved. https://doi.org/10.1038/s41598-023-41032-5
- Caulfield (2019), SIFT. Trace claims, quotes, and media back to the original context. Why independence means separate origins. https://hapgood.us/2019/06/19/sift-the-four-moves/
- ODNI (2015, amended 2022), ICD 203 Analytic Standards, read in full. Consider contrary information, describe source quality, and distinguish information from judgment. Why the contradicting search and the reasoning label. https://archive.dni.gov/files/documents/ICD/ICD-203.pdf
- GRADE Handbook (2013). Certainty is rated down for risk of bias, inconsistency, indirectness, imprecision, and publication bias. Why each confidence level carries a reason. https://gdt.gradepro.org/app/handbook/handbook.html
- Wineburg & McGrew (2019), Teachers College Record 121(11), read through Breakstone et al. (2021). Fact checkers judge a site by leaving it. Why unfamiliar sources are read laterally. https://misinforeview.hks.harvard.edu/article/lateral-reading-college-students-learn-to-critically-evaluate-internet-sources-in-an-online-course/
- Schneider, Woods & Proescholdt (2022), the RISRS report. 5.4% of citations made after a retraction acknowledged it. Why load-bearing papers get a status check. https://pmc.ncbi.nlm.nih.gov/articles/PMC9483880/
- Rethlefsen et al. (2021), PRISMA-S, Systematic Reviews 10:39. Searches reported as run, with the date. Why absence claims name their searches. https://pmc.ncbi.nlm.nih.gov/articles/PMC7839230/

**What confirmed it.** Pew Research Center (2024) found 38% of pages from 2013 gone a decade later, and Zittrain, Albert & Lessig (2014) found reference rot in most law-journal links. The rule that downloaded sources are kept on disk already answers both. https://www.pewresearch.org/data-labs/2024/05/17/when-online-content-disappears/
