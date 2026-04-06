# Mikael Hillman Pepin — Quant & AI Systems Engineer

Building **self-evolving agent systems** and quantitative infrastructure that go from data ingestion through model execution to trade automation—powered by local AI infrastructure and a complete MCP ecosystem.

---

## AI & Agent Infrastructure

### Local RAG System
| Component | Stack | Description |
|-----------|-------|-------------|
| **repo_search** | Qdrant · BAAI/bge-m3 · hybrid | Semantic code/document search with dense embeddings + BM25 hybrid and reranking |
| **mem0** | Qdrant · BAAI/bge-m3 | Agent memory system with semantic search for persistent context |

### MCP Ecosystem
| Server | Stack | Description |
|--------|-------|-------------|
| **mm-mcp** | FastMCP · mm-infra | Financial analytics tools (data, pricing, volatility, portfolio optimization) |
| **repo_search_mcp** | MCP SDK | Semantic search over indexed codebases |
| **mem0_mcp** | MCP SDK | Memory operations (add, search, update, delete) |
| **traceforge** | TypeScript · Playwright · MCP | Reverse-engineer website APIs from browser traffic |

### Agent Systems
| Project | Stack | Description |
|---------|-------|-------------|
| **crime_investigator_system** | OpenCode · markdown artifacts | OpenCode-based investigation scaffold with specialist subagents (evidence-intake, timeline-analyst, hypothesis-challenger) |

---

## Homelab & Infrastructure

Isolated trading network with separate VLANs (Vault, DMZ, Lab), Tailscale for end-to-end encrypted remote access, and a dedicated trade execution node physically separated from the development environment.

---

## Quantitative Infrastructure (mm-infra)

Monorepo with 8 namespace packages under `mm.*` for production-grade quantitative finance.

### Data & Features
| Package | Import | Status | Description |
|---------|--------|--------|-------------|
| **mm-data** | `mm.data` | ![Active](https://img.shields.io/badge/-active-brightgreen) | Multi-source market data: Yahoo, MSN, ETFdb, FRED, WRDS |
| **Feature-Fetcher** | CLI | ![Active](https://img.shields.io/badge/-active-brightgreen) | Daily feature pipeline: 5K equities, 300+ features, ArcticDB storage |

### Pricing & Volatility
| Package | Import | Status | Description |
|---------|--------|--------|-------------|
| **mm-options** | `mm.quantlib.options` | ![Active](https://img.shields.io/badge/-active-brightgreen) | Black-Scholes, Bjerksund-Stensland, eSSVI calibration, FFT exotics, full Greeks |
| **mm-volatility** | `mm.quantlib.volatility` | ![Active](https://img.shields.io/badge/-active-brightgreen) | GARCH, GJR-GARCH, DCC, HAR models, jump-robust estimators |

### Portfolio & Selection
| Package | Import | Status | Description |
|---------|--------|--------|-------------|
| **mm-portfolio** | `mm.quantlib.portfolio` | ![Active](https://img.shields.io/badge/-active-brightgreen) | HRP, MVO, Black-Litterman, CVaR, ERC, covariance shrinkage |
| **mm-selection** | `mm.quantlib.selection` | ![Active](https://img.shields.io/badge/-active-brightgreen) | Stepwise regression with AIC/BIC/adj-R², model averaging |
| **mm-core** | `mm.quantlib.core` | ![Active](https://img.shields.io/badge/-active-brightgreen) | Zero curve bootstrapping, optimization engines, numerical primitives |

### Strategies
| Package | Import | Status | Description |
|---------|--------|--------|-------------|
| **mm-strategies** | `mm.strategies` | ![Active](https://img.shields.io/badge/-active-brightgreen) | PE rebalance, intraday mean reversion, signal trader, VRP harvesting |

---

## Trading & Execution

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **mm-ibkr-mcp** | MCP · ib-insync · Pydantic | ![Active](https://img.shields.io/badge/-active-brightgreen) | Agent-facing IB execution MCP (23+ tools for health, positions, orders, basket execution) |
| **mm-trading** | Pydantic · ZMQ · FastAPI | ![Active](https://img.shields.io/badge/-active-brightgreen) | Signal-to-order pipeline: position calculator, order planner, risk checker, executor |
| **mm-portfolio-tracker** | Pydantic · Streamlit · MCP | ![Active](https://img.shields.io/badge/-active-brightgreen) | Append-only ledger, EOD valuation, EWMA volatility, Ledoit-Wolf covariance |
| **mm-ibkr-gateway** | Docker Compose | ![Active](https://img.shields.io/badge/-active-brightgreen) | IB Gateway container deployment (live/paper) |

---

## Data Acquisition & Research

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **traceforge** | TypeScript · Playwright | ![Experimental](https://img.shields.io/badge/-experimental-orange) | API reverse-engineering from browser traffic, OpenAPI/TypeScript generation |

---

## Real Estate & Personal Finance

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **centris_analyser** | requests · bs4 · pandas | ![Active](https://img.shields.io/badge/-active-brightgreen) | Centris.ca scraper + Quebec plex investment analysis |
| **condo-vs-house-cost-sim** | dataclasses · yaml · mypy | ![Active](https://img.shields.io/badge/-active-brightgreen) | PV comparison with deterministic and Monte Carlo simulations |
