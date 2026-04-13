---
tags:
  - operations-management
  - forecasting
  - quantitative
aliases:
  - Hồi quy tuyến tính
  - Causal Forecasting
---

# Linear Regression

## Định nghĩa
**Hồi quy tuyến tính (Linear Regression)** là phương pháp dự báo nhân quả sử dụng mối quan hệ tuyến tính giữa biến phụ thuộc và biến độc lập.

## Công thức
$$y = a + bx$$
- $b = \frac{n\sum xy - \sum x \sum y}{n\sum x^2 - (\sum x)^2}$
- $a = \bar{y} - b\bar{x}$

## Giải thích
- Dùng khi có mối quan hệ nhân quả rõ ràng giữa biến (ví dụ: quảng cáo → doanh số)
- Hệ số tương quan $r$ đo mức độ tương quan tuyến tính
- Khác với time series: dự báo dựa trên biến giải thích, không chỉ thời gian

## Liên kết
- [[Forecasting]]
- [[Demand Patterns]]
- [[Moving Average]]
- [[Exponential Smoothing]]
