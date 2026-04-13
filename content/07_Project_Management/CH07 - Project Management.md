---
tags: [chapter-7, part2, project-management, CPM, critical-path, crashing, agile, scrum, WBS]
aliases: [Quản lý dự án, Project Management, OM Chapter 7]
---
# Chapter 7 - Project Management

## Tổng quan (Overview)

Chương 7 giới thiệu [[Project Management]] (Quản lý dự án) - lĩnh vực quản lý các hoạt động có thời điểm bắt đầu, kết thúc xác định, và tạo ra sản phẩm/kết quả duy nhất. Dự án khác với vận hành thường nhật: vận hành lặp đi lặp lại hàng ngày (sản xuất ô tô), dự án là duy nhất và tạm thời (xây một nhà máy mới).

Chương trình bày toàn bộ quy trình quản lý dự án từ A đến Z: xác định phạm vi ([[Scope]]), tổ chức nhóm, lập lịch bằng [[Critical Path Method]] (CPM), tối ưu chi phí-thời gian ([[Crashing]]), quản lý rủi ro, và giám sát tiến độ. Ngoài ra, chương giới thiệu phương pháp [[Agile]]/[[Scrum]] - cách tiếp cận linh hoạt phổ biến trong phát triển phần mềm.

Quản lý dự án là kỹ năng thiết yếu bất kể bạn làm ngành nào. Từ tổ chức đám cưới đến xây dựng nhà máy, mọi thứ đều là dự án.

---

## Defining and Organizing Projects (Xác định và tổ chức dự án)

### Scope (Phạm vi dự án)

#### Định nghĩa (Definition)
[[Project Scope]] là tuyên bố rõ ràng về mục tiêu, sản phẩm giao nộp (deliverables), mốc thời gian, và giới hạn của dự án. Scope trả lời: "Dự án này LÀM GÌ và KHÔNG LÀM GÌ?"

#### Giải thích chi tiết
- **[[Project Scope Statement]]**: Tài liệu chính thức mô tả phạm vi
- **[[Scope Creep]]** (Phình phạm vi): Phạm vi dự án mở rộng dần mà không kiểm soát → nguyên nhân #1 dự án thất bại!
- **[[Triple Constraint]]** (Tam giác ràng buộc): Mọi dự án bị ràng buộc bởi ba yếu tố: **Scope** (Phạm vi), **[[Schedule]]** (Thời gian), **[[Budget]]** (Chi phí). Thay đổi một yếu tố → ảnh hưởng hai yếu tố còn lại.

### Project Team (Nhóm dự án)

#### Giải thích chi tiết
- **[[Project Manager]]** (Quản lý dự án): Người chịu trách nhiệm tổng thể, điều phối mọi hoạt động
- **Cấu trúc tổ chức dự án:**
  - [[Functional Structure]]: Dự án quản lý trong phòng ban → phù hợp dự án nhỏ
  - [[Project Structure]]: Nhóm dự án riêng, tách khỏi phòng ban → phù hợp dự án lớn
  - [[Matrix Structure]]: Kết hợp cả hai → phổ biến nhất nhưng phức tạp nhất (nhân viên có hai sếp)

### Work Breakdown Structure (WBS)

#### Định nghĩa (Definition)
[[WBS]] (Work Breakdown Structure - Cấu trúc phân chia công việc) là sơ đồ phân chia dự án thành các công việc nhỏ hơn, dễ quản lý hơn, theo cấu trúc cây.

#### Giải thích chi tiết
- Cấp 1: Tên dự án
- Cấp 2: Các giai đoạn chính (phases)
- Cấp 3: Các gói công việc (work packages)
- Cấp 4: Các hoạt động cụ thể (activities)

**Quy tắc 100%**: Tổng công việc ở cấp dưới phải bằng 100% cấp trên.

### Ví dụ thực tế
WBS cho dự án "Mở nhà hàng mới":
```
1. Mở nhà hàng mới
   1.1 Chuẩn bị
       1.1.1 Nghiên cứu thị trường
       1.1.2 Lập kế hoạch kinh doanh
       1.1.3 Xin giấy phép
   1.2 Xây dựng
       1.2.1 Thiết kế nội thất
       1.2.2 Thi công
       1.2.3 Mua thiết bị bếp
   1.3 Vận hành
       1.3.1 Tuyển nhân viên
       1.3.2 Đào tạo
       1.3.3 Marketing khai trương
```

### Liên kết
- [[Project Scope]]
- [[WBS]]
- [[Triple Constraint]]
- [[Project Manager]]

---

## Constructing Project Networks (Xây dựng mạng dự án)

### AON Diagrams (Sơ đồ AON)

#### Định nghĩa (Definition)
[[AON]] (Activity-on-Node) là phương pháp biểu diễn mạng dự án trong đó mỗi NODE (nút/hình vuông) đại diện cho một hoạt động, và các MŨI TÊN thể hiện quan hệ thứ tự giữa các hoạt động.

#### Giải thích chi tiết

> ![Figure 7.3 - Sơ đồ mạng AON](/images/figures/ch07_fig7.3.jpg)
> *Figure 7.3: Activity-on-Node network diagram*

**Các mối quan hệ thứ tự ([[Precedence Relationship]]):**
- **[[Finish-to-Start]] (FS)**: A phải kết thúc trước khi B bắt đầu (phổ biến nhất)
  - Ví dụ: Đổ móng (A) → Xây tường (B)
- **[[Start-to-Start]] (SS)**: A và B bắt đầu cùng lúc
- **[[Finish-to-Finish]] (FF)**: A và B kết thúc cùng lúc
- **[[Start-to-Finish]] (SF)**: Hiếm dùng

**Thông tin trong mỗi node:**
```
┌──────────────┐
│  ES  | Dur | EF │
├──────────────┤
│  Activity ID     │
├──────────────┤
│  LS  | Slack| LF │
└──────────────┘
```

- **ES** (Early Start): Thời điểm bắt đầu sớm nhất
- **EF** (Early Finish): Thời điểm kết thúc sớm nhất = ES + Duration
- **LS** (Late Start): Thời điểm bắt đầu muộn nhất mà không trễ dự án
- **LF** (Late Finish): Thời điểm kết thúc muộn nhất
- **Duration**: Thời gian thực hiện
- **[[Slack]]**: Thời gian dự trữ = LS - ES = LF - EF

### Liên kết
- [[Critical Path Method]]
- [[Activity Slack]]
- [[Precedence Relationship]]
- [[Gantt Chart]]

---

## Developing Project Schedule (Lập lịch dự án)

### Critical Path Method (CPM) - Phương pháp đường găng

#### Định nghĩa (Definition)
[[Critical Path Method]] (CPM) là kỹ thuật xác định chuỗi hoạt động dài nhất trong dự án, quyết định thời gian hoàn thành TỐI THIỂU của dự án.

#### Giải thích chi tiết

> ![Figure 7.5 - Đường găng & Slack](/images/figures/ch07_fig7.5.jpg)
> *Figure 7.5: Forward/Backward pass xác định Critical Path và Activity Slack*

**[[Critical Path]]** (Đường găng) là chuỗi hoạt động liên tiếp dài nhất từ đầu đến cuối dự án. Đặc điểm:
- Tổng thời gian trên đường găng = thời gian hoàn thành dự án
- Mọi hoạt động trên đường găng có [[Slack]] = 0 (không có thời gian dự trữ)
- Nếu BẤT KỲ hoạt động nào trên đường găng bị trễ → TOÀN BỘ dự án bị trễ!

**Hai bước tính:**

**Bước 1: Forward Pass (Tính xuôi)** - Tính ES và EF
- Bắt đầu từ hoạt động đầu tiên
- ES = max(EF của tất cả hoạt động tiên quyết)
- EF = ES + Duration
- Kết quả: EF của hoạt động cuối = thời gian dự án

**Bước 2: Backward Pass (Tính ngược)** - Tính LS và LF
- Bắt đầu từ hoạt động cuối cùng
- LF = min(LS của tất cả hoạt động kế tiếp)
- LS = LF - Duration

**Xác định Critical Path:**
- Tính Slack = LS - ES (hoặc LF - EF) cho mỗi hoạt động
- Hoạt động có Slack = 0 nằm trên Critical Path

### Ví dụ thực tế
Dự án tổ chức sự kiện:

| Hoạt động | Mô tả | Thời gian (ngày) | Tiên quyết |
|-----------|-------|-------------------|------------|
| A | Lên ý tưởng | 3 | - |
| B | Thiết kế | 5 | A |
| C | Tìm địa điểm | 4 | A |
| D | Mời khách | 2 | B |
| E | Chuẩn bị logistics | 6 | C |
| F | Tổ chức | 1 | D, E |

**Forward Pass:**
- A: ES=0, EF=3
- B: ES=3, EF=8
- C: ES=3, EF=7
- D: ES=8, EF=10
- E: ES=3, EF=9... Sai! ES(E) = EF(C) = 7, EF(E) = 13
   
Sửa lại: C: ES=3, EF=7; E: ES=7, EF=13; F: ES=max(10,13)=13, EF=14

**Backward Pass:** LF(F)=14, LS(F)=13; LF(E)=13, LS(E)=7; LF(D)=13, LS(D)=11; LF(C)=7, LS(C)=3; LF(B)=11, LS(B)=6; LF(A)=3, LS(A)=0

**Slack:** A=0, B=3, C=0, D=3, E=0, F=0

**Critical Path: A → C → E → F** (tổng = 3+4+6+1 = 14 ngày)

→ Dự án mất ít nhất 14 ngày. Nếu "Chuẩn bị logistics" (E) trễ 1 ngày → dự án trễ 1 ngày. Nhưng "Thiết kế" (B) có thể trễ tới 3 ngày mà không ảnh hưởng.

### Liên kết
- [[Critical Path]]
- [[Activity Slack]]
- [[Gantt Chart]]
- [[Crashing]]

---

## Activity Slack (Thời gian dự trữ)

### Định nghĩa (Definition)
[[Activity Slack]] (hay [[Float]]) là khoảng thời gian một hoạt động có thể bị trì hoãn mà không ảnh hưởng đến ngày hoàn thành dự án.

### Giải thích chi tiết

$$\text{Slack} = LS - ES = LF - EF$$

- **Slack = 0**: Hoạt động nằm trên [[Critical Path]] → KHÔNG được phép trễ!
- **Slack > 0**: Hoạt động có "dư" thời gian → Quản lý dự án có thể:
  - Điều chuyển nguồn lực từ hoạt động có slack sang hoạt động critical
  - Linh hoạt hơn trong lập lịch
  - Nhưng CẢNH GIÁC: nếu dùng hết slack, hoạt động trở thành critical!

**[[Free Slack]]** vs **[[Total Slack]]:**
- **Total Slack**: Thời gian trì hoãn mà không ảnh hưởng đến DỰ ÁN
- **Free Slack**: Thời gian trì hoãn mà không ảnh hưởng đến HOẠT ĐỘNG TIẾP THEO

### Liên kết
- [[Critical Path Method]]
- [[Critical Path]]
- [[Resource Allocation]]

---

## Cost-Time Trade-Offs: Crashing (Đánh đổi chi phí-thời gian)

### Định nghĩa (Definition)
[[Crashing]] là kỹ thuật rút ngắn thời gian dự án bằng cách bổ sung nguồn lực (thêm người, làm thêm giờ, thuê ngoài) vào các hoạt động, với chi phí tăng thêm.

### Giải thích chi tiết

> ![Figure 7.7 - Đánh đổi Chi phí-Thời gian](/images/figures/ch07_fig7.7.jpg)
> *Figure 7.7: Crashing - tăng chi phí để rút ngắn thời gian dự án*

**Các khái niệm:**
- **[[Normal Time]]**: Thời gian hoàn thành bình thường
- **[[Crash Time]]**: Thời gian hoàn thành ngắn nhất có thể (với nguồn lực tối đa)
- **[[Normal Cost]]**: Chi phí khi thực hiện trong Normal Time
- **[[Crash Cost]]**: Chi phí khi thực hiện trong Crash Time (luôn cao hơn)

**Chi phí crash mỗi đơn vị thời gian:**
$$\text{Cost to Crash per Period} = \frac{\text{Crash Cost} - \text{Normal Cost}}{\text{Normal Time} - \text{Crash Time}}$$

**Quy trình Crashing:**
1. Xác định [[Critical Path]] hiện tại
2. Tính Cost to Crash cho mỗi hoạt động trên Critical Path
3. Crash hoạt động có chi phí crash THẤP NHẤT trên Critical Path
4. Crash đến khi:
   - Đạt thời gian mục tiêu, HOẶC
   - Critical Path thay đổi (có thể xuất hiện đường găng mới), HOẶC
   - Tất cả hoạt động trên Critical Path đã ở Crash Time
5. Nếu có nhiều Critical Path → phải crash hoạt động trên TẤT CẢ các đường găng cùng lúc

> **Lưu ý quan trọng**: Chỉ crash hoạt động trên Critical Path! Crash hoạt động không critical = lãng phí tiền.

### Ví dụ thực tế

| Hoạt động | Normal Time | Crash Time | Normal Cost | Crash Cost | Cost/Day |
|-----------|------------|------------|-------------|------------|----------|
| A (critical) | 8 ngày | 6 ngày | 40M | 52M | 6M/ngày |
| B (critical) | 6 ngày | 4 ngày | 30M | 42M | 6M/ngày |
| C (critical) | 10 ngày | 7 ngày | 50M | 71M | 7M/ngày |

Cần giảm 3 ngày:
- Crash A 2 ngày: chi phí thêm 12M (rẻ nhất, cùng giá với B)
- Crash B 1 ngày: chi phí thêm 6M
- Tổng chi phí crash: 18M
- (Không crash C vì đắt nhất: 7M/ngày)

### Liên kết
- [[Critical Path Method]]
- [[Critical Path]]
- [[Project Budget]]
- [[Resource Allocation]]

---

## Assessing and Analyzing Risks (Đánh giá và phân tích rủi ro)

### Statistical Analysis with PERT

#### Định nghĩa (Definition)
[[PERT]] (Program Evaluation and Review Technique) mở rộng CPM bằng cách xét đến sự không chắc chắn trong thời gian hoạt động, sử dụng 3 ước tính thời gian.

#### Giải thích chi tiết

**Ba ước tính thời gian:**
- $a$ = [[Optimistic Time]] (thời gian lạc quan - nhanh nhất)
- $m$ = [[Most Likely Time]] (thời gian khả năng nhất)
- $b$ = [[Pessimistic Time]] (thời gian bi quan - lâu nhất)

**Thời gian kỳ vọng:**
$$t_e = \frac{a + 4m + b}{6}$$

**Phương sai:**
$$\sigma^2 = \left(\frac{b - a}{6}\right)^2$$

**Phương sai đường găng** = Tổng phương sai các hoạt động trên Critical Path:
$$\sigma^2_{path} = \sum \sigma^2_i$$

**Xác suất hoàn thành dự án đúng hạn:**
$$z = \frac{T - T_E}{\sigma_{path}}$$

Trong đó $T$ = thời hạn mục tiêu, $T_E$ = thời gian kỳ vọng đường găng. Tra bảng [[Normal Distribution]] với giá trị $z$.

### Near-Critical Paths (Đường gần găng)

#### Định nghĩa (Definition)
[[Near-Critical Path]] là đường có tổng thời gian gần bằng Critical Path. Nếu hoạt động trên đường này bị trễ đủ lớn, nó có thể trở thành Critical Path mới.

#### Giải thích chi tiết
- Dự án có thể có NHIỀU đường gần găng
- Slack nhỏ → rủi ro cao vì dễ trở thành critical
- Quản lý tốt = theo dõi cả Critical Path lẫn Near-Critical Paths
- PERT giúp đánh giá rủi ro này vì xét đến biến động thời gian

### Liên kết
- [[PERT]]
- [[Critical Path]]
- [[Risk Management]]
- [[Normal Distribution]]
- [[Probability]]

---

## Scrum/Agile (Phương pháp linh hoạt)

### Định nghĩa (Definition)
[[Agile]] là phương pháp quản lý dự án linh hoạt, thay vì lập kế hoạch chi tiết từ đầu, dự án được chia thành các chu kỳ ngắn (iterations) với phản hồi liên tục. [[Scrum]] là framework Agile phổ biến nhất.

### Giải thích chi tiết

**So sánh Waterfall vs Agile:**

| | [[Waterfall]] (Truyền thống) | [[Agile]] |
|---|---|---|
| Kế hoạch | Chi tiết từ đầu | Linh hoạt, thay đổi được |
| Giao sản phẩm | Cuối dự án | Từng phần, liên tục |
| Phản hồi khách | Cuối dự án | Mỗi iteration |
| Thay đổi yêu cầu | Khó, tốn kém | Dễ, chào đón |
| Phù hợp | Dự án rõ ràng, ít thay đổi | Dự án sáng tạo, nhiều thay đổi |

**Framework Scrum:**

- **[[Product Backlog]]**: Danh sách tất cả yêu cầu/tính năng, sắp xếp theo ưu tiên
- **[[Sprint]]**: Chu kỳ phát triển ngắn (thường 2-4 tuần)
- **[[Sprint Backlog]]**: Danh sách công việc cho sprint hiện tại
- **[[Daily Standup]]** (Daily Scrum): Họp đứng 15 phút mỗi ngày - mỗi người trả lời 3 câu: Hôm qua làm gì? Hôm nay làm gì? Có vướng mắc gì?
- **[[Sprint Review]]**: Demo sản phẩm cuối sprint cho stakeholder
- **[[Sprint Retrospective]]**: Nhìn lại sprint - điều gì tốt, điều gì cần cải thiện

**Vai trò trong Scrum:**
- **[[Product Owner]]**: Đại diện khách hàng, quản lý Product Backlog
- **[[Scrum Master]]**: Hỗ trợ nhóm, loại bỏ trở ngại, KHÔNG phải quản lý
- **[[Development Team]]**: Nhóm tự tổ chức, đa kỹ năng, 5-9 người

### Ví dụ thực tế
Phát triển ứng dụng di động:
- Sprint 1 (2 tuần): Đăng nhập + Đăng ký → Demo cho khách hàng
- Sprint 2: Trang chủ + Danh mục sản phẩm → Khách hàng phản hồi
- Sprint 3: Giỏ hàng + Thanh toán → Khách hàng thấy app gần hoàn chỉnh
- Sprint 4: Tối ưu + Sửa lỗi → Ra mắt!

Thay vì chờ 2 tháng mới thấy sản phẩm (Waterfall), khách hàng thấy sản phẩm sau mỗi 2 tuần và có thể yêu cầu thay đổi.

### Liên kết
- [[Agile]]
- [[Scrum]]
- [[Sprint]]
- [[Iterative Development]]
- [[Continuous Improvement]]

---

## Monitoring and Controlling Projects (Giám sát và kiểm soát dự án)

### Giải thích chi tiết

**Các công cụ giám sát:**

1. **[[Gantt Chart]]** (Biểu đồ Gantt): Biểu đồ thanh ngang thể hiện lịch các hoạt động theo thời gian. Dễ đọc, trực quan, nhưng không thể hiện rõ mối quan hệ giữa các hoạt động.

2. **[[Earned Value Management]]** (EVM - Quản lý giá trị thu được): Phương pháp đo lường tiến độ dự án bằng cách kết hợp phạm vi, thời gian, và chi phí:
   - **[[Planned Value]]** (PV): Chi phí theo kế hoạch
   - **[[Earned Value]]** (EV): Giá trị công việc đã hoàn thành
   - **[[Actual Cost]]** (AC): Chi phí thực tế đã chi

   Các chỉ số:
   - **[[Schedule Variance]]** (SV) = EV - PV (SV < 0 → trễ tiến độ)
   - **[[Cost Variance]]** (CV) = EV - AC (CV < 0 → vượt ngân sách)
   - **[[Schedule Performance Index]]** (SPI) = EV/PV (SPI < 1 → trễ)
   - **[[Cost Performance Index]]** (CPI) = EV/AC (CPI < 1 → vượt chi phí)

3. **[[Status Reports]]**: Báo cáo định kỳ về tiến độ, vấn đề, rủi ro

4. **[[Change Control]]**: Quy trình kiểm soát thay đổi phạm vi, ngăn [[Scope Creep]]

### Ví dụ thực tế - EVM
Dự án xây nhà kế hoạch 100 ngày, ngân sách 1 tỷ VNĐ. Sau 50 ngày:
- PV (kế hoạch chi 500M) = 500M
- EV (công việc hoàn thành tương đương 400M) = 400M
- AC (thực tế đã chi 450M) = 450M

- SV = 400 - 500 = **-100M** → Trễ tiến độ (hoàn thành ít hơn kế hoạch)
- CV = 400 - 450 = **-50M** → Vượt ngân sách (chi nhiều hơn giá trị tạo ra)
- SPI = 400/500 = **0.80** → Chỉ hoàn thành 80% công việc kế hoạch
- CPI = 400/450 = **0.89** → Mỗi đồng chi ra chỉ tạo 0.89 đồng giá trị

→ Dự án đang có VẤN ĐỀ cả về tiến độ lẫn chi phí!

### Liên kết
- [[Gantt Chart]]
- [[Earned Value Management]]
- [[Scope Creep]]
- [[Change Control]]
- [[Risk Management]]

---

## Công thức quan trọng (Key Formulas)

| Chỉ số | Công thức | Ý nghĩa |
|--------|-----------|---------|
| EF | $ES + \text{Duration}$ | Thời điểm kết thúc sớm nhất |
| LS | $LF - \text{Duration}$ | Thời điểm bắt đầu muộn nhất |
| [[Slack]] | $LS - ES$ hoặc $LF - EF$ | Thời gian dự trữ |
| PERT $t_e$ | $\frac{a + 4m + b}{6}$ | Thời gian kỳ vọng |
| PERT $\sigma^2$ | $\left(\frac{b-a}{6}\right)^2$ | Phương sai thời gian |
| Crash Cost/Period | $\frac{CC - NC}{NT - CT}$ | Chi phí crash mỗi kỳ |
| [[Schedule Variance]] | $EV - PV$ | Sai lệch tiến độ |
| [[Cost Variance]] | $EV - AC$ | Sai lệch chi phí |
| [[SPI]] | $EV / PV$ | Chỉ số hiệu suất tiến độ |
| [[CPI]] | $EV / AC$ | Chỉ số hiệu suất chi phí |

---

## Từ khóa chính (Key Terms)

- [[Project Management]] - Quản lý dự án
- [[Project Scope]] - Phạm vi dự án
- [[WBS]] - Cấu trúc phân chia công việc
- [[Triple Constraint]] - Tam giác ràng buộc
- [[AON]] - Activity-on-Node
- [[Precedence Relationship]] - Quan hệ thứ tự
- [[Critical Path Method]] (CPM) - Phương pháp đường găng
- [[Critical Path]] - Đường găng
- [[Activity Slack]] / [[Float]] - Thời gian dự trữ
- [[Forward Pass]] - Tính xuôi
- [[Backward Pass]] - Tính ngược
- [[Crashing]] - Rút ngắn thời gian dự án
- [[Normal Time]] - Thời gian bình thường
- [[Crash Time]] - Thời gian rút ngắn tối đa
- [[PERT]] - Program Evaluation and Review Technique
- [[Near-Critical Path]] - Đường gần găng
- [[Agile]] - Phương pháp linh hoạt
- [[Scrum]] - Framework Scrum
- [[Sprint]] - Chu kỳ phát triển ngắn
- [[Product Backlog]] - Danh sách yêu cầu sản phẩm
- [[Product Owner]] - Chủ sản phẩm
- [[Scrum Master]] - Người hỗ trợ Scrum
- [[Gantt Chart]] - Biểu đồ Gantt
- [[Earned Value Management]] - Quản lý giá trị thu được
- [[Scope Creep]] - Phình phạm vi
- [[Project Manager]] - Quản lý dự án

---

> **Ghi chú ôn tập**: Chương 7 đòi hỏi THỰC HÀNH nhiều. Hãy luyện tập: (1) Vẽ AON diagram, (2) Tính Forward Pass và Backward Pass để tìm Critical Path, (3) Tính Crashing, (4) Tính PERT. Sử dụng [[Decision Tree]] từ [[SA - Decision Making]] khi có yếu tố không chắc chắn trong dự án.
