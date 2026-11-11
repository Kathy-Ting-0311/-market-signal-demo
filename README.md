# Tavreniq

**Incomplete demo project.** A dependency-free prediction-market and stock-forecast dashboard. Every price, probability and volume is synthetic; nothing here is live, real money or investment advice.

- Live preview: https://market-signal-demo.jiantingh2.chatgpt.site/ (may ask you to sign in)
- Source: https://github.com/Kathy-Ting-0311/-market-signal-demo

## Run locally

Requires Node.js 22 or newer (`node --version` to check). There is nothing to install.

```sh
git clone https://github.com/Kathy-Ting-0311/-market-signal-demo.git market-signal-demo
cd market-signal-demo
npm start
```

Then open **local network (e.g., http:// )** in your browser. Press `Ctrl+C` in the terminal to stop it.

## What is in it

- Four stock histories with chart periods, hover inspection and a five-session forecast with uncertainty bands.
- MAE, MAPE and directional accuracy from 30 rolling one-step forecasts.
- Event markets with filters and search, Yes/No paper orders with local persistence.
- Paper portfolio, watchlist, account reset and CSV export.
- Keyboard focus, reduced motion and responsive layouts.

## Checks

```sh
npm run check
```

Runs JavaScript syntax checks and tests the forecast calculations and order accounting. `tests/browser.html` is a manual interaction harness; serve the project root to use it.

## Limitations

Forecast bands use an approximate normal-residual assumption and their coverage is unvalidated. Prices, volumes and probabilities are fixtures; weekday dates ignore exchange holidays. Paper execution has no fees, order book or settlement, and stored data is per browser. The data seed and model live in `dist/model.js`; `PLAN.md` explains implementation decisions.
