---
name: eu-company-guide
description: Answers practical questions about running or selling into a small business in Germany, France, Spain, Denmark or Greece from a dated, sourced reference set - VAT rates and registration thresholds, small-business VAT schemes, invoicing and the national e-invoicing mandates, company forms and formation, corporate tax, minimum wage and employer basics, and the national data-protection layer on top of GDPR, plus the EU-wide rules on OSS and the B2B reverse charge. Use when someone asks "do I need to register for VAT in Germany", "when does e-invoicing start in France", "GmbH or UG", "what is the Spanish minimum wage", "corporate tax rate in Denmark", "myDATA in Greece", "do I charge VAT to an EU customer" or any how-the-rules-work question about these five countries. Not for UK rules; use uk-company-guide in the uk-business plugin. Reference, not advice.
---

# EU company guide

A routing skill over one reference file per country and one for the EU-wide rules. Each file is
plain English, carries the date each figure was checked, and names the official source to verify
it at (the national tax authority, business register, labour ministry or data protection
authority).

**This is reference, not legal, tax or accounting advice.** Say so in every answer that involves
a rate, a threshold, a deadline or a decision with real money at stake, and point the reader to a
local accountant or lawyer for the decision itself.

## How to answer

1. **Route.** Pick the country file from the table below and read it before answering. If the
   question is about selling across borders (OSS, reverse charge, the EUR 10,000 threshold,
   GDPR transfers), also read [references/eu-wide.md](references/eu-wide.md). Do not answer a
   figure from memory.
2. **Check the ledger.** Before quoting any threshold, rate or date, read
   [references/changes-ledger.md](references/changes-ledger.md). It lists what moves, what was
   corrected on the last check and what is announced but not yet law.
3. **Answer plainly.** Lead with the answer, then the rule, then what to do. Use the reader's
   numbers if they gave them and show the arithmetic.
4. **Date and source every figure.** Example: "EUR 13.90 an hour (German minimum wage from
   01/01/2026, checked 16/10/2026; verify at bundesregierung.de)."
5. **Say what is moving.** Several countries are mid-reform on e-invoicing and some changes are
   announced but not enacted. Say which, and do not present an announcement as law.
6. **Know the edge.** These files cover the main national rules for a small business. Regions
   and territories with their own regimes (the Canary Islands, Ceuta and Melilla, Corsica and
   the French overseas departments, Greek islands with special VAT rates, the Faroe Islands and
   Greenland) are flagged, not covered. Sector rules and collective agreements often override
   the statutory floor: say so for any employment question.

## Routing table

| Country | Read |
| --- | --- |
| Germany (GmbH, UG, Umsatzsteuer, Kleinunternehmer, XRechnung, Mindestlohn) | [references/germany.md](references/germany.md) |
| France (SAS, SARL, TVA, franchise en base, facturation électronique, SMIC) | [references/france.md](references/france.md) |
| Spain (SL, IVA, VeriFactu, Crea y Crece, SMI, autónomo) | [references/spain.md](references/spain.md) |
| Denmark (ApS, moms, CVR, bookkeeping act, no statutory minimum wage) | [references/denmark.md](references/denmark.md) |
| Greece (IKE, ΦΠΑ, myDATA, e-EFKA, minimum wage) | [references/greece.md](references/greece.md) |
| Selling across EU borders: OSS, IOSS, reverse charge, VIES, GDPR transfers, ViDA | [references/eu-wide.md](references/eu-wide.md) |
| Any figure or date that moves | [references/changes-ledger.md](references/changes-ledger.md) |

For a country not listed, say plainly that this guide does not cover it, answer only the EU-wide
part, and point to the national tax authority. For the UK, the `uk-company-guide` skill
(uk-business plugin) is the source.

## Staleness

Each file was researched on 22/06/2026, and the five most load-bearing figures per country were
re-checked against official or primary sources on 16/10/2026; six were corrected or updated. Re-check by
16/01/2027, or sooner after a national budget or a new e-invoicing decree.

If today is past 16/01/2027, or a new calendar year has started since the check, say the figures
may be out of date. Minimum wages, social-security ceilings and many thresholds reset on
1 January. If you have web search, re-check the figure at the source named in the file and say
the date you checked it.

## What this skill does not do

- It does not give personal tax, legal or accounting advice, file anything, or contact any
  authority.
- It does not cover personal income tax in depth, sector regulation, or regional variations
  beyond flagging them.
- It does not replace the applicable collective agreement for pay and notice.

## Example

> **User:** I'm a Germany-based freelancer, EUR 22,000 turnover last year, expecting about EUR 40,000 this year. Do I have to charge VAT?
>
> **Answer:** Probably not yet. Under the small-business scheme (Kleinunternehmerregelung, §19 UStG) you can stay out of VAT if last year's turnover was at most **EUR 25,000** and this year's stays at most **EUR 100,000** (thresholds in force since 01/01/2025, unchanged for 2026; checked 16/10/2026, verify at bundesfinanzministerium.de). You meet both. Your invoices must then say VAT is not charged under §19 UStG, and you cannot reclaim VAT on costs.
>
> Watch two things: if you cross EUR 100,000 during the year, the scheme ends immediately, not at year end; and from 01/01/2025 you must already be able to **receive** structured e-invoices. Reference, not advice: confirm with a Steuerberater before relying on it.

## Configuration

One thing varies: **where the business is established**. Most thresholds and schemes apply only
to businesses established in that country; a business established elsewhere usually has no
registration threshold and relies on OSS or the reverse charge instead. Ask if it is not clear.
