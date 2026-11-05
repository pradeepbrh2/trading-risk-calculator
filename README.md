# Trading Risk Calculator

A browser-based position sizing and trading risk workspace for planning Indian-market trades. The app runs on GitHub Pages and stores working data locally in the browser; it does not connect to a broker or place orders.

## Workspaces

- **Position Calculator** — [Open calculator](https://pradeepbrh2.github.io/trading-risk-calculator/)
  - Account capital, safety reserve, risk budget and assumed leverage
  - Multiple long/short instrument setups
  - Quantity constrained by both risk and buying power
  - Stop-loss risk, estimated costs, break-even exit price and 1:2 / 1:3 targets
- **Risk Dashboard** — [Open dashboard](https://pradeepbrh2.github.io/trading-risk-calculator/risk-dashboard.html)
  - Daily realised net P&L and configurable loss / trade-count guardrails
  - Combined planned position value, margin and risk across active setups
- **Trade Journal** — [Open journal](https://pradeepbrh2.github.io/trading-risk-calculator/trade-journal.html)
  - Manual completed-trade records and delete action
  - Gross P&L, estimated costs and net P&L
  - Weekly/monthly net P&L, win rate, profit factor, average win/loss and closed-trade drawdown
  - CSV and Excel exports, plus full JSON backup and restore

## Cost estimator

Configure brokerage per executed order, STT on sell-side turnover, exchange transaction charges on total turnover, stamp duty on buy-side turnover, GST on brokerage/exchange/SEBI fees, SEBI fees per crore, and estimated slippage per unit per side. Defaults are zero intentionally. Enter rates from your broker's current tariff and instrument/segment. The result is an estimate, not an official contract note; actual taxes, fees, rounding, order types and execution can differ.

Estimated costs are saved with each newly recorded journal trade so changing the tariff later does not rewrite previously recorded results. Legacy trades without a saved cost estimate use the currently configured profile.

## Mini game

- **Candle Catch** — [Play the 30-second mini game](https://pradeepbrh2.github.io/trading-risk-calculator/game.html)
- Tap green candles to score, avoid red candles, and beat your personal best.
- Best score is stored locally in the browser. The game uses no market feed and has no effect on calculator data.

## Data and privacy

- Calculator settings, charge profile, risk controls and journal are stored in this browser's local storage.
- Data does not automatically sync between browsers or devices.
- Use **Full backup (JSON)** in the Trade Journal to export all app data. Use **Restore backup** on the same page to import a previously exported backup. Restore replaces the current browser data.
- Clearing browser site data can erase locally stored records. Keep a backup.

## Calculation notes

For each setup, the app calculates risk-based quantity and buying-power-based quantity, rounds both down to whole units, and uses the smaller quantity. Planned risk is based on the entered stop-loss price and does not guarantee the realised loss. Gaps, liquidity, slippage, rejected orders, broker margin changes and other execution conditions can produce a different result.

Daily guardrails are advisory only. They do not block orders or monitor a live broker account.

## Development

The app is a static HTML/CSS/JavaScript project hosted with GitHub Pages. No server-side account or broker integration is required.
