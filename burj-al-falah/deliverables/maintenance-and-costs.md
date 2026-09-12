# Maintenance Guide and Recurring Costs

---

## Recurring costs

### What you already pay

| Item | Cost | Notes |
|---|---|---|
| Domain `burjalfalahtech.com` | ~AED 40–80/year | Registrar |
| Domain `burjalfalah.com` | ~AED 40–80/year | Renewed to 2027-01-01. **Currently redirects to an unrelated site** — either repoint it here or let it lapse. Paying for a domain that sends your visitors elsewhere is the worst of both |
| Web hosting | Varies | LiteSpeed host |

### What this project adds

| Item | Cost |
|---|---|
| Google Search Console | **Free** |
| Google Analytics 4 | **Free** |
| Google Business Profile | **Free** |
| Sitemap, robots.txt, schema | **Free** — already in place |
| Form handler (Web3Forms) | **Free**, unlimited |
| Lead sheet, report, AI log | **Free** — plain files |

**Total added recurring cost: AED 0.**

### Things you'll be sold that you don't need

| Pitch | Verdict |
|---|---|
| "SEO packages, AED 2,000/month" | No. The technical work is already done; the rest is content only you can supply |
| "Guaranteed #1 on Google" | Impossible. Nobody controls Google's results. Walk away |
| "AI visibility / LLM optimisation" | No established method exists. See `ai-search-discoverability.md` |
| "Directory submissions, 500 sites" | Harmful. Low-quality bulk listings create inconsistent business data |
| "Paid backlinks" | Against Google's spam policies; risks a penalty |
| Premium form/CRM tools | Not until volume justifies it. Free handles this fine |

**Worth paying for eventually:** Google Ads, if you want immediate enquiries and can
track what a won job is worth. Only after the free measurement exists — otherwise you
can't tell whether it's working.

---

## Maintenance

### Weekly — 10 minutes
- Answer every enquiry within one working day. This beats every optimisation in these documents
- Log enquiries in the lead sheet **and ask how they found you**
- Reply to any new review

### Monthly — 45 minutes
- Fill in the monthly report
- Search Console → **Pages → Not indexed**, check for new problems
- Run the 8 AI questions, log results
- Add one project case study
- Post once to the Google Business Profile
- Check the contact links still work — one broken WhatsApp link costs a month of enquiries

### Quarterly — 2 hours
- Re-check every phone number, address and hours on the site, profile and Instagram.
  **Consistency matters more than almost anything else in local search**
- Add fresh photos to the profile
- Review which services bring work worth having; adjust emphasis
- Re-read the FAQ against questions customers actually asked

### Annually
- Renew domains — **set a calendar reminder**. An expired domain is the fastest way to
  lose everything built here
- Re-check the crawler documentation in `ai-search-discoverability.md`; vendors change it
- Confirm the trade licence activities still match what the site advertises

---

## If something breaks

| Symptom | Likely cause | First check |
|---|---|---|
| Enquiries stop suddenly | Broken contact link, or a form handler that stopped | Click every WhatsApp, phone and form button yourself, on a phone |
| Site disappears from Google | Accidental `noindex`, robots.txt change, expired domain, hosting down | Search Console → Pages; then load the site in a private window |
| Traffic falls gradually | Competitors, or a Google update | Search Console → Queries, compare 3 months |
| Analytics shows nothing | Tag removed by a redeploy | GA4 Realtime while browsing on your phone |
| Profile suspended | Guideline breach — name stuffing, wrong address, fake reviews | Profile notifications; appeal with evidence |

**The Next.js risk:** your site is a statically-exported Next.js build. Analytics tags
and tracking added to exported HTML by hand are **wiped on the next deploy**. They must
live in the source project. Whoever rebuilds the site needs to know this.

---

## Key facts to keep

| | |
|---|---|
| Website | https://burjalfalahtech.com |
| Built with | Next.js, statically exported, LiteSpeed hosting |
| Second domain | burjalfalah.com — redirect needs fixing |
| DNS | Cloudflare (for burjalfalah.com) |
| Sitemap | https://burjalfalahtech.com/sitemap.xml |

**Record and keep safe** (never in this repository, never in chat): registrar login,
hosting login, Cloudflare login, the Google account owning GSC/GA4/the Business Profile,
and who holds the Next.js source.
