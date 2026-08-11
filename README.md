# Crypto Futures: design prototypes

Design artefacts for the Ajaib Crypto Futures trade experience. Everything here is static HTML with no build step and no backend.

**Live site:** https://jose-ajaib.github.io/crypto-futures-prototype/

## Contents

| Path | What it is |
| --- | --- |
| `index.html` | Landing page linking the artefacts below |
| `tpsl-chart-lines/` | One pager on showing unlimited TP/SL order lines on the chart. Problem statement, the density based clustering decision, three label tiers, interactive prototype of the BTCIDR-PERP chart tab, interaction rules, pseudocode, TradingView Advanced Charts API constraints, edge cases, open questions |
| `ubah-leverage/` | Clickable prototype of the leverage adjustment bottom sheet, testing the conditional liquidation risk warning and the fixed sheet height |

## Enabling Pages

Settings &rarr; Pages &rarr; Deploy from a branch &rarr; `main` / `/ (root)`. The `.nojekyll` file at the root stops Jekyll from touching the output.

## Notes for reviewers

The grey control panels below each device frame are testing aids, not part of the design. They let you push a prototype into states that are otherwise hard to reach. Anything inside the phone frame is the actual proposal.

Prices and order data in every prototype are synthetic.
