---
tags: [key-concept]
aliases: [Hằng số san bằng]
---
# Smoothing Constant

**Smoothing Constant** (Hằng số san bằng, α) là trọng số trong exponential smoothing, quyết định mức phản ứng với dữ liệu mới.

## Giải thích
- Ft+1 = α × At + (1 - α) × Ft, với 0 < α < 1.
- α lớn (gần 1): phản ứng nhanh với thay đổi, nhưng nhạy cảm với nhiễu.
- α nhỏ (gần 0): forecast ổn định hơn, nhưng chậm phản ứng.
- Chọn α tối ưu bằng cách minimize MAD hoặc MSE trên dữ liệu lịch sử.

## Liên kết
- [[Time-Series Methods]]
- [[Trend]]
- [[MAD]]
- [[MAPE]]
