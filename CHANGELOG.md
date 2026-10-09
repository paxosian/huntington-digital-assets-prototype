# Changelog

All notable changes to this demo. Versions follow `MAJOR.MINOR.PATCH`; each version is a git tag.

## [0.4.3] – 2026-10-09
- Removed the flag notes from the roadmap boxes and legend.

## [0.4.2] – 2026-10-09
- Roadmap simplified to a high-level phasing view: removed dependency arrows, the Dependencies table and the per-box Paxos capability tags. Kept phases, milestones, flags and the dashed "needs partner or approval" style.

## [0.4.1] – 2026-10-09
- Roadmap dependencies reviewed for accuracy. Removed arrows that weren't real dependencies, such as Buy/sell → Tokenized assets, Held-away crypto → Staking, Receivables → Cards, Supplier payments → Deposit tokens, and the ops and platform chains.
- Arrows now always point from the prerequisite to what it unlocks. Solid = required; dashed = planned before but not required (e.g. Debit card → Crypto-backed credit card reuses the card program and issuing partner).
- Lines are routed through the gaps between columns so they no longer pass behind other boxes.
- Paxos capabilities each box relies on are shown as tags instead of lines. Card partner (Rain or Reap) is now its own platform box.
- New Dependencies table under the roadmap explains every arrow. Hover an arrow to see the reason.

## [0.4.0] – 2026-10-09
- Phases removed from the demo screens. Every experience now shows the full set of capabilities, with no phase selector, phase tags or locked features.
- Roadmap tab rebuilt as a swimlane roadmap: one lane per segment plus the Paxos platform, three phase columns, capability boxes, dependency arrows, milestones, and flags for partners, approvals and open questions.
- Clicking a roadmap box opens that part of the demo.

## [0.3.0] – 2026-10-09
- Simpler landing page: one card per experience with "Try" steps and an Open button.
- Roadmap moved to its own tab (phases, features by phase, platform stack).
- Removed sales framing: banner stats, taglines, competitor comparison and "why it matters" panels.
- Plain wording throughout. All descriptive text moved into one `COPY` block for easy editing.
- Each tab now opens with a short intro and things to try; consumer side panel lists what's on each screen.
- Phase selector relabeled "Show features through: Phase 1 / 2 / 3".
- Version number shown in the footer.

## [0.2.0] – 2026-10-07
- Current market prices (as of Oct 7, 2026) and modeled 12-month chart history with 1D–1Y periods and hover.
- Sell in coin units with USD equivalent; 25/50/75/Max; unit toggle.
- Customer-facing confirmations simplified; execution quality (TCA) report added to Operations.
- Clickable tokenized treasuries, stocks and ETFs; USDC alongside USDG.
- Closed-loop transfers in Phase 1; external wallets and crypto send/receive in Phase 2.
- Earn tab with staking; crypto-backed credit card; held-away crypto deposit flow; tokenized deposit walkthrough.
- First version under version control. (0.1.0, the first draft, was not preserved.)
