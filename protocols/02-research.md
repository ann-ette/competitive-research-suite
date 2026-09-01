# Research Protocol

> Read this first on "deep research", "do a deep dive on X", "research X for me", or any request for sourced answers on a topic.

This is the workflow for any sourced research. It applies to product work, client work, writing, and personal study alike.

> **Upstream phase.** For coverage-heavy topics, run the [elicitation protocol](01-research-elicitation.md) first: exhaust what the model already holds, map the topic, and find the thin spots. Then this workflow sources the gaps instead of re-deriving what's known. That sweep is the input to step 2 (the source map).
>
> **When the subject is another organization**, [the competitive research protocol](04-competitive-research.md) layers on top of this one. Everything here still applies; that file adds what changes when the source has a marketing department: evidence tiers E1 to E6, the buyer's-set inclusion test, falsification in fresh context, the per-competitor record schema, refresh cadence, and the collection-and-publication legal gate.

---

## When This Fires
- Phrase triggers: "deep research", "deep dive", "research this", "find sources on", "what do we know about", "look into X for me"
- Auto-fires for any question where the right answer requires citations, not just reasoning.
- Does NOT fire for quick lookups ("what year did X ship") unless the answer is contested or load-bearing.

## Workflow

1. **Confirm scope before searching.** One sentence back to whoever asked: "Reading this as: [restated question]. Time-bounded to [horizon]? Geography? Adjacent topics in or out?" Skip this only if the ask is unambiguous.
2. **Build a source map first.** Before opening anything, list intended source categories (academic / industry / primary / news / opinion). For anything substantial (>30 min of work) show the map and let the asker redirect.
3. **Prioritize primary sources.** Company filings, official docs, original research papers, press releases from the source. Secondary sources are for synthesis, not for load-bearing claims.
4. **Cross-verify load-bearing claims.** Never trust a single source for a number, date, or causal claim that the final artifact will rest on. Two independent sources minimum.
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

## Blocked-Source Protocol

If a high-value source is paywalled, login-walled, geo-blocked, or otherwise inaccessible:

1. **Stop. Do not silently substitute** a weaker source. Silent substitution is the failure mode this protocol exists to prevent.
2. **Say exactly what's blocked and why it matters.** Format: *"Blocked: [source]. Needed for: [specific claim or section]. Substitute quality: [strong / weak / none available]."*
3. **Offer the access options, in this order:**
   - Open it in a signed-in browser session the model can read (works for login-walled sources where an account exists).
   - Download the PDF and drop it in the relevant folder.
   - Paste the relevant excerpt.
   - Approve moving on without it (and I flag the gap in the deliverable).
4. **Never paraphrase a source I haven't actually read.** If I only saw the abstract, the citation says "abstract only."

## Bibliography Format

**Default entry shape:**
```
- [Title](url) · Author(s), Publication, YYYY-MM-DD. Accessed YYYY-MM-DD. [primary / secondary / opinion]
  Used for: [which claim or section]
```

**Where the bibliography lives.** Two places, and only two. A searchable union across every project (mine is one JSON file the workspace writes to; a spreadsheet does the same job), and the per-deliverable record: sources at the bottom of the post, page, or report itself, in the entry shape above, so they ship with the artifact. A third copy in between only drifts.

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

## Deliverable Format

Default structure for any deep-research output:

```
# [Topic]

## TL;DR
[2-3 sentence answer. The thing that was actually asked.]

## Confidence map
- High confidence: [claims with 2+ independent primary sources]
- Medium confidence: [single strong source, or multi-source but secondary]
- Contested / unresolved: [conflicting sources, flag both sides]

## [Body sections with inline citations]

## What I couldn't access
[Blocked sources, what they would have changed, what to do about it]

## Bibliography
[Full entries]
```

Skip sections that don't apply. Don't pad.

## Anti-Patterns (Do Not Do)

- Don't aggregate from secondary sources without checking the primary.
- Don't pad the deliverable with adjacent-but-irrelevant context to look thorough.
- Don't hedge with "seems," "may," "could" when a take was asked for. Confidence flags are how I express uncertainty, not weasel words.
- Don't silently skip blocked sources.
- Don't write a wall of prose when a table or list would serve.
- Don't violate the house voice rules (no em dashes, no space-hyphen-space, sentence case in prose, no AI tells, fewer words).
