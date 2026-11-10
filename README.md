<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B3D0B,50:1E7B34,100:30D158&height=200&section=header&text=📈%20OptiStocks&fontSize=56&fontColor=ffffff&fontAlignY=38&desc=Budget-%20and%20risk-aware%20portfolio%20builder&descSize=18&descAlignY=60&animation=fadeIn" width="100%" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/yfinance-6001D2?style=for-the-badge&logo=yahoo&logoColor=white" />
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" />
</p>

<p align="center">
  <b>Tell OptiStocks how much you want to invest and how much risk you can stomach.<br/>It builds a diversified, sector-balanced stock portfolio from live market prices in seconds.</b>
</p>

---

## ✨ Highlights

- 💰 **Budget in, portfolio out:** enter a dollar amount and get back exactly which stocks to buy and how many shares of each
- 🎚️ **Risk slider:** controls the split between **mid-cap stocks** (higher growth, higher risk) and **S&P 500 large caps** (more stable)
- 🧺 **Sector diversification:** capital is spread across sectors with target weights (Technology 40% · Healthcare 30% · Consumer Goods 20% · Energy 10%)
- ⏱️ **Live market data:** real-time prices and sector classification pulled from Yahoo Finance via `yfinance`
- 🧮 **Whole-share allocation:** buys only whole shares and tracks the remaining budget so the portfolio never goes over
- 🖥️ **Clean dashboard:** a Next.js + Tailwind frontend shows each pick's ticker, category, sector, price and quantity

Built where my two majors meet: **computer science + economics**.

---

## 🏗️ How It Works

```mermaid
flowchart LR
    U[👤 Investor] -- "budget + risk %" --> F[⚛️ Next.js dashboard]
    F -- "POST /allocate" --> B[🐍 Flask API]
    B --> D[(📄 Mid-cap &<br/>S&P 500 universes)]
    B -- prices + sectors --> Y[📡 Yahoo Finance]
    B --> A[🧮 Allocation engine]
    A -- "ticker · sector · price · qty" --> F
```

### The allocation engine

```mermaid
flowchart TD
    A[Total budget] --> B{Risk slider}
    B -- "risk %" --> C[🚀 Mid-cap budget]
    B -- "100 − risk %" --> D[🏛️ S&P 500 budget]
    C --> E[Split by sector weights<br/>Tech 40 · Health 30 · Consumer 20 · Energy 10]
    D --> E
    E --> F[Buy whole shares per stock<br/>while sector budget remains]
    F --> G[📋 Portfolio recommendations]
```

---

## 📡 API

**`POST /allocate`**

```json
// request
{ "budget": 10000, "risk": 60 }

// response
[
  { "Category": "Mid Cap", "Sector": "Technology", "Symbol": "XYZ", "Price": 42.10, "Quantity": 12 },
  { "Category": "S&P 500", "Sector": "Healthcare", "Symbol": "ABC", "Price": 118.55, "Quantity": 3 }
]
```

---

## 🚀 Getting Started

### Backend
```bash
git clone https://github.com/JeevanJyot55/OptiStocks.git
cd OptiStocks/cheesybackend
pip install flask flask-cors yfinance pandas tqdm
python stockSelectorFunctions.py      # runs on http://127.0.0.1:5000
```

### Frontend
```bash
cd ../cheesyfrontend
npm install
npm run dev                           # http://localhost:3000
```

---

## 📁 Project Structure

```
OptiStocks/
├── cheesybackend/
│   ├── stockSelectorFunctions.py   # Flask API + allocation engine
│   ├── mid-cap.csv                 # Mid-cap stock universe
│   └── s&p500.csv                  # S&P 500 universe with sectors
└── cheesyfrontend/
    ├── components/OptiStock.tsx    # Budget input, risk slider, results
    └── src/app/                    # Next.js app router
```

---

## 🗺️ Roadmap

- [ ] 📊 Momentum and RSI scoring to rank stocks within each sector
- [ ] ⏪ Historical back-testing of generated portfolios
- [ ] 🎛️ User-defined sector weights
- [ ] 📰 News sentiment signals
- [ ] 🔐 Accounts and saved portfolios
- [ ] ⚡ Caching of price and sector lookups for faster responses

> ⚠️ *For educational purposes only. Not financial advice.*

---

<p align="center">
  Built by <a href="https://github.com/JeevanJyot55"><b>Jeevan Jyot Singh</b></a> · <a href="https://www.linkedin.com/in/jeevanjyotsingh">LinkedIn</a> · <a href="https://jeevanjyot55.github.io">Portfolio</a>
</p>
