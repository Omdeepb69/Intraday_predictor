# 🚀 Intraday Predictor Goo

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![PyTorch](https://img.shields.io/badge/PyTorch-Latest-red.svg)](https://pytorch.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Trading](https://img.shields.io/badge/Market-NSE%20India-orange.svg)](https://nseindia.com)

> **🎯 AI-Powered Next-Day Stock Price Predictor for Indian Markets**

Transform your trading game with deep learning! This advanced LSTM-based predictor analyzes historical data to forecast next-day High, Low, and Close prices for top Indian stocks, complete with actionable trading signals.

![Stock Prediction Demo](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)

## 🔥 Key Features

- **🤖 Deep Learning**: Multi-target LSTM neural network for precise predictions
- **📊 Multi-Price Prediction**: Predicts High, Low, and Close prices simultaneously
- **🎯 Smart Trading Signals**: Automated BUY/SELL/HOLD recommendations
- **📈 Technical Indicators**: RSI, Moving Averages, Volatility analysis
- **🕘 Market Timing**: Respects Indian market hours and holidays
- **📱 Visual Analytics**: Beautiful charts and profit/loss scenarios
- **⚡ Real-time Data**: Live data fetching from Yahoo Finance

## 🏆 Supported Stocks

Premium Indian stocks including:
- **RELIANCE** - Reliance Industries
- **TCS** - Tata Consultancy Services  
- **INFY** - Infosys
- **HDFCBANK** - HDFC Bank
- **ICICIBANK** - ICICI Bank
- **SBIN** - State Bank of India
- **ITC** - ITC Limited
- **HINDUNILVR** - Hindustan Unilever
- **KOTAKBANK** - Kotak Mahindra Bank
- **BAJFINANCE** - Bajaj Finance

## 🚀 Quick Start

### Prerequisites
```bash
Python 3.8+
CUDA (optional, for GPU acceleration)
```

### Installation
```bash
# Clone the repository
git clone https://github.com/Omdeepb69/Intraday_predictor_goo.git
cd Intraday_predictor_goo

# Install dependencies
pip install -r requirements.txt
```

### Dependencies
```bash
pip install yfinance torch numpy pandas matplotlib scikit-learn pytz
```

### Run Predictions
```bash
python predictor.py
```

## 💡 How It Works

### 1. **Data Collection**
- Fetches 2 years of historical data
- Calculates technical indicators (RSI, Moving Averages, Volatility)
- Handles market holidays and weekends

### 2. **Feature Engineering**
- **Price Features**: Open, High, Low, Close, Volume
- **Technical Features**: RSI, Moving Averages (20, 50 days)
- **Market Features**: Volatility, Volume Ratio, Price Range

### 3. **Deep Learning Model**
- **Architecture**: Multi-target LSTM with 3 layers
- **Sequence Length**: 30 days lookback
- **Targets**: Next-day High, Low, Close prices
- **Optimization**: AdamW optimizer with learning rate scheduling

### 4. **Trading Signals**
```python
# Signal Generation Logic
if expected_return > 2%:
    signal = "BUY"
elif expected_return < -2%:
    signal = "SELL/SHORT"
else:
    signal = "HOLD"
```

## 📊 Sample Output

```
🔥 NEXT DAY TRADING PREDICTIONS FOR RELIANCE 🔥
========================================================
📅 Today: Monday, 2024-06-24
📅 Next Trading Day: 2024-06-25
🕘 Market Status: CLOSED
⏰ Prediction Time: 2024-06-24 20:30:15 IST

📊 PRICE PREDICTIONS:
Current Price: ₹2,845.60
Predicted HIGH: ₹2,892.40
Predicted LOW:  ₹2,798.20
Predicted CLOSE: ₹2,867.80

💰 PROFIT ANALYSIS:
Expected Return: 0.78%
Trading Range: ₹94.20
Risk-Reward Ratio: 1.45

🎯 TRADING RECOMMENDATION:
Action: HOLD
Entry Price: ₹2,845.60
Target Price: ₹2,867.80
Stop Loss: ₹2,742.23
Profit Potential: 0.78%
Risk Level: MEDIUM
```

## 🎨 Visualization Features

- **📈 Price Prediction Charts**: Historical vs Predicted prices
- **📊 Profit/Loss Scenarios**: Conservative, Expected, Optimistic
- **📉 Volume Analysis**: Recent trading volume trends
- **🎯 Price Level Comparisons**: Current vs Predicted levels

## ⚙️ Configuration

### Model Parameters
```python
seq_length = 30      # Days of historical data to consider
hidden_dim = 128     # LSTM hidden layer size
num_layers = 3       # Number of LSTM layers
epochs = 150         # Training epochs
```

### Trading Parameters
```python
buy_threshold = 2%    # Minimum return for BUY signal
sell_threshold = -2%  # Maximum loss for SELL signal
stop_loss_buffer = 2% # Additional buffer for stop loss
```

## 🕐 Market Timing

- **Trading Hours**: 9:15 AM - 3:30 PM IST
- **Market Days**: Monday - Friday
- **Automatic Detection**: Respects weekends and Indian holidays
- **Next Day Logic**: Smart prediction for next available trading day

## 📈 Performance Features

- **GPU Acceleration**: Automatic CUDA detection
- **Memory Efficient**: Optimized data processing
- **Robust Training**: Gradient clipping and learning rate scheduling
- **Model Persistence**: Saves best performing model

## 🛡️ Risk Management

- **Stop Loss Calculation**: Automatic stop loss levels
- **Risk-Reward Ratio**: Built-in risk assessment
- **Volatility Analysis**: Market volatility consideration
- **Conservative Targets**: Safe profit booking levels

## 🔧 Advanced Usage

### Custom Stock Analysis
```python
# Analyze specific stock
predictor = NextDayTradingPredictor("HDFCBANK")
if predictor.fetch_data():
    predictions = predictor.predict_next_day()
    signals = predictor.generate_trading_signals(predictions)
    predictor.display_trading_recommendations(predictions, signals)
```

### Model Customization
```python
# Custom model parameters
predictor = NextDayTradingPredictor(
    ticker="TCS",
    seq_length=45,      # Longer sequence
    hidden_dim=256,     # Larger model
    num_layers=4        # Deeper network
)
```

## 📋 Requirements.txt
```
yfinance>=0.2.18
torch>=2.0.0
numpy>=1.21.0
pandas>=1.3.0
matplotlib>=3.5.0
scikit-learn>=1.0.0
pytz>=2021.3
```

## ⚠️ Disclaimer

> **Important**: This tool is for educational and research purposes only. Stock market investments carry inherent risks. Always:
> - Do your own research
> - Consult financial advisors
> - Never invest more than you can afford to lose
> - Past performance doesn't guarantee future results

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests, report bugs, or suggest features.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Omdeepb69/Intraday_predictor_goo/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Omdeepb69/Intraday_predictor_goo/discussions)
- **Email**: Your support email here

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=Omdeepb69/Intraday_predictor_goo&type=Date)](https://star-history.com/#Omdeepb69/Intraday_predictor_goo&Date)

---

**Made with ❤️ for Indian Stock Market Traders**

*Happy Trading! 📈💰*
