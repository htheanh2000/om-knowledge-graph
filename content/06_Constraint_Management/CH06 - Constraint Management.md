---
tags: [chapter-6, part2, TOC, bottleneck, drum-buffer-rope, line-balancing, constraint-management]
aliases: [Quản lý ràng buộc, Constraint Management, OM Chapter 6]
---
# Chapter 6 - Constraint Management

## Tổng quan (Overview)

Chương 6 giới thiệu [[Constraint Management]] (Quản lý ràng buộc) - triết lý quản lý tập trung vào việc tìm và xử lý điểm yếu nhất trong hệ thống. Ý tưởng cốt lõi: **một chuỗi chỉ mạnh bằng mắt xích yếu nhất**. Cho dù các quy trình khác tuyệt vời đến mấy, hiệu suất tổng thể bị giới hạn bởi [[Bottleneck]] (nút thắt cổ chai) - quy trình chậm nhất hoặc có công suất thấp nhất.

Chương trình bày [[Theory of Constraints]] (TOC) do [[Eliyahu Goldratt]] phát triển, phương pháp [[Drum-Buffer-Rope]] (DBR), ứng dụng TOC vào quyết định sản phẩm hỗn hợp, và [[Line Balancing]] (cân bằng dây chuyền). Đây là những công cụ cực kỳ thực tế giúp tăng throughput mà không cần đầu tư lớn.

Constraint Management bổ sung cho [[Lean Systems]] và [[Six Sigma]]: Lean loại bỏ lãng phí ở mọi nơi, Six Sigma giảm biến động, còn TOC tập trung nguồn lực vào điểm ràng buộc quan trọng nhất.

---

## Theory of Constraints (TOC) - Lý thuyết ràng buộc

### Định nghĩa (Definition)
[[Theory of Constraints]] (TOC) là phương pháp quản lý hệ thống do [[Eliyahu Goldratt]] phát triển, dựa trên nguyên tắc: mọi hệ thống đều có ít nhất một ràng buộc (constraint) giới hạn hiệu suất tổng thể. Cải tiến tại ràng buộc → cải tiến toàn hệ thống.

### Giải thích chi tiết

#### Key Principles (Nguyên tắc chính)

![Figure 6.1 - Theory of Constraints Steps](/images/figures/ch06_fig6.1.jpg)
> *Figure 6.1: Năm bước tập trung của TOC - Identify, Exploit, Subordinate, Elevate, Repeat*

**5 bước tập trung của TOC (Five Focusing Steps):**

1. **IDENTIFY** (Nhận diện): Tìm ra ràng buộc/nút thắt cổ chai ([[Bottleneck]])
   - Nơi nào tồn kho tích tụ nhiều nhất? → Trước bottleneck
   - Nơi nào luôn chạy hết công suất? → Chính là bottleneck
   - Nơi nào các trạm sau luôn phải chờ? → Sau bottleneck

2. **EXPLOIT** (Khai thác): Tận dụng tối đa ràng buộc hiện tại
   - Không để bottleneck ngừng hoạt động (kể cả giờ nghỉ trưa)
   - Đảm bảo bottleneck luôn có việc làm
   - Chỉ xử lý sản phẩm chất lượng qua bottleneck (kiểm tra TRƯỚC bottleneck)
   - Ví dụ: Nếu máy X là bottleneck, bố trí ăn trưa ca so le để máy không bao giờ dừng

3. **SUBORDINATE** (Phụ thuộc): Tất cả quy trình khác phục vụ cho bottleneck
   - Không sản xuất nhanh hơn bottleneck (sẽ tạo tồn kho thừa)
   - Điều chỉnh nhịp toàn hệ thống theo nhịp bottleneck
   - Non-bottleneck có thể nghỉ (idle) mà không sao!

4. **ELEVATE** (Nâng cao): Tăng công suất ràng buộc
   - Mua thêm máy, thuê thêm nhân viên cho bottleneck
   - Thuê ngoài ([[Outsourcing]]) công đoạn bottleneck
   - Đầu tư công nghệ mới cho bottleneck
   - Chỉ đầu tư khi bước 2 và 3 đã được tối ưu

5. **REPEAT** (Lặp lại): Quay lại bước 1
   - Khi bottleneck cũ được giải quyết → bottleneck MỚI sẽ xuất hiện
   - Quy trình cải tiến là vô tận
   - **Cảnh báo**: Đừng để quán tính (inertia) trở thành ràng buộc!

### Ví dụ thực tế
Nhà máy sản xuất đồ gỗ có 4 công đoạn:
- Cắt gỗ: 100 sản phẩm/giờ
- Lắp ráp: **50 sản phẩm/giờ** ← BOTTLENECK
- Sơn: 80 sản phẩm/giờ
- Đóng gói: 120 sản phẩm/giờ

Toàn bộ nhà máy chỉ sản xuất được 50 SP/giờ dù cắt gỗ có thể làm 100. Nếu cắt gỗ chạy hết công suất → 50 sản phẩm dở dang tích tụ trước lắp ráp mỗi giờ!

### Liên kết
- [[Bottleneck]]
- [[Throughput]]
- [[Drum-Buffer-Rope]]
- [[Eliyahu Goldratt]]
- [[CH05 - Capacity Planning]]

---

## Managing Bottlenecks (Quản lý nút thắt cổ chai)

### In Services (Trong dịch vụ)

#### Giải thích chi tiết
Bottleneck trong dịch vụ thường khó nhận diện hơn vì:
- Sản phẩm vô hình → không thấy tồn kho tích tụ
- Nhu cầu biến động lớn → bottleneck có thể thay đổi theo thời gian
- Khách hàng tham gia vào quy trình → thời gian xử lý không đồng nhất

**Dấu hiệu bottleneck trong dịch vụ:**
- Hàng chờ dài nhất
- Thời gian chờ lâu nhất
- Nhân viên luôn bận rộn nhất

Ví dụ: Trong bệnh viện, phòng chụp MRI thường là bottleneck - máy đắt, số lượng ít, nhiều bệnh nhân cần.

### In Manufacturing (Trong sản xuất)

#### Giải thích chi tiết
Bottleneck trong sản xuất dễ nhận diện hơn:
- Tồn kho WIP tích tụ TRƯỚC bottleneck
- Các trạm SAU bottleneck thường rảnh rỗi
- Bottleneck có [[Utilization]] cao nhất (thường > 90%)

![Figure 6.2 - Bottleneck Identification](/images/figures/ch06_fig6.2.jpg)
> *Figure 6.2: Nhận diện nút thắt cổ chai - WIP tích tụ trước bottleneck, các trạm sau bottleneck thường rảnh rỗi*

### Identifying and Relieving Bottlenecks (Nhận diện và giải tỏa nút thắt)

**Cách nhận diện:**
1. Đo [[Utilization]] tại mỗi trạm → trạm cao nhất = bottleneck
2. Quan sát WIP → nơi WIP cao nhất = trước bottleneck
3. Hỏi nhân viên → "Chỗ nào luôn bận nhất?"

**Cách giải tỏa (từ rẻ đến đắt):**
1. Tăng giờ làm tại bottleneck (tăng ca, làm thêm ngày nghỉ)
2. Giảm thời gian setup ([[SMED]])
3. Đào tạo thêm nhân viên ([[Cross-Training]])
4. Giảm phế phẩm tại bottleneck (mỗi sản phẩm lỗi = mất công suất quý giá)
5. Thuê ngoài ([[Outsourcing]])
6. Mua thêm thiết bị (đắt nhất)

> **Quy tắc vàng**: Một giờ mất tại bottleneck = một giờ mất của TOÀN BỘ hệ thống. Một giờ tiết kiệm tại non-bottleneck = ảo tưởng (không giúp gì cho hệ thống).

### Liên kết
- [[Theory of Constraints]]
- [[Utilization]]
- [[WIP]]
- [[SMED]]
- [[Outsourcing]]

---

## Drum-Buffer-Rope (DBR)

### Định nghĩa (Definition)
[[Drum-Buffer-Rope]] (DBR) là phương pháp lập lịch sản xuất dựa trên TOC, sử dụng bottleneck làm trung tâm điều phối toàn bộ hệ thống.

### Giải thích chi tiết

![Figure 6.4 - Drum-Buffer-Rope](/images/figures/ch06_fig6.4.jpg)
> *Figure 6.4: Phương pháp Drum-Buffer-Rope (DBR) - Bottleneck là Drum đặt nhịp, Buffer bảo vệ bottleneck, Rope kiểm soát đầu vào*

**Ba thành phần:**

1. **[[Drum]]** (Trống) = BOTTLENECK
   - Bottleneck đặt nhịp (pace) cho toàn hệ thống
   - Giống tiếng trống chèo thuyền - mọi người chèo theo nhịp trống
   - Lịch sản xuất của bottleneck = lịch sản xuất của nhà máy

2. **[[Buffer]]** (Đệm) = HÀNG CHỜ TRƯỚC BOTTLENECK
   - Duy trì một lượng WIP vừa đủ trước bottleneck
   - Đảm bảo bottleneck không bao giờ bị "đói" (starved)
   - Thường đo bằng thời gian (time buffer), không phải số lượng
   - Ví dụ: Buffer 2 giờ = luôn có 2 giờ việc làm chờ trước bottleneck

3. **[[Rope]]** (Dây) = TÍN HIỆU KIỂM SOÁT ĐẦU VÀO
   - Kiểm soát tỷ lệ nguyên liệu đưa vào hệ thống
   - "Kéo" nguyên liệu vào theo nhịp bottleneck
   - Ngăn sản xuất quá nhanh ở đầu vào → tránh WIP quá nhiều
   - Tương tự [[Kanban]] trong [[Lean Systems]]

### Ví dụ thực tế
Nhà máy bánh kẹo:
- Trộn bột: 200 kg/giờ
- Nướng: **100 kg/giờ** ← DRUM (bottleneck)
- Đóng gói: 150 kg/giờ

**Áp dụng DBR:**
- **Drum**: Lên lịch nướng 100 kg/giờ = lịch của nhà máy
- **Buffer**: Luôn giữ 200 kg bột đã trộn sẵn trước lò nướng (buffer 2 giờ)
- **Rope**: Chỉ cho phép trộn bột MỚI khi buffer giảm dưới mức quy định. Trộn bột chỉ chạy 100 kg/giờ (theo nhịp nướng), KHÔNG phải 200 kg/giờ (hết công suất)

### Liên kết
- [[Theory of Constraints]]
- [[Bottleneck]]
- [[Kanban System]]
- [[Production Scheduling]]
- [[WIP]]

---

## Product Mix Decisions with TOC (Quyết định sản phẩm hỗn hợp theo TOC)

### Định nghĩa (Definition)
TOC cung cấp phương pháp xác định sản phẩm hỗn hợp ([[Product Mix]]) tối ưu khi có bottleneck bằng cách ưu tiên sản phẩm có [[Throughput]] (lợi nhuận đóng góp) cao nhất trên mỗi đơn vị thời gian bottleneck.

### Giải thích chi tiết

**Nguyên tắc**: Maximizing throughput per bottleneck minute

**Bước thực hiện:**
1. Xác định bottleneck
2. Tính [[Contribution Margin]] mỗi sản phẩm = Giá bán - Chi phí biến đổi
3. Tính thời gian mỗi sản phẩm dùng tại bottleneck
4. Tính: **Throughput per bottleneck minute = Contribution Margin / Bottleneck time**
5. Ưu tiên sản xuất sản phẩm có tỷ lệ này CAO NHẤT
6. Phân bổ công suất bottleneck theo thứ tự ưu tiên cho đến khi hết công suất

> **Lưu ý**: Phương pháp này KHÁC với kế toán truyền thống. Kế toán thường ưu tiên sản phẩm có margin cao nhất, nhưng TOC ưu tiên margin/bottleneck minute cao nhất - có thể cho kết quả rất khác!

### Ví dụ thực tế
Nhà máy sản xuất 2 sản phẩm, bottleneck là máy CNC:

| | Sản phẩm A | Sản phẩm B |
|---|---|---|
| Giá bán | 100.000 VNĐ | 150.000 VNĐ |
| Chi phí biến đổi | 60.000 VNĐ | 100.000 VNĐ |
| Contribution Margin | 40.000 VNĐ | 50.000 VNĐ |
| Thời gian bottleneck | 10 phút | 25 phút |
| **Throughput/phút BN** | **4.000 VNĐ/phút** | **2.000 VNĐ/phút** |

Theo kế toán truyền thống: ưu tiên B (margin 50K > 40K)
Theo TOC: ưu tiên A (4.000/phút > 2.000/phút) → **ĐÚNG!**

Nếu bottleneck có 480 phút/ngày:
- Sản xuất hết nhu cầu A trước, rồi mới sản xuất B bằng thời gian còn lại

### Liên kết
- [[Theory of Constraints]]
- [[Contribution Margin]]
- [[Bottleneck]]
- [[Product Mix]]
- [[SA - Decision Making]]

---

## Line Balancing (Cân bằng dây chuyền)

### Định nghĩa (Definition)
[[Line Balancing]] là quá trình phân bổ công việc cho các trạm trên dây chuyền lắp ráp sao cho thời gian nhàn rỗi (idle time) được giảm thiểu và sản lượng đạt mục tiêu.

### Giải thích chi tiết

![Figure 6.5 - Line Balancing](/images/figures/ch06_fig6.5.jpg)
> *Figure 6.5: Cân bằng dây chuyền (Line Balancing) - phân bổ công việc cho các trạm để giảm thiểu thời gian nhàn rỗi*

**Các khái niệm quan trọng:**

- **[[Work Element]]** (Yếu tố công việc): Đơn vị công việc nhỏ nhất không thể chia nhỏ hơn
- **[[Precedence Diagram]]** (Sơ đồ thứ tự): Biểu diễn thứ tự bắt buộc của các yếu tố công việc
- **[[Cycle Time]]** (Thời gian chu kỳ): Thời gian tối đa cho phép tại mỗi trạm

$$\text{Cycle Time} (c) = \frac{1}{r} = \frac{\text{Available Time}}{\text{Desired Output}}$$

Trong đó $r$ là output rate mong muốn.

- **Số trạm tối thiểu theo lý thuyết:**

$$TM = \left\lceil\frac{\sum t_i}{c}\right\rceil$$

Trong đó $\sum t_i$ = tổng thời gian tất cả work elements, $c$ = cycle time, $\lceil \rceil$ = làm tròn lên.

- **[[Efficiency]]** (Hiệu quả dây chuyền):

$$\text{Efficiency} = \frac{\sum t_i}{nc} \times 100\%$$

Trong đó $n$ = số trạm thực tế, $c$ = cycle time.

- **[[Balance Delay]]** (Độ trễ cân bằng):

$$\text{Balance Delay} = 100\% - \text{Efficiency}$$

**Quy trình Line Balancing:**
1. Vẽ [[Precedence Diagram]]
2. Tính Cycle Time theo sản lượng mong muốn
3. Tính số trạm tối thiểu (TM)
4. Áp dụng quy tắc gán việc (ví dụ: [[Longest Task Time]] - ưu tiên việc dài nhất)
5. Gán work elements vào trạm sao cho không vượt cycle time và đúng thứ tự
6. Tính Efficiency, điều chỉnh nếu cần

![Figure 6.7 - Assembly Line Balancing](/images/figures/ch06_fig6.7.jpg)
> *Figure 6.7: Ví dụ cân bằng dây chuyền lắp ráp - Precedence Diagram, phân bổ work elements vào trạm và tính Efficiency*

### Rebalancing Assembly Line (Tái cân bằng dây chuyền)

Khi nào cần tái cân bằng:
- Nhu cầu thay đổi → cần thay đổi sản lượng → cycle time mới
- Thiết kế sản phẩm thay đổi → work elements thay đổi
- Muốn cải tiến hiệu quả dây chuyền
- Ở [[Lean Systems]], tái cân bằng theo [[Takt Time]]

### Ví dụ thực tế
Dây chuyền lắp ráp quạt điện, cần sản xuất 240 quạt/ngày (8 giờ):
- Cycle Time = 480 phút / 240 quạt = 2 phút/trạm
- Tổng thời gian công việc = 8 phút
- TM = ⌈8/2⌉ = 4 trạm tối thiểu
- Efficiency = 8/(4×2) = 100% (lý tưởng, thường khó đạt)

Nếu thực tế cần 5 trạm: Efficiency = 8/(5×2) = 80% → 20% thời gian nhàn rỗi.

### Liên kết
- [[Assembly Line]]
- [[Precedence Diagram]]
- [[Cycle Time]]
- [[Takt Time]]
- [[CH04 - Lean Systems]]
- [[Bottleneck]]

---

## Công thức quan trọng (Key Formulas)

| Chỉ số | Công thức | Ý nghĩa |
|--------|-----------|---------|
| Throughput/BN minute | $\frac{\text{Contribution Margin}}{\text{Bottleneck Time}}$ | Ưu tiên sản phẩm theo TOC |
| [[Cycle Time]] | $\frac{\text{Available Time}}{\text{Desired Output}}$ | Nhịp dây chuyền |
| Số trạm tối thiểu (TM) | $\lceil\frac{\sum t_i}{c}\rceil$ | Số trạm tối thiểu cần |
| [[Efficiency]] | $\frac{\sum t_i}{nc} \times 100\%$ | Hiệu quả dây chuyền |
| [[Balance Delay]] | $100\% - \text{Efficiency}$ | Phần trăm thời gian lãng phí |

---

## Từ khóa chính (Key Terms)

- [[Constraint Management]] - Quản lý ràng buộc
- [[Theory of Constraints]] (TOC) - Lý thuyết ràng buộc
- [[Bottleneck]] - Nút thắt cổ chai
- [[Eliyahu Goldratt]] - Cha đẻ của TOC
- [[Drum-Buffer-Rope]] (DBR) - Trống-Đệm-Dây
- [[Drum]] - Trống (nhịp bottleneck)
- [[Buffer]] - Đệm (tồn kho bảo vệ)
- [[Rope]] - Dây (tín hiệu kiểm soát)
- [[Throughput]] - Thông lượng
- [[Product Mix]] - Sản phẩm hỗn hợp
- [[Contribution Margin]] - Biên đóng góp
- [[Line Balancing]] - Cân bằng dây chuyền
- [[Work Element]] - Yếu tố công việc
- [[Precedence Diagram]] - Sơ đồ thứ tự
- [[Cycle Time]] - Thời gian chu kỳ
- [[Efficiency]] - Hiệu quả
- [[Balance Delay]] - Độ trễ cân bằng
- [[Assembly Line]] - Dây chuyền lắp ráp

---

> **Ghi chú ôn tập**: TOC là triết lý bổ sung cho [[Lean Systems]] và [[Six Sigma]]. Nhớ 5 bước tập trung (Identify → Exploit → Subordinate → Elevate → Repeat), nguyên tắc Product Mix theo TOC (throughput per bottleneck minute), và công thức Line Balancing. Chương này liên kết chặt với [[CH05 - Capacity Planning]] và [[CH04 - Lean Systems]].

