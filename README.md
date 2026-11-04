<p align="center">
  <img src="https://github.com/Nihal-Pandey-2302/Nihal-Pandey-2302/blob/main/Untitled%20design.png" alt="Banner" width="800"/>
</p>

<h1 align="center">Nihal Pandey</h1>
<h3 align="center">Senior Founding Engineer & Tech Lead @ Tvaram · Ex-PMO, Govt. of India · ParadeDB contributor · Author of poolproof</h3>
<p align="center"><b>Rust · Go · TypeScript · PostgreSQL · Redis</b></p>

<p align="center">
I build backend and data systems where being nearly correct is not good enough.
Most of my time goes into PostgreSQL: its executor internals at ParadeDB, the connection
poolers in front of it with poolproof, and the ingestion pipelines behind it at Tvaram.
Before that I wrote Rust security tooling at the Prime Minister's Office, and shipped
production systems on Solana, EVM, Stellar and Kaspa, winning five hackathons along the way.
</p>

<p align="center">
  <a href="https://linkedin.com/in/nihal-pandey-8529b6257/">
    <img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="https://x.com/PandeyNihal23">
    <img src="https://img.shields.io/badge/Twitter-000000.svg?style=for-the-badge&logo=X&logoColor=white"/>
  </a>
  <a href="mailto:pandeynihal232@gmail.com">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
  <a href="https://portfolio-nihals-projects-7da31bb2.vercel.app/">
    <img src="https://img.shields.io/badge/Portfolio-4285F4?style=for-the-badge&logo=google-chrome&logoColor=white"/>
  </a>
</p>

---

## Experience

**Senior Founding Engineer & Tech Lead · [Tvaram](https://tvaram.com/)** · Bengaluru · June 2026 – present\
Building **[Tasvam](https://tasvam.ai/)** and **[MailTitan](https://mailtitan.ai/)**.
- **Tasvam**, Tvaram's data intelligence platform, merges customer records scattered across systems into unified, enriched profiles for audience building. I own its backend architecture, storage layer, ingestion pipeline and production deployment (Go · PostgreSQL · Redis)
- **MailTitan** is enterprise email relay: dedicated sending infrastructure with separate IP pools for transactional and marketing traffic, automated bounce handling, and signed, idempotent delivery webhooks

**Cybersecurity Research Intern · Prime Minister's Office (PMO), Government of India** · New Delhi · June – Sept 2025
- Wrote Tokio-based Rust tooling that automated vulnerability scanning across critical government infrastructure, cutting manual assessment time by **over 60%** with no downtime during rollout
- Threat-modelling workflows I built were picked up by **2 internal teams**
- Details under NDA

**B.Tech, Electronics Engineering** · Rajiv Gandhi Institute of Petroleum Technology · 2022 – 2026

---

## Open Source

### [poolproof](https://github.com/Nihal-Pandey-2302/poolproof) · Rust · find out what breaks when you put a connection pooler in front of Postgres

Poolers like PgBouncer, PgDog and Supavisor are meant to be invisible. In transaction mode they mostly are, until a `SET` leaks to another client, a temp table appears in someone else's session, or half a query string silently never runs. poolproof replays small scenarios against plain Postgres and then through the pooler, and reports every step where the two differ. Postgres is the oracle, so no scenario hardcodes expected output.

- **50 scenarios** across **PgBouncer, PgDog, Supavisor, PgCat and Odyssey**, multiple versions each, on Postgres 17 and 18, with a [results site](https://nihal-pandey-2302.github.io/poolproof/) showing every step's trace and the version where a behaviour broke or got fixed
- Reproduces **14 upstream bugs** in PgBouncer, PgDog and Supavisor, e.g. PgDog acknowledging only the `BEGIN` of `BEGIN; INSERT; COMMIT` and never committing the insert ([pgdog#1849](https://github.com/pgdogdev/pgdog/issues/1849)), and Supavisor hanging on 4 pipelined requests in 9 of 10 runs ([supavisor#1239](https://github.com/supabase/supavisor/issues/1239))
- `poolproof scan` reads `pg_stat_statements` exports, Postgres logs or `.sql` files, parses them with the real Postgres parser, and flags queries that break under transaction pooling, checked against what your pooler version actually did. SARIF output for code scanning
- Runs real drivers (psycopg, pgx, node-postgres, pgjdbc) through each pooler; classifies failures as silent, error or hang, and separates documented limitations from bugs
- Ships as signed binaries for Linux, macOS and Windows (SHA256SUMS + build attestation) and as a GitHub Action for CI

### Contributions

**[ParadeDB](https://github.com/paradedb/paradedb) (YC S23) · Rust · PostgreSQL · Tantivy** · 3 merged, 787 lines across 15+ files

| PR | Status | What it does |
|---|---|---|
| [#4763](https://github.com/paradedb/paradedb/pull/4763) | ✅ Merged | `JoinScan` returned wrong rows on self-joins with duplicate sort keys. Traced it to late materialization in the optimizer and rewrote physical projection to bind columns by index instead of by name; caught a misbinding in my own fix during review and rebuilt it |
| [#4924](https://github.com/paradedb/paradedb/pull/4924) | ✅ Merged | Nested `ExecutorRun` panicked in `fake_aminsertcleanup` on PG16. Found a second bug on the recursive DML path mid-review, then replaced the depth counter with an RAII `FrameGuard` so every nesting level gets its own frame |
| [#4765](https://github.com/paradedb/paradedb/pull/4765) | ✅ Merged | Removed `ctid` from `SearchIndexScore` in favour of batched lookups, folding 5 duplicated ctid-lookup blocks into a single helper across 6 execution paths |
| [#5093](https://github.com/paradedb/paradedb/issues/5093) | 📝 Proposed | Replace the `resolve_physical_index` heuristic with explicit column lineage tracking, the structural follow-up to #4763 |

---

## Hackathons

| Year | Achievement | Prize |
|------|-------------|-------|
| 2026 | 1st Prize, UK AI Agent Hackathon, Kaspa Track ([KaspaSwarm](https://github.com/Nihal-Pandey-2302/kaspaswarm)) | USD 1,000 |
| 2026 | 3 prizes at Kaspathon (Top 5 Main Prize, Real-Time Data, Most Creative Use of Kaspa), 500+ global teams | USD 1,200 |
| 2025 | 1st place, Andromeda aOS Buildathon, 2,500+ global teams ([A.R.I.A.](https://github.com/Nihal-Pandey-2302/ARIA-QIE)) | USD 2,500 |
| 2025 | Global Top-Tier Finalist, Kraken Forge Hackathon, Performance Optimization ([kraken-rs](https://github.com/Nihal-Pandey-2302/kraken-rs)) | — |
| 2024 | Winner, Smart India Hackathon, NTRO Govt. of India, 50,000+ participants | INR 100K |
| 2024 | Winner, Graph-e-thon 2.0, Graphic Era TBI | INR 175K |

---

## Selected Projects

**[KaspaSwarm](https://github.com/Nihal-Pandey-2302/kaspaswarm)** · Python · FastAPI · React · WebSockets · Kaspa SDK · [Live Demo](https://kaspaswarm.vercel.app/)\
Autonomous AI agents post, bid on, solve and settle tasks as real Kaspa transactions, with an LLM verifier checking results before payment. Auction, escrow, transport and LLM services behind a React dashboard; PyTest, CI and one-command Docker Compose.

**[Kraken Market Data SDK](https://github.com/Nihal-Pandey-2302/kraken-rs)** · Rust · Tokio · Serde · WebSockets\
Async WebSocket ingestion benchmarked at **648,000 msgs/sec** via zero-copy deserialization and ring-buffer reuse; 100% message delivery across 50+ simulated network partitions.

**[Ethereum EVM Indexer](https://github.com/Nihal-Pandey-2302/rust-evm-indexer)** · Rust · Tokio · Axum · SQLx · PostgreSQL\
Indexed **10M+ transactions** with atomic SQL transactions: zero data-integrity failures across crash and block-reorg tests, idempotent reorg detection and rollback, read API on Axum.

**[Solana Stablecoin Standard](https://github.com/Nihal-Pandey-2302/sss-solana-stablecoin-sdk)** · Rust · Anchor · Token-2022 · TypeScript · [Live Demo](https://sss-solana-stablecoin-sdk.vercel.app/)\
OpenZeppelin-style SDK for Solana stablecoins in three tiers: minimal, compliant (Transfer Hook blacklist, Permanent Delegate seizure) and private (ZK Confidential Transfers PoC). TypeScript SDK, 15-command CLI, Helius indexer, admin dashboard; **19/19 Anchor tests** on Devnet.

**[A.R.I.A.](https://github.com/Nihal-Pandey-2302/ARIA-QIE)** · Solidity · Hardhat · IPFS · React\
RWA tokenization protocol: ERC-721 minting, on-chain marketplace and fractionalized ownership, with IPFS-anchored metadata and on-chain document hash verification.

More in [my repositories](https://github.com/Nihal-Pandey-2302?tab=repositories), including Solana Job Queue, Solana Webhook Processor, InjectiveQL, EVM Event Watchdog and VatanPay.

---

## Skills

| | |
|---|---|
| **Languages** | Rust, Go, TypeScript, Python, SQL, Solidity |
| **Backend** | Tokio, Axum, SQLx, Express, Bull, FastAPI, GraphQL, WebSockets, zero-copy deserialization |
| **Data** | PostgreSQL (executor internals, extensions, wire protocol, connection poolers), Redis |
| **Chains** | Solana (Anchor, Token-2022), EVM (Solidity, Hardhat), Stellar (Soroban), Kaspa |
| **Infra** | Docker Compose, GitHub Actions, AWS (EC2, S3), Prometheus/Grafana |

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=Nihal-Pandey-2302&label=Profile%20Views&color=0e75b6&style=flat"/>
</p>
