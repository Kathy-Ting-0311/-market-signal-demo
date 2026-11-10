# Tavreniq

A dependency-free prediction market and stock forecast demo. All market data is synthetic and clearly labeled in the app. No live prices, real orders, or performance claims.

## Run

Requires Node 22 or newer.

```sh
npm start
```

Open http://127.0.0.1:5173. The deployable static app is in `dist/`.

## Features

- Four selectable stock histories, four chart periods, hover inspection, and a five-session forecast with uncertainty bands.
- MAE, MAPE and directional accuracy computed from 30 rolling one-step forecasts.
- Event markets with category filters and search.
- Yes/No paper orders with whole shares, integer-cent accounting, validation and local persistence.
- A paper portfolio, account reset, watchlist and CSV data export.
- Responsive desktop, tablet and phone layouts; keyboard focus, reduced motion and native accessible trade dialog.

## Validation

`npm run check` checks JavaScript syntax and tests the forecast calculations and order accounting.

`tests/browser.html` is a same-origin interaction harness. Serve the project root to run it; it exercises stock changes, chart ranges, forecast toggle, watchlist, search/filter, input validation, order creation and reload persistence. It restores existing stored account data afterward.

The data seed and model are in `dist/model.js`. `PLAN.md` explains implementation decisions and the adaptation of the supplied design skill to an application dashboard.

## Limitations

Forecast bands use an approximate normal-residual assumption; coverage has not been validated. Prices, volumes and probabilities are fixtures. Weekday date generation does not implement exchange holidays. Paper execution has no fees, order book or settlement. Stored data is per browser and can be cleared through the portfolio reset.
