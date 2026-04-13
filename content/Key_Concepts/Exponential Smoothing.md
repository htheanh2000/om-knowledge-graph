---
tags: [key-concept, chapter-13, forecasting]
aliases: [Exponential Smoothing, San bằng mũ, San bằng hàm mũ, ES]
---
# Exponential Smoothing

## Định nghĩa (Definition)
**Exponential Smoothing** (San bằng mũ) là phương pháp [[Forecasting|dự báo]] chuỗi thời gian, trong đó dự báo mới là **bình quân gia quyền** giữa nhu cầu thực tế gần nhất và dự báo kỳ trước, với trọng số giảm dần theo hàm mũ cho các dữ liệu cũ hơn.

## Giải thích chi tiết (Detailed Explanation)

### Ý tưởng cốt lõi:
- Dữ liệu **gần đây hơn** nên có **ảnh hưởng lớn hơn** đến dự báo
- Thay vì tính trung bình đều (như [[Moving Average]]), Exponential Smoothing cho trọng số giảm dần

### Công thức cơ bản:
$$F_{t+1} = \alpha A_t + (1-\alpha) F_t$$

Hay viết cách khác:
$$F_{t+1} = F_t + \alpha (A_t - F_t)$$

→ Dự báo mới = Dự báo cũ + α × (Sai số dự báo)

### Hệ số α (Alpha) — Smoothing Constant:
- Giá trị từ **0 đến 1**
- **α cao (gần 1):** Phản ứng NHANH với thay đổi gần đây, nhưng dao động nhiều
- **α thấp (gần 0):** Phản ứng CHẬM, dự báo ổn định hơn nhưng chậm bắt kịp xu hướng

| α | Đặc điểm | Phù hợp khi |
|---|----------|-------------|
| 0.1 - 0.2 | Rất ổn định, chậm thay đổi | Nhu cầu ổn định, ít biến động |
| 0.3 - 0.5 | Cân bằng | Nhu cầu có biến động vừa |
| 0.6 - 0.9 | Phản ứng nhanh, dao động | Nhu cầu thay đổi nhanh, cần bắt kịp |

### So sánh với [[Moving Average]]:
| Exponential Smoothing | Moving Average |
|---|---|
| Chỉ cần lưu F(t) và A(t) | Cần lưu n kỳ dữ liệu |
| Trọng số giảm dần (gần > xa) | Trọng số bằng nhau cho n kỳ |
| 1 tham số (α) | 1 tham số (n) |
| Tính toán đơn giản hơn | Dễ hiểu hơn |

### Biến thể nâng cao:
- **Double Exponential Smoothing (Holt's):** Xử lý được **xu hướng (trend)**
- **Triple Exponential Smoothing (Holt-Winters):** Xử lý cả **xu hướng + mùa vụ**

## Ví dụ thực tế (Real-world Example)
**Cửa hàng bán trà sữa dự báo doanh số tuần tới:**

| Tuần | Nhu cầu thực (A) | Dự báo (F) với α=0.3 |
|------|-------------------|----------------------|
| 1 | 200 | 200 (khởi đầu) |
| 2 | 220 | 200 |
| 3 | 180 | 200 + 0.3×(220-200) = **206** |
| 4 | 240 | 206 + 0.3×(180-206) = **198.2** |
| 5 | ? | 198.2 + 0.3×(240-198.2) = **210.7** |

→ Dự báo tuần 5 = **211 ly** (làm tròn)

**Nếu dùng α = 0.7 (phản ứng nhanh hơn):**
- Tuần 3: 200 + 0.7×(220-200) = **214**
- Tuần 4: 214 + 0.7×(180-214) = **190.2**
- Tuần 5: 190.2 + 0.7×(240-190.2) = **225.1**

→ α = 0.7 phản ứng mạnh hơn với tuần 4 = 240 → dự báo 225 thay vì 211

## Mối liên hệ (Relationships)
- Thuộc về: [[Forecasting]] (Quantitative / Time Series method)
- So sánh với: [[Moving Average]]
- Phục vụ: [[Demand Management]], [[Sales and Operations Planning (S&OP)]]
- Ảnh hưởng đến: [[Inventory]], [[Safety Stock]]
- Thuộc chương: Chapter 13 — Forecasting

## Công thức (Formula)
**Simple Exponential Smoothing:**
$$F_{t+1} = \alpha A_t + (1-\alpha) F_t$$

Trong đó:
- $F_{t+1}$ = Dự báo cho kỳ tiếp theo
- $A_t$ = Nhu cầu thực tế kỳ hiện tại
- $F_t$ = Dự báo kỳ hiện tại
- $\alpha$ = Hệ số san bằng (0 < α < 1)

**Khai triển cho thấy trọng số giảm dần:**
$$F_{t+1} = \alpha A_t + \alpha(1-\alpha)A_{t-1} + \alpha(1-\alpha)^2 A_{t-2} + ...$$

→ Trọng số: α, α(1-α), α(1-α)², ... → giảm theo **hàm mũ** → "Exponential" Smoothing!
