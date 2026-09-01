# Naming

Page 03 covers messaging and touches naming as one of its outputs. This page covers the naming decision itself: whether a capability needs a name at all, what kind of name the trademark spectrum makes available and at what cost, what the behavioral research does and does not support, and what renaming costs once developers depend on the old one. It is the study version of [the launch campaign protocol](../protocols/05-launch-campaign.md) step 3, which is the binding process and wins on any conflict.

Scoped to B2B software and developer tools. Consumer brand naming is a different question with a different evidence base, and conflating the two is how the studies below get misquoted.

Last checked: 2026-08

**Evidence note, read first.** This topic splits cleanly and the split is the most useful thing on the page. The legal half rests on primary law, it is settled, and it is precise. The behavioral half rests almost entirely on lab studies of undergraduates rating fictitious consumer goods, none of which has been tested on a software buyer. And the question most people actually ask, whether a feature should be named at all, has **no empirical literature in any commercial software context**. Sourcing and a rejected-sources list are in [`research/product-naming.md`](../research/product-naming.md).

## Core concepts

### The first question has no evidence behind it, and that is worth knowing

Should this capability be a named object, or the descriptive phrase buyers already use?

I could not find a single study on this in a B2B or software setting. Nothing comparing named against unnamed features on adoption, recall, pricing power, or sales-cycle length. The marketing literature studies brands at the company or consumer-product level. The software-engineering literature studies naming as identifier readability in source code. The commercial feature name inside a product a committee buys sits between them and is unstudied.

Every framework offered for this decision, including the one in the launch protocol, is reasoning from mechanism. **Say so when you use it.** A naming recommendation dressed in citations that are about something else is the specific failure this page exists to prevent.

### The strength spectrum is a legal gate, and the statute is exact

*Abercrombie & Fitch Co. v. Hunting World, Inc.*, 537 F.2d 4 (2d Cir. 1976), Judge Friendly. The classes, in his words, are "arrayed in an ascending order which roughly reflects their eligibility to trademark status and the degree of protection accorded": generic, descriptive, suggestive, arbitrary or fanciful.

Legal protectability increases along that order and immediate comprehension decreases. That is the shape of the decision, and it is a statement about law plus a statement about semantics. Neither half is an empirical claim about buyers.

Three things the practitioner retellings drop:

**The category decides, and a name can sit in two classes at once.** *Abercrombie* itself held SAFARI generic for the safari hat, jacket and suit while valid for boots, luggage, ice chests, axes, tents and tobacco. Friendly: "a term that is in one category for a particular product may be in quite a different one for another." A name that is arbitrary for a database is descriptive for a search product, so clearance is per-class and a clean result in one class says nothing about another.

**Genericness is a one-way door.** Friendly again: "proof of secondary meaning, by virtue of which some 'merely descriptive' marks may be registered, cannot transform a generic term into a subject for trademark." Descriptive marks can be rescued. Generic ones cannot.

**The §2(f) escape hatch is weaker than it reads.** 15 U.S.C. §1052(f) says the Director **may** accept, as **prima facie evidence** of acquired distinctiveness, proof of "substantially exclusive and continuous use" for five years. A feature name built from the category's own words is exactly the case where substantially exclusive use does not exist, because competitors are using the same phrase for the same reason. Five years is also five years after launch, so it is never the answer to a launch-day question.

The Supplemental Register is the usual fallback and 15 U.S.C. §1094 says precisely what it withholds: no §1057(b) prima facie evidence of validity and exclusive right, no §1072 constructive notice, no §1115 evidentiary presumptions and therefore no road to incontestability, no §1124 customs recordation, and no intent-to-use filing, so the mark must already be in use. What it gives: a federal record, the ® symbol, a citable bar against later confusingly similar applications, and standing in federal court. Under §1095 it does not preclude later Principal Register registration and is not an admission that distinctiveness is absent.

### The behavioral research is real, small, and probably does not transfer

**Processing fluency.** Alter and Oppenheimer (2006, *PNAS* 103(24)) ran three studies. In the lab, 29 Princeton undergraduates predicted fluent-named stocks would appreciate 3.90% and disfluent-named ones depreciate 3.86%, t(29) = 4.14, P < 0.0001. Against real NYSE data the effect was significant at one day and one week and **gone by six months and one year** (β = −0.05, P = 0.64 at six months). In the ticker study the one-day effect had η² = 0.01, which the authors themselves call small.

**Sound symbolism.** Yorkston and Menon (2004, *Journal of Consumer Research* 31(1)) manipulated a single phoneme in a fictitious ice cream brand, Frish against Frosh, on 126 undergraduates. The effect held when participants were told the name was real (M = 5.06 against 4.25), and **disappeared entirely when the same participants were told it was a test name** (4.36 against 4.08, F < 1). Under cognitive load the discounting failed and the raw effect returned. Lowrey and Shrum (2007) add that the direction is conditional on category fit rather than absolute: the same connotation helps a convertible and hurts an SUV.

**Why this probably does not carry to B2B.** Fluency effects are strongest where processing effort is the main available cue and weakest where diagnostic information is abundant. A software purchase is a months-long evaluation by several people who read documentation, run a trial, and call references, which is the abundant-information case. And the Yorkston and Menon moderator is the sharp one: a technical buyer reading a launch post about a newly coined name **knows it is a marketing name** and has full attention, which is precisely the cell where the effect vanished.

The honest position: the mechanism is plausible, it is untested here, and what evidence exists on the moderators points toward the effect being smaller in B2B rather than larger. Do not cite these papers as license for a naming choice.

### The counterweight: a coined name is a container

Landgraf, Luffarelli and Stamatogiannakis (2026, *Journal of Business Research* 202) argue non-semantic names provoke curiosity, and curiosity makes the information the brand then supplies more persuasive. Study 1 is an observational analysis of 6,487 Kickstarter campaigns finding non-semantic-named brands raise more; the authors state they work in the context of technology brands.

The load-bearing study is the fourth: **the advantage attenuates when compelling brand information is absent.** Read against the fluency work, the two literatures agree more than they look like they do. A coined name performs when there is something behind it for the curious reader to land on, and does nothing when there is not.

That is an argument for coining a name only for a capability with a real story attached, and against coining one for an increment. It is the same line the launch tiers draw. Caveats: Kickstarter consumer hardware is not B2B software, and Study 1 cannot rule out that better teams both coin names and raise more.

### Brand architecture is a vocabulary with no test behind it

Aaker and Joachimsthaler (2000, *California Management Review* 42(4)) introduced the brand relationship spectrum: House of Brands, endorsed brands, sub-brands, Branded House. It is the standard framework and it is genuinely useful, because it makes the options visible and gives a room words to argue with.

**No empirical test of it turned up.** Nothing comparing architectures on a business outcome, nothing establishing conditions under which one wins. It is a taxonomy plus case-based argument, and the large secondary literature repeats the taxonomy without adding evidence. Present it as vocabulary.

Its relevance to feature naming is also narrower than its fame suggests. Most feature decisions sit entirely inside a Branded House already, where the only question is whether the capability gets a proper name or a descriptor. The spectrum's interesting cases, endorsement and separation, come up for acquisitions and for products aimed at a different buyer.

One real connection: a sub-brand inherits the parent's trademark position and earns none of its own, and a descriptor is not a mark at all. The architecture choice and the *Abercrombie* choice are the same choice seen from two directions, and separating them is how a company ends up with a name it likes and cannot own.

### Discoverability: the argument is sound and unmeasured

A coined name launches with no search volume attached and competes against the descriptive phrase buyers type. No study measures this. What exists is three artifacts, all consistent with the argument and none of them a measurement:

- A commenter on the Docker to Moby rename PR, in the project's own tracker: "Now everybody will have to filter a lot of search rubbish about musician, moby dick, moby explorer."
- A third party maintaining an "AWS in Plain English" translation table because "with 50 plus opaquely named services, we decided that enough was enough."
- Google shipping a pronunciation guide inside the Kubernetes launch post: "Kubernetes (koo-ber-nay'-tace) is Greek for 'helmsman' of a ship." A launch announcement that has to teach you to say the name is the fluency cost being paid in public, by a company that paid it and won the category anyway.

**The practical resolution, marked as reasoning:** ship the name and the descriptive phrase together every time until the name carries alone, and treat "appears in search queries and third-party writing without the descriptor" as the observable stopping condition.

### Renaming turns on one variable

Two documented cases, and they split cleanly.

Microsoft announced Azure AD becoming Microsoft Entra ID on 2023-07-11, with SKU names changing 2023-10-01, and **explicitly held login URLs, APIs, PowerShell cmdlets and libraries** including MSAL, keeping Microsoft Graph and Azure AD B2C under existing names. The marketing surface moved and the developer namespace did not.

Docker announced the Moby Project on 2017-04-18 with the assurance that Docker "is staying exactly the same from a user's perspective," and the rename PR merged two days later with one sentence of explanation. The tracker carries the response: "This is not gonna work nice for all the projects that depend on github.com/docker/docker. No notice, nothing, and just breaking everything." Issue #40222, "Rename moby to docker," was opened in 2019 and remains open.

**A rename survives when the technical namespace does not move.** Two cases, so treat it as a hypothesis with evidence rather than a finding.

Two more cases worth knowing. OpenTF became OpenTofu in September 2023 purely to put distance between itself and Terraform's mark, trading an instantly decodable abbreviation for a coined name, which is the *Abercrombie* trade-off paid in public. And `golang/go` issue #9, filed days after Go's launch by someone who had spent ten years on a language of the same name, was closed with the label **"Unfortunate."** Google did not rename. A prior-use collision is a risk to price, not an automatic veto.

## How strong teams do it

They answer "does this need a name" before "what should the name be," and they say out loud that the answer is judgment.

They run clearance per class, early, and before any surface is built, because the *Abercrombie* class depends on the goods and a clean result elsewhere means nothing.

They pick the point on the spectrum deliberately and name the cost they are accepting: comprehension if they coin, ownability if they describe.

They ship the name beside the descriptive phrase until the name carries, and they have a stated condition for stopping.

They coin a name only where there is a story behind it, which is the one finding in the behavioral literature that survives contact with the setting.

They separate the marketing surface from the technical namespace on any rename, and they publish migration guidance before the rename lands rather than after.

They do not cite consumer fluency studies as justification for a B2B name.

## Common mistakes

- **Starting at "what should we call it."** The prior question is whether it needs a name, and the default answer is no.
- **Treating clearance as a formality after the decision.** It is the gate, and the *Abercrombie* class is what determines whether there is anything to clear.
- **Assuming a clean clearance in one class transfers.** SAFARI was generic and valid simultaneously.
- **Relying on §2(f).** Five years of substantially exclusive use is exactly what a descriptive feature name will not have, and it is five years too late anyway.
- **Coining a name for an increment.** The curiosity advantage attenuates when there is nothing behind the name.
- **Quoting Frish and Frosh at a B2B audience.** The effect disappeared when participants knew it was a marketing name, which is the condition your buyer is always in.
- **Leading with the coined name and never stating the descriptive one.** Invisible to everyone who has not already heard it.
- **Renaming the namespace along with the brand.** The Docker case, still open in the tracker years later.
- **Reading brand architecture as evidence.** It is a taxonomy, and a good one.

## Worked example

**Valoquent.** A coined name, and by the *Abercrombie* test a fanciful or arbitrary one, so it is at the strong end for protectability and started at zero comprehension. That is the trade-off taken deliberately, and the cost shows up exactly where the framework predicts: nobody types "Valoquent" until they have heard it, and the descriptive phrase they actually search is something closer to talking to historical figures.

The resolution in practice is the paired form. The name never travels alone in launch copy; the descriptor rides with it. The stopping condition is observable, which is when the name starts appearing in third-party writing and search queries without the descriptor attached.

The naming section of page 03 and the positioning work on page 02 are where the harder question lives, which is that the category itself is unsettled. Conversational skill development is a category claim, and a coined product name inside an unnamed category has to carry two unfamiliar things at once. The launch protocol's tier 1 definition, a new reason to consider the product at all, is what earns that cost.

**The Tapestry family** is the sub-brand case. Tapestry, OwnMind, the Loom, Threads: a coined set inside a Branded House, each one arbitrary against its function. The architecture note above applies directly, since none of them earns its own trademark position and all of them inherit whatever the parent has.

It also carries a documented rename with the namespace lesson attached. On 2026-08-02 "soul" was retired from user-facing names and the values file became GROUND.md. The user-facing name moved and the internal one moved with it, which is the Docker shape rather than the Entra shape, and it is survivable here only because the dependents are all internal. A public API with the old name in it would have made that a different decision.

## Interview fluency

**Terms to know cold:**

- **The *Abercrombie* spectrum.** Generic, descriptive, suggestive, arbitrary, fanciful. Protectability rises along it, comprehension falls. *Abercrombie & Fitch v. Hunting World*, 537 F.2d 4 (2d Cir. 1976).
- **Genericness is irreversible.** Secondary meaning rescues a descriptive mark and cannot rescue a generic one.
- **Class-dependence.** SAFARI was generic for hats and valid for luggage at the same time. Clearance is per class.
- **Lanham §2(f) / acquired distinctiveness.** Five years of substantially exclusive continuous use as prima facie evidence. Not available to a name built from the category's own words, and not a launch-day asset.
- **Supplemental Register.** A federal record and the ® symbol, without the §1057(b), §1072, §1115 and §1124 advantages, and no road to incontestability.
- **Processing fluency.** Easier-to-pronounce names draw better fast judgments. Alter and Oppenheimer 2006, and the effect decayed to nothing past a week.
- **Diagnosticity moderator.** Yorkston and Menon 2004: the sound-symbolism effect vanished when participants knew the name was a test name.
- **The container finding.** Landgraf et al. 2026: coined names help, and the help attenuates when there is no compelling information behind them.
- **Brand relationship spectrum.** Aaker and Joachimsthaler 2000. House of Brands to Branded House. A vocabulary with no empirical test found.
- **The rename variable.** A rename survives when the technical namespace does not move. Entra against Moby.

**Likely questions and talking points:**

*How do you decide what to name a new feature?* The first question is whether it needs a name at all, and I would say plainly that this one has no research behind it in any software context. Nothing compares named against unnamed features on adoption or recall or sales cycle, so anyone presenting a framework here is reasoning from mechanism and should say so. My default is the descriptive phrase buyers already use, because a name is a claim that the thing is a distinct object worth remembering and it carries a maintenance cost forever. What earns a name is a capability with a real story behind it, which is also the one thing the evidence supports: the recent work on coined names finds their advantage attenuates when there is nothing compelling for the curious reader to land on.

*What is the trademark angle on naming?* The *Abercrombie* spectrum from 1976 is the gate, and it runs generic, descriptive, suggestive, arbitrary, fanciful. Protectability rises along it and immediate comprehension falls, so the choice is which cost you pay. Two things I would flag that get dropped in the usual summary. The class decides, so a name can be generic for one product and valid for another simultaneously, which means clearance has to run per class. And genericness is a one-way door, where secondary meaning can rescue a descriptive mark and can never rescue a generic one. People also reach for the §2(f) five-year acquired-distinctiveness route, and it requires substantially exclusive use, which is exactly what a name built from the category's own words will never have.

*Does naming psychology actually matter?* Less than it gets quoted, and I would be careful with it. The fluency and sound-symbolism results are real, but they are undergraduates judging fictitious consumer goods in one shot, and the moderators point the wrong way for B2B. Alter and Oppenheimer's pronounceability effect on real stocks was gone by six months. And Yorkston and Menon found the sound-symbolism effect disappeared the moment participants were told the name was a test name rather than a real one. A technical buyer reading a launch post knows perfectly well it is a marketing name and has full attention, which is the exact cell where the effect vanished. So I treat it as unestablished here in either direction rather than as license.

*What does it cost to rename something?* It depends almost entirely on whether the technical namespace moves. Microsoft renamed Azure AD to Entra ID and explicitly froze the login URLs, the APIs, the PowerShell cmdlets and the libraries, so only the marketing surface moved. Docker's Moby rename moved the namespace developers had already taken a dependency on, with one sentence of explanation, and there is still an open issue in their tracker asking for it back. The other cost is search: someone on that PR pointed out they would now be filtering results about the musician and Moby Dick. So the rule I would work to is that a rename survives when the namespace does not move, and that migration guidance ships before the rename rather than after.

*How do you handle a coined name having no search volume?* Ship it beside the descriptive phrase every time, and keep doing that until the name carries alone. The stopping condition is observable, which is when it starts showing up in search queries and in third-party writing without the descriptor attached. I would also be honest that the discoverability cost here is argued rather than measured. There is no study comparing named against descriptive features on search performance. What there is is a decoder site somebody built for AWS's fifty-plus opaque service names, and Google shipping a pronunciation guide inside the Kubernetes launch post, which tells you both that the cost is real and that a company can pay it and still take the category.

## Signals to watch

In a daily scan, the items that belong on this page rather than on 02 or 03:

- **Registrability rulings on the descriptive-suggestive line**, TTAB decisions, and anything moving the genericness standard for software marks.
- **Trademark disputes between software vendors**, especially where a name derived from a category term is at issue.
- **Documented renames in dev tools and infrastructure**, with attention to whether the technical namespace moved and what the tracker said.
- **Replication or extension of the naming psychology**, particularly anything run on professional or B2B samples, which would upgrade the largest gap on this page.
- **Empirical work on named versus unnamed features.** Currently a void. The first real study would be the most valuable thing that could land here.
- **Naming that creates a category**, and the disciplined version of that claim: who used the term first, and what is actually verifiable about it.

## Sources

1. Abercrombie & Fitch Co. v. Hunting World, Inc., 537 F.2d 4 (2d Cir. 1976). Hosted by WIPO Lex. https://www.wipo.int/wipolex/en/text/581586
2. 15 U.S.C. §1052 (Lanham Act §2), subsections (e)(1) and (f). Cornell Legal Information Institute. https://www.law.cornell.edu/uscode/text/15/1052
3. 15 U.S.C. §1091, §1094, §1095 (Supplemental Register). Cornell Legal Information Institute. https://www.law.cornell.edu/uscode/text/15/1094
4. Strong trademarks. United States Patent and Trademark Office, updated 2023-11-30. https://www.uspto.gov/trademarks/basics/strong-trademarks
5. Alter, A. L. and Oppenheimer, D. M. "Predicting short-term stock fluctuations by using processing fluency." PNAS 103(24), 2006, pp. 9369-9372. https://www.pnas.org/doi/10.1073/pnas.0601071103
6. Yorkston, E. and Menon, G. "A Sound Idea: Phonetic Effects of Brand Names on Consumer Judgments." Journal of Consumer Research 31(1), 2004, pp. 43-51. https://academic.oup.com/jcr/article-abstract/31/1/43/1812051
7. Lowrey, T. M. and Shrum, L. J. "Phonetic Symbolism and Brand Name Preference." Journal of Consumer Research 34(3), 2007, pp. 406-414. https://academic.oup.com/jcr/article-abstract/34/3/406/1798924
8. Landgraf, P., Luffarelli, J. and Stamatogiannakis, A. "Meaningless brand names can spark consumer curiosity and improve brand evaluations." Journal of Business Research 202, 2026. https://ideas.repec.org/a/eee/jbrese/v202y2026ics0148296325005909.html
9. Aaker, D. A. and Joachimsthaler, E. "The Brand Relationship Spectrum: The Key to the Brand Architecture Challenge." California Management Review 42(4), 2000, pp. 8-23. https://journals.sagepub.com/doi/10.1177/000812560004200401
10. The new name for Azure AD is Microsoft Entra ID. Microsoft Identity Platform blog, 2023-07-11. https://devblogs.microsoft.com/identity/aad-rebrand/
11. Introducing the Moby Project. Docker blog, 2017-04-18. https://www.docker.com/blog/introducing-the-moby-project/
12. moby/moby PR #32691 and issue #40222. GitHub. https://github.com/moby/moby/issues/40222
13. golang/go issue #9. GitHub, filed 2009-11-11. https://github.com/golang/go/issues/9
14. Announcing OpenTofu. The Linux Foundation, 2023-09-20. https://www.linuxfoundation.org/press/announcing-opentofu
15. An update on container support on Google Cloud Platform. Google Open Source blog, 2014-06-11. https://opensource.googleblog.com/2014/06/an-update-on-container-support-on.html
16. AWS in Plain English. Expedited Security. https://expeditedsecurity.com/aws-in-plain-english/

**Source-quality note.** Items 1 to 4 are primary law and the page's legal claims rest entirely on them. Items 5 and 6 were read in full; 7, 8 and 9 are abstract-or-citation only and the page states no effect size for them. Items 10 to 16 are primary artifacts from the parties themselves. Klink (2000) is cited in the underlying research page and is carried only through Yorkston and Menon's description of it, with no sample size or statistic stated. Full detail, including a rejected-sources list, is in [`research/product-naming.md`](../research/product-naming.md).

## Related

- Messaging and value propositions (page 03 of the larger wiki, not in this package)
- Positioning and category design (page 02 of the larger wiki, not in this package)
- [Campaigns and channels](16-campaigns-and-channels.md)
- [Developer marketing](18-developer-marketing.md)
- [Competitive research execution](15-competitive-research-execution.md) for the comparative-advertising law that sits beside the trademark law here.
- [The launch campaign protocol](../protocols/05-launch-campaign.md), step 3, is the binding version of this page.
- [`research/product-naming.md`](../research/product-naming.md) holds the sourcing.
