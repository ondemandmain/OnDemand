# Personal Product Case Study: On-Demand (The Authentic PM Journey)

This document details the product thinking, strategic trade-offs, and authentic motivations behind **On-Demand**. Rather than treating paper trading as a trivial mock portfolio script, I approached this platform as an aspiring Product Manager targeting fintech, wealth-tech, and consumer platforms.

---

### 1. User Discovery (The Psychological Capital Trap)
**The Raw Problem:** Financial education in retail investing has an enormous drop-off rate. When newcomers start trading with their own savings, their first negative trade triggers intense anxiety and panic-selling. Most quit markets forever within 90 days. On the other hand, institutional paper-trading tools look like clunky 1990s accounting software. They are solitary, boring, and disconnected from the social reality of modern retail traders who share ideas on WhatsApp, Telegram, and Reddit.  
**The PM Discovery:** Retail traders don't just want to practice math; they want social validation, friendly competition, and a safe sandbox to test their convictions before putting real skin in the game. I realized the core product hook wasn't the order execution engine: it was the **Social League Layer**.

---

### 2. Roadmapping & Prioritization (The Complexity Scope Cut)
**The Core Goal:** Build a working, intuitive trading simulation loop where a user can go from sign-up to executing their first virtual stock trade in under 90 seconds, and immediately compare their performance against friends in a league.  
**My Scope Pivot:** My initial instinct was to build advanced order types: trailing stop-losses, options chain simulation, and real-time level-2 order book depth. But I had to check my ego. Real-time options pricing and order book depth require expensive low-latency feeds and overwhelm beginners with cognitive overload. I ruthlessly cut options and complex derivatives. My MVP focused on:
1. Clean search and real-time market quote retrieval.
2. Market buy/sell orders with instant weighted average price calculations.
3. Private league creation with shareable invite codes and automated leaderboards.

---

### 3. Sprint Execution & Technical Architecture
I architected the system around clean separation of concerns:
*   **Decoupled Market Data Adapter:** Designed an abstraction layer over external market pricing APIs (Alpha Vantage / Twelve Data / Yahoo Finance) with in-memory Redis/database caching to prevent API rate-limit exhaustion while maintaining realistic tick updates.
*   **Deterministic Portfolio Math:** Modeled relational schemas (`USERS`, `LEAGUES`, `ORDERS`, `TRADES`, `HOLDINGS`) where portfolio valuation is computed idempotently from immutable trade histories rather than mutable client state.
*   **Asynchronous Leaderboard Engine:** Separated user trade placements from league ranking calculations to ensure the UI remains blazing fast even when hundreds of participants are trading simultaneously.

---

### 4. Self-Management (Preventing the "Gaming" Anti-Pattern)
**The Crisis:** In virtual trading games, users frequently exploit infinite resets or take 100x leverage gambles because there is no real-world penalty for blowing up an account. If users treat the platform as a reckless casino, the educational value collapses.  
**My Action:** I introduced strict product guardrails:
1. Virtual wallet resets are prohibited during an active competitive league.
2. Position sizing caps to discourage single-stock "all-in" gambling.
3. Transparent audit trails on leaderboards so participants can inspect each other's historical trade rationale, reinforcing disciplined portfolio construction.

---

### 5. Value Proposition & Measurement (Real-Time Financial Confidence)
**The True ROI:** The value of On-Demand is not paper trading volume: it is **Risk-Free Habit Formation & Financial Literacy**.
*   **For the User:** Safe experimentation, strategy validation, and the joy of peer competition without financial dread.
*   **Product Success Metrics:**
    *   **Time-to-First-Trade (TTFT):** Target < 90 seconds.
    *   **League Virality (K-Factor):** > 1.5 organic invites generated per active league creator.
    *   **Portfolio Diversification Score:** Measuring educational adoption through multi-sector asset distribution.

---

### 6. Product Intuition (The Empathy Lens)
**The Skill:** Just as I apply intuitive pattern recognition from cinema narrative arcs to understand what keeps an audience emotionally hooked, I look at consumer fintech products through the lens of emotional tension. Trading is inherently an emotional rollercoaster of hope, fear, and ego.  
**The Realization:** If a trading app feels sterile and lonely, users abandon it the second their novelty wears off. By injecting social accountability (private leagues with college friends or co-workers) into a risk-free simulator, the emotional experience shifts from lonely fear to positive, competitive camaraderie. I designed On-Demand to make financial empowerment accessible, safe, and social.
