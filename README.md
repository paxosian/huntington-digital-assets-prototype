# Huntington Digital Assets Demo

> **Internal / confidential (Paxos).** A demo built for Huntington Bank discussions. It is not a Huntington product. Don't publish it publicly.

A clickable demo of how digital assets could work across Huntington: consumer, private bank, business banking, commercial treasury and the bank's own operations. It's one HTML file with no dependencies and works offline.

Current version: see the badge in the page footer, or `VERSION` in `index.html`.

## Open it

- **Locally:** open `index.html` in Chrome, Safari or Edge.
- **GitHub Pages:** go to **Settings → Pages → Deploy from a branch**, then choose `main` and `/ (root)`.
  - Keep the repo private or internal.
  - On GitHub Enterprise Cloud you can limit the site to org members (**Pages → Visibility: Private**).
  - On other plans a Pages site is public even when the repo is private. In that case, share the repo and have people open the file locally.

## What's in it

| Tab | What you can do |
|---|---|
| Overview | Pick an experience. Each card lists a few things to try. |
| Consumer | Phone app: Home, Invest, Earn, Pay, Card, Borrow. The side panel explains each screen. |
| Private Bank & Wealth | Advisor portfolio view, allocation slider, bringing in crypto held elsewhere, staking, pledged credit line |
| Business Banking | Weekend supplier payments, auto-convert receivables, employee cards |
| Commercial & Treasury | USDG mint/redeem, payout batch, deposit tokens |
| Bank Operations | Revenue by product, execution quality (TCA), prefunding, compliance alerts, product controls |
| Roadmap | High-level phasing by segment, with milestones. Click a box to jump into the demo. |

The demo screens show the full set of capabilities. Phasing appears only on the Roadmap tab. Refresh the page to reset.

## Editing the wording

All descriptive text lives in one block near the top of `index.html`: search for `const COPY=`. That block holds:

- the overview cards
- the intro line on each tab
- the phase descriptions used on the Roadmap
- the consumer side panel
- the footer

You can edit text inside the quotes without touching any code. Two rules:

- If you use an apostrophe inside single quotes, write it as `\'` (e.g. `client\'s`).
- Open the page afterwards to check it still loads.

Button labels and field names inside the screens live further down in the view functions.

## Editing the roadmap

Search `index.html` for `RM_ITEMS` to find the roadmap data:

- **`RM_ITEMS`:** the boxes. Each one has a lane, a phase, a title, a note; `dashed:1` marks a box that needs a partner or approval.
- **`RM_MILESTONES`:** the diamonds.

## Version control

Each release is a git commit with a tag (`v0.2.0`, `v0.3.0`, …). `CHANGELOG.md` says what changed in each one.

**Making a new version**
1. Edit `index.html`.
2. Bump `VERSION` (near the top of the script).
3. Add an entry to `CHANGELOG.md`.
4. Commit and tag:
   ```bash
   git add -A
   git commit -m "v0.5.0: short description"
   git tag -a v0.5.0 -m "v0.5.0"
   git push origin main --tags
   ```

**Looking at or rolling back to an old version**
```bash
git tag                                # list versions
git log --oneline --decorate           # history
git checkout v0.2.0 -- index.html      # restore an old version's file into your working copy
git commit -m "Roll back to v0.2.0"    # ...and keep it (history is preserved)
git revert <commit>                    # undo one specific change
```

You can also browse any version on GitHub through the **Tags** / **Releases** page. Each tag can be published as a Release with `index.html` attached.

## Data notes

- Crypto and gold prices are as of Oct 7, 2026. Stock prices are the Oct 6 close.
- Chart history is modeled from month-end closes; it isn't tick data.
- Names, balances, rates and revenue are made up.
- Phase 2 and 3 features are concepts and would need Huntington and Paxos product, legal, regulatory and risk approval.

**Refreshing prices before a demo:** in `index.html`, update the following, and keep them in step with the `COPY.footer` text:

- `TODAY`
- the last `[0, price]` entry in each `PX` asset's `wp` list (the entry before it is the prior close)
- `TOK` prices

## Open items

1. Confirm Paxos supports USDC end to end.
2. Confirm execution quality (TCA) data is available to the bank.
3. Agree the wording for consumer USDG rewards under stablecoin yield rules.
