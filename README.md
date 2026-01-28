# Task 1: Predictive Core – Stock Price Forecasting

## Overview
This project implements a predictive forecasting engine for financial time series data.
Using historical stock market data, the model forecasts future price movements while explicitly modeling uncertainty and volatility.

The system is designed to analyze trends, momentum, and seasonality in stock prices and generate probabilistic forecasts with confidence intervals.

---

## Objectives
- Learn from historical stock price data
- Forecast future prices for a fixed horizon (7 days)
- Model uncertainty and volatility using confidence intervals
- Evaluate forecasting accuracy using past data

---

## Dataset
- Format: CSV
- Contents: Daily OHLCV (Open, High, Low, Close, Volume) stock data
- Frequency: Business days
- Source: User-provided CSV file (can be extended to multiple tickers)

---

## Methodology

### Data Preprocessing
- Converted date column to datetime format
- Set date as the index
- Enforced business-day frequency
- Handled missing values using forward fill

### Model Used
**SARIMA (Seasonal AutoRegressive Integrated Moving Average)**

Why SARIMA:
- Captures trends using differencing
- Models short-term momentum using AR and MA terms
- Accounts for weekly seasonality in financial markets
- Provides confidence intervals for uncertainty estimation

### Validation Strategy
- Dataset split into training (85%) and testing (15%)
- Rolling forecast validation performed on unseen data

---

## Evaluation Metrics
The model is evaluated using out-of-sample data with the following metrics:

- **RMSE (Root Mean Squared Error)**  
  Measures the average magnitude of prediction error

- **MAPE (Mean Absolute Percentage Error)**  
  Measures relative forecasting accuracy

---

## Output & Visualizations
The notebook produces the following outputs:

- Historical stock price trend
- Rolling forecasts on past (test) data
- 7-day future price forecast
- Shaded confidence intervals indicating uncertainty and volatility
- Printed accuracy metrics (RMSE and MAPE)

---

## Results
- The model successfully captures historical trends and seasonal patterns
- Forecast uncertainty increases over time, reflected by widening confidence intervals
- The approach provides both point estimates and risk-aware predictions

---

## Limitations & Future Improvements
- SARIMA assumes linear relationships and may not capture abrupt market shocks
- Performance may degrade during extreme volatility events
- Future enhancements may include:
  - LSTM or Transformer-based deep learning models
  - Multi-ticker forecasting
  - Incorporation of macroeconomic indicators

---

## Technologies Used
- Python
- Pandas
- NumPy
- Statsmodels
- Matplotlib
- Scikit-learn

---

## How to Run
1. Place the CSV dataset in the project directory
2. Open the Jupyter Notebook
3. Run all cells sequentially from top to bottom
4. View generated plots and evaluation metrics

---

# Task 2: Analytical Chatbot (RAG & Market Explanation)

## Overview

This project implements an **Analytical Financial Chatbot** using **Retrieval-Augmented Generation (RAG)** to answer natural language questions about stock market behavior.  
The chatbot understands user intent, identifies relevant stock tickers, retrieves contextual data (prices, trends, and news), and provides **human-readable explanations** for market movements.

The system is designed to go beyond raw numbers by explaining *why* a stock moved, not just *when* or *how much*.

---

## Goal

To build a natural language interface that allows users to:

- Query financial datasets using conversational language
- Identify relevant stock tickers automatically (e.g., Apple → `AAPL`)
- Analyze historical trends (uptrends, downtrends)
- Retrieve contextual information (news/events)
- Explain market behavior using RAG-based reasoning

---

## Example Queries

### Contextual Explanation
**User:**  
> Why did Apple stock drop?

**System Behavior:**  
- Identifies ticker: `AAPL`
- Retrieves relevant price movements
- Searches related news and reports
- Explains the likely causes behind the decline

---

### Trend Analysis
**User:**  
> When did Microsoft go up?

**System Behavior:**  
- Identifies ticker: `MSFT`
- Analyzes historical price trends
- Detects uptrend periods
- Correlates movements with key events or sentiment

---

## Key Concepts Used

- **Retrieval-Augmented Generation (RAG)**
- **Semantic Intent Understanding**
- **Financial Time-Series Analysis**
- **Contextual Explanation using LLMs**

---

## Architecture & Design

### Agent-Based Workflow

The system is modular and can be extended using multiple agents:

- **Research Agent**  
  Retrieves financial news, reports, and contextual documents.

- **Analysis Agent**  
  Performs trend detection and price movement analysis.

- **Explanation Agent**  
  Uses an LLM to generate natural language explanations.

---

### RAG Pipeline

- Query Rephrasing  
- Query Splitting  
- Vector Search & Reranking  
- Context Injection into LLM Prompt  

This ensures accurate, relevant, and explainable answers.

---

## Technologies Used

- **Python**
- **Pandas / NumPy** – Data processing & analysis
- **LangChain** – LLM orchestration
- **Vector Database** – Context retrieval
- **LLMs**  
  - Open-source models (Hugging Face)  
  - or APIs (Groq / Gemini)
- **Sentiment Analysis** – Enhances explanation quality

---




