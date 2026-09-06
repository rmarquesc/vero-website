# Vero — Site Copy

Complete copy document for the Vero website, including all pages and the slide deck.
Last updated: 06 Sep 2026 (post-registry)

---

## 1. Navigation (all pages)

- Problem
- Mechanism
- Scope
- Sources
- Landscape
- Roadmap
- Progress

---

## 2. Homepage (index.html)

### Meta

- **Title:** Vero — Credibility you can prove
- **Description:** Vero is a verifiable credibility layer for people and organisations publishing online, built on Midnight. Prove a relevant credential or accountability claim — and choose what you reveal.

### Hero

- **Kicker:** Verifiable credibility · Midnight Buildathon
- **Headline:** Credibility you can prove.
- **Lede:** Vero is a verifiable credibility layer for people and organisations publishing online. Prove a relevant credential or accountability claim — and choose what you reveal.
- **CTAs:** Follow the build / See the mechanism

### Hero specimen (visual annotations)

- fig. 01 — disclosure path
- ZK / SELECTIVE
- witness · private
  - issuer: [redacted]
  - holder: [redacted]
  - credential_id: [redacted]
  - expires_at: [redacted]
  - type: accredited_journalist
- compact circuit · verified off-chain
- ledger · public
- A source, verified.
- Vero verified ✓
- The source chooses what to reveal. Identity can stay private — only the credential-backed fact becomes public.

### § 01 — The Problem

- **Headline:** Publishing is easy. Credibility is harder to prove.
- **Lede:** Anyone can publish. Not every source can prove what qualifies them to speak with authority.

**Clippings:**

1. **Platform badges** — "Prove platform approval."
   A checkmark tells you that a platform approved an account. It doesn't prove professional credentials or expertise.

2. **Content provenance** — "Prove where content came from."
   Provenance systems can show how content was created or changed. They don't necessarily prove the credentials of the source behind it.

3. **Professional credentials** — "Prove qualifications."
   Professional credentials already exist — but they are rarely portable, cryptographically verifiable trust signals on the open web.

- **Conclusion:** Vero connects these worlds by turning credentials into verifiable trust signals.

### § 02 — Mechanism

- **Headline:** Verifiable credibility, by design.
- **Lede:** Vero turns existing credentials into cryptographic proofs. The source decides how much of the underlying information to reveal.

**Four-stage schematic:**

1. **Source — Holds a credential:** A professional licence, organisational credential, or accountability claim — issued by a recognised body. It stays on the source's side.
2. **Circuit — Compact circuit:** Proves the credential is one of those in the issuer registry, and that it has not expired. The credential itself is never submitted — and the proof does not reveal *which* registered credential it is.
3. **disclose() — Choose what to reveal:** The source discloses only what it chooses. Identity can be public, associated with an organisation, or private.
4. **Render — Reader sees it:** The frontend reads the ledger and shows the verified signal next to the source or post.

**Disclosure choice:**

- identity public → ✓ verified
- identity private / pseudonymous → ✓ verified

- **Conclusion:** Identity and credibility don't have to be the same thing.

### § 03 — Scope

- **Headline:** What Vero verifies — and what it doesn't.

**Verifies:**

- ✓ Valid professional credentials — accredited journalist, licensed doctor, registered accountant, licensed engineer, other recognised professionals
- ✓ Recognised organisations — news outlets, research organisations, companies, crypto/Web3 organisations
- ✓ Credential validity — the credential is registered by a recognised issuer, and is not expired
- ✓ Accountability claims — an organisation can prove it is a recognised entity willing to stand behind what it publishes

**Doesn't verify yet:**

- × Whether a specific claim is true
- × Whether an opinion is correct
- × Whether content is scientifically accurate
- × Whether a publisher is politically or editorially trustworthy

- **Closing:** Vero verifies the source. It doesn't decide what you should believe.

### § 04 — Source Types

- **Headline:** Credibility isn't one-size-fits-all.

**Professionals:**
- Journalists
- Doctors
- Accountants
- Engineers
- Researchers
- Other credentialed professionals

**Organisations:**
- News outlets
- Research organisations
- Companies
- NGOs
- Crypto / Web3 organisations

**Pseudonymous:**
- A source can prove relevant credentials without necessarily revealing a legal identity.
- Example: @anon_eth — Vero verified ✓ — credential verified · identity: pseudonymous

### § 05 — Competitive Landscape

- **Headline:** Different trust problems need different proofs.

**Comparison table:**

| Approach | What it proves | Main limitation |
|---|---|---|
| Platform verification | Platform approval of an account | Controlled by the platform |
| Community Notes | Community consensus about a claim | Slow and platform-dependent |
| Fact-checking | Editorial judgement about a claim | Requires an intermediary |
| C2PA / Content Credentials | Content provenance and history | Doesn't primarily establish source credentials |
| Professional credentials | A person's or organisation's qualification | Usually not portable/verifiable where content is published |
| **Vero** | Verifiable credentials / accountability of the source | Early-stage ecosystem and issuer registry |

**C2PA distinction:**

- C2PA helps answer: "What happened to this content?"
- Vero helps answer: "What can this source prove about itself?"

- **Conclusion:** Vero doesn't replace fact-checking, Community Notes or content provenance. It addresses a different, upstream problem: giving sources a portable way to prove what they are qualified or authorised to claim.

### § 06 — Personas

- **Headline:** Three sides of the trust problem.

1. **Reader** — "Can I trust this source?"
   Readers need a simple signal that tells them what a source can actually prove about itself.

2. **Professional** — "Can I prove my credibility?"
   Professionals should be able to demonstrate relevant credentials without being forced to expose information they don't want to share.

3. **Organisation** — "Can we stand behind what we publish?"
   Organisations should be able to establish accountability and credibility around the content they publish.

### § 07 — Crypto / Web3 Use Case

- **Headline:** Credibility matters most when identity is complicated.
- **Lede:** Crypto and Web3 already operate with pseudonyms, DAOs, collectives and globally distributed organisations. Vero can separate a source's credibility from the requirement to expose a legal identity.
- **Example:** @protocol_research — Vero verified ✓ — credential / organisation verified · identity: pseudonymous
- **Note:** A particularly strong early use case — accountability and pseudonymity often coexist in Web3.

### § 08 — Adoption

- **Headline:** Two problems, not one.
- **Lede:** A registry with no issuers is worthless, and issuers with nowhere to show the signal are too. Whoever displays a Vero badge and whoever issues the credential behind it are different parties, with different reasons to move.

**Who displays it — Web3-native publishing, first:** Mirror, Farcaster, Lens and wallet-based social already assume a wallet, already understand proofs, and already publish under pseudonyms. Then individual publications and newsletters, where one editor can say yes. Then the platforms, which move last and only on evidence.

**Who issues it — bodies that already credential:** journalists' associations, medical councils, engineering orders. Vero does not ask them to make a new judgement, only to publish one they already make. Slow to adopt, which is why they follow rather than lead — but they are the only entities that can make the signal mean anything.

**Why anyone bothers before the ecosystem exists:**
- *The source* — a credentialed journalist who cannot safely publish under their own name wants this with or without a platform. That is demand, not adoption strategy.
- *The bot problem* — "a credentialed human stands behind this" is a signal no platform checkmark can give, and the need arrived recently and suddenly.
- *Regulation ahead* — the Digital Services Act and AI Act push platforms towards provenance obligations. Built early is cheaper than retrofitted under a deadline.

**Who operates the registry:** today, one registrar run by the project and labelled a demo. The destination is one registrar **per issuer** — whoever grants a credential is the only one who can say whether it still holds. That is why multiple registrars is the next contract work, not a later refinement.

- **Conclusion:** Vero does not need an ecosystem to be useful to its first source. It needs one source who cannot publish under their own name, and one reader who wants to know whether to listen.

### § 09 — Roadmap

- **Headline:** Four waves, one foundation.

1. **Wave 01 · Now — Prove:** Credential → ZK proof → Verified. Core mechanism proven end-to-end, with a Merkle registry of issuers and on-chain expiry.
2. **Wave 02 — Trust:** Wallet bridge → Governance → Revocation. Close the DApp Connector gap so a source can prove from the browser, then move beyond one registrar and deploy off the local devnet.
3. **Wave 03 — Expand:** Professionals → Organisations → Pseudonymous sources. Multiple credential types and verification policies.
4. **Beyond — Infrastructure:** Web → Social → Crypto → APIs. Browser overlay, platform integrations, verification API, broader credential ecosystem.

### § 10 — Current Status

- **Headline:** Where Wave 1 stands.

**Done:**
- ✓ Product concept, mechanism and naming finalized
- ✓ Competitive landscape, personas and risk notes documented
- ✓ Local Midnight dev stack — node, indexer, proof server
- ✓ Compact contract — Merkle issuer registry, expiry enforcement
- ✓ End-to-end proof flow on the local devnet
- ✓ Automated checks — end-to-end and proof-forgery regression

**Now:**
- Demo frontend connected end-to-end

**Next:**
- Demo video
- Wave 1 submission

- **Statement:** Wave 1 is about proving the mechanism — not building the entire product.
- **Deadline:** Wave 1 deadline · September 16, 2026
- **Link:** Read the full build log →

### Closing

- **Headline:** A trust layer for the open web.
- **Copy:** Vero starts with verifiable professional and organisational credentials — and a simple idea: sources should be able to prove what they are qualified to claim.

### Footer

- Built solo by **Rafaela Costa** — Strategic UX/UI designer & product builder.
- Compact implementation with AI-assisted tooling, guided by the Midnight community.
- Slide deck · GitHub repository
- Apache License 2.0 · Midnight Buildathon 2026

---

## 3. Progress Page (progress.html)

### Meta

- **Title:** Vero — Build log & status
- **Description:** Where the Vero buildathon project stands right now, and what's been done so far. Updated as Wave 1 progresses.

### § 00 — Status

- **Headline:** Where Wave 1 stands.
- **Intro:** A live record of what's done, what's in motion, and what's next — so I can stay oriented, and anyone following the buildathon can see where Vero is at.

**Stamp row:**
- live
- last updated 06 Sep 2026
- wave 1 of 4
- 9 of 11 milestones complete

**Done:**
- ✓ Product concept, mechanism and naming finalized
- ✓ Competitive landscape, personas and risk notes documented
- ✓ Local dev environment fully operational — Docker stack, wallet, and CLI tested
- ✓ Compact contract — Merkle issuer registry, expiry enforcement
- ✓ End-to-end proof flow on the local devnet
- ✓ Automated checks — end-to-end and proof-forgery regression
- ✓ Reader view — verified badge rendered from live ledger state
- ✓ Contract tests that need no devnet — 30 of them, under a second
- ✓ Multiple registrars — one per issuer type, appointed by governance

**Now:**
- Demo video

**Next:**
- Wave 1 submission

- **Statement:** Wave 1 is about proving the mechanism — not building the entire product.
- **Deadline:** Wave 1 deadline · September 16, 2026

### § 01 — Build Log

- **Headline:** What's been happening.
- **Lede:** Newest first. Each entry is one step forward — finished, in progress, or blocked.

**Entry 1 — 06 Sep 2026 · done**
- **Title:** One registrar per issuer type — and why the subject stopped building its own credential
- **Body:** The contract held a single registrar, so one authority granted every kind of credential. The adoption model does not work that way: the body that grants a credential is the only one that can say whether it still holds. There are now three roles — governance appoints registrars, a registrar grants credentials of its own issuer type, a holder proves — each with its own domain-separated commitment. The part that mattered was not the map but who builds the credential: earlier versions took a finished commitment from the subject, so a subject could take a commitment built as "accredited journalist" to whichever registrar was easiest to convince. The subject now hands over only a commitment to a secret it never reveals. Binding the granting registrar into the credential means replacing a registrar invalidates everything it granted — intended, since governance replaces a registrar precisely when it should no longer be trusted.

**Entry 2 — 06 Sep 2026 · done**
- **Title:** Thirty tests for the contract, and not one of them needs Docker
- **Body:** The only tests needed a running devnet, which is the right test for the wiring and the wrong one for the contract's logic — and it meant a fresh clone running the test command was told there were no tests. The suite now drives the compiled circuits directly through the Compact runtime: circuit execution is real, only the proving is skipped, and it runs in under a second. There is one test per rejection the contract can make, because a credential system that also verifies invalid credentials is worse than none — it looks like it works. Running in process makes block time settable, which bought two tests a live devnet cannot: the expiry boundary one second either side, and a regression for the millisecond trap.

**Entry 3 — 06 Sep 2026 · done**
- **Title:** A reader can now see the signal — and the wallet bridge is scoped for Wave 2
- **Body:** The demo had been a command line; there is now a frontend. The reader view queries the indexer, decodes the ledger with the contract's own decoder, and renders the verified badge beside a post — with no wallet, no account and nothing installed. The publisher view connects to a wallet and holds a credential but stops short of a proof: browser wallets speak DApp Connector API v4, which passes transactions as serialized strings, while the midnight-js version this contract uses expects objects. An official bridge exists for the proving half and none for the wallet half; writing that adapter is Wave 2 work, specified in docs/wave2-wallet-bridge.md.

**Entry 4 — 06 Sep 2026 · done**
- **Title:** Closing a privacy leak in the disclosed expiry
- **Body:** Verification discloses the credential's expiry, and an exact per-credential timestamp behaves like a serial number — two posts verified by the same credential share it, so an observer could group a pseudonymous source's posts without ever identifying them. Expiries are now issued rounded up to a shared quarter boundary. Removing the disclosure entirely is designed and deferred.

**Entry 5 — 06 Sep 2026 · done**
- **Title:** Credential registry — prove membership without revealing which credential
- **Body:** A Merkle tree of credential commitments replaces the single accepted credential. A source proves that one of the registered credentials is theirs, without revealing which. Registration is gated on a registrar secret; the subject derives its own commitment off-chain. The circuit binds the Merkle path to the prover's own commitment — without that, a public path alone would forge a proof — and a regression test plays that attacker.

**Entry 6 — 06 Sep 2026 · done**
- **Title:** Issuer type and expiry bound into the credential
- **Body:** The commitment binds secret, issuer type and expiry together, so a source cannot re-badge itself or extend its own validity while reusing a secret. The ledger records the issuer type per post rather than a bare flag. Expiry is enforced on-chain against block time.

**Entry 7 — 06 Sep 2026 · done**
- **Title:** Contract wired end-to-end — first real proof on the devnet
- **Body:** The deploy and CLI scripts still targeted the project template's placeholder circuit. They are now wired to the real Vero circuit. A dependency fix that had only existed in the original working copy was also committed, so a clean clone runs from scratch.

**Entry 8 — 05 Sep 2026 · done**
- **Title:** Local dev environment fully operational — Docker stack, wallet, and CLI tested
- **Body:** The local Midnight dev stack (node + indexer + proof server) is running successfully via Docker. A wallet has been created with test tokens (tNight and DUST), a contract has been deployed, and the CLI plumbing — deploy, transaction submission, ledger reads and balance checking — works end to end. The contract at this point was still the project template's placeholder circuit, so nothing was being verified yet.

**Entry 9 — 01 Sep 2026 · done**
- **Title:** Minimal Compact contract — compiling
- **Body:** The credential-verification circuit is being written in Compact. Currently working through the validity checks (issuer allowlist, expiry, scope) and getting the contract to compile cleanly against the local Midnight dev stack.

**Entry 10 — 01 Sep 2026 · done**
- **Title:** Product concept and positioning refined
- **Body:** Vero is now positioned as a verifiable credibility layer — not just identity verification. The core distinction: credibility is the product value, privacy/selective disclosure is a capability. Identity is optional: a source can be fully identified, associated with an organisation, or pseudonymous. The architecture — source → Compact circuit → selective disclosure → frontend — is settled, and the name "Vero" is chosen.

**Entry 11 — 01 Sep 2026 · done**
- **Title:** Competitive landscape, personas and risk notes documented
- **Body:** Comparison against platform verification, Community Notes, fact-checking, C2PA/Content Credentials, and professional credentials; three personas (reader, credentialed professional, organisation); and risk notes captured in the repo README. This is the foundation the rest of Wave 1 builds on.

### Footer

- Built solo by **Rafaela Costa** — Strategic UX/UI designer & product builder.
- Compact implementation with AI-assisted tooling, guided by the Midnight community.
- Back to overview · Slide deck · GitHub repository
- Apache License 2.0 · Midnight Buildathon 2026

---

## 4. Slide Deck (slides.html)

### Meta

- **Title:** Vero — Slide Deck
- **Description:** Vero pitch deck — Midnight Buildathon Wave 1, September 2026.

### Navigation

- Overview
- Progress
- Slides

### Slide 1 — Cover

- **Kicker:** Midnight Buildathon · Wave 1
- **Title:** Vero
- **Subtitle:** Credibility you can prove.
- **Tagline:** A verifiable credibility layer for online publishing, built on Midnight.
- **Footer:** Midnight Buildathon — Wave 1 · September 2026

### Slide 2 — The Problem

- **Label:** The problem
- **Headline:** Publishing online is easy. Proving credibility is hard.
- **Bullets:**
  - A post can come from a journalist, doctor, accountant, engineer, news outlet — or anyone.
  - Readers have no portable way to verify what a source can legitimately claim about itself.
  - Trust signals are fragmented: platform badges, screenshots, reputation, manual research.
- **Callout:** Vero focuses on one narrower problem: making source credibility provable.

### Slide 3 — The Solution

- **Label:** The solution
- **Headline:** From "an authority says so" to "a proof says so."
- **Steps:**
  1. Source holds a credential (journalist, professional, organisation)
  2. Compact circuit proves the credential is in the issuer registry, and unexpired
  3. Source discloses only what it chooses
  4. Reader sees a cryptographically verified signal
- **Callout:** Identity and credibility are separate dimensions.

### Slide 4 — Why Midnight

- **Label:** Why Midnight
- **Headline:** Why Midnight?
- **Bullets:**
  - **Selective disclosure** — prove "this publisher is credentialed" without exposing the credential
  - **Compact** — ZK circuit complexity abstracted into TypeScript-like code (matters for design-led teams)
  - **Dual-ledger model** — private witness data stays local, only verified outcome is anchored publicly
- **Callout:** This is the exact primitive the problem needs.

### Slide 5 — Demo

- **Label:** Demo
- **Headline:** Verified badge, on-chain.
- **Screenshot:** the reader view rendering live ledger state — one post unverified, one carrying the Vero verified badge
- **Caption:** The reader view, reading live ledger state. No wallet, no account, nothing installed.
- **Meta:**
  - Registry membership proven — without revealing which credential. Expiry enforced on-chain.
  - Local Midnight devnet · block 5995

### Slide 6 — Roadmap

- **Label:** Roadmap
- **Headline:** Roadmap

**Wave 1 · Prove (Aug 27 – Sep 16):**
- ✓ Concept, personas, competitive landscape
- ✓ Local dev stack operational
- ✓ Compact contract + end-to-end proof flow
- ✓ Merkle registry — one registrar per issuer type, expiry enforced
- ✓ Reader view — badge from live ledger state
- ✓ Contract test suite — 30 tests, no devnet needed
- → Demo video

**Wave 2 · Trust (Sep – Oct):**
- Wallet bridge — prove from the browser (DApp Connector ↔ midnight-js)
- Governance beyond a single key — multisig or on-chain vote
- Credential revocation and public-network deployment

**Wave 3 · Expand (Oct – Nov):**
- Multiple credential types
- Verification policies
- Broader demo surface

**Beyond · Infrastructure (Future):**
- Portable verification across websites and social feeds
- Browser integrations, APIs

### Slide 7 — Adoption

- **Label:** Adoption
- **Headline:** Two problems, not one.
- **A — Who displays it:** Web3-native publishing first (Mirror, Farcaster, Lens), then individual publications, then platforms.
- **B — Who issues it:** journalists' associations, medical councils, professional orders — publishing a judgement they already make.
- **Why before the ecosystem exists:** a source who cannot safely use their own name wants this regardless; generated content made "a credentialed human stands behind this" a signal no checkmark can give.
- **Callout:** One registrar *per issuer* — whoever grants a credential is the only one who can say whether it still holds. The contract has worked that way since Wave 1.

### Slide 8 — Team

- **Label:** Team
- **Headline:** Team
- **Photo:** assets/rafaela.png
- **Name:** Rafaela Costa
- **Role:** Strategic UX/UI designer & product builder
- **Callout:** Vero is a trust-signal design problem as much as a cryptography one — what a reader can understand at a glance decides whether any of the proof underneath matters. That is why it is built design-first.
- **Note:** Compact implementation written with AI-assisted tooling (Midnight Expert, Claude Code) and guidance from the Midnight Discord — which is what let a design-led author work at the contract level rather than around it.
- **Footer:** Built for the Midnight Buildathon — Wave 1.

### Footer (hidden in deck view)

- Built solo by **Rafaela Costa** — Strategic UX/UI designer & product builder.
- Compact implementation with AI-assisted tooling, guided by the Midnight community.
- Back to overview · Build log
- Apache License 2.0 · Midnight Buildathon 2026
