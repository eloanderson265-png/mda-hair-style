# AI Search Discoverability

Checked against official documentation on 2026-09-12. Vendors change these; re-check
before acting on anything here more than a few months from now.

---

## First, an honest statement of what is and isn't possible

Nobody can guarantee that ChatGPT, Gemini, Claude or Perplexity will mention your
business. There is no submission form, no ranking to buy, and no file you can add that
forces inclusion. Anyone who tells you otherwise is selling something.

Specifically, **none** of the following are guaranteed routes into AI answers:

- `llms.txt` or similar proposed files — not an agreed standard, not honoured by the
  major assistants
- Structured data (schema) — genuinely useful for search engines; not a lever for AI
  assistants
- Repeating keywords, or publishing AI-written articles at volume

What you *can* control is whether the crawlers are permitted to reach you, and whether
what they find is accurate, specific and consistent. That is the whole of it.

## The distinction you need to decide on

Two different things are often confused:

| | **Search discovery** | **Model training** |
|---|---|---|
| What it does | Lets the assistant find, cite and link your site when answering a live question | Lets your content be used to train future AI models |
| Benefit to you | Direct — you can be cited and clicked | Indirect and unmeasurable |
| Separate control? | Yes, for the major vendors | Yes |

**You can allow one and refuse the other.** Most businesses that want visibility allow
search discovery. Whether to allow training is a preference, not a marketing decision —
it will not measurably change how often you are cited today.

## The actual crawlers, per current official docs

| User-agent | Vendor | Purpose | Recommended |
|---|---|---|---|
| `Googlebot` | Google | Google Search, Images, News, Discover | **Allow** |
| `Google-Extended` | Google | Training Gemini models, and grounding | Your choice |
| `OAI-SearchBot` | OpenAI | "surface websites in search results in ChatGPT's search features" | **Allow** |
| `ChatGPT-User` | OpenAI | Fetches a page when a user's question requires it | **Allow** |
| `GPTBot` | OpenAI | Training foundation models | Your choice |
| `Claude-SearchBot` | Anthropic | "improve search result quality for users" | **Allow** |
| `Claude-User` | Anthropic | Fetches a page when a user asks Claude something | **Allow** |
| `ClaudeBot` | Anthropic | Training | Your choice |
| `PerplexityBot` | Perplexity | "surface and link websites in search results on Perplexity. It is not used to crawl content for AI foundation models." | **Allow** |
| `Perplexity-User` | Perplexity | Visits a page to answer a user's question | **Allow** |

**Important:** Google states plainly that `Google-Extended` *"does not impact a site's
inclusion in Google Search nor is it used as a ranking signal in Google Search."*
Blocking it costs you nothing in Google Search.

Sources:
- https://developers.openai.com/api/docs/bots
- https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler
- https://developers.google.com/search/docs/crawling-indexing/google-common-crawlers
- https://docs.perplexity.ai/guides/bots

## Your current position

Your `robots.txt` reads:

```
User-Agent: *
Allow: /

Host: https://burjalfalahtech.com
Sitemap: https://burjalfalahtech.com/sitemap.xml
```

**Every crawler above is already allowed**, including all the search ones.
**No change is required** for AI search discovery. This is already correct.

The only decision left is whether you want to *refuse training*. Two options:

**Option A — leave it exactly as is.** Everything allowed, including training.
Nothing to do.

**Option B — allow search and AI answers, refuse training.** Append:

```
# Training crawlers — disallowed. Search and user-initiated crawlers stay allowed above.
User-agent: GPTBot
Disallow: /

User-agent: ClaudeBot
Disallow: /

User-agent: Google-Extended
Disallow: /
```

This keeps `OAI-SearchBot`, `Claude-SearchBot`, `PerplexityBot`, `Googlebot` and the
user-initiated agents fully allowed, so it does **not** reduce your chance of being
cited in AI answers or found in Google.

**This is your call — tell me A or B and I'll prepare the exact file.**
Note that `robots.txt` is a request, not enforcement. Well-behaved crawlers honour it;
others ignore it entirely.

## What genuinely helps you get cited

Assistants cite sources that answer a specific question clearly and verifiably. Your
best assets are the things only you have:

1. **Real project detail** — 19 projects with actual scope, location, duration and
   materials beats any amount of generic copy.
2. **Direct answers to real buyer questions** — your FAQ structure is already right;
   it needs depth. "How long does a villa kitchen replacement take?" answered concretely
   is citable. "We deliver quality solutions" is not.
3. **Consistency everywhere** — name, address and phone identical on your site, Google
   Business Profile, Instagram and every directory. Contradictions make you a weaker
   candidate for citation.
4. **Being findable in ordinary search first.** Assistants lean heavily on conventional
   search and on Maps data. Search Console, a clean sitemap and a Google Business
   Profile do more for AI visibility than anything AI-specific.

## How we will measure it — honestly

You cannot "rank" in an AI assistant. There is no position to track; two people asking
the same question can get different answers, and the same question asked twice can
differ. So we sample and log, and treat it as a rough signal only.

**Fixed question set**, asked the same way each month:

1. fit out company in Sharjah
2. bespoke joinery Dubai
3. who can build a custom wardrobe in Sharjah
4. villa renovation contractor Ajman
5. apartment kitchen replacement Dubai cost
6. SPC flooring installer Sharjah
7. office fit out contractor Sharjah industrial area
8. best joinery workshop near Al Sajaa

**Log for each**, in `ai-visibility-log.csv`:

| Field | Why |
|---|---|
| Date | Results drift over time |
| Platform | ChatGPT / Gemini / Claude / Perplexity |
| Web search on or off | Changes the answer completely — record it every time |
| Question, verbatim | Rewording changes results |
| Were we mentioned? | yes / no |
| Were we cited with a link? | A citation is worth far more than a mention |
| Which competitors appeared | The genuinely useful output |
| Sources cited | Shows which sites these systems trust for your market |

**How to read it:** as a directional signal, nothing more. A month where you appear in
three of eight is not a "ranking", and a month where you disappear is not necessarily a
decline. The competitor and source columns are the most valuable part — they show where
your market's visibility actually lives.
