# Ubah Leverage — Interactive Prototype

Clickable prototype of the leverage-adjustment bottom sheet for the Futures trade page.

**Live:** enable GitHub Pages on this repo (Settings → Pages → Deploy from branch → `main` / `/root`)

**Figma source:** [Futures Trade Page, node 20893-38209](https://www.figma.com/design/qcGcRvqMdDtl44HcNUA7eV/Futures-Trade-Page?node-id=20893-38209)

## Behaviour being tested

| Requirement | Implementation |
| --- | --- |
| Slider range | 1x–25x, continuous 1x steps. Tick dots at 1/5/10/15/20/25 fill as the thumb passes them. |
| Conditional warning | Liquidation-risk warning appears only when the selected value is **greater than** the current leverage. Hidden otherwise. |
| Fixed sheet height | Sheet is locked at 552px. The warning occupies a reserved 38px slot using `visibility: hidden`, not `display: none`, so the panel and CTA never shift. |

## Prototype controls

The panel below the device frame is a testing aid, not part of the design. It lets a reviewer change the **current leverage** and the **position side** (long/short) to exercise the warning logic in both directions.

## Open questions for the team

1. Sliding *down* from 10x to 5x shows no warning, per the requirement as written. A user who opens the sheet at 25x and stays at 25x therefore never sees a risk warning. Worth confirming with risk whether the trigger should be an absolute threshold instead of a relative one.
2. The margin and liquidation figures in the Figma mockup (`1,51 → 1,31` and `0,2014 → 0,2423` at 12x) are not mathematically consistent with a fixed position size. This prototype uses a self-consistent model (`margin = notional / leverage`) so values behave believably across the full 1–25x range. If the mockup figures came from a real API response, the formula needs review before handoff.

## Notes for engineering

Single self-contained HTML file, no build step and no dependencies. Not production code — it exists to validate interaction behaviour and the fixed-height constraint before the real spec is written.
