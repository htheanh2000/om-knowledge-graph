---
tags: [key-concept, chapter-12, inventory]
aliases: [Safety Stock, Tồn kho an toàn, Buffer Stock, Tồn kho dự phòng]
---
# Safety Stock

## Định nghĩa (Definition)
**Safety Stock** (Tồn kho an toàn) là lượng [[Inventory|tồn kho]] **dự phòng** giữ thêm ngoài nhu cầu dự kiến, nhằm **bảo vệ** doanh nghiệp khỏi tình trạng hết hàng (stockout) do **biến động nhu cầu** hoặc **thời gian giao hàng không chắc chắn**.

## Giải thích chi tiết (Detailed Explanation)

### Tại sao cần Safety Stock?
Trong thực tế, hai yếu tố luôn biến động:
1. **Nhu cầu khách hàng** — có thể tăng đột ngột (ví dụ: nắng nóng → nhu cầu kem tăng)
2. **Thời gian giao hàng** — nhà cung cấp có thể giao trễ (ví dụ: tắc cảng, thiên tai)

→ Nếu không có Safety Stock → **hết hàng → mất doanh thu → mất khách hàng**

### Yếu tố quyết định mức Safety Stock:
1. **Mức phục vụ mong muốn (Service Level):**
   - 90% → chấp nhận 10% khả năng hết hàng
   - 95% → chấp nhận 5% khả năng hết hàng (z = 1.65)
   - 99% → chấp nhận 1% khả năng hết hàng (z = 2.33)
   - Service Level cao hơn → Safety Stock lớn hơn → chi phí cao hơn

2. **Biến thiên nhu cầu (σ_d):** Nhu cầu càng biến động → Safety Stock càng lớn

3. **Thời gian giao hàng (L):** Lead time càng dài → Safety Stock càng lớn

4. **Biến thiên lead time (σ_L):** Lead time càng không ổn định → Safety Stock càng lớn

### Trade-off:
- Safety Stock **quá nhiều** → Chi phí giữ hàng cao, đọng vốn
- Safety Stock **quá ít** → Rủi ro hết hàng, mất khách
- Cần cân bằng dựa trên **Service Level** phù hợp với chiến lược

### Phân loại qua [[ABC Analysis]]:
- **Loại A** (giá trị cao): Service level cao → Safety Stock tính toán kỹ
- **Loại C** (giá trị thấp): Có thể giữ Safety Stock lớn hơn vì chi phí thấp

## Ví dụ thực tế (Real-world Example)
**Nhà thuốc:**
- Thuốc cảm cúm: Nhu cầu trung bình 50 hộp/tuần, σ_d = 10 hộp
- Lead time: 1 tuần (ổn định)
- Service level mong muốn: 95% (z = 1.65)

$$Safety\ Stock = z \times \sigma_d \times \sqrt{L} = 1.65 \times 10 \times \sqrt{1} = 16.5 ≈ 17\ hộp$$

→ Giữ thêm **17 hộp** ngoài nhu cầu trung bình → 95% không bao giờ hết hàng

**Trước mùa COVID:**
Nhu cầu khẩu trang biến thiên cực cao (σ_d rất lớn) → Safety Stock cần rất lớn → nhiều nhà thuốc vẫn hết hàng vì không dự trù đủ.

## Mối liên hệ (Relationships)
- Thuộc về: [[Inventory]] (một trong 4 loại tồn kho)
- Ảnh hưởng đến: [[Reorder Point]] (R = d×L + Safety Stock)
- Tối ưu kết hợp: [[Economic Order Quantity (EOQ)]]
- Dự báo biến động: [[Forecasting]], [[Demand Management]]
- Phân loại ưu tiên: [[ABC Analysis]]
- [[Lean Systems]] hướng đến giảm Safety Stock bằng cách giảm biến thiên
- Thuộc chương: Chapter 12 — Inventory Management

## Công thức (Formula)
**Khi chỉ nhu cầu biến thiên (lead time cố định):**
$$Safety\ Stock = z \times \sigma_d \times \sqrt{L}$$

**Khi cả nhu cầu và lead time biến thiên:**
$$Safety\ Stock = z \times \sqrt{L \times \sigma_d^2 + d^2 \times \sigma_L^2}$$

Trong đó:
- z = Hệ số phân phối chuẩn (tra bảng theo Service Level)
- σ_d = Độ lệch chuẩn nhu cầu (trong 1 đơn vị thời gian)
- L = Lead time trung bình
- d = Nhu cầu trung bình (trong 1 đơn vị thời gian)
- σ_L = Độ lệch chuẩn lead time

**Bảng z thường dùng:**
| Service Level | z |
|---|---|
| 85% | 1.04 |
| 90% | 1.28 |
| 95% | 1.65 |
| 97.5% | 1.96 |
| 99% | 2.33 |
