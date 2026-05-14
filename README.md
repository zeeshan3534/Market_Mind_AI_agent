# Market_Mind_AI_agent
# 📈 Stock Predictor Agent
 
An AI-powered stock analysis agent that fetches real-time market data, computes technical indicators, and uses an LLM to generate a **Buy / Hold / Sell** recommendation — built with Python, CrewAI, yfinance, and OpenRouter.
 
---
 
## 🧠 How It Works
 
```
Stock Ticker (e.g. HASCOL.KA)
        │
        ▼
  yfinance — fetches 6 months of OHLCV data + live price/market cap
        │
        ▼
  ta library — computes 7 technical indicators
        │
        ▼
  LLM via OpenRouter (DeepSeek) — generates investment recommendation
        │
        ▼
  CrewAI Market Analyst Agent — wraps the analysis in an agentic role
```
 
---
 
## ✨ Features
 
- **Live stock data** — fetches current price, market cap, and 6-month OHLCV history via yfinance
- **7 technical indicators** — RSI, MACD, SMA20, EMA20, Bollinger Bands, Stochastic Oscillator, ADX
- **AI recommendation** — sends indicators to an LLM and gets a clear Buy / Don't Buy answer with reasoning
- **CrewAI agent** — wraps the analyst logic in a role-based agent framework for extensibility
- **Free LLM** — uses DeepSeek via OpenRouter (free tier)
---
 
## 🗂️ Project Structure
 
```
Stock_predictor_agent.ipynb   # Main notebook — all logic lives here
README.md                     # This file
```
 
---
 
## ⚙️ Requirements
 
| Package   | Purpose                          |
|-----------|----------------------------------|
| `yfinance`| Fetch stock data from Yahoo Finance |
| `pandas`  | Data manipulation                |
| `ta`      | Technical analysis indicators    |
| `openai`  | OpenAI-compatible client (for OpenRouter) |
| `crewai`  | Agent framework                  |
 
Install all dependencies:
 
```bash
pip install yfinance pandas ta openai crewai
```
 
---
 
## 🚀 Getting Started
 
### 1. Clone / open the notebook
 
Open `Stock_predictor_agent.ipynb` in Jupyter or Google Colab.
 
### 2. Set your API key
 
In the notebook, replace the OpenRouter API key:
 
```python
client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY",   # ← replace this
)
```
 
Get a free key at → [openrouter.ai](https://openrouter.ai)
 
### 3. Set the stock ticker
 
```python
stockName = "HASCOL.KA"   # ← change to any Yahoo Finance ticker
```
 
Examples: `AAPL`, `GOOGL`, `TSLA`, `PSO.KA`, `ENGRO.KA`
 
### 4. Run all cells
 
The notebook will:
1. Fetch live price and market cap
2. Download 6 months of historical data
3. Calculate all technical indicators
4. Send indicators to the LLM
5. Print the AI recommendation
---
 
## 📊 Technical Indicators Explained
 
| Indicator | What it tells you |
|-----------|-------------------|
| **RSI** (Relative Strength Index) | Overbought (>70) or oversold (<30) |
| **MACD** | Momentum and trend direction |
| **SMA20** | 20-day simple moving average — trend baseline |
| **EMA20** | 20-day exponential moving average — more weight on recent prices |
| **Bollinger Bands** | Volatility range — price near upper band = overbought |
| **Stochastic Oscillator** | Momentum relative to price range |
| **ADX** | Trend strength — >25 means strong trend |
 
---
 
## 🤖 LLM & Model
 
- **Provider:** [OpenRouter](https://openrouter.ai) (free tier)
- **Model:** `deepseek/deepseek-v4-flash:free`
- **Alternative free models:** `meta-llama/llama-4-scout:free`, `mistralai/mistral-7b-instruct:free`



📊 Technical Indicators Explained
IndicatorWhat it tells youRSI (Relative Strength Index)Overbought (>70) or oversold (<30)MACDMomentum and trend directionSMA2020-day simple moving average — trend baselineEMA2020-day exponential moving average — more weight on recent pricesBollinger BandsVolatility range — price near upper band = overboughtStochastic OscillatorMomentum relative to price rangeADXTrend strength — >25 means strong trend
