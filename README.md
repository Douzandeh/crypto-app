# 🪙 CryptoTracker — Real-Time Cryptocurrency Dashboard

A sleek, responsive React application that lets you explore, search, and analyze live cryptocurrency market data powered by the CoinGecko API.

---

## 📌 Overview

CryptoTracker is a front-end web app built with **React + Vite** that displays real-time cryptocurrency rankings, prices, 24-hour changes, and interactive 7-day price charts. Users can search for any coin, switch between major fiat currencies, paginate through 200 top coins, and dive into detailed market charts — all in a clean dark-themed UI.

---

## ✨ Features

- **Live Coin Rankings** — Fetches the top 200 cryptocurrencies sorted by market cap from CoinGecko, displayed in a sortable table with price, 24h change, and total volume.
- **Interactive Price Charts** — Click any coin symbol to open an overlay chart showing 7-day historical data for Prices, Market Caps, or Total Volumes (powered by Recharts).
- **Real-Time Search** — Debounced search with a live dropdown showing coin icons and names as you type, with abort-controlled fetch requests to avoid stale results.
- **Multi-Currency Support** — Switch between USD, EUR, and JPY on the fly; the entire coin list re-fetches in the selected currency.
- **Paginated Browsing** — Navigate through 10 pages of 20 coins each with a smart pagination component that highlights the current page.
- **24h Trend Indicators** — Color-coded percentage badges (green / red) and trend arrow icons make it immediately clear which coins are up or down.
- **Loading States** — Animated `RotatingLines` spinner from `react-loader-spinner` during data fetches keeps UX smooth.
- **Responsive Table** — Horizontal scroll on mobile ensures the full table is accessible on all screen sizes.

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Framework | React 19 |
| Build Tool | Vite 7 |
| Charting | Recharts 3 |
| Spinner / UI | react-loader-spinner 6 |
| Styling | CSS Modules |
| API | CoinGecko REST API v3 |
| Linting | ESLint 9 + react-hooks plugin |
| Language | JavaScript (JSX) |

---

## 📂 Project Structure

```
crypto-app/
├── index.html                   # HTML entry point
├── vite.config.js               # Vite configuration
├── eslint.config.js             # ESLint flat config
├── package.json
│
└── src/
    ├── main.jsx                 # React DOM root, Global.css import
    ├── App.jsx                  # Root component — wires Layout + HomePage
    ├── Global.css               # Global reset & body styles (dark theme)
    │
    ├── services/
    │   └── CryptoApi.js         # API URL builders (getCoinList, searchCoin, marketChart)
    │
    ├── helpers/
    │   └── convertData.js       # Transforms raw CoinGecko chart arrays into Recharts-ready objects
    │
    ├── layouts/
    │   ├── Layout.jsx           # Header + Footer shell
    │   └── Layout.module.css
    │
    └── components/
        ├── templates/
        │   └── HomePage.jsx     # Page-level state (coins, page, currency, chart)
        │
        └── modules/
            ├── TableCoin.jsx        # Coin table + TableRow sub-component
            ├── TableCoin.module.css
            ├── Search.jsx           # Search input, currency selector, results dropdown
            ├── Search.module.css
            ├── Pagination.jsx       # Previous / Next + page number pills
            ├── Pagination.module.css
            ├── Chart.jsx            # Modal overlay with LineChart + type switcher + coin details
            └── Chart.module.css
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** `>= 20.19.0` (required by Vite 7)
- **npm** `>= 8`

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/douzandeh/crypto-app.git
cd crypto-app

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Build for Production

```bash
npm run build       # outputs to /dist
npm run preview     # serve the production build locally
```

### Lint

```bash
npm run lint
```

---

## 🔑 API Configuration

The app uses the **CoinGecko Demo API** (free tier). The base URL and API key are defined in `src/services/CryptoApi.js`:

```js
const BASE_URL = "https://api.coingecko.com/api/v3";
const API_KEY  = "YOUR_API_KEY_HERE";
```

> **Note:** The demo key included in the source is public and rate-limited. For production use, register for a CoinGecko API key at [coingecko.com/api](https://www.coingecko.com/api/documentation) and replace the value.

---

## 🖥️ Usage

1. **Browse coins** — The homepage loads the top 20 coins by market cap on arrival.
2. **Change currency** — Use the dropdown next to the search bar (USD / EUR / JPY).
3. **Search** — Type a coin name in the search box; a live dropdown appears with matching results.
4. **View chart** — Click a coin's symbol/icon in the table to open the 7-day chart overlay.
5. **Switch chart type** — Inside the chart modal, toggle between **Prices**, **Market Caps**, and **Total Volumes**.
6. **Paginate** — Use **Previous** / **Next** buttons or the numbered page pills to explore more coins.

---

## 📸 Screenshots

> _Add screenshots here once the app is running._

| Homepage | Search | Chart Modal |
|---|---|---|
| `screenshot-home.png` | `screenshot-search.png` | `screenshot-chart.png` |

---

## 🔮 Future Improvements

- [ ] **Favorites / Watchlist** — Allow users to star coins and persist selections in localStorage.
- [ ] **Dark / Light Mode Toggle** — Add a theme switcher while keeping the dark default.
- [ ] **More Currencies** — Extend the currency selector beyond USD / EUR / JPY (GBP, BTC, ETH, etc.).
- [ ] **Adjustable Chart Range** — Let users switch the historical window (1D, 7D, 30D, 1Y).
- [ ] **Portfolio Tracker** — Input holdings to calculate total portfolio value and P&L.
- [ ] **React Router** — Add `/coin/:id` detail pages for deeper per-coin statistics.
- [ ] **Error Boundary** — Wrap async sections with React Error Boundaries for graceful failure UI.
- [ ] **Unit Tests** — Add Vitest + React Testing Library coverage for core components.
- [ ] **PWA Support** — Add a service worker and manifest for offline usage and installability.

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork** the repository.
2. **Create** a feature branch: `git checkout -b feature/your-feature-name`
3. **Commit** your changes with a descriptive message: `git commit -m "feat: add portfolio tracker"`
4. **Push** to your fork: `git push origin feature/your-feature-name`
5. **Open a Pull Request** against the `main` branch and describe your changes.

Please make sure your code passes `npm run lint` before submitting a PR.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

<p align="center">Developed by <strong>Hossein</strong> with ❤️ &nbsp;|&nbsp; <a href="https://github.com/douzandeh">@douzandeh</a></p>
