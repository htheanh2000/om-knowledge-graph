---
tags: [key-concept, forecasting, chapter-11]
aliases: [Forecast Error, Sai số dự báo, Prediction Error]
---
# Forecast Error

## Định nghĩa (Definition)
**Forecast Error** (Sai số dự báo) là sự **chênh lệch** giữa giá trị thực tế và giá trị dự báo: **e_t = A_t - F_t**

## Giải thích (Explanation)
Các thước đo sai số dự báo phổ biến:

| Thước đo | Công thức | Đặc điểm |
|---|---|---|
| **CFE** | Sum(e_t) | Đo bias (thiên lệch), có thể âm/dương |
| **MAD** | Sum(abs(e_t)) / n | Sai số tuyệt đối trung bình, dễ hiểu |
| **MSE** | Sum(e_t^2) / n | Phạt nặng sai số lớn |
| **MAPE** | Sum(abs(e_t)/A_t x 100) / n | Sai số phần trăm, so sánh được giữa các chuỗi |

Ý nghĩa:
- **CFE gần 0** → dự báo không bị bias (tốt)
- **MAD nhỏ** → dự báo chính xác
- **Tracking signal** = CFE/MAD → nằm trong +-4 là chấp nhận được

Sai số dự báo ảnh hưởng trực tiếp đến [[Safety Stock]] — dự báo càng sai → cần Safety Stock càng lớn.

## Mối liên hệ (Relationships)
- Thuộc về: [[Forecasting]]
- Ảnh hưởng: [[Safety Stock]], [[Inventory Management]]
- Phương pháp: [[Moving Average]], [[Exponential Smoothing]]
- Liên quan: [[Demand Management]]
- Thuộc chương: Chapter 11 — Forecasting
