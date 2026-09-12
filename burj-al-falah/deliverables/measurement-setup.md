# Measurement — Setup Instructions

You currently have **no analytics of any kind**. Until this exists, nothing else in this
project can be judged: not whether traffic grew, not which pages persuade people, not
which enquiries came from search.

All of it is free. None of it can be done without your account access.

---

## 1. Google Search Console — do this first

Shows what people searched before reaching you, which pages Google has indexed, and any
crawl problems. It is the only honest source for "are we being found".

**Setup:**
1. Go to `search.google.com/search-console`, sign in with the Google account that should
   own this long-term — **not a personal account you might lose access to**
2. Add a **Domain property** for `burjalfalahtech.com` (covers all subdomains and both
   protocols — better than the URL-prefix option)
3. Verify by **DNS TXT record**. Google gives you a string; it goes in your DNS. Your
   domain appears to be on the same host as the site — I'll help once you have the string
4. Once verified: **Sitemaps → submit** `sitemap.xml`
5. **URL Inspection** on `https://burjalfalahtech.com/` to confirm it's indexed

**What to look at, monthly:** total clicks and impressions; queries you appear for;
**Pages → Not indexed** (the most useful screen — it tells you what Google is skipping
and why).

⚠️ Submitting a sitemap asks Google to crawl. It does not guarantee indexing, and
nothing guarantees ranking.

## 2. Google Analytics 4

**Setup:**
1. `analytics.google.com` → create account "Burj Alfalah Technical Services"
2. Create a property. **Set the time zone to Dubai (GST) and currency to AED** — easy to
   miss, and painful to correct later
3. Create a **Web** data stream for `https://burjalfalahtech.com`
4. Copy the Measurement ID (format `G-XXXXXXXXXX`)
5. The tag goes in the site's `<head>` — this is a **Next.js** site, so it belongs in
   the source project, not hand-edited into exported HTML
6. **Link GA4 to Search Console** (Admin → Product links). Most people skip this; it's
   what lets you see search queries and behaviour together

⚠️ **Never trust a tag because the code is present.** After installing, open the site on
your phone and check GA4 **Realtime** shows you. If you don't appear, it isn't working.

## 3. Conversion tracking — the part that matters

Pageviews don't pay anyone. What matters is contact attempts.

Your site's contact routes are WhatsApp links, `tel:` links, and `mailto:` links. GA4
doesn't track these by default — **outbound clicks need explicit tracking.**

Once GA4 exists, add this to the site (in the Next.js source):

```html
<script>
document.addEventListener('click', function (e) {
  var a = e.target.closest('a');
  if (!a || !a.href) return;

  var href = a.href;
  var type =
    href.indexOf('wa.me') > -1 || href.indexOf('whatsapp') > -1 ? 'whatsapp' :
    href.indexOf('tel:') === 0 ? 'phone' :
    href.indexOf('mailto:') === 0 ? 'email' : null;

  if (type && typeof gtag === 'function') {
    gtag('event', 'contact_click', {
      contact_method: type,
      page_path: location.pathname
    });
  }
});
</script>
```

Then in GA4: **Admin → Events → mark `contact_click` and `generate_lead` as key events.**

### 🔴 Read this before interpreting any of it

**A contact click is a click. It is not a lead.**

Someone clicking WhatsApp may never send the message. They may send "hi" and vanish.
They may be a supplier, a job applicant, or a wrong number. Treat these numbers as
*interest*, never as customers.

- `contact_click` → someone **tried** to make contact
- `generate_lead` (form submission) → someone **actually sent** their details
- A real lead → someone you **spoke to** with a genuine project

The gap between the first and last is large, and it's the only number that matters
commercially.

## 4. Qualified-lead tracking — the one manual thing

No tool can tell you whether an enquiry was any good. This takes five minutes a week and
is worth more than every automated dashboard combined.

A single sheet, one row per enquiry:

| Column | Notes |
|---|---|
| Date | |
| Name | |
| Channel | WhatsApp / form / phone / email / walk-in |
| How they found you | **Just ask.** "How did you come across us?" The single most valuable data point you own |
| Project type | |
| Location | |
| Qualified? | Real project, in your area, in your scope — yes/no |
| Quoted? | |
| Quote value | AED |
| Won / lost / no reply | |
| If lost, why | Price, timing, went quiet, chose someone else |

After three months this tells you what no analytics tool can: which channel produces work
that gets *won*, not just enquiries. A channel producing ten enquiries and no jobs is
worse than one producing two enquiries and a signed contract.

## 5. Monthly report

Fifteen minutes, same day each month. Suggested format in
`monthly-report-template.md`.

**Deliberately excluded:** "impressions", "reach", "engagement", and any metric that
can't be connected to an enquiry.

---

## What you need to do vs what I can do

| Task | Who |
|---|---|
| Create GSC and GA4 accounts, verify domain | **You** — your accounts, your ownership |
| Choose the owning Google account | **You** |
| Add the GA4 tag and click tracking to the Next.js source | Me, given repository access |
| Give you the exact DNS record to add | Me, once you have the string |
| Set up the lead sheet and report template | Me — done, see this folder |

**Own the accounts yourself.** Never let an agency or freelancer create these under their
own account — people lose their analytics history that way every day.
