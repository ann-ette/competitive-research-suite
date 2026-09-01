# Contributing

This package is a cut from a working repo, and the copies here are downstream of it. That shapes what a good contribution looks like and how it lands.

## What Is Welcome

- **A sourced correction.** A claim in a protocol, a study page, or a research page that a primary source contradicts. Name the source, quote the line, say what the corrected claim is. A correction with a link that resolves is the highest-value change this package can receive.
- **A worked pass, de-identified.** The protocols say "protocol plus one worked pass, or it does not count," and they mean it. A pass you ran under one of them, with the client and every competitor reduced to its role, is welcome as a folder under `worked-examples/` once that folder exists. Include: decision sentence, roster with evidence, axes as declared, verdicts that moved and why, what you could not access.
- **A prompt that ran.** A variant of a P-series prompt that produced a better record on a real pass, with a sentence on what it fixed.
- **A study-page amendment.** The pages carry dated in-line amendments (`**Amended YYYY-MM-DD**`), and a silent rewrite destroys the record of what the page said before. Follow that shape.

## What Will Be Declined

- Vendor content marketing as a source for anything above the E5 tier the competitive protocol defines. A vendor's page is a primary source about what the vendor claims and nothing else.
- A number synthesized from a vague source. "Several days" does not become "48 to 72 hours."
- A rewrite of an evidence-status table that removes a `[reasoning]` mark without adding the research that earns the removal.
- A competitor named in a protocol. The protocols are vendor-agnostic by design, and the worked examples carry the names as roles.

## House Rules for Prose

- No em dashes, and no space-hyphen-space either, since that is the substitution models reach for when told the first one is banned. Use a period, a comma, a semicolon, or parentheses.
- Headers in Title Case; body prose in sentence case.
- Every empirical claim carries an author and a year inline, and every statistic links to a source that resolves. When no verified source exists, name the author and year and stop; never construct a plausible-looking link.
- Absence claims are the highest-risk claims in any of these documents. Phrase every one as a statement about a named source on a named date.
- Mark reasoning as `[reasoning]` where it sits. A document in this style reads as sourced whether or not it is.

## How Canon Works

The canonical versions of every file under `protocols/`, `study/`, and `research/` live in my working repo, and `MANIFEST.md` records the hash of each source at cut time. When a change is accepted here, I apply it to the canonical file and re-cut, so the package and canon stay one thing. A pull request against a copy is the right way to propose the change; it lands by way of the source, and the copy is regenerated.

If a manifest hash no longer matches its source, the copy is behind canon and a fresh cut is owed.
