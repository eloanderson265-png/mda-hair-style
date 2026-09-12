# Launch Checklist

Status at 2026-09-12. Nothing has been published, activated, or changed on any live
system. No account has been accessed. No message has been sent to anyone.

---

## ✅ Done — drafted locally, nothing live

| | Deliverable | File |
|---|---|---|
| ✅ | Verified company fact sheet with sources | `FACT-SHEET.md` |
| ✅ | Search visibility audit and prioritised plan | `AUDIT.md` |
| ✅ | Enquiry form — built, validated, brand-matched | `deliverables/enquiry-form-preview.html` |
| ✅ | Lead capture decisions and test plan | `deliverables/lead-capture-setup.md` |
| ✅ | Google Business Profile pack | `deliverables/google-business-profile-pack.md` |
| ✅ | Review workflow and response templates | `deliverables/reviews-workflow.md` |
| ✅ | Measurement setup instructions | `deliverables/measurement-setup.md` |
| ✅ | AI discoverability guidance, from official docs | `deliverables/ai-search-discoverability.md` |
| ✅ | Case study template | `deliverables/case-study-template.md` |
| ✅ | Monthly report template | `deliverables/monthly-report-template.md` |
| ✅ | AI visibility log | `deliverables/ai-visibility-log.csv` |
| ✅ | Maintenance guide and cost list | `deliverables/maintenance-and-costs.md` |

## ⛔ Blocked — needs your answers

| | Needed for |
|---|---|
| Opening hours | Google Business Profile, schema, site |
| Exact legal name + trade licence number | Profile name, schema, correct identification |
| Is the warehouse signed, staffed, visited by customers? | **Decides whether the profile shows or hides your address** |
| Which Instagram is real — `@Burjalfalahtechnical` or `@burj_alfalah`? | Schema, profile, consistency |
| Does a Google Business Profile already exist? | Claim it vs create — never duplicate |
| Where should enquiries be delivered? | Form handler |
| How long to keep enquiry data? | Privacy page |
| Preferred primary category | Profile |
| Robots: leave as-is, or block training crawlers? | robots.txt |
| Burj Khalifa project — confirmed and permitted? | Case studies, profile photos |
| Client and photo permissions | Anything published from the portfolio |

## 🔑 Blocked — needs account access or your action

| | Action | Who |
|---|---|---|
| ⛔ | Create + verify Google Search Console, submit sitemap | You (I'll supply the DNS record) |
| ⛔ | Create GA4, get Measurement ID | You |
| ⛔ | Add GA4 tag + click tracking **to the Next.js source** | Me, with repository access |
| ⛔ | Add the enquiry form to the site | Me, with repository access |
| ⛔ | Create or claim the Google Business Profile | You — your business identity |
| ⛔ | Repoint `burjalfalah.com` away from the education site | You — Cloudflare |
| ⛔ | Verify which Instagram account is real | You |

**The blocker behind most of these:** I don't have the Next.js source. The live site is a
static export; editing exported HTML gets wiped on the next deploy. Tell me where the
source lives and most of the ⛔ items above become things I can just do.

## 💰 Costs

Nothing proposed costs money. Added recurring cost: **AED 0**.
Nothing will be purchased or activated without showing you the cost first.

## 🚫 Explicitly not done

- Not modified the live site — no access
- Not created any account, profile, or listing
- Not published anything
- Not sent any message to any person
- Not submitted anything to Google
- Not verified the Facebook or Instagram profiles — both require a login
- Not invented any review, project detail, statistic, credential, price, or client name

---

## Suggested order

1. **Answer the ⛔ questions** — unblocks most of the rest
2. **Search Console** — free, 15 minutes, starts collecting data immediately
3. **Google Business Profile** — likely your biggest single gain
4. **GA4 + click tracking** — needs the source
5. **Enquiry form** — needs the source
6. **Fix the `burjalfalah.com` redirect**
7. **Start the review workflow** — with the very next customer
8. **One case study a week**

Steps 2 and 3 are free, need no developer, and would start working this week.
