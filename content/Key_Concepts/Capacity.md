---
tags: [key-concept, chapter-6, capacity-constraints]
aliases: [Capacity, Năng lực sản xuất, Công suất, Production Capacity]
---
# Capacity

## Định nghĩa (Definition)
**Capacity** (Năng lực sản xuất/Công suất) là **lượng đầu ra tối đa** mà một [[Process|quy trình]] có thể sản xuất trong một khoảng thời gian nhất định, trong điều kiện hoạt động bình thường.

## Giải thích chi tiết (Detailed Explanation)

### Ba khái niệm năng lực:

#### 1. Design Capacity (Công suất thiết kế)
- Sản lượng tối đa **lý thuyết** trong điều kiện lý tưởng
- Ví dụ: Nhà máy thiết kế sản xuất 1000 áo/ngày (chạy 24/24, không dừng)

#### 2. Effective Capacity (Công suất hiệu dụng)
- Sản lượng tối đa **thực tế có thể đạt** khi tính đến bảo trì, nghỉ ngơi, setup
- Luôn **nhỏ hơn** Design Capacity
- Ví dụ: Tính đến bảo trì 2h/ngày, nghỉ trưa, setup → 750 áo/ngày

#### 3. Actual Output (Sản lượng thực tế)
- Sản lượng **thực sự sản xuất** được
- Có thể thấp hơn Effective Capacity do máy hỏng, thiếu nguyên liệu, sản phẩm lỗi
- Ví dụ: Hôm nay máy hỏng 1h, 20 áo bị lỗi → thực tế chỉ 680 áo

### Hai chỉ số đo lường:

**Utilization (Hệ số sử dụng):**
- So sánh sản lượng thực tế với **công suất thiết kế**
- Cho biết "dùng bao nhiêu % năng lực tối đa?"

**Efficiency (Hiệu suất):**
- So sánh sản lượng thực tế với **công suất hiệu dụng**
- Cho biết "hoạt động tốt đến đâu so với mức có thể đạt?"

### Chiến lược năng lực:
- **Capacity Lead Strategy:** Mở rộng năng lực TRƯỚC khi nhu cầu tăng → rủi ro dư thừa
- **Capacity Lag Strategy:** Mở rộng SAU khi nhu cầu đã tăng → rủi ro mất khách
- **Capacity Match Strategy:** Mở rộng từ từ theo nhu cầu → cân bằng

### Liên quan đến quy mô:
- Mở rộng quá mức → [[Diseconomies of Scale]]
- Mở rộng hợp lý → [[Economies of Scale]]

## Ví dụ thực tế (Real-world Example)
**Nhà hàng lẩu:**
- **Design Capacity:** 100 bàn × 3 lượt/ngày = 300 lượt khách/ngày
- **Effective Capacity:** Tính thực tế (giờ vắng, dọn bàn, nghỉ lễ) = 200 lượt/ngày
- **Actual Output:** Hôm nay chỉ phục vụ 150 lượt (trời nóng, ít khách ăn lẩu)
- **Utilization** = 150/300 = 50%
- **Efficiency** = 150/200 = 75%

## Mối liên hệ (Relationships)
- Liên quan đến: [[Bottleneck]] (giới hạn năng lực), [[Theory of Constraints (TOC)]]
- Ảnh hưởng bởi: [[Economies of Scale]], [[Diseconomies of Scale]]
- Hỗ trợ quyết định: [[Operations Strategy]], [[Forecasting]]
- Kế hoạch: [[Sales and Operations Planning (S&OP)]]
- Cải tiến qua: [[Lean Systems]], [[Continuous Improvement]]
- Thuộc chương: Chapter 6 — Capacity Planning

## Công thức (Formula)
**Utilization (Hệ số sử dụng):**
$$Utilization = \frac{Actual\ Output}{Design\ Capacity} \times 100\%$$

**Efficiency (Hiệu suất):**
$$Efficiency = \frac{Actual\ Output}{Effective\ Capacity} \times 100\%$$

**Ví dụ:**
- Design Capacity = 1000 đơn vị/tuần
- Effective Capacity = 800 đơn vị/tuần
- Actual Output = 720 đơn vị/tuần
- Utilization = 720/1000 = **72%**
- Efficiency = 720/800 = **90%**
