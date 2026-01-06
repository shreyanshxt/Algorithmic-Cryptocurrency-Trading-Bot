# Multi-Exchange Quant Trading Engine with CSP

A high-concurrency, asynchronous trading bot built for the **GoQuant** ecosystem. This system manages automated execution across multiple exchanges simultaneously with a focus on capital preservation.

## 🚀 Key Features
* **Multi-Exchange Synchronization**: Unified portfolio tracking across OKX, Bybit, and KuCoin.
* **Asynchronous Architecture**: Built using `asyncio` and `websockets` for non-blocking, real-time market data processing.
* **Dynamic Rebalancing**: Automatically transitions between 'Strategic Buying' and 'Liquidity Recovery' modes based on a $2,000 reserve threshold.
* **Critical Stop Protection (CSP)**: An automated circuit-breaker that liquidates positions and shuts down the bot if total USDT drops below $0.00.

## 🛠 Tech Stack
* **Language**: Python 3.12+
* **Libraries**: `websockets`, `aiohttp`, `requests`
* **APIs**: GoQuant WebSocket V1, Coinbase Spot Price API

## 📋 Strategy Logic
1.  **Short-Covering**: Closes any risky net short positions immediately.
2.  **Liquidity Check**: If USDT < $2,000, the bot sells long positions to free up capital.
3.  **Algorithmic Entry**: If USDT > $2,000, the bot places $100 trades using the `market_edge` algorithm.

## 🚦 Getting Started
1. Clone the repository.
2. Install dependencies: `pip install -r requirements.txt`.
3. Update `USER_EMAIL` and `USER_PASSWORD` in the script.
4. Run the bot: `python trading_bot.py`.
