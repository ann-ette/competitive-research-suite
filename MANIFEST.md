# Manifest

Cut 2026-09-30 from the Lantern Works working repo by `cut-research-suite.py`.

Each row: SHA-256 of the canonical source at cut time, the path inside this package, the canonical source path. The copies here carry generalizations (paths, tool names, one client detail) applied by the cut script; the hash is of the source before those edits, so it tells you whether canon has moved on since the cut, and the script is where to look for what changed on the way in.

`prompts/README.md`, `README.md`, `CONTRIBUTING.md`, and `LICENSE.md` have no canonical source; the first is generated from the protocols at cut time and the other three are authored for this package.

| SHA-256 (source) | Package path | Canonical source |
|---|---|---|
| `19282d36d813e6e3…` | `protocols/01-research-elicitation.md` | `research-elicitation-protocol.md` |
| `aa3703e45232273f…` | `protocols/02-research.md` | `RESEARCH-PROTOCOL.md` |
| `d82e5e0d5d8b30d8…` | `protocols/03-options-review.md` | `OPTIONS-REVIEW-PROTOCOL.md` |
| `0dd306cf9d7ff99b…` | `protocols/04-competitive-research.md` | `COMPETITIVE-RESEARCH-PROTOCOL.md` |
| `79c08cac7911e431…` | `protocols/05-launch-campaign.md` | `LAUNCH-CAMPAIGN-PROTOCOL.md` |
| `36c1a9f51a9f0922…` | `study/09-competitive-intelligence.md` | `product-marketing-wiki/09-competitive-intelligence.md` |
| `27b6eafd00187b75…` | `study/15-competitive-research-execution.md` | `product-marketing-wiki/15-competitive-research-execution.md` |
| `e3d1189d7d508807…` | `study/16-campaigns-and-channels.md` | `product-marketing-wiki/16-campaigns-and-channels.md` |
| `a7db038b015abc75…` | `study/17-naming.md` | `product-marketing-wiki/17-naming.md` |
| `7e10d41237007be8…` | `study/18-developer-marketing.md` | `product-marketing-wiki/18-developer-marketing.md` |
| `94af48502e6ae506…` | `research/competitive-research-methods.md` | `_Knowledge-Base/Industries/Competitive-Research-Methods/ci-methodology-and-sourcing.md` |
| `b4725f0c8edd3587…` | `research/product-naming.md` | `_Knowledge-Base/Industries/Product-Naming/README.md` |
| `9e0b931327c28db3…` | `research/llm-search-visibility.md` | `_Knowledge-Base/Industries/LLM-Search-Visibility/README.md` |

Full hashes:

```
19282d36d813e6e362b4b5dc5ee6c3d06e78ad315716c4f08921684f53f16ba5  protocols/01-research-elicitation.md
aa3703e45232273f29b6026d8cbb96fc1ad7176ee1c366f33e26d84ca4c13a1b  protocols/02-research.md
d82e5e0d5d8b30d8d17467109e4cf9e065ac4dd52c5438cfc934d6475d1bbbc3  protocols/03-options-review.md
0dd306cf9d7ff99bfd56418aa8219656760242c475d9d695514180346c76701f  protocols/04-competitive-research.md
79c08cac7911e431f6057282aad18b654615187e82112fc6f9f43f9a4752ef73  protocols/05-launch-campaign.md
36c1a9f51a9f0922b8a521536a15fb8708897e8f1ee051fc88200dd163eb7841  study/09-competitive-intelligence.md
27b6eafd00187b75bb3d5b787fb7ba2de4e53e02f2990382870dd97a2236d518  study/15-competitive-research-execution.md
e3d1189d7d5088076a26a5c177df0ce20aaf56b252c0416228ea8bff058e70b4  study/16-campaigns-and-channels.md
a7db038b015abc75ecc8e5658ecdfee55d8b0bc5b36823006ec9a232ab59903e  study/17-naming.md
7e10d41237007be8169e792a0beb96919749d6a9ca45fe6f23235751e52a0c89  study/18-developer-marketing.md
94af48502e6ae50616b78fc7097165d9e23852d7a797ef5245ea7d57f19c3fa5  research/competitive-research-methods.md
b4725f0c8edd35872c42ac33f1a5131a23db6108cb9e8ea73600011609dae51e  research/product-naming.md
9e0b931327c28db3e2e71d7f2e0403f3f50e02d874a856fea4735c984085ecd7  research/llm-search-visibility.md
```
