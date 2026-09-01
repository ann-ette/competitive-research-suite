# Competitive Research Suite

Five protocols for research that holds up when someone checks it, plus study pages, prompts, and sourced research behind them. For product marketers and founders making a positioning, pricing, naming, or launch call.

## Method in Seven Lines

1. Name the decision before any search. Research with no decision attached produces a forty-factor list nobody acts on.
2. Build the buyer's set from evidence a buyer considered a name. A roster drawn from who *could* compete profiles the wrong fifteen companies.
3. Declare comparison axes before opening a competitor's page, or they get chosen to flatter.
4. Tier every claim to its evidence. Vendor marketing is primary about what a company claims, weak about what it ships.
5. Try to break each load-bearing claim in fresh context before it goes public.
6. Write the record with a refresh cadence and a named owner.
7. Run the legal gate before anything comparative ships. Then plan the launch.

## Start Here

| Read | File | Covers |
|---|---|---|
| 1 | [`protocols/04-competitive-research.md`](protocols/04-competitive-research.md) | Buyer's-set inclusion test · E1 to E6 evidence tiers · adversarial verification · per-competitor record · capability matrix rules · cadence · legal gate |
| 2 | [`protocols/05-launch-campaign.md`](protocols/05-launch-campaign.md) | Launch tiers by what changed for the buyer · one-sentence launch thesis · naming gate · surfaces ordered by decay rate · measurement declared before launch, with a kill criterion · answer-engine surface as a citation problem |
| 3 | [`prompts/README.md`](prompts/README.md) | Every prompt from the protocols, ready to paste |

## All Five Protocols

| File | Job | Runs when |
|---|---|---|
| [`01-research-elicitation.md`](protocols/01-research-elicitation.md) | Find gaps in a topic before sourcing starts | Building or extending a corpus; "am I missing anything" |
| [`02-research.md`](protocols/02-research.md) | Sourced-research workflow: source maps, primary-source priority, cross-verification, blocked-source rule, bibliography shape, filing | Any question that needs citations |
| [`03-options-review.md`](protocols/03-options-review.md) | Benchmark a load-bearing technical choice against the whole field, including options nobody chose | Choosing or revisiting expensive-to-change technology |
| [`04-competitive-research.md`](protocols/04-competitive-research.md) | Claims about other organizations | Positioning, pricing, battlecards, comparison pages |
| [`05-launch-campaign.md`](protocols/05-launch-campaign.md) | What a launch is for, what it's called, which surfaces carry it, how you'd know it worked | Any launch above a changelog entry |

Order matters at one join: competitive research runs before launch planning. A launch planned before the buyer's set exists is positioned against guesses.

## Evidence Status

- Launch protocol opens with a table marking each section sourced or `[reasoning]`; sections carry the tag inline.
- Study pages carry the same marks.
- Read the table first. A document in this style reads as sourced whether or not it is.

Two findings contradict what the field generally says:

- **Naming.** Legal half rests on primary law and is settled. Behavioral half rests on lab studies of undergraduates rating fictitious consumer goods; Yorkston and Menon's sound-symbolism effect vanished when participants knew the name was a test name, which is a technical buyer's permanent condition. Whether a capability needs a name at all has no empirical literature in any commercial software context. Sourcing: [`research/product-naming.md`](research/product-naming.md).
- **Answer-engine visibility.** GEO's founding paper ran gpt-3.5-turbo over five Google results and measured word share, never human behavior. Direct replication found most tactics ineffective or negative; gains concentrated in low-ranked sources while top-ranked sources lost visibility. Measurement needs 7 to 8 repetitions per prompt over two to four weeks. Circulating advice on robots.txt, Google-Extended, llms.txt, and structured data is wrong on specifics; provider documentation is cited for each correction. Sourcing: [`research/llm-search-visibility.md`](research/llm-search-visibility.md).

## Layout

```
competitive-research-suite/
  README.md          this file
  CONTRIBUTING.md    what changes are welcome, how canon works
  LICENSE.md         CC BY 4.0 on documents, MIT on scripts
  MANIFEST.md        source hash per cut file, so drift is visible
  protocols/         five binding processes, in reading order
  study/             09 frameworks · 15 execution · 16 campaigns · 17 naming · 18 developer marketing
  prompts/           every prompt from the protocols, gathered
  research/          sourced research behind the sourced sections
```

## Notes on the Study Pages

- Page numbers (09, 15, 16, 17, 18) match the larger wiki they came from, since pages cite each other by number. Links to pages outside this cut render as plain text and say so.
- "Interview fluency" sections are first-person study material. Client copy uses the client's style guide.
- Worked examples use my own public products. No client engagement is named anywhere in this package.
- `## Sources` lists predate the `## Bibliography` convention in the protocols and were left alone; the competitive protocol says why.

## Using It with a Model

- Prompts assume web access and a large context window, or an orchestrator that spawns workers with separate contexts.
- Every prompt starts with the P0 preamble: read the protocol before the first tool call, note where prompt and protocol disagree.
- Two rules break most often: marketing copy is never recorded as documentation, and a number absent from a source is never synthesized from one.
- A model's own recall about a competitor is not a source. Company facts in model memory are stale by construction and wrong about pricing in particular. Every fact gets fetched.

## Not Here Yet

- A de-identified worked pass: eight process diagrams from a real engagement plus a read-along companion, every company reduced to its role.
- A deck checker that guards built boards against text overrun and voice slips.

Both land in their own folders when ready.

## Provenance

- Written by Annette Lapham at Lantern Works from the working copies I run these protocols with.
- Cut from that repo by a script that generalizes internal paths and tool names and refuses to write if a private name survives. `MANIFEST.md` carries each source hash at cut time.
- Corrections: open an issue or pull request here. I fold accepted changes into canon and re-cut. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

## License

Documents [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Scripts MIT. Both in [`LICENSE.md`](LICENSE.md).
