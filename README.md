<p align="center">
  <img src="https://drive.google.com/uc?id=1WIAq3KN05TBSeoL7x8Ur5RAnCbyp2PkB" alt="CosmoTrade Logo" width="200"/>
</p>

<h1 align="center">🚀 CosmoTrade</h1>
<h3 align="center">An Automated Crypto Signal Bot for Telegram Using Technical Indicators</h3>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#installation">Installation</a> •
  <a href="#usage">Usage</a> •
  <a href="#example-signal">Example</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#license">License</a>
</p>

---

## 📈 Overview

**CosmoTrade** is a fully automated crypto trading signal bot that analyzes market trends using multiple technical indicators and delivers real-time alerts to your Telegram chat. Designed for crypto traders, developers, and enthusiasts, it supports multiple exchanges and strategies, all while being lightweight and easy to deploy.

---

## 🚀 Features

- 📡 Real-time price data for top 30 cryptocurrencies  
- 🔍 Multiple technical analysis strategies:
  - RSI & MACD Divergence
  - Bollinger Band & RSI
  - Moving Average Exponential Crosses in Daily timeframe (50/200)
  - M & W patterns
  - Head and shoulders pattern
  - RSI & Hanging man & Fibonacci levels
- 📤 Automatically sends formatted signals to your Telegram bot
- 🪐 Duplicate signal prevention
- ☁️ Lightweight & VPS-friendly (24/7 operation)
- 🧾 Built-in Flask app to view signals and maintain a trading journal

---

## 🧠 Strategy Logic

**Divergence Detection (RSI & MACD):**  
When price movement conflicts with indicator direction (e.g., rising price but falling RSI/MACD), this may indicate an upcoming reversal.

**Bollinger Band & RSI:**  
Bullish: When the price is in lower band of the bollinger and rsi is less than 30
Bearish: when the price is in upper band of the bollinger and rsi is more than 70

**Moving Average Exponential Crossovers:**  
Cross: 50=200

**M & W patterns**

**Head and shoulders pattern**

**RSI & Hanging Man & Fibonacci Levels**:  
Bullish: When the price is at a Fibonacci support level, the last candle is a hanging man, and RSI is oversold  
Bearish: When the price is at a Fibonacci resistance level, the last candle is a hanging man, and RSI is overbought


> ⚠️ **Disclaimer:** This bot is for informational purposes. Always conduct independent market analysis before trading.

---

## 📦 Requirements

- Python 3.8+
- `pip` or Docker
- Telegram Bot Token and Chat ID
- Flask (for journal interface)
- `.env` file with exchange and credentials
- Redis (used as a database/cache)


---

## 🛠️ Setup Instructions

### 1. Clone the repo

```bash
git clone https://github.com/cosmicdeveloper-lab/cosmotrade.git
cd cosmotrade
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Create a .env file
more about the exchanges https://docs.ccxt.com/#/

```bash
TELEGRAM_TOKEN=your_bot_token
CHAT_ID=your_chat_id
EXCHANGE=your_exchange_name(coinex, kucoin, binance, ...)
WTF_SECRET_KEY=YOUR_SECRET_KEY
REDIS_HOST=YOUR_HOST #localhost
REDIS_PORT=YOUR_PORT #6379
```

### 4. Install Redis

**Redis is required for managing state and caching signals.**

### 🖥️ On Ubuntu/Debian:

```bash
sudo apt update
sudo apt install redis-server

sudo systemctl enable redis-server
sudo systemctl start redis-server
```

### 🍎 On macOS (using Homebrew):

```bash
brew install redis
brew services start redis
```
> ⚠️ **Disclaimer:** Make sure Redis is running and accessible before starting the bot..


### 5. Run the Bot (Basic)

```bash
python main.py
```

## 📸 Example Signal

Sample output delivered via Telegram:

Routes available: /signals/, /journal/

![CosmoTrade Signal Screenshot](https://drive.google.com/uc?id=1nnmfVOSD7a3ox4nY8n6bsguXqvwVmWJR)

![FLASK JORNAL](https://drive.google.com/uc?id=1ITpNnZ-5R_9eM2cqasAZGUM5RgJHZOby)

![FLASK SIGNALS](https://drive.google.com/uc?id=1-ZvmWb9rmhV29XCbcPRt_v_DjqZASD0P)


## Run tests
```bash
python -m unittest discover tests
```

## 🧑‍💻 Author

### Built by Benjamin Amini — feel free to fork and modify!

## 📄 License

This project is licensed under the [MIT License](./LICENSE).

