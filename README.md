# EU business skills for Claude

**Run or sell into a small business in Germany, France, Spain, Denmark or Greece with Claude: dated, sourced answers on VAT, e-invoicing, company forms, corporate tax, minimum wage and data protection.**

```bash
/plugin marketplace add kristian-presso/claude-eu-business-skills
/plugin install eu-business@claude-eu-business-skills
```

One department of [claude-skills](https://github.com/kristian-presso/claude-skills), where all departments live in one place. Free, MIT licensed, no sign-up.

One skill for founders, freelancers and small teams who are established in, or sell into, these five countries. Most of the rules that trip people up are mid-reform (e-invoicing above all), and the answers you get from memory or a quick search are often a year out of date.

> **Reference, not advice.** This skill explains how the rules work. It is not legal, tax or accounting advice, it never files or pays anything, and the figures change. Every rate, threshold and deadline carries the date it was checked and the official source to verify it at. For decisions with real money at stake, talk to an accountant or lawyer in the country concerned.

## Skills

| Skill | Use it when |
| --- | --- |
| [eu-company-guide](skills/eu-company-guide/SKILL.md) | You have a question about VAT rates and registration, small-business VAT schemes, invoicing and e-invoicing, company forms, corporate tax, minimum wage and employer basics, or data protection in Germany, France, Spain, Denmark or Greece. |

What it covers, one reference file each:

- **Germany:** GmbH and UG, Umsatzsteuer, Kleinunternehmerregelung, XRechnung and the e-invoicing timetable, Mindestlohn and mini-jobs.
- **France:** SAS and SARL, TVA, franchise en base, facturation électronique, SMIC.
- **Spain:** SL and autónomo, IVA, VeriFactu and the B2B e-invoicing Order, Crea y Crece, SMI.
- **Denmark:** ApS, moms, CVR, the bookkeeping act, and why there is no statutory minimum wage.
- **Greece:** IKE, VAT, myDATA and e-invoicing, e-EFKA, minimum wage.
- **EU-wide:** OSS and IOSS, the B2B reverse charge, VIES, the EUR 10,000 distance-selling threshold, GDPR transfers and ViDA.

Regional regimes (the Canary Islands, Ceuta and Melilla, Corsica and the French overseas departments, Greek islands with special VAT rates, the Faroe Islands and Greenland) are flagged, not covered. For the UK, use [uk-business](https://github.com/kristian-presso/claude-uk-business-skills).

## Tested, not just written

The skill is evaluated with Claude Code's built-in `claude plugin eval`: five cases (three it should handle, two near-misses it must leave alone, a UK VAT question and a US sales tax question), each run three times with the skill and three times without, graded by a separate model. It ships only because Claude does better with it than without it. Results from 16/10/2026:

| Skill | Score with | Without | Gain | Fired when it should, and only then |
| --- | --- | --- | --- | --- |
| eu-company-guide | 1.00 | 0.75 | +0.25 | 15/15 |

Where plain Claude falls short is the recent changes: Spain's B2B e-invoicing dates, Greece's minimum wage, and Denmark's filing deadline and VAT threshold.

## Install

### Claude Code

On its own, from this repository:

```bash
/plugin marketplace add kristian-presso/claude-eu-business-skills
/plugin install eu-business@claude-eu-business-skills
```

Or with every other department, from the hub:

```bash
/plugin marketplace add kristian-presso/claude-skills
/plugin install eu-business@claude-skills
```

Use one or the other, not both, or the skill loads twice.

### Claude app

On claude.ai or the Claude desktop app, download this repository as a zip (Code, then Download ZIP), take the `skills/eu-company-guide` folder (the one containing `SKILL.md`), zip that folder on its own and upload it in your skills settings.

## How fresh is it

The reference material was researched against national tax authorities, business registers, labour ministries and data protection authorities on 22/06/2026. The five most load-bearing figures per country were re-checked against official or primary sources on 16/10/2026, and six were corrected:

- Spain: B2B e-invoicing from 06/10/2027 (turnover over EUR 8m) and 06/10/2028 (everyone else), under Order HAC/1028/2026, in force 06/10/2026
- Spain: VeriFactu still starts in 2027 in law; a deferral to 2028 is announced, not enacted
- Greece: minimum wage EUR 920 a month from 01/04/2026
- Greece: B2B e-invoicing for remaining businesses from 02/11/2026, transition to 31/01/2027
- Denmark: annual report due within 6 months for class B and C
- Denmark: the DKK 50,000 VAT threshold is measured per calendar year

Among those confirmed unchanged: Germany's minimum wage EUR 13.90 an hour (2026) and Kleinunternehmer limits EUR 25,000 / EUR 100,000; France's SMIC EUR 12.31 an hour from 01/06/2026 and e-invoicing from 01/09/2026 (receive) and 01/09/2027 (issue, SMEs).

Re-check by 16/01/2027, or sooner after a national budget or a new e-invoicing decree. Minimum wages and social-security ceilings reset each January (Greece each April). The full list, with sources, is in `skills/eu-company-guide/references/changes-ledger.md`.

## Re-run the evals and checks

The eval cases live in `evals/`. From the repository root:

```bash
claude plugin eval . --trust-plugin --scaffold --ablation with-without --runs 3 --no-publish
```

Every push runs the same checks as CI: the skill through the validator, the manifests through `claude plugin validate`, and a scan for em dashes:

```bash
for d in skills/*/; do python3 tools/validate_skill.py "$d"; done
claude plugin validate .
```

The skill has no scripts, so there are no unit tests.

## Feedback

Two minutes on [this form](https://tally.so/r/7XlJbL?source=claude-eu-business-skills) tells me what worked, what broke and what to build next. Every answer gets read. Bugs with steps to reproduce are best as a GitHub issue: if the skill fired when it should not have, did not fire when it should, or gave a wrong figure, tell me what you typed and what happened.

## Contributing

Corrections are the most useful thing you can send. If a figure is wrong or out of date, open an issue or a pull request with the official source and the date you checked it. Changes to a figure go in the country file and in `references/changes-ledger.md`. Run the checks above before opening a pull request. New countries are welcome on the same pattern: one reference file, every figure dated and sourced, and eval cases that show Claude does better with it.

## More departments

[claude-skills](https://github.com/kristian-presso/claude-skills) has all departments in one place: operator discipline, building with Claude, go-to-market, marketing, UK business and more, installable together or one at a time.

## All of it in one install

This skill also runs inside [Corey](https://getcorey.ai), alongside the rest of the library I use to run my business: one install that already knows your business, remembers it between chats and keeps itself up to date. It is free for individuals.

## Licence

[MIT](LICENSE). Take it, fork it, strip the parts you disagree with.

How these were built, and why, is written up at [kristianpapadakis.com/guides](https://kristianpapadakis.com/guides).
