---
tags: [key-concept, chapter-8, quality-improvement, lean]
aliases: [Just-in-Time, JIT, Đúng lúc, Sản xuất đúng lúc, Sản xuất kịp thời]
---
# Just-in-Time (JIT)

## Định nghĩa (Definition)
**Just-in-Time (JIT)** (Đúng lúc) là triết lý sản xuất trong [[Lean Systems]] nhấn mạnh việc sản xuất **đúng sản phẩm, đúng số lượng, đúng lúc cần** — không sớm hơn, không muộn hơn, không nhiều hơn, không ít hơn.

## Giải thích chi tiết (Detailed Explanation)

### Ý tưởng cốt lõi:
- **Tồn kho = Lãng phí** (và che giấu vấn đề)
- Hình ảnh kinh điển: "Mực nước và đá ngầm"
  - Mực nước = [[Inventory|Tồn kho]]
  - Đá ngầm = Các vấn đề (máy hỏng, chất lượng kém, nhà cung cấp chậm)
  - Hạ mực nước (giảm tồn kho) → lộ ra đá ngầm → buộc phải giải quyết vấn đề

### Yêu cầu để JIT hoạt động:
1. **Pull System ([[Kanban]]):** Chỉ sản xuất khi có tín hiệu nhu cầu
2. **Small Lot Sizes (Lô nhỏ):** Sản xuất từng lô nhỏ, chuyển đổi nhanh
3. **Quick Setups (Chuyển đổi nhanh):** Giảm thời gian setup máy (SMED — Single-Minute Exchange of Dies)
4. **Uniform Plant Loading:** Sản xuất đều đặn, ổn định (Heijunka)
5. **Nhà cung cấp tin cậy:** Giao hàng thường xuyên, đúng hẹn, chất lượng cao
6. **Chất lượng tại nguồn:** [[Total Quality Management (TQM)]] — không để lỗi đi qua

### Lợi ích:
- Giảm [[Inventory|tồn kho]] → giảm chi phí lưu kho, giảm đọng vốn
- Phát hiện lỗi nhanh hơn → giảm chi phí sửa lỗi
- Thời gian sản xuất (lead time) ngắn hơn
- Linh hoạt hơn khi nhu cầu thay đổi

### Rủi ro:
- Nếu nhà cung cấp giao trễ → **dây chuyền dừng** (không có tồn kho dự phòng)
- Cần mối quan hệ rất chặt chẽ với nhà cung cấp
- Thiên tai, đại dịch (COVID-19) → chuỗi cung ứng JIT bị gián đoạn nghiêm trọng

## Ví dụ thực tế (Real-world Example)
**Toyota:**
- Nhà cung cấp giao linh kiện **mỗi vài giờ** (không phải mỗi tuần)
- Tồn kho trong nhà máy chỉ đủ cho **vài giờ sản xuất**
- Kết quả: Toyota cần ít vốn lưu động hơn đối thủ rất nhiều

**Ví dụ đời thường:**
- **Không JIT:** Đi chợ mua thức ăn cho cả tuần → tủ lạnh đầy, một số thức ăn hỏng
- **JIT:** Mua thức ăn mỗi ngày vừa đủ nấu → tươi ngon, không lãng phí

**COVID-19 và JIT:**
- Nhiều nhà máy ô tô thiếu chip bán dẫn vì không có tồn kho dự phòng
- Bài học: JIT cần kết hợp với quản lý rủi ro chuỗi cung ứng

## Mối liên hệ (Relationships)
- Thuộc về: [[Lean Systems]]
- Sử dụng: [[Kanban]] (hệ thống kéo)
- Giảm: [[Inventory]] (đặc biệt cycle inventory)
- Yêu cầu: [[Total Quality Management (TQM)]] (chất lượng tại nguồn)
- Liên quan: [[Supply Chain]] (cần nhà cung cấp đáng tin cậy)
- Đối lập với: tích trữ [[Safety Stock]] lớn
- Thuộc chương: Chapter 8 — Lean Systems

## Công thức (Formula)
Không có công thức riêng cho JIT. Các chỉ số liên quan:
- **Inventory Turns** = COGS / Average Inventory (càng cao càng tốt với JIT)
- **Days of Supply** = Average Inventory / Daily Usage (JIT hướng đến càng ít ngày càng tốt)
