# Naming a Product Feature or Tier in B2B Software

Topic page. What holds up when a company ships a major capability and has to
decide whether it gets a name at all, what kind of name, and how that choice is
checked before launch. Scoped to B2B software and developer tools rather than
consumer brand naming, and that scope is the finding: the legal half of this
question rests on primary law and is settled, while the behavioral half rests
almost entirely on consumer lab work with undergraduate samples that nobody has
tested on a buying committee.

Opened 2026-08-26. Prompted by [the launch campaign protocol](../protocols/05-launch-campaign.md) naming gate.

Tags: `product-naming` · `trademark-law` · `brand-architecture`

---

> **Status: complete for this pass.** Sections 1 to 5 and 7 are sourced. Sections
> 6, 8 and 9 were completed 2026-08-26 and their finding is largely negative: brand
> architecture is a taxonomy with no empirical test, the discoverability cost of an
> opaque name is unmeasured, and no research describes how naming decisions are
> actually run inside software companies. Those are recorded as gaps rather than
> filled with practitioner content.

## TL;DR

The naming decision has one hard gate and one soft one, and they get confused.
The hard gate is legal: the *Abercrombie* spectrum determines whether a name can
be owned at all, and the statute is unambiguous about what each point on it buys.
The soft gate is behavioral, and there the evidence is thinner than the confidence
with which it gets quoted. Fluency and sound symbolism are real findings on
undergraduates rating ice cream and stock tickers, they have never been tested on
software buyers, and the one effect most relevant to B2B (a coined name being
discounted once the audience is told it is a marketing name) is documented in the
same paper people cite for the opposite conclusion.

## Confidence map

**High confidence** (primary document read directly, or two independent sources)

- The four-category strength spectrum and its consequences for registrability.
  *Abercrombie* is a primary opinion, 15 U.S.C. §§1052, 1091, 1094, 1095 are
  primary statute, and the USPTO's own public page restates the same ladder.
- What the Supplemental Register does and does not confer. This is enumerated in
  15 U.S.C. §1094 by section number, so it is not a matter of interpretation.
- Alter and Oppenheimer 2006 found a pronounceability effect on short-run stock
  returns that decayed to non-significance beyond about a week. Read in full.
- Yorkston and Menon 2004 found a single-phoneme brand name effect on attribute
  judgments that **disappeared when participants were told the name was a test
  name**. Read in full.
- Docker's Moby rename, the Elastic and Amazon trademark dispute, the OpenTF to
  OpenTofu rename, and Go issue #9 are documented in primary sources including
  the projects' own trackers and blogs.

**Medium confidence** (one strong source, or a strong source read only in part)

- Landgraf, Luffarelli and Stamatogiannakis 2026 on non-semantic names raising
  more crowdfunding. Abstract and study structure verified; full text paywalled,
  so the effect size is not carried here.
- Klink 2000. Full text paywalled. Carried through Yorkston and Menon's
  description of it in a peer-reviewed article I did read.
- Azure Active Directory to Microsoft Entra ID as a case of a surface-only
  rename. Single primary source, which is Microsoft's own blog.

**Contested or unresolved**

- Whether any fluency or sound-symbolism finding transfers to B2B software. No
  study tests it. Both directions are argument, not evidence.
- Whether a coined name or a descriptive one performs better on discovery. See
  the discoverability section; the honest answer is that the question has not
  been studied outside vendor content.

**Explicitly unusable, recorded so the next pass does not re-find it**

- Corey Quinn, "The AWS service I hate the most" (2022-01-05) is widely cited as
  AWS naming criticism. It is not. It is about Isengard being internal-only, and
  it praises the name. Do not use it for a naming argument.
- The Kubernetes "Project Seven of Nine" codename story and the claim that
  Google's legal department rejected thirteen other names. Both trace to a single
  2016 GeekWire article that could not be fetched. Do not assert them.
- Attribution of the term "DevOps" to Patrick Debois via the DevOpsDays 2009
  event page. The page confirms the event and does not name him. Sourced
  elsewhere or not at all.

---

## 1. The first question is whether it needs a name, and there is no evidence base for it

The decision the naming gate actually serves is upstream of everything below:
should this capability be a named object, or should it be the descriptive phrase
buyers already use.

I could not find a single empirical study on this question in a B2B or software
context. Not one comparing named against unnamed features on adoption, recall,
pricing power, or sales-cycle length. The marketing literature studies brand
names as brands, meaning company-level or consumer-product-level names, and the
software engineering literature studies naming as an identifier-readability
problem in source code. The middle case, a commercial feature name inside a
product a committee buys, is unstudied.

That is the most useful thing on this page. Every framework offered for this
decision, including the one in the launch protocol, is reasoning from mechanism.
It should be labeled as such and not dressed in citations that are about
something else.

## 2. The trademark strength spectrum is a legal gate, and the statute is precise

### The spectrum

*Abercrombie & Fitch Co. v. Hunting World, Inc.*, 537 F.2d 4 (2d Cir. 1976),
Judge Friendly, is the source. The operative sentence:

> "Arrayed in an ascending order which roughly reflects their eligibility to
> trademark status and the degree of protection accorded, these classes are (1)
> generic, (2) descriptive, (3) suggestive, and (4) arbitrary or fanciful."

Two things in the opinion get dropped in the practitioner retellings and both
matter for a software feature name.

First, the categories are not stable. Friendly: "The lines of demarcation,
however, are not always bright... a term that is in one category for a particular
product may be in quite a different one for another... because a term may shift
from one category to another in light of differences in usage through time." The
*Abercrombie* holding is itself an example. SAFARI was held generic for the
safari hat, safari jacket, and safari suit, and still valid for boots, luggage,
ice chests, axes, tents, and tobacco. One word, one owner, different answers by
category. A name that is arbitrary for a database is descriptive for a search
product.

Second, genericness is a one-way door. Friendly, on generic terms: "proof of
secondary meaning, by virtue of which some 'merely descriptive' marks may be
registered, cannot transform a generic term into a subject for trademark."

The USPTO restates the same ladder in its own public guidance, with examples:
fanciful marks are "invented words. They only have meaning in relation to their
goods or services" (EXXON, PEPSI); arbitrary marks are "actual words that have no
association with the underlying goods or services" (APPLE for computers);
suggestive marks are "words that suggest some quality of the goods or services,
but don't state that quality outright" (COPPERTONE); descriptive marks "merely
describe some aspect of your goods or services without identifying or
distinguishing the source" and are "only registrable in certain circumstances";
generic terms "do not indicate source and cannot function as trademarks" and "are
not federally registrable" (USPTO, page last updated 2023-11-30). The same page
tells applicants to consider "whether the public will remember, pronounce, and
spell your trademark," which is the agency itself gesturing at the fluency
question in section 3 without any evidence behind it.

### What registrability actually means at each point

This is where the practitioner summaries get sloppy, and the statute is exact.

**Descriptive marks.** 15 U.S.C. §1052(e)(1) bars registration of a mark that
"when used on or in connection with the goods of the applicant is merely
descriptive or deceptively misdescriptive of them."

**Acquired distinctiveness, Lanham §2(f).** 15 U.S.C. §1052(f) is the escape
hatch: "The Director may accept as prima facie evidence that the mark has become
distinctive, as used on or in connection with the applicant's goods in commerce,
proof of substantially exclusive and continuous use thereof as a mark by the
applicant in commerce for the five years before the date on which the claim of
distinctiveness is made."

Read that carefully before relying on it. It says the Director **may** accept, it
says **prima facie evidence** and not proof, and the qualifying use must be
**substantially exclusive**. For a feature name built out of the category's own
words, substantially exclusive use is exactly what a company does not have,
because competitors are using the same descriptive phrase for the same reason.
Five years of use is also five years after launch, which is not a launch-day
asset.

**The Supplemental Register.** 15 U.S.C. §1091 admits marks "capable of
distinguishing applicant's goods or services" that cannot yet qualify for the
Principal Register. It is routinely described as a consolation prize, and §1094
says precisely what is withheld:

> "applications for and registrations on the supplemental register shall not be
> subject to or receive the advantages of sections 1051(b), 1052(e), 1052(f),
> 1057(b), 1057(c), 1062(a), 1063 to 1068, inclusive, 1072, 1115 and 1124 of this
> title."

Decoded, the ones that bite: no §1057(b) prima facie evidence of validity,
ownership, and exclusive right; no §1072 constructive notice of the claim of
ownership; no §1115 evidentiary presumptions, which also forecloses the road to
incontestability; no §1124 customs recordation; no §1051(b) intent-to-use filing,
so the mark must already be in use in commerce. What it does give you: a federal
registration record, the ® symbol, a citable bar against later confusingly
similar applications, and standing in federal court.

15 U.S.C. §1095 adds two things worth knowing: supplemental registration "shall
not preclude registration by the registrant on the principal register," and it
"shall not constitute an admission that the mark has not acquired
distinctiveness."

### The trade-off, stated honestly

Legal protectability increases along the spectrum and immediate comprehension
decreases along it. That is the actual shape of the decision, and it is a
statement about law plus a statement about semantics, neither of which is an
empirical claim about buyer behavior. The empirical question is what the
comprehension cost is worth, and section 6 is where that evidence should be. It
mostly is not there.

## 3. Processing fluency: a real effect, in a setting nothing like B2B software

**Alter, A. L. and Oppenheimer, D. M. (2006).** "Predicting short-term stock
fluctuations by using processing fluency." *PNAS* 103(24), 9369-9372. Read in
full. Three studies.

**Study 1.** 29 Princeton undergraduates, 14 female, partial course credit.
Within-subjects. Participants predicted one-year performance for 30 fictional
stock names on a 9-point scale spanning -40% to +40%. Names were split by a pilot
(n=10) into 15 easy-to-pronounce and 15 difficult-to-pronounce. Fluent names drew
a mean predicted appreciation of 3.90% (SD 6.46), disfluent names a mean
predicted depreciation of -3.86% (SD 6.54), t(29) = 4.14, P < 0.0001, η² = 0.39.

**Study 2.** 16 Princeton undergraduates rated the pronounceability of 89 real
NYSE stocks that debuted between 1990 and 2004 on a 6-point scale. Regressing
returns on that rating: 1 day β = -0.23, t = -2.17, P < 0.05; 1 week β = -0.21, t
= -1.96, P = 0.05; **6 months β = -0.05, P = 0.64; 1 year β = -0.08, P = 0.47.**
The much-quoted dollar figure is from this study: a $1,000 investment in a basket
of fluently named shares returned $112 more after one day than the disfluent
basket.

**Study 3.** Ticker codes rather than names. Two coders classified three-letter
tickers as pronounceable or not (KAR versus RDO). 665 NYSE stocks out of 1,388
IPOs 1990-2004, plus 116 AMEX stocks. NYSE 1 day: t(665) = 2.40, P < 0.05, **η²
= 0.01.** Beyond one day, all P > 0.20. AMEX 1 day: t(116) = 1.74, P = 0.09.
$1,000 across both markets yielded an $85.35 advantage at 1 day, falling to
$20.25 at 1 year. The authors controlled for firm size and industry and found
neither explained the result, and they describe the Study 3 effect size as
"small" themselves.

**What this supports and what it does not.** It supports the claim that a hard-to
-pronounce name carries a measurable penalty in a fast, low-information judgment.
The effect is in the regression coefficients and it is in the right direction
across a lab study and two market datasets, which is a genuinely strong design.

The transfer to B2B software naming is not established, and I would not argue it
without saying so. The judgment measured is a snap prediction about an unfamiliar
security by a retail-scale actor with essentially no other information. A software
purchase is a months-long evaluation by multiple people who read documentation,
run trials, and talk to references. Fluency effects are, by their own theory,
strongest where processing effort is the main available cue and weakest where
diagnostic information is abundant. B2B software evaluation is the abundant-
information case. The honest position is that the mechanism is plausible and
untested here, and that Study 2's decay to non-significance at six months is the
result most relevant to a product name that has to live for years.

## 4. Phonetic symbolism: real, small, and it switches off when the audience knows it is a name

**Yorkston, E. and Menon, G. (2004).** "A Sound Idea: Phonetic Effects of Brand
Names on Consumer Judgments." *Journal of Consumer Research* 31(1), 43-51. Read
in full. Two studies, fictitious ice cream brands **Frish** versus **Frosh**,
differing in exactly one phoneme, the front vowel [i] against the back vowel [ä].

**Study 1.** 126 undergraduates at a large northeastern university, 2 x 2 x 2
between-subjects: brand name (Frish/Frosh) x diagnosticity (told it was the true
name versus a test name) x timing (diagnosticity information given simultaneously
with the name or afterward). Dependent measure was an Attribute Perception Index
averaging creaminess, richness, and smoothness (Cronbach's α = .86) plus a Brand
Evaluation Index (α = .81). The predicted three-way interaction held, F(1,117) =
3.84, p < .05, with a main effect of brand name, F(1,117) = 9.51, p < .01.

The load-bearing detail is inside the simultaneous condition. Told the name was
real, participants rated Frosh above Frish on the attributes, M = 5.06 versus
4.25, contrast F(1,122) = 4.43, p < .05. **Told the same name was only a test
name, the effect vanished**, Frish M = 4.36 versus Frosh M = 4.08, contrast F <
1. When the diagnosticity information arrived only after the name had been
encountered, the effect reappeared regardless of what participants were told,
F(1,118) = 9.94, p < .01.

Participants did not know this was happening. Self-rated influence of the brand
name averaged 2.68 on a 7-point scale with a midpoint of 4, and the correlation
between that rating and the attribute index was non-significant, p > .6.

**Study 2.** 111 undergraduates at a large West Coast university, same design
with cognitive load substituted for timing. Under normal capacity, the discounting
held: true name Frosh 63.3 versus Frish 49.2 on 100-point scales, contrast
F(1,108) = 5.47, p < .05, while under the test-name framing Frish 54.9 versus
Frosh 50.3, F < 1. **Under impaired capacity the discounting failed**: only a main
effect of sound symbolism survived, F(1,107) = 7.81, p < .01, Frosh 62.4 versus
Frish 50.0, regardless of framing.

**Why this matters more than the usual retelling.** The paper is normally cited as
"Frosh beats Frish, so pick your vowels carefully." What it actually shows is that
the effect is **automatic but suppressible**, and it is suppressed exactly when the
audience is told the name is a name rather than a description, and when they have
the cognitive capacity to act on that. A developer or a technical buyer reading a
launch post about a newly coined capability name is close to the low-diagnosticity
condition with full cognitive capacity, which is the cell where the effect
disappeared. The authors are also explicit that they manipulated one phoneme in a
one-syllable word in a low-involvement consumer category chosen for exactly that
property.

**Klink, R. R. (2000).** "Creating Brand Names With Meaning: The Use of Sound
Symbolism." *Marketing Letters* 11(1), 5-20. DOI 10.1023/A:1008184423824.
**Full text paywalled; not read.** Yorkston and Menon describe it in the article
above: "Klink (2000) showed that the use of front vowels (as opposed to the back
vowels) in brand names conveys attribute qualities of smallness, lightness,
thinness, fastness, coldness, bitterness, femininity, weakness, lightness, and
prettiness," and Klink's design was within-subjects on attribute perceptions
rather than brand evaluations. I do not have Klink's sample size or statistics and
will not state one.

**Lowrey, T. M. and Shrum, L. J. (2007).** "Phonetic Symbolism and Brand Name
Preference." *Journal of Consumer Research* 34(3), 406-414. DOI 10.1086/518530.
Abstract verified, full text not read. Two experiments on fictitious brand names
differing only in vowel sound. The finding worth carrying is conditional rather
than absolute: participants preferred a name **more** when the connoted attribute
was positive for the category (small and sharp for a convertible or a knife) and
**less** when the same connotation was negative for the category (an SUV, a
hammer). Sound symbolism is not a quality ranking of sounds; it is a fit question
against what the category wants to signal.

**The honest caveat, stated once for all of section 4.** Every study here uses
undergraduate samples, fictitious consumer goods, single-phoneme manipulations,
and one-shot judgments. None of it is B2B, none is software, none involves a
multi-person purchase, a trial, or documentation. The direction of the effects is
consistent across independent labs and that is worth something. The magnitude in
a technical-buyer setting is unknown, and the moderator that most likely governs
it, diagnosticity, points toward the effect being smaller in B2B rather than
larger.

## 5. The counterweight: there is recent evidence for meaningless names, in technology

**Landgraf, P., Luffarelli, J. and Stamatogiannakis, A. (2026).** "Meaningless
brand names can spark consumer curiosity and improve brand evaluations."
*Journal of Business Research* 202. DOI 10.1016/j.jbusres.2025.115767. Abstract
and study structure verified; full text paywalled, so no effect size is carried
here.

The argument is that non-semantic names (their example pair is Leaf versus Leuf)
provoke curiosity, and curiosity increases the persuasiveness of information the
brand then supplies. The authors state they evaluate this "in the context of
technology brands." Study 1 is an observational analysis of **6,487 Kickstarter
campaigns** finding non-semantic-named brands raise more funding. Study 2
replicates experimentally, Study 3 tests the curiosity mechanism, and **Study 4
is the one that matters for a launch decision: the advantage of a non-semantic
name is attenuated when compelling brand information is absent.**

Read against section 4, these two literatures agree more than they appear to. A
coined name is a container. It performs when there is something behind it that
the audience then reads, and it does nothing when there is not. That is an
argument for coining a name only for a capability that has a real story attached,
and against coining one for an increment.

Caveats: Kickstarter consumer-hardware campaigns are not B2B software purchases,
Study 1 is observational and cannot rule out that better-funded and more
sophisticated teams both coin names and raise more, and I have not read the paper's
controls.

## 6. Brand architecture is a vocabulary, and it has no test behind it

**Aaker, D. A. and Joachimsthaler, E. (2000).** "The Brand Relationship Spectrum:
The Key to the Brand Architecture Challenge." *California Management Review* 42(4),
Summer 2000, pp. 8-23. DOI 10.1177/000812560004200401. Citation, venue, volume,
issue and pagination verified. Full text not read; the framework's structure is
consistent across every secondary description I checked.

The contribution is the spectrum itself: a continuum running from **House of
Brands** (fully separate brands, the parent invisible) through **Endorsed Brands**
and **Sub-brands** to **Branded House** (one master brand, descriptors underneath).
The paper defines brand architecture as an organizing structure specifying brand
roles and the relationships between them.

**What I could not find is any empirical test of it.** No study comparing
architectures on a business outcome, no conditions under which one is
demonstrably better, nothing that would let you predict which choice performs
better for a given company. What exists is a taxonomy plus case-based argument
from a highly credentialed author, and a large secondary literature that repeats
the taxonomy without adding evidence.

That is worth saying plainly because the framework is usually presented with the
authority of a finding. It is a vocabulary, and a good one. It makes the options
visible and it gives them names that a room can argue about. It does not tell you
which to pick, and any document that uses it to justify a choice is doing that
work with reasoning while wearing a citation.

**The relevance to a feature name is narrower than the framework's fame suggests.**
Most feature-naming decisions live entirely inside a Branded House already: the
company name carries, and the question is only whether the capability underneath
gets a proper name or a descriptor. The spectrum's interesting cases, endorsement
and separation, arise for acquisitions and for products aimed at a different buyer,
which is a different decision from the one in §1.

**One connection that is real.** A sub-brand inherits the parent's trademark
position but earns none of its own, and a descriptor is not a mark at all. So the
architecture choice and the *Abercrombie* choice in §2 are the same choice viewed
from two directions, and treating them as separate is how a company ends up with a
name it likes and cannot own.

## 7. Documented cases in developer tools and infrastructure

All of the following were verified in primary sources.

### The rename that froze the technical namespace: Azure AD to Microsoft Entra ID

Microsoft announced the rename on **2023-07-11** on its identity dev blog, with
SKU and service-plan display names changing **2023-10-01**. Stated reasons:
unifying identity products under one brand and reducing confusion with
on-premises Active Directory.

The instructive part is what did not change. Microsoft explicitly held "existing
login URLs, APIs, PowerShell cmdlets, and libraries" including MSAL, and kept
Microsoft Graph, Microsoft Identity Platform, and Azure AD B2C under their
existing names. Licensing, pricing, SLAs and deployments were untouched. This is
the cleanest documented example of separating the marketing surface from the
developer namespace during a rename, which is the mechanism that makes a rename
survivable in a developer product. [primary]

### The rename the community rejected: Docker to Moby

Solomon Hykes announced the Moby Project on **2017-04-18**, splitting Moby (for
system builders) from Docker (for application developers), with the assurance that
Docker "is staying exactly the same from a user's perspective." The
`moby/moby` PR that executed the rename was opened the same day and merged
**2017-04-20** with a single sentence of explanation.

The backlash is in the project's own tracker, which is what makes it citable
rather than anecdotal. Comments on the PR: "This is not gonna work nice for all
the projects that depend on github.com/docker/docker. No notice, nothing, and
just breaking everything." And, directly on the discoverability cost: "Now
everybody will have to filter a lot of search rubbish about musician, moby dick,
moby explorer." Issue **moby/moby#40222**, "Rename moby to docker," was opened
**2019-11-17** arguing that "Moby was a confusing rename that largely did not
contribute any value to the ecosystem." It carries the `roadmap` label and was
still open when checked. [primary]

The failure mode on display is not the name. It is a rename executed without
migration communications, in a namespace developers had already taken a
dependency on.

### Naming as the actual subject of litigation: Elastic and Amazon

Amazon launched "Amazon Elasticsearch Service" in 2015. Shay Banon, writing
**2021-01-19**: "We consider this to be a pretty obvious trademark violation,"
and the harm claimed was naming confusion specifically, "users thinking Amazon
Elasticsearch Service is actually a service provided jointly with Elastic, with
our blessing and collaboration. This is just not true." Elastic sued.

AWS announced OpenSearch on **2021-04-12**, stating "We plan to rename our
existing Amazon Elasticsearch Service to Amazon OpenSearch Service," and framed
the move around Apache 2.0 licensing rather than the trademark suit. The parties
settled, announced by Elastic on **2022-02-16**, with the result that "the only
Elasticsearch service on AWS and the AWS Marketplace is Elastic Cloud." [primary,
both sides]

Two things to take from it. A name derived from your own product's generic
category term is the hardest kind of name to defend and the most likely to be
used by someone else, and the two parties narrate the identical rename with
different stated causes, which is itself a lesson about reading rename
announcements.

### A rename driven purely by trademark distance: OpenTF to OpenTofu

The Linux Foundation announced OpenTofu on **2023-09-20**, describing it as
"Previously named OpenTF," in response to Terraform's move to BUSL v1.1. The
press release gives no reason for the rename. The reason is in reporting the same
day: Sebastian Stadil of Scalr, a fork organizer, said "HashiCorp has been super
aggressive in sending cease and desist out to a bunch of folks. And so we just
thought that TF was a little bit too close to Terraform." [primary for the
rename; secondary for the reason]

A project traded a descriptive, instantly-decodable abbreviation for a
deliberately non-descriptive coined name, purely to move away from a competitor's
mark. That is the *Abercrombie* trade-off being paid in public.

### The collision that was acknowledged and not fixed: Go

`golang/go` issue **#9**, filed **2009-11-11** by Francis McCabe days after Go's
launch: "I have been working on a programming language, also called Go, for the
last 10 years. There have been papers published on this and I have a book. I
would appreciate it if google changed the name of this language." The issue was
closed and labeled **"Unfortunate."** Google did not rename. [primary]

The citable artifact is the label. A prior-use collision was publicly acknowledged
as real and the answer was still no, which is a useful correction to the idea that
a collision automatically forces a rename.

### Category-creating names, and what is actually verifiable about them

Kubernetes is the standard example and only part of the usual story checks out.
The etymology is in Google's own launch post of **2014-06-11**: "Kubernetes
(koo-ber-nay'-tace) is Greek for 'helmsman' of a ship." Note that Google shipped a
pronunciation guide **inside the launch announcement**, which is a company
conceding on day one that its coined name failed the fluency test in section 3 and
choosing it anyway. The Borg lineage is confirmed in a Kubernetes blog post of
**2015-04-23**. The "Project Seven of Nine" codename and the claim that Google
legal rejected thirteen other candidate names are **not verified** and should not
be repeated (see the unusable list above).

### Criticism of opaque cloud service naming: what the evidence actually is

This argument is made constantly and the evidence for it is weak. What exists:

- A behavioral artifact. A third party built and maintains an "AWS in Plain
  English" translation table, explicitly because "with 50 plus opaquely named
  services, we decided that enough was enough and that some plain english
  descriptions were needed." Someone spending effort to build a decoder ring is
  better evidence than someone complaining, but it is still one artifact.
  [secondary artifact]
- Practitioner criticism. Corey Quinn, *Last Week in AWS*, **2026-02-23**, on
  stacked geological metaphors obscuring what services do. This is opinion and
  carries no fact. [opinion]

I could not find AWS itself publicly addressing its naming philosophy, and I could
not find any study measuring comprehension, time-to-find, or adoption against
service-name descriptiveness in any cloud catalog. **The claim that opaque cloud
service names cost discoverability is, as far as I can source it, unmeasured.**

### A vacated name is not a free name (added 2026-08-30)

AWS shipped **Database Migration Service Fleet Advisor** in preview in December
2021, for automated discovery and analysis of database and analytics workloads,
covering Microsoft SQL Server, MySQL, Oracle, and PostgreSQL servers. It then
retired the name. The end-of-support page states it plainly: "On May 20, 2026,
AWS will end support for AWS Database Migration Service Fleet Advisor. After
May 20, 2026, you will no longer be able to access the AWS DMS Fleet Advisor
console or AWS DMS Fleet Advisor resources," with new customers cut off a year
earlier on 2025-05-20 and existing projects pointed at AWS Migration Evaluator.
[primary]

**Why it belongs in a naming file.** A vendor abandoning a name does not return
the string to a clean state for the next claimant. The docs, the 2021
announcement, the 2023 target-recommendations release, and the AWS blog posts all
stay indexed and keep ranking, so a later product using the exact string competes
with several years of a hyperscaler's documentation for its own name. This is the
discoverability argument in §8 pointed the other way: the cost is not zero volume,
it is volume already resolving to someone else. It also cuts against the reflex
that a retired product clears a naming conflict. The trademark question is
separate and per class (§2), and abandonment there has its own evidentiary
standard that a support-end notice does not by itself establish.

Surfaced while screening umbrella-term candidates for a client launch, where one
candidate scored well on every axis until this check.

## 8. Discoverability: the argument is sound and the evidence is one anecdote

The claim is that a coined name launches with zero search volume attached to it,
competes against the descriptive phrase buyers actually type, and therefore costs
discovery until recognition catches up.

**I could not find a study measuring this.** No comparison of named against
descriptive features on organic search performance, no measurement of
time-to-recognition for a coined name, and nothing in any cloud catalog measuring
comprehension or time-to-find against name descriptiveness. As far as I can source
it, the discoverability cost of an opaque name is unmeasured. That is the finding.

What does exist, and it is worth more than the usual assertion:

**A developer complaint recorded in a project's own tracker.** On the Docker to
Moby rename PR (`moby/moby#32691`, April 2017), a commenter wrote: "Now everybody
will have to filter a lot of search rubbish about musician, moby dick, moby
explorer." That is a primary-source instance of exactly the predicted mechanism, a
coined name colliding with existing meanings and degrading search. It is one
comment on one rename. It is evidence and it is not a measurement.

**A behavioral artifact.** A third party built and maintains an "AWS in Plain
English" translation table because, in its own words, "with 50 plus opaquely named
services, we decided that enough was enough and that some plain english
descriptions were needed." Somebody spending sustained effort to build a decoder
ring is stronger evidence than somebody complaining about the need for one, and it
is still a single artifact.

**A company conceding the point on launch day.** Google's Kubernetes announcement
(2014-06-11) shipped a pronunciation guide inside the announcement itself:
"Kubernetes (koo-ber-nay'-tace) is Greek for 'helmsman' of a ship." A launch post
that has to teach you to say the name is the fluency cost of §3 being paid in
public, by a company that chose to pay it anyway and won the category regardless.
Both halves of that sentence matter.

**The practical resolution, marked as reasoning.** Ship the name and the
descriptive phrase together every time until the name carries alone, and treat
"appears in search queries and third-party writing without the descriptor" as the
observable condition for stopping. I can find no evidence for or against this
practice. It is mechanism, and the §5 finding is the closest thing to support:
a coined name performs when there is information behind it for the curious reader
to land on.

## 9. Name screening in practice

This section is the weakest on the page and I want that visible. What follows is
assembled from primary law plus the documented cases in §7, and it has no
practitioner survey or process research behind it. No source I found describes how
software companies actually run naming decisions, who decides, or how often
clearance kills a name.

**The ecosystem's own trademark policy is a screening input, and it is free to
read (added 2026-08-30).** An open-source project with a foundation behind it
often publishes one, and it can be stricter than trademark law requires. The
PostgreSQL policy is a worked instance: "the terms *Postgres* and *PostgreSQL* and
the Elephant Logo (Slonik) are all registered trademarks of the PostgreSQL
Community Association of Canada," it instructs "do not use the marks in a business
name or trade name" and "do not seek to register any trademark containing one of
our marks or a variant thereof," and it requires prior approval to use the marks
"or some variant of them" in a company, product, or domain name. [primary]

Two consequences that generalise past Postgres. A descriptive phrase built on the
mark stays usable in copy while being unregistrable, which is a real argument for
choosing a phrase over a name when the category word belongs to somebody else. And
where a mark is closed, ecosystems evolve a prefix convention around it: the
Postgres tool namespace runs on `pg` (pgAdmin, pgBouncer, pgHero, pgDash,
pgMustard, pgvector, pgBackRest), which reads as native to the audience
and sidesteps the mark. Whether the prefix counts as "a variant thereof" under a
policy written that broadly is the open question, and it is answered by the
project's own community rather than by reading the policy harder.

**What is genuinely established, from §2 and §7:**

- **Clearance is a legal gate with a real failure mode, and the failure lands
  years later.** The Elastic and Amazon dispute (2015 to 2022) turned on naming
  confusion specifically, and it ran for years. A name built from the category's own
  generic term is the hardest to defend and the likeliest to be taken.
- **The category determines the answer, so screening has to be per-category.**
  *Abercrombie* held SAFARI generic for hats and jackets and valid for boots,
  luggage, tents and tobacco simultaneously. A name that clears in one class says
  nothing about another.
- **Prior use does not automatically force a rename.** `golang/go` issue #9
  documented a decade-old prior language named Go, and the issue was closed with
  the label "Unfortunate." A collision is a risk to be priced rather than an
  automatic veto.
- **Trademark distance can be the whole reason for a name.** OpenTF became
  OpenTofu to move away from Terraform's mark, trading an instantly decodable
  abbreviation for a coined name. Sourced primary for the rename, secondary for the
  reason.

**On renaming, which is the same problem run backwards.** The two documented cases
point in opposite directions and the difference is the mechanism worth carrying.
Microsoft's Azure AD to Entra ID rename (announced 2023-07-11) explicitly froze
login URLs, APIs, PowerShell cmdlets and libraries, changing the marketing surface
while leaving the developer namespace alone. Docker's Moby rename moved the
namespace developers had taken a dependency on, with one sentence of explanation,
and the project's own tracker still carries an open issue asking for it to be
reversed. **The separable claim: a rename survives when the technical namespace
does not move, and the cases documented here are consistent with that.** Two cases
is not a finding.

**What is owed.** Whether trademark clearance, domain and handle availability, and
cross-language linguistic screening are worth their cost, and at what point in the
process they run. Nothing on this page answers that.

## What I could not access

- **Klink 2000 full text.** *Marketing Letters* via Springer, auth-walled;
  Ovid returned HTTP 402. Substitute quality: weak. Carried only through Yorkston
  and Menon's description. No sample size or statistic is stated for it here.
- **Lowrey and Shrum 2007 full text.** Oxford Academic, abstract only.
- **Landgraf, Luffarelli and Stamatogiannakis 2026 full text.** ScienceDirect,
  abstract only via RePEc. The widely repeated 17% funding figure was not
  verified in a source I read and is deliberately omitted.
- **Shrum, Lowrey, Luna, Lerman and Liu (2012), "Sound symbolism effects across
  languages: Implications for global brand names,"** *International Journal of
  Research in Marketing*, DOI 10.1016/j.ijresmar.2012.03.002. Citation and
  authorship verified via the Semantic Scholar API; the abstract is publisher-
  restricted and ScienceDirect returned 403. This is the paper most likely to
  bound the cross-language generalizability of section 4, and its finding is not
  stated anywhere on this page because I could not read it. Largest single gap.
- **Alter, A. L. and Oppenheimer, D. M. (2009), "Uniting the Tribes of Fluency to
  Form a Metacognitive Nation,"** *Personality and Social Psychology Review*, DOI
  10.1177/1088868309341564. This is the review that would have carried the
  "broader fluency literature" part of section 3. SAGE returned 403 and the
  author's institutional page returned empty. Author and year named, nothing
  claimed from it.
- **The Abercrombie opinion on Justia, CourtListener HTML, OpenJurist, Casetext,
  and Google Scholar.** All returned 403, 401, or empty. Read instead via WIPO
  Lex's hosted text of the judgment, which is a primary host.
- **GeekWire's 2016 Kubernetes naming article.** 403. See the unusable list.
- **The Weaveworks GitOps coining post.** Domain parked, Medium mirror 403,
  Internet Archive unavailable in this environment. GitOps origin unverified; the
  CNCF GitOps Working Group site gives four principles and attributes the term to
  nobody.
- **ACM Queue, "Borg, Omega, and Kubernetes."** 403.
- **An OpenTofu-authored account of its own rename.** Their blog no longer lists
  2023 posts. The reason is secondhand only.

## Related Pages

- [The launch campaign protocol](../protocols/05-launch-campaign.md) (step 3, the naming gate this page sources)
- [`study/17-naming.md`](../study/17-naming.md) (method and interview framing, written from
  this page on 2026-08-26)
- [`competitive-research-methods.md`](competitive-research-methods.md)
  (evidence tiers, and the trademark and comparative-advertising law that the
  legal gate inherits)
- [`llm-search-visibility.md`](llm-search-visibility.md) (the answer-engine surface a
  new name has to reach)

## Bibliography

**Primary law**

- [Abercrombie & Fitch Co. v. Hunting World, Inc., 537 F.2d 4 (2d Cir. 1976)](https://www.wipo.int/wipolex/en/text/581586) · U.S. Court of Appeals for the Second Circuit, 1976-01-16, hosted by WIPO Lex. Accessed 2026-08-26. [primary]
  Used for: §2, the four-category spectrum, the "lines of demarcation are not always bright" passage, the SAFARI holding, and genericness as irreversible.
- [Abercrombie & Fitch Co. v. Hunting World, Inc. · WIPO Lex record](https://www.wipo.int/wipolex/en/judgments/details/925) · WIPO. Accessed 2026-08-26. [primary]
  Used for: §2, citation verification (537 F.2d 4, decided 1976-01-16, Second Circuit, keyword "spectrum of distinctiveness").
- [15 U.S.C. §1052 (Lanham Act §2)](https://www.law.cornell.edu/uscode/text/15/1052) · Cornell Legal Information Institute. Accessed 2026-08-26. [primary]
  Used for: §2, subsection (e)(1) on merely descriptive marks and subsection (f) on acquired distinctiveness including the five-year provision.
- [15 U.S.C. §1091 (Supplemental Register)](https://www.law.cornell.edu/uscode/text/15/1091) · Cornell Legal Information Institute. Accessed 2026-08-26. [primary]
  Used for: §2, the "capable of distinguishing" eligibility standard.
- [15 U.S.C. §1094](https://www.law.cornell.edu/uscode/text/15/1094) · Cornell Legal Information Institute. Accessed 2026-08-26. [primary]
  Used for: §2, the enumerated list of advantages withheld from supplemental registrations.
- [15 U.S.C. §1095](https://www.law.cornell.edu/uscode/text/15/1095) · Cornell Legal Information Institute. Accessed 2026-08-26. [primary]
  Used for: §2, supplemental registration does not preclude the Principal Register and is not an admission of non-distinctiveness.
- [Strong trademarks](https://www.uspto.gov/trademarks/basics/strong-trademarks) · United States Patent and Trademark Office, page last updated 2023-11-30. Accessed 2026-08-26. [primary]
  Used for: §2, the agency's own restatement of the spectrum with examples, and its "remember, pronounce, and spell" guidance.

**Academic**

- [Predicting short-term stock fluctuations by using processing fluency](https://www.pnas.org/doi/10.1073/pnas.0601071103) · Alter, A. L. and Oppenheimer, D. M., *PNAS* 103(24), 9369-9372, 2006-06-13. Full text read at [PMC1482615](https://pmc.ncbi.nlm.nih.gov/articles/PMC1482615/). Accessed 2026-08-26. [primary]
  Used for: §3, all three studies, samples, coefficients, time windows, dollar figures, and the decay beyond one week.
- [A Sound Idea: Phonetic Effects of Brand Names on Consumer Judgments](https://academic.oup.com/jcr/article-abstract/31/1/43/1812051) · Yorkston, E. and Menon, G., *Journal of Consumer Research* 31(1), 43-51, June 2004. Full text read via the Stanford course copy at [web.stanford.edu/class/linguist62n/yorkston.pdf](https://web.stanford.edu/class/linguist62n/yorkston.pdf). Accessed 2026-08-26. [primary]
  Used for: §4, both studies, samples of 126 and 111, the Frish/Frosh manipulation, all reported F statistics and means, the diagnosticity and cognitive-load moderators, and the unawareness finding.
- [Creating Brand Names With Meaning: The Use of Sound Symbolism](https://doi.org/10.1023/A:1008184423824) · Klink, R. R., *Marketing Letters* 11(1), 5-20, 2000. Accessed 2026-08-26. [primary, NOT READ, paywalled]
  Used for: §4, front-vowel attribute associations, carried only through Yorkston and Menon's description of it. No sample or statistic stated.
- [Phonetic Symbolism and Brand Name Preference](https://academic.oup.com/jcr/article-abstract/34/3/406/1798924) · Lowrey, T. M. and Shrum, L. J., *Journal of Consumer Research* 34(3), 406-414, October 2007. DOI 10.1086/518530. Accessed 2026-08-26. [primary, abstract only]
  Used for: §4, the conditional finding that vowel connotation helps or hurts depending on category fit.
- [Meaningless brand names can spark consumer curiosity and improve brand evaluations](https://ideas.repec.org/a/eee/jbrese/v202y2026ics0148296325005909.html) · Landgraf, P., Luffarelli, J. and Stamatogiannakis, A., *Journal of Business Research* 202, 2026. DOI 10.1016/j.jbusres.2025.115767. Accessed 2026-08-26. [primary, abstract only]
  Used for: §5, the four-study structure, the 6,487-campaign Kickstarter sample, the technology-brand context, and Study 4's attenuation finding.

- [The Brand Relationship Spectrum: The Key to the Brand Architecture Challenge](https://journals.sagepub.com/doi/10.1177/000812560004200401) · Aaker, D. A. and Joachimsthaler, E., *California Management Review* 42(4), Summer 2000, pp. 8-23. DOI 10.1177/000812560004200401. Accessed 2026-08-26. [primary, citation and venue verified, full text not read]
  Used for: §6, the House of Brands to Branded House spectrum and the definition of brand architecture. No empirical test of the framework was found; §6 says so.

**Cases in dev tools and infrastructure**

- [The new name for Azure AD is Microsoft Entra ID](https://devblogs.microsoft.com/identity/aad-rebrand/) · Microsoft Identity Platform blog, 2023-07-11. Accessed 2026-08-26. [primary]
  Used for: §7, the rename, its stated reasons, the 2023-10-01 SKU change date, and the explicit freeze on login URLs, APIs, PowerShell cmdlets, and libraries.
- [Introducing the Moby Project](https://www.docker.com/blog/introducing-the-moby-project/) · Hykes, S., Docker blog, 2017-04-18. Accessed 2026-08-26. [primary]
  Used for: §7, the Moby/Docker split and the "staying exactly the same from a user's perspective" claim.
- [moby/moby PR #32691](https://github.com/moby/moby/pull/32691) · GitHub, opened 2017-04-18, merged 2017-04-20. Accessed 2026-08-26. [primary]
  Used for: §7, the one-sentence rename rationale and the verbatim community objections about dependency breakage and search pollution.
- [moby/moby issue #40222, "Rename moby to docker"](https://github.com/moby/moby/issues/40222) · GitHub, opened 2019-11-17. Accessed 2026-08-26. [primary]
  Used for: §7, a rename still contested in the project's own tracker two years later, labeled `roadmap`.
- [Why license change? AWS, Elasticsearch, and open source](https://www.elastic.co/blog/why-license-change-aws) · Banon, S., Elastic, 2021-01-19. Accessed 2026-08-26. [primary]
  Used for: §7, the trademark-violation claim and the naming-confusion harm.
- [Introducing OpenSearch](https://aws.amazon.com/blogs/opensource/introducing-opensearch/) · Meadows, C. et al., AWS Open Source blog, 2021-04-12. Accessed 2026-08-26. [primary]
  Used for: §7, AWS's announcement of the rename and its licensing framing.
- [Elastic and Amazon reach agreement on trademark infringement lawsuit](https://www.elastic.co/blog/elastic-and-amazon-reach-agreement-on-trademark-infringement-lawsuit) · Banon, S. and Kulkarni, A., Elastic, 2022-02-16. Accessed 2026-08-26. [primary]
  Used for: §7, the settlement outcome.
- [Announcing OpenTofu](https://www.linuxfoundation.org/press/announcing-opentofu) · The Linux Foundation, 2023-09-20. Accessed 2026-08-26. [primary]
  Used for: §7, the rename from OpenTF, with no stated reason.
- [OpenTF renames to OpenTofu](https://www.theregister.com/2023/09/20/terraform_fork_opentf_opentofu/) · Claburn, T., *The Register*, 2023-09-20. Accessed 2026-08-26. [secondary]
  Used for: §7, Sebastian Stadil's stated trademark-distance reason for the rename.
- [golang/go issue #9](https://github.com/golang/go/issues/9) · GitHub, filed 2009-11-11 by Francis McCabe. Accessed 2026-08-26. [primary]
  Used for: §7, the prior-use naming collision, the verbatim request, and the "Unfortunate" label.
- [An update on container support on Google Cloud Platform](https://opensource.googleblog.com/2014/06/an-update-on-container-support-on.html) · Brewer, E., Google Open Source blog, 2014-06-11. Accessed 2026-08-26. [primary]
  Used for: §7, the Kubernetes name announcement, the Greek etymology, and the pronunciation guide shipped in the launch post.
- [Borg: The Predecessor to Kubernetes](https://kubernetes.io/blog/2015/04/borg-predecessor-to-kubernetes/) · Kubernetes blog, 2015-04-23. Accessed 2026-08-26. [primary]
  Used for: §7, the Borg lineage.
- [AWS in Plain English](https://expeditedsecurity.com/aws-in-plain-english/) · Expedited Security, no date shown. Accessed 2026-08-26. [secondary artifact]
  Used for: §7, a third party building a naming decoder for a cloud catalog, and the "50 plus opaquely named services" quote.
- [Agents, Plugins, and AgentCore: AWS Has an AI Naming Problem](https://www.lastweekinaws.com/newsletter/agents-plugins-and-agentcore-aws-has-an-ai-naming-problem/) · Quinn, C., *Last Week in AWS*, 2026-02-23. Accessed 2026-08-26. [opinion]
  Used for: §7, practitioner criticism of stacked metaphors in service naming. Carries no fact.

**Rejected, recorded so the next pass does not re-find them**

- [The AWS Service I Hate the Most](https://www.lastweekinaws.com/blog/the-aws-service-i-hate-the-most/) · Quinn, C., 2022-01-05. Accessed 2026-08-26. [opinion, REJECTED]
  Frequently cited as AWS naming criticism. It is about Isengard being internal-only and it praises the name. Not usable for a naming argument.
- [DevOpsDays Ghent 2009](http://legacy.devopsdays.org/events/2009-ghent/) · devopsdays. Accessed 2026-08-26. [primary, REJECTED for the claim it is usually cited for]
  Confirms the inaugural event. Does not name Patrick Debois and does not date the coining of "DevOps."
- [Google SRE Book, Introduction](https://sre.google/sre-book/introduction/) · Treynor Sloss, B., Google. Accessed 2026-08-26. [primary, REJECTED for the coining claim]
  Identifies Treynor Sloss as founder of Google SRE. Does not state when the term was coined.
- [OpenGitOps](https://opengitops.dev/) · CNCF GitOps Working Group. Accessed 2026-08-26. [primary, insufficient]
  Gives four principles, attributes the term to nobody. GitOps origin remains unverified.

Last updated: 2026-08-26
