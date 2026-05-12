<p align="center">
  <img src="https://github.com/Nihal-Pandey-2302/Nihal-Pandey-2302/blob/main/Untitled%20design.png" alt="Banner" width="800"/>
</p>

<h1 align="center">Nihal Pandey</h1>
<h3 align="center">Backend Engineer | OSS Contributor at ParadeDB (YC S23) · Rust · Node.js · PostgreSQL</h3>

<p align="center">
I build high-throughput backend systems in Rust and Node.js, with a focus on 
performance, reliability, and correctness. Currently contributing to ParadeDB 
(YC S23) - PR #4765 merged into the production Rust codebase, three more in 
review touching the BM25 scan path, JoinScan correctness, and query pipeline 
internals. Previously built Rust security tooling at the Prime Minister's Office, 
Government of India, deployed across critical infrastructure. On the blockchain 
side I've shipped production systems on Solana, EVM, and Stellar - from a 
Token-2022 stablecoin SDK with ZK proofs to an EVM indexer handling 10M+ 
transactions with atomic SQL guarantees.
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
## Open Source

**[ParadeDB](https://github.com/paradedb/paradedb) (YC S23) — Rust · PostgreSQL · Tantivy**

| PR | Status | What it does |
|---|---|---|
| [#4765](https://github.com/paradedb/paradedb/pull/4765) | ✅ Merged | Removed `ctid` from `SearchIndexScore`; consolidated duplicate lookup logic into a centralized `resolve_ctid` helper across 5 execution paths |
| [#4924](https://github.com/paradedb/paradedb/pull/4924) | 🔄 In Review | Fixed nested `ExecutorRun` panic in `fake_aminsertcleanup` on PG16; replaced depth-counter with RAII `FrameGuard` after identifying a second correctness bug mid-review |
| [#4763](https://github.com/paradedb/paradedb/pull/4763) | 🔄 In Review | Fixed `JoinScan` returning wrong rows on self-joins with duplicate sort keys; caught a column misbinding in my own fix and rebuilt using physical index mapping |
| [#4752](https://github.com/paradedb/paradedb/pull/4752) | 🔄 In Review | Added partition-aware BM25 search via SPI expansion; fixed lifecycle panics in `begin_custom_scan` and `rescan` for partitioned index relations |

---

## Backend Systems

**[Kraken Market Data SDK](https://github.com/Nihal-Pandey-2302/kraken-rs)** | Rust · Tokio · Serde · WebSockets
- Async WebSocket ingestion engine benchmarked at **648,000 msgs/sec** via zero-copy deserialization and ring-buffer reuse
- 100% message delivery across 50+ simulated network partition scenarios using exponential backoff with jitter
- Global Top-Tier Finalist, Kraken Forge Hackathon 2025

**[Ethereum EVM Indexer](https://github.com/Nihal-Pandey-2302/rust-evm-indexer)** | Rust · Tokio · Axum · SQLx · PostgreSQL · Docker
- Production ingestion pipeline indexing **10M+ transactions** with atomic SQL guarantees and zero data integrity failures across crash and block-reorg scenarios
- Idempotent block reorganization detection and rollback handling; REST API with pagination and block range queries

**[Solana Webhook Processor](https://github.com/Nihal-Pandey-2302/solana_webhook_processor)** | Node.js · TypeScript · Express · Bull · Redis · PostgreSQL · Docker
- Production webhook ingestion service for Helius: Bull/Redis job queue keeps the HTTP layer non-blocking, background worker parses and persists normalized transaction data to PostgreSQL
- Dead letter queue with `/dlq` retry and discard API, idempotent ingestion via signature deduplication, alert rules engine firing email or Telegram notifications on user-defined chain conditions
- Pino structured logging, typed error classes, graceful SIGTERM shutdown, health check with per-dependency latency, metrics endpoint; **11/11 Jest tests passing**

**[InjectiveQL](https://github.com/Nihal-Pandey-2302/injectiveql)** | Node.js · TypeScript · Apollo GraphQL · PostgreSQL · Redis · Docker
- GraphQL and REST gateway over Injective SDK with pre-computed volatility, liquidity scoring, arbitrage detection, and whale tracking
- **15ms average response time** via multi-tier Redis and PostgreSQL caching; NFT-gated rate limiting; **8/8 tests passing**
- [Live Docs](https://nihal-pandey-2302.github.io/injectiveql/)

---

## Solana

**[Solana Stablecoin Standard (SSS)](https://github.com/Nihal-Pandey-2302/sss-solana-stablecoin-sdk)** | Rust · Anchor · Token-2022 · TypeScript · Next.js · Docker
- OpenZeppelin-equivalent SDK for Solana stablecoins: SSS-1 minimal, SSS-2 compliant (Transfer Hook blacklist enforcement, Permanent Delegate seizure), SSS-3 private (ZK Confidential Transfers PoC)
- TypeScript SDK, 15-command CLI, Helius webhook indexer to PostgreSQL, Docker backend, Next.js admin dashboard with live Switchboard oracle feeds
- **19/19 Anchor tests passing**, deployed live on Solana Devnet
- [Live Demo](https://sss-solana-stablecoin-sdk.vercel.app/)

**[Solana Job Queue](https://github.com/Nihal-Pandey-2302/solana-job-queue)** | Rust · Anchor · TypeScript · Next.js
- Redis/SQS-style job queue rebuilt entirely on-chain: native **O(log n) binary max-heap** in Queue PDA, DAG task dependencies via cryptographic prerequisite validation using `remaining_accounts`
- Full worker lifecycle, dead letter queue via retry count, scheduled execution, rent reclamation; Next.js dashboard
- **17/17 tests**, benchmarked at 400 TPS per isolated Queue PDA
- [Live Demo](https://solana-job-queue.vercel.app/)

---

## EVM and Web3

**[A.R.I.A. – RWA Tokenization Protocol](https://github.com/Nihal-Pandey-2302/ARIA-QIE)** | Solidity · Hardhat · IPFS · React · TypeScript
- ERC-721 smart contracts for NFT minting, on-chain marketplace trading, and DeFi fractionalized asset ownership; IPFS-anchored tamper-proof metadata with on-chain document hash verification
- **Winner — Andromeda aOS Global Buildathon 2025, 1st of 2,500+ global teams (USD 2,500)**

**[EVM Event Watchdog](https://github.com/Nihal-Pandey-2302/evm_event_watchdog)** | Rust · Multi-Chain
- Real-time exploit detection across Ethereum, Polygon, and Arbitrum with sub-second latency
- Terminal UI dashboard with Telegram and Discord webhook alerts
- [Live Demo](https://nihal-pandey-2302.github.io/evm_event_watchdog/)

---

## Stellar

**[VatanPay](https://github.com/Nihal-Pandey-2302/VatanPay)** | TypeScript · Soroban (Rust) · React · Stellar SDK
- Live remittance protocol on Stellar Testnet: Soroban smart contract with escrow, Stellar DEX path payments for atomic USDC to INR conversion, full MoneyGram anchor model (SEP-24)
- Targets the $50B Gulf-India remittance corridor at 0.5% vs 5 to 7% industry average
- [Live Demo](https://vatan-pay.vercel.app/)

---

## Skills

| | |
|---|---|
| **Rust** | Tokio, Axum, SQLx, zero-copy deserialization, async concurrency |
| **Node.js** | Express, TypeScript, Bull, Jest, Pino, Zod |
| **Data** | PostgreSQL (raw SQL), Redis, Docker, Helius webhooks |
| **Solana** | Anchor, Token-2022 (Transfer Hooks, Permanent Delegate, Confidential Transfers), PDA design, Soroban |
| **Web3** | Solidity, ERC-721/ERC-20, Hardhat, IPFS, DeFi protocols |
| **Frontend** | Next.js, React, GraphQL (Apollo Server 4), Chakra UI |
| **Infra** | AWS (EC2, S3), Docker Compose, Prometheus/Grafana (basic) |

---

## Recognition

| Year | Achievement | Prize |
|------|-------------|-------|
| 2025 | 1st place, Andromeda aOS Buildathon, 2,500+ global teams | USD 2,500 |
| 2025 | Global Top-Tier Finalist, Kraken Forge Hackathon | — |
| 2024 | Winner, Smart India Hackathon, NTRO Govt. of India, 50,000+ participants | INR 100K |
| 2024 | Winner, Graph-e-thon 2.0, Graphic Era TBI | INR 175K |

**Cybersecurity Research Intern, Prime Minister's Office, Govt. of India** (June to Sept 2025)
Rust-based security tooling for critical infrastructure. Details under NDA.

---

## Open to
```yaml
Roles:    Backend Engineer · Solana Engineer · Blockchain Backend · Rust Engineer
Type:     Full-time, Remote
Status:   Available immediately
```

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=Nihal-Pandey-2302&label=Profile%20Views&color=0e75b6&style=flat"/>
</p>
