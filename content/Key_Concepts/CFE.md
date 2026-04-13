---
tags: [key-concept]
aliases: [Cumulative Sum of Forecast Errors, Tổng tích lũy sai số dự báo]
---
# CFE

**CFE** (Cumulative Sum of Forecast Errors - Tổng tích lũy sai số dự báo) là tổng các sai số dự báo qua các kỳ.

## Giải thích
- CFE = Σ(Actual - Forecast). Dương = under-forecast, Âm = over-forecast.
- CFE gần 0 cho thấy dự báo không thiên lệch (unbiased).
- Dùng tracking signal = CFE / MAD để phát hiện bias; |TS| > 4 cần điều chỉnh.

## Liên kết
- [[MAD]]
- [[MAPE]]
- [[Time-Series Methods]]
- [[Demand Forecasting]]
