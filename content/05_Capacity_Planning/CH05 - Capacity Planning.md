---
tags: [chapter-5, part2, capacity-planning, economies-of-scale, utilization, expansion-strategy]
aliases: [Hoạch định công suất, Capacity Planning, OM Chapter 5]
---
# Chapter 5 - Capacity Planning

## Tổng quan (Overview)

Chương 5 bàn về [[Capacity Planning]] (Hoạch định công suất) - quá trình xác định khả năng sản xuất/phục vụ mà doanh nghiệp cần để đáp ứng nhu cầu thay đổi. Đây là quyết định chiến lược dài hạn vì đầu tư công suất thường tốn kém và khó đảo ngược: xây nhà máy mới mất vài năm, nhưng nếu không đủ công suất thì mất khách hàng.

Chương giải thích các khái niệm quan trọng như [[Economies of Scale]] (lợi thế kinh tế nhờ quy mô) và [[Diseconomies of Scale]], cách tính [[Utilization]] (hệ số sử dụng công suất), chiến lược mở rộng công suất, và phương pháp ra quyết định có hệ thống. Các công cụ hỗ trợ bao gồm [[Waiting-Line Models]], [[Simulation]], và [[Decision Tree]].

Quyết định công suất ảnh hưởng trực tiếp đến [[Cost]], [[Quality]], [[Time]], và [[Flexibility]] - tất cả bốn [[Competitive Priorities]].

---

## Planning Long-Term Capacity (Hoạch định công suất dài hạn)

### Measures of Capacity (Đo lường công suất)

#### Định nghĩa (Definition)
[[Capacity]] (Công suất) là tỷ lệ sản xuất/phục vụ tối đa mà một cơ sở có thể đạt được trong điều kiện hoạt động bình thường.

#### Giải thích chi tiết

Có hai cách đo công suất:

1. **[[Output Measures]]** (Đo theo đầu ra): Phù hợp khi sản phẩm đồng nhất
   - Ví dụ: Nhà máy ô tô → 500 xe/ngày; Nhà máy bia → 1 triệu lít/tháng
   
2. **[[Input Measures]]** (Đo theo đầu vào): Phù hợp khi sản phẩm đa dạng
   - Ví dụ: Bệnh viện → 200 giường bệnh; Nhà hàng → 100 chỗ ngồi; Trường đại học → 2.000 sinh viên

**Hai mức công suất:**
- **[[Design Capacity]]** (Công suất thiết kế): Mức tối đa theo lý thuyết (100% thời gian, không bảo trì, không nghỉ)
- **[[Effective Capacity]]** (Công suất hiệu quả): Mức tối đa thực tế khi xét đến bảo trì, nghỉ ngơi, thiết lập máy. Luôn ≤ Design Capacity.

### Utilization (Hệ số sử dụng)

$$\text{Utilization} = \frac{\text{Average Output Rate}}{\text{Maximum Capacity}} \times 100\%$$

Ví dụ: Nhà máy có công suất 1.000 SP/ngày, thực tế sản xuất 800 SP/ngày:
$$\text{Utilization} = \frac{800}{1000} \times 100\% = 80\%$$

> **Lưu ý**: Utilization 100% KHÔNG phải mục tiêu! Sử dụng quá cao dẫn đến: máy không được bảo trì, nhân viên kiệt sức, chất lượng giảm, không linh hoạt khi nhu cầu tăng đột biến. Mức lý tưởng thường là 70-90% tùy ngành.

### Ví dụ thực tế
Phòng gym có công suất 200 người/lúc. Giờ cao điểm (5-8pm) có 190 người → Utilization = 95% → quá đông, khách phải chờ máy. Giờ thấp điểm (2-4pm) chỉ 40 người → 20% → lãng phí. Giải pháp: giảm giá giờ thấp điểm để kéo khách từ giờ cao điểm sang.

### Liên kết
- [[Design Capacity]]
- [[Effective Capacity]]
- [[Bottleneck]]
- [[CH06 - Constraint Management]]

---

## Economies of Scale vs Diseconomies of Scale

### Economies of Scale (Lợi thế kinh tế nhờ quy mô)

#### Định nghĩa (Definition)
[[Economies of Scale]] là hiện tượng chi phí trung bình trên mỗi đơn vị sản phẩm GIẢM khi sản lượng TĂNG.

#### Giải thích chi tiết

Tại sao chi phí giảm khi sản xuất nhiều hơn?

1. **Phân bổ [[Fixed Cost]]**: Tiền thuê nhà máy 100 triệu/tháng. Sản xuất 1.000 SP → 100.000/SP. Sản xuất 10.000 SP → 10.000/SP. → Chi phí cố định trên mỗi SP giảm 10 lần!

2. **[[Purchasing Discount]]** (Chiết khấu mua hàng): Mua 100 tấn thép rẻ hơn mua 10 tấn (discount theo số lượng)

3. **[[Learning Curve Effect]]** (Đường cong học hỏi): Sản xuất càng nhiều → công nhân càng quen → năng suất tăng → chi phí giảm

4. **[[Specialization]]** (Chuyên môn hóa): Quy mô lớn cho phép phân công lao động chuyên sâu hơn

### Diseconomies of Scale (Bất lợi kinh tế do quy mô)

#### Định nghĩa (Definition)
[[Diseconomies of Scale]] là hiện tượng chi phí trung bình TĂNG khi sản lượng vượt quá một mức tối ưu.

#### Giải thích chi tiết
Tại sao "lớn quá" lại tốn kém hơn?

1. **Phức tạp quản lý**: Nhà máy quá lớn → khó kiểm soát → cần thêm quản lý → chi phí gián tiếp tăng
2. **Giao thông nội bộ**: Nhà máy rộng → vận chuyển nội bộ xa hơn → tốn thời gian và chi phí
3. **Mất linh hoạt**: Tổ chức quá lớn → phản ứng chậm với thay đổi thị trường
4. **Tinh thần nhân viên**: Nhà máy quá lớn → nhân viên cảm thấy như "bánh răng trong máy" → động lực giảm

> **Đồ thị chi phí hình chữ U**: Chi phí trung bình giảm khi tăng sản lượng (Economies of Scale) → đạt điểm tối ưu ([[Best Operating Level]]) → tăng khi sản lượng tiếp tục tăng (Diseconomies of Scale).


### Ví dụ thực tế
Amazon xây dựng nhiều kho nhỏ phân tán thay vì một kho khổng lồ. Mỗi kho phục vụ một khu vực → giao hàng nhanh hơn, quản lý dễ hơn. Đây là ví dụ về việc tránh Diseconomies of Scale.

### Liên kết
- [[Best Operating Level]]
- [[Fixed Cost]]
- [[Learning Curve Effect]]
- [[Capacity Planning]]

---

## Capacity Timing and Sizing Strategies (Chiến lược thời điểm và quy mô mở rộng)

### Capacity Cushion (Đệm công suất)

#### Định nghĩa (Definition)
[[Capacity Cushion]] là phần công suất dự trữ vượt trên nhu cầu dự kiến, nhằm đối phó với sự không chắc chắn của nhu cầu.

$$\text{Capacity Cushion} = 100\% - \text{Average Utilization Rate (\%)}$$

#### Giải thích chi tiết
- **Đệm lớn** (công suất dư nhiều): Phù hợp khi nhu cầu biến động mạnh, cần giao nhanh. Ví dụ: phòng cấp cứu bệnh viện cần đệm lớn.
- **Đệm nhỏ** hoặc **âm**: Phù hợp khi sản phẩm chuẩn hóa, nhu cầu ổn định, chi phí công suất rất cao. Ví dụ: nhà máy lọc dầu.

### Expansion Strategies (Chiến lược mở rộng)


Có ba chiến lược chính:

1. **[[Expansionist Strategy]]** (Chiến lược mở rộng trước)
   - Xây dựng công suất LỚN TRƯỚC khi nhu cầu tăng
   - Ưu: Không bao giờ mất đơn hàng, sẵn sàng đón khách
   - Nhược: Rủi ro nếu nhu cầu không tăng như dự kiến → lãng phí đầu tư
   - Phù hợp: Chi phí mất khách hàng cao, thị trường đang tăng trưởng nhanh

2. **[[Wait-and-See Strategy]]** (Chiến lược chờ đợi)
   - Chỉ mở rộng SAU KHI nhu cầu thực sự tăng
   - Ưu: Giảm rủi ro, đầu tư chắc chắn hơn
   - Nhược: Có thể mất khách hàng trong thời gian chờ xây dựng
   - Phù hợp: Chi phí công suất rất cao, khó dự đoán nhu cầu

3. **[[Follow-the-Leader Strategy]]** (Chiến lược theo đối thủ)
   - Mở rộng khi đối thủ mở rộng
   - Ưu: Không bị tụt hậu
   - Nhược: Có thể tạo ra thừa công suất toàn ngành


### Ví dụ thực tế
- **Expansionist**: TSMC đầu tư hàng tỷ USD xây nhà máy chip trước khi có đơn hàng, vì họ tin nhu cầu chip sẽ tăng. Chiến lược này giúp họ chiếm >50% thị phần chip hợp đồng.
- **Wait-and-See**: Nhiều hãng hàng không chờ đợi sau COVID mới quyết định có đầu tư máy bay mới hay không.

### Liên kết
- [[Capacity Cushion]]
- [[Demand Forecasting]]
- [[Operations Strategy]]
- [[Risk Management]]

---

## Systematic Approach to Long-Term Capacity Decisions (Phương pháp hệ thống cho quyết định công suất dài hạn)

### Giải thích chi tiết

**4 bước ra quyết định công suất:**

#### Bước 1: Estimate Future Capacity Requirements (Ước tính nhu cầu công suất tương lai)
- Sử dụng [[Demand Forecasting]] (dự báo nhu cầu)
- Xem xét xu hướng thị trường, đối thủ, công nghệ mới
- Tính toán [[Capacity Gap]] = Nhu cầu dự kiến - Công suất hiện tại

$$\text{Capacity Gap} = \text{Projected Demand} - \text{Current Capacity}$$

#### Bước 2: Identify Gaps (Xác định khoảng cách)
- So sánh nhu cầu với công suất hiện tại
- Xác định thời điểm cần mở rộng
- Xem xét cả công suất nội bộ và [[Outsourcing]]

#### Bước 3: Develop Alternatives (Phát triển các phương án)
- Mở rộng tại chỗ (thêm ca, thêm máy)
- Xây cơ sở mới
- Thuê ngoài ([[Outsourcing]])
- Không làm gì (giữ nguyên)
- Kết hợp nhiều phương án

#### Bước 4: Evaluate Alternatives (Đánh giá các phương án)
- Phân tích tài chính: [[Break-Even Analysis]], [[NPV]] (Net Present Value), [[IRR]]
- Phân tích định tính: [[Preference Matrix]]
- Phân tích rủi ro: [[Decision Tree]], [[Simulation]], phân tích kịch bản

### Ví dụ thực tế
VinFast cần mở rộng công suất:
1. Dự báo nhu cầu xe điện tăng 50%/năm trong 5 năm
2. Capacity Gap: cần thêm 100.000 xe/năm
3. Phương án: (A) Mở rộng nhà máy Hải Phòng, (B) Xây nhà máy mới ở Mỹ, (C) Kết hợp A+B
4. Đánh giá: NPV, Break-Even, rủi ro chính trị, logistics...

### Liên kết
- [[Break-Even Analysis]]
- [[SA - Decision Making]]
- [[Decision Tree]]
- [[Demand Forecasting]]

---

## Tools for Capacity Planning (Công cụ hoạch định công suất)

### Waiting-Line Models (Mô hình hàng chờ)

[[Waiting-Line Models]] (hay [[Queueing Models]]) giúp xác định công suất phù hợp khi có yếu tố ngẫu nhiên (khách đến bất kỳ lúc nào, thời gian phục vụ khác nhau). Chi tiết trong [[SB - Waiting Lines]].

Ứng dụng: Xác định số quầy thu ngân trong siêu thị, số đường dây điện thoại hotline, số máy chủ cho website.

### Simulation (Mô phỏng)

[[Simulation]] sử dụng máy tính để mô phỏng hoạt động của hệ thống trong nhiều kịch bản khác nhau. Đặc biệt hữu ích khi hệ thống quá phức tạp cho mô hình toán học.

Ví dụ: Mô phỏng hoạt động sân bay để xác định cần bao nhiêu đường băng, quầy check-in, cổng boarding.

### Decision Trees (Cây quyết định)


[[Decision Tree]] đặc biệt hữu ích cho quyết định công suất vì thường có nhiều giai đoạn (mở rộng bây giờ hoặc sau, quy mô lớn hay nhỏ) và nhiều kịch bản nhu cầu. Chi tiết trong [[SA - Decision Making]].

### Liên kết
- [[SB - Waiting Lines]]
- [[SA - Decision Making]]
- [[Monte Carlo Simulation]]
- [[Decision Tree]]

---

## Công thức quan trọng (Key Formulas)

| Chỉ số | Công thức | Ý nghĩa |
|--------|-----------|---------|
| [[Utilization]] | $\frac{\text{Average Output}}{\text{Max Capacity}} \times 100\%$ | Hệ số sử dụng công suất |
| [[Capacity Cushion]] | $100\% - \text{Utilization}$ | Phần trăm công suất dự trữ |
| [[Capacity Gap]] | Projected Demand - Current Capacity | Khoảng thiếu hụt công suất |
| [[Break-Even Point]] | $\frac{F}{p - c}$ | Sản lượng hòa vốn (xem [[SA - Decision Making]]) |

---

## Từ khóa chính (Key Terms)

- [[Capacity Planning]] - Hoạch định công suất
- [[Capacity]] - Công suất
- [[Design Capacity]] - Công suất thiết kế
- [[Effective Capacity]] - Công suất hiệu quả
- [[Utilization]] - Hệ số sử dụng
- [[Economies of Scale]] - Lợi thế kinh tế nhờ quy mô
- [[Diseconomies of Scale]] - Bất lợi kinh tế do quy mô
- [[Best Operating Level]] - Mức hoạt động tối ưu
- [[Capacity Cushion]] - Đệm công suất
- [[Expansionist Strategy]] - Chiến lược mở rộng trước
- [[Wait-and-See Strategy]] - Chiến lược chờ đợi
- [[Capacity Gap]] - Khoảng cách công suất
- [[Waiting-Line Models]] - Mô hình hàng chờ
- [[Simulation]] - Mô phỏng
- [[Decision Tree]] - Cây quyết định
- [[Outsourcing]] - Thuê ngoài
- [[Demand Forecasting]] - Dự báo nhu cầu
- [[Learning Curve Effect]] - Hiệu ứng đường cong học hỏi

---

> **Ghi chú ôn tập**: Chương 5 kết nối với nhiều chương khác: [[SA - Decision Making]] (Break-Even, Decision Tree), [[SB - Waiting Lines]] (Waiting-Line Models), [[CH06 - Constraint Management]] (Bottleneck). Hãy nhớ: Utilization 100% KHÔNG phải mục tiêu, và luôn xem xét cả Economies lẫn Diseconomies of Scale!


---
## Hình minh họa từ sách (Textbook Figures)

![Figure 5.1](/images/figures/ch05_fig5.1.jpg)
> *Figure 5.1*

![Figure 5.2](/images/figures/ch05_fig5.2.jpg)
> *Figure 5.2*

![Figure 5.3](/images/figures/ch05_fig5.3.jpg)
> *Figure 5.3*

![Figure 5.4](/images/figures/ch05_fig5.4.jpg)
> *Figure 5.4*

![Figure 5.5](/images/figures/ch05_fig5.5.jpg)
> *Figure 5.5*

