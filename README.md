# Mikael Hillman Pepin — Quant & Data Engineer

Quant dev focused on research-grade Python tooling for market data ingestion, portfolio analytics, and systematic strategy prototyping, with a bias toward reproducible backtests, clean packaging, and lightweight dashboards.

---

## 📊 Data & Modeling Libraries

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **Finance-Utils** | pandas · requests · yfinance · SQLite | ![Active](https://img.shields.io/badge/-active-brightgreen) | Modular Yahoo Finance and index/CIK client with ticker scraping, fundamentals/prices retrieval across intervals, and database helpers for durable local datasets |
| **MSN-Scraper** | pandas · requests · bs4 | ![Active](https://img.shields.io/badge/-active-brightgreen) | Unofficial MSN Finance API wrapper delivering quotes, ratios, financials, earnings, estimates, and ownership with multi-ticker support and structured parsers |
| **Feature-Fetcher** | DuckDB · asyncio · TOML · pytest | ![In Progress](https://img.shields.io/badge/-in%20progress-yellow) | Daily append-only feature store pipeline for equities on Raspberry Pi-scale hardware, with CLI, registry-driven feature computation, and idempotent upserts |
| **step_criterion** | statsmodels · patsy | ![Active](https://img.shields.io/badge/-active-brightgreen) | Educational stepwise regression toolkit exposing AIC/BIC/adj-R²/p-value selection for OLS/GLM with model averaging and detailed step tables |
| **mgarchx** | NumPy · pandas | ![Experimental](https://img.shields.io/badge/-experimental-orange) | Early-stage multivariate GARCH modeling package with example notebooks and diagnostics |

---

## 💼 Portfolio & Trading Systems

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **Portfolio** | pandas · pyarrow · Streamlit · Pydantic | ![Active](https://img.shields.io/badge/-active-brightgreen) | Multi-broker portfolio tracker with append-only ledgers, EOD valuation via Yahoo, risk analytics (EWMA, shrinkage cov), reconciliation, and Streamlit dashboard/CLI |
| **quant-blend-optimizer** | pandas · scikit-learn · Streamlit | ![Active](https://img.shields.io/badge/-active-brightgreen) | Portfolio optimizer supporting EW/MVP/MDP/MSR, covariance shrinkage variants, CLI and Streamlit UI, and strategy blending/backtests with Yahoo/FRED data |
| **quant-PE-rebalance** | scikit-learn · pandas · tqdm | ![Active](https://img.shields.io/badge/-active-brightgreen) | Modular ML strategy framework with feature engineering, walk-forward cross-validation, portfolio construction, metrics, and visualization for long-only/long-short equities |
| **intraday_reversion** | pandas · Optuna · matplotlib | ![Active](https://img.shields.io/badge/-active-brightgreen) | Intraday mean reversion toolkit with session-specific price processing, regime detection (beta, rank corr, decile spread, Theil-Sen), Optuna hyperparam search, and blended backtests |
| **TLH+OpOl** | pydantic · pyproject | ![In Progress](https://img.shields.io/badge/-in%20progress-yellow) | Tax-loss harvesting simulator with specific-ID lot accounting, mock price generator, Canadian tax hooks, and scaffolding for covered-call/cash-secured-put overlays driven by YAML config |
| **Brandt_Portfolio** | finance_utils | ![In Progress](https://img.shields.io/badge/-in%20progress-yellow) | Data ingestor populating a SQLite DB of prices and selected fundamentals for a diversified ticker set to support Brandt-style portfolio experiments |
| **Algo-Trading_Statistical-Arbitrage** | yfinance · pandas · sqlite | ![Experimental](https://img.shields.io/badge/-experimental-orange) | Scripted pipeline to scrape current S&P 500 membership and maintain an adjusted-close SQLite dataset for stat-arb research |
| **Short** | Python notebooks | ![Experimental](https://img.shields.io/badge/-experimental-orange) | Notebooks analyzing short interest, dilution tracking, and backtests on related signals |
| **Sentiment-Factors** | Reddit API utilities | ![Experimental](https://img.shields.io/badge/-experimental-orange) | Configurable Reddit crawler setup for sentiment-based factor construction and rate-limit inspection |
| **Various_Algo_tests** | notebooks · misc scripts | ![Archived](https://img.shields.io/badge/-archived-lightgrey) | Sandbox of exploratory notebooks (covariance weighting, MSN API trials, IBKR client experiments) and legacy algo tests |
| **quadrature-options-pricer** | NumPy | ![Experimental](https://img.shields.io/badge/-experimental-orange) | Research code for Bermudan/American/European option pricing via quadrature-based backward induction with benchmarking notebooks and scripts |

---

## 📈 Options & Volatility Research

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **mgarchx** | NumPy · pandas | ![Experimental](https://img.shields.io/badge/-experimental-orange) | Prototype multivariate GARCH tooling for risk/vol modeling |
| **TLH+OpOl** | pydantic · pyproject | ![In Progress](https://img.shields.io/badge/-in%20progress-yellow) | Includes options overlay scaffolding for covered calls and CSPs |

---

## 🏠 Real Estate & Personal Finance

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **centris_analyser** | requests · bs4 · pandas · rapidfuzz | ![Active](https://img.shields.io/badge/-active-brightgreen) | Dual repo: high-speed Centris.ca scraper (overview + detailed parallel scraping, filtering, export) and educational analysis toolkit for Quebec plex deals with modeling notebooks and config-driven paths |
| **condo-vs-house-cost-sim** | dataclasses · yaml · mypy · pytest | ![Active](https://img.shields.io/badge/-active-brightgreen) | Library/CLI to compare condo vs house ownership PV using deterministic and Monte Carlo simulations with economic shocks, event modeling, and reporting/notebook examples |

---

## 🎓 Academic & Coursework

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **HEC_Team** | Python notebooks | ![Archived](https://img.shields.io/badge/-archived-lightgrey) | Graduate quantitative investing assignments with extensive feature engineering documentation, sector-neutral ML models, and walk-forward validation for S&P 500 strategies |
| **Eff_frontier_max_sharpe_GP_TP1** | cvxpy notebooks | ![Archived](https://img.shields.io/badge/-archived-lightgrey) | Portfolio management class project optimizing efficient frontier/Sharpe via conic solvers with Anaconda environment specs |

---

## 🔧 Data & Compliance Utilities

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **Institutional** | yfinance · requests · bs4 · openpyxl | ![Experimental](https://img.shields.io/badge/-experimental-orange) | SEC data helpers to fetch insider/holding data, scrape CIKs, and enrich institutional datasets, plus TSX ticker retrieval routines |
| **Other/13F_Portfolio** | BeautifulSoup | ![Archived](https://img.shields.io/badge/-archived-lightgrey) | Form 13F XML parser and portfolio analyzer classes for recent filing changes |
| **Share_liquidation** | Python notebook | ![Incomplete](https://img.shields.io/badge/-incomplete-red) | Prototype notebook to retrieve and study share liquidation filings |

---

## 🛠 Personal & Misc Tools

| Project | Stack | Status | Description |
|---------|-------|--------|-------------|
| **Spotify** | spotipy · pandas | ![Complete](https://img.shields.io/badge/-complete-blue) | Script to pull and export liked songs via Spotify API to Excel |
| **ticker_wallpaper** | HTML · CSS · JS | ![Complete](https://img.shields.io/badge/-complete-blue) | Browser-based animated ticker "wallpaper" with configurable board JSON and media previews |
