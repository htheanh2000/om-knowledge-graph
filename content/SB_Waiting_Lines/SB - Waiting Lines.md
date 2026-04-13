---
tags: [supplement-B, waiting-lines, queueing-theory, littles-law, service-operations]
aliases: [Hàng chờ, Waiting Lines, Supplement B, Phụ lục B, Lý thuyết hàng chờ]
---
# Supplement B - Waiting Lines

## Tổng quan (Overview)

Phụ lục B giới thiệu [[Waiting-Line Models]] (Mô hình hàng chờ), hay còn gọi là [[Queueing Theory]] (Lý thuyết hàng chờ). Đây là công cụ toán học giúp phân tích và tối ưu hóa các hệ thống mà khách hàng phải xếp hàng chờ đợi để được phục vụ.

Hàng chờ xuất hiện ở khắp nơi trong cuộc sống: xếp hàng ở siêu thị, chờ khám bệnh, chờ cuộc gọi được kết nối với tổng đài, chờ trang web tải... Vấn đề cốt lõi là sự ĐÁNH ĐỔI: thêm server (quầy phục vụ) → giảm thời gian chờ nhưng tăng chi phí; giảm server → giảm chi phí nhưng khách chờ lâu hơn.

Hiểu mô hình hàng chờ giúp bạn ra quyết định [[Capacity Planning]] chính xác hơn, đặc biệt trong ngành dịch vụ.

---

## Structure of Waiting-Line Problems (Cấu trúc bài toán hàng chờ)

### Định nghĩa (Definition)
Mọi hệ thống hàng chờ đều có ba thành phần: [[Customer Population]] (nguồn khách hàng), [[Service System]] (hệ thống phục vụ), và [[Priority Rule]] (quy tắc ưu tiên).

### Giải thích chi tiết

#### 1. Customer Population (Nguồn khách hàng)

[[Customer Population]] mô tả nguồn mà khách hàng đến từ đó:

- **[[Infinite Population]]** (Nguồn vô hạn): Số khách tiềm năng rất lớn, khách đến không ảnh hưởng đáng kể đến tỷ lệ đến. Ví dụ: khách hàng đến siêu thị, người gọi đến tổng đài.
- **[[Finite Population]]** (Nguồn hữu hạn): Số khách tiềm năng nhỏ, khi một khách đang được phục vụ thì nguồn giảm. Ví dụ: 10 máy trong xưởng có thể hỏng → khi 3 máy đang sửa, chỉ còn 7 máy có thể hỏng tiếp.

#### 2. Service System (Hệ thống phục vụ)

Gồm hai đặc điểm:
- **Arrangement** (Cách sắp xếp):
  - [[Single-Server Single-Phase]]: 1 quầy, 1 bước (ví dụ: quầy thanh toán một nhân viên)
  - [[Single-Server Multiple-Phase]]: 1 quầy, nhiều bước (ví dụ: rửa xe tự động - rửa → xả → sấy)
  - [[Multiple-Server Single-Phase]]: Nhiều quầy, 1 bước (ví dụ: nhiều quầy thu ngân siêu thị)
  - [[Multiple-Server Multiple-Phase]]: Nhiều quầy, nhiều bước (ví dụ: khám bệnh → xét nghiệm → lấy thuốc, mỗi bước có nhiều phòng)

- **Number of Servers**: Số quầy phục vụ song song ($s$)

#### 3. Priority Rule (Quy tắc ưu tiên)

[[Priority Rule]] xác định ai được phục vụ trước:
- **[[FCFS]]** (First-Come, First-Served): Ai đến trước phục vụ trước - phổ biến nhất
- **[[Priority Scheduling]]**: Phục vụ theo mức ưu tiên (ví dụ: cấp cứu trước khám thường)
- **[[Shortest Processing Time]]** (SPT): Phục vụ việc nhanh nhất trước
- **[[Earliest Due Date]]** (EDD): Phục vụ việc gấp nhất trước

### Ví dụ thực tế
Phòng khám đa khoa:
- **Customer Population**: Infinite (nhiều bệnh nhân có thể đến)
- **Service System**: Multiple-Server Multiple-Phase (nhiều bác sĩ, qua nhiều bước: đăng ký → khám → xét nghiệm → kê đơn)
- **Priority Rule**: Kết hợp - cấp cứu ưu tiên, còn lại FCFS

### Liên kết
- [[Capacity Planning]]
- [[CH05 - Capacity Planning]]
- [[Service Process]]

---

## Probability Distributions (Phân phối xác suất)

### Arrival Distribution (Phân phối thời gian đến)

#### Định nghĩa (Definition)
[[Arrival Rate]] ($\lambda$ - lambda) là số khách hàng trung bình đến hệ thống trong một đơn vị thời gian.

#### Giải thích chi tiết
- Thường tuân theo [[Poisson Distribution]] (Phân phối Poisson):

$$P(n) = \frac{e^{-\lambda}\lambda^n}{n!}$$

Trong đó $P(n)$ là xác suất có đúng $n$ khách đến trong một khoảng thời gian, $\lambda$ là số khách đến trung bình.

- Poisson phù hợp khi: khách đến độc lập với nhau, tỷ lệ đến ổn định, hai khách không đến cùng lúc.
- Khoảng thời gian giữa hai lần đến tuân theo [[Exponential Distribution]].

### Service Time Distribution (Phân phối thời gian phục vụ)

#### Định nghĩa (Definition)
[[Service Rate]] ($\mu$ - mu) là số khách hàng trung bình được phục vụ xong trong một đơn vị thời gian (bởi MỘT server).

#### Giải thích chi tiết
- Thời gian phục vụ thường tuân theo [[Exponential Distribution]] (Phân phối mũ):

$$P(t \leq T) = 1 - e^{-\mu T}$$

- Đặc điểm: Phần lớn khách được phục vụ nhanh, một số ít mất rất lâu
- Điều kiện hệ thống ổn định: $\lambda < s\mu$ (tỷ lệ đến < tổng khả năng phục vụ)

> **Điều kiện quan trọng**: $\rho = \frac{\lambda}{s\mu} < 1$ (hệ số sử dụng phải nhỏ hơn 1, nếu không hàng chờ sẽ dài vô hạn!)

### Liên kết
- [[Poisson Distribution]]
- [[Exponential Distribution]]
- [[Probability]]
- [[Statistical Analysis]]

---

## Single-Server Model (Mô hình một quầy phục vụ)

### Định nghĩa (Definition)
[[Single-Server Model]] (M/M/1) là mô hình hàng chờ đơn giản nhất với một server, arrival theo Poisson, service time theo Exponential, hàng chờ vô hạn, FCFS.

### Giải thích chi tiết

**Ký hiệu Kendall**: M/M/1
- M thứ nhất: Markovian arrival (Poisson)
- M thứ hai: Markovian service (Exponential)
- 1: Một server

**Các công thức quan trọng:**

| Ký hiệu | Công thức | Ý nghĩa |
|----------|-----------|---------|
| $\rho$ | $\frac{\lambda}{\mu}$ | [[Utilization]] - hệ số sử dụng server |
| $L$ | $\frac{\lambda}{\mu - \lambda}$ | Số khách trung bình trong HỆ THỐNG (chờ + phục vụ) |
| $L_q$ | $\frac{\lambda^2}{\mu(\mu - \lambda)}$ | Số khách trung bình trong HÀNG CHỜ |
| $W$ | $\frac{1}{\mu - \lambda}$ | Thời gian trung bình trong HỆ THỐNG |
| $W_q$ | $\frac{\lambda}{\mu(\mu - \lambda)}$ | Thời gian trung bình trong HÀNG CHỜ |
| $P_0$ | $1 - \frac{\lambda}{\mu}$ | Xác suất hệ thống trống (không có khách) |
| $P_n$ | $(1-\rho)\rho^n$ | Xác suất có đúng $n$ khách trong hệ thống |

### Ví dụ thực tế
Quầy ATM duy nhất tại một ngân hàng:
- Khách đến: $\lambda = 20$ người/giờ
- Phục vụ: $\mu = 30$ người/giờ (mỗi giao dịch trung bình 2 phút)

| Chỉ số | Tính toán | Kết quả |
|--------|-----------|---------|
| $\rho$ | 20/30 | 66.7% |
| $L$ | 20/(30-20) | 2 người trong hệ thống |
| $L_q$ | 20²/(30×10) | 1.33 người chờ |
| $W$ | 1/(30-20) | 0.1 giờ = 6 phút |
| $W_q$ | 20/(30×10) | 0.067 giờ = 4 phút chờ |

→ Trung bình khách chờ 4 phút trước khi đến lượt, tổng thời gian tại ATM là 6 phút.

### Liên kết
- [[Little's Law]]
- [[Utilization]]
- [[Multiple-Server Model]]

---

## Multiple-Server Model (Mô hình nhiều quầy phục vụ)

### Định nghĩa (Definition)
[[Multiple-Server Model]] (M/M/s) là mô hình hàng chờ với $s$ server giống nhau hoạt động song song, một hàng chờ chung.

### Giải thích chi tiết

**Ký hiệu Kendall**: M/M/s (s = số server)

**Điều kiện ổn định**: $\rho = \frac{\lambda}{s\mu} < 1$

**Các công thức phức tạp hơn** (thường dùng bảng tra hoặc phần mềm):

Xác suất hệ thống trống:
$$P_0 = \left[\sum_{n=0}^{s-1} \frac{(\lambda/\mu)^n}{n!} + \frac{(\lambda/\mu)^s}{s!} \cdot \frac{1}{1 - \rho}\right]^{-1}$$

Số khách trung bình trong hàng chờ:
$$L_q = \frac{P_0 (\lambda/\mu)^s \rho}{s!(1-\rho)^2}$$

Sau khi có $L_q$, dùng [[Little's Law]] để tính:
- $W_q = L_q / \lambda$
- $W = W_q + 1/\mu$
- $L = \lambda W$

### Ví dụ thực tế
Siêu thị có 3 quầy thu ngân ($s = 3$), $\lambda = 10$ khách/giờ, $\mu = 4$ khách/giờ/quầy:
- $\rho = 10/(3 \times 4) = 0.833$ (83.3%)
- Dùng bảng tra hoặc phần mềm: $L_q \approx 2.59$ khách chờ
- $W_q = 2.59/10 = 0.259$ giờ ≈ 15.5 phút chờ

Nếu thêm 1 quầy ($s = 4$): $\rho = 10/16 = 0.625$, $L_q \approx 0.17$, $W_q \approx 1$ phút. Thêm 1 quầy giảm thời gian chờ từ 15.5 phút xuống 1 phút!

### Liên kết
- [[Single-Server Model]]
- [[Little's Law]]
- [[Capacity Planning]]

---

## Little's Law (Định luật Little)

### Định nghĩa (Definition)
[[Little's Law]] là mối quan hệ cơ bản nhất trong lý thuyết hàng chờ, áp dụng cho MỌI hệ thống hàng chờ ổn định, bất kể phân phối arrival hay service time.

### Công thức

$$L = \lambda W$$

Trong đó:
- $L$ = Số khách trung bình trong hệ thống
- $\lambda$ = Tỷ lệ đến trung bình (arrival rate)
- $W$ = Thời gian trung bình trong hệ thống

**Biến thể:**
$$L_q = \lambda W_q$$

- $L_q$ = Số khách trung bình trong hàng chờ
- $W_q$ = Thời gian chờ trung bình

### Giải thích chi tiết

Little's Law đơn giản nhưng cực kỳ mạnh mẽ vì:
1. **Phổ quát**: Áp dụng cho mọi hệ thống ổn định (stable system)
2. **Không cần biết phân phối**: Dù arrival hay service time có phân phối gì
3. **Dễ sử dụng**: Biết 2 trong 3 biến → tính được biến còn lại

### Ví dụ thực tế
**Nhà hàng:**
- Trung bình có 45 khách trong nhà hàng ($L = 45$)
- Khách đến 15 người/giờ ($\lambda = 15$)
- → $W = L/\lambda = 45/15 = 3$ giờ (mỗi khách ở trung bình 3 giờ)

**Ứng dụng trong sản xuất (Lean):**
- Tồn kho WIP trung bình: $L = 200$ sản phẩm
- Throughput rate: $\lambda = 50$ sản phẩm/giờ
- → [[Lead Time]]: $W = 200/50 = 4$ giờ

> Đây là lý do tại sao giảm [[WIP]] (tồn kho bán thành phẩm) trong [[Lean Systems]] sẽ tự động giảm Lead Time!

### Liên kết
- [[Lean Systems]]
- [[CH04 - Lean Systems]]
- [[WIP]]
- [[Lead Time]]
- [[Throughput]]

---

## Finite-Source Model (Mô hình nguồn hữu hạn)

### Định nghĩa (Definition)
[[Finite-Source Model]] là mô hình hàng chờ trong đó [[Customer Population]] có giới hạn (N nguồn). Khi một "khách hàng" đang trong hệ thống, nguồn giảm đi.

### Giải thích chi tiết

Đặc điểm:
- Tổng số nguồn (N) nhỏ và cố định
- Khi nhiều nguồn đang trong hệ thống → tỷ lệ đến giảm (vì ít nguồn còn lại)
- Không thể dùng mô hình M/M/1 hay M/M/s vì chúng giả định nguồn vô hạn
- Thường dùng **bảng tra Finite-Source** hoặc phần mềm chuyên dụng

**Ứng dụng điển hình:** Quản lý bảo trì máy móc
- N = tổng số máy trong xưởng
- Mỗi máy có thể hỏng (trở thành "khách hàng" cần sửa)
- Khi nhiều máy đang sửa → ít máy chạy → ít máy có thể hỏng tiếp

### Ví dụ thực tế
Xưởng có 10 máy (N = 10), 1 thợ sửa (s = 1):
- Mỗi máy hỏng trung bình 1 lần/50 giờ
- Thời gian sửa trung bình: 4 giờ

Dùng bảng tra finite-source: trung bình 1.5 máy đang hỏng hoặc chờ sửa → chỉ 8.5 máy hoạt động → năng suất giảm 15%. Thêm 1 thợ sửa → chỉ 0.5 máy chờ → năng suất tăng đáng kể.

### Liên kết
- [[Finite Population]]
- [[Maintenance Management]]
- [[Single-Server Model]]
- [[Capacity Planning]]

---

## Công thức quan trọng (Key Formulas)

| Công thức | Mô hình | Ý nghĩa |
|-----------|---------|---------|
| $L = \lambda W$ | [[Little's Law]] (mọi hệ thống) | Quan hệ cơ bản |
| $L_q = \lambda W_q$ | Little's Law (hàng chờ) | Quan hệ cho hàng chờ |
| $\rho = \lambda / \mu$ | [[Single-Server Model]] (M/M/1) | Utilization |
| $L = \lambda/(\mu - \lambda)$ | M/M/1 | Số khách trong hệ thống |
| $W = 1/(\mu - \lambda)$ | M/M/1 | Thời gian trong hệ thống |
| $\rho = \lambda / (s\mu)$ | [[Multiple-Server Model]] (M/M/s) | Utilization |
| $P(n) = \frac{e^{-\lambda}\lambda^n}{n!}$ | [[Poisson Distribution]] | Xác suất n khách đến |

---

## Từ khóa chính (Key Terms)

- [[Waiting-Line Models]] - Mô hình hàng chờ
- [[Queueing Theory]] - Lý thuyết hàng chờ
- [[Customer Population]] - Nguồn khách hàng
- [[Infinite Population]] - Nguồn vô hạn
- [[Finite Population]] - Nguồn hữu hạn
- [[Service System]] - Hệ thống phục vụ
- [[Priority Rule]] - Quy tắc ưu tiên
- [[FCFS]] - First Come First Served
- [[Arrival Rate]] ($\lambda$) - Tỷ lệ đến
- [[Service Rate]] ($\mu$) - Tỷ lệ phục vụ
- [[Utilization]] ($\rho$) - Hệ số sử dụng
- [[Little's Law]] - Định luật Little
- [[Single-Server Model]] - Mô hình một server (M/M/1)
- [[Multiple-Server Model]] - Mô hình nhiều server (M/M/s)
- [[Finite-Source Model]] - Mô hình nguồn hữu hạn
- [[Poisson Distribution]] - Phân phối Poisson
- [[Exponential Distribution]] - Phân phối mũ

---

> **Ghi chú ôn tập**: Little's Law ($L = \lambda W$) là công thức QUAN TRỌNG NHẤT của Supplement B. Nó áp dụng mọi nơi - kể cả trong [[CH04 - Lean Systems]] (WIP = Throughput × Lead Time). Hãy nhớ các công thức M/M/1 và biết khi nào dùng bảng tra cho M/M/s.
