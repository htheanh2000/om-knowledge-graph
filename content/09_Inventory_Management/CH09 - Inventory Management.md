---
tags: [chapter-9, part3, inventory, EOQ, safety-stock, ABC-analysis, Q-system, P-system]
aliases: [Quản lý tồn kho, Inventory Management, Quản trị hàng tồn kho]
---
# Chapter 9 - Inventory Management (Quản lý tồn kho)

## Tổng quan (Overview)

[[Inventory Management]] (Quản lý tồn kho) là một trong những chủ đề quan trọng nhất trong [[Operations Management]]. Tồn kho chiếm tỷ trọng lớn trong tài sản doanh nghiệp -- đối với nhiều công ty bán lẻ và sản xuất, tồn kho có thể chiếm 20-60% tổng tài sản. Quản lý tồn kho hiệu quả nghĩa là cân bằng giữa hai mục tiêu mâu thuẫn: **giữ đủ hàng để phục vụ khách** và **giảm thiểu chi phí lưu kho**.

Chương này giới thiệu các khái niệm nền tảng: tại sao tồn kho tồn tại ([[Inventory Trade-Offs]]), các loại tồn kho, phân tích [[ABC Analysis]], mô hình [[Economic Order Quantity (EOQ)]] kinh điển, và hai hệ thống kiểm soát tồn kho chính: [[Continuous Review System (Q System)]] và [[Periodic Review System (P System)]].

Quản lý tồn kho liên quan mật thiết đến [[Forecasting]] (dự báo nhu cầu), [[Supply Chain Management]] (quản lý chuỗi cung ứng), và [[Operations Planning and Scheduling]] (lập kế hoạch sản xuất). Sai lầm trong tồn kho ảnh hưởng trực tiếp đến [[Customer Service]], [[Cash Flow]], và khả năng cạnh tranh.

---

## Inventory Trade-Offs (Đánh đổi trong tồn kho)

### Định nghĩa (Definition)
[[Inventory Trade-Offs]] là sự mâu thuẫn cơ bản giữa áp lực giữ tồn kho ít ([[Pressures for Small Inventories]]) và áp lực giữ tồn kho nhiều ([[Pressures for Large Inventories]]).

### Giải thích chi tiết (Detailed Explanation)

#### Pressures for Small Inventories (Áp lực giảm tồn kho)

Mỗi loại chi phí đều "kêu gào" đòi giảm tồn kho:

1. **[[Holding Cost]]** (Chi phí lưu giữ / Chi phí tồn trữ): 15-35% giá trị hàng/năm
   - **Chi phí vốn** ([[Cost of Capital]]): Tiền nằm trong kho = tiền không thể đầu tư. Nếu 10 tỷ VND nằm trong kho, với lãi suất 10%/năm → mất 1 tỷ VND chi phí cơ hội.
   - **Chi phí kho bãi** ([[Storage and Handling]]): Thuê kho, điện, nhân viên kho
   - **Thuế và bảo hiểm** ([[Taxes and Insurance]]): Tồn kho lớn → thuế tài sản và phí bảo hiểm cao
   - **Hao hụt** ([[Shrinkage]]): Mất mát, hư hỏng, lỗi thời, hết hạn
     - Ví dụ: Rau quả tươi ở siêu thị hao hụt 5-10%/tuần
     - Điện thoại tồn kho 6 tháng mất giá 20-30% ([[Obsolescence]])

2. **[[Opportunity Cost]]**: Tiền đầu tư vào tồn kho không thể dùng cho R&D, marketing, hoặc đầu tư sinh lời khác.

#### Pressures for Large Inventories (Áp lực tăng tồn kho)

Nhưng nhiều bộ phận lại muốn tồn kho nhiều:

1. **[[Customer Service]]**: Khách muốn hàng có sẵn ngay. Hết hàng ([[Stockout]]) = mất doanh thu + mất khách hàng. Amazon cam kết giao hàng 1 ngày → cần kho hàng khổng lồ.

2. **[[Ordering Cost]]** (Chi phí đặt hàng): Mỗi lần đặt hàng tốn chi phí (giấy tờ, vận chuyển, kiểm tra chất lượng). Đặt ít lần nhưng số lượng lớn → giảm tổng chi phí đặt hàng.

3. **[[Setup Cost]]** (Chi phí thiết lập): Trong sản xuất, chuyển đổi máy móc giữa các sản phẩm tốn thời gian và tiền bạc. Sản xuất lô lớn → ít lần setup → giảm chi phí.

4. **[[Quantity Discounts]]** (Chiết khấu số lượng): Mua nhiều thì được giảm giá. Mua 1.000 thùng mì giá 80.000 VND/thùng, mua 10.000 thùng giá 72.000 VND/thùng → tiết kiệm 8%.

5. **[[Transportation Cost]]**: Vận chuyển container đầy tải rẻ hơn nhiều so với nửa container.

6. **Phòng ngừa biến động** ([[Hedge Inventory]]): Giá nguyên liệu sắp tăng → mua trữ trước. Ví dụ: dự báo giá thép tăng 15% → nhà thầu mua trữ.

### Ví dụ thực tế (Real-world Example)
Thế Giới Di Động phải cân bằng: giữ quá nhiều iPhone tồn kho có nguy cơ mất giá khi Apple ra model mới ([[Obsolescence]]), nhưng hết hàng iPhone mùa Tết thì mất doanh thu khổng lồ ([[Stockout Cost]]). Họ dùng [[ABC Analysis]] để ưu tiên quản lý chặt các mặt hàng giá trị cao.

### Liên kết (Related Concepts)
- [[Holding Cost]]
- [[Ordering Cost]]
- [[Stockout]]
- [[Lean Operations]]
- [[Just-in-Time (JIT)]]

---

## Types of Inventory (Các loại tồn kho)

### Định nghĩa (Definition)
Tồn kho được phân loại theo **chức năng** (tại sao nó tồn tại):

### Giải thích chi tiết (Detailed Explanation)

#### 1. [[Cycle Inventory]] (Tồn kho chu kỳ)
- Phần tồn kho biến thiên theo kích thước lô hàng ([[Lot Size]])
- Trung bình Cycle Inventory = Q/2 (Q = kích thước lô)
- Tồn tại vì: mua/sản xuất theo lô rẻ hơn mua/sản xuất từng cái
- Ví dụ: Nhà hàng Phở 24 đặt 100 kg bò mỗi 3 ngày thay vì 33 kg mỗi ngày → chi phí đặt hàng thấp hơn

#### 2. [[Safety Stock]] (Tồn kho an toàn)
- Lượng hàng dự trữ thêm để phòng khi nhu cầu cao hơn dự báo hoặc giao hàng trễ
- Đóng vai trò "đệm" ([[Buffer]]) chống [[Stockout]]
- Phụ thuộc vào: mức [[Service Level]] mong muốn, độ biến thiên nhu cầu ([[Demand Variability]]), và [[Lead Time Variability]]
- Ví dụ: Bệnh viện luôn giữ thêm 20% thuốc cấp cứu so với dự báo → [[Safety Stock]] để đảm bảo không bao giờ hết thuốc

#### 3. [[Anticipation Inventory]] (Tồn kho dự trù / Tồn kho dự phòng mùa vụ)
- Sản xuất trước để đáp ứng nhu cầu cao điểm sắp tới
- Liên quan mật thiết đến [[S&OP - Sales and Operations Planning]]
- Ví dụ: Nhà máy bánh trung thu bắt đầu sản xuất từ tháng 6 (dù bán chạy nhất tháng 8 âm lịch) vì công suất máy không đủ nếu chỉ sản xuất trong tháng 8

#### 4. [[Pipeline Inventory]] (Tồn kho đường ống / Tồn kho vận chuyển)
- Hàng đang trên đường vận chuyển giữa các điểm trong [[Supply Chain]]
- Pipeline Inventory = $\bar{d} \times L$ (nhu cầu trung bình × [[Lead Time]])
- Ví dụ: Container hàng từ Trung Quốc về Việt Nam mất 5 ngày trên biển. Nếu mỗi ngày cần 100 đơn vị → 500 đơn vị luôn "trôi nổi" trên biển = [[Pipeline Inventory]]

### Ví dụ thực tế (Real-world Example)
Vinamilk quản lý đủ 4 loại tồn kho:
- [[Cycle Inventory]]: Đặt bao bì in sẵn theo lô 100.000 hộp
- [[Safety Stock]]: Giữ thêm sữa tươi nguyên liệu phòng nhà cung cấp trễ
- [[Anticipation Inventory]]: Sản xuất sữa hộp quà Tết từ tháng 10
- [[Pipeline Inventory]]: Sữa đang vận chuyển từ nhà máy đến 200.000+ điểm bán

### Liên kết (Related Concepts)
- [[Economic Order Quantity (EOQ)]]
- [[Reorder Point]]
- [[Lead Time]]
- [[Service Level]]

---

## Inventory Reduction Tactics (Chiến thuật giảm tồn kho)

### Định nghĩa (Definition)
Các chiến thuật cụ thể để giảm từng loại tồn kho mà không ảnh hưởng [[Customer Service]]:

### Giải thích chi tiết (Detailed Explanation)

| Loại tồn kho | Chiến thuật giảm |
|---------------|------------------|
| [[Cycle Inventory]] | Giảm [[Lot Size]] (Q) bằng cách giảm [[Ordering Cost]] hoặc [[Setup Cost]]. Triết lý [[Lean Operations]] và [[Just-in-Time (JIT)]]: đặt hàng thường xuyên hơn, số lượng ít hơn. |
| [[Safety Stock]] | Cải thiện [[Forecasting]], giảm [[Lead Time]], giảm [[Lead Time Variability]], hợp tác với nhà cung cấp ([[Supplier Partnerships]]). |
| [[Anticipation Inventory]] | Sử dụng [[Level Strategy]] hoặc đầu tư tăng công suất linh hoạt ([[Flexible Capacity]]). |
| [[Pipeline Inventory]] | Rút ngắn [[Lead Time]], chọn nhà cung cấp gần hơn, cải thiện [[Transportation]]. |

### Liên kết (Related Concepts)
- [[Lean Operations]]
- [[Just-in-Time (JIT)]]
- [[Supply Chain Management]]
- [[Continuous Improvement]]

---

## ABC Analysis (Phân tích ABC)

### Định nghĩa (Definition)
[[ABC Analysis]] (hay [[Pareto Analysis]]) phân loại hàng tồn kho thành 3 nhóm dựa trên **giá trị sử dụng hàng năm** (Annual Dollar Usage = nhu cầu hàng năm × giá trị đơn vị), áp dụng [[Pareto Principle]] (nguyên tắc 80/20).

### Giải thích chi tiết (Detailed Explanation)

| Nhóm | % SKU | % Giá trị | Cách quản lý |
|-------|-------|-----------|--------------|
| **A** | ~20% | ~80% | Kiểm soát chặt chẽ, dự báo thường xuyên, [[Continuous Review System (Q System)]], đàm phán nhà cung cấp kỹ |
| **B** | ~30% | ~15% | Kiểm soát trung bình, cân nhắc [[EOQ]] |
| **C** | ~50% | ~5% | Kiểm soát đơn giản, [[Periodic Review System (P System)]], đặt hàng lô lớn để giảm tần suất |

#### Quy trình thực hiện [[ABC Analysis]]:
1. Tính giá trị sử dụng hàng năm cho mỗi SKU
2. Sắp xếp giảm dần
3. Tính % tích lũy
4. Phân loại A, B, C

**Ví dụ**:

| SKU | Nhu cầu/năm | Giá (VND) | Giá trị/năm | % tích lũy | Nhóm |
|-----|------------|-----------|-------------|------------|------|
| X01 | 5.000 | 200.000 | 1 tỷ | 50% | A |
| X02 | 10.000 | 50.000 | 500 tr | 75% | A |
| X03 | 2.000 | 100.000 | 200 tr | 85% | B |
| X04 | 20.000 | 5.000 | 100 tr | 90% | B |
| ... | ... | ... | ... | ... | C |

### Ví dụ thực tế (Real-world Example)
Chuỗi nhà thuốc Long Châu quản lý hàng nghìn SKU. Thuốc đặc trị giá cao (nhóm A) được kiểm kê hàng tuần, theo dõi hạn sử dụng chặt. Vitamin giá rẻ (nhóm C) chỉ kiểm kê hàng tháng và đặt theo lô lớn.

### Liên kết (Related Concepts)
- [[Pareto Principle]]
- [[Inventory Management]]
- [[Continuous Review System (Q System)]]
- [[Periodic Review System (P System)]]

---

## Economic Order Quantity (EOQ) - Lượng đặt hàng kinh tế

### Định nghĩa (Definition)
[[Economic Order Quantity (EOQ)]] là kích thước lô hàng tối ưu giúp **tối thiểu hóa tổng chi phí tồn kho hàng năm** (bao gồm [[Holding Cost]] và [[Ordering Cost]]).

### Giải thích chi tiết (Detailed Explanation)

#### Các giả định của mô hình [[EOQ]]:
1. Nhu cầu ổn định và biết trước (không đổi theo thời gian)
2. Không có [[Quantity Discounts]] (giá không đổi theo số lượng)
3. Toàn bộ lô hàng giao cùng lúc (instantaneous replenishment)
4. Chỉ có 2 loại chi phí: [[Holding Cost]] và [[Ordering Cost]]
5. Không có [[Stockout]] (không hết hàng)
6. [[Lead Time]] không đổi

#### Derivation (Suy ra công thức):

**Tổng chi phí hàng năm** ([[Total Annual Cost]]):
$$TC = \text{Annual Holding Cost} + \text{Annual Ordering Cost}$$

$$TC = \frac{Q}{2} \times H + \frac{D}{Q} \times S$$

Trong đó:
- $Q$ = kích thước lô đặt hàng
- $D$ = nhu cầu hàng năm (đơn vị/năm)
- $H$ = [[Holding Cost]] (chi phí lưu giữ/đơn vị/năm)
- $S$ = [[Ordering Cost]] (chi phí mỗi lần đặt hàng)
- $Q/2$ = tồn kho trung bình ([[Average Cycle Inventory]])
- $D/Q$ = số lần đặt hàng/năm

**Lấy đạo hàm và cho = 0**:
$$\frac{dTC}{dQ} = \frac{H}{2} - \frac{DS}{Q^2} = 0$$

$$Q^2 = \frac{2DS}{H}$$

### **Công thức EOQ:**
$$EOQ = Q^* = \sqrt{\frac{2DS}{H}}$$

#### Insights quan trọng từ EOQ:

1. **Tại điểm tối ưu**: Annual Holding Cost = Annual Ordering Cost. Đây là điều nhiều người bất ngờ -- chi phí lưu giữ đúng bằng chi phí đặt hàng!

2. **EOQ không nhạy cảm** với sai số: Nếu ước lượng D hoặc H sai 50%, tổng chi phí chỉ tăng ~5%. Đường cong TC rất "thoải" quanh điểm tối ưu.

3. **Khi D tăng gấp đôi, EOQ chỉ tăng √2 lần** (khoảng 41%). Không cần tăng kích thước lô tỷ lệ thuận với nhu cầu.

4. **Thời gian giữa các đơn hàng** ([[Time Between Orders]]): $TBO = \frac{EOQ}{D}$ (tính theo năm)

### Ví dụ thực tế (Real-world Example)

**Bài toán**: Một cửa hàng Bách Hóa Xanh bán 6.000 thùng nước suối/năm. Chi phí mỗi lần đặt hàng = 300.000 VND. Chi phí lưu giữ = 10.000 VND/thùng/năm.

$$EOQ = \sqrt{\frac{2 \times 6.000 \times 300.000}{10.000}} = \sqrt{360.000} \approx 600 \text{ thùng}$$

- Số lần đặt hàng/năm = 6.000/600 = **10 lần**
- TBO = 600/6.000 = 0.1 năm ≈ **36.5 ngày**
- Tổng chi phí tối thiểu:
  - Holding = (600/2) × 10.000 = **3.000.000 VND**
  - Ordering = (6.000/600) × 300.000 = **3.000.000 VND**
  - TC = **6.000.000 VND/năm**

Chú ý: Holding = Ordering tại điểm tối ưu!

### Liên kết (Related Concepts)
- [[Holding Cost]]
- [[Ordering Cost]]
- [[Cycle Inventory]]
- [[Continuous Review System (Q System)]]
- [[Quantity Discounts]]
- [[Lot Sizing]]

---

## Continuous Review System (Q System) - Hệ thống kiểm tra liên tục

### Định nghĩa (Definition)
[[Continuous Review System (Q System)]] (hay [[Reorder Point System]] / hệ thống Q) theo dõi tồn kho **liên tục**. Khi tồn kho giảm xuống đến [[Reorder Point]] (R), đặt ngay một lượng cố định Q.

### Giải thích chi tiết (Detailed Explanation)

#### Hoạt động:
- Theo dõi tồn kho liên tục (mỗi khi có giao dịch xuất/nhập)
- Khi Inventory Position ≤ R → đặt hàng Q đơn vị
- Q thường = [[EOQ]]

#### [[Inventory Position]] (Vị trí tồn kho):
$$IP = OH + SR - BO$$
- OH = On-Hand (tồn kho thực có)
- SR = Scheduled Receipts (hàng đã đặt đang trên đường)
- BO = Backorders (đơn hàng chờ)

#### [[Reorder Point]] (Điểm đặt hàng lại):
$$R = \bar{d} \times L + \text{Safety Stock}$$

Trong đó:
- $\bar{d}$ = nhu cầu trung bình mỗi ngày/tuần
- $L$ = [[Lead Time]] (thời gian giao hàng)
- $\bar{d} \times L$ = nhu cầu trung bình trong lead time

#### [[Safety Stock]] (Tồn kho an toàn):
$$\text{Safety Stock} = z \times \sigma_{dLT}$$

Trong đó:
- $z$ = giá trị z từ bảng phân phối chuẩn, phụ thuộc [[Service Level]]
  - [[Service Level]] 90% → z = 1.28
  - [[Service Level]] 95% → z = 1.65
  - [[Service Level]] 99% → z = 2.33
- $\sigma_{dLT}$ = độ lệch chuẩn của nhu cầu trong lead time

$$\sigma_{dLT} = \sigma_d \times \sqrt{L}$$

(khi chỉ có biến thiên nhu cầu, lead time cố định)

Công thức đầy đủ khi cả nhu cầu và lead time biến thiên:
$$\sigma_{dLT} = \sqrt{L\sigma_d^2 + \bar{d}^2\sigma_{LT}^2}$$

### Ví dụ thực tế (Real-world Example)

**Bài toán**: Cửa hàng bán 30 đơn vị/ngày ($\bar{d}$ = 30), $\sigma_d$ = 5 đơn vị/ngày, Lead time = 4 ngày (cố định), Service Level = 95%.

- $\sigma_{dLT} = 5 \times \sqrt{4} = 5 \times 2 = 10$
- Safety Stock = 1.65 × 10 = **16.5 ≈ 17 đơn vị**
- R = 30 × 4 + 17 = **137 đơn vị**

→ Khi tồn kho giảm xuống 137, đặt hàng ngay Q đơn vị. 17 đơn vị safety stock đảm bảo 95% khả năng không hết hàng trong lead time.

### Liên kết (Related Concepts)
- [[Economic Order Quantity (EOQ)]]
- [[Reorder Point]]
- [[Safety Stock]]
- [[Service Level]]
- [[Lead Time]]
- [[Periodic Review System (P System)]]

---

## Periodic Review System (P System) - Hệ thống kiểm tra định kỳ

### Định nghĩa (Definition)
[[Periodic Review System (P System)]] (hay [[Fixed-Interval Reorder System]]) kiểm tra tồn kho theo **chu kỳ cố định** (P), và đặt hàng đủ để nâng tồn kho lên mức mục tiêu [[Target Inventory Level]] (T). Mỗi lần đặt hàng số lượng **khác nhau**.

### Giải thích chi tiết (Detailed Explanation)

#### Hoạt động:
- Mỗi P ngày/tuần, kiểm tra tồn kho
- Đặt hàng: Q = T - IP (trong đó IP = [[Inventory Position]] hiện tại)
- Q thay đổi mỗi lần (khác Q System là Q cố định)

#### [[Target Inventory Level]] (Mức tồn kho mục tiêu):
$$T = \bar{d}(P + L) + \text{Safety Stock}$$

$$\text{Safety Stock} = z \times \sigma_{d(P+L)}$$

$$\sigma_{d(P+L)} = \sigma_d \times \sqrt{P + L}$$

**Tại sao P+L?** Vì khi kiểm tra hôm nay, hàng sẽ đến sau L ngày. Nhưng đơn hàng kế tiếp sẽ không được đặt cho đến P ngày nữa. Vậy tồn kho phải đủ cho P + L ngày.

### Ví dụ thực tế (Real-world Example)

**Bài toán**: Cùng dữ liệu: $\bar{d}$ = 30/ngày, $\sigma_d$ = 5/ngày, L = 4 ngày, P = 7 ngày (kiểm tra mỗi tuần), Service Level = 95%.

- $\sigma_{d(P+L)} = 5 \times \sqrt{7+4} = 5 \times \sqrt{11} = 5 \times 3.317 = 16.58$
- Safety Stock = 1.65 × 16.58 = **27.4 ≈ 28 đơn vị**
- T = 30(7+4) + 28 = 330 + 28 = **358 đơn vị**

Nếu khi kiểm tra, IP = 200 → Đặt hàng Q = 358 - 200 = **158 đơn vị**

**So sánh**: Safety stock ở P System (28) > Q System (17) vì phải "bảo vệ" cho khoảng thời gian dài hơn (P+L thay vì chỉ L).

### Liên kết (Related Concepts)
- [[Continuous Review System (Q System)]]
- [[Target Inventory Level]]
- [[Safety Stock]]
- [[Service Level]]

---

## Comparing Q vs P Systems (So sánh hệ thống Q và P)

### Giải thích chi tiết (Detailed Explanation)

| Tiêu chí | [[Continuous Review System (Q System)]] | [[Periodic Review System (P System)]] |
|-----------|------|------|
| **Khi nào kiểm tra** | Liên tục (mỗi giao dịch) | Định kỳ (mỗi P ngày) |
| **Số lượng đặt** | Cố định (Q) | Thay đổi (T - IP) |
| **Khi nào đặt hàng** | Khi IP ≤ R | Mỗi P ngày |
| **Safety Stock** | Thấp hơn ($z \times \sigma_d\sqrt{L}$) | Cao hơn ($z \times \sigma_d\sqrt{P+L}$) |
| **Chi phí hệ thống** | Cao hơn (cần theo dõi liên tục) | Thấp hơn (chỉ kiểm tra định kỳ) |
| **Phù hợp cho** | Mặt hàng nhóm A (giá trị cao) | Mặt hàng nhóm B, C; hoặc khi nhiều SKU đặt cùng nhà cung cấp |
| **Ưu điểm** | Safety stock thấp, phản ứng nhanh | Dễ quản lý, kết hợp đơn hàng |
| **Nhược điểm** | Cần hệ thống theo dõi liên tục | Safety stock cao hơn |

### Ví dụ thực tế (Real-world Example)
Chuỗi cửa hàng Circle K:
- **Q System** cho thuốc lá (nhóm A, giá trị cao): hệ thống POS tự động theo dõi, khi xuống R → đặt hàng
- **P System** cho kẹo/snack (nhóm C): mỗi thứ 3 và thứ 6, nhân viên kiểm kệ và đặt bổ sung lên mức T

### Liên kết (Related Concepts)
- [[ABC Analysis]]
- [[Inventory Management]]
- [[Technology in Operations]]
- [[Barcode]] / [[RFID]]

---

## Công thức quan trọng (Key Formulas)

| Công thức | Ký hiệu | Mô tả |
|-----------|----------|-------|
| $EOQ = \sqrt{\frac{2DS}{H}}$ | [[Economic Order Quantity (EOQ)]] | Lượng đặt hàng tối ưu |
| $TC = \frac{Q}{2}H + \frac{D}{Q}S$ | [[Total Annual Cost]] | Tổng chi phí hàng năm |
| $TBO = \frac{EOQ}{D}$ | [[Time Between Orders]] | Thời gian giữa các đơn hàng |
| $R = \bar{d}L + z\sigma_d\sqrt{L}$ | [[Reorder Point]] | Điểm đặt hàng lại (Q System) |
| $T = \bar{d}(P+L) + z\sigma_d\sqrt{P+L}$ | [[Target Inventory Level]] | Mức tồn kho mục tiêu (P System) |
| $\text{Safety Stock} = z\sigma_{dLT}$ | [[Safety Stock]] | Tồn kho an toàn |
| $\text{Pipeline} = \bar{d} \times L$ | [[Pipeline Inventory]] | Tồn kho đường ống |
| $IP = OH + SR - BO$ | [[Inventory Position]] | Vị trí tồn kho |

---

## Từ khóa chính (Key Terms)

- [[Inventory Management]] - Quản lý tồn kho
- [[Holding Cost]] - Chi phí lưu giữ
- [[Ordering Cost]] - Chi phí đặt hàng
- [[Setup Cost]] - Chi phí thiết lập
- [[Stockout]] - Hết hàng
- [[Cycle Inventory]] - Tồn kho chu kỳ
- [[Safety Stock]] - Tồn kho an toàn
- [[Anticipation Inventory]] - Tồn kho dự trù
- [[Pipeline Inventory]] - Tồn kho đường ống
- [[ABC Analysis]] - Phân tích ABC
- [[Pareto Principle]] - Nguyên tắc 80/20
- [[Economic Order Quantity (EOQ)]] - Lượng đặt hàng kinh tế
- [[Reorder Point]] - Điểm đặt hàng lại
- [[Continuous Review System (Q System)]] - Hệ thống kiểm tra liên tục
- [[Periodic Review System (P System)]] - Hệ thống kiểm tra định kỳ
- [[Target Inventory Level]] - Mức tồn kho mục tiêu
- [[Service Level]] - Mức phục vụ
- [[Lead Time]] - Thời gian giao hàng
- [[Inventory Position]] - Vị trí tồn kho
- [[Quantity Discounts]] - Chiết khấu số lượng
- [[Lot Size]] - Kích thước lô
- [[Demand Variability]] - Độ biến thiên nhu cầu
