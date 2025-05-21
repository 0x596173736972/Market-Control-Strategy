
# 📈 MarketControl Strategy

## Description
MarketControl is an automated trading strategy built for **TradingView Pine Script v6**. It analyzes market structure by calculating the balance between buying and selling forces using a combination of technical factors including:

- Candlestick size and shape  
- Volume analysis  
- Detection of chart patterns (Three White Soldiers, Three Black Crows, Engulfing, Hammers, Dojis)  
- Pivot points (swing high/low)  
- Trend analysis via moving average and slope calculation  

## Features

### Market Control Indicator
- Real-time calculation of buyer and seller scores  
- Trend change detection  
- Market control visualization via background color changes  
- Identification of specific chart formations (score bonus)  

### Trading Signals
- Long/Short entry signal generation  
- Pattern confirmation for signal reinforcement  
- Automatic stop loss and take profit level calculation  
- Auto-close of positions on opposite signal  

### Filters and Risk Management
- Configurable time filter (trade only during specified hours)  
- Trend filter based on moving average slope  
- Price/MA position filter  
- Stop loss based on pivot levels  
- Customizable take profit / stop loss ratio  
- Auto-close positions on signal reversal  

### Visualization
- Information tables showing current scores and position  
- Display of stop loss and take profit levels  
- Marking of key chart patterns  
- Arrows for entry signals  
- Moving average with slope-based coloring  
- Detected pivot point display  
- Trend slope and price/MA position info table  

## How to Use

1. Copy the Pine Script code into the TradingView Pine Script editor  
2. Adjust the parameters to fit your preferences:
   - Indicator settings (analysis period, factor weights)
   - Trading settings (time filters, TP/SL ratio)
3. Apply the script to your chart  
4. Enable the strategy in the "Strategy Tester" tab to backtest or trade live  

## Customizable Parameters

### Indicator
- `lookbackPeriod`: Analysis period for score calculation (default: 2)  
- `volumeWeight`: Weight of volume in score (default: 2.5)  
- `bodySizeWeight`: Weight of candlestick body size (default: 2)  
- `wickWeight`: Weight of candlestick wicks (default: 0.8)  
- `closePosWeight`: Weight of closing position (default: 2)  

### Trading
- `startHour` / `endHour`: Trading time range (UTC+3)  
- `timeFrameFilter`: Enable/disable time filter  
- `swingPeriod`: Period for detecting swing highs/lows (default: 5)  
- `tpRatio`: Take profit / stop loss ratio (default: 1.5)  

### Trend Filter
- `maPeriod`: Moving average period (default: 50)  
- `slopePeriod`: Slope calculation period (default: 14)  
- `minAbsSlope`: Minimum slope in % (default: 0.15)  
- `useMAFilter`: Enable/disable slope filter  
- `useMACrossFilter`: Enable/disable price/MA position filter  

---

## 📊 Optimal Parameters – Trading Strategy

These settings have been tested and optimized for better performance.

### ⚙️ Risk Management

| Parameter                    | Value |
|-----------------------------|-------|
| Swing High/Low Period       | `5`   |
| TP/SL Ratio                 | `2`   |

---

### 📈 Trend Filters

| Parameter                          | Value  |
|-----------------------------------|--------|
| Moving Average Period             | `11`   |
| Slope Calculation Period          | `14`   |
| Minimum Slope (%)                 | `0.006`|
| Enable Slope Filter               | ✅     |
| Enable Price/MA Position Filter  | ✅     |

---

### 🕯️ Candlestick Score Weights

| Component                         | Weight |
|----------------------------------|--------|
| Volume Importance                | `2.5`  |
| Candle Body Size Importance      | `2`    |
| Wick Importance                  | `1.3`  |
| Close Position Importance        | `2`    |

---

### ⏰ Time Filters

| Parameter                   | Value |
|----------------------------|-------|
| Enable Time Filter         | ❌     |
| Start Hour (UTC+3)         | `9`   |
| End Hour (UTC+3)           | `19`  |

---

## Installation

1. Open TradingView and access the Pine Script Editor  
2. Create a new script and paste the code  
3. Save and apply it to your desired chart  

---

## Backtesting Results

The strategy showed **exceptional performance** in backtesting on the 4H candlestick chart of Gold futures with the following results:

- **Total Profit**: +2,315,540 USD (+226.20%)  
- **Max Drawdown**: 215,340 USD (6.59%)  
- **Total Trades**: 496  
- **Winning Trades**: 39.52% (196/300)  
- **Profit Factor**: 1.982  

### Performance Details

- **Net Profit**: +2,238,140 USD (+223.81%)  
- **Net Long Profit**: +1,694,800 USD (+169.48%)  
- **Net Short Profit**: +543,340 USD (+54.33%)  
- **Gross Profit**: 4,518,160 USD (451.82%)  
- **Gross Loss**: 2,280,020 USD (228.00%)  
- **Commissions Paid**: 19,860 USD  

### Risk Metrics

- **Sharpe Ratio**: 0.852  
- **Sortino Ratio**: 3.94  
- **Overall Profit Factor**: 1.982  
- **Long Profit Factor**: 2.733  
- **Short Profit Factor**: 1.417

These results indicate a **highly efficient strategy** with strong risk control, as evidenced by a low max drawdown (6.59%) versus high total return (226.20%).

---

## Important Notes

- Designed to work on various timeframes, but performance may vary based on instrument and trading horizon  
- It is strongly recommended to backtest the strategy before using it live  
- Default parameters may require adjustment based on your trading style and assets  
- Trend filter significantly improves signal quality by avoiding trades in unclear market directions  
- Price/MA filter helps avoid counter-trend trades  

**Disclaimer**: This script is provided for educational purposes only. Trading involves significant risk and this script does not constitute financial advice.
