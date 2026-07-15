# Compliance Necessities for Crypto Startups
### What's in the data room when you exit

**Collider · Crypto Exits in Israel** — Collider office, Tel Aviv, July 14, 2026
Speaker: [Nevo Lapidot](https://www.linkedin.com/in/nevol) · [Event recap](https://www.linkedin.com/posts/another-packed-evening-at-the-collider-office-ugcPost-7482866521711480832-OnhJ/)

---

## The frame

Compliance is roughly **10× cheaper on day one than the week before you
sign.** When an acquirer's diligence team opens your data room, there are six
things they will look for in the first afternoon — a seventh if you claim to
be decentralized. Each one that's missing doesn't just slow the deal; it
reprices it.

This talk walked through those seven necessities: what "done" looks like on
day one, and what the question sounds like when it arrives in diligence.

## The seven necessities

| # | Necessity | Day one | In the data room |
|---|---|---|---|
| 1 | **Know your perimeter** | Say in one sentence what you are — and where your users actually sit | They price the markets you *reached*, not the one you're based in |
| 2 | **Safeguard client assets** | Segregate client funds, control the keys, reconcile to one-to-one backing | "Where are the client assets — and can you prove they're all there?" |
| 3 | **Product governance** | A product-approval gate every new feature, asset or market passes before launch | "Show me how you decide to launch something" — assessments and sign-offs on file |
| 4 | **Financial-crime basics** | Policy + MLRO, KYC at onboarding, monitoring, sanctions screening, SAR process | A policy written for the sale, or one sanctioned user — either reprices the deal |
| 5 | **Say only what you can legally say** | Risk warnings, no guaranteed-return claims, jurisdiction-specific promo rules | A tweet you deleted two years ago is still discoverable — and inherited |
| 6 | **Keep the receipts** | Retention, GDPR-grade privacy, terms that match what the product does | Half of diligence is one question: can you produce it? |
| 7 | **Decentralized? Prove it.** *(decentralized projects)* | Keep the protocol autonomous; ring-fence the interface, fees and marketing | "Show me you can't touch user funds" — or you're an unlicensed operator |

## The takeaway

**Built in. Not bolted on.** Treat compliance as a product feature from day
one — the same way you treat security or UX.

---

## 📄 The presentation

The full deck: [compliance-necessities-for-crypto-startups.pdf](./compliance-necessities-for-crypto-startups.pdf)

## 🤖 The companion skill: crypto-startup-triage

The talk's method, packaged as a **Claude skill** you can run on your own
startup. It interviews you (or reads a written description of the company)
and walks **12 domains** — the seven necessities above, plus corporate
structure, token classification, licensing strategy, tax, and fundraising
compliance. The output is a triage report with a Red/Amber/Green rating per
domain, the open questions to answer, how to research each one further, and
which advisor to engage — sequenced, so you're not hiring twelve advisors on
day one.

It's a structured first pass, not legal advice: it tells you *what to ask,
where to dig, and who to call*.

**Get it:** [`skills/crypto-startup-triage.skill`](../../skills/crypto-startup-triage.skill)
(the browsable source is in [`skills/crypto-startup-triage/`](../../skills/crypto-startup-triage/))

**Install:**

- **Claude apps (claude.ai / desktop):** Settings → Capabilities → Skills →
  upload the `.skill` file.
- **Claude Code:** unzip into `~/.claude/skills/` (it contains a
  `crypto-startup-triage/` folder).

**Then just ask**, e.g.:

> "Run a compliance triage on my startup — we're building a non-custodial
> wallet with a swap feature, users mostly in the EU and Israel."

For specific questions the triage surfaces — including which kind of advisor
a particular situation actually needs — you're welcome to reach out to me on
[LinkedIn](https://www.linkedin.com/in/nevol).

---

*The skill and this page are shared as general guidance for founders. They
are not legal, tax, or financial advice, and no advisor–client relationship
is created by using them.*
