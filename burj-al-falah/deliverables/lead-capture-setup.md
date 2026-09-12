# Lead Capture — Setup and Decisions

The form is drafted and validated: `enquiry-form-preview.html`.
It is **not connected to anything** and sends nothing. Two decisions are yours.

---

## What the form asks, and why

Every field earns its place. Long forms lose enquiries, so anything that isn't
either essential or genuinely useful for quoting was left out.

| Field | Required | Why |
|---|---|---|
| Name | Yes | To reply properly |
| Phone / WhatsApp | Yes | Your customers expect a call or a chat |
| Email | No | Some prefer it; forcing it costs enquiries |
| Type of work | Yes | Routes to the right part of the business |
| Property type | Yes | A villa kitchen and an office fit-out are different jobs |
| Location | Yes | Dubai, Sharjah, Ajman, or elsewhere — flags out-of-area early |
| Approximate area | No | Rough sizing; "not sure" is an option |
| Budget range | No | Optional on purpose. Compulsory budget fields drive people away. "Prefer to discuss" is the default |
| Target start | No | Separates "ready now" from "researching" |
| Description | Yes | The single most useful field for quoting |
| Consent | Yes | Explicit permission to contact them |

**Deliberately excluded:** exact address (not needed until a site visit), company name
(irrelevant for homeowners), and how they heard about you (analytics answers this better).

### Built in already
- **Mobile-first**, single column on phones, `font-size:16px` on inputs so iOS doesn't
  zoom, and correct `inputmode`/`autocomplete` so keyboards and autofill behave
- **Accessible** — every control labelled, errors announced, `aria-invalid` on failures,
  focus jumps to the first problem, visible focus rings
- **Spam trap** — a hidden honeypot field; bot submissions are discarded silently
- **Validation** in plain language: "A sentence or two about the work, please", not
  "Invalid input"
- **WhatsApp and phone shown alongside**, so the form never becomes the only route
- **A GA4 hook** that fires `generate_lead` on real submission only — dormant until GA4 exists

---

## Decision 1 — where do enquiries go?

I need an email address. It can be `info@burjalfalahtech.com` or something dedicated.
**Recommendation:** a dedicated address, so enquiries don't get lost among supplier mail.

## Decision 2 — how do they get there?

Your site is a **statically exported Next.js** site on LiteSpeed hosting. Static sites
can't process a form themselves, so submissions need a handler. Options:

| Option | Cost | Notes |
|---|---|---|
| **Web3Forms** | Free — unlimited submissions | Email-only, no account or dashboard. Simplest thing that works |
| **Formspree** | Free to 50/month, then ~$10/mo | Dashboard, spam filtering, file uploads |
| **PHP script on your own hosting** | Free | LiteSpeed almost certainly supports PHP. No third party at all, but deliverability needs checking — mail from shared hosting often lands in spam |
| **Google Forms** | Free | Ugly, off-brand, breaks the page flow. Not recommended |

**Recommendation: Web3Forms.** No recurring cost, no account, no third-party dashboard
holding your customers' data, and it's a one-line change to the form. If you later want
a CRM, moving is easy.

**No paid tool is needed for any of this.** If that changes, I'll show you the cost first.

---

## Decision 3 — how long do you keep enquiry data?

Enquiries contain personal data — names, numbers, sometimes photos of people's homes.
The UAE's Federal Decree-Law No. 45 of 2021 on Personal Data Protection sets obligations
around consent and retention.

⚠️ **I am not a lawyer and this is not legal advice.** For a business of your size a
sensible, defensible position is enough, but if you want certainty, have a UAE legal
adviser confirm it.

A practical default:

- **Won-work enquiries:** keep for the duration of the job plus the warranty period
- **Lost or unanswered enquiries:** delete after 12 months
- **Never** add form submitters to a marketing list — they consented to a reply about
  *their enquiry*, nothing more
- If you later send marketing, every message needs a working opt-out

**Tell me your preferred retention period and I'll write it into the privacy page.**
Your site already has `/privacy/`; I'll draft an update once the form exists.

---

## Testing before it goes live

Nothing gets switched on until it's proven. In order:

1. Connect the endpoint in a **test** configuration
2. I submit **test data only** — clearly marked, never a real customer's details
3. You confirm the email arrived, in the inbox and not in spam
4. Check it on a real phone, not just a desktop browser
5. Submit an invalid form and confirm errors behave
6. Only then does it go live on the site

I will not activate anything or send any message to a real person without you saying so.

---

## Follow-up messages

Worth having, but **only after** the form is live and tested:

- **Instant acknowledgement** to the enquirer: confirms receipt, sets a response time,
  offers WhatsApp for photos. No selling.
- **Internal notification** to you: the enquiry, formatted for quick triage.
- **A human follow-up reminder** if an enquiry goes unanswered for two working days.
  Deliberately a reminder to *you*, not an automated chase to the customer — automated
  nagging reads badly to someone choosing a contractor.

Drafts on request once Decisions 1–3 are settled.
