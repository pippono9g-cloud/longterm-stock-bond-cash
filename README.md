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
