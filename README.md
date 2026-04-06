# Mikael Hillman Pepin
**AI Systems Architect & Quantitative Engineer**

I architect domain-agnostic, self-evolving agent ecosystems that deliver asymmetric speed, scale, and cost-efficiency to complex data environments. My flagship implementation is a full-stack, autonomous quantitative trading lab. By engineering custom Model Context Protocol (MCP) toolchains and human-guided semantic memory networks, I build digital workforces capable of everything from multi-asset volatility modeling to unstructured data investigation.

---

### Core Agent Infrastructure & The "Engine"
*The generalized nervous system designed for rapid deployment, massive scale, and continuous, human-guided architectural evolution.*

* **Semantic Memory & Context (Mem0 & RAG):** Built a persistent memory network utilizing Qdrant and BAAI/bge-m3 embeddings with BM25 hybrid reranking, allowing agents to maintain long-term context across discrete sessions.
* **MCP Ecosystem Engineering:** Developed custom MCP servers (via FastMCP and MCP SDK) that grant LLM agents read/write capabilities over indexed codebases, active trading environments, and local file systems.
* **Automated Reverse-Engineering (`traceforge`):** Engineered a TypeScript/Playwright agent tool to autonomously reverse-engineer undocumented website APIs from browser traffic, creating a scalable pipeline for alternative data ingestion.

### Flagship Implementation: Autonomous Quant Lab (`mm-infra`)
*A production-grade quantitative monorepo serving as the primary proving ground for my agentic infrastructure. The agents actively monitor, optimize, and write code to evolve the system under my guidance.*

* **Agent-Driven Options & Volatility:** Integrated complex pricing engines (Black-Scholes, Bjerksund-Stensland, FFT exotics) and jump-robust volatility estimators (GARCH, HAR) directly into the `mm-mcp` server for autonomous research and execution.
* **Self-Optimizing Execution (`mm-ibkr-mcp`):** Deployed an Interactive Brokers execution interface (23+ tools) allowing agents to handle health checks, dynamic position sizing, and complex basket execution based on real-time slippage and PnL monitoring.
* **Signal-to-Order Pipeline:** Built a deterministic Pydantic/ZMQ/FastAPI architecture that calculates positions and verifies risk parameters before execution.

### Proof of Flexibility: Unstructured Investigation Systems
*Demonstrating the multi-purpose flexibility of the underlying agent scaffolding on highly unstructured, non-deterministic data.*

* **Asynchronous Data Synthesis (`crime_investigator_system`):** Built an OpenCode-based framework utilizing interacting subagents (evidence-intake, timeline-analyst, hypothesis-challenger) to autonomously process, synthesize, and challenge hypotheses within complex, multi-threaded investigations.

### Infrastructure, Security & Homelab
*The physical and network foundation required to run local AI models and live trading nodes securely.*

* **Air-Gapped Architecture:** Designed an isolated home network with dedicated VLANs (Vault, DMZ, Lab) and Tailscale end-to-end encryption.
* **Hardware Segregation:** Enforced strict physical separation between the high-compute AI development/training environment and the deterministic, low-latency live trade execution nodes.

---

## Main Projects in Detail

### mm-infra (Quantitative Monorepo)
A production-grade `uv` workspace with 8 namespace packages under `mm.*`:

| Package | Purpose |
|---------|---------|
| **mm-data** | Multi-source market data fetching (Yahoo, MSN, ETFdb, FRED, WRDS) |
| **mm-options** | Options pricing: Black-Scholes, Bjerksund-Stensland, eSSVI calibration, FFT exotics, full Greeks |
| **mm-volatility** | Volatility models: GARCH, GJR-GARCH, DCC, HAR, jump-robust estimators |
| **mm-portfolio** | Portfolio optimization: HRP, MVO, Black-Litterman, CVaR, ERC, covariance shrinkage |
| **mm-selection** | Model selection: stepwise regression with AIC/BIC/adj-R2 |
| **mm-core** | Primitives: zero curve bootstrapping, optimization engines, numerical utilities |
| **mm-strategies** | Trading strategies: PE rebalance, intraday mean reversion, signal trader, VRP harvesting |
| **mm-mcp** | MCP server exposing all above capabilities to AI agents |

All packages are vectorized (no loops over arrays), use `BlockedTimeSeriesSplit` to prevent data leakage, and are verified against reference implementations.

### crime_investigator_system
An OpenCode-based crime investigation framework built on the same agent infrastructure used for quantitative work. It demonstrates that the same tools can handle highly unstructured, non-deterministic data analysis:

* **Lead agent**: `crime-investigator` owns case strategy, caseboard maintenance, and final synthesis
* **Specialist subagents**:
  * `evidence-intake`: Extracts attributable facts and provenance from source material
  * `visual-evidence-intake`: Reviews rendered pages and image crops when OCR is insufficient
  * `timeline-analyst`: Normalizes chronology and surfaces contradictions
  * `hypothesis-challenger`: Maintains competing theories and pressures them with disconfirming evidence
  * `brief-writer`: Converts the caseboard into operational summaries or final briefings

All working state lives in markdown artifacts (`case-brief.md`, `evidence-log.md`, `timeline.md`, `hypotheses.md`), making the investigation process fully transparent and auditable.

### traceforge (Reverse Engineering Agent Tooling)
A TypeScript MCP server for autonomous API discovery and reverse-engineering:

* **Capture**: Uses Playwright to capture browser network traffic as users interact with any website
* **Discovery**: Analyzes captured requests to identify data endpoints, separating useful data loads from page shell and analytics noise
* **Lineage**: Traces values from the UI back to their source endpoints
* **Replay**: Replays captured requests with optional mutations to probe parameter requirements and validation rules
* **Export**: Generates OpenAPI 3.0.3 specs and TypeScript type definitions from captured samples

This enables rapid ingestion of alternative data sources without manual API documentation parsing.

### mm-ibkr-mcp (Execution Tooling)
The canonical Interactive Brokers MCP server enabling agent-driven trading:

* **23+ MCP tools** covering health monitoring, positions, orders, basket execution, and approvals
* **Safety model**: `control.json` toggles and optional Telegram approval flow
* **Persistence**: SQLite for audit logs, order history, trade intents, and position snapshots
* **Safe defaults**: `orders_enabled=false`, `dry_run=true` — all production actions require explicit enablement

Agents can query real-time positions, calculate position sizes, plan orders with transaction cost modeling, and execute with human-in-the-loop approval.

### AI System Architecture

The broader AI system that powers the agent infrastructure:

```
                    ┌───────────────────────────────────────┐
                    │           Local LLM (lain)            │
                    │     (self-hosted inference API)       │
                    └───────────────┬───────────────────────┘
                                    │
          ┌─────────────────────────┼─────────────────────────┐
          │                         │                         │
          ▼                         ▼                         ▼
┌─────────────────┐    ┌─────────────────────┐    ┌──────────────────┐
│   repo_search   │    │       mem0          │    │   MCP Servers    │
│  (Code Search)  │    │  (Agent Memory)     │    │  (Tool Access)   │
└────────┬────────┘    └──────────┬──────────┘    └────────┬─────────┘
         │                        │                        │
         ▼                        ▼                        ▼
┌─────────────────┐    ┌─────────────────────┐    ┌──────────────────┐
│  BAAI/bge-m3    │    │    BAAI/bge-m3      │    │  mm-mcp, ibkr,   │
│  (Embeddings)   │    │    (Embeddings)     │    │  repo_search,    │
└────────┬────────┘    └──────────┬──────────┘    │  mem0, etc.      │
         │                        │               └──────────────────┘
         └───────────┬────────────┘
                     │
                     ▼
         ┌─────────────────────────┐
         │    Qdrant Vector Store  │
         │  (repo_index_chunks_v2) │
         │     (mem0_memories)     │
         └─────────────────────────┘
```

**Components:**

* **lain**: Self-hosted local LLM inference via an OpenAI-compatible API (`http://127.0.0.1:8080/v1`). Powers all local model interactions without relying on external APIs.

* **mem0**: Agent memory system with semantic search. Agents can store experiences, retrieve relevant past context, update or delete memories. Uses Qdrant for vector storage with BAAI/bge-m3 embeddings (1024 dimensions).

* **repo_search**: Semantic code/document search over indexed repositories. Uses BAAI/bge-m3 for dense embeddings combined with BM25 sparse search for hybrid retrieval. Includes BAAI/bge-reranker-v2-m3 for improved result ranking. Indexed content lives in Qdrant collection `repo_index_chunks_v2`.

* **MCP Servers**: Model Context Protocol servers providing structured tool access:
  * `mm-mcp`: Financial analytics (data, pricing, volatility, portfolio)
  * `ibkr-execution`: Trading execution via IB Gateway
  * `repo_search_mcp`: Codebase semantic search
  * `mem0_mcp`: Memory operations
  * `traceforge`: API reverse-engineering

The entire system runs locally — no external API dependencies for core functionality. This provides privacy, cost control (no per-token fees), and low-latency inference critical for trading applications.
