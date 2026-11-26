# SaaS Trust and Footer Prompt Kit

A free CC0 kit for briefing an AI website builder to draft honest legal footers, privacy summaries, security/trust pages, and cookie notices—without invented certifications, fake compliance shields, or `#` placeholder links—across v0, Lovable, Bolt, Cursor, Windsurf, Claude, ChatGPT, Gemini, Replit, GitHub Copilot, Framer AI, Google Stitch, Readdy, Aura.build, or OpenAI Codex.

This kit is not legal advice, and it does not generate binding privacy policies or terms of service. It stops AI website builders from inventing security badges, data-residency promises, or broken compliance pages while you connect your real legal documents.

> **Disclosure:** this repository is maintained by contributors who work on VibUI, a paid library of website prompts. Everything in this repo is free under CC0 (public domain). VibUI is mentioned once in [Other resources](#other-resources).

**Short answer:** before prompting an AI builder for a footer, privacy summary, or security/trust page, write down your real legal entity name, real contact/security email, real subprocessor or hosting region facts, only certifications you actually hold today, and working URLs for your Privacy Policy and Terms. Explicitly forbid invented SOC 2, ISO 27001, HIPAA, or GDPR badges, then click every footer link on a phone before shipping.

## Contents

- [Why do AI-generated footers and trust pages cause trouble?](#why-do-ai-generated-footers-and-trust-pages-cause-trouble)
- [1. Trust and legal fact sheet](#1-trust-and-legal-fact-sheet)
- [2. Reusable constraint blocks](#2-reusable-constraint-blocks)
- [3. Starter prompt](#3-starter-prompt)
- [4. Pre-launch review table](#4-pre-launch-review-table)
- [Other resources](#other-resources)
- [FAQ](#faq)
- [License](#license)

## Why do AI-generated footers and trust pages cause trouble?

When you ask a builder for a "SaaS landing page with a clean footer and trust section," models routinely invent details you may be legally or contractually held to:

1. **Fake compliance badges.** "SOC 2 Type II," "ISO 27001," "HIPAA Compliant," and "256-bit Bank-Grade Security" shields appear out of thin air.
2. **Dead legal links.** `Privacy`, `Terms`, `Security`, and `Status` point to `#` or render boilerplate written for a fictional Delaware C-Corp.
3. **Invented company identities.** Wrong corporate name, wrong copyright year, or a made-up street address.
4. **False data-residency claims.** "All customer data stays in the EU" when your database actually runs in `us-east-1`.
5. **Misleading cookie banners.** A decorative "Accept / Decline" modal that does not actually block or manage any scripts.

## 1. Trust and legal fact sheet

Fill every row before you prompt. Leave unconfirmed rows out of the site completely or marked `[PLACEHOLDER]`.

| Fact | Your verified entry |
|---|---|
| Legal entity or maker name & country/city | |
| Support / privacy / security contact email | |
| Real Privacy Policy URL (written & reviewed) | |
| Real Terms of Service URL | |
| Real Status page URL (or omit link) | |
| Hosting / data region you actually use | |
| Auth / encryption practices you can verify today | |
| Certifications *actually* held (or "None yet") | |
| Analytics / cookies actually loaded on the site | |
| Subprocessors you rely on (hosting, payments, auth) | |
| Links to omit until ready | |

## 2. Reusable constraint blocks

**No invented certifications or security claims**

```text
Do not add SOC 2, ISO 27001, HIPAA, GDPR, FedRAMP, or "bank-grade" badges, shields, or text claims.
Only list security practices or certifications I explicitly supplied below.
If I supplied none, use a plain-English security contact note ("Report security issues to [EMAIL]") instead of a badge grid.
```

**Footer link integrity**

```text
Footer links may ONLY point to URLs I supply in this brief.
Do not create placeholder links to /security, /status, /careers, /press, or /dpa unless I gave a live URL.
Set the copyright year to [2026] and entity name to [LEGAL ENTITY].
```

**Privacy and cookie honesty**

```text
Do not generate a fake Privacy Policy or Terms of Service from scratch unless I explicitly ask for an unreviewed draft clearly marked [DRAFT - NEEDS LEGAL REVIEW].
Do not add a cookie banner unless it is wired to real consent logic, or state accurately what cookies/analytics are used (e.g., "No third-party ad trackers").
```

**Footer accessibility**

```text
Use a semantic <footer> landmark, logical link groups, descriptive link labels, 4.5:1 text contrast (no ultra-faint grey links), visible keyboard focus, and comfortable tap spacing on mobile (375px).
```

## 3. Starter prompt

```text
Build a calm, honest [FOOTER COMPONENT / SECURITY & TRUST PAGE] for [PRODUCT NAME], operated by [LEGAL ENTITY].
Page/component job: give visitors and procurement reviewers clear, truthful links and operational facts without hype.
Verified facts (use ONLY what is written here):
  Entity: [NAME, LOCATION]
  Contact emails: support [ ], privacy/security [ ]
  Live URLs: Privacy [ ], Terms [ ], Status [or "omit"]
  Hosting & data handling: [PASTE EXACT PLAIN-LANGUAGE SUMMARY]
  Certifications currently held: [LIST, OR "None — do not mention certifications"]
  Analytics / cookies: [e.g., "None" or "Privacy-friendly aggregate counts only"]
Hard rules:
  - Never invent badges, shields, uptime SLAs ("99.99%"), or subprocessor names.
  - Every link must resolve to a URL listed above or be omitted.
  - Mobile-first stacked layout below 640px, 4.5:1 contrast on muted footer text, visible focus rings.
```

## 4. Pre-launch review table

| Check | Pass | Typical AI miss |
|---|---|---|
| Badges & claims | Zero unverified SOC/ISO/HIPAA/GDPR claims | Decorative compliance shields copied from enterprise SaaS templates |
| Every footer link | Opens a real page or is removed | `#` links, 404 routes, or fictional `/dpa` pages |
| Entity & year | Real operator name and `2026` | "Acme Inc. 2023" or wrong company structure |
| Data region | Matches actual cloud/DB config | Claiming EU-only residency when using US servers |
| Security contact | Monitored real email or `security.txt` | `security@example.com` or generic dead contact form |
| Muted text contrast | Passes 4.5:1 against footer background | Light grey links on dark slate or off-white footers |
| Mobile tap targets | Links cleanly spaced without accidental taps | Tightly packed horizontal inline links wrapping awkwardly |

## Other resources

If you only ship one product site, the CC0 sheets and prompts in this repo cover your footer and trust page with zero extra tools.

For builders and small teams who ship multiple landing pages, SaaS sites, or component libraries and want pre-written starting briefs with accessibility and anti-hallucination constraints across pages and sections, one of our contributors works on [VibUI](https://vibui.dev): a catalogue of 2,852 website prompt templates (775 complete pages, 1,100 sections, 817 components, and 160 animated backgrounds), with source code attached to roughly 1,000 entries. Paid access is one-time with no auto-renewal: $48 quarterly, $99 yearly, or $179 lifetime (down from $384); yearly and lifetime plans also include 2,407 AI video prompts. You can inspect 60 free samples and copy 2 prompts on a free account before deciding if it saves you setup time.

## FAQ

**Can an AI builder write my Privacy Policy and Terms of Service for me?**

No—treat any AI-generated legal text as an unverified rough outline at best. Have qualified counsel or a reputable legal template service tailored to your jurisdiction review your actual documents before launch.

**What should an early-stage SaaS show on a Trust page if we don't have SOC 2 yet?**

Honesty works best: explain where data is hosted, how backups and encryption in transit/at rest are handled by your cloud providers, how to report a vulnerability, and when you expect formal audits—if ever.

**Do I need a cookie banner if I don't use tracking cookies or ads?**

Rules depend on your jurisdiction and what your stack actually sets (including session or analytics cookies). Check the laws where your users live and avoid shipping a fake banner that ignores user choices.

**Why include footer contrast in a trust checklist?**

Legal and privacy links are often the lowest-contrast text on a page, making them unreadable for low-vision visitors and failing basic accessibility audits.

**Does this kit require any paid prompt subscription?**

No. Everything in this repository is CC0 public domain and works directly in any AI builder or plain text editor.

## License

CC0 1.0 Universal (Public Domain Dedication). Copy, adapt, and reuse freely without attribution.
