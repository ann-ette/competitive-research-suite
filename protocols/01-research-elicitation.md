# Research Elicitation Protocol

Last reviewed: 2026-09-30 (third pass, against work published through 2025).

Purpose: get near-complete coverage of a topic from a model deliberately, in one structured run, instead of across 10 ad hoc passes. Use it when the goal is coverage. Skip it when you just need one fact.

## When to Run It
- Building or expanding a wiki section.
- A deep-research question where missing a nuance is costly.
- Constructing or extending a RAG corpus.
- Any "make sure I'm not missing anything" task.

## When Not To
- Simple factual lookups.
- Time-sensitive single answers.
- Anything where one good response is enough. The full sweep costs tokens and time. Reserve it for coverage goals, or it becomes the kind of busywork that feels productive and isn't.

## The Protocol

1. **Map before you ask.** "List every sub-topic, dimension, and question needed to fully understand X, with the probability that each appears in a standard treatment of X. Do not answer them, just enumerate. Then list ten more, each under 0.10." Then: "Critique that list. What's missing?" This externalizes the structure before you fill it. Asking for a set with stated probabilities counters the pull toward the most typical answers that preference training leaves in a model (verbalized sampling, Zhang et al. 2025); the under-0.10 pass is an adaptation aimed at the long tail.

2. **Sweep each sub-topic across fixed axes (the generating set):**
   - Abstraction: definition, mechanism, application, critique.
   - Perspective: the four to six perspectives this topic's own literature takes, found by skimming related articles or a review's sections before the sweep (STORM, Shao et al. 2024). A therapy topic might give clinician, researcher, patient, skeptic; a database topic, operator, developer, vendor, skeptic. It surfaces different material but does not improve factual accuracy (see grounding), so use it to widen coverage and leave facts to the sources.
   - Polarity: what it is, and what it is not. Differential against the things it gets confused with.
   - Edges: exceptions, failure modes, contraindications, when it does not apply. Safety-critical content lives here.
   - Stance: the case for, the case against, the strongest critique.
   - Time: origins, current consensus, what's emerging or disputed.

3. **Work the negative space.** After each answer: "What did you leave out?" and "What would an expert say is oversimplified here?" Then once per topic: "What questions about X am I not asking?" Ask for these as a list with probabilities, as in step 1, so the answer reaches past the obvious omissions.

4. **Stop at saturation, checked against an outside list.** Done when new framings stop producing new content and the map covers an outside yardstick: the section list of a review article, a textbook's contents, or the headings of related reference articles. One model repeats itself and different models converge on the same answers (Artificial Hivemind, Jiang et al. 2025), so the model running dry is weak evidence that the topic has. Coverage is defined by marginal return going to zero, measured against that list.

5. **Detect gaps.** When triangulating a point makes the model vague, hedgy, or self-contradictory across framings, that's a parametric gap. Switch to primary sources for that point. Do not let the model fill it from memory. This is semantic-entropy hallucination detection in plain clothes (Farquhar et al. 2024): disagreement across samples is the signal.

## Guardrail
Self-critique is not ground truth. Models do not reliably self-correct reasoning without external grounding (Huang et al. 2023). Verify the union against real sources before it enters a corpus. The corpus is the external grounding that makes the whole loop trustworthy in the first place.

Two techniques sharpen the verify step:
- Verify with independent questions. Ask your fact-check questions in a fresh context so the model does not see its own draft. Models that re-read their own output repeat their own errors (chain-of-verification, Dhuliawala et al. 2023).
- Decompose to atomic claims. Break a long answer into single-fact claims and check each against a source before ingest. This is the standard decompose-then-verify pipeline (FactScore, Min et al. 2023; SAFE, Wei et al. 2024), and it is the right QA pass for a corpus.

And the empirical reason any of this matters: models reliably hold popular facts but fail on the long tail, where retrieval is what saves them (Mallen et al. 2023). Your wiki is the long tail.

## Reliability Upgrades (Second Pass)
Beyond eliciting coverage, these raise the reliability of the union (revised in the third pass):
- Sample and vote, on the shaky points only. Run a question several independent times and take the majority where step 5 found the model vague or inconsistent. The original gains came on models that were often wrong in one pass (self-consistency, Wang et al. 2022; More Agents Is All You Need, Li et al. 2024); on Gemini 2.5, 20 samples added 0.4% on HotpotQA (Loo 2025, one preprint), so voting on everything spends tokens for little.
- Vote instead of debating. Majority voting accounts for most of the gain credited to multi-agent debate, and debate alone does not raise expected correctness (Choi et al. 2025; Smit et al. 2024). Debate (Du et al. 2023) was dropped in the third pass.
- Branch and backtrack only on a model without built-in reasoning. Reasoning models already explore and prune paths inside their own thinking, so prompting for explicit branches (Tree of Thoughts, Yao et al. 2023) mostly repeats that work. This is judgment; no source was checked for it.

## Copy-Paste Starter
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

## Research Grounding
Two fields converged on this. None of it is a single named protocol; the packaging here is assembled from these results.

**Coverage and the stopping rule (qualitative social science).**
- Glaser & Strauss (1967), theoretical saturation in grounded theory. Origin of "iterate until no new categories emerge."
- Guest, Bunce & Johnson (2006), "How many interviews are enough? An experiment with data saturation and variability," Field Methods 18(1):59-82. Empirical work on when saturation actually hits. https://journals.sagepub.com/doi/10.1177/1525822X05279903
- Hennink, Kaiser & Marconi (2017), code vs meaning saturation. You reach "what the codes are" fast and "what they mean" slowly. Maps to: surface coverage is quick, nuance is the long tail. https://pmc.ncbi.nlm.nih.gov/articles/PMC9359070/

**Why the union beats one pass (LLM research).**
- Wang et al. (2022), Self-Consistency. Sampling diverse reasoning paths and aggregating beats the single greedy answer. https://arxiv.org/abs/2203.11171
- Arora et al. (2022), Ask Me Anything. Prompting is brittle; multiple imperfect prompts aggregated beat any single prompt. Direct grounding for "the union of framings." https://arxiv.org/abs/2210.02441
- Zhou et al. (2022), Least-to-Most Prompting, and Khot et al. (2022), Decomposed Prompting. Decompose into sub-questions first. Grounds the map-first move. https://arxiv.org/abs/2205.10625

**Self-critique, and its limit.**
- Madaan et al. (2023), Self-Refine. One model as generator, critic, and refiner improves outputs by roughly 20%. Grounds the negative-space step. https://arxiv.org/abs/2303.17651
- Huang et al. (2023), "Large Language Models Cannot Self-Correct Reasoning Yet." Intrinsic self-correction is unreliable without external feedback. This is why the guardrail exists. https://arxiv.org/abs/2310.01798

**Perspective prompting, honest caveat.**
- Zheng et al. (2024), "When 'A Helpful Assistant' Is Not Really Helpful." Personas do not improve factual accuracy, and any single persona's effect is close to random. But aggregating the best persona per question does help. Translation: use perspectives to widen coverage, rely on the union, never trust one voice for correctness. https://arxiv.org/abs/2311.10054

**Whether the model knows its own gaps.**
- Kadavath et al. (2022), "Language Models (Mostly) Know What They Know." Models are decently calibrated on whether they know an answer, but calibration degrades on new tasks, which is exactly where real gaps live. Their sense of "I know" rises when relevant sources are in context. This is the calibration basis for the gap-detector, and an argument for RAG. https://arxiv.org/abs/2207.05221

## Research Grounding, Second Pass
Strands surfaced by running this protocol on itself.

**Why the wiki (the long tail) matters.**
- Mallen et al. (2023), When Not to Trust Language Models. LMs hold popular facts but fail on long-tail facts; retrieval fixes the tail and scaling does not. Retrieval can also mislead on popular facts, so retrieve selectively. https://arxiv.org/abs/2212.10511

**Verification and hallucination.**
- Dhuliawala et al. (2023), Chain-of-Verification. Draft, plan verification questions, answer them independently, revise. Independence is the crux. https://arxiv.org/abs/2309.11495
- Farquhar, Kossen, Kuhn & Gal (2024), Detecting hallucinations using semantic entropy, Nature 630:625-630. Disagreement across sampled meanings flags confabulation. Basis for the gap-detector. https://www.nature.com/articles/s41586-024-07421-0
- Min et al. (2023), FactScore, and Wei et al. (2024), SAFE. Decompose long text into atomic claims and verify each against evidence. The corpus QA pipeline. https://arxiv.org/abs/2305.14251

**Aggregation and reliability.**
- Du et al. (2023), Multiagent Debate. https://arxiv.org/abs/2305.14325
- Yao et al. (2023), Tree of Thoughts. https://arxiv.org/abs/2305.10601
- Li et al. (2024), More Agents Is All You Need. https://arxiv.org/abs/2402.05120

**Saturation, the honest caveat.**
- Tight (2024), Saturation: An Overworked and Misunderstood Concept? The stopping rule is contested and often used loosely. Treat it as a heuristic, not proof of completeness. https://journals.sagepub.com/doi/10.1177/10778004231183948
- Active-learning analog: query where the model is least certain, and vary queries to avoid redundancy (uncertainty, representativeness, diversity). Same shape as the sweep.

## Research Grounding, Third Pass (2026-09-30)
A check against work the first two passes did not cite. All seven papers were read at abstract level.

**What changed the protocol.**
- Choi, Zhu & Li (2025), Debate or Vote, NeurIPS 2025. Majority voting accounts for most of multi-agent debate's gain, and debate alone does not improve expected correctness. Why debate is out. https://arxiv.org/abs/2508.17536
- Smit et al. (2024), Should We Be Going MAD? Debate does not reliably beat self-consistency or ensembling, though tuned agreement levels can. https://arxiv.org/abs/2311.17371
- Loo (2025), Self-Consistency Is Losing Its Edge. On Gemini 2.5, a 0.4% gain on HotpotQA across 20 samples and 1.6% on MATH-500. One single-author preprint; why voting is scoped to the shaky points. https://arxiv.org/abs/2511.00751
- Jiang et al. (2025), Artificial Hivemind, NeurIPS 2025 Datasets and Benchmarks. A model repeats itself, and different models produce strikingly similar outputs. Why saturation is checked against an outside list. https://arxiv.org/abs/2510.22954
- Zhang et al. (2025), Verbalized Sampling. Mode collapse traced to typicality bias in preference data; asking for a set of responses with probabilities raised diversity 1.6 to 2.1 times in creative writing without loss of factual accuracy. Why steps 1 and 3 ask for probabilities. https://arxiv.org/abs/2510.01171
- Shao et al. (2024), STORM, NAACL 2024. Perspectives discovered from related articles, then questions put to a source-grounded expert; a 25% absolute gain in organization and 10% in coverage breadth over an outline-driven retrieval baseline. Why perspectives are chosen per topic. https://arxiv.org/abs/2402.14207

**What confirmed it.**
- Kamoi et al. (2024), When Can LLMs Actually Correct Their Own Mistakes?, TACL. Prompted self-correction has no demonstrated success outside tasks unusually suited to it, and external feedback works. The guardrail stands. https://arxiv.org/abs/2406.01297

**Still open.** Whether a model can judge its own saturation. No source was found in this pass or in the 2026-08-25 research-method pass.

## Relation to the Research Workflow
This is the upstream phase. It exhausts and structures what a model already holds and flags where it doesn't. Two things consume its output:
- [The research protocol](02-research.md), the sourced-research workflow. Run this sweep first to build the map and locate gaps, then let the research protocol source the gaps with primary material. This sweep is the input to its step 2 (source map).
- A deep-research tool or agent that fans out web searches and synthesizes from external sources. Point it at the gaps this surfaces.

They are complementary, not redundant: this finds what's missing, those go get it.
