---
tags: [chapter-3, part1, quality, TQM, six-sigma, SPC, process-capability, ISO]
aliases: [Chất lượng và hiệu suất, Quality and Performance, OM Chapter 3]
---
# Chapter 3 - Quality and Performance

## Tổng quan (Overview)

Chương 3 tập trung vào [[Quality]] (Chất lượng) - một trong bốn [[Competitive Priorities]] quan trọng nhất. Chất lượng không chỉ là "sản phẩm tốt" mà là toàn bộ hệ thống quản lý nhằm đảm bảo sản phẩm và dịch vụ luôn đáp ứng hoặc vượt kỳ vọng của khách hàng.

Chương giới thiệu hai triết lý quản lý chất lượng hàng đầu: [[Total Quality Management]] (TQM) và [[Six Sigma]], cùng các công cụ thống kê như [[Statistical Process Control]] (SPC) và [[Process Capability]]. Ngoài ra, chương trình bày các tiêu chuẩn và giải thưởng chất lượng quốc tế như [[ISO 9001]] và [[Malcolm Baldrige National Quality Award]].

Hiểu chương này giúp bạn xây dựng hệ thống quản lý chất lượng toàn diện, phát hiện vấn đề trước khi chúng ảnh hưởng đến khách hàng, và liên tục cải tiến quy trình.

---

## Costs of Quality (Chi phí chất lượng)

### Định nghĩa (Definition)
[[Cost of Quality]] (COQ) là tổng chi phí liên quan đến việc đảm bảo chất lượng và chi phí phát sinh do chất lượng kém. COQ thường chiếm 20-30% doanh thu!

### Giải thích chi tiết

Có bốn loại chi phí chất lượng:

#### 1. [[Prevention Cost]] (Chi phí phòng ngừa)
Chi phí để NGĂN CHẶN lỗi xảy ra ngay từ đầu:
- Đào tạo nhân viên về chất lượng
- Thiết kế quy trình chống lỗi ([[Poka-Yoke]])
- Bảo trì phòng ngừa ([[Preventive Maintenance]])
- Đánh giá và chọn nhà cung cấp
- Lập kế hoạch chất lượng

#### 2. [[Appraisal Cost]] (Chi phí đánh giá / Thẩm định)
Chi phí để PHÁT HIỆN lỗi trước khi sản phẩm đến tay khách hàng:
- Kiểm tra nguyên vật liệu đầu vào
- Kiểm tra trong quá trình sản xuất ([[In-Process Inspection]])
- Kiểm tra sản phẩm cuối cùng
- Kiểm định thiết bị đo lường
- Thử nghiệm trong phòng lab

#### 3. [[Internal Failure Cost]] (Chi phí lỗi nội bộ)
Chi phí khi phát hiện lỗi TRƯỚC KHI sản phẩm đến khách hàng:
- Phế phẩm ([[Scrap]]) - phải bỏ đi
- Làm lại ([[Rework]]) - sửa sản phẩm lỗi
- Thời gian chờ do máy hỏng
- Giảm giá sản phẩm lỗi nhẹ

#### 4. [[External Failure Cost]] (Chi phí lỗi bên ngoài)
Chi phí khi khách hàng NHẬN ĐƯỢC sản phẩm lỗi - **ĐẮT NHẤT trong 4 loại**:
- Bảo hành ([[Warranty]])
- Thu hồi sản phẩm ([[Product Recall]])
- Kiện tụng, bồi thường
- Mất khách hàng, mất uy tín
- Xử lý khiếu nại

> **Quy tắc 1:10:100**: Phát hiện lỗi ở giai đoạn thiết kế tốn 1 đồng, ở giai đoạn sản xuất tốn 10 đồng, sau khi đến tay khách hàng tốn 100 đồng. → Đầu tư vào [[Prevention Cost]] là hiệu quả nhất!

### Ví dụ thực tế
Samsung Galaxy Note 7 (2016): Chi phí lỗi bên ngoài khổng lồ - thu hồi toàn bộ sản phẩm trên toàn thế giới, mất khoảng 5.3 tỷ USD, thiệt hại uy tín nghiêm trọng. Nếu Samsung đầu tư thêm vào Prevention Cost (kiểm tra pin kỹ hơn), họ đã tránh được thảm họa này.

### Liên kết
- [[Quality]] 
- [[Total Quality Management]]
- [[Process Improvement]]
- [[Poka-Yoke]]

---

## Total Quality Management (TQM) - Quản lý chất lượng toàn diện

### Định nghĩa (Definition)
[[Total Quality Management]] (TQM) là triết lý quản lý nhấn mạnh ba nguyên tắc: (1) sự hài lòng của khách hàng, (2) sự tham gia của mọi nhân viên, và (3) cải tiến liên tục trong chất lượng.

### Giải thích chi tiết

**Ba nguyên tắc cốt lõi:**

1. **[[Customer Satisfaction]]** (Sự hài lòng khách hàng)
   - [[Conformance Quality]]: Sản phẩm đúng thiết kế, đúng tiêu chuẩn
   - [[Design Quality]]: Thiết kế đáp ứng nhu cầu khách hàng
   - Chất lượng do KHÁCH HÀNG định nghĩa, không phải doanh nghiệp

2. **[[Employee Involvement]]** (Sự tham gia của nhân viên)
   - Mọi người đều chịu trách nhiệm về chất lượng
   - [[Quality Circles]]: Nhóm nhỏ nhân viên họp định kỳ tìm cách cải tiến
   - [[Empowerment]]: Trao quyền cho nhân viên dừng dây chuyền khi phát hiện lỗi (giống [[Jidoka]] trong [[Toyota Production System]])

3. **[[Continuous Improvement]]** ([[Kaizen]])
   - Không bao giờ hài lòng với hiện tại
   - Cải tiến nhỏ nhưng liên tục
   - Sử dụng [[PDCA Cycle]] (Plan-Do-Check-Act) - Chu trình Deming:
     - **Plan**: Xác định vấn đề, lập kế hoạch
     - **Do**: Thực hiện thay đổi nhỏ
     - **Check**: Đánh giá kết quả
     - **Act**: Chuẩn hóa nếu thành công, lặp lại nếu chưa

### Liên kết
- [[Six Sigma]]
- [[Continuous Improvement]]
- [[Kaizen]]
- [[PDCA Cycle]]
- [[CH04 - Lean Systems]]

---

## Six Sigma và DMAIC

### Định nghĩa (Definition)
[[Six Sigma]] là phương pháp cải tiến chất lượng có hệ thống nhằm giảm sai lỗi xuống mức cực thấp: tối đa 3.4 lỗi trên mỗi triệu cơ hội ([[DPMO]] - Defects Per Million Opportunities).

### Giải thích chi tiết

**Tại sao gọi là "Six Sigma"?**
Trong thống kê, [[Sigma]] (σ) là [[Standard Deviation]] (độ lệch chuẩn). Nếu quy trình đạt 6σ, nghĩa là giới hạn đặc tính kỹ thuật cách trung bình 6 độ lệch chuẩn → xác suất lỗi cực thấp.

| Mức Sigma | DPMO | Tỷ lệ đạt |
|-----------|------|-----------|
| 1σ | 691.462 | 30.85% |
| 2σ | 308.538 | 69.15% |
| 3σ | 66.807 | 93.32% |
| 4σ | 6.210 | 99.38% |
| 5σ | 233 | 99.977% |
| 6σ | 3.4 | 99.99966% |

#### DMAIC Framework

[[DMAIC]] là quy trình 5 bước cải tiến:

1. **[[Define]]** (Xác định)
   - Vấn đề là gì? Khách hàng cần gì?
   - Lập [[Project Charter]], xác định [[CTQ]] (Critical to Quality - Yếu tố quan trọng với chất lượng)
   - Công cụ: [[SIPOC Diagram]] (Supplier-Input-Process-Output-Customer)

2. **[[Measure]]** (Đo lường)
   - Thu thập dữ liệu về hiệu suất hiện tại
   - Xác định [[Baseline]] (đường cơ sở)
   - Công cụ: [[Process Capability]], [[Control Chart]], [[Checklist]]

3. **[[Analyze]]** (Phân tích)
   - Tìm nguyên nhân gốc rễ ([[Root Cause]])
   - Công cụ: [[Fishbone Diagram]], [[Pareto Chart]], [[5 Whys]], phân tích hồi quy

4. **[[Improve]]** (Cải tiến)
   - Thiết kế và triển khai giải pháp
   - Công cụ: [[Design of Experiments]] (DOE), [[Poka-Yoke]], brainstorming

5. **[[Control]]** (Kiểm soát)
   - Duy trì cải tiến, ngăn tái phát
   - Công cụ: [[Control Chart]], [[Standard Operating Procedure]] (SOP), đào tạo

**Hệ thống đai (Belt System):**
- [[Green Belt]]: Nhân viên được đào tạo, dành một phần thời gian cho Six Sigma
- [[Black Belt]]: Chuyên gia Six Sigma toàn thời gian
- [[Master Black Belt]]: Chuyên gia cao cấp, đào tạo Black Belt
- [[Champion]]: Lãnh đạo cấp cao hỗ trợ dự án

### Ví dụ thực tế
GE (General Electric) dưới thời Jack Welch đã triển khai Six Sigma toàn công ty, tiết kiệm hơn 12 tỷ USD trong 5 năm. Motorola - nơi khởi xướng Six Sigma - đã giảm tỷ lệ lỗi từ 6.000 DPMO xuống dưới 3.4 DPMO trong nhiều quy trình.

### Liên kết
- [[Total Quality Management]]
- [[Statistical Process Control]]
- [[Process Capability]]
- [[Continuous Improvement]]

---

## Acceptance Sampling (Lấy mẫu chấp nhận)

### Định nghĩa (Definition)
[[Acceptance Sampling]] là phương pháp kiểm tra chất lượng bằng cách lấy mẫu ngẫu nhiên từ một lô hàng, rồi quyết định chấp nhận hoặc từ chối toàn bộ lô dựa trên kết quả kiểm tra mẫu.

### Giải thích chi tiết
- **Tại sao không kiểm tra 100%?** Vì tốn kém, mất thời gian, hoặc không thể (ví dụ: kiểm tra bằng cách phá hủy sản phẩm như test pháo hoa)
- **[[Acceptable Quality Level]] (AQL)**: Tỷ lệ lỗi tối đa mà khách hàng chấp nhận
- **[[Lot Tolerance Percent Defective]] (LTPD)**: Tỷ lệ lỗi mà khách hàng từ chối lô hàng

**Hai loại rủi ro:**
- **[[Producer's Risk]] (α - Rủi ro nhà sản xuất)**: Xác suất từ chối lô hàng tốt (Type I Error). Thường α = 5%.
- **[[Consumer's Risk]] (β - Rủi ro người tiêu dùng)**: Xác suất chấp nhận lô hàng xấu (Type II Error). Thường β = 10%.

**[[Operating Characteristic Curve]] (OC Curve)**: Đồ thị cho thấy xác suất chấp nhận lô hàng ở các mức tỷ lệ lỗi khác nhau.

### Liên kết
- [[Quality Control]]
- [[Statistical Process Control]]
- [[Sampling Plan]]

---

## Statistical Process Control (SPC) - Kiểm soát quy trình bằng thống kê

### Định nghĩa (Definition)
[[Statistical Process Control]] (SPC) là phương pháp sử dụng các kỹ thuật thống kê để giám sát và kiểm soát quy trình, đảm bảo quy trình hoạt động ổn định và sản xuất sản phẩm đạt chất lượng.

### Giải thích chi tiết

#### Biến động trong quy trình
Mọi quy trình đều có [[Variation]] (biến động). Có hai loại:
- **[[Common Cause Variation]]** (Biến động ngẫu nhiên / tự nhiên): Biến động nhỏ, luôn tồn tại, thuộc về bản chất quy trình. Ví dụ: trọng lượng gói mì dao động ±0.5g là bình thường.
- **[[Assignable Cause Variation]]** (Biến động có nguyên nhân xác định): Biến động bất thường do nguyên nhân cụ thể. Ví dụ: máy bị hỏng, nguyên liệu lỗi, công nhân mới chưa quen. CẦN TÌM VÀ LOẠI BỎ.

Quy trình chỉ có Common Cause Variation gọi là [[In Statistical Control]] (trong tầm kiểm soát thống kê).

#### Control Charts (Biểu đồ kiểm soát)

[[Control Chart]] là đồ thị theo dõi một chỉ số chất lượng theo thời gian, với ba đường:
- **[[UCL]]** (Upper Control Limit - Giới hạn kiểm soát trên)
- **[[Center Line]]** (Đường trung tâm - giá trị trung bình)
- **[[LCL]]** (Lower Control Limit - Giới hạn kiểm soát dưới)

Thông thường: $UCL = \bar{x} + 3\sigma$ và $LCL = \bar{x} - 3\sigma$ (giới hạn 3-sigma)

**Quy tắc phát hiện bất thường:**
- Điểm nằm ngoài UCL hoặc LCL
- 7 điểm liên tiếp nằm cùng một phía so với Center Line (xu hướng - [[Run]])
- Mẫu hình bất thường (cyclical patterns)

#### Variables Charts vs Attributes Charts

| Loại | [[Variables Chart]] | [[Attributes Chart]] |
|------|-------------------|---------------------|
| Dữ liệu | Liên tục (đo được) | Rời rạc (đếm được) |
| Ví dụ | Trọng lượng, chiều dài, nhiệt độ | Số lỗi, tỷ lệ hỏng, đạt/không đạt |
| Biểu đồ | [[X-bar Chart]] + [[R Chart]] (hoặc [[S Chart]]) | [[p Chart]], [[c Chart]], [[np Chart]] |

**[[X-bar Chart]]** (Biểu đồ X-bar): Theo dõi giá trị TRUNG BÌNH của mẫu
$$UCL_{\bar{x}} = \bar{\bar{x}} + A_2 \bar{R}$$
$$LCL_{\bar{x}} = \bar{\bar{x}} - A_2 \bar{R}$$

**[[R Chart]]** (Biểu đồ R): Theo dõi PHẠM VI (Range) của mẫu - đo mức biến động
$$UCL_R = D_4 \bar{R}$$
$$LCL_R = D_3 \bar{R}$$

Trong đó $A_2$, $D_3$, $D_4$ là hệ số tra bảng phụ thuộc cỡ mẫu $n$.

**[[p Chart]]** (Biểu đồ p): Theo dõi TỶ LỆ lỗi trong mẫu
$$UCL_p = \bar{p} + 3\sqrt{\frac{\bar{p}(1-\bar{p})}{n}}$$
$$LCL_p = \bar{p} - 3\sqrt{\frac{\bar{p}(1-\bar{p})}{n}}$$

**[[c Chart]]** (Biểu đồ c): Theo dõi SỐ LỖI trong mỗi đơn vị
$$UCL_c = \bar{c} + 3\sqrt{\bar{c}}$$
$$LCL_c = \bar{c} - 3\sqrt{\bar{c}}$$

### Ví dụ thực tế
Nhà máy sản xuất chai nước suối kiểm tra dung tích. Mỗi giờ lấy 5 chai (n=5), đo dung tích. Vẽ X-bar chart và R chart. Nếu một điểm vượt UCL → dừng máy, tìm nguyên nhân (có thể vòi chiết bị hỏng).

### Liên kết
- [[Process Capability]]
- [[Six Sigma]]
- [[Variation]]
- [[Control Chart]]

---

## Process Capability (Năng lực quy trình)

### Định nghĩa (Definition)
[[Process Capability]] đo lường khả năng quy trình sản xuất sản phẩm nằm trong [[Specification Limits]] (giới hạn đặc tính kỹ thuật) do khách hàng hoặc kỹ sư thiết kế đặt ra.

### Giải thích chi tiết

> **Phân biệt quan trọng:**
> - [[Control Limits]] (UCL, LCL): Do QUY TRÌNH quyết định - "Quy trình đang làm gì"
> - [[Specification Limits]] (USL, LSL): Do KHÁCH HÀNG/THIẾT KẾ quyết định - "Khách hàng muốn gì"

#### Chỉ số Cp

[[Cp]] đo khả năng quy trình khi quy trình NẰM CHÍNH GIỮA specification limits:

$$C_p = \frac{USL - LSL}{6\sigma}$$

- $C_p > 1$: Quy trình có khả năng (specification rộng hơn biến động quy trình)
- $C_p = 1$: Vừa đủ (ranh giới)
- $C_p < 1$: Quy trình không đủ khả năng (biến động lớn hơn specification)
- **Mục tiêu thường là $C_p \geq 1.33$**

#### Chỉ số Cpk

[[Cpk]] đo khả năng quy trình khi xét cả vị trí trung bình (quy trình có thể LỆCH TÂM):

$$C_{pk} = \min\left(\frac{USL - \bar{x}}{3\sigma}, \frac{\bar{x} - LSL}{3\sigma}\right)$$

- $C_{pk} = C_p$: Quy trình nằm chính giữa
- $C_{pk} < C_p$: Quy trình bị lệch tâm
- $C_{pk} < 0$: Trung bình quy trình nằm ngoài specification limits!
- **Mục tiêu: $C_{pk} \geq 1.33$** (tương đương 4-sigma)

### Ví dụ thực tế
Sản xuất bu lông đường kính 10mm, specification: 10 ± 0.1mm (LSL = 9.9, USL = 10.1), σ = 0.025mm, trung bình = 10.02mm

$$C_p = \frac{10.1 - 9.9}{6(0.025)} = \frac{0.2}{0.15} = 1.33$$ ✓ Đủ khả năng

$$C_{pk} = \min\left(\frac{10.1 - 10.02}{3(0.025)}, \frac{10.02 - 9.9}{3(0.025)}\right) = \min\left(\frac{0.08}{0.075}, \frac{0.12}{0.075}\right) = \min(1.07, 1.60) = 1.07$$

$C_{pk} = 1.07 < 1.33$ → Quy trình bị lệch sang phải, cần điều chỉnh trung bình về 10.00mm.

### Liên kết
- [[Statistical Process Control]]
- [[Specification Limits]]
- [[Six Sigma]]
- [[Standard Deviation]]

---

## ISO 9001:2015

### Định nghĩa (Definition)
[[ISO 9001]] là tiêu chuẩn quốc tế về hệ thống quản lý chất lượng (Quality Management System - QMS) do [[International Organization for Standardization]] (ISO) ban hành.

### Giải thích chi tiết
- **Không phải tiêu chuẩn sản phẩm** mà là tiêu chuẩn HỆ THỐNG QUẢN LÝ
- Yêu cầu doanh nghiệp phải có quy trình rõ ràng, được tài liệu hóa, giám sát và cải tiến
- Được công nhận toàn cầu, thường là yêu cầu bắt buộc trong thương mại quốc tế
- **7 nguyên tắc**: Customer focus, Leadership, Engagement of people, Process approach, Improvement, Evidence-based decision making, Relationship management
- Phiên bản 2015 nhấn mạnh [[Risk-Based Thinking]] (tư duy dựa trên rủi ro)

Lợi ích:
- Cải thiện chất lượng sản phẩm/dịch vụ
- Tăng sự hài lòng khách hàng
- Mở cửa thị trường quốc tế
- Cải thiện quy trình nội bộ

### Liên kết
- [[Quality Management System]]
- [[Continuous Improvement]]
- [[Risk-Based Thinking]]

---

## Malcolm Baldrige National Quality Award

### Định nghĩa (Definition)
[[Malcolm Baldrige National Quality Award]] là giải thưởng chất lượng danh giá nhất của Mỹ, trao cho các tổ chức xuất sắc trong quản lý và hiệu suất.

### Giải thích chi tiết
**7 tiêu chí đánh giá** (tổng 1000 điểm):
1. **Leadership** (Lãnh đạo) - 120 điểm
2. **Strategy** (Chiến lược) - 85 điểm
3. **Customers** (Khách hàng) - 85 điểm
4. **Measurement, Analysis, Knowledge Management** - 90 điểm
5. **Workforce** (Nhân lực) - 85 điểm
6. **Operations** (Vận hành) - 85 điểm
7. **Results** (Kết quả) - 450 điểm

> Lưu ý Results chiếm 45% tổng điểm → Quan trọng nhất là KẾT QUẢ thực tế, không chỉ quy trình đẹp trên giấy.

### Liên kết
- [[Total Quality Management]]
- [[Performance Excellence]]
- [[ISO 9001]]
- [[Continuous Improvement]]

---

## Công thức quan trọng (Key Formulas)

| Chỉ số | Công thức | Ý nghĩa |
|--------|-----------|---------|
| [[Cp]] | $\frac{USL - LSL}{6\sigma}$ | Năng lực quy trình (centered) |
| [[Cpk]] | $\min\left(\frac{USL-\bar{x}}{3\sigma}, \frac{\bar{x}-LSL}{3\sigma}\right)$ | Năng lực quy trình (actual) |
| [[X-bar Chart]] UCL | $\bar{\bar{x}} + A_2\bar{R}$ | Giới hạn trên biểu đồ trung bình |
| [[R Chart]] UCL | $D_4\bar{R}$ | Giới hạn trên biểu đồ phạm vi |
| [[p Chart]] UCL | $\bar{p} + 3\sqrt{\frac{\bar{p}(1-\bar{p})}{n}}$ | Giới hạn trên biểu đồ tỷ lệ lỗi |
| [[c Chart]] UCL | $\bar{c} + 3\sqrt{\bar{c}}$ | Giới hạn trên biểu đồ số lỗi |
| [[DPMO]] | $\frac{\text{Defects}}{\text{Opportunities}} \times 10^6$ | Số lỗi trên triệu cơ hội |

---

## Từ khóa chính (Key Terms)

- [[Quality]] - Chất lượng
- [[Cost of Quality]] - Chi phí chất lượng
- [[Prevention Cost]] - Chi phí phòng ngừa
- [[Appraisal Cost]] - Chi phí thẩm định
- [[Internal Failure Cost]] - Chi phí lỗi nội bộ
- [[External Failure Cost]] - Chi phí lỗi bên ngoài
- [[Total Quality Management]] - Quản lý chất lượng toàn diện
- [[Six Sigma]] - Sáu Sigma
- [[DMAIC]] - Define-Measure-Analyze-Improve-Control
- [[Continuous Improvement]] - Cải tiến liên tục
- [[PDCA Cycle]] - Chu trình Plan-Do-Check-Act
- [[Statistical Process Control]] - Kiểm soát quy trình thống kê
- [[Control Chart]] - Biểu đồ kiểm soát
- [[Common Cause Variation]] - Biến động ngẫu nhiên
- [[Assignable Cause Variation]] - Biến động có nguyên nhân
- [[Process Capability]] - Năng lực quy trình
- [[Cp]] - Chỉ số năng lực quy trình
- [[Cpk]] - Chỉ số năng lực quy trình thực tế
- [[Acceptance Sampling]] - Lấy mẫu chấp nhận
- [[ISO 9001]] - Tiêu chuẩn quản lý chất lượng quốc tế
- [[Malcolm Baldrige National Quality Award]] - Giải thưởng Baldrige
- [[X-bar Chart]] - Biểu đồ trung bình
- [[R Chart]] - Biểu đồ phạm vi
- [[p Chart]] - Biểu đồ tỷ lệ lỗi
- [[c Chart]] - Biểu đồ số lỗi
- [[Specification Limits]] - Giới hạn đặc tính kỹ thuật
- [[Poka-Yoke]] - Chống sai lỗi
- [[Fishbone Diagram]] - Biểu đồ xương cá
- [[Pareto Chart]] - Biểu đồ Pareto

---

> **Ghi chú ôn tập**: Chương 3 có nhiều công thức. Hãy chắc chắn phân biệt được Control Limits (do quy trình) vs Specification Limits (do thiết kế), và Cp (centered) vs Cpk (actual). SPC liên kết chặt chẽ với [[CH04 - Lean Systems]] và [[Six Sigma]].
