# The Five Foundation Domains

Adjacent domains every crypto founder hits, beyond the seven exit-critical
necessities. Same structure: essence, triage questions, red flags, research
paths, advisors (advisor types defined in `advisors-and-research.md`).

---

## 8. Corporate structure & jurisdiction

**Essence:** Where the company (and each of its pieces) lives determines
which rules, taxes, and courts apply — and whether the cap table survives
diligence.

**Triage questions:**
- Draw the org chart: which entities exist, where, and what does each one
  *do* (employ people, hold IP, sign users, hold the token treasury)?
- Does the entity map match the operating reality — or does one company do
  everything while the structure diagram says otherwise?
- Is the cap table clean: all equity, SAFEs, options, and any token
  side-letters documented and reconcilable?
- If there's a foundation (Cayman, Swiss, Panama…): what does it actually
  control, and who actually controls *it*?

**Red flags:**
- IP, token treasury, and user contracts all in different entities with no
  intercompany agreements.
- A foundation that exists on paper but is run from the startup's Slack.
- Cap-table surprises: undocumented token promises to early
  investors/advisors (these collide with domain 12).
- Operating from a jurisdiction the structure pretends not to be in
  (management-and-control creates tax and regulatory presence — see
  domain 11).

**Research further:** Produce the one-page entity diagram with arrows for
IP, money, employment, and user relationships. List every intercompany
agreement that should exist and check which do. This diagram is also the
first page of any future data room.

**Advisors:** Corporate/startup counsel (structure and cap table); if a
foundation or DAO wrapper is involved, a specialist in that specific
jurisdiction's vehicles. Structure changes get exponentially more expensive
after a token launch — get this reviewed *before* issuing anything.

---

## 9. Token & instrument classification

**Essence:** What the token *is* (security, e-money, utility, commodity,
something else) is the question from which licensing, marketing, tax, and
fundraising consequences flow — and the answer differs by jurisdiction.

**Triage questions:**
- Is there a token, or a plan for one? What does the holder actually get —
  cash flows, governance, access, nothing?
- Has any legal analysis of its classification been done, in which
  jurisdictions, and is it written down?
- How was/will it be distributed — sale, airdrop, rewards, investor
  allocations — and were any distributions to US persons or other
  restricted-market residents?
- Does anything about the product create *other* regulated instruments —
  yield products, derivatives, staking-as-a-service, stablecoins?

**Red flags:**
- "It's a utility token" as a conclusion reached without counsel.
- Classification memo from one jurisdiction stretched to cover all markets.
- Sold to investors with return language (deck slides count) — that's the
  fact pattern securities regulators build cases on.
- Yield/staking/lending features bolted on post-launch with no fresh
  analysis.

**Research further:** Collect the facts an analysis depends on before paying
for it: distribution history, marketing language used at sale, what the
token does in the product, treasury holdings. Read the relevant regulator
frameworks at a high level (e.g., MiCA's ART/EMT/other-crypto-asset
categories, US Howey line of cases, UK FCA guidance) — to *converse* with
counsel, not to conclude.

**Advisors:** Securities/crypto counsel per material market — this is the
domain where "one good lawyer" is most likely to be insufficient across
jurisdictions. For stablecoins or anything yield-bearing, treat specialist
review as mandatory, not optional.

---

## 10. Licensing & registration strategy

**Essence:** The deliberate version of domain 1: given the perimeter, which
licenses to get, where, in what order — and what to restrict until then.

**Triage questions:**
- Which licenses/registrations does the current footprint *require* (from
  the domain-1 analysis), and which does the company *hold* or have in
  flight?
- Is there a sequencing decision — e.g., one EU CASP license passporting
  across the EEA vs. market-by-market; VARA vs. MAS vs. an EU base — made
  on purpose, or by default?
- What is deliberately restricted (markets, features) until licensing
  catches up, and is the restriction real (enforced in product) or
  aspirational?
- Any past regulator contact — inquiries, warnings, applications withdrawn?

**Red flags:**
- Serving licensed-activity markets on a "we'll get licensed later" basis
  with no restriction in the meantime.
- License applications drifting for years while the product expands.
- Regulator correspondence handled ad hoc, undocumented, or ignored.
- "Our competitor does it without a license" as the strategy.

**Research further:** Build the license map: rows = markets with material
users, columns = required authorization, status, gating decision. Regulator
websites publish application requirements, timelines, and fees — enough to
rough-cost each path. Note which regimes offer passporting (one license,
many markets) since that reshapes sequencing.

**Advisors:** Regulatory counsel for the strategy; local licensed counsel or
licensing consultants for each application (applications are a craft —
regulators notice DIY). A fractional compliance officer to own the map and
the regulator relationships.

---

## 11. Tax

**Essence:** Crypto tax exposure accrues silently — token treasuries,
cross-border structures, and user transactions each generate obligations
someone will eventually total up. Acquirers hire people to do exactly that.

**Triage questions:**
- Has a crypto-literate tax advisor ever reviewed the structure — corporate
  presence, transfer pricing between entities, where value is created vs.
  where it's booked?
- How is the token treasury treated for tax — at issuance, on sales, on
  grants to team/advisors — and in which jurisdiction?
- Employee/contractor token grants: is anyone withholding/reporting, under
  any regime?
- Any user-facing tax obligations — reporting regimes (e.g., CARF/DAC8-style
  crypto reporting), VAT/GST on fees — in the top user markets?

**Red flags:**
- Token grants to team members with no tax treatment at all — this surfaces
  in *every* diligence and often as a personal liability for the recipients.
- The "management and control" mismatch: incorporated in a zero-tax
  jurisdiction, actually run from somewhere else entirely.
- Treasury sales/swaps executed for years with no tax computation.
- "Crypto isn't taxed here" folklore doing the work of an analysis.

**Research further:** Assemble the facts first: entity locations and where
people actually work; complete treasury transaction history (on-chain data
makes this cheap to compile and expensive to hide); grant records. Most tax
authorities now publish crypto guidance — read the top markets' pages to
know which questions to bring to the advisor.

**Advisors:** A tax advisor with actual crypto engagements (ask for them) in
the headquarters jurisdiction, plus per-market advice where users or staff
concentrate. Do this before an exit process starts — tax findings mid-deal
create escrow holdbacks and price chips.

---

## 12. Fundraising & investor compliance

**Essence:** How you raised — equity, SAFEs, SAFTs, token warrants, public
sale — is itself a regulated event, and every future investor will re-read
those documents.

**Triage questions:**
- List every raise: instrument, investors, jurisdictions, exemptions relied
  on (accredited/qualified investors? private placement?) — was that
  documented at the time?
- Any token-linked instruments (SAFTs, token warrants, side letters
  promising allocations) — and do they collide with the current token plan
  or cap table?
- Any public or community sale, in any form (ICO, IDO, launchpad, NFT mint
  that funded the company) — to whom, and with what restrictions?
- Do investor updates and warranties made in past rounds still hold true?

**Red flags:**
- A past public sale to retail with no exemption analysis — the classic
  unresolvable diligence finding; surface it to counsel early, not mid-deal.
- Token promises to investors that exceed the planned supply or contradict
  each other.
- SAFTs from 2021–22 that nobody has re-read against what the token
  actually became.
- Raising *now* on projections or return language that domain 5 would flag
  as a promotion problem.

**Research further:** Build the instrument register: every financing
document, its token implications, and the exemption it relied on. Reconcile
total token commitments against planned supply. This register is the first
thing sophisticated crypto funds ask for.

**Advisors:** Securities counsel (the same one doing domain 9, ideally —
these interlock); corporate counsel for cap-table hygiene. If a past raise
looks problematic, counsel *first*, before any written internal analysis
exists — sequence matters for privilege.
