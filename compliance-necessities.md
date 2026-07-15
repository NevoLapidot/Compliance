# The Seven Compliance Necessities

The seven exit-critical domains, from Nevo Lapidot's Collider talk. These are
the things a diligence team will look for in the first afternoon — and the
things that reprice a deal when missing. Each domain gives: the essence, the
day-one standard, triage questions, red flags, how to research further, and
which advisor to consult (advisor types are defined in
`advisors-and-research.md`).

---

## 1. Know your perimeter

**Essence:** What you are — and where you're allowed to offer it. Diligence
prices the markets you *reached*, not the one you're based in.

**Day-one standard:** The founder can say in one sentence what the product is
in regulatory terms, and knows where their users actually sit.

**Triage questions:**
- In one sentence: what is the product, and which regulated activity does it
  most resemble (exchange, brokerage, custody, payments, lending, issuance)?
- Where are your users — by actual traffic/KYC data, not by intention?
- Which markets do you *target*, which do you merely *not block*, and what
  geo-controls actually exist (IP blocks, KYC country checks, app-store
  availability)?
- Has anyone ever mapped which licenses/registrations the current footprint
  requires?

**Red flags:**
- "We're global" with no market-by-market analysis.
- Users in heavily-regulated markets (US, UK, EU) reached "passively" with no
  restriction or legal review.
- The regulatory characterization changes depending on who on the team you
  ask.

**Research further:** Pull the startup's own analytics for a real user-country
breakdown. Read the regulator's public perimeter guidance for the top 3
user markets (most regulators publish "do you need a license?" guidance).
Check the regulator's public warning lists — appearing on one is a
first-afternoon diligence find.

**Advisors:** Crypto-specialist regulatory counsel in each *material* user
market (start with the top one). This is the single highest-leverage legal
spend; everything else in the triage depends on the perimeter answer.

---

## 2. Safeguard client assets

**Essence:** If you hold it, it isn't yours — prove it's all there.

**Day-one standard:** Client funds segregated from company funds, keys under
real access control, and reconciliation proving one-to-one backing.

**Triage questions:**
- Do you ever hold, control, or have the technical ability to move user
  funds or keys? (Include "temporarily" and "in the smart contract we
  admin".)
- Are client assets segregated from operating funds — separate wallets,
  separate bank accounts, never commingled?
- Who can move client assets, with what approval flow (multi-sig? MPC?
  one founder's laptop?), and is that documented?
- Do you reconcile client balances against on-chain/custodial holdings — how
  often, and is it written down anywhere?

**Red flags:**
- Client and company funds in the same wallet or account, ever.
- A single person (or single key) able to move client assets.
- "We use a custodian" with no contract review — sub-custody terms, asset
  segregation at the custodian, and insolvency treatment unexamined.
- No reconciliation, or reconciliation that lives in one person's head.

**Research further:** Map every wallet/account that ever touches user funds
and who controls it — a one-page diagram is the deliverable. If a third-party
custodian is used, obtain their terms, regulatory status, and any SOC/ISAE
reports. Compare the setup against safeguarding rules in the top user market
(e.g., MiCA's CASP safeguarding provisions).

**Advisors:** Regulatory counsel (safeguarding obligations); a custody or
wallet-infrastructure specialist for key-management design; an audit firm
once reconciliation needs independent verification. If designing from
scratch: qualified custodian vs. self-custody is a decision to make *with*
counsel, not after launch.

---

## 3. Product governance

**Essence:** Every launch passes a gate — before it ships. Diligence will
ask: "show me how you decide to launch something," and expect assessments
and sign-offs on file.

**Day-one standard:** A product-approval gate that every new feature, asset,
or market passes before launch — even a lightweight one.

**Triage questions:**
- When you last launched a feature, listed an asset, or entered a market —
  did anything resembling a review happen before ship? Is it written down?
- Who can say "no" to a launch, and has that ever happened?
- For asset listings specifically: is there any assessment of legal status,
  and technical risk per asset?
- Are past launch decisions recoverable — could you produce the reasoning
  today?

**Red flags:**
- Listings/launches decided in a chat thread with no record.
- No one below the CEO empowered to block a launch.
- Assets listed with zero documented assessment (legal status of the token is
  the acquirer's favorite question).

**Recover cheaply:** A one-page launch checklist + a folder of completed
ones is a real gate. Retroactive memos for the biggest past decisions are
imperfect but far better than nothing.

**Research further:** Reconstruct the launch history and check which
decisions have any paper trail. Look at MiCA/FCA product-governance
expectations for the shape of what "good" looks like — then scale it down to
startup size.

**Advisors:** Regulatory counsel to set the gate's criteria; for asset
listings, a crypto due-diligence provider or counsel for token legal status.
This domain is mostly *process*, though — a fractional compliance officer can
stand it up in weeks.

---

## 4. Financial-crime basics

**Essence:** AML, KYC, sanctions — the baseline, done for real. A policy
written for the sale, or one sanctioned user, either reprices the deal.

**Day-one standard:** A real AML policy + a named responsible person (MLRO or
equivalent), KYC at onboarding, transaction monitoring, sanctions screening,
and a suspicious-activity reporting process.

**Triage questions:**
- Is there an AML policy, and does it describe what you *actually do* (not
  aspirationally)?
- Who is the named money-laundering reporting officer / compliance officer —
  and do they know they are?
- What happens at onboarding — identity verification by whom (vendor?), with
  what rejection criteria?
- Are users and transactions screened against sanctions lists (OFAC, UN, EU)
  — at onboarding only, or ongoing?
- Is there any transaction monitoring — even rules-based — and has anyone
  ever filed or considered filing a suspicious-activity report?
- For crypto flows: any blockchain-analytics screening of deposits and
  withdrawals?

**Red flags:**
- A polished policy that doesn't match operations ("written for the sale" is
  a phrase diligence teams use).
- No sanctions screening, or screening at onboarding only with no re-screen.
- One confirmed sanctioned user in the history — treat as Red always.
- KYC thresholds designed around avoiding KYC rather than doing it.

**Research further:** Test the actual funnel: open an account, see what's
checked. Ask the KYC/analytics vendors for coverage reports. Read the FATF
Recommendations (esp. R.15 and the VASP guidance) as the global baseline any
jurisdiction-specific regime will rhyme with.

**Advisors:** An AML/financial-crime consultant (design and remediation);
regulatory counsel for the registration/licensing consequences of being a
VASP/CASP; screening and blockchain-analytics vendors for tooling. If there
are live users and none of this exists, this advisor call is *this week's*
call.

---

## 5. Say only what you can legally say

**Essence:** Your old marketing is discoverable. A tweet you deleted two
years ago is still discoverable — and inherited by the acquirer.

**Day-one standard:** Risk warnings where required, no guaranteed-return
claims, and awareness that promo rules differ per jurisdiction.

**Triage questions:**
- Who writes and approves public-facing content (site, app copy, socials,
  influencers, community/Discord) — is there any review step?
- Have you ever promised, implied, or memed returns, yield, or "number go
  up"? (Include the token's Discord and the founders' personal accounts.)
- Do risk warnings appear where the top user markets require them (UK
  financial promotions, EU MiCA marketing rules, US securities-adjacent
  claims)?
- Any paid influencers or affiliates — with contracts and disclosure
  requirements, or informal?

**Red flags:**
- Guaranteed / "risk-free" / fixed-APY claims anywhere in the history.
- Influencer campaigns with no disclosure and no contracts.
- Marketing into a market the product legally can't serve (perimeter and
  marketing failures compound).
- The belief that deletion fixes anything — archives and screenshots are
  standard diligence sources.

**Research further:** Run the archive check on yourself before an acquirer
does: Wayback Machine on the site, a search of the official accounts'
history, the community channels' pinned messages. Inventory every claim
about returns or safety, and check the promo rules of the top user market.

**Advisors:** Regulatory counsel with financial-promotions expertise in the
key markets; a compliance-trained marketing reviewer for ongoing content. A
cleanup here is cheap; an inherited misleading-promotion liability is not.

---

## 6. Keep the receipts

**Essence:** Half of diligence is one question: can you produce it — and is
it current?

**Day-one standard:** Record retention, privacy compliance to roughly a
GDPR grade, and terms of service that match what the product actually does.

**Triage questions:**
- If asked today for: corporate documents, board decisions, user terms
  versions, KYC files, past marketing — could you produce each within days?
- Do the current terms of service describe the *current* product, and when
  were they last read against it?
- Is there a privacy policy, and does the data-handling reality match it
  (what's collected, where stored, who processes, retention periods)?
- Any data outside GDPR-safe processing — EU user data with vendors that
  have no processing agreements, say?

**Red flags:**
- Terms of service copied from another product and never adapted (diligence
  teams spot the leftover names).
- KYC/user records held by a vendor the startup couldn't extract them from.
- No versioning: nobody can say which terms a 2024 user accepted.
- Privacy policy promises ("we never share data") contradicted by the vendor
  list.

**Research further:** Build a data-room skeleton now — the standard M&A
checklist folder structure — and note what's missing; that gap list *is* the
triage output. Map data flows: what personal data, where, with whom.

**Advisors:** Corporate counsel for the data-room and records discipline;
privacy/data-protection counsel (or DPO service) for GDPR-grade review;
whoever manages vendors for the processing-agreement sweep.

---

## 7. Decentralized? Prove it. *(Decentralized projects only)*

**Essence:** "Show me you can't touch user funds" — or you're an unlicensed
operator. Or ring-fence what you can't exempt.

**Day-one standard:** Keep the protocol genuinely autonomous; ring-fence the
interface, fees, and marketing — the parts a company demonstrably controls —
into the regulated-or-restructured perimeter.

**Triage questions:**
- Can any key, multisig, or admin function held by the team (or its
  investors) upgrade the protocol, pause it, or touch user funds? Prove the
  answer on-chain, not in the whitepaper.
- Who runs the front-end, earns the fees, and does the marketing — and could
  a regulator treat that entity as the operator?
- If the company disappeared tomorrow, would the protocol keep working —
  fully, partially, or not at all?
- Is there a governance token, and does voting power actually decentralize
  control or concentrate it in the team/treasury?

**Red flags:**
- "Decentralized" in the marketing + an EOA admin key in the contracts. This
  is the single fastest way to be an unlicensed operator with extra steps.
- Upgradeable contracts with team-controlled proxies, described as immutable.
- Fee switch flowing to a company that claims to have no role.
- Governance theater: token votes that the team's holdings always decide.

**Research further:** An on-chain audit of admin functions — what can each
privileged key actually do, verified from the deployed contracts (block
explorers + the audit reports' access-control sections). Compare the claim
made in marketing against that reality; the *gap* is the risk. Follow how
regulators are treating "sufficient decentralization" in the relevant
markets — it is an evolving line, which is exactly why this domain needs
counsel rather than a blog post.

**Advisors:** Crypto-native regulatory counsel (the decentralization
question is jurisprudence-in-motion; generalists struggle); a smart-contract
security firm for the admin-key audit; potentially a foundation/DAO
structuring specialist if ring-fencing is the path.
