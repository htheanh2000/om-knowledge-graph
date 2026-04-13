---
tags: [chapter-10, part3, operations-planning, SOP, scheduling, sequencing, chase-strategy, level-strategy]
aliases: [Lập kế hoạch và Lịch trình vận hành, Operations Planning and Scheduling, S&OP]
---
# Chapter 10 - Operations Planning and Scheduling (Lập kế hoạch và Lịch trình vận hành)

## Tổng quan (Overview)

[[Operations Planning and Scheduling]] là quá trình chuyển đổi dự báo nhu cầu ([[Forecasting]]) thành kế hoạch hành động cụ thể: sản xuất bao nhiêu, khi nào, với nguồn lực nào. Chương này đi từ tầm chiến lược ([[S&OP - Sales and Operations Planning]]) xuống tầm chiến thuật ([[Scheduling]]) và tầm tác vụ ([[Sequencing]]).

Hãy tưởng tượng một kim tự tháp kế hoạch: trên cùng là [[S&OP]] (kế hoạch 3-18 tháng, mức tổng hợp), giữa là [[Master Production Schedule (MPS)]] (kế hoạch sản xuất chi tiết theo sản phẩm), và dưới cùng là [[Scheduling]] (ai làm gì, máy nào chạy đơn nào, vào lúc nào). Mỗi cấp cung cấp ràng buộc và hướng dẫn cho cấp dưới.

Đây là chương kết nối giữa [[Forecasting]] (dự báo) ở Chapter 8, [[Inventory Management]] ở Chapter 9, và [[Resource Planning]] ở Chapter 11. Nếu dự báo trả lời "cần bao nhiêu?", thì operations planning trả lời "làm thế nào để đáp ứng?"

---

## Levels in Operations Planning (Các cấp trong lập kế hoạch vận hành)


### Định nghĩa (Definition)
Hệ thống lập kế hoạch vận hành được tổ chức thành nhiều cấp, từ dài hạn/tổng quát đến ngắn hạn/chi tiết.

### Giải thích chi tiết (Detailed Explanation)

```
┌─────────────────────────────────────┐
│   S&OP (Sales & Operations Plan)    │  ← 3-18 tháng, mức product family
│   → Resource Planning               │
├─────────────────────────────────────┤
│   Master Production Schedule (MPS)  │  ← Vài tuần-vài tháng, mức sản phẩm
│   → Rough-Cut Capacity Planning     │
├─────────────────────────────────────┤
│   MRP (Material Requirements Plan)  │  ← Chi tiết linh kiện, nguyên liệu
│   → Capacity Requirements Planning  │
├─────────────────────────────────────┤
│   Scheduling & Sequencing           │  ← Ngày/giờ, mức công việc cụ thể
│   → Shop Floor Control              │
└─────────────────────────────────────┘
```

| Cấp | Tầm nhìn | Mức tổng hợp | Ví dụ |
|-----|----------|--------------|-------|
| [[S&OP - Sales and Operations Planning]] | 3-18 tháng | Product family | "Sản xuất 50.000 xe máy quý tới" |
| [[Master Production Schedule (MPS)]] | Vài tuần-tháng | Sản phẩm cụ thể | "Sản xuất 5.000 Wave Alpha tuần 12" |
| [[Material Requirements Planning (MRP)]] | Tuần | Linh kiện/nguyên liệu | "Cần 10.000 piston tuần 10" |
| [[Scheduling]] | Ngày/giờ | Công việc/máy | "Máy CNC #3 gia công piston 8h-12h thứ 2" |

### Liên kết (Related Concepts)
- [[Aggregate Planning]]
- [[Resource Planning]]
- [[Capacity Planning]]
- [[Demand Management]]

---

## S&OP Supply Options (Các lựa chọn cung ứng trong S&OP)

### Định nghĩa (Definition)
[[S&OP Supply Options]] là các "đòn bẩy" mà nhà quản lý có thể điều chỉnh để cân bằng năng lực sản xuất với nhu cầu.

### Giải thích chi tiết (Detailed Explanation)

#### Reactive Options (Phản ứng -- điều chỉnh cung theo cầu):

1. **Điều chỉnh [[Workforce Level]]** (Mức lao động)
   - Thuê thêm ([[Hiring]]) hoặc sa thải ([[Layoff]]) công nhân
   - Chi phí: tuyển dụng, đào tạo, sa thải (bồi thường, tinh thần giảm)
   - Ví dụ: Nhà máy Samsung Thái Nguyên tuyển thêm 5.000 công nhân trước mùa ra iPhone mới

2. **Điều chỉnh [[Work Schedule]]** (Lịch làm việc)
   - Tăng ca ([[Overtime]]) -- trả lương gấp 1.5-2 lần
   - Giảm giờ ([[Undertime]]) -- trả lương nhưng không sản xuất, lãng phí
   - Ví dụ: Nhà máy dệt tăng ca 4 tiếng/ngày trước Tết

3. **Điều chỉnh [[Inventory Level]]** (Mức tồn kho)
   - Sản xuất trước khi nhu cầu tăng → [[Anticipation Inventory]]
   - Tốn [[Holding Cost]] nhưng tránh tăng ca/thuê thêm người

4. **[[Subcontracting]]** (Thuê ngoài)
   - Thuê nhà sản xuất khác làm khi quá tải
   - Mất kiểm soát chất lượng, chi phí cao hơn tự sản xuất
   - Ví dụ: Nike thuê các nhà máy gia công ở Việt Nam

5. **[[Backlog]]** / **[[Backorder]]** (Đơn hàng tồn đọng)
   - Nhận đơn nhưng giao sau
   - Khách hàng phải chờ → giảm [[Customer Satisfaction]]

6. **[[Stockout]]** (Hết hàng)
   - Không nhận đơn, khách đi nơi khác
   - Rủi ro mất khách vĩnh viễn

#### Aggressive Options (Chủ động -- tác động cầu):
- [[Complementary Products]]: Sản phẩm bổ sung cân bằng mùa vụ
- [[Promotional Pricing]]: Giảm giá kích cầu mùa thấp
- [[Creative Pricing]]: "Happy Hour", giá ngoài giờ cao điểm

### Liên kết (Related Concepts)
- [[Capacity Planning]]
- [[Workforce Planning]]
- [[Inventory Management]]
- [[Demand Management]]

---

## S&OP Strategies (Chiến lược S&OP)

### Định nghĩa (Definition)
Hai chiến lược cực đoan trong [[S&OP - Sales and Operations Planning]]: [[Chase Strategy]] và [[Level Strategy]]. Thực tế, hầu hết doanh nghiệp dùng [[Mixed Strategy]] kết hợp cả hai.

### Giải thích chi tiết (Detailed Explanation)


#### [[Chase Strategy]] (Chiến lược đuổi theo / Chiến lược theo sát nhu cầu)

**Nguyên tắc**: Điều chỉnh **sản lượng** (qua thuê/sa thải hoặc tăng ca) để khớp chính xác với nhu cầu mỗi kỳ.

| Ưu điểm | Nhược điểm |
|----------|-----------|
| Tồn kho gần = 0 | Chi phí thuê/sa thải cao |
| Không tốn [[Holding Cost]] | Tinh thần nhân viên thấp |
| Phản ứng nhanh với thị trường | Chất lượng không ổn định (nhân viên mới) |
| | Chi phí đào tạo liên tục |

**Phù hợp khi**: Chi phí lưu giữ rất cao, sản phẩm dễ hỏng ([[Perishable]]), lao động linh hoạt.

**Ví dụ**: Công ty du lịch thuê hướng dẫn viên thời vụ vào mùa hè, giải phóng vào mùa đông. Nhà máy chế biến thủy sản ở miền Tây tuyển thêm công nhân mùa nước nổi khi tôm cá dồi dào.

#### [[Level Strategy]] (Chiến lược cân bằng / Chiến lược ổn định)

**Nguyên tắc**: Giữ **sản lượng/nhân lực ổn định**, dùng tồn kho hoặc backlog để điều chỉnh chênh lệch cung-cầu.

| Ưu điểm | Nhược điểm |
|----------|-----------|
| Lao động ổn định, tinh thần cao | [[Holding Cost]] tồn kho cao |
| Năng suất ổn định | Có thể phải backlog hoặc stockout |
| Chất lượng đồng đều | Vốn bị "chôn" trong tồn kho |
| Dễ lập kế hoạch | |

**Phù hợp khi**: Chi phí thuê/sa thải cao, yêu cầu kỹ năng cao, nhân lực khó tìm.

**Ví dụ**: Vinamilk duy trì nhân lực sản xuất ổn định quanh năm, sản xuất sữa tích trữ trước Tết ([[Anticipation Inventory]]).

#### [[Mixed Strategy]] (Chiến lược hỗn hợp)

Kết hợp linh hoạt: giữ lực lượng cốt lõi ổn định (Level), dùng overtime và subcontracting cho peak (Chase).

### Ví dụ thực tế (Real-world Example)

| Tháng | Nhu cầu | Chase (sx = cầu) | Level (sx = 400/tháng) |
|-------|---------|------------------|----------------------|
| 1 | 300 | Sx 300, sa thải bớt | Sx 400, tồn kho +100 |
| 2 | 350 | Sx 350 | Sx 400, tồn kho +150 |
| 3 | 500 | Sx 500, thuê thêm | Sx 400, tồn kho +50 |
| 4 | 600 | Sx 600, thuê thêm | Sx 400, dùng tồn kho -150 |
| 5 | 450 | Sx 450, sa thải bớt | Sx 400, dùng tồn kho -200 |
| 6 | 200 | Sx 200, sa thải nhiều | Sx 400, tồn kho +0 |

### Liên kết (Related Concepts)
- [[Aggregate Planning]]
- [[Workforce Planning]]
- [[Inventory Management]]
- [[Holding Cost]]
- [[Hiring and Layoff Costs]]

---

## Constraints and Costs (Ràng buộc và Chi phí)

### Định nghĩa (Definition)
Khi lập kế hoạch S&OP, cần xem xét các ràng buộc thực tế và các loại chi phí liên quan.

### Giải thích chi tiết (Detailed Explanation)

#### Constraints (Ràng buộc):
- **[[Capacity Constraints]]**: Công suất máy móc, nhà xưởng có giới hạn
- **[[Workforce Constraints]]**: Số lao động có sẵn, luật lao động (giới hạn overtime)
- **[[Material Constraints]]**: Nguyên vật liệu có sẵn, [[Lead Time]] cung cấp
- **[[Storage Constraints]]**: Kho bãi có giới hạn
- **[[Policy Constraints]]**: Chính sách công ty (ví dụ: không sa thải quá 10%/quý)

#### Costs (Chi phí trong S&OP):
1. **[[Regular Time Cost]]**: Lương cơ bản
2. **[[Overtime Cost]]**: Lương tăng ca (thường 150-200% lương cơ bản)
3. **[[Hiring Cost]]**: Tuyển dụng + đào tạo nhân viên mới
4. **[[Layoff Cost]]**: Bồi thường, thủ tục sa thải
5. **[[Holding Cost]]**: Chi phí lưu giữ tồn kho
6. **[[Backorder Cost]]**: Chi phí xử lý đơn trễ + mất uy tín
7. **[[Stockout Cost]]**: Mất doanh thu + mất khách hàng
8. **[[Subcontracting Cost]]**: Chi phí thuê ngoài (thường > chi phí tự sản xuất)

### Liên kết (Related Concepts)
- [[S&OP - Sales and Operations Planning]]
- [[Linear Programming]]
- [[Optimization]]

---

## Sales and Operations Planning as a Process (S&OP như một quy trình)

### Định nghĩa (Definition)
[[S&OP - Sales and Operations Planning]] không chỉ là bài toán tối ưu mà là **quy trình quản lý** liên phòng ban, diễn ra hàng tháng.

### Giải thích chi tiết (Detailed Explanation)

#### 5 bước quy trình S&OP hàng tháng:

1. **Data Gathering** (Thu thập dữ liệu): Cập nhật [[Forecasting]], đơn hàng thực tế, tồn kho, năng lực
2. **Demand Planning** (Lập kế hoạch nhu cầu): [[Marketing]] và [[Sales]] thống nhất dự báo nhu cầu
3. **Supply Planning** (Lập kế hoạch cung ứng): [[Operations]] xác định cách đáp ứng (sản xuất, tồn kho, thuê ngoài)
4. **Pre-S&OP Meeting** (Họp chuẩn bị): Các phòng ban giải quyết mâu thuẫn, đề xuất phương án
5. **Executive S&OP Meeting** (Họp ban lãnh đạo): CEO/COO phê duyệt kế hoạch cuối cùng

**Yếu tố thành công**:
- Cam kết từ lãnh đạo cấp cao
- Hợp tác liên phòng ban ([[Cross-Functional Collaboration]])
- Dữ liệu chính xác và kịp thời
- [[Consensus]] (đồng thuận) -- không phải chỉ một phòng ban quyết định

### Ví dụ thực tế (Real-world Example)
VinFast mỗi tháng tổ chức S&OP meeting: Sales báo cáo đơn đặt xe VF8/VF9 từ các đại lý, Operations đánh giá công suất nhà máy Hải Phòng, Supply Chain kiểm tra nguồn cung pin LFP, Finance đánh giá ngân sách. CEO phê duyệt kế hoạch sản xuất 3 tháng tới.

### Liên kết (Related Concepts)
- [[Cross-Functional Teams]]
- [[Enterprise Resource Planning (ERP)]]
- [[Demand Management]]
- [[Capacity Planning]]

---

## Spreadsheets for S&OP (Bảng tính cho S&OP)

### Định nghĩa (Definition)
Bảng tính Excel/Google Sheets là công cụ phổ biến nhất để lập và so sánh các phương án [[S&OP - Sales and Operations Planning]].

### Giải thích chi tiết (Detailed Explanation)

#### Cấu trúc bảng tính S&OP điển hình:

| | T1 | T2 | T3 | T4 | T5 | T6 | Tổng |
|---|---|---|---|---|---|---|---|
| **Nhu cầu (Forecast)** | 300 | 350 | 500 | 600 | 450 | 200 | 2.400 |
| **Sản xuất (Regular)** | 400 | 400 | 400 | 400 | 400 | 400 | 2.400 |
| **Overtime** | 0 | 0 | 0 | 100 | 0 | 0 | 100 |
| **Subcontract** | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **Tổng cung** | 400 | 400 | 400 | 500 | 400 | 400 | 2.500 |
| **Tồn kho cuối kỳ** | 100 | 150 | 50 | -50 | -100 | 100 | — |
| **Backlog** | 0 | 0 | 0 | 50 | 100 | 0 | — |

#### Tính chi phí:

| Loại chi phí | Đơn giá | Số lượng | Tổng |
|-------------|---------|----------|------|
| Regular time | 500K/đvị | 2.400 | 1.200M |
| Overtime | 750K/đvị | 100 | 75M |
| Tồn kho | 20K/đvị/tháng | Σ tồn kho | ... |
| Backorder | 50K/đvị/tháng | Σ backlog | ... |
| **Tổng** | | | **...** |

So sánh nhiều phương án (Chase vs Level vs Mixed) → chọn phương án có **tổng chi phí thấp nhất** hoặc cân bằng tốt nhất giữa chi phí và các yếu tố khác (tinh thần nhân viên, rủi ro...).

### Liên kết (Related Concepts)
- [[S&OP - Sales and Operations Planning]]
- [[Chase Strategy]]
- [[Level Strategy]]
- [[Total Cost]]

---

## Workforce and Workstation Scheduling (Lập lịch lao động và trạm làm việc)

### Định nghĩa (Definition)
[[Workforce Scheduling]] xác định lịch làm việc cụ thể cho từng nhân viên/nhóm, đặc biệt quan trọng trong ngành dịch vụ hoạt động 24/7.

### Giải thích chi tiết (Detailed Explanation)

#### Bài toán lập lịch nhân viên:
- **Đầu vào**: Nhu cầu nhân lực mỗi ngày/ca, ràng buộc (mỗi người làm 5 ngày nghỉ 2 ngày liên tiếp)
- **Đầu ra**: Lịch làm việc cụ thể

#### Phương pháp giải:
1. Xác định nhu cầu nhân lực tối thiểu mỗi ngày
2. Phân bổ nhân viên sao cho đủ người mỗi ngày
3. Tối ưu để giảm tổng nhân lực cần thiết

#### Ví dụ: Bài toán "2 ngày nghỉ liên tiếp"
- Bước 1: Tìm 2 ngày liên tiếp có nhu cầu thấp nhất
- Bước 2: Gán nhân viên nghỉ 2 ngày đó
- Bước 3: Giảm nhu cầu các ngày làm việc đi 1
- Bước 4: Lặp lại cho nhân viên tiếp theo

### Ví dụ thực tế (Real-world Example)
Bệnh viện Bạch Mai cần lập lịch trực cho y tá:
- Ca sáng (7h-15h): cần 10 y tá
- Ca chiều (15h-23h): cần 8 y tá
- Ca đêm (23h-7h): cần 4 y tá
- Mỗi y tá làm 5 ca/tuần, 2 ngày nghỉ liên tiếp
- Cuối tuần cần ít hơn ngày thường

### Liên kết (Related Concepts)
- [[Scheduling]]
- [[Service Operations]]
- [[Capacity Planning]]
- [[Shift Scheduling]]

---

## Job and Facility Scheduling (Lập lịch công việc và cơ sở vật chất)

### Định nghĩa (Definition)
[[Job Scheduling]] là gán các công việc cụ thể cho máy/trạm làm việc, xác định thứ tự và thời gian thực hiện.

### Giải thích chi tiết (Detailed Explanation)

#### Các khái niệm quan trọng:

- **[[Job]]**: Một đơn hàng hoặc lô công việc cần hoàn thành
- **[[Machine]]** / **[[Workstation]]**: Nơi thực hiện công việc
- **[[Processing Time]]** ($p_j$): Thời gian xử lý job j
- **[[Due Date]]** ($d_j$): Hạn giao hàng
- **[[Flow Time]]**: Tổng thời gian job ở trong hệ thống (chờ + xử lý)
- **[[Makespan]]**: Thời gian hoàn thành tất cả các job
- **[[Tardiness]]** ($T_j$): max(0, Completion time - Due date) -- số ngày trễ hạn
- **[[Lateness]]** ($L_j$): Completion time - Due date (có thể âm nếu sớm hạn)

#### Gantt Chart (Biểu đồ Gantt):
Công cụ trực quan để theo dõi lịch trình, hiển thị thời gian bắt đầu/kết thúc mỗi job trên mỗi máy.

### Liên kết (Related Concepts)
- [[Scheduling]]
- [[Sequencing]]
- [[Shop Floor Control]]

---

## Sequencing Jobs: Priority Rules (Sắp xếp thứ tự: Quy tắc ưu tiên)

### Định nghĩa (Definition)
[[Sequencing]] (sắp xếp thứ tự) xác định thứ tự các job được xử lý trên một hoặc nhiều máy. [[Priority Rules]] (quy tắc ưu tiên) là các luật đơn giản để quyết định thứ tự.

### Giải thích chi tiết (Detailed Explanation)

#### Các [[Priority Rules]] phổ biến:

| Quy tắc | Tên đầy đủ | Nguyên tắc | Ưu/nhược điểm |
|---------|-----------|-----------|---------------|
| **[[FCFS]]** | First Come First Served | Đến trước làm trước | Công bằng nhưng không tối ưu |
| **[[SPT]]** | Shortest Processing Time | Job ngắn nhất làm trước | Giảm flow time TB, **tốt nhất cho WIP** |
| **[[EDD]]** | Earliest Due Date | Hạn sớm nhất làm trước | **Giảm tardiness tối đa** |
| **[[CR]]** | Critical Ratio | CR = (Due date - Now) / Processing time remaining; nhỏ nhất trước | Cân bằng giữa hạn và thời gian còn lại |
| **[[LPT]]** | Longest Processing Time | Job dài nhất làm trước | Dùng cho scheduling trên nhiều máy |
| **[[S-RO|S/RO]]** | Slack per Remaining Operations | Slack/Số công đoạn còn lại; nhỏ nhất trước | Xem xét nhiều công đoạn |

#### Đo lường hiệu quả:
- **Average Flow Time** (Thời gian trung bình trong hệ thống): $\bar{F} = \frac{\sum F_j}{n}$
- **Average Tardiness** (Trễ hạn trung bình): $\bar{T} = \frac{\sum T_j}{n}$
- **Number of Tardy Jobs** (Số job trễ hạn)
- **Makespan** (Thời gian hoàn thành tổng)

### Ví dụ thực tế (Real-world Example)

**Bài toán**: Xưởng in Đà Nẵng có 5 đơn hàng chờ xử lý trên 1 máy in:

| Job | Processing Time (ngày) | Due Date (ngày) |
|-----|----------------------|----------------|
| A | 3 | 5 |
| B | 1 | 3 |
| C | 4 | 8 |
| D | 2 | 4 |
| E | 5 | 10 |

**Theo SPT** (B→D→A→C→E):

| Job | PT | Completion | Due | Tardiness |
|-----|----|-----------|-----|-----------|
| B | 1 | 1 | 3 | 0 |
| D | 2 | 3 | 4 | 0 |
| A | 3 | 6 | 5 | 1 |
| C | 4 | 10 | 8 | 2 |
| E | 5 | 15 | 10 | 5 |

- Avg Flow Time = (1+3+6+10+15)/5 = **7.0 ngày**
- Avg Tardiness = (0+0+1+2+5)/5 = **1.6 ngày**

**Theo EDD** (B→D→A→C→E):

Trùng với SPT trong ví dụ này! Nhưng nếu thay đổi due date → kết quả khác nhau.

**Theo FCFS** (A→B→C→D→E):

| Job | PT | Completion | Due | Tardiness |
|-----|----|-----------|-----|-----------|
| A | 3 | 3 | 5 | 0 |
| B | 1 | 4 | 3 | 1 |
| C | 4 | 8 | 8 | 0 |
| D | 2 | 10 | 4 | 6 |
| E | 5 | 15 | 10 | 5 |

- Avg Flow Time = (3+4+8+10+15)/5 = **8.0 ngày**
- Avg Tardiness = (0+1+0+6+5)/5 = **2.4 ngày**

→ SPT cho flow time tốt hơn FCFS (7.0 vs 8.0)

#### [[Johnson's Rule]] (cho 2 máy tuần tự):
Khi n job phải qua máy 1 rồi máy 2:
1. Tìm thời gian xử lý nhỏ nhất trong tất cả
2. Nếu thời gian đó ở máy 1 → xếp job đầu danh sách
3. Nếu thời gian đó ở máy 2 → xếp job cuối danh sách
4. Loại job đó, lặp lại

### Liên kết (Related Concepts)
- [[Scheduling]]
- [[Operations Planning and Scheduling]]
- [[Lean Operations]]
- [[Theory of Constraints (TOC)]]
- [[Bottleneck]]
- [[Gantt Chart]]

---

## Công thức quan trọng (Key Formulas)

| Công thức | Ký hiệu | Mô tả |
|-----------|----------|-------|
| $\bar{F} = \frac{\sum F_j}{n}$ | Average [[Flow Time]] | Thời gian TB trong hệ thống |
| $\bar{T} = \frac{\sum T_j}{n}$ | Average [[Tardiness]] | Trễ hạn trung bình |
| $T_j = \max(0, C_j - d_j)$ | [[Tardiness]] | Số ngày trễ hạn |
| $CR_j = \frac{d_j - t_{now}}{p_j}$ | [[Critical Ratio]] | Tỷ lệ tới hạn |
| $\text{WIP} = \lambda \times \bar{F}$ | [[Little's Law]] | WIP = Tốc độ đến × Flow time |

---

## Từ khóa chính (Key Terms)

- [[Operations Planning and Scheduling]] - Lập kế hoạch và lịch trình vận hành
- [[S&OP - Sales and Operations Planning]] - Kế hoạch bán hàng và vận hành
- [[Chase Strategy]] - Chiến lược đuổi theo
- [[Level Strategy]] - Chiến lược cân bằng
- [[Mixed Strategy]] - Chiến lược hỗn hợp
- [[Overtime]] - Tăng ca
- [[Subcontracting]] - Thuê ngoài
- [[Anticipation Inventory]] - Tồn kho dự trù
- [[Backlog]] - Đơn hàng tồn đọng
- [[Workforce Scheduling]] - Lập lịch lao động
- [[Scheduling]] - Lập lịch trình
- [[Sequencing]] - Sắp xếp thứ tự
- [[Priority Rules]] - Quy tắc ưu tiên
- [[FCFS]] - Đến trước phục vụ trước
- [[SPT]] - Thời gian xử lý ngắn nhất
- [[EDD]] - Hạn giao sớm nhất
- [[Critical Ratio]] - Tỷ lệ tới hạn
- [[Johnson's Rule]] - Luật Johnson (2 máy)
- [[Flow Time]] - Thời gian trong hệ thống
- [[Makespan]] - Thời gian hoàn thành tổng
- [[Tardiness]] - Trễ hạn
- [[Gantt Chart]] - Biểu đồ Gantt


---
## Hình minh họa từ sách (Textbook Figures)

![Figure 10.1](/images/figures/ch10_fig10.1.jpg)
> *Figure 10.1*

![Figure 10.10](/images/figures/ch10_fig10.10.jpg)
> *Figure 10.10*

![Figure 10.11](/images/figures/ch10_fig10.11.jpg)
> *Figure 10.11*

![Figure 10.2](/images/figures/ch10_fig10.2.jpg)
> *Figure 10.2*

![Figure 10.3](/images/figures/ch10_fig10.3.jpg)
> *Figure 10.3*

![Figure 10.4](/images/figures/ch10_fig10.4.jpg)
> *Figure 10.4*

![Figure 10.5](/images/figures/ch10_fig10.5.jpg)
> *Figure 10.5*

![Figure 10.6](/images/figures/ch10_fig10.6.jpg)
> *Figure 10.6*

![Figure 10.7](/images/figures/ch10_fig10.7.jpg)
> *Figure 10.7*

![Figure 10.8](/images/figures/ch10_fig10.8.jpg)
> *Figure 10.8*

![Figure 10.9](/images/figures/ch10_fig10.9.jpg)
> *Figure 10.9*

