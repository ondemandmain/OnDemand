# Data Sources & Market APIs

Short notes about market data options, limitations, and setup.

Recommended providers

- Alpha Vantage — free tier, rate limits; good for prototypes.
- Twelve Data — simple API, paid tiers for higher limits.
- Yahoo Finance (unofficial) — easy access but limited guarantees.
- IEX Cloud — solid API, US-focused, paid plans.
- Local NSE/BSE providers — paid feeds for low-latency / official data.

Important considerations

- Real-time vs delayed: exchanges often charge for real-time feeds.
- Rate limits: cache and batch requests to avoid throttling.
- Licensing: check usage rights for redistribution or public display.
- Timezones & market hours: handle market open/close and holidays.

Setup tips

- Store API keys in environment variables (`MARKET_API_KEY`).
- Implement server-side caching (Redis or in-memory TTL) for quotes.
- Normalize symbols and handle exchanges explicitly (e.g., `NSE:RELIANCE`).

Example env variables

- `MARKET_API_PROVIDER=alpha_vantage`
- `MARKET_API_KEY=your_api_key_here`
