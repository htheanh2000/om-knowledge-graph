---
tags: [key-concept, chapter-13, forecasting]
aliases: [Moving Average, Trung bình trượt, Trung bình di động, MA, Simple Moving Average]
---
# Moving Average

## Định nghĩa (Definition)
**Moving Average** (Trung bình trượt) là phương pháp [[Forecasting|dự báo]] chuỗi thời gian đơn giản nhất, tính **trung bình cộng** nhu cầu thực tế của **n kỳ gần nhất** để dự báo cho kỳ tiếp theo.

## Giải thích chi tiết (Detailed Explanation)

### Ý tưởng:
- Lấy n giá trị gần nhất → tính trung bình → đó là dự báo
- Mỗi kỳ mới: bỏ giá trị cũ nhất, thêm giá trị mới nhất → "trượt" (moving)

### Cách chọn n (số kỳ):
- **n lớn (ví dụ 12 tháng):** Dự báo ổn định, san phẳng biến động, nhưng **chậm phản ứng** với thay đổi
- **n nhỏ (ví dụ 3 tháng):** Phản ứng **nhanh** hơn, nhưng dao động nhiều hơn

### Ưu điểm:
- Rất dễ hiểu và tính toán
- Phù hợp khi nhu cầu **tương đối ổn định** (không có trend rõ rệt)

### Nhược điểm:
- Tất cả n kỳ có **trọng số bằng nhau** (kỳ gần nhất = kỳ xa nhất)
- **Chậm phản ứng** khi nhu cầu thay đổi đột ngột
- Cần lưu trữ n giá trị
- Không xử lý được trend hay seasonality

### Biến thể: Weighted Moving Average (Trung bình trượt có trọng số)
- Gán trọng số khác nhau cho từng kỳ
- Kỳ gần hơn → trọng số lớn hơn
- Linh hoạt hơn Simple Moving Average

### So sánh với [[Exponential Smoothing]]:
| Moving Average | Exponential Smoothing |
|---|---|
| Trọng số bằng nhau | Trọng số giảm dần |
| Cần lưu n kỳ | Chỉ cần F(t) và A(t) |
| Đơn giản, trực quan | Phức tạp hơn một chút |
| Chậm phản ứng hơn | Linh hoạt hơn (tùy α) |

## Ví dụ thực tế (Real-world Example)
**Cửa hàng bán áo thun dự báo nhu cầu tháng 7 (3-month MA):**

| Tháng | Nhu cầu thực |
|-------|-------------|
| Tháng 1 | 100 |
| Tháng 2 | 120 |
| Tháng 3 | 110 |
| Tháng 4 | 130 |
| Tháng 5 | 125 |
| Tháng 6 | 140 |

**Dự báo tháng 7 (n=3):**
$$F_7 = \frac{A_4 + A_5 + A_6}{3} = \frac{130 + 125 + 140}{3} = \frac{395}{3} = 131.7 ≈ 132$$

**Nếu dùng n=5:**
$$F_7 = \frac{A_2 + A_3 + A_4 + A_5 + A_6}{5} = \frac{120+110+130+125+140}{5} = 125$$

→ n=3 cho dự báo cao hơn (132) vì phản ứng nhanh với xu hướng tăng gần đây
→ n=5 cho dự báo thấp hơn (125) vì bao gồm cả tháng 2 và 3 thấp hơn

## Mối liên hệ (Relationships)
- Thuộc về: [[Forecasting]] (Quantitative / Time Series method)
- So sánh với: [[Exponential Smoothing]]
- Phục vụ: [[Demand Management]], [[Sales and Operations Planning (S&OP)]]
- Ảnh hưởng đến: [[Inventory]], [[Safety Stock]]
- Thuộc chương: Chapter 13 — Forecasting

## Công thức (Formula)
**Simple Moving Average:**
$$F_{t+1} = \frac{A_t + A_{t-1} + ... + A_{t-n+1}}{n} = \frac{\sum_{i=0}^{n-1} A_{t-i}}{n}$$

**Weighted Moving Average:**
$$F_{t+1} = w_1 A_t + w_2 A_{t-1} + ... + w_n A_{t-n+1}$$

Trong đó:
- $F_{t+1}$ = Dự báo cho kỳ tiếp theo
- $A_t$ = Nhu cầu thực tế kỳ t
- n = Số kỳ tính trung bình
- $w_i$ = Trọng số (tổng $\sum w_i = 1$)
