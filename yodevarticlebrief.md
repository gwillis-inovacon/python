# yodevarticlebrief

# Article brief — "Mejor IA para programar"

Paste this into the yoDEV publishing project. It carries the research context;
your existing publishing and indexing steps stay unchanged.

***

## The target

**Primary query:** `mejor ia para programar` — 1,300 searches/month (Spain, es),
keyword difficulty **0**.

**Language: Spanish. Not English.** This is the decision, and it is
counter-intuitive, so here is the evidence:

* `cursor vs claude code` gets 8,100/mo in English and 320/mo in Spanish.
* But searching **from Spain, in Spanish**, Google returns twenty results and
  **every single one is English** — Reddit, builder.io, SitePoint, DataCamp,
  dev.to, Medium, Hacker News.
* There is no Spanish-language competition in this niche at all. That is why
  difficulty is 0.

So we are not fighting for scraps of a big English market. We are writing the
Spanish answer that does not currently exist. English versions are generated
automatically from the Spanish original, so nothing is lost by writing in
Spanish — write it once, well, in Spanish.

## Why this shape, specifically

Measured across 104,539 community impressions (Jun–Sep 2026):

| query shape                              | CTR        |
| ---------------------------------------- | ---------- |
| bare tool name (`markitdown`, `caveman`) | **0.72%**  |
| question / how-to                        | 2.33%      |
| **comparison / "best X" listicle**       | **12.26%** |

Comparisons and "mejor/mejores" listicles convert **17× better** than tool
names. Our single best-performing article of this type, `opencode vs crush`,
earns 21% CTR and carries \~3.5% of all site traffic on its own.

The reason is intent. Someone searching a tool name wants that tool's own site
and will never click us. Someone searching *"which is best"* wants exactly what
we can provide: an opinionated comparison from people who use these daily.

## Audience and voice — hard rules

* **Neutral Spanish. NEVER Argentinian voseo** (`tenés`, `podés`, `vos`).
  Readers have complained about this before. Use `tienes`, `puedes`, `tú`.
* **Proper accents throughout.** Accentless Spanish reads as careless.
* Readers are \~95% working developers across Iberoamérica. Assume competence;
  do not explain what an IDE or an LLM is.
* Do not copy the register of neighbouring articles — write it clean.

## What makes this article good, not just optimised

The SEO framing gets it found. These make it worth reading:

* **Take a position.** "It depends" is the failure mode of every comparison
  article on this SERP. Say who each tool is actually for, and be willing to
  say which one you would pick and why.
* **Ground it in real use.** We run these tools daily. Concrete specifics —
  what broke, what surprised us, where one saved real time — is the one thing
  the English incumbents cannot copy from us.
* **Never fabricate benchmarks, token counts, or pricing.** If a number is
  quoted, it must be from the vendor's own docs or a test we actually ran, and
  dated. Invented figures are the fastest way to lose a technical audience.
* **Date it and state the versions.** This topic moves monthly; an undated
  comparison is worthless within a quarter. The competing articles all carry
  visible dates.

## Structure

* **Headings should be the questions people type.** Our own data shows articles
  are rewarded when the H2 matches the query — `¿Cuál es la mejor IA para
  programar?`, `¿Cuál conviene para trabajo en equipo?`, `¿Cuál es más barata?`
* Lead with a short answer near the top. Both this SERP and the AI Overview
  reward content that answers directly rather than building up to it.
* A comparison table is expected on this query — every competitor has one.
* Cover at minimum: Claude Code, Cursor, Codex, GitHub Copilot. These are what
  the audience is choosing between, and each is a topic we already publish on.

## Internal linking

Link to our existing coverage — it is substantial and currently disconnected:
**118 topics tagged&#x20;****`claude-code`**, 32 `cursor`, 30 `codex`, plus
`github-copilot`. Deep links to specific articles, not tag pages.

⚠️ **Do not link to&#x20;****`/tag/`****&#x20;pages.** They were noindexed on 2026-09-08 — they
earned zero clicks in three months and competed with the articles themselves.

## Translation-awareness

The article is auto-translated into English and Portuguese and those versions
are indexed separately. Write Spanish that survives translation: clear
sentences, few idioms, no wordplay that only works in one language. Technical
terms and product names stay in English (`prompt`, `commit`, `Claude Code`).

## What NOT to do

* Do not target the bare tool names (`claude code`, `cursor`). We already rank
  for those with six-figure impressions and 0.72% CTR — that traffic is
  navigational and unwinnable, and chasing it wastes the article.
* Do not write a neutral roundup that avoids conclusions.
* Do not pad for length. The competing articles are 1,500–2,500 words; match
  the depth, not a word count.

## How we will know it worked

Tracked on YOD-522. The signal is **`mejor ia para programar`****&#x20;appearing in
Search Console with a CTR above 4%** within 4–8 weeks — not raw impressions,
which on this property are dominated by unwinnable tool-name queries.

⚠️ Expect below our usual 12% comparison CTR: this SERP carries an AI Overview,
which our niche comparisons do not.

***

## Next in the queue (same treatment)

1. `cursor vs claude code` — 320/mo ES, KD 0
2. `claude code vs codex` — 320/mo ES, KD 6
