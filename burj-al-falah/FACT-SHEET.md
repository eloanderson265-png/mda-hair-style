# Burj Alfalah Technical Services LLC — Company Fact Sheet

**Purpose:** single source of truth for anything published to the website,
Google Business Profile, directories, or structured data.
**Rule:** nothing marked ⚠️ or ❌ may appear in public-facing content.

**Status key**
- ✅ **Verified** — confirmed by the owner, or checked directly against a primary technical source
- ⚠️ **Published by the company, awaiting owner confirmation** — taken from the company's own
  live website, so it is the company's own public claim, but not yet confirmed to me as correct
- ❌ **Missing or conflicting** — must be resolved before publication

Primary source for ⚠️ rows: `https://burjalfalahtech.com`, crawled 2026-09-12.

Last updated: 2026-09-12

---

## 1. Identity

| Fact | Value | Status | Source |
|---|---|---|---|
| Trading name | Burj Alfalah | ⚠️ | Site header and footer |
| Legal name | BURJ ALFALAH TECHNICAL SERVICES LLC | ⚠️ | `LocalBusiness` schema, `name` field |
| Sector | Technical services — fit-out, renovation, bespoke joinery | ✅ | Owner, this session; matches site |
| Trade licence number | — | ❌ | Not published |
| Licensing authority | Presumably Sharjah (warehouse address); unconfirmed | ❌ | Not published |
| Year established | — | ❌ | Not published |

## 2. Contact

| Fact | Value | Status | Source |
|---|---|---|---|
| Address | Warehouse 4, Al Sajaa St 129, Al Sajaa Industrial, Sharjah, UAE | ⚠️ | `PostalAddress` schema; `/contact/` |
| Premises type | Warehouse — likely not a walk-in customer location | ⚠️ | Address wording; **affects Google Business Profile address display** |
| Geo coordinates | 25.30384635925293, 55.624820709228516 | ⚠️ | `GeoCoordinates` schema |
| Phone 1 | +971 56 328 7272 | ⚠️ | Displayed sitewide; `tel:` links |
| Phone 2 | +971 52 338 8357 | ⚠️ | `/contact/`; `tel:` links |
| **WhatsApp (published)** | **+971 52 989 6076 — belongs to a different business, see §6.1** | ❌ | **Conflict — do not use** |
| Email | info@burjalfalahtech.com | ⚠️ | `mailto:` links; schema |
| Opening hours | — | ❌ | Not published; absent from schema |
| Service areas | Dubai, Sharjah, Ajman | ⚠️ | `areaServed` schema; stated sitewide |
| Languages | English only | ⚠️ | `lang="en"`, `og:locale=en_AE`; no Arabic version |

## 3. Digital assets

| Asset | Value | Status | Source |
|---|---|---|---|
| **Live website** | burjalfalahtech.com — live, HTTP 200, LiteSpeed | ✅ | Checked 2026-09-12 |
| Last modified | 2026-09-05 | ✅ | `Last-Modified` header |
| Pages | 32 URLs in sitemap | ✅ | `/sitemap.xml` |
| robots.txt | Present, `Allow: /`, declares sitemap | ✅ | `/robots.txt` |
| Canonical / hreflang | Present on pages checked | ✅ | Crawl |
| Structured data | `LocalBusiness` sitewide; `BreadcrumbList`, `Service`, `FAQPage` where relevant | ✅ | Crawl |
| **Analytics / tracking** | **None whatsoever** | ✅ | No GA4, GTM, Meta Pixel, Clarity on any page |
| Contact form | **None** — WhatsApp, phone and email links only | ✅ | No `<form>` on any page crawled |
| Instagram (in schema) | instagram.com/Burjalfalahtechnical | ⚠️ | `sameAs` schema |
| Instagram (found in search) | instagram.com/burj_alfalah — **different handle** | ❌ | Conflict, see §6.3 |
| Facebook | facebook.com/p/Burj-Alfalah-Technical-Services-61559814113912 | ⚠️ | Search result; needs login to verify |
| Google Business Profile | Unknown — none found in search | ❌ | Existence unconfirmed |
| Search Console | Unknown | ❌ | — |
| Second domain | burjalfalah.com — 301s to an unrelated site, see §6.2 | ✅ | Checked 2026-09-12 |

## 4. Services published

| # | Service | Detail as published | Dedicated page |
|---|---|---|---|
| 1 | Fit-Out & Renovation | Villas, apartments, offices, retail; partitions, false ceilings, plaster, painting, wall finishes, tiling, demolition | `/services/fit-out-renovation/` |
| 2 | Bespoke Joinery | Kitchens, wardrobes, TV/media units, vanities, wall panels, wooden doors, shelving, storage | `/services/bespoke-joinery/` |
| 3 | Flooring | SPC, vinyl, laminate; skirting, floor preparation and replacement | `/services/flooring/` |
| 4 | Electrical | Repairs, lighting, sockets, switches, troubleshooting | `/services/electrical/` |
| 5 | Plumbing | Leak repairs, taps, sinks, renovation-related plumbing | `/services/plumbing/` |

All ⚠️ — published by the company; **must be checked against the trade licence** before
being promoted further. Electrical and plumbing work in the UAE is activity-restricted.

**Stated process (8 stages):** Consultation → Measurement → Design → Quotation →
Production → Installation → Handover → Follow-up. ⚠️

## 5. Project portfolio — 19 published case studies

Kitchen Solution · Bathroom Renovation · Kids' Custom Bed for Twins ·
Nursery Landscape (Abu Dhabi) · Pergola Solution · Reception Solution ·
Custom TV Unit · Burj Khalifa Apartment Bathroom Furniture · Living Area Update ·
Fence Solution · Landscape Solution · Office Kitchen · Kids' Play Equipment ·
Vanity Storage Solution · Display Shelving Solution · Stair Solution ·
Door Painting · Plumbing Work · Electrical Work

All ⚠️. Outstanding permission questions:
- Are the project photographs the company's own work? (They appear to be — real,
  consistently named, responsively sized WebP assets, not stock.)
- Has any client consented to their project being shown publicly?
- **"Burj Khalifa Apartment Bathroom Furniture"** names a landmark building. Confirm the
  work was genuinely done there and that naming it publicly is permitted.
- No dates, durations, sizes, budgets, or outcomes are published for any project.

## 6. Conflicts and defects to resolve

### 6.1 🔴 Every WhatsApp link goes to an unrelated business
All WhatsApp links across the site point to `wa.me/971529896076`. That number,
**+971 52 989 6076**, is the published WhatsApp number of *MDA Hair Style*, a ladies'
hair salon in Sharjah — see `index.html` in this repository. It is not one of the two
phone numbers the site displays for Burj Alfalah.

The `/contact/` page also displays it in text, labelled "WhatsApp — Send a description,
project photos and available measurements."

Confirmed on all 12 pages crawled, with 11–15 WhatsApp links per page.
**WhatsApp is the site's primary call to action, so its main conversion path currently
delivers every enquiry to a hair salon.** Fix before any other work.

### 6.2 🟠 The other domain redirects visitors away
`burjalfalah.com` is registered until 2027-01-01 on Cloudflare, but 301-redirects to
`highereducationinusa.com`, which redirects on to a third site. It previously hosted a
WooCommerce clothing store, "Burj Al Falah Garments Trading". Anyone reaching the
business through that domain is sent to an unrelated website.

### 6.3 🟡 Two different Instagram handles
Schema declares `@Burjalfalahtechnical`; search returns `@burj_alfalah` (Sharjah).
Only the genuine account should be linked, and it should be the one linked everywhere.

### 6.4 🟡 Abu Dhabi project vs stated service area
Service areas are published as Dubai, Sharjah and Ajman, but a portfolio project is
titled "Nursery Landscape — Abu Dhabi". Either the service area is wider than stated,
or the project is historical. Worth stating clearly either way.

### 6.5 🟡 Unrelated business in this repository
This repository also contains `index.html` for *MDA Hair Style*. Unmodified. The shared
WhatsApp number in §6.1 suggests both sites were built from the same template.

## 7. Open questions for the owner

1. Confirm the correct WhatsApp number for Burj Alfalah.
2. Is the `burjalfalah.com` redirect intentional, and who controls that Cloudflare account?
3. Exact legal name and trade licence number; which authority issued it.
4. Opening hours.
5. Does the warehouse receive visitors, or is it site-visits only?
6. Which Instagram account is genuine?
7. Is there an existing Google Business Profile?
8. Where should written enquiries be delivered, and who approves published content?
9. Is Arabic content needed?
10. Client and photo permissions for the 19 published projects.
