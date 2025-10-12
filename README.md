# OptiStock 📈
OptiStock is a smart stock-recommender platform that analyzes historical trends to suggest potential buy opportunities.  
It combines financial logic with custom momentum indicators to help users discover promising stocks quickly.

---

## 🚀 Features
- Real-time stock search and visualization  
- Custom algorithm based on **momentum and RSI analysis**  
- Interactive dashboard for tracking multiple tickers  
- API-driven backend for fetching and caching stock data  
- Clean and responsive UI for an intuitive experience  

---

## 🧰 Tech Stack
**Backend:** Python (Flask), Pandas, Yahoo Finance API  
**Frontend:** TypeScript, React, HTML, CSS  
**Database:** SQLite / JSON storage (prototype)  
**Deployment:** Dockerized backend + frontend containers  

---

## 🧩 System Overview
1. User selects or searches for stocks  
2. Backend retrieves data via the Yahoo Finance API and applies custom scoring logic  
3. Recommendations are ranked by computed momentum indicators  
4. Frontend displays real-time charts and scores through REST API calls  

---

## 🧠 Learning & Development Notes
- Implemented the project to explore **data-driven decision systems** and API integration.  
- Experimented with various weighting schemes for stock momentum and volatility.  
- Used Docker for consistent environment setup and easy deployment.  
- Learned how to design and consume RESTful APIs across backend and frontend.  

---

## 💡 Future Improvements
- Add ML-based prediction models for enhanced accuracy  
- Integrate real-time news sentiment analysis  
- Implement authentication and personalized dashboards  
- Store data in a scalable cloud database (e.g., Firestore or PostgreSQL)

---

> *Created to combine our interests in economics, data analysis, and software engineering.*
