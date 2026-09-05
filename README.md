# Vero

**Credibility you can prove.**

Vero is a verifiable credibility layer for people and organisations publishing online, built on [Midnight](https://midnight.network). It lets a source prove that it satisfies a defined credential or accountability policy — such as being an accredited journalist, licensed professional, recognised outlet, or verified organisation — and choose how much of its identity or credential information to reveal.

Readers get a cryptographically backed trust signal that can travel beyond a single platform.

Built for the [Midnight Buildathon](https://akindo.io) — Wave 1.

---

## The Problem

Publishing online is easy. Establishing credible provenance is hard. A post can come from a journalist, doctor, accountant, engineer, news outlet, company, research organisation, or anonymous account — but the reader often has no portable way to verify what the source can legitimately claim about itself.

Today's trust signals answer different questions. A platform badge says an account was approved. Content Credentials can establish aspects of a file's provenance. Fact-checking evaluates individual claims. Professional credentials establish qualifications, but they are not designed primarily as portable, machine-verifiable trust signals for everything a source publishes online.

The result is a fragmented trust layer. Readers have to rely on platform decisions, screenshots of credentials, reputation, or manual research. Vero focuses on one narrower problem: **making source credibility provable.**

Vero does not decide whether a post is true. It provides evidence about the source behind it, so readers, platforms, and communities can make better-informed trust decisions.

## The Idea

Vero moves the trust marker from **"an authority says so"** to **"a proof says so."**

1. A source holds a credential or other verifiable evidence of eligibility — for example, a journalism credential, professional licence, recognised organisation credential, or an accountability credential.
2. A Compact **circuit** checks that the witness satisfies the required conditions, such as validity, non-expiry, issuer, scope, or other policy rules.
3. The source can disclose only the information it chooses to disclose. The proof can establish a credential-backed fact without requiring the underlying credential or personal data to become public.
4. A reader-facing frontend reads the resulting verification state and renders a trust signal next to the source or post.

**Identity and credibility are separate dimensions.** A journalist may publish under their real name and associate the proof with that identity. A small publication may publish under its brand. A pseudonymous crypto researcher may prove a relevant credential without revealing their legal identity.

This is Midnight's selective disclosure model applied to source credibility: prove the relevant fact, reveal only what is useful.

## What Vero Verifies — and What It Doesn't (Yet)

**Value proposition, in one line:** give readers verifiable evidence about the source behind a post, without requiring a single global authority to decide what is true.

At this stage, Vero verifies **credential-backed source claims** — for individuals, organisations, and eventually pseudonymous publishers. Examples include accredited journalists, licensed healthcare professionals, registered accountants or engineers, recognised news outlets, and organisations willing to take responsibility for what they publish.

A "Vero-verified" signal means that the source has cryptographically proven that it satisfies a defined verification policy. It does **not** mean that Vero has determined that a specific article, post, opinion, or claim is true.

The distinction is deliberate. Vero verifies **who or what a source is qualified or authorised to be**, while leaving content judgement to readers, editors, platforms, communities, or specialised fact-checking systems.

### Identity is optional

A source can choose to associate its proof with a public identity, publication, organisation, or pseudonym. Where the credential system supports it, the underlying identity can remain private while the relevant credential-backed fact is proven.

### Long-term vision

Vero can become a broader trust layer for online publishing: multiple credential types, issuer policies, portable verification, and integrations across websites, social platforms, and crypto/Web3 communities. Content-level verification may become a complementary layer later, but it is deliberately out of scope for the current build.

## Competitive Landscape

| Approach | What it actually proves | Where it fits | Main limitation |
|---|---|---|---|
| **Platform verification** (e.g. X) | The platform approved an account | Account identity / platform status | Controlled by one platform; meaning can change |
| **C2PA / Content Credentials** | Aspects of content origin, history, and provenance | Content | Does not primarily establish professional or organisational credibility |
| **Community Notes** | Community assessment of a specific claim | Content / claims | Requires participation and platform governance |
| **Traditional fact-checking** | Editorial assessment of a specific claim | Content / claims | Human-led, slower, and claim-specific |
| **Professional credentials** | A person or organisation satisfies a professional requirement | Qualification / authorisation | Credentials are not inherently portable trust signals for online publishing |
| **Vero** | A cryptographic proof that a source satisfies a defined credential or accountability policy | Source credibility | Early-stage issuer and policy ecosystem |

Vero is deliberately **complementary** to these systems. C2PA can help answer *"what happened to this content?"* Fact-checking can answer *"is this claim supported?"* Vero asks a different question: **"what can this source prove about itself?"**

## Why Midnight

- **Selective disclosure** is exactly the primitive this problem needs — prove "this publisher is credentialed" without exposing the credential.
- **Compact** abstracts the ZK circuit complexity into TypeScript-like contract code, which matters for a project built by a design-led, non-cryptography team.
- **Dual-ledger model** keeps the private witness data local while anchoring only the verified outcome publicly.

## Architecture (high level)

```
Publisher's credential (private witness)
        │
        ▼
  Compact circuit  ──assert──▶  validity checks (issuer, expiry, scope)
        │
        └──disclose()──▶  `verified: bool`  ──▶  Midnight ledger
                                                      │
                                                      ▼
                                        Frontend reads ledger state
                                                      │
                                                      ▼
                                     "Verified" badge rendered on the post
```

### Planned components
- `/contracts` — Compact contract(s): credential-verification circuit and ledger state.
- `/frontend` — minimal demo interface: a sample feed showing the verified source signal, wired to the local proof server. Planned components: `VerifiedBadge` (states: verified / pending / failed), `CredentialSelector` (publisher-side demo), `ProofStatus` (generating / verifying / done).
- `/docs` — supporting design notes: personas, competitive research, risk notes ([docs/personas.md](./docs/personas.md)).

## Project Status

This repository is being built for **Wave 1** of the Midnight Buildathon (Aug 27 – Sep 16, 2026).

- [x] Product concept, mechanism, and naming finalized
- [x] Competitive landscape, personas, and risk notes documented
- [ ] Minimal Compact contract (credential-verification circuit) — compiling
- [ ] Local dev stack wired up (node, indexer, proof server)
- [ ] Demo frontend connected end-to-end
- [ ] Tests
- [ ] Slide deck + demo video

This section will be updated as each piece lands — see commit history for progress.

## Getting Started

*This section is a placeholder and will be filled in once the Compact contract and local dev setup are committed.* The project runs entirely locally against Midnight's local dev stack (node + indexer + proof server) — no wallet or real tokens required for evaluation.

```bash
# planned:
git clone <this repo>
cd vero
# midnight-local-dev setup instructions will go here
# contract compile + test instructions will go here
# frontend run instructions will go here
```

## Roadmap

**Wave 1 — PROVE (Aug 27 to Sep 16):** establish the core mechanism end-to-end: credential witness → Compact verification → selective disclosure → Midnight ledger → reader-facing verified signal. Research, competitive positioning, personas, and product scope are documented.

**Wave 2 — TRUST:** introduce the first issuer/trust-registry model, starting with a small manually maintained allowlist; build credential issuance; strengthen automated testing; refine publisher and reader UX.

**Wave 3 — EXPAND:** support multiple credential types, including individual professionals and organisations/outlets; introduce verification policies so readers can understand which issuers or credential standards a signal represents; broaden the demo surface.

**Beyond the buildathon — INFRASTRUCTURE:** portable verification across websites and social feeds, browser integrations, APIs, and additional source/accountability credentials. Content-level verification may become a complementary layer later.

## Team

Built solo by **Rafaela** — UI/UX designer, design lead. Non-cryptography background; Compact implementation developed with AI-assisted tooling (Midnight Expert, Claude Code) and community guidance via the Midnight Discord.

## Website

This repo also hosts a small static site that documents the project and tracks Wave 1 progress:

- `index.html` — landing page: problem, how it works, scope, landscape, personas, roadmap.
- `progress.html` — current status checklist + a chronological build log, updated as work lands.
- `assets/styles.css` — shared stylesheet.

**Run locally:** open `index.html` directly in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

**Publish on GitHub Pages:** the included workflow at `.github/workflows/deploy.yml` deploys on every push to `main`. In the repo settings (Settings → Pages), set "Source" to **GitHub Actions**. Before deploying, replace `YOUR-USERNAME` in `index.html` and `progress.html` with the actual GitHub username/repo.

The site is plain HTML + CSS with no build step, so it can also be dropped into a subfolder of a personal site or portfolio.

## License

Apache License 2.0 — see [LICENSE](./LICENSE).
