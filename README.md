# Task-2_predict_Future_Stock_Prices-
## 📈 Predicting Apple Stock Prices Using Machine Learning

![Python](https://img.shields.io/badge/Python-3.10.11-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.2.2-orange)
![pandas](https://img.shields.io/badge/pandas-2.0.3-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## 📋 Project Overview

This project focuses on predicting the next day's closing price of Apple (AAPL) stock using historical market data. The model leverages features like Open, High, Low, and Volume to forecast future prices. This is Task 2 of my internship program, demonstrating skills in time series analysis, regression modeling, and data visualization.

### 🎯 Objective
Use historical stock data to predict the next day's closing price with machine learning models.

## 📊 Dataset

- **Source:** Yahoo Finance (via `yfinance` Python library)
- **Stock:** Apple Inc. (AAPL)
- **Period:** January 2020 - December 2024
- **Records:** 1,257 trading days
- **Features:** Open, High, Low, Close, Volume

### Sample Data
| Date | Open | High | Low | Close | Volume |
|------|------|------|-----|-------|--------|
| 2020-01-02 | $71.41 | $72.46 | $71.16 | $72.40 | 135,480,400 |
| 2020-01-03 | $71.63 | $72.46 | $71.47 | $71.70 | 146,322,800 |
| 2020-01-06 | $70.82 | $72.31 | $70.57 | $72.27 | 118,387,200 |

## 🛠️ Technologies Used

| Library | Purpose |
|---------|---------|
| **yfinance** | Fetching stock data from Yahoo Finance |
| **pandas** | Data manipulation and analysis |
| **numpy** | Numerical computations |
| **scikit-learn** | Machine learning models and evaluation |
| **matplotlib** | Data visualization |
| **seaborn** | Statistical visualizations |

## 🔧 Installation & Setup

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/stock-price-prediction.git
cd stock-price-prediction
```

2. **Install required packages**
```bash
pip install yfinance pandas numpy matplotlib seaborn scikit-learn jupyter
```

3. **Run the Jupyter notebook**
```bash
jupyter notebook Task_02_Predict_Future_Stock_Prices.ipynb
```


## 🧠 Methodology

### 1. Data Collection
```python
import yfinance as yf
df = yf.download("AAPL", start="2020-01-01", end="2024-12-31")
df.columns = [col[0] for col in df.columns]  # Flatten MultiIndex
```

### 2. Feature Engineering
- Created target variable: `Next_Close` (tomorrow's closing price)
- Features used: Open, High, Low, Volume (today's data)
- Removed last row with NaN values

### 3. Model Training
- **Linear Regression** - Baseline model
- Train-test split: 80% training, 20% testing (maintaining chronological order)

### 4. Evaluation Metrics
- **R² Score**: Measures model accuracy (0-1 scale)
- **Mean Squared Error (MSE)**: Average squared difference between predictions and actual values

## 📈 Results

### Model Performance
| Metric | Value |
|--------|-------|
| **R² Score** | 0.9849 |
| **MSE** | 9.6403 |
| **Training Data** | 1,004 days (80%) |
| **Testing Data** | 251 days (20%) |

### Prediction Example
```
Input Values:
- Open: $175.50
- High: $178.20
- Low: $174.80
- Volume: 85,000,000

Predicted Next Day Close: $177.32
```

## 📊 Visualizations

### 1. Actual vs Predicted Pric
<img width="916" height="383" alt="image" src="https://github.com/user-attachments/assets/871baa6f-e30c-40e0-a8a1-1d48eb139e6a" />
(images/stock_prediction_timeseries.png)
*Comparison of actual stock prices vs Linear Regression predictions*

### 2. Model Accuracy Scatter Plot
![Scatter Plot](images/stock_prediction_scatter.png)
*Scatter plot showing predicted vs actual values with perfect prediction line*

### 3. Feature Importance (Random Forest)
![Feature Importance](images/feature_importance.png)
*Relative importance of each feature in predicting stock prices*

## 💡 Key Insights

1. **High Accuracy**: The Linear Regression model achieved 98.5% accuracy (R² = 0.9849)
2. **Feature Importance**: Open and High prices are the strongest predictors
3. **Data Quality**: No missing values in the dataset
4. **Temporal Patterns**: Stock prices show strong autocorrelation

## 🚀 How to Use the Predictor

### Simple User Input Prediction

```python
# Run the prediction cell in the notebook
Enter today's Open price: $175.50
Enter today's High price: $178.20
Enter today's Low price: $174.80
Enter today's Volume: 85000000

# Output:
📈 Based on today's values:
   Open: $175.50
   High: $178.20
   Low: $174.80
   Volume: 85,000,000

🔮 PREDICTED TOMORROW'S CLOSE: $177.32
```

## ✅ Task Requirements Checklist

- [x] Select a stock (Apple - AAPL)
- [x] Load historical data using yfinance
- [x] Use Open, High, Low, Volume as features
- [x] Train Linear Regression model
- [x] Train Random Forest model (optional)
- [x] Plot actual vs predicted prices
- [x] Make predictions with new user input
- [x] Evaluate model performance

## 🔮 Future Improvements

1. **Add more features**: Moving averages, RSI, MACD
2. **Try advanced models**: LSTM, XGBoost, Prophet
3. **Multi-day prediction**: Forecast 5-10 days ahead
4. **Sentiment analysis**: Include news and social media data
5. **Web application**: Deploy as a Streamlit or Flask app

## ⚠️ Note

This project is for **educational purposes only**. Stock market prediction is inherently uncertain, and this model should not be used for actual trading decisions.


## 👤 Author

**DeveloperHC Intern**
- GitHub: [zaryab ahmad ](https://github.com/ZaryabAhmad01)
- Date: March 2026
- Task: Internship Task 2 - Predict Future Stock Prices (Short-Term)

## 🙏 Acknowledgments

- Yahoo Finance for providing free stock data
- scikit-learn documentation for machine learning resources
- My internship mentor for guidance

---


