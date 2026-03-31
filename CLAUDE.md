# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## How to Run

This is a zero-build, single-file web app. Open `index.html` directly in a browser — no server, no npm, no compilation needed.

## Architecture

The entire application lives in `index.html` as a single self-contained file with inline CSS and JavaScript. There are no external local assets, build tools, or dependencies to install.

**External CDN dependencies (loaded at runtime):**
- Bootstrap 5.3.2 (CSS + JS)
- Bootstrap Icons 1.11.1
- Chart.js 4.4.0
- CoinGecko public API (`https://api.coingecko.com/api/v3/`)

**Key JavaScript globals in `index.html`:**
- `cryptos` — array defining the 6 tracked coins (BTC, ETH, SOL, ADA, BNB, XRP) with their CoinGecko IDs, symbols, and display colors
- `currentCurrency` — `'brl'` or `'usd'`, persisted via `localStorage`
- `priceChart` — Chart.js instance for the trend graph
- `currentCrypto` / `currentPeriod` — state for the chart section

**API calls:**
- Price cards: `GET /simple/price` — fetches all 6 coins at once in the selected currency
- Chart: `GET /coins/{id}/market_chart` — fetches historical OHLC data for the selected coin + period

**Rate limiting strategy:** The free CoinGecko API allows ~10–50 req/min. The app uses manual refresh only (no auto-polling), a 45-second client-side cache, and up to 3 retries with progressive delays (2s, 4s, 6s) on 429 or network errors.
