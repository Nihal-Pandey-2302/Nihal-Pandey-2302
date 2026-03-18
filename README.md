<p align="center">
  <img src="https://github.com/Nihal-Pandey-2302/Nihal-Pandey-2302/blob/main/Untitled%20design.png" alt="Banner" width="800"/>
</p>

<h1 align="center">Nihal Pandey</h1>
<h3 align="center">Backend and Blockchain Engineer | Rust · Node.js · TypeScript · Solana · EVM</h3>

<p align="center">
I build high-throughput backend systems and the blockchain infrastructure around them.
My backend work includes a Rust WebSocket engine at 648k msgs/sec, an EVM indexer handling
10M+ transactions, a GraphQL gateway at 15ms response time, and a production Node.js webhook
processor with job queues, dead letter queues, and full observability. On Solana I have shipped
a Token-2022 stablecoin SDK with Transfer Hooks and ZK proofs and an on-chain job queue with
a native binary max-heap. I write Rust for performance-critical systems and Node.js with
TypeScript for everything else.
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

**[Solana Stablecoin Standard (SSS)](https://github.com/Nihal-Pandey-2302/solana-stablecoin-standard)** | Rust · Anchor · Token-2022 · TypeScript · Next.js · Docker
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
