# Long-Term Stocks, Bonds & Cash

Standalone project for the long-run comparison of U.S. stocks, bonds, and cash since 1957.

## Files

- `longterm_interactive.html` — interactive presentation
- `longterm_interactive.png` — rendered interactive presentation preview
- `longterm_multiasset.html` — static presentation
- `longterm_multiasset.png` — rendered static presentation preview
- `longterm_series.json` — asset return series
- `longterm_events.json` — historical market events

Open either HTML file in a browser to view the presentation.

## Project access

- Local project: `/Users/pippono/dev/longterm-stock-bond-cash`
- GitHub repository: <https://github.com/pippono9g-cloud/longterm-stock-bond-cash>
- Live GitHub Pages app: <https://pippono9g-cloud.github.io/longterm-stock-bond-cash/>

This directory is a sibling of `fund-automation` inside the `/Users/pippono/dev` Obsidian vault. Claude sessions scoped only to `fund-automation` should open this directory as a separate project, or use `/Users/pippono/dev` as the workspace root.

## Current interactive behavior

- All event categories are selected when the chart first opens.
- Event search covers the full history and moves the chart to the selected result.
- Event cards show S&P 500 price performance 1, 3, 6, and 12 months after an event, using the prior month-end as the baseline.
- A 12-month market-response timeline shows the lowest point, months to the low, and whether/when the index returned to its pre-event level.
- These metrics describe market movement after an event; they do not establish that the event caused the movement.

## Event data review (2026-09-14)

Reviewed `longterm_events.json` (189 events, 1957–2026) and the card-rendering logic in
`longterm_interactive.html` for correctness. Findings, for Claude/Codex to act on together:

**Dates/labels checked look accurate.** Spot-checked ~15 well-documented events (Black Monday
Oct 19 1987, GFC peak Oct 9 2007, market bottom Mar 9 2009, COVID crash −34%/33 days, Aug 2011
S&P downgrade −17%, Q4 2018 sell-off −19.8%, Oct 2022 bear bottom −25%) against known history —
all dates and magnitudes match.

**Computation logic is sound.** `eventPerformance()` (line ~376) anchors to prior month-end,
walks forward up to 12 months for low/recovery, matches the documented methodology
disclaimer shown in the card's "เกี่ยวกับข้อมูล" panel. `idxAt()` nearest-index lookup is
correct. No bug found in the 1M/3M/6M/12M or market-response calculations.

**Citation status after the priority upgrade: 22 of 189 events have per-event sources.** The
remaining 167 events still have an empty `sources` array. Citations distinguish their scope:
official event sources support dates and context, while market-return figures shown by the card
continue to be calculated from the chart's monthly S&P 500 price series.

**Priority upgrade completed:** all 19 severity-1 (highest-severity) events now have at least one
per-event source. The 17 additions cover Kennedy Slide, the 1969–70 bear-market low, OPEC embargo,
Volcker, the 1980 inflation peak, the 1982 bull-market turn, Iraq/Kuwait, the 1994 bond rout,
dot-com peak, 9/11, the March 2009 market bottom, the August 2011 downgrade, Q4 2018 sell-off,
COVID crash, the June 2022 inflation peak, SVB/Signature, and the April 2025 tariffs.

**Next recommendation:** continue the same citation pattern for the remaining 167 lower-severity
events in manageable batches. Prefer primary agency or index-provider sources and state each
source's scope precisely rather than implying that an event caused the subsequent market return.
