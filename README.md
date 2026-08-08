
# On-Demand — Paper Trading Platform

A simple, social paper-trading app for learning and competitive practice with
virtual money and real market data.

Why this project exists

- Learn trading without financial risk.
- Test strategies using real market prices.
- Compete and compare performance with friends.

Highlights

- Every user starts with a configurable virtual balance (default: ₹1,00,000).
- Real (live or delayed) market data from a pricing API.
- Simulated buy/sell orders, instant portfolio updates, and P/L tracking.
- Social leagues, leaderboards, and trade sharing.

Quick demo

1. Sign up and get ₹1,00,000 in virtual cash.
2. Search for a stock (e.g., Reliance Industries).
3. Buy/sell at market price and watch your portfolio update.
4. Join or create a private league and compare rankings.

Core concepts

- Virtual balance: No real deposits or withdrawals — purely simulated.
- Market feed: Connect to a stock price API to fetch quotes and chart data.
- Trading engine: Execute simulated market orders and update holdings.
- Leaderboard: Rank users by portfolio value, returns, or custom metrics.

Features

- User accounts: sign up, sign in, profile, friends
- Portfolio: holdings, cash balance, total return, history
- Market data: quotes, simple charts, instrument search
- Orders: market buy/sell, order confirmation, simulated fills
- Social: leagues, invites, leaderboards, shareable portfolios

Example leaderboard

| Rank | User | Portfolio Value |
|------|------|-----------------:|
| 1 | Rahul | ₹1,12,500 |
| 2 | Arjun | ₹1,08,200 |
| 3 | You | ₹1,05,900 |

MVP roadmap

1. Basic auth + initial virtual balance
2. Market data integration (one API)
3. Buy/sell simulation and portfolio calculations
4. Leagues, invites, and leaderboard

Starter tech suggestions

- Backend: Node.js + Express, or Python + FastAPI/Django
- Database: PostgreSQL (recommended) or SQLite for quick MVP
- Market API: Alpha Vantage, Yahoo Finance, Twelve Data, or an NSE/BSE provider
- Frontend: React (CRA/Vite), Vue, or Svelte
- Real-time: WebSockets (Socket.IO or native) for live updates

Getting started (local)

1. Clone the repo:

```bash
git clone https://github.com/ondemand-main/On-Demand.git
cd On-Demand
```

2. Read the project `docs/` or start the backend and frontend per subfolder
(add instructions here as you scaffold services).

Configuration

- Add your market API key to `./backend/.env` as `MARKET_API_KEY` (provider
	dependent).
- Configure initial virtual balance and other feature flags in the
	backend configuration.

Contributing

- Open issues for features or bugs.
- Fork, implement, and send a pull request. Keep PRs scoped and include
	tests for core logic (order simulation, portfolio math).

License

This repo is currently experimental. Add a `LICENSE` file to declare terms.

Contact

Create an issue or open a discussion in this repository for questions and
collaboration.

