---
tags: [key-concept, chapter-5, quality-improvement]
aliases: [Statistical Process Control, SPC, Kiểm soát quy trình bằng thống kê, Kiểm soát quá trình thống kê]
---
# Statistical Process Control (SPC)

## Định nghĩa (Definition)
**Statistical Process Control (SPC)** (Kiểm soát quy trình bằng thống kê) là phương pháp sử dụng **biểu đồ kiểm soát (control charts)** và các công cụ thống kê để **giám sát và kiểm soát** quy trình, phát hiện biến thiên bất thường trước khi tạo ra sản phẩm lỗi.

## Giải thích chi tiết (Detailed Explanation)

### Hai loại biến thiên (Variation):
1. **Common Cause Variation (Biến thiên tự nhiên):**
   - Luôn tồn tại trong mọi quy trình
   - Ngẫu nhiên, nhỏ, không thể loại bỏ hoàn toàn
   - Ví dụ: Nhiệt độ phòng dao động nhẹ, rung động nhỏ của máy

2. **Assignable Cause Variation (Biến thiên có nguyên nhân xác định):**
   - Bất thường, có nguyên nhân cụ thể có thể tìm và loại bỏ
   - Ví dụ: Dao cụ bị mòn, nguyên liệu lô mới kém chất lượng, nhân viên mới chưa thạo

→ SPC giúp phân biệt hai loại này. Nếu chỉ có common cause → quy trình **trong kiểm soát (in control)**. Nếu có assignable cause → quy trình **ngoài kiểm soát (out of control)** → cần can thiệp!

### Control Charts (Biểu đồ kiểm soát):

#### Cấu trúc:
- **Center Line (CL):** Đường trung tâm = giá trị trung bình
- **Upper Control Limit (UCL):** Giới hạn kiểm soát trên = CL + 3σ
- **Lower Control Limit (LCL):** Giới hạn kiểm soát dưới = CL - 3σ

#### Các loại biểu đồ:
| Loại | Đo gì | Dữ liệu |
|------|--------|----------|
| **x̄-chart** | Trung bình mẫu | Biến liên tục |
| **R-chart** | Phạm vi (range) mẫu | Biến liên tục |
| **p-chart** | Tỷ lệ lỗi | Thuộc tính (đạt/không đạt) |
| **c-chart** | Số lỗi trên đơn vị | Thuộc tính (đếm lỗi) |

#### Dấu hiệu "ngoài kiểm soát":
- Điểm nằm ngoài UCL hoặc LCL
- 7 điểm liên tiếp cùng phía (trên hoặc dưới) CL
- Xu hướng tăng hoặc giảm liên tục
- Mẫu hình lặp lại (cyclic pattern)

## Ví dụ thực tế (Real-world Example)
**Nhà máy sản xuất lon bia Heineken:**
- Mỗi 30 phút, lấy mẫu 5 lon → cân trọng lượng
- Tính trung bình (x̄) và range (R) của mẫu
- Vẽ lên biểu đồ x̄ và R-chart
- Nếu điểm nào vượt giới hạn → **dừng máy, tìm nguyên nhân** (dao cụ mòn? nguyên liệu lỗi?)
- Nếu tất cả trong giới hạn → quy trình ổn định, tiếp tục sản xuất

## Mối liên hệ (Relationships)
- Công cụ của: [[Total Quality Management (TQM)]], [[Six Sigma]] (bước Control trong DMAIC)
- Liên quan đến: [[Continuous Improvement]]
- Hỗ trợ: [[Lean Systems]] (phát hiện lỗi sớm)
- Thuộc về: [[Competitive Priorities]] (Quality)
- Thuộc chương: Chapter 5 — Quality and Performance

## Công thức (Formula)

**x̄-chart (Biểu đồ trung bình):**
$$UCL_{\bar{x}} = \bar{\bar{x}} + A_2 \bar{R}$$
$$LCL_{\bar{x}} = \bar{\bar{x}} - A_2 \bar{R}$$

**R-chart (Biểu đồ phạm vi):**
$$UCL_R = D_4 \bar{R}$$
$$LCL_R = D_3 \bar{R}$$

**p-chart (Biểu đồ tỷ lệ lỗi):**
$$UCL_p = \bar{p} + 3\sqrt{\frac{\bar{p}(1-\bar{p})}{n}}$$
$$LCL_p = \bar{p} - 3\sqrt{\frac{\bar{p}(1-\bar{p})}{n}}$$

Trong đó:
- $\bar{\bar{x}}$ = trung bình của các trung bình mẫu
- $\bar{R}$ = trung bình range
- $A_2, D_3, D_4$ = hằng số tra bảng (phụ thuộc cỡ mẫu n)
- $\bar{p}$ = tỷ lệ lỗi trung bình
