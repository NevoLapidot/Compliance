---
name: crypto-startup-triage
description: >-
  Run a structured compliance and regulatory triage of a crypto / Web3 startup —
  at any stage from idea to exit-readiness. Interviews the founder (or reads a
  written description), walks 12 domains (regulatory perimeter, client asset
  safeguarding, product governance, financial-crime basics, marketing,
  records & privacy, decentralization claims, corporate structure, token
  classification, licensing strategy, tax, fundraising), and produces a
  prioritized triage report: what to ask, red flags, how to research further,
  and which advisors to engage. Use this skill whenever a user mentions
  building, launching, assessing, investing in, acquiring, or preparing to
  sell a crypto/Web3/DeFi/token/exchange/wallet/stablecoin startup and wants
  to understand its regulatory or compliance posture, risks, gaps, readiness,
  or "what should we be worrying about" — even if they never say the word
  "compliance". Also trigger for due-diligence prep, data-room prep, and
  "are we ready to raise / exit" questions for crypto companies.
---

# Crypto Startup Triage

A high-level triage of the compliance and regulatory posture of a crypto
startup. Not a legal opinion, not a substitute for counsel — a structured
first pass that tells a founder **what to ask, where to dig, and who to call**.

Based on Nevo Lapidot's Collider talk *"Compliance Necessities for Crypto
Startups — what's in the data room when you exit."* The organizing insight of
that talk drives everything here: **compliance is roughly 10× cheaper on day
one than the week before you sign an exit.** Every gap this triage surfaces is
something an acquirer's diligence team will find in their first afternoon —
and price into (or out of) the deal.

## What this skill produces

A written **Triage Report** covering 12 domains, each rated Red / Amber /
Green / Not-Applicable, with per-domain open questions, research paths, and
the specific advisor type to engage. The exact template is in
`references/report-template.md` — always use it.

This is guidance, not judgment-as-a-service. The report's job is to make the
founder's *next conversations* (with counsel, with an AML consultant, with
their board) sharper — not to replace them.

## The two modes

**Interactive triage (default).** Interview the user, then write the report.
Use this whenever the user is available to answer questions.

**One-shot triage.** If the user pastes a description of the startup (a deck,
a memo, a website dump) and asks for the triage directly — or is clearly not
available for a back-and-forth — extract what you can from the material, mark
everything you couldn't establish as an explicit **open question** in the
report, and never guess facts you weren't given. One-shot runs generate more
open questions than interviews — keep each domain to the 3–5 most material
ones, and for the report byline use "a written description provided by
{the user / the named source}".

## Workflow

### Stage 0 — Profile the startup

Before any domain questions, establish the four facts everything else hangs
on. Ask conversationally (2–4 questions at a time, not a wall of text):

1. **What is it, in one sentence?** (exchange, wallet, DeFi protocol, token
   issuer, stablecoin, payments, custody, NFT platform, infrastructure/B2B,
   trading app, other). If the founder can't answer this in one sentence,
   that is itself a triage finding — write it down.
2. **Where are the users?** Not where the company is incorporated — where the
   users actually sit. Which jurisdictions are targeted, which are merely
   not blocked, and is anything geo-fenced?
3. **What does it touch?** Does it ever hold, control, or have the technical
   ability to move user funds or keys? Does it issue a token? Does it earn
   fees on user transactions?
4. **What stage?** Idea / building / live with users / revenue / raising /
   preparing for exit or acquisition. Stage sets the tone of the report:
   pre-launch triage is about *designing it right*; pre-exit triage is about
   *what diligence will find*.

### Stage 1 — Select and walk the domains

Read both domain reference files before interviewing:

- `references/compliance-necessities.md` — the seven exit-critical domains
  (perimeter, client assets, product governance, financial crime, marketing,
  records & privacy, decentralization).
- `references/foundation-domains.md` — the five foundation domains
  (corporate structure, token classification, licensing strategy, tax,
  fundraising).

Use the profile to skip what doesn't apply — a pure B2B infrastructure
company with no user funds and no token skips client-asset safeguarding and
token classification (mark them N/A with one line of reasoning, so the reader
knows they were considered, not forgotten). Domain 7 (decentralization)
applies **only** to projects claiming to be, or planning to become,
decentralized.

For each applicable domain, ask the 2–4 triage questions from the reference
file that the profile hasn't already answered. Batch questions across domains
where natural — the goal is a conversation, not a form. Don't interrogate:
if the founder says "we haven't thought about that", that's a complete
answer; record it as a gap and move on.

### Stage 2 — Rate and write

Rate each domain:

- **Green** — basics in place and documented; a diligence team would find
  answers, not surprises.
- **Amber** — thought about, partially done, or undocumented. The most common
  rating for a real startup, and fine — the report's job is to sequence
  the ambers.
- **Red** — an active exposure: operating in a market without a required
  license, commingled client funds, no AML program with live users,
  guaranteed-return marketing, a "decentralized" protocol with an admin key.
  Reds come with a "stop and call an advisor this week" framing. A Red must
  rest on a *stated* fact, not an inference — if the exposure only exists
  under an assumption ("that yield probably comes from lending"), rate
  Amber and make the assumption an open question instead.
- **N/A** — doesn't apply, with one line of why.

Then write the full report using `references/report-template.md`, drawing
red flags, research paths, and advisor mappings from the domain files and
`references/advisors-and-research.md`. Deliver it as a markdown file, not
just chat text.

Two writing rules that keep messy real-world cases readable: when one fact
implicates several domains (a stale terms-of-service, a 2021 SAFT), give it
a *home* domain — the one whose reference file lists it as a red flag —
rate it there, and cross-reference from the others rather than repeating
the finding. And when Reds cluster (real startups can rack up four or
five), group the act-this-week items by *advisor call* rather than by
domain — one call to regulatory counsel covering three Reds is one item,
not three.

## Calibration

- **High-level means high-level.** This skill points; it doesn't draft
  policies, legal analyses, or license applications. If the user asks for
  those, help — but outside the triage, and with the advice-of-counsel
  caveat.
- **Jurisdiction honesty.** Name the regimes that plausibly apply (MiCA/CASP
  in the EU, FCA registration in the UK, the US federal/state patchwork,
  VARA in Dubai, MAS in Singapore, the Israel Securities Authority and
  Capital Market Authority in Israel, FATF standards globally) but do not pronounce on what a specific
  regulator would decide — that is exactly what the advisor column is for.
- **Never invent facts.** Ratings rest only on what the user told you or
  gave you. Unknowns are open questions, not assumptions in either
  direction.
- **Tone.** Founder-friendly and direct. The reader is likely a technical
  founder with no compliance background; explain terms on first use, skip
  the scare tactics, and keep the "why" attached to every "what" — founders
  act on reasons, not rules.
