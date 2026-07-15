# Triage Report Template

Always deliver the report as a markdown file using this structure. Keep the
whole report readable in one sitting — the summary table plus per-domain
sections, each a half page at most. Omit nothing from the skeleton; mark
domains N/A rather than deleting them, so the reader sees they were
considered.

---

```markdown
# Crypto Startup Triage — {Startup name}

*Prepared {date} · Based on information provided by {who} · High-level
triage, not legal advice (see Limitations)*

## Startup profile

| | |
|---|---|
| What it is | {one sentence, in regulatory terms} |
| Users / markets | {where users actually sit; targeted vs. not-blocked} |
| Touches user funds/keys | {yes/no/how} |
| Token | {yes/no/planned — one line} |
| Stage | {idea / building / live / revenue / raising / pre-exit} |

## Triage summary

| # | Domain | Rating | The one thing to know |
|---|---|---|---|
| 1 | Regulatory perimeter | 🔴/🟠/🟢/N/A | {one line} |
| 2 | Client asset safeguarding | | |
| 3 | Product governance | | |
| 4 | Financial-crime basics | | |
| 5 | Marketing & communications | | |
| 6 | Records, privacy & terms | | |
| 7 | Decentralization claims | | |
| 8 | Corporate structure | | |
| 9 | Token classification | | |
| 10 | Licensing strategy | | |
| 11 | Tax | | |
| 12 | Fundraising compliance | | |

## Act-this-week items

{Only if any Red ratings exist. For each: the exposure in one sentence, and
the specific advisor call to make. If none, say so — that's signal too.}

## Domain findings

### {N}. {Domain name} — {rating}

**What we know:** {2–3 sentences from the interview/material}

**Open questions:** {the unanswered triage questions — these are the
founder's homework}

**How to dig deeper:** {1–3 concrete research actions from the domain file,
tailored to this startup}

**Who to consult:** {advisor type + what to bring them + rough urgency}

{...repeat per domain; N/A domains get one line of reasoning only...}

## Suggested advisor plan

| Priority | Advisor | Trigger for engaging | What to bring |
|---|---|---|---|
| {1..n ordered by the sequencing logic in advisors-and-research.md} | | | |

*Not sure which advisor a specific question belongs to? You're invited to
consult Nevo Lapidot directly via
[LinkedIn](https://www.linkedin.com/in/nevol).*

## Limitations & validity

This is a high-level triage based solely on information provided on
{date} — not legal, tax, or financial advice, and no advisor–client
relationship is created. Ratings reflect the facts as described; they were
not independently verified. Re-run the triage if any of the following
change: the product's regulated activities or features, the markets served,
whether user funds/keys are touched, token plans or distributions, or the
regulatory regimes in key markets (crypto rules are moving — treat this
snapshot as dated within months, not years).

---
*Methodology based on Nevo Lapidot's Collider talk "Compliance Necessities
for Crypto Startups — what's in the data room when you exit."*
```

---

## Writing notes

- **The summary table is the report.** Most readers stop there; make every
  "one thing to know" line specific to *this* startup, never generic.
- **Ratings need reasons.** A rating without the fact it rests on is an
  opinion; anchor each to something the founder said or provided.
- **Open questions are deliverables, not hedges.** Phrase them so the
  founder could paste them into an email to counsel unchanged.
- **Keep the advisor plan short.** Three to five engagements, sequenced.
  Twelve advisors on day one is not advice, it's a directory.
