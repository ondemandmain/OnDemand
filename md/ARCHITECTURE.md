# Architecture

High-level components and data flows for the On-Demand paper trading app.

Components

- Frontend: SPA (React/Vue) for search, orders, portfolio, and leaderboards.
- Backend API: Auth, order simulation, portfolio calculations, and business logic.
- Database: Persist users, portfolios, trades, leagues, and audit logs.
- Market data adapter: Normalizes and caches quotes from providers.
- Trading engine (simulator): Validates orders and computes fills and P/L.
- Real-time: WebSockets for live price updates and leaderboard refreshes.

Data flow

1. Frontend requests quote -> Backend market adapter (cached) -> Provider.
2. User places order -> Backend validates -> Trading simulator updates DB.
3. Portfolio endpoint aggregates holdings + latest prices -> Frontend.

Integration points

- Market API (Alpha Vantage, Twelve Data, etc.)
- Authentication provider (email/password, OAuth optional)
- Optional analytics (e.g., Amplitude) and monitoring
