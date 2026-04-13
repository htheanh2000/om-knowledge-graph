---
tags: [key-concept, chapter-5, quality-improvement]
aliases: [Six Sigma, 6 Sigma, Sáu Sigma]
---
# Six Sigma

## Định nghĩa (Definition)
**Six Sigma** là phương pháp luận cải tiến chất lượng có hệ thống, nhằm **giảm biến thiên (variation)** trong quy trình xuống mức cực thấp: chỉ **3.4 lỗi trên 1 triệu cơ hội** (3.4 DPMO — Defects Per Million Opportunities).

## Giải thích chi tiết (Detailed Explanation)

### Tại sao gọi là "Six Sigma"?
- **Sigma (σ)** là ký hiệu thống kê chỉ **độ lệch chuẩn** (standard deviation)
- 6σ nghĩa là giới hạn quy cách nằm cách trung bình **6 độ lệch chuẩn** → xác suất lỗi cực nhỏ
- Mức sigma càng cao → càng ít lỗi:

| Mức Sigma | DPMO | % Không lỗi |
|-----------|------|-------------|
| 1σ | 691,462 | 30.9% |
| 2σ | 308,538 | 69.1% |
| 3σ | 66,807 | 93.3% |
| 4σ | 6,210 | 99.4% |
| 5σ | 233 | 99.98% |
| **6σ** | **3.4** | **99.99966%** |

### Phương pháp DMAIC:
Quy trình 5 bước để cải tiến quy trình hiện tại:

1. **D — Define (Xác định):** Xác định vấn đề, mục tiêu, phạm vi dự án, tiếng nói khách hàng (VOC)
2. **M — Measure (Đo lường):** Thu thập dữ liệu, đo lường hiện trạng quy trình, xác định baseline
3. **A — Analyze (Phân tích):** Tìm nguyên nhân gốc rễ (root cause) bằng thống kê
4. **I — Improve (Cải tiến):** Đề xuất và thực hiện giải pháp, thử nghiệm
5. **C — Control (Kiểm soát):** Duy trì kết quả cải tiến, sử dụng [[Statistical Process Control (SPC)|SPC]]

### Hệ thống Belt (Đai):
- **Champion:** Lãnh đạo cấp cao hỗ trợ dự án
- **Master Black Belt:** Chuyên gia đào tạo và tư vấn
- **Black Belt:** Lãnh đạo dự án toàn thời gian
- **Green Belt:** Thành viên dự án bán thời gian
- **Yellow Belt:** Nhân viên được đào tạo cơ bản

### So sánh với [[Total Quality Management (TQM)]]:
Six Sigma **cụ thể** và **dựa trên dữ liệu** hơn TQM. TQM là triết lý rộng, Six Sigma là phương pháp luận chặt chẽ với mục tiêu đo lường được.

## Ví dụ thực tế (Real-world Example)
**Motorola** — Nơi sinh ra Six Sigma (1986):
- Giảm lỗi sản xuất chip điện thoại
- Tiết kiệm $16 tỷ trong 10 năm đầu

**General Electric (GE) — Jack Welch:**
- Áp dụng Six Sigma toàn công ty từ 1995
- Tiết kiệm $12 tỷ trong 5 năm

**Ví dụ đơn giản:**
Một nhà máy sản xuất chai nước đóng thể tích 500ml:
- Mức 3σ: Có ~66,807 chai/triệu chai bị sai thể tích → ~67 chai lỗi
- Mức 6σ: Chỉ 3.4 chai/triệu chai bị sai thể tích → gần như hoàn hảo

## Mối liên hệ (Relationships)
- Liên quan đến: [[Total Quality Management (TQM)]], [[Statistical Process Control (SPC)]]
- Kết hợp với: [[Lean Systems]] → "Lean Six Sigma"
- Sử dụng: [[Continuous Improvement]] (DMAIC là dạng cải tiến có cấu trúc)
- Thuộc về: [[Competitive Priorities]] (Quality)
- Thuộc chương: Chapter 5 — Quality and Performance

## Công thức (Formula)
**DPMO (Defects Per Million Opportunities):**
$$DPMO = \frac{Số\ lỗi}{Số\ cơ\ hội\ lỗi} \times 1,000,000$$

**Process Capability (Năng lực quy trình):**
$$C_p = \frac{USL - LSL}{6\sigma}$$

Trong đó:
- USL = Upper Specification Limit (Giới hạn trên)
- LSL = Lower Specification Limit (Giới hạn dưới)
- σ = Độ lệch chuẩn của quy trình
