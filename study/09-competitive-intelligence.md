# Competitive intelligence and analyst relations

Competitive intelligence (CI) is the discipline of legally and ethically collecting, analyzing, and distributing intelligence about competitors and the market so the business can act on it. Analyst relations (AR) is the related practice of engaging research-firm analysts to earn third-party validation. For a product marketer, these are the same job seen from two sides: knowing the field cold, and getting outsiders who shape buying decisions to repeat your version of it.

Last checked: 2026-06 · amended 2026-08-25 (eleven corrections and additions from the competitive-research method pass; every one is marked in-line as **Amended 2026-08-25**. Evidence: [`research/competitive-research-methods.md`](../research/competitive-research-methods.md). Execution detail moved to the new page 15.)

> **Where this page stops.** 09 owns the frameworks and the program shape. The execution layer (how the set is drawn, what each source type can carry, how a claim gets verified, how the record is filed and refreshed, and what the law requires before a comparison ships) is [15 Competitive research execution](15-competitive-research-execution.md), and the binding process is [the competitive research protocol](../protocols/04-competitive-research.md).

## Core concepts

CI sits at the center of a triangle. Market and competitor research feeds sales enablement, enablement feeds win/loss learning, and win/loss feeds back into positioning. Crayon's framing of the stakes is the line most often quoted: "a whopping 68% of sales opportunities are competitive." (Crayon's underlying State of Competitive Intelligence report phrases the stat as competitors being involved in 68% of deals; the blog renders it as sales opportunities.) That is why CI has moved from a once-a-year slide deck to a living program. The job is not to know everything about every competitor. It's to surface the few insights that change how a rep handles the next deal and how the company positions itself.

**Amended 2026-08-25: the buyer's set is small, early, and pre-formed, and the CI roster does not match it.** 6sense's 2025 B2B Buyer Experience Report (n≈4,000, median deal $200,000 to $300,000) found buyers carrying a median of 3.6 vendors on their Day One list, evaluating 5.1 in total, and purchasing from the Day One list 95% of the time. 85% had prior experience with the vendor they chose and 77% contacted that winner first. TrustRadius's 2026 B2B Buying Disconnect (n=1,862) reports 83% shortlisting three or fewer products and 79% already knowing the product they bought.

Now put that beside Crayon's 2026 report, where 80% of CI teams track thirty or fewer competitors (most between eleven and thirty) and only 36% of intelligence comes from win/loss interviews. A program holds twenty names, a buyer holds five, and the roster does not say which five. That arithmetic is the argument for an **inclusion test**: a name enters the competitive set only when there is evidence a buyer considered it, and capability to compete is not evidence. It is also the operational form of the phantom-competitor warning further down this page. Mechanics and the three-tier roster on page 15. (The Crayon figures are a vendor survey with no disclosed sample size; treat them as medium confidence.)

### Building a CI program

A working program has three layers.

- **Collection.** Pull from primary sources (your own win/loss interviews, field intel from reps, customer conversations) and secondary sources (competitor websites, pricing pages, job postings, G2 reviews, earnings calls, analyst reports).
- **Analysis.** Turn raw signal into a point of view. Not "Competitor X shipped feature Y," but what it means and what a seller should do about it.
- **Distribution.** Get that point of view into the workflow where it's needed, usually battlecards and Slack alerts.

Crayon's framing is useful here: the CI team should act as a connector that tracks who is winning against each competitor and spreads that learning, not as the sole expert who hoards intel.

**Amended 2026-08-25: what survives when you strip the vendor maturity model.** The staged CI-maturity ladders published by Klue and Crayon are shaped by the tool they sell, and most of the rungs are platform features. Five things hold without buying anything: a **named owner**, a **fixed cadence** with a stated trigger for off-cycle updates, intelligence sourced from **your own calls first** (win/loss and field intel outrank any monitoring feed), a **declared consumer** for every artifact (who reads it and what they do differently), and **one pre-declared KPI** chosen before the program starts. A program missing the declared consumer produces the Hill and Westbrook failure below at scale.

**Amended 2026-08-25: analysis needs a decision attached, or it becomes a list.** Hill and Westbrook studied SWOT use at fifty companies (*Long Range Planning* 30(1), 1997, pp. 46-52) and found lists averaging more than twenty factors and often more than forty, with no prioritization, no verification of any individual factor, and no evidence that any list fed a later stage of the strategy process. The finding generalizes to any competitive artifact produced without a named decision behind it: an unbounded list has no stopping rule and no consumer, so it grows until effort runs out and then sits. Write the decision the research serves in one sentence before collection starts.

Tooling has consolidated around a few platforms. **Klue** and **Crayon** are the two best-known dedicated CI platforms. Both aggregate competitor monitoring, host dynamic battlecards, and increasingly fold in win/loss. Klue acquired **DoubleCheck Research** (a win/loss analysis firm) in January 2022 and productized it as Klue Win-Loss, combining deal-level intel with battlecards in one place. **Kompyte** is often positioned for automated mid-market tracking. Forrester now evaluates this whole space in a dedicated Market and Competitive Intelligence Platforms Wave (Q4 2024), a signal that CI tooling is a recognized category.

### Battlecards: structure, landmines, and staleness

A battlecard is the bridge between intelligence and execution. Klue's recommended structure has four core sections: your product's key features and benefits, the competitor's, common buyer objections with handling guidance, and talk tracks for competitor-specific questions.

Klue layers a **FIA** model on each insight:

- **Fact.** The competitive context.
- **Impact.** Why it matters and when a seller uses it.
- **Act.** The talk track or follow-up.

Klue stresses three properties for any insight on the card: context (never isolated facts), charge (positively or negatively framed language, not neutral description), and specificity (concrete metrics, not vague comparisons). Crayon's version adds a "Why We Win" block (top three validated differentiators), competitor strengths paired with seller responses, recent wins by segment, recent field intel, and a landmines section.

**Landmines** (some teams say "traps") are the depositioning tactic. A landmine is a pointed but indirect question or statement that leads a prospect to discover a competitor's weakness themselves, rather than you attacking the competitor head-on. Klue is explicit: "laying a landmine isn't about starting a war with your competitor, but rather having your prospect come to their own conclusion about their weaknesses." Two common formats: a provoking question with a "why we ask" rationale, or a power statement that frames the competitor's gap and lets the buyer connect the dots. The words "traps" and "landmines" are used interchangeably across vendor sources, so treat them as one tactic rather than over-engineer a distinction.

The number-one failure mode is staleness. Klue puts it bluntly: "The moment a seller finds something out-of-date or incorrect in your battlecard, all trust is out the window." A living battlecard has a named owner, a steady intake of field intel, and updates tied to competitor moves (pricing changes, feature sunsets, repositioning) rather than to the calendar. Different roles consume them differently. BDRs lean on discovery and early objection handling, AEs on late-stage competitive positioning, so mature programs ship role-specific variants instead of one universal card.

**Amended 2026-08-25: do not quote a decay rate.** The claim that battlecards or competitive intelligence go stale in about ninety days circulates constantly and traces only to CI vendor blog content with no stated method, no sample, and no definition of stale. The qualitative point above stands. The number does not exist. Set cadence from the observable rate of change in each source instead, and record it as a four-column table (what · how often · where · **what would change my mind**), where the fourth column is what turns a refresh into a check rather than a re-read. Also: amend a changed fact with a dated in-line note rather than overwriting it, and keep `last_verified` per competitor, since a document-level date claims freshness for the least-checked fact on the page.

### Win/loss analysis

Win/loss closes the gap between what you think drives deals and what buyers actually say. The mechanics: interview recent decision-makers (both wins and losses) shortly after the decision, roughly two to four weeks out, while memory is fresh but emotion has cooled. Ask open questions about the evaluation, the alternatives considered, what nearly changed the outcome, pricing perception, and the moment they decided.

An underweighted competitor here is "no decision." April Dunford notes that in enterprise software, vendors "typically lose between 20% and 30% of deals to 'no decision,'" meaning the real competitor is often the customer's status quo, not a rival vendor. (Dunford cites this figure from Strategic Dynamics rather than originating it; the 20 to 30% range is hers to endorse, and shouldn't be conflated with the higher 40%-plus no-decision numbers from other studies.)

**Amended 2026-08-25: state the range and the reason for it, and stop picking a point estimate.** Published no-decision rates run from roughly 20% up to the 40 to 60% band associated with the JOLT research (Dixon and McKenna, *The JOLT Effect*, 2022), and most of the spread is a **denominator problem**: some counts are of all opportunities entered, some of qualified opportunities, some of late-stage forecast deals. JOLT also separates **indecision**, a buyer who wants to act and cannot commit, from **status-quo preference**, which is a different failure with a different remedy, and popular summaries collapse the two. Say "20 to 60% depending on what is being counted," name the denominator, and treat the distinction as the useful part.

**Amended 2026-08-25: one widely repeated win/loss figure is untraceable.** The claim that 48% of buyers cite price as the deciding factor while only 23% of sellers know it, usually attributed to Primary Intelligence, could not be traced to a published report with a stated sample or method. Do not quote it. It is recorded here so the next pass does not re-find it and assume it checked out.

The central design choice is **internal versus third-party**. The hard constraint, agreed across practitioners, is that the sales rep who owned the deal should never run the interview. Buyers sugarcoat feedback to the person they just said no to. Internal product marketing or RevOps can credibly run interviews for smaller or high-volume deals. An independent third party (Clozd, Klue, or a research firm) tends to get more candid feedback and is worth reserving for strategic deals. A common operating model is third-party for large strategic deals and internal for the long tail. For a sample big enough to drive roadmap or pricing decisions, aim for a meaningful number of interviews spread across deal sizes, segments, and outcomes rather than a handful of anecdotes. (Buyers being more candid with a neutral third party is the supportable claim; specific candor-lift multipliers and response-rate ranges circulate widely but lack a locatable primary study, so don't quote them.)

### Positioning and the trap framework

April Dunford's positioning work reframes the competitive question. Her framework rests on five components: competitive alternatives, differentiated capabilities, differentiated value, best-fit customers, and market category. She deliberately says "competitive alternatives" rather than "competitors." The test question is: what would a customer do if your offering didn't exist? Often the answer is a spreadsheet, a manual process, or doing nothing, which is why the status quo is usually your first competitor.

She names two traps. The first is misidentifying the alternatives, assuming the competition is a rival product when it's really inertia. The second is positioning against "phantom competitors," companies that theoretically could compete but never actually show up on buyers' shortlists. "Just because a company could compete with you doesn't mean they ever will," she warns. Positioning against invisible rivals waters down your real differentiation. Her memorable illustration: the true competitor to a Bugatti isn't a Ferrari or a Porsche, it's a yacht, because at that price the buyer is purchasing status, not transportation.

### Primary versus secondary intelligence, and ethical CI

CI distinguishes **primary intelligence** (collected directly: win/loss interviews, conversations with prospects, your own field reps, customer references) from **secondary intelligence** (already published: websites, pricing pages, reviews, filings, analyst reports). Primary is harder to get and more defensible. Secondary is fast and cheap but available to everyone.

Ethical CI is bounded by the **SCIP (Strategic and Competitive Intelligence Professionals) Code of Ethics**, the industry-standard guideline set. Its provisions include complying with all applicable laws (domestic and international) and accurately disclosing all relevant information, including your identity and organization, before interviews. The practical effect is a bar on misrepresentation. The line is bright: posing as a customer to extract a competitor's roadmap is a violation; reading a competitor's public pricing page is not.

**Amended 2026-08-25: ethics is one of two gates, and the contract is the other.** Even a fully disclosed, honest signup for a competitor's free trial is frequently barred by the terms you accept. Salesforce's Master Subscription Agreement bars competitors from accessing the services. Atlassian's Cloud Terms of Service bar use of the products "for competitive analysis." **DeWitt clauses**, which prohibit publishing benchmark results without vendor approval, remain live in database and enterprise-software licences, and SPEC and TPC both publish fair-use rules governing how their results may be quoted. So the two doors close on each other: the contract bars the honest signup and SCIP bars the dishonest one. Read the terms before creating any account, and if hands-on evaluation is closed, record the block by name and source the claim from published documentation instead.

**Amended 2026-08-25: publication has its own gate, and it is more permissive than most teams assume and stricter about blank cells.** **16 CFR §14.15**, the FTC's Statement of Policy Regarding Comparative Advertising, states that comparative advertising which is truthful and non-deceptive is a source of important information, that industry codes should not restrain the naming of competitors, and that the substantiation standard for a comparative claim is **the same** as for any other advertising claim, with no higher bar. Naming a competitor is encouraged. Holding the proof is the cost.

- **Lanham Act §43(a)** is the private right of action for a false or misleading statement of fact about a competitor's product in commercial advertising. The elements are laid out in *Pizza Hut, Inc. v. Papa John's International, Inc.*, 227 F.3d 489 (5th Cir. 2000): a false or misleading statement of fact, actual deception or a tendency to deceive, materiality, interstate commerce, and injury. *Pizza Hut* also draws the puffery line, finding "Better Ingredients. Better Pizza." non-actionable standing alone while holding that the surrounding factual comparisons changed the analysis.
- **NAD** (BBB National Programs' National Advertising Division) is the practical venue: faster and cheaper than litigation, and public. **Case #7304, Deel v. Rippling (2024-08-08)** recommended discontinuing comparison-table claims where checkmarks and blank cells implied a competitor lacked a feature **without affirmative evidence for the absence**, plus "market leader," "#1 Global HR platform," and "Teams prefer Deel over Rippling." **SharkNinja (2024-11-24)** went past the individual claims to the **category boundary itself**, finding the comparison set drawn so as to make the superiority claim true. Together: a blank cell is an affirmative claim, and the reviewed set is a claim that needs stating beside the table.
- **Nominative fair use** permits using a competitor's trademark to refer to that competitor, under the three-part test from *New Kids on the Block v. News America Publishing, Inc.*, 971 F.2d 302 (9th Cir. 1992): the product is not readily identifiable without the mark, only as much of the mark as is reasonably necessary is used, and nothing suggests sponsorship or endorsement.
- **Outside the US**, EU Directive 2006/114/EC permits comparative advertising subject to conditions including objective comparison of material, relevant, verifiable, and representative features. National implementations vary.

A claim that cannot be substantiated does not ship softened. It comes out.

### Analyst relations

Analyst relations is the proactive engagement of research-firm analysts (Gartner, Forrester, IDC) to build advocacy and third-party validation. You don't need to be a paying client to brief them. The flagship outputs:

- **Gartner Magic Quadrant** plots vendors on a 2x2. The horizontal x-axis is completeness of vision (how differentiated and future-proof the strategy is) and the vertical y-axis is ability to execute (the ability to take the product to market and serve customers), producing Leaders, Challengers, Visionaries, and Niche Players.
- **Forrester Wave** scores vendors on a current-offering axis and a strategy axis, with a third dimension shown by marker size. Don't memorize a fixed left-right mapping for the Wave. Gartner and Forrester use opposite axis conventions, individual Wave reports have placed the same two axes differently over time, and each report carries its own legend. The historical default for marker size was market presence, but as of mid-2024 some Waves use marker size to represent customer feedback instead, so read the legend of the specific report.
- **Forrester Tech Tide** is different in kind. It assesses the maturity and business value of a category of technologies and tells clients whether to Experiment, Invest, Maintain, or Divest, rather than ranking named vendors.

Two engagement modes matter. A **briefing** is you presenting to the analyst (your story, roadmap, differentiators). It's outbound and vendor-initiated. An **inquiry** is a paid client asking the analyst a question, which is where analysts recommend vendors to buyers, so influencing inquiries is a big part of AR's value. To land in a Wave or MQ, start the relationship early. The guidance is to introduce the company six months to a year before the next anticipated update, because inclusion is invitation-only and driven by criteria plus established reputation. Expect a real resource commitment: detailed questionnaires, demos mapped to evaluation criteria, and coordinated customer references, often dozens of hours of executive time.

### Peer-review sites and community intelligence

Analyst firms are no longer the only validators. **G2** runs a Grid that plots products on customer satisfaction (from reviews) against market presence, sorting them into Leaders, High Performers, Contenders, and Niche, effectively a crowd-sourced quadrant. Peer reviews now sit early in the buying journey, and Gartner's B2B buying research indicates a large majority of software buyers consult peer-review sites before talking to sales.

**Amended 2026-08-25: know what a Grid position is made of before citing one.** G2's **Market Presence** score is a composite that includes web presence and **pay-per-click spend**, domain authority, employee count, social following, and revenue estimates. A vendor that buys more ads moves right on the Grid. Review volume is also materially shaped by vendor-run review campaigns, which G2 permits and which are standard practice. Use the Grid for direction and volume, never for a factual claim about a product's capability.

**Amended 2026-08-25: Forrester's methodology change has a date.** Forrester replaced the **Market Presence** scoring category with **Customer Feedback**, effective for Waves published on or after **2024-07-01**. That is the change the marker-size note above gestures at. It is a real improvement, and the customer feedback is still gathered from **vendor-supplied references**, so a selection effect remains.

**Amended 2026-08-25: the shortlist is increasingly formed inside an AI assistant.** G2's 2026 buyer research reports **AI chatbots at 37%** as a software discovery source against **review sites at 38%**, and that **51% of buyers now begin a search with an AI chatbot, up from 29% in April 2025**. TrustRadius's 2026 report puts analyst reports at **13%**. Both are vendor-published and directionally consistent. The consequence for CI: what the public corpus says about a category is increasingly the first thing a buyer reads, which raises the stakes on comparison pages, docs, and third-party write-ups, and lowers the reliability of any single review site as a proxy for buyer attention. This is the same surface page 13 covers as GEO/AEO, arriving from the competitive side. **Community intelligence** extends this to where buyers actually talk: Reddit (G2 and Reddit announced a partnership to bring vendor presence into Reddit communities), Slack groups, and review-site sentiment, which tools can monitor and route into Slack, Linear, or Jira for the CI and product teams. For a modern PMM, peer-review and community signals belong in the same CI program as battlecards and win/loss, because they shape the shortlist before any seller is in the room.

## How strong teams do it

Strong teams treat CI as a living program, not a quarterly artifact. There's a named owner, a steady intake of field intel, and a distribution habit (battlecards plus Slack alerts) that lands the insight inside the workflow where a rep decides what to say next.

They analyze, they don't just monitor. Anyone can forward a competitor's pricing change. The value is the so-what: what it means, which deals it touches, and the talk track that follows. The CI lead acts as a connector who spreads winning patterns across the team rather than hoarding intel.

They run win/loss honestly. The rep who lost the deal never interviews the buyer. Strategic deals go to a neutral third party for candor; the long tail runs internally. Findings flow back into positioning and the roadmap, not just into a quarterly readout.

They start AR early and resource it. The relationship with a Gartner or Forrester analyst begins six months to a year before an evaluation, with questionnaires answered carefully, demos mapped to the published criteria, and customer references lined up. They influence inquiries, where buyers actually get steered, not just the once-a-year report.

They source ethically and say so. Identity disclosed before every interview, no pretexting, public sources used as public sources. It protects the brand and it keeps the intel defensible.

## Common mistakes

- **Monitoring without analysis.** Forwarding competitor news with no point of view. Raw signal a rep can't act on is noise.
- **Stale battlecards.** One incorrect line and the rep stops trusting the whole card. Stale beats missing in only one direction, and it's the wrong one.
- **Positioning against phantom competitors.** Building messaging against a company that never shows up on a buyer's shortlist dilutes your real differentiation.
- **Misreading the real competitor.** Treating a rival vendor as the threat when 20 to 30% of enterprise deals are lost to no decision. The status quo is often the thing to beat.
- **Letting the losing rep run win/loss.** Buyers soften feedback to the face that just lost the deal, so the most important signal gets sanded off.
- **Pretexting.** Posing as a customer or recruiter to extract a roadmap. It violates the SCIP code, and it's the kind of thing that ends up in a lawsuit.
- **Treating AR as a one-time submission.** Filling out the questionnaire the month it's due, with no relationship built and no inquiries influenced, and then wondering about the placement.
- **Building the set from capability instead of evidence.** (Amended 2026-08-25.) Every company that could solve the problem, rather than every company a buyer actually weighed. Produces a roster of twenty for a decision about five.
- **Producing a list with no decision attached.** (Amended 2026-08-25.) Hill and Westbrook's forty-factor SWOT: no prioritization, no verification, no downstream use. The artifact becomes the deliverable.
- **Shipping a checkmark-and-blank comparison table.** (Amended 2026-08-25.) A blank cell is an affirmative claim that they lack the feature, and NAD has said so. It also needs the reviewed set stated beside it.
- **Reading vendor marketing as capability.** (Amended 2026-08-25.) A competitor's site is a primary source about what they claim and a weak source about what the product does. Tiering the sources is what keeps the two apart.
- **Quoting the ninety-day staleness figure, or a point-estimate no-decision rate.** (Amended 2026-08-25.) Neither number survives a look at its source.

## Worked example

**Valoquent** (iOS app, real-time video conversations with historical figures, scored by a visible 0-100 conversation quality meter; positioned "Yoodli tells you how you talk, Valoquent tells you how you think") is a clean test of the competitive-alternatives idea, because the naive competitor map is wrong.

The reflexive move is to build a battlecard against the direct historical-AI set (Hello History, Text With History, History Chat AI) and the AI-companion set (Character.ai, Replika). Dunford's question reframes it: what would a user do if Valoquent didn't exist? For most, the answer isn't "use Hello History." It's "do nothing," or "keep using a generic chatbot," or "watch a documentary." The real first competitor is the status quo, the same no-decision problem in a consumer skin.

The phantom-competitor trap is just as live. Yoodli is a speech-coaching tool, not a historical-conversation app. It theoretically overlaps, but it rarely shows up on the same shortlist. Positioning hard against Yoodli would water down the actual differentiation. So the line goes the other way and uses Yoodli as a contrast, not a rival: "Yoodli tells you how you talk, Valoquent tells you how you think." That sentence does the depositioning work a landmine does, by getting the listener to notice the gap themselves rather than attacking a competitor by name.

Peer-review and community signals matter here even without a B2B sales motion. App Store reviews, the AI-companion and AI-tutoring conversations on Reddit, and sentiment on the historical-AI tools are the consumer equivalent of a G2 Grid. They shape what a prospective user believes before the first scored conversation, which is exactly where a CI program should be watching.

## Interview fluency

**Terms to know cold:**

- **Battlecard.** A short competitive document covering a rival's strategy, your differentiation, landmines to set, and objection responses.
- **Landmine / trap.** A depositioning question or statement that leads a prospect to discover a competitor's weakness themselves, rather than attacking the competitor directly.
- **FIA (Fact, Impact, Act).** Klue's model for a battlecard insight: the competitive fact, why it matters and when, and the talk track that follows.
- **Win/loss analysis.** Structured post-decision interviews with buyers (wins and losses) about why a deal went the way it did. The losing rep never runs it.
- **No decision.** The status quo as competitor. Enterprise vendors lose roughly 20 to 30% of deals to it, per Dunford.
- **Competitive alternatives.** Dunford's term for what a buyer would do without you, which is often a spreadsheet or doing nothing, not a rival product.
- **Phantom competitor.** A company that could compete on paper but never shows up on real shortlists. Positioning against it dilutes your message.
- **Primary vs. secondary intelligence.** Collected directly (interviews, field intel) versus already published (websites, filings, reviews).
- **SCIP Code of Ethics.** The industry ethics standard: comply with the law, disclose your identity before interviews, no pretexting.
- **Magic Quadrant.** Gartner's 2x2 on completeness of vision (x) and ability to execute (y).
- **Forrester Wave.** Forrester's scored evaluation on a current-offering axis and a strategy axis, with marker size as a third dimension; read the report's own legend.
- **Briefing vs. inquiry.** A briefing is you presenting to an analyst (outbound). An inquiry is a paying client asking an analyst a question (where buyers get steered).
- **Day One list.** (Added 2026-08-25.) The vendors a buyer starts with. Median 3.6, and 95% of purchases come from it (6sense 2025).
- **Inclusion test.** (Added 2026-08-25.) A name enters the competitive set only with evidence a buyer considered it. The operational form of the phantom-competitor rule.
- **16 CFR §14.15.** (Added 2026-08-25.) The FTC policy encouraging comparative advertising that names competitors, at the ordinary substantiation standard.
- **NAD.** (Added 2026-08-25.) BBB National Programs' National Advertising Division, the fast public venue where comparison claims get challenged. Deel v. Rippling is the checkmark-table case.
- **DeWitt clause.** (Added 2026-08-25.) A licence term barring publication of benchmark results without vendor approval.

**Likely questions and talking points:**

*How do you keep a battlecard from going stale?* Stale is the number-one failure mode, because one wrong line and the rep abandons the whole card. So it needs a named owner, a steady intake of field intel and win/loss, and updates tied to competitor moves like pricing changes and feature sunsets, not to a calendar. I also ship role-specific variants, since a BDR and an AE use the card at different points in the deal.

*Who is your real competitor?* I start from Dunford's question: what would the buyer do if we didn't exist? Often it's a spreadsheet or nothing, and in enterprise software 20 to 30% of deals go to no decision, so the status quo is usually the first competitor. I'm careful not to position against phantom competitors, companies that could compete on paper but never show up on a real shortlist, because that just dilutes the message.

*How do you run win/loss without biasing the results?* The hard rule is that the rep who owned the deal never runs the interview, because buyers soften feedback to the face that just lost. I use a neutral third party for strategic deals to get candor and run the long tail internally. I interview two to four weeks after the decision, ask open questions about the alternatives and the moment they decided, and feed the findings back into positioning and the roadmap.

*How do you get into a Magic Quadrant or a Wave?* Start the relationship six to twelve months early, because inclusion is invitation-only and reputation-driven. Briefings are free, so I'd brief the relevant analyst regularly, answer the questionnaire carefully, map the demo to the published criteria, and line up customer references. The leverage isn't just the report, it's influencing the inquiries where the analyst actually recommends vendors to buyers.

## Signals to watch

In a daily product-marketing scan, the items that belong on this page:

- **CI tooling moves**: Klue, Crayon, and Kompyte feature launches, AI battlecard generation, win/loss integrations, and any M&A. Klue's DoubleCheck acquisition is the template for what consolidation looks like here.
- **Analyst report drops**: new Magic Quadrants, Forrester Waves (including the Market and Competitive Intelligence Platforms Wave), and Tech Tides in Valoquent's and Tapestry's categories. Note who moved into Leaders and how the criteria shifted.
- **Methodology changes** at Gartner or Forrester, like the mid-2024 shift in what a Wave's marker size represents. These change how a placement should be read and cited.
- **Competitor battlecard and depositioning signals**: a public battlecard, a comparison page, or a "vs." landing page reveals exactly how a rival frames the fight and which landmines they're laying.
- **Peer-review and community shifts**: G2 Grid movement, new review velocity, and sentiment on Reddit or in Slack communities, especially the G2-Reddit partnership surfacing vendor presence in those threads.
- **Win/loss and no-decision data**: any new study on candor by interview method or on no-decision loss rates, since those numbers anchor how the program is justified internally.
- **Ethics and legal flashpoints**: pretexting cases, CI-related lawsuits, or SCIP guidance updates, which set the boundary line for how aggressive collection can get.

## Sources

1. Sales Battlecards 101: Guide + Battlecard Templates. Klue. https://klue.com/blog/competitive-battlecards-101
2. Competitive Battlecards 101: Landmines to Lay Template. Klue. https://klue.com/blog/competitive-battlecards-101-landmines
3. Sales Battlecards 101: The Ultimate Guide. Crayon. https://www.crayon.co/blog/competitive-battlecards-101
4. Positioning and Competition. April Dunford. https://www.aprildunford.com/post/positioning-and-competition
5. A Buyer-Centric Approach to Competitive Positioning. April Dunford. https://aprildunford.substack.com/p/a-buyer-centric-approach-to-competitive
6. Sales Win-Loss Analysis: DIY vs. Third Party. Satrix Solutions. https://www.satrixsolutions.com/blog/sales-win-loss-analysis-diy-vs-third-party/
7. 8 Tips for Effective Win/Loss Analysis. Product Marketing Alliance. https://www.productmarketingalliance.com/8-tips-for-effective-win-loss-analysis/
8. SCIP Code of Ethics for Competitive and Market Intelligence. SCIP (via Octopus Intelligence). https://www.octopusintelligence.com/scip-competitive-intelligence-code-of-ethics/
9. Analyst Relations 101: How to Engage and Brief Analyst Firms. Insight Partners. https://www.insightpartners.com/ideas/analyst-relations-unlocks-scaleup-superpowers/
10. The Forrester Tech Tide Methodology. Forrester. https://www.forrester.com/policies/tech-tide-methodology/
11. The Forrester Wave: Market And Competitive Intelligence Platforms, Q4 2024. Forrester. https://www.forrester.com/report/the-forrester-wave-tm-market-and-competitive-intelligence-platforms-q4-2024/RES181756
12. Gartner Magic Quadrant and Forrester Wave Explained in PM Terms. Alex Cruz Farmer. https://medium.com/alexcruzfarmer/gartner-magic-quadrant-and-forrester-wave-explained-in-pm-terms-d07624c433c4
13. G2 and Reddit Partner to Expand B2B Brand Presence. G2. https://company.g2.com/news/g2-partners-with-reddit
14. Four Things to Know if You Want to Be in a Gartner Magic Quadrant. Metis Communications. https://www.metiscomm.com/four-things-to-know-if-you-want-to-be-in-a-gartner-magic-quadrant/

*Added in the 2026-08-25 amendment pass:*

15. 2025 B2B Buyer Experience Report. 6sense. https://6sense.com/
16. 2026 B2B Buying Disconnect. TrustRadius. https://www.trustradius.com/
17. State of Competitive Intelligence 2026. Crayon. https://www.crayon.co/ (sample size not disclosed)
18. 2026 Buyer Behavior Report. G2. https://www.g2.com/
19. Hill, T. and Westbrook, R. "SWOT Analysis: It's Time for a Product Recall." Long Range Planning 30(1), 1997, pp. 46-52.
20. Dixon, M. and McKenna, T. The JOLT Effect. Portfolio, 2022.
21. Statement of Policy Regarding Comparative Advertising, 16 CFR §14.15. Federal Trade Commission. https://www.ecfr.gov/current/title-16/chapter-I/subchapter-B/part-14/section-14.15
22. Pizza Hut, Inc. v. Papa John's International, Inc., 227 F.3d 489 (5th Cir. 2000).
23. New Kids on the Block v. News America Publishing, Inc., 971 F.2d 302 (9th Cir. 1992).
24. NAD Case #7304, Deel v. Rippling, decided 2024-08-08. BBB National Programs.
25. NAD, SharkNinja, decided 2024-11-24. BBB National Programs.
26. Directive 2006/114/EC concerning misleading and comparative advertising. European Parliament and Council. https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32006L0114

## Related

- [Competitive research execution](15-competitive-research-execution.md)
- Positioning and category design (page 02 of the larger wiki, not in this package)
- Customer and market understanding (page 04 of the larger wiki, not in this package)
- Sales enablement (page 08 of the larger wiki, not in this package)
- Metrics and proving PMM impact (page 11 of the larger wiki, not in this package)
- PMM career and interview study guide (page 14 of the larger wiki, not in this package)
- [The competitive research protocol](../protocols/04-competitive-research.md) is the binding process; [`research/competitive-research-methods.md`](../research/competitive-research-methods.md) holds the evidence behind the 2026-08-25 amendments.
