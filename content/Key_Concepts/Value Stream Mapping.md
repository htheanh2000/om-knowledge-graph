---
tags: [key-concept, chapter-8, quality-improvement, lean]
aliases: [Value Stream Mapping, VSM, Bản đồ dòng giá trị, Sơ đồ dòng giá trị]
---
# Value Stream Mapping

## Định nghĩa (Definition)
**Value Stream Mapping (VSM)** (Bản đồ dòng giá trị) là công cụ trực quan trong [[Lean Systems]] dùng để **vẽ toàn bộ dòng chảy** của vật liệu và thông tin từ nhà cung cấp đến khách hàng, nhằm **phân biệt hoạt động tạo giá trị và không tạo giá trị** (lãng phí).

## Giải thích chi tiết (Detailed Explanation)

### Mục đích:
- Nhìn thấy **toàn cảnh** quy trình, không chỉ từng bước riêng lẻ
- Phát hiện **lãng phí** ẩn giấu (7 wastes trong [[Lean Systems]])
- Xác định [[Bottleneck|nút thắt cổ chai]]
- Tạo kế hoạch cải tiến có trọng tâm

### Hai bản đồ:
1. **Current State Map (Bản đồ hiện tại):** Mô tả quy trình đang hoạt động như thế nào — bao gồm cả lãng phí
2. **Future State Map (Bản đồ tương lai):** Mô tả quy trình lý tưởng sau khi loại bỏ lãng phí

### Các ký hiệu chính trong VSM:
- **Process box:** Mỗi công đoạn sản xuất
- **Data box:** Cycle time, changeover time, uptime
- **Inventory triangle:** Tồn kho giữa các công đoạn
- **Arrow (mũi tên):** Dòng chảy vật liệu và thông tin
- **Timeline:** Phân tích thời gian tạo giá trị vs không tạo giá trị

### Các bước thực hiện:
1. Chọn sản phẩm/dòng sản phẩm cần phân tích
2. Vẽ Current State Map — đi thực tế (gemba walk) để thu thập dữ liệu
3. Phân tích: Đâu là lãng phí? Đâu là [[Bottleneck]]?
4. Vẽ Future State Map — loại bỏ lãng phí, tạo dòng chảy liên tục
5. Lập kế hoạch hành động để chuyển từ hiện tại sang tương lai

### Chỉ số quan trọng:
- **Value-Added Time (VA):** Thời gian thực sự tạo giá trị
- **Non-Value-Added Time (NVA):** Thời gian lãng phí (chờ, vận chuyển, kiểm tra...)
- **VA Ratio** = VA Time / Total Lead Time × 100%
- Thực tế: VA Ratio thường chỉ **1-5%** → rất nhiều cơ hội cải tiến!

## Ví dụ thực tế (Real-world Example)
**Nhà máy sản xuất ghế gỗ:**
- **Current State:** Nguyên liệu gỗ chờ 3 ngày → Cắt (2 giờ) → Chờ 1 ngày → Lắp ráp (1 giờ) → Chờ 2 ngày → Sơn (30 phút) → Chờ 1 ngày → Giao hàng
- **Tổng Lead Time:** 7 ngày 3.5 giờ
- **VA Time:** 3.5 giờ
- **VA Ratio:** 3.5 / (7×24 + 3.5) ≈ **2%** → 98% thời gian là lãng phí!

- **Future State:** Giảm tồn kho giữa các công đoạn, áp dụng [[Kanban]], sắp xếp lại layout
- **Mục tiêu:** Lead Time giảm từ 7 ngày → 2 ngày

## Mối liên hệ (Relationships)
- Thuộc về: [[Lean Systems]]
- Công cụ phát hiện: [[Bottleneck]], lãng phí (7 wastes)
- Hỗ trợ: [[Continuous Improvement]], [[Just-in-Time (JIT)]]
- Liên quan đến: [[Kanban]] (cải tiến dòng chảy)
- Sử dụng trong: [[Six Sigma]] (bước Analyze)
- Thuộc chương: Chapter 8 — Lean Systems

## Công thức (Formula)
**VA Ratio (Tỷ lệ giá trị gia tăng):**
$$VA\ Ratio = \frac{Value\text{-}Added\ Time}{Total\ Lead\ Time} \times 100\%$$
