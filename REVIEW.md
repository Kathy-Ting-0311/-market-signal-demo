GATE: OPEN 17 (rounds used up)

# Tavreniq demo review

The user requested a working prediction-market fintech dashboard with clear stock trends and prices. This is an application workspace. The supplied design skill was designed primarily for company and marketing pages; its screen-height, call-to-action and page-shell checks remain open where they conflict with the requested application. This report does not claim a complete design-gate pass.

## Result

- Four selectable synthetic stock histories, four periods and a five-session forecast with uncertainty bands.
- MAE, MAPE and directional accuracy computed from 30 preceding-only one-step predictions.
- Searchable event contracts, Yes/No tickets, cent-based paper orders, a browser-local portfolio and CSV export.
- Opposing Yes/No positions on the same event are mutually exclusive when calculating maximum payout.
- Native accessible dialog, keyboard focus, responsive sidebar and a full-width phone menu.

## Design decisions

Kind: software / fintech. Deal: lunar-grey-bronze (charcoal grounds separate marks, bronze identifies controls), Schibsted Grotesk + JetBrains Mono, sharp radii. Green/red denote financial direction and Yes/No state. The collage marketing hero and pinned-chapters moment were dealt but replaced with the actual dashboard. No shader ground, scene, photo, stock photograph, customer logo or placeholder asset. The kit's hover/press layer and one load entrance remain. Equal content padding is measured inside the sidebar's remaining workspace. The desktop sidebar intentionally occupies the left edge.

Voice: facts only; financial nouns, explicit units, short labels; no investment performance claims or customer proof.

## Verification

Final desktop screenshot: shots/final-desktop.png. A fresh headless Chrome profile resolved a one-off startup failure during the optional final capture.

- Six Node model/accounting tests passed. These cover seeded history, independent backtest arithmetic, no future input, widening forecast intervals, integer-cent order costs, invalid inputs, insufficient funds, and mutually exclusive event payout.
- Eleven actual browser interaction checks passed: chart/metrics, asset switching, period switching, forecast toggle, watchlist, navigation/filter, search empty state, invalid order, whole-share purchase, reload persistence and document overflow. Evidence: shots/interactions-final.png.
- Desktop and tablet layouts were visually inspected at 1440, 1024, 820, 768; phone at 390. Final gate covers 1440 and 390 and walks 320.
- The full consistency run checked assets, motion, reduced motion, focus, touch targets, collisions and links. Genuine focus, link, navigation and contrast findings were corrected. The final gate below gives exact remaining findings.
- Performance: 0 FAIL, 3 WARN. Approximately 148 KiB transferred, 48 KiB parsed JavaScript, two font families/files, no broken requests, no WebGL contexts. Desktop layout shift 0.055; phone 0.000. The CPU was busy (66% before), so measured first paint (140ms desktop / 240ms phone) is a local lab result, not a field guarantee. The hidden phone sidebar's sub-1KiB logo was flagged as a non-lazy below-fold image. Retained because it is the navigation brand.
- Copy lint: 0 FAIL; one retained stat-strip WARN is a false classification of the chart-period controls (1M, 3M) and market count. These are functional UI labels, not marketing proof.
- The standalone layout checker ran at all five widths and reported marketing hero-fold constraints. Its first attempt failed on a missing .wrap; an explicit dashboard content wrapper was added and its rerun completed.

## Data and limits

All values are simulation fixtures, visibly disclosed. Closing-price endpoints: NVDA $187.42, AAPL $232.84, MSFT $514.72, TSLA $321.56; 90 seeded weekday sessions ending 6 Nov 2026. Next five weekday sessions run 9–13 Nov 2026. No exchange calendar or holiday feed is integrated.

Synthetic event quotes: NVDA above $200 at 67¢ Yes / 33¢ No; AAPL above $240 at 42¢ / 58¢; December Fed cut at 74¢ / 26¢; MSFT above $530 at 61¢ / 39¢. Stock events use 13 Nov 2026; Fed uses 9 Dec 2026. Volumes are $128,450, $84,620, $312,800 and $68,400 respectively. The account begins with $10,000 simulated funds. None are actual market prices, exchange probabilities, company metrics, or claims of validated predictive accuracy.

Model: next = last + 0.55 × (last − sixth preceding close) / 5. Future medians extend that same step. Range = median ± 1.645 × backtest RMSE × square root of horizon, clamped above zero. The nominal 90% band assumes independent normal residuals; coverage is not validated. Event prices are independent fixtures, not the forecast model's confidence.

No external form service or .example email stand-in is needed: paper orders execute only in this browser. There is no real order routing, liquidity matching, fee calculation or settlement. Browser storage may be cleared; unavailable storage is disclosed and falls back to this visit. A live-data version needs a licensed data source and credentials supplied by the user.

## Name, assets and domain

Tavreniq is a coined demo name. Searches for \"Tavreniq\" fintech and \"tavreniq.com\" found an unrelated watch storefront, no finance business or famous person with that exact name in returned results. Market Signal was rejected because existing financial services use that name; Veydris was also rejected. Full queries and decisions are in names.json. This is not a trademark-clearance claim or a domain-availability claim.

Canonical URL: https://market-signal-demo.jiantingh2.chatgpt.site/ . This slug describes the demo; the app is branded Tavreniq. Social share image is a dashboard screenshot in dist/share.jpg. No client photographs, art, trailers, renders, company facts, testimonials or user assets were supplied or needed; there are no empty client slots. The favicon is an original abstract price-chart mark. Company names in the market data identify the synthetic instruments.

## Documented waivers

- **no-visual** — section#overview "Market overview."

  The requested deliverable is the live dashboard itself. Its stock chart, forecast metrics, trading quotes and controls are real product UI; adding decorative marketing media would reduce space for analysis.

- **copy-actions** — div#overview-markets > article.market-card:nth-of-type(1) > div.market-buttons > button:nth-of-type(2) "No 33¢ ↗"

  These are per-market Yes and No trading controls in a working application, not competing marketing calls to action. The user asked for a prediction-market dashboard.

- **moment-none** — (the page)

  The user requested an analytical dashboard. Keep its chart still until input; a full-screen scroll storytelling scene would displace the requested market workspace.

- **hero-screen** — section#overview "Your market workspaceMarket overview.Fol"

  This section is an application workspace using the kit hero class for its single load entrance. Its working panels scroll naturally; it is not a one-screen marketing hero.

- **heading-scale** — strong#current-price "$187.42"

  The user explicitly prioritized clear stock trends and prices. Prominent price figures intentionally exceed the mobile page title in this financial application.

## Every remaining gate failure

1. **button-styles** — (one screen)

   3 button styles on one screen: soft, fill #28241f, outline #3a3129 ("Overview"); soft, fill #1d2b24, outline #335043 ("Yes 67¢ ↗"); soft, fill #1e1e1e ("NVDA NVIDIA 187.42 -0.51%"); the odd one out: "NVDA NVIDIA 187.42 -0.51%"

   Checker suggestion: one primary and one secondary button: one shape, one height per size, one label size

2. **button-styles** — (the page)

   3 button styles on the page: soft, fill #28241f, outline #3a3129 x6 ("Overview"); soft, fill #1e1e1e x1 ("NVDA NVIDIA 187.42 -0.51%"); soft, fill #1d2b24, outline #335043 x4 ("Yes 67¢ ↗")

   Checker suggestion: one primary and one secondary button: one shape, one height per size, one label size

3. **heading-scale** — div#overview-markets > article.market-card:nth-of-type(1) > div.probability-row > div.probability "67%chance"

   the figure "67%chance" is set at 28px, larger than the section headings (h2 19px); 3 more like it

   Checker suggestion: set figures at the h2 size or under: a stat reads as data, not as the heading

4. **off-grid** — section#overview > div.wrap.dashboard-content > div.data-notice > span:nth-of-type(2) "Synthetic data / 6 Nov 2026 close"

   left edge at 270px, 14px off the page margin at 256px (10 elements, like button.ticker-card.active)

   Checker suggestion: move it onto the page margin, or the column edge its section uses

5. **section-height** — section#overview "Your market workspaceMarket overview.Fol"

   the section starts at 72px, 72px below the screen grid (0 x 900px): sections start on whole screens (SR-2)

   Checker suggestion: make every section above it exactly one or two screens tall, so this one starts on a whole screen

6. **one-heading** — h2#chart-name "NVIDIA"

   the hero holds an h2 (3): its heading is the h1, and an h2 opens the next section (SR-5)

   Checker suggestion: give each section one h2, first in its .wrap, and the hero only its h1

7. **container-edges** — section#overview "Your market workspaceMarket overview.Fol"

   the content of section 1 runs 256px from the left and 32px from the right: 256 and 32px are not one margin; the margin is 64-120px at 1440px (one container, equal margins, 2px either way) (SR-6)

   Checker suggestion: use one container on every section and the nav (.wrap): one margin left and right, 64-120px on a desktop, 16-24px on a phone

8. **container-edges** — div.app-shell > header.topbar "Workspace/OverviewSimulation modeJD"

   the nav's content runs 256px from the left and 39px from the right (read from its outermost blocks: no .wrap): 256 and 39px are not one margin; the margin is 64-120px at 1440px (one container, equal margins, 2px either way) (SR-6)

   Checker suggestion: use one container on every section and the nav (.wrap): one margin left and right, 64-120px on a desktop, 16-24px on a phone

9. **container-edges** — a.skip-link "Skip to dashboard"

   a <a> at the top of the page, outside header.nav, main, footer.closing and nav.actionbar (SR-6)

   Checker suggestion: build the page as header.nav, a main of sections (each one in-flow .wrap plus background layers) and footer.closing

10. **container-edges** — aside#sidebar "tavreniq. MPersonal workspacePaper accou"

   a <aside> at the top of the page, outside header.nav, main, footer.closing and nav.actionbar (SR-6)

   Checker suggestion: build the page as header.nav, a main of sections (each one in-flow .wrap plus background layers) and footer.closing

11. **container-edges** — div.app-shell "Workspace/OverviewSimulation modeJD Your"

   a <div> at the top of the page, outside header.nav, main, footer.closing and nav.actionbar (and 1 more like it: "Your market workspaceMar") (SR-6)

   Checker suggestion: build the page as header.nav, a main of sections (each one in-flow .wrap plus background layers) and footer.closing

12. **container-edges** — div.main-grid > article.panel.forecast-panel > div.panel-heading > h2 "Forecast snapshot"

   the h2 starts 809px right of the container's left: every h1 and h2 starts on it, 2px either way (SR-6)

   Checker suggestion: start the text on the container's left, or on the one split line every split shares

13. **container-edges** — h2#chart-name "NVIDIA"

   the h2 starts 73px right of the container's left: every h1 and h2 starts on it, 2px either way (SR-6)

   Checker suggestion: start the text on the container's left, or on the one split line every split shares

14. **container-edges** — section#overview > div.wrap.dashboard-content > div.data-notice > span:nth-of-type(2) "Synthetic data / 6 Nov 2026 close"

   1 text block starts on a left line at x 270, 14px from the container's left: text starts on the container's left, or on one split line (x 746, 844, 942) (SR-6)

   Checker suggestion: start the text on the container's left, or on the one split line every split shares

15. **button-styles** — button#export-button "Export data"

   one button style (soft, fill #1c1c1c, outline #363636) with labels in 2 sizes: 13, 16px ("Export data", "Yes 67¢ ↗")

   Checker suggestion: one primary and one secondary button: one shape, one height per size, one label size

16. **heading-scale** — div#overview-markets > article.market-card:nth-of-type(1) > h3.contract-title "NVIDIA to close above $200?"

   an h3 at 19px, as large as the smallest h2 (16px) or larger (and 2 more like it: "Apple to close above $24", "Fed to cut rates in Dece")

   Checker suggestion: size headings by level: the h1 largest, one size per level, each level below the one above

17. **hero-fold** — #overview section.dashboard-view.hero "Your market workspaceMarket over"

   starts at y 72, not under the nav

   Checker suggestion: the hero fills the first screen alone, its button inside it

These are retained application-layout differences: the sidebar occupies one edge, headings and values live inside financial panels, interactive chart/market controls have semantic states, and the workspace scrolls beyond one screen. The report preserves each exact checker finding; it does not suppress them or modify the kit.

## Gate warnings

- fold-card — section#overview > div.wrap.dashboard-content > div.main-grid > article.panel.price-panel "N NVIDIA Semiconductors · NASDAQ $187.42": the 760x519 card starts on the first screen and runs 26px past its bottom
- fold-card — section#overview > div.wrap.dashboard-content > div.main-grid > article.panel.forecast-panel "Forecast snapshot Trend model Next-sessi": the 368x519 card starts on the first screen and runs 26px past its bottom
- fold-cut — div.main-grid > article.panel.price-panel > div.chart-footer > span "Approximate 90% forecast range": a line of the hero text is sliced by the bottom of the first screen
- pricing-tiers — div#overview-markets "NVDA Weekly close NVIDIA to close above ": 4 priced cards laid out as plans, with no subscription to choose
- copy-headings — h2#chart-name "NVIDIA": "NVIDIA" names no product, part, place or section (the one brand line a page may have)
- copy-buttons — aside#sidebar > nav.side-nav > a:nth-of-type(1) "Overview": "Overview" does not start with a verb (book, buy, try, start, get, see...) (and 10 more like it: "NVDA NVIDIA 187.42 -0.51", "Export data", "Yes 67¢ ↗", "No 33¢ ↗", ...)
- copy-buttons — div#watchlist > button.watch-item.selected "NVDA NVIDIA 187.42 -0.51%": "NVDA NVIDIA 187.42 -0.51%" is 6 words (1 to 5)
- copy-actions — (the page): 11 different button labels on the page (at most 10)
- heading-scale — div.wrap.dashboard-content > div.market-section-heading > div > h2 "Prediction markets": h2 headings in 2 sizes, 16px ("NVIDIA") to 19px (x1.19)
- nav-family — aside#sidebar: the nav's links and actions use 2 type families (Schibsted Grotesk, JetBrains Mono)
- nav-labels — aside#sidebar > nav.side-nav > a:nth-of-type(4) "Methodology": "Methodology" opens a section headed "Behind the forecast."
- label-centre — aside#sidebar > nav.side-nav > a:nth-of-type(1) "Overview": its label sits 73px off-centre (13px of room at the left, 86px at the right)
- fake-button — div.app-shell > header.topbar > div.top-actions > span.demo-pill "Simulation mode": "Simulation mode" looks like a button (soft, fill #221e1a, outline #3a3028, the same look as the page's buttons) but is not a link or a button
- stranded-action — button#export-button "Export data": stands 745px across from the nearest text of its block ("Market overview.")
- copy-length — section#overview "Market overview.": 1 section over 90 words a screen outside the UI mocks ("Market overview." 156); 156 words a screen across the page (218 words in 1.4 screens): a tech page says it in about 80 or fewer
- button-contrast — div#watchlist > button.watch-item.selected "NVDA NVIDIA 187.42 -0.51%": the button "NVDA NVIDIA 187.42 -0.51%" (#1e1e1e) stands only 1.11:1 off the ground around it: it reads as part of the ground, or as switched off
- fold-action — div#overview-markets > article.market-card:nth-of-type(1) > div.market-buttons > button:nth-of-type(1): the hero's second button "Yes 67¢ ↗" starts 274px below the first screen (900px tall): it is not seen on load
- fold-action — div#overview-markets > article.market-card:nth-of-type(1) > div.market-buttons > button:nth-of-type(2): the hero's second button "No 33¢ ↗" starts 274px below the first screen (900px tall): it is not seen on load
- fold-action — div#overview-markets > article.market-card:nth-of-type(2) > div.market-buttons > button:nth-of-type(1): the hero's second button "Yes 42¢ ↗" starts 274px below the first screen (900px tall): it is not seen on load
- fold-action — div#overview-markets > article.market-card:nth-of-type(2) > div.market-buttons > button:nth-of-type(2): the hero's second button "No 58¢ ↗" starts 274px below the first screen (900px tall): it is not seen on load
- fold-action — div#overview-markets > article.market-card:nth-of-type(3) > div.market-buttons > button:nth-of-type(1): the hero's second button "Yes 74¢ ↗" starts 274px below the first screen (900px tall): it is not seen on load
- fold-action — div#overview-markets > article.market-card:nth-of-type(3) > div.market-buttons > button:nth-of-type(2): the hero's second button "No 26¢ ↗" starts 274px below the first screen (900px tall): it is not seen on load
- fold-action — div#overview-markets > article.market-card:nth-of-type(4) > div.market-buttons > button:nth-of-type(1): the hero's second button "Yes 61¢ ↗" starts 274px below the first screen (900px tall): it is not seen on load
- fold-action — div#overview-markets > article.market-card:nth-of-type(4) > div.market-buttons > button:nth-of-type(2): the hero's second button "No 39¢ ↗" starts 274px below the first screen (900px tall): it is not seen on load
- visual-caption — div.main-grid > article.panel.price-panel > div.chart-footer > span "Approximate 90% forecast range": a muted 13px line of 2 rows sits 9px under the drawing (svg): it reads as a caption: "Approximate 90% forecast range"; no caption or description under any image, render or visual (house rule)
