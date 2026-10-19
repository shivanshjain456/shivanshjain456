# Shivansh Jain

**Final-year CSE (AI/ML) undergraduate at Manipal Institute of Technology, Bengaluru.** I build production-minded backend, full-stack, and applied-AI systems, and I maintain [docket-dev-org](https://github.com/docket-dev-org).

## Featured Projects

### Docket
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://docket-dev-org.github.io/docket/assets/logo-horizontal-dark.svg">
  <img src="https://docket-dev-org.github.io/docket/assets/logo-horizontal.svg" alt="Docket: a local budget-and-evidence layer for AI agents" height="56">
</picture>

*A local budget-and-evidence layer for AI agent runs, published on PyPI as [`docket-ai`](https://pypi.org/project/docket-ai/).*

- **Caps bind outside the agent.** A recording boundary refuses the call that would cross the spending cap, and a supervisor terminates the run. No account, no server, no telemetry, and zero runtime dependencies.
- **Every run emits a receipt.** A hash-chained, RFC 6962 Merkle-rooted ledger records model calls, tool calls, and file changes; a verifier recomputes costs from raw token counts and an embedded price table, offline.
- **The format is a contract.** `docket/receipt/v1` is frozen by a written specification and a 44-vector conformance corpus (42 negative, 2 positive), held to three implementations that share no code: the Python reference, a zero-dependency Node verifier, and a clean-room Go verifier written from the spec alone.
- **Engineered like evidence infrastructure.** 1,216 tests, fully offline; `make check` adds lint, mypy, bandit, the Node verifier, the conformance corpus, and deployment checks. Docker, Compose, Helm, and Kubernetes artifacts, with docs, release, and security workflows.

`Python` `Go` `Node.js` `RFC 6962 Merkle` `Ed25519` `HMAC` `PyPI` `Helm/Kubernetes`

[Repository](https://github.com/docket-dev-org/docket) · [Documentation](https://docket-dev-org.github.io/docket/) · [PyPI](https://pypi.org/project/docket-ai/) · [Specification](https://github.com/docket-dev-org/docket/blob/main/spec/docket-receipt-1.md)

### DocScout
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/shivanshjain456/DocScout/master/docs/brand/svg/docscout-primary-dark.svg">
  <img src="https://raw.githubusercontent.com/shivanshjain456/DocScout/master/docs/brand/svg/docscout-primary.svg" alt="DocScout: citation-grounded regulatory retrieval over RBI and SEBI circulars" height="56">
</picture>

*Citation-grounded search and question answering over RBI and SEBI circulars. Every answer cites its source, or it refuses.*

- **Measured retrieval.** Hybrid BM25 + BGE-small-en-v1.5 with reciprocal-rank fusion and regulatory-acronym expansion: Recall@5 of 0.966 and MRR of 0.854 on a committed 365-item gold set, with p95 retrieval latency of 48 ms cold / 2.1 ms warm in committed bench reports.
- **Grounded generation.** Calibrated answering with 100% citation precision on a double-labelled set, and an abstention gate for unanswerable questions.
- **A platform, not a notebook.** FastAPI over PostgreSQL with a React analyst console, Docker/Compose deployment, and a corpus ingestion pipeline with PDF extraction, chunking, embeddings, a provision/citation graph, and PII scanning.
- **Eval-gated CI.** Mutation-score ratcheting, differential patch-coverage gates, cryptographic provenance checks, gitleaks, and an SBOM supply-chain audit, against a seven-document specification set with numbered ADRs.

`Python` `FastAPI` `PostgreSQL` `React` `BM25 + embeddings` `Docker`

[Repository](https://github.com/shivanshjain456/DocScout)

### ShopCore
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/shivanshjain456/shopcore/main/public/brand/svg/shopcore-primary-dark.svg">
  <img src="https://raw.githubusercontent.com/shivanshjain456/shopcore/main/public/brand/svg/shopcore-primary.svg" alt="ShopCore: full-stack commerce and financial transaction platform" height="56">
</picture>

*A full-stack commerce engine with financial-transaction discipline: integer-money accounting, zero-trust pricing, atomic inventory.*

- **Money that survives arithmetic.** All amounts are integer paise; the server recomputes every price, discount, and GST figure from the database inside an atomic Prisma transaction (52 models, 16 migrations), and conditional stock decrements stop overselling in the concurrency test suites.
- **Orders that survive retries.** Idempotency keys with SHA-256 payload fingerprints prevent double placement; dual HttpOnly session boundaries (customer vs staff) with refresh-token rotation, HMAC-CSRF, and mutation audit logging prevent privilege escalation.
- **The domain is real.** UPI/UTR payment verification with replay deduplication, B2B tier pricing with GSTIN checksum validation and a counter-quote lifecycle, an in-process background job runner, and a 13-section homepage CMS.
- **44 dedicated test suites** (auth, idempotency, stock and price-integrity concurrency, rate limiting, and more) run in CI with lint and full production builds.

`TypeScript` `Next.js 14` `React` `Prisma + SQLite WAL` `Zod` `Sharp`

[Repository](https://github.com/shivanshjain456/shopcore)

### OSINTiger
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/shivanshjain456/osintiger/main/public/brand/svg/osintiger-primary-dark.svg">
  <img src="https://raw.githubusercontent.com/shivanshjain456/osintiger/main/public/brand/svg/osintiger-primary.svg" alt="OSINTiger: multi-source intelligence and threat research platform" height="56">
</picture>

*Multi-agent open-source intelligence and threat analysis, where every claim must trace back to hashed evidence.*

- **Wide collection, no paid keys.** Telemetry from 74 public sources (DNS, TLS certificate logs, corporate registries, sanction lists, blockchain explorers, threat feeds), gathered by an async pipeline with per-source timeouts and partial-failure tolerance.
- **Provenance before prose.** Every raw payload is SHA-256 hashed into an append-only ledger before analysis, and any model-generated claim without `[SOURCE: name, URL: url]` attribution is flagged for human review.
- **Analytical tradecraft, built in.** Analysis of Competing Hypotheses (Heuer) and an Advocate-vs-Skeptic debate engine, with Admiralty/NATO source-reliability grading across tiers.
- **Credential safety.** BYO-LLM API keys encrypted at rest with AES-256-GCM and scrypt key derivation, decrypted only in memory during dispatch.

`TypeScript` `Next.js 16` `React 19` `Prisma` `AES-256-GCM` `Vitest`

[Repository](https://github.com/shivanshjain456/osintiger)

### CanICarryIt.com *(live)*
<img src="https://canicarryit.com/favicon.svg" alt="CanICarryIt.com: can you bring it on a plane?" height="56">

*Aviation-compliance platform: TSA and CATSA checkpoint rules for 918+ travel items, in plain English.*

- **Live product at [canicarryit.com](https://canicarryit.com/).** Per-item rules with exact limits, 17-airline baggage comparisons, battery watt-hour calculator, bag sizer, pack checklist, and an offline airport-security game. The item Q&A runs on-device; nothing is uploaded.
- **Six generated languages** (English, French, Spanish, German, Japanese, Arabic), each with its own sitemap.
- **Edge-native build.** Cloudflare with Astro and TypeScript on D1, Playwright-tested, with multilingual static generation and serverless ingestion.

`Astro` `TypeScript` `Cloudflare` `D1` `Playwright`

[Live site](https://canicarryit.com/)

---

## More work

- **[Browser Workflow Tools](https://github.com/shivanshjain456/browser-workflow-tools)**: seven production-grade, zero-dependency userscripts, including [Codebase Uploader](https://github.com/shivanshjain456/browser-workflow-tools/tree/main/scripts/codebase-uploader) (packages a repository into token-budgeted Markdown for 20+ AI chat UIs), [Web Archives](https://github.com/shivanshjain456/browser-workflow-tools/tree/main/scripts/web-archives) (Wayback, Archive.today, Perma.cc, Software Heritage), and [Save Image as Type](https://github.com/shivanshjain456/browser-workflow-tools/tree/main/scripts/save-image-as-type) (local conversion and metadata stripping). Audited permission and privacy matrices per script; path-filtered CI runs syntax, secret, and privilege checks. `JavaScript` `Userscripts` `MIT/AGPL-3.0`
- **[Telegram Migration Pipeline](https://github.com/shivanshjain456/telegram-migration-pipeline)**: crash-resilient MTProto migration and archiving for Telegram channels: 100-message RPC batches with server-side media copy, deterministic SHA-256 checkpoint/resume, adaptive FloodWait backoff, and a PyQt6 GUI bridged to asyncio alongside a Rich CLI. `Python` `Telethon` `asyncio` `PyQt6`
- **[VeriFix](https://github.com/shivanshjain456/neatHack)** *(repo `neatHack`; built solo as Team HyperX for the neatHack 2026 hackathon)*: a coding agent that accepts a patch only after every caller of the changed function has been re-executed against it, with static and dynamic assurance gates and rollback on regression. Its controlled three-arm experiment repaired 5/5 planted bugs at 871 mean context tokens versus 2,383 for whole-repository context, with the planted caller-breaking regression rolled back; 175 offline tests, and 43 published claims recomputed by CI on every push. `Python` `AWS Lambda` `neatlogs` `Entire`


## Core stack

- **Languages:** TypeScript, Python, JavaScript, Go, SQL
- **Frameworks & runtimes:** Next.js (14/16), React (18/19), FastAPI, Node.js, asyncio/Telethon, PyQt6, Prisma
- **Data & retrieval:** PostgreSQL, SQLite (WAL), BM25 + embedding retrieval with rank fusion, hash-chained and Merkle-rooted ledgers
- **Platform & delivery:** Docker, Kubernetes/Helm, Cloudflare, GitHub Actions, PyPI packaging, mkdocs
- **Security & verification:** Zod boundary validation, JWT/session rotation, AES-256-GCM, Ed25519 and HMAC sealing, SAST, secret scanning, SBOM audits, Playwright, Vitest, pytest

## Contact

[LinkedIn](https://www.linkedin.com/in/456-shivansh-jain/) · [Email](mailto:shivanshjain456@gmail.com) · [docket-dev-org](https://github.com/docket-dev-org)
