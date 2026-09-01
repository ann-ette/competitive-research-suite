# Developer marketing

Marketing to developers when the developer is the buyer, the evaluator, or the person who has to be convinced before the buyer will sign. Page 16 covers campaign structure and page 10 covers demand generation; both hold when the audience is technical, and the weight moves. This page covers what moves: docs as the evaluation surface, trust as a spendable balance, standards and open source as distribution, and the specific overclaim that costs more here than anywhere else.

Last checked: 2026-08

**Evidence note, read first.** The sourced material behind this page comes from a research pass on developer audiences and go-to-market benchmarks held outside this package; its two pages carry 92 bibliography entries between them and the findings are general. **Most of the practitioner guidance below is labeled opinion in that source and stays labeled here.** It is directionally consistent across independent practitioners and it is not data. A sourced pass on developer marketing as its own discipline is owed.

## Core concepts

### Docs are the evaluation surface

A developer evaluating a tool reads the reference and then tries it. Marketing pages get skimmed on the way through, which makes a docs page that cannot answer the evaluation question the actual conversion failure, sitting in a place no marketing dashboard is watching. **[reasoning]**

The practical consequence for campaign work: the docs are a launch surface with a slow decay rate under page 16's ordering, and they get built before the loud surfaces point at them.

### Trust is a balance you spend

Heavybit frames marketing to developers as trust engineering: help developers solve the problem, without gating the content and without oversimplifying it (Heavybit, n.d., opinion). The framing is useful because it makes the currency legible. Gated content, a benchmark with a hidden config, and a claim that does not survive a ten-minute test each take a withdrawal, and the balance is what makes the next launch land.

**The proof has to be runnable.** A claim a developer can check in ten minutes beats a claim they have to take, and this is the single highest-leverage move available in the step 2 thesis on page 16.

### Overclaiming is the repeated own-goal

The robotics benchmark page identifies undisclosed capability inflation as the most repeated credibility failure in its category: Tesla's We Robot event (2024-10-10) demonstrated Optimus units that were human-teleoperated without disclosure (TechCrunch, 2024-10-14), and later Tesla videos carried explicit "AI, NOT tele-operation" captions (Interesting Engineering, 2025-10). 1X's NEO launch (2025-10-28) drew tens of millions of views and then the teleoperation arrangement became the story rather than the product (Tom's Guide, 2025-10/11; The Robot Report, 2025-11).

That generalizes cleanly and it is the reason to keep it on this page. A technical audience will find the gap between the claim and the artifact, the finding travels faster than the original claim, and the correction becomes the thing the category remembers. **Explicit disclosure of what is and is not automatic reads as credibility to this audience and as hedging to nobody in it.**

### Standards and open source are distribution

An open standard recruits competitors as a distribution channel. Anthropic released the Model Context Protocol on 2024-11-25; OpenAI and Google adopted it within six months, and the first-anniversary post reported 10,000+ public servers and 97M+ monthly SDK downloads (MCP blog, 2025-11-25). MCP was donated to the Linux Foundation in December 2025, with neutral governance functioning as a trust move (Anthropic, 2025-12).

Three adjacent patterns from the same source, each sourced and each generalizable:

- **Own the format, ship a cheap reference implementation.** Hugging Face's LeRobot pairs a dataset and format standard with an open low-cost device, and ran a worldwide hackathon with 3,000+ registrants across 100+ sites on sponsor money, with AMD hosting local events (Hugging Face, 2025-06; AMD, 2025).
- **Free education converts users into practitioners.** LangChain runs an academy alongside the library, with the hosted layer as the paid product (Contrary Research, 2025; Sacra, 2025).
- **Frictionlessness is itself the marketing asset.** Ollama grew on a one-command install and community integrations with close to no formal marketing.

**The license is the brand promise, and walking it back is a public event.** Adafruit called out Arduino Pro's hardware as not open source (2021-07-07), Hackaday declared Prusa's open-hardware position dead with Core ONE (2024-11-20), and Adafruit ran a lawyer's critique of Prusa's replacement license (2026-03-19). All three are opinion pieces and that is the point: the enforcement mechanism here is community writing, and it does not expire.

### The community funnel, and its failure modes

Peter Levine's a16z model runs community → users → buyers as three nested funnels (a16z, 2020, opinion). The failure modes named in the source are the useful half: **user-buyer mismatch**, where the people who love it are not the people who sign, and **a commercial offering that violates community trust**. Hosted platforms have largely replaced pure open-core as the default monetization.

### Where the audience already is

Robotics communities organize around conferences, forums, and package standards more than social platforms, and the source's guidance is to sponsor and speak where the audience already gathers before building an owned event (Open Robotics Discourse, 2025). The transferable form: **an owned channel is the expensive option and it earns its place only after the borrowed ones are exhausted.**

The counterweight, also sourced: founder accounts outperform company accounts everywhere the robotics benchmark saw both tried. For a technical audience the named engineer carries what the brand account cannot, which makes the first marketer's leverage arming the founder rather than substituting for them.

### Once it is deployed, operational metrics replace stunts

Agility Robotics markets on totes moved, hours run, and an hourly rate through case studies and trade shows (Agility Robotics, 2025; Contrary Research, 2025-26). Boston Dynamics, which built its brand almost entirely on YouTube at very low cost by its own founder's account (Raibert, VentureBeat interview, ~2021), deliberately skipped stunts at CES 2026 and showed Atlas sorting parts (Gasgoo, 2026, opinion).

The pattern is a lifecycle. Spectacle earns attention pre-deployment and stops working once buyers can ask what it does in production, and the metric that replaces it has to be operational.

## How strong teams do it

They ship the docs before the announcement, and they treat a failed evaluation in the docs as a conversion loss rather than a support ticket.

They put a runnable artifact behind every claim. A repo, a sandbox, a one-command install, a benchmark with the config published.

They disclose the boundary of what works. What is automatic, what is manual, what is in early access, and what the known failure cases are.

They publish their ecosystem numbers on a rhythm. OpenAI's annual developer tentpole with an ecosystem-metrics slide compounds into press shorthand for momentum (Latent Space, 2025-10, opinion).

They arm the founder or the lead engineer as the channel, and they measure the community funnel separately from the user funnel so that a user-buyer mismatch is visible before it is a revenue problem.

They read the license and the governance as marketing surfaces, because the community does.

## Common mistakes

- **A marketing page that a developer has to leave to evaluate.** The docs are where the decision happens.
- **Gating the thing that would have built the trust.** An email wall in front of a technical answer converts a would-be advocate into someone who found the answer elsewhere.
- **Overclaiming autonomy, performance, or completeness.** The audience checks, and the correction becomes the story.
- **A benchmark with an unpublished config.** Read as a claim that the config would not survive publication.
- **Building an owned community before exhausting the ones that exist.** Expensive, slow, and usually a worse version of a forum the audience already reads.
- **The company account doing the founder's job.** Every benchmark that tried both found the founder account outperformed.
- **Measuring the community funnel as if it were the user funnel.** Hides the user-buyer mismatch until it shows up in revenue.
- **Walking back an openness commitment quietly.** There is no quiet version.
- **Running stunt marketing past deployment.** Once buyers can ask about production, spectacle reads as evasion.

## Worked example

**OwnMind.** The engine under Tapestry, open source under MIT, with the proprietary experience layer above it. The three-layer structure is exactly the shape the a16z nested-funnel model describes, and the failure mode it warns about is the live risk: the people most drawn to a local-first sovereign engine are the people least inclined to pay for a hosted anything, which is user-buyer mismatch by construction.

The trust-engineering read says the sovereignty stance is the marketing. No telemetry, no proxied inference, no hidden cloud calls, and the cloud-egress feature gate in the codebase is a runnable proof of exactly that. A developer can read the gate. That is the ten-minute check, and it is worth more than any page describing the position.

The license-as-brand-promise finding is the binding constraint rather than a nice-to-have. An engine marketed on sovereignty and open governance has committed publicly, and the Arduino and Prusa cases are what the walk-back costs when the community writes it up.

The overclaim rule applies to build state. In my own workspace a generated built-state block exists because prose about what is built goes stale and misleads, and the same discipline governs external claims: say what runs, say what is specified and unshipped, and scope the sentence to what is true at publish time.

The channel read says the founder is the channel and the standard is the distribution. An engine that speaks a protocol other tools already implement borrows their reach, and that is the MCP finding applied one layer down.

## Interview fluency

**Terms to know cold:**

- **Trust engineering.** Heavybit's framing of developer marketing: solve the problem for them, ungated and unsimplified. Trust is a balance that gets spent.
- **The runnable proof.** A claim a developer can verify in ten minutes. Beats any claim they have to accept.
- **Docs as the evaluation surface.** The developer's real decision page, and the one no marketing dashboard is watching.
- **Nested funnels.** a16z's community → users → buyers. Three funnels, measured separately.
- **User-buyer mismatch.** The people who adopt it are not the people who sign. The named failure mode of the open-source funnel.
- **Open standard as distribution.** MCP: OpenAI and Google adopted it within six months, 10,000+ public servers and 97M+ monthly SDK downloads at one year, then donated to the Linux Foundation for neutral governance.
- **Reference implementation as top of funnel.** Own the format, ship something cheap that uses it. LeRobot and Reachy Mini.
- **The license is the brand promise.** Walking back openness is a public event enforced by community writing. Arduino Pro, Prusa Core ONE.
- **Disclosure as credibility.** Explicit statements about what is automatic and what is not. The undisclosed-teleoperation cases are what the alternative costs.
- **Operational metrics replace stunts.** Post-deployment, the marketable number is what it does in production.
- **Founder as channel.** Founder accounts outperformed company accounts in every benchmark case that ran both.
- **Pi-shaped marketer.** MKT1's first-hire profile: expert in two functions, usually product marketing plus growth, carrying marketing to roughly Series B.

**Likely questions and talking points:**

*How is marketing to developers different?* The buyer evaluates by doing rather than by reading, so the docs are the real conversion surface and the marketing site is what they pass through on the way. The framing I use is Heavybit's, that this is trust engineering, and what makes it concrete is that trust is spendable: a gate in front of a technical answer, a benchmark with a config you did not publish, or a claim that does not survive ten minutes of poking each takes a withdrawal, and you need the balance for the launch that matters. So the highest-leverage thing I can put behind a claim is something runnable. A repo, a sandbox, a one-command install.

*What is the most common way developer marketing fails?* Overclaiming, because this audience checks and then writes it up. The clearest cases are in robotics, where undisclosed teleoperation has been the repeated own-goal: Tesla's We Robot event in 2024 ran teleoperated units without saying so, and later Tesla videos were captioned "AI, not tele-operation," which is the correction becoming the message. 1X had the same problem when the review cycle made the teleop arrangement the story instead of the robot. It generalizes past robotics. Explicitly stating what is automatic, what is manual, and what is in early access reads as credibility to a technical audience, and there is nobody in that audience who reads it as hedging.

*How do you think about open source as a go-to-market motion?* As three nested funnels, community to users to buyers, which is Peter Levine's a16z model, and I would measure them separately because the failure mode is user-buyer mismatch. The people who love a free local-first tool are often exactly the people who will never buy a hosted one, and that is invisible until it is a revenue problem. The other thing I would take seriously is that the license is a public commitment. When Arduino and Prusa were seen to walk back openness, the enforcement came from Adafruit and Hackaday writing it up, and that kind of coverage does not expire.

*Can you give an example of a standard used as distribution?* MCP. Anthropic published it in November 2024, OpenAI and Google both adopted it within six months, and by the first anniversary it had over ten thousand public servers and more than 97 million monthly SDK downloads. Then it was donated to the Linux Foundation, which converts the standard from one company's asset into neutral infrastructure and is what makes competitors comfortable building on it. The move recruits your competitors as your distribution channel, and the cost is giving up control of the thing.

*Where do you spend first with a developer audience?* Where they already are, before building anything owned. Robotics is instructive because that community organizes around conferences, forums, and package standards more than social platforms, so sponsoring and speaking beats standing up your own event and waiting. The owned channel is the expensive option and it earns its place after the borrowed ones are working. The other thing I would do early is arm the founder or the lead engineer as the channel, because every benchmark I have seen that ran both a founder account and a company account found the founder account outperformed. My leverage as the first marketer is making that person effective rather than replacing them.

## Signals to watch

In a daily scan, the items that belong on this page rather than on 10 or 16:

- **Standards adoption events**: a protocol picked up by a competitor, donated to a foundation, or forked. The distribution consequence is the story.
- **License changes and relicensing backlash**, and who wrote it up. The community-enforcement pattern is the reusable finding.
- **Capability-claim corrections**: a demo shown to be assisted, a benchmark with a disputed config, a retracted performance number.
- **Docs and DX research with a stated method.** Rare, and it would upgrade the largest [reasoning] block on this page.
- **Developer-population and community-size data** with a disclosed counting method, including which counts are login-walled.
- **First-marketing-hire and DevRel practitioner writing.** Currently the entire evidence base for the role guidance here, and all of it opinion.

## Sources

1. Marketing to developers is not hard. Heavybit. https://www.heavybit.com/library/article/marketing-to-developers-is-not-hard
2. Open source: from community to commercialization. Peter Levine, a16z, 2020. https://a16z.com/open-source-from-community-to-commercialization/
3. Introducing the Model Context Protocol. Anthropic, 2024-11-25. https://www.anthropic.com/news/model-context-protocol
4. One year of MCP. MCP blog, 2025-11-25. https://blog.modelcontextprotocol.io/posts/2025-11-25-first-mcp-anniversary/
5. Donating the Model Context Protocol and establishing the Agentic AI Foundation. Anthropic, 2025-12. https://www.anthropic.com/news/donating-the-model-context-protocol-and-establishing-of-the-agentic-ai-foundation
6. LeRobot worldwide hackathon. Hugging Face, 2025-06. https://huggingface.co/LeRobot-worldwide-hackathon
7. AMD open robotics hackathon recap. AMD, 2025. https://www.amd.com/en/developer/resources/technical-articles/2025/amd-open-robotics-hackathon-recap.html
8. LangChain business breakdown. Contrary Research, 2025. https://research.contrary.com/company/langchain
9. LangChain valuation and metrics. Sacra, 2025. https://sacra.com/c/langchain/
10. ollama/ollama. GitHub. https://github.com/ollama/ollama
11. Tesla Optimus bots were controlled by humans during the We Robot event. TechCrunch, 2024-10-14. https://techcrunch.com/2024/10/14/tesla-optimus-bots-were-controlled-by-humans-during-the-we-robot-event/
12. Optimus robot performs kung fu moves. Interesting Engineering, 2025-10. https://interestingengineering.com/innovation/optimus-robot-performs-kung-fu-moves
13. The NEO home robot that's breaking the internet promises to change the world, but there's one huge problem. Tom's Guide, 2025-10/11. https://www.tomsguide.com/home/smart-home/the-neo-home-robot-thats-breaking-the-internet-promises-to-change-the-world-but-theres-one-huge-problem
14. Teleop, not autonomy, is the path for 1X's NEO humanoid. The Robot Report, 2025-11. https://www.therobotreport.com/teleop-not-autonomy-the-path-for-1x-neo-humanoid/
15. Digit moves over 100,000 totes. Agility Robotics, 2025. https://www.agilityrobotics.com/content/digit-moves-over-100k-totes
16. Agility Robotics business breakdown. Contrary Research, 2025-26. https://research.contrary.com/company/agility-robotics
17. Boston Dynamics CEO on the company's top 3 robots, AI and viral videos. VentureBeat, ~2021. https://venturebeat.com/ai/boston-dynamics-ceo-on-the-companys-top-3-robots-ai-and-viral-videos
18. When Atlas stops dancing. Gasgoo, 2026. https://autonews.gasgoo.com/articles/news/when-atlas-stops-dancing-an-internet-famous-robotics-companys-shift-from-hype-to-substance-2009603713771872256
19. Arduino Pro hardware is not open-source hardware. Adafruit, 2021-07-07. https://blog.adafruit.com/2021/07/07/arduino-pro-hardware-is-not-open-source-hardware/
20. With Core ONE, Prusa's open source hardware dream quietly dies. Hackaday, 2024-11-20. https://hackaday.com/2024/11/20/with-core-one-prusas-open-source-hardware-dream-quietly-dies/
21. Prusa's open community license is neither open nor for the community. Adafruit, 2026-03-19. https://blog.adafruit.com/2026/03/19/prusas-open-community-license-is-neither-open-nor-for-the-community-a-lawyer-explains-why/
22. Full ROSCon 2025 program released. Open Robotics Discourse, 2025. https://discourse.openrobotics.org/t/full-roscon-2025-program-released/49264
23. DevDay 2025: developers as the distribution layer. Latent Space, 2025-10. https://www.latent.space/p/devday-2025
24. How to hire your first marketer. Emily Kramer and Kathleen Estreich, MKT1, 2021-01-28, updated 2024-09. https://newsletter.mkt1.co/p/how-to-hire-your-first-marketer
25. The first 90 days in DevRel. swyx, dx.tips, ~2022. https://dx.tips/first-90
26. Finding success with your first DevRel hire. Common Room, ~2023. https://www.commonroom.io/blog/finding-success-with-your-first-devrel-hire/

**Source-quality note.** Items 1, 2, 18, 19, 20, 21, 23, 24, 25, and 26 are opinion or practitioner writing, labeled as such in the underlying research page. The role and first-90-days guidance rests entirely on that tier. Items 3, 4, 5, 6, and 15 are primary. Everything about the robotics cases is secondary press coverage with the primary announcement also on file.

## Related

- [Campaigns and channels](16-campaigns-and-channels.md)
- Content and demand generation (page 10 of the larger wiki, not in this package)
- Go-to-market strategy (page 05 of the larger wiki, not in this package)
- Customer and market understanding (page 04 of the larger wiki, not in this package)
- [Naming](17-naming.md)
- [The launch campaign protocol](../protocols/05-launch-campaign.md), step 7, is the binding version of this page's campaign guidance.
- The sourcing is a developer-marketing research pass held outside this package: two pages, 92 bibliography entries, general findings filed under a product heading.
