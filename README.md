# Huntington Digital Assets – Enterprise Vision Prototype

> **INTERNAL / CONFIDENTIAL – Paxos.** Concept prototype prepared for Huntington Bank discussions. Not a Huntington product. Do not publish publicly.

An interactive, clickable prototype that "paints the picture" of a bank-wide digital asset experience for Huntington, from Phase 1 (buy/sell/hold, stablecoin payments) through the full vision (earn, cards, crypto-backed lending, tokenized assets and deposits).

It is a single self-contained HTML file with no build step, no dependencies and no network calls. It works offline.

## Run it

- **Locally:** open `index.html` in any modern browser (Chrome, Safari, Edge).
- **GitHub Pages:** in the repo, go to **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, and save. The site serves `index.html`.
  - **Visibility:** keep the repo **private/internal**. On GitHub Enterprise Cloud you can restrict a Pages site to org members (**Settings → Pages → Visibility: Private**). On other plans a Pages site is public even if the repo is private, so if that applies, share the repo and have people open the file locally instead.

## What's inside

| Tab | What it shows |
|---|---|
| Enterprise overview | Map of customer segments × product areas, colored by phase; Paxos platform stack; competitive comparison |
| Consumer | Phone app: Home, Invest (live-style charts, buy/sell in USD or coin units, tokenized treasuries & stocks), Earn (USDG rewards, staking), Pay (closed-loop → external wallets, USDG/USDC, receive), Card (USDG debit, crypto-backed credit), Borrow |
| Private Bank & Wealth | Advisor portfolio view, allocation proposal slider, held-away crypto deposit flow, staking, pledged lines, tokenized funds |
| Business Banking | Supplier payments 24/7, receivables auto-convert rule, employee cards, deposit tokens |
| Commercial & Treasury | USDG mint/redeem, payout batches, **Huntington Deposit Token** walkthrough (tokenize, pay three ways, program it) |
| Huntington Operations | Revenue by product line, execution quality (TCA), prefund float, compliance queue, product controls, architecture |

Use the **Roadmap view** toggle (top right) to switch between Phase 1, Phases 1–2 and the full vision. Later-phase features stay visible but locked.

### Demo tips

- Consumer → Invest → Bitcoin: switch chart periods and hover or drag across the chart.
- Sell BTC with 25%/50%/Max, then toggle "Enter in USD".
- Pay → send USDG to Jordan; Receive → switch to "From a wallet" (Phase 2).
- Card → switch to "Credit · crypto-backed" (Phase 3).
- Commercial → scroll to Huntington Deposit Token and try each payment route.
- The page keeps state in memory only, so refresh the browser to reset the demo.

## Data notes

- Crypto and gold prices reflect **Oct 7, 2026** market levels. Tokenized equity prices use the **Oct 6, 2026** close.
- Chart history is modeled: it is anchored to published month-end closes (BTC), with some anchors estimated (ETH, SOL, gold) and simulated paths in between. It is not tick data.
- All customer names, balances, rates, yields and revenue figures are **illustrative**.
- Phase 2/3 capabilities are roadmap concepts, subject to Huntington and Paxos product, legal, regulatory and risk approvals.

### Open items to confirm before external use

1. USDC support end-to-end via Paxos (the decks list USD, USDG and PYUSD).
2. Availability of bank-level execution quality (TCA) data from Paxos.
3. Wording for consumer "USDG rewards" given final rules on stablecoin yield.

## Updating prices before a demo

Everything lives in the `<script>` block of `index.html`, near the top:

- `TODAY`: the "as of" date/time.
- `PX`: crypto assets. Each has `wp`, a list of `[daysAgo, price]` anchors; the **last entry `[0, price]` is the current price** and the second-to-last is the prior close (used for the daily % change). Add a new `[0, …]` and shift older anchors as needed.
- `TOK`: tokenized assets, with a fixed `p` price for each.
- Update the footer text (search for "Oct 7, 2026") to match.

## Source materials

Built from the Paxos decks presented to Huntington (Track 1: Experience Demo, Track 5: Commercial, New BD & Co-Innovation), the 10/2/26 shortlist response, and public market and regulatory sources current as of Oct 7, 2026.
