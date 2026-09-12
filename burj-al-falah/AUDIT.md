# Search Visibility Audit — burjalfalahtech.com

Crawled 2026-09-12. 12 of 32 pages fetched and inspected directly; sitemap, robots,
schema, headers and image assets checked against the live site.

**No rankings, AI recommendations, or lead volumes are promised anywhere in this
document.** Search and AI systems decide what to show; we control correctness,
clarity, evidence and measurement.

---

## Verdict

The site is **technically well built** — better than most small UAE contractor sites.
The SEO fundamentals are already in place and do not need rebuilding.

Its main weaknesses are **no measurement at all**, **no written enquiry route**, and a
**second, fictional business published under the same phone number**.

---

## 🔴 Critical — fix before anything else

### C1. A second, fictional business is published using your phone number
*(Revised 2026-09-12 after the owner confirmed the salon is not a real business.)*

The WhatsApp number on the site, **+971 52 989 6076**, is confirmed as genuinely yours,
so the WhatsApp links are **correct**. No change needed there.

The problem is the other end. A page for *"MDA Hair Style — Ladies Hair Salon in
Sharjah"* is **live and publicly crawlable** at
`https://eloanderson265-png.github.io/mda-hair-style/`. It carries no `noindex` tag, so
search engines are free to index it. That page publishes:

- A business that **does not exist**
- **Your** WhatsApp number, +971 52 989 6076
- A different business name, a different industry, and a different Sharjah address
- Three placeholder five-star reviews reading *"Add a real client review here"*
- Stock photographs captioned as the real premises — e.g. `alt="Elegant hair salon
  interior at MDA Hair Style"`

**Why this matters for search.** A phone number is one of the strongest signals search
engines use to decide which business an entity *is*. Your number is currently published
against two contradictory identities — a Sharjah fit-out contractor and a Sharjah hair
salon. That ambiguity works directly against the local visibility we are trying to build,
and it will also feed any AI assistant that crawls the page.

There is also a straightforward honesty problem: a public page presents invented reviews
and stock photos as a real salon's own.

**Fix:** unpublish the page — disable GitHub Pages for this repository in
Settings → Pages. That removes it immediately and leaves the source file intact.
**Effort:** under a minute. **Requires:** your approval and your GitHub account.
*It is a publishing change, so I will not do it without you saying so.*

## 🟠 High

### H1. No analytics or conversion tracking of any kind
No GA4, Google Tag Manager, Meta Pixel, Clarity or any alternative on any page. There is
currently no way to know how many people visit, what they search for, which pages they
read, or how many click WhatsApp or call.

Without this, no future work can be judged. **Fix:** GA4 plus Search Console, with
click-tracking on WhatsApp, `tel:` and `mailto:` links. Free.
*Note: a contact click is a click, not a confirmed lead — the two must be counted separately.*

### H2. Not verified in Google Search Console
Nothing confirms Google has crawled or indexed the site, whether pages are excluded, or
what queries it already appears for. The sitemap exists but submission is unconfirmed.
**Fix:** verify the domain and submit `/sitemap.xml`. Free. **Requires:** DNS or file access.

### H3. No Google Business Profile found
For a contractor serving Dubai, Sharjah and Ajman, Maps is where much of this demand
looks first. No profile surfaced in search. **Note:** the address is a warehouse in an
industrial area, so eligibility and whether the address is displayed or hidden need
checking against Google's current rules before anything is created. A service-area
business with a hidden address is often the correct configuration.
**Never** create a duplicate profile or a fake location.

### H4. `burjalfalah.com` sends visitors to an unrelated website
The second domain 301-redirects to an education site. Anyone using that domain — from a
card, an old listing, or memory — never reaches the business. Repointing it to
`burjalfalahtech.com` would recover that traffic and consolidate the brand.
**Requires:** Cloudflare account access, and confirmation the redirect wasn't deliberate.

## 🟡 Medium

### M1. No written enquiry option
WhatsApp, phone and email links only; no form anywhere. Some buyers — particularly
offices, retail and property managers — will not open WhatsApp, and email invites vague
enquiries. A short form capturing project type, location, approximate area, budget range
and target date would qualify enquiries before the first conversation.

### M2. Opening hours missing
Absent from the site and from `LocalBusiness` schema. Hours matter for local search and
for Maps, and are one of the most common pre-contact questions.

### M3. Schema could be more specific
`LocalBusiness` is generic. `HomeAndConstructionBusiness` or `GeneralContractor`
describes the business more precisely. Adding `openingHoursSpecification` and the
correct `sameAs` profiles would strengthen it. Schema must always match visible content.

### M4. Projects carry no verifiable detail
19 project pages with photographs, but no dates, durations, sizes, locations, scope or
outcomes. Those specifics are what make a case study persuasive to a buyer and
distinctive to a search engine. Requires owner input and client permission.

### M5. No reviews anywhere
None on the site, none found publicly. Reviews are among the strongest local-search and
trust signals. Needs an honest process: ask every customer, no incentives, no filtering
out unhappy ones. Inventing reviews is never an option.

### M6. Conflicting Instagram handles
Schema says `@Burjalfalahtechnical`; search returns `@burj_alfalah`. One genuine account,
linked consistently.

### M7. English only
`lang="en"`, no Arabic version. Whether Arabic is worth adding depends on the customer
mix — worth a deliberate decision rather than drift.

## 🟢 Already good — leave alone

| Item | State |
|---|---|
| Sitemap | 32 URLs, clean structure, hreflang annotations |
| robots.txt | Correct, permissive, declares sitemap |
| Canonical URLs | Present |
| Structured data | `LocalBusiness` sitewide; `Service` + `FAQPage` on service pages; `BreadcrumbList` |
| Titles | Unique per page, all within sensible length |
| Meta descriptions | Unique, 90–142 characters — a good range |
| URL structure | Logical `/services/…`, `/projects/…` hierarchy |
| Images | 100% WebP, responsive widths, **every image has alt text**, all with width+height (no layout shift), lazy-loaded below the fold |
| Security headers | `X-Content-Type-Options`, `Referrer-Policy`, `X-Frame-Options`, `Permissions-Policy` |
| Service pages | Five real services, each with its own page and FAQs |
| Portfolio | 19 project pages with genuine-looking photography |

Whoever built this did competent work. The plan below **builds on it** rather than
replacing it.

---

## Prioritised plan

### A. I can do locally, now — no access, no cost
- Draft the corrected WhatsApp link change for review
- Draft an enquiry form (fields, validation, consent wording, privacy note)
- Draft improved schema: business type, opening hours, correct `sameAs`
- Draft a Google Business Profile pack: categories, services, description, photo plan
- Draft a review-request workflow and honest response templates — including for negative reviews
- Draft a case-study template turning the 19 projects into verifiable studies
- Draft the AI-search visibility check: a fixed question set, and a log format recording
  platform, date, question, web-search setting and cited sources
- Draft the monthly report format and the maintenance guide

### B. Needs your factual answers
- Approval to unpublish the fictional salon page *(C1)*
- Opening hours; whether the warehouse takes visitors
- Trade licence name, number and permitted activities
- Which Instagram account is real
- Project dates, sizes, scope, outcomes, and client/photo permissions
- Where enquiries should go, and how long enquiry data should be kept

### C. Needs account access — you act, or you grant access
- Site files or CMS (to deploy the WhatsApp fix and the form)
- Google Search Console verification
- Analytics installation
- Google Business Profile creation or claim
- Cloudflare, to repoint `burjalfalah.com`

### D. Costs money — nothing without your approval first
Nothing so far requires paid tools. GA4, Search Console, Google Business Profile and
schema are all free. A form needs somewhere to send submissions; there are free options.
Any recurring cost will be presented before it is incurred, never added quietly.

---

## What I have not done
- Not modified the live site — I have no access to it
- Not created any account, profile or listing
- Not published anything
- Not contacted anyone
- Not verified the Facebook or Instagram profiles (both require a login)
