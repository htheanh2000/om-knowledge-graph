---
tags: [chapter-13, part3, logistics, location-decisions, transportation, warehouse, GIS, load-distance, break-even]
aliases: [Mạng lưới logistics chuỗi cung ứng, Supply Chain Logistics Networks, CH13]
---
# Chapter 13 - Supply Chain Logistics Networks (Mạng lưới Logistics chuỗi cung ứng)

## Tổng quan (Overview)

Chương này tập trung vào việc thiết kế mạng lưới logistics — bao gồm các quyết định về vị trí đặt cơ sở (facility location), phương pháp vận chuyển (transportation), và chiến lược kho hàng (warehouse strategy). Đây là những quyết định dài hạn, có tác động lớn đến chi phí và hiệu quả vận hành của toàn bộ chuỗi cung ứng.

Việc chọn đúng vị trí cho nhà máy, kho hàng, và trung tâm phân phối có thể tạo ra lợi thế cạnh tranh bền vững. Ngược lại, sai lầm trong quyết định vị trí rất tốn kém để sửa chữa vì liên quan đến đầu tư cố định lớn (đất đai, nhà xưởng, cơ sở hạ tầng).

Chương giới thiệu nhiều công cụ phân tích định lượng: **[[Load-Distance Method]]** (Phương pháp tải-khoảng cách), **[[Break-Even Analysis]]** (Phân tích điểm hòa vốn), và **[[Transportation Method]]** (Phương pháp vận tải), cùng với các công nghệ hiện đại như [[GIS]] và **[[Autonomous Warehouse]]** (Kho hàng tự trị).

---

## 1. Các yếu tố ảnh hưởng đến quyết định vị trí (Factors Affecting Location Decisions)

### Định nghĩa (Definition)
**[[Location Decision]]** (Quyết định vị trí) là quá trình lựa chọn vị trí địa lý cho các cơ sở vật chất của doanh nghiệp (nhà máy, kho hàng, cửa hàng, văn phòng) dựa trên các yếu tố kinh tế, chiến lược, và vận hành.

![Figure 13.1 - Location Factors](/images/figures/ch13_fig13.1.jpg)
> *Figure 13.1: Các yếu tố ảnh hưởng đến quyết định vị trí cơ sở sản xuất và dịch vụ*

### 1.1 Yếu tố cho doanh nghiệp sản xuất (Manufacturing)

| Yếu tố | Giải thích | Ví dụ |
|--------|-----------|-------|
| **[[Labor Cost]]** (Chi phí lao động) | Tiền lương, phúc lợi, năng suất lao động | Samsung chọn Việt Nam vì chi phí lao động thấp hơn Hàn Quốc |
| **Gần nguồn nguyên liệu** | Giảm chi phí vận chuyển nguyên liệu đầu vào | Nhà máy thép Formosa đặt tại Hà Tĩnh gần cảng biển để nhập quặng sắt |
| **Gần thị trường tiêu thụ** | Giảm chi phí vận chuyển sản phẩm, tăng tốc độ giao hàng | Nhà máy bia Heineken đặt tại nhiều tỉnh thành để phục vụ thị trường nội địa |
| **[[Infrastructure]]** (Cơ sở hạ tầng) | Đường xá, cảng biển, sân bay, điện, nước, internet | Các **[[Industrial Parks]]** (khu công nghiệp) ở Bình Dương có hạ tầng tốt |
| **[[Taxes & Incentives]]** (Thuế và ưu đãi) | Ưu đãi thuế, miễn thuế nhập khẩu cho **[[Export Processing Zone]]** (khu chế xuất) | Khu CNC Hòa Lạc có nhiều ưu đãi thuế cho doanh nghiệp công nghệ |
| **Chất lượng nguồn nhân lực** | Trình độ kỹ thuật, kỹ năng chuyên môn của lao động địa phương | Intel đặt nhà máy chip tại TP.HCM vì có nguồn kỹ sư dồi dào |
| **Quy định môi trường** | Luật bảo vệ môi trường, yêu cầu xử lý chất thải | Ảnh hưởng đến chi phí vận hành của nhà máy hóa chất, xi măng |

### 1.2 Yếu tố cho doanh nghiệp dịch vụ (Services)

| Yếu tố | Giải thích | Ví dụ |
|--------|-----------|-------|
| **[[Proximity to Customers]]** (Gần khách hàng) | Yếu tố QUAN TRỌNG NHẤT cho dịch vụ — khách hàng cần tiếp cận dễ dàng | Bệnh viện, siêu thị, ngân hàng cần ở nơi đông dân cư |
| **Mật độ dân cư** | Số lượng khách hàng tiềm năng trong vùng phục vụ | Starbucks chọn vị trí có lưu lượng người qua lại cao |
| **[[Traffic Flow]]** (Giao thông) | Khả năng tiếp cận bằng các phương tiện giao thông | Trung tâm thương mại cần gần đường lớn, có bãi đỗ xe |
| **[[Competitors]]** (Đối thủ cạnh tranh) | Vị trí của đối thủ — có thể tụ họp (cluster) hoặc tránh xa | Các quán phở tập trung trên cùng một con phố (cluster) |
| **Dịch vụ trực tuyến** | Xu hướng chuyển sang online giảm tầm quan trọng của vị trí vật lý | Ngân hàng số (Timo, CAKE) không cần nhiều chi nhánh |

### Giải thích chi tiết
**Sự khác biệt quan trọng**: Đối với sản xuất, chi phí thường là yếu tố chính (vì khách hàng không cần đến nhà máy). Đối với dịch vụ, sự tiện lợi cho khách hàng là yếu tố chính (vì khách hàng cần đến tận nơi). Tuy nhiên, ranh giới này đang mờ dần nhờ thương mại điện tử và [[logistics]] hiện đại.

### Liên kết
- [[CH12 - Supply Chain Design]] — Thiết kế chuỗi cung ứng tổng thể
- [[CH15 - Supply Chain Sustainability]] — Yếu tố bền vững trong quyết định vị trí
- [[CH02 - Operations Strategy]] — Chiến lược vận hành

---

## 2. **[[Load-Distance Method]]** (Phương pháp Tải-Khoảng cách)

### Định nghĩa (Definition)
**[[Load-Distance Method]]** (Phương pháp tải-khoảng cách) là phương pháp định lượng để đánh giá và so sánh các vị trí tiềm năng dựa trên tổng "tải" (lượng hàng vận chuyển) nhân với "khoảng cách" đến các điểm quan trọng (nhà cung cấp, khách hàng, kho hàng).

### 2.1 Đo lường khoảng cách (Distance Measures)

#### **[[Euclidean Distance]]** (Khoảng cách Euclid)
Khoảng cách đường thẳng giữa hai điểm — "đường chim bay".

$$d_{AB} = \sqrt{(x_A - x_B)^2 + (y_A - y_B)^2}$$

**Khi nào dùng**: Khi vận chuyển đường hàng không, hoặc khi đường giao thông gần như thẳng.

**Ví dụ**: Khoảng cách từ điểm A(2, 3) đến điểm B(5, 7):
$$d_{AB} = \sqrt{(2-5)^2 + (3-7)^2} = \sqrt{9 + 16} = \sqrt{25} = 5$$

#### **[[Rectilinear Distance]]** (Khoảng cách Rectilinear / Manhattan Distance)
Khoảng cách theo đường ô bàn cờ — chỉ di chuyển theo chiều ngang và dọc (phản ánh đường phố trong thành phố).

$$d_{AB} = |x_A - x_B| + |y_A - y_B|$$

**Khi nào dùng**: Khi vận chuyển trong thành phố có mạng lưới đường phố dạng ô bàn cờ (grid).

**Ví dụ**: Cùng hai điểm A(2, 3) và B(5, 7):
$$d_{AB} = |2-5| + |3-7| = 3 + 4 = 7$$

> **So sánh**: Khoảng cách Rectilinear luôn >= Khoảng cách Euclid. Trong thực tế đường đi thường dài hơn đường chim bay.

![Figure 13.2 - Load-Distance Method](/images/figures/ch13_fig13.2.jpg)
> *Figure 13.2: Phương pháp Tải-Khoảng cách — so sánh các vị trí tiềm năng dựa trên tải và khoảng cách*

### 2.2 **[[Load-Distance Score]]** (Điểm Tải-Khoảng cách)

**Công thức**:
$$ld = \sum_{i} l_i \times d_i$$

Trong đó:
- $l_i$ = Tải (load) tại điểm $i$ — có thể là số chuyến vận chuyển, số tấn hàng, số khách hàng
- $d_i$ = Khoảng cách từ vị trí đề xuất đến điểm $i$
- $ld$ = Tổng điểm tải-khoảng cách — **càng thấp càng tốt**

**Ví dụ chi tiết**:
Một công ty cần chọn vị trí kho hàng mới. Có 3 điểm giao hàng chính:

| Điểm giao hàng | Tọa độ (x, y) | Số chuyến/tuần (Load) |
|----------------|---------------|----------------------|
| Cửa hàng A | (2, 5) | 10 |
| Cửa hàng B | (6, 1) | 20 |
| Cửa hàng C | (8, 7) | 15 |

So sánh hai vị trí đề xuất: **P1(4, 3)** và **P2(5, 4)**

**Tính cho P1(4, 3)** (dùng Euclidean):
- $d_{P1,A} = \sqrt{(4-2)^2 + (3-5)^2} = \sqrt{8} = 2.83$
- $d_{P1,B} = \sqrt{(4-6)^2 + (3-1)^2} = \sqrt{8} = 2.83$
- $d_{P1,C} = \sqrt{(4-8)^2 + (3-7)^2} = \sqrt{32} = 5.66$

$$ld_{P1} = 10(2.83) + 20(2.83) + 15(5.66) = 28.3 + 56.6 + 84.9 = 169.8$$

**Tính cho P2(5, 4)** (dùng Euclidean):
- $d_{P2,A} = \sqrt{(5-2)^2 + (4-5)^2} = \sqrt{10} = 3.16$
- $d_{P2,B} = \sqrt{(5-6)^2 + (4-1)^2} = \sqrt{10} = 3.16$
- $d_{P2,C} = \sqrt{(5-8)^2 + (4-7)^2} = \sqrt{18} = 4.24$

$$ld_{P2} = 10(3.16) + 20(3.16) + 15(4.24) = 31.6 + 63.2 + 63.6 = 158.4$$

**Kết luận**: Chọn P2 vì có điểm tải-khoảng cách thấp hơn (158.4 < 169.8).


![Figure 13.4 - Center of Gravity Method](/images/figures/ch13_fig13.4.jpg)
> *Figure 13.4: Phương pháp Trọng tâm — tìm vị trí tối ưu bằng trung bình có trọng số tọa độ*

### 2.3 **[[Center of Gravity]]** (Trọng tâm)

**Định nghĩa**: Phương pháp tìm vị trí "tối ưu" ban đầu bằng cách tính trung bình có trọng số của tọa độ các điểm, với trọng số là load.

**Công thức**:
$$x^* = \frac{\sum_{i} l_i \cdot x_i}{\sum_{i} l_i} \qquad y^* = \frac{\sum_{i} l_i \cdot y_i}{\sum_{i} l_i}$$

**Ví dụ** (tiếp từ trên):
$$x^* = \frac{10(2) + 20(6) + 15(8)}{10 + 20 + 15} = \frac{20 + 120 + 120}{45} = \frac{260}{45} = 5.78$$

$$y^* = \frac{10(5) + 20(1) + 15(7)}{10 + 20 + 15} = \frac{50 + 20 + 105}{45} = \frac{175}{45} = 3.89$$

**Vị trí trọng tâm**: (5.78, 3.89) — đây là điểm xuất phát tốt để tìm kiếm vị trí thực tế lân cận.

> **Lưu ý**: Center of Gravity chỉ là điểm khởi đầu. Vị trí thực tế cần xem xét thêm các yếu tố như đường giao thông, giá đất, và quy hoạch đô thị.

### Liên kết
- **[[Break-Even Analysis]]** (Phân tích điểm hòa vốn) — Phương pháp bổ sung
- [[GIS]] — Công cụ trực quan hóa kết quả

---

## 3. **[[Break-Even Analysis]]** cho vị trí (Phân tích điểm hòa vốn for Location)

### Định nghĩa (Definition)
**[[Break-Even Analysis]]** (Phân tích điểm hòa vốn) so sánh tổng chi phí của các vị trí khác nhau dựa trên chi phí cố định (fixed cost) và chi phí biến đổi (variable cost) tại mỗi vị trí, để xác định vị trí nào có chi phí thấp nhất tùy theo mức sản lượng.

### Công thức
$$\text{Total Cost} = F + cQ$$

Trong đó:
- $F$ = **[[Fixed Cost]]** (Chi phí cố định) — tiền thuê đất, xây nhà xưởng, chi phí cố định hàng năm
- $c$ = **[[Variable Cost]]** trên mỗi đơn vị (Chi phí biến đổi per Unit)
- $Q$ = Sản lượng (Quantity)

**Điểm hòa vốn giữa hai vị trí A và B**:
$$F_A + c_A \cdot Q = F_B + c_B \cdot Q$$
$$Q^* = \frac{F_B - F_A}{c_A - c_B}$$

### Ví dụ chi tiết
Một công ty đang xem xét 3 vị trí đặt nhà máy:

| Vị trí | Chi phí cố định/năm | Chi phí biến đổi/SP |
|--------|---------------------|---------------------|
| **Bình Dương** | 2 tỷ VND | 150.000 VND |
| **Long An** | 1.5 tỷ VND | 200.000 VND |
| **Đồng Nai** | 2.5 tỷ VND | 120.000 VND |

**Tìm điểm hòa vốn giữa Long An và Bình Dương**:
$$Q^* = \frac{2{,}000 - 1{,}500}{200 - 150} = \frac{500}{50} = 10{,}000 \text{ sản phẩm/năm}$$

(Đơn vị: triệu VND cho F, nghìn VND cho c)

**Kết luận**:
- Nếu sản lượng < 10.000 SP/năm → Chọn **Long An** (chi phí cố định thấp bù đắp chi phí biến đổi cao)
- Nếu sản lượng > 10.000 SP/năm → Cần so sánh tiếp Bình Dương vs Đồng Nai

**Tìm điểm hòa vốn giữa Bình Dương và Đồng Nai**:
$$Q^* = \frac{2{,}500 - 2{,}000}{150 - 120} = \frac{500}{30} = 16{,}667 \text{ sản phẩm/năm}$$

**Tổng kết**:
- Q < 10.000: Chọn **Long An**
- 10.000 < Q < 16.667: Chọn **Bình Dương**
- Q > 16.667: Chọn **Đồng Nai**

### Liên kết
- [[CH05 - Capacity Planning]] — Hoạch định công suất
- **[[Load-Distance Method]]** (Phương pháp Tải-Khoảng cách) — Phương pháp phân tích bổ sung
- Chi phí cố định vs Chi phí biến đổi

---

## 4. **[[Transportation Method]]** (Phương pháp vận tải)


### Định nghĩa (Definition)
**[[Transportation Method]]** (Phương pháp vận tải) là kỹ thuật **[[Linear Programming]]** (quy hoạch tuyến tính) đặc biệt, dùng để tìm phương án vận chuyển tối ưu (chi phí thấp nhất) từ nhiều nguồn cung (plants/warehouses) đến nhiều điểm cầu (warehouses/customers).

![Figure 13.5 - Transportation Method](/images/figures/ch13_fig13.5.jpg)
> *Figure 13.5: Phương pháp vận tải — tối ưu hóa chi phí vận chuyển từ nguồn cung đến điểm cầu*

### 4.1 Bảng ban đầu (Initial Tableau)

Bảng vận tải có dạng ma trận:
- **Hàng (rows)**: Các nguồn cung (nhà máy / kho) với công suất cung (supply capacity)
- **Cột (columns)**: Các điểm cầu (kho / khách hàng) với nhu cầu (demand)
- **Ô (cell)**: Chi phí vận chuyển trên mỗi đơn vị từ nguồn $i$ đến điểm $j$

**Ví dụ**: 2 nhà máy cung cấp cho 3 kho hàng

|  | Kho HN | Kho ĐN | Kho SG | Cung |
|--|--------|--------|--------|------|
| **NM Hải Phòng** | 30 | 50 | 60 | 500 |
| **NM Bình Dương** | 55 | 25 | 15 | 700 |
| **Cầu** | 400 | 300 | 500 | **1200** |

(Đơn vị chi phí: nghìn VND/tấn)

Tổng cung = 500 + 700 = 1200 = Tổng cầu → Bài toán **cân bằng** (balanced).

### 4.2 **[[Dummy Plants]]** và **[[Dummy Warehouses]]** (Nhà máy ảo và Kho hàng ảo)

**Khi nào cần Dummy?**
- Khi **Tổng cung > Tổng cầu**: Thêm cột **[[Dummy Warehouse]]** (kho hàng ảo) với nhu cầu = Tổng cung - Tổng cầu, chi phí vận chuyển = 0 (hàng "vận chuyển" đến kho ảo nghĩa là hàng tồn kho).
- Khi **Tổng cung < Tổng cầu**: Thêm hàng **[[Dummy Plant]]** (nhà máy ảo) với công suất = Tổng cầu - Tổng cung, chi phí vận chuyển = 0 (nhu cầu "nhận" từ nhà máy ảo nghĩa là nhu cầu không được đáp ứng).

**Ví dụ**: Nếu trong bài trên, NM Bình Dương chỉ cung cấp 600 (thay vì 700):
- Tổng cung = 500 + 600 = 1100 < Tổng cầu = 1200
- Thêm Dummy Plant với cung = 1200 - 1100 = 100, chi phí = 0

|  | Kho HN | Kho ĐN | Kho SG | Cung |
|--|--------|--------|--------|------|
| NM Hải Phòng | 30 | 50 | 60 | 500 |
| NM Bình Dương | 55 | 25 | 15 | 600 |
| **Dummy** | **0** | **0** | **0** | **100** |
| Cầu | 400 | 300 | 500 | **1200** |

### Giải thích chi tiết về cách giải
Có nhiều phương pháp giải bảng vận tải:
1. **[[Northwest Corner Method]]**: Bắt đầu từ ô góc trên bên trái, phân bổ tối đa có thể, rồi di chuyển sang phải hoặc xuống dưới. Đơn giản nhưng thường cho kết quả xa tối ưu.
2. **[[Vogel's Approximation Method]]** (VAM): Tính "phạt" (penalty) cho mỗi hàng/cột, ưu tiên phân bổ cho hàng/cột có phạt cao nhất. Cho kết quả gần tối ưu hơn.
3. **[[Stepping Stone Method]]** hoặc **[[MODI Method]]**: Kiểm tra và cải tiến phương án cho đến khi tối ưu.

### Liên kết
- **[[Linear Programming]]** (Quy hoạch tuyến tính)
- [[CH12 - Supply Chain Design]] — Thiết kế chuỗi cung ứng
- **[[Transportation Cost]]** (Chi phí vận chuyển)

---

## 5. **[[Geographical Information Systems]]** (Hệ thống thông tin địa lý - GIS)

### Định nghĩa (Definition)
[[GIS]] là hệ thống phần mềm tích hợp dữ liệu địa lý (bản đồ) với dữ liệu kinh doanh (dân số, thu nhập, giao thông, vị trí đối thủ) để hỗ trợ quyết định vị trí.

![Figure 13.6 - Geographical Information Systems](/images/figures/ch13_fig13.6.jpg)
> *Figure 13.6: Hệ thống thông tin địa lý (GIS) — tích hợp dữ liệu địa lý và kinh doanh để hỗ trợ quyết định vị trí*

### Giải thích chi tiết
GIS cho phép doanh nghiệp **trực quan hóa** dữ liệu trên bản đồ, giúp:

- **Phân tích thị trường**: Xác định khu vực có mật độ khách hàng cao, thu nhập phù hợp
- **Phân tích đối thủ**: Xem vị trí đối thủ để tìm "khoảng trống" thị trường
- **Phân tích giao thông**: Đánh giá khả năng tiếp cận từ các tuyến đường chính
- **Phân tích rủi ro**: Xác định vùng ngập lụt, động đất, hoặc rủi ro thiên tai
- **Tối ưu hóa mạng lưới**: Xác định vị trí tối ưu cho kho hàng, trung tâm phân phối

**Các lớp dữ liệu (layers) trong GIS**:
1. Lớp đường giao thông
2. Lớp dân cư
3. Lớp kinh tế (thu nhập, GDP)
4. Lớp khách hàng hiện tại
5. Lớp đối thủ cạnh tranh
6. Lớp cơ sở hạ tầng (điện, nước, viễn thông)

### Ví dụ thực tế
- **Starbucks**: Sử dụng GIS (phần mềm Atlas) để phân tích vị trí mở cửa hàng mới — kết hợp dữ liệu dân số, lưu lượng giao thông, vị trí đối thủ, thu nhập trung bình khu vực.
- **Grab/Be**: Sử dụng dữ liệu GIS để tối ưu hóa vị trí đặt trạm sạc xe điện, hub giao hàng.
- **Bách Hóa Xanh**: Phân tích mật độ dân cư và thu nhập để chọn vị trí mở cửa hàng mới trong khu dân cư.

### Liên kết
- **[[Load-Distance Method]]** (Phương pháp Tải-Khoảng cách) — Kết hợp GIS với phân tích định lượng
- [[Big Data Analytics]] — Nguồn dữ liệu cho GIS
- [[Digital Transformation]] — Chuyển đổi số

---

## 6. Chiến lược kho hàng trong mạng lưới Logistics (Warehouse Strategy in Logistics Networks)

![Figure 13.10 - Warehouse Strategy](/images/figures/ch13_fig13.10.jpg)
> *Figure 13.10: Chiến lược kho hàng — so sánh kho tập trung và kho phân tán trong mạng lưới logistics*

### 6.1 **[[Inventory Placement]]** (Đặt vị trí tồn kho)

**Định nghĩa**: Quyết định nên đặt hàng tồn kho ở đâu trong mạng lưới logistics — tập trung ([[centralized]]) hay phân tán ([[decentralized]]).

#### **[[Centralized Warehousing]]** (Kho tập trung)
- **Mô tả**: Một hoặc ít kho lớn phục vụ khu vực rộng
- **Ưu điểm**: Giảm tổng tồn kho an toàn (nhờ hiệu ứng gộp — [[Risk Pooling Effect]]), giảm chi phí kho bãi, dễ quản lý
- **Nhược điểm**: Thời gian giao hàng dài hơn, chi phí vận chuyển "last mile" cao hơn
- **Phù hợp**: Sản phẩm có giá trị cao, nhu cầu thấp, hoặc khi chi phí tồn kho > chi phí vận chuyển

#### **[[Decentralized Warehousing]]** (Kho phân tán)
- **Mô tả**: Nhiều kho nhỏ đặt gần khách hàng
- **Ưu điểm**: Giao hàng nhanh, dịch vụ khách hàng tốt hơn
- **Nhược điểm**: Tổng tồn kho cao hơn (mỗi kho cần tồn kho an toàn riêng), chi phí vận hành nhiều kho
- **Phù hợp**: Sản phẩm cần giao nhanh, nhu cầu cao, hoặc khi tốc độ giao hàng là lợi thế cạnh tranh

**Ví dụ**:
- **Amazon**: Kết hợp cả hai — kho lớn (Fulfillment Centers) cho hàng chung + nhiều trạm giao hàng nhỏ (Delivery Stations) gần khu dân cư để giao trong ngày.
- **Lazada/Shopee**: Đặt kho lớn ở TP.HCM và Hà Nội, cùng nhiều hub nhỏ ở các tỉnh thành lớn.

### 6.2 **[[Autonomous Warehouse]]** Operations (Kho hàng tự trị)

**Định nghĩa**: Kho hàng sử dụng [[robot]], [[AI]], [[IoT]] để tự động hóa phần lớn hoạt động — từ nhận hàng, lưu kho, lấy hàng, đóng gói đến xuất kho.

**Công nghệ chính**:
- **[[AGV]]** (Automated Guided Vehicles): Xe tự hành di chuyển hàng trong kho
- **[[AS-RS|AS/RS]]** (Automated Storage and Retrieval Systems): Hệ thống tự động lưu trữ và lấy hàng
- **[[Robot pick-and-pack]]**: Robot lấy hàng từ kệ và đóng gói
- **[[Drone trong kho]]**: Drone kiểm kê hàng tồn kho trên kệ cao
- **[[Warehouse Management System]] ([[WMS]])**: Phần mềm quản lý kho thông minh tích hợp AI

**Lợi ích**:
- Tăng tốc độ xử lý đơn hàng (từ hàng giờ → vài phút)
- Giảm sai sót (error rate gần 0%)
- Hoạt động 24/7 không cần nghỉ
- Tối ưu hóa không gian kho (kệ cao hơn, lối đi hẹp hơn)

### Ví dụ thực tế
- **Amazon Robotics**: Hơn 750.000 robot Kiva/Proteus trong kho, giảm thời gian xử lý đơn hàng từ 60-75 phút xuống 15 phút.
- **Cainiao (Alibaba)**: Kho tự động tại Huiyang xử lý 1 triệu gói/ngày chỉ với vài chục nhân viên giám sát.
- **JD.com**: Kho "tối" (dark warehouse) hoàn toàn tự động — không cần ánh sáng vì không có con người bên trong.

### Liên kết
- [[CH12 - Supply Chain Design]] — Chuỗi cung ứng tự trị
- Quản lý tồn kho — Inventory Management
- [[Risk Pooling Effect]] — Hiệu ứng gộp rủi ro

---

## 7. Quy trình lựa chọn vị trí có hệ thống (Systematic Location Selection Process)

### Giải thích chi tiết

Quy trình chọn vị trí gồm các bước:

**Bước 1: Xác định tiêu chí** (Identify Criteria)
- Liệt kê tất cả yếu tố quan trọng (chi phí, thị trường, hạ tầng, nhân lực, v.v.)
- Xác định trọng số cho mỗi tiêu chí dựa trên chiến lược kinh doanh

**Bước 2: Xác định khu vực** (Identify Region)
- Chọn quốc gia / vùng miền dựa trên yếu tố vĩ mô (kinh tế, chính trị, pháp luật)

**Bước 3: Xác định cộng đồng/tỉnh thành** (Identify Community)
- Thu hẹp xuống tỉnh / thành phố dựa trên yếu tố trung mô (hạ tầng, lao động, ưu đãi)

**Bước 4: Xác định địa điểm cụ thể** (Identify Site)
- Chọn lô đất / tòa nhà cụ thể dựa trên yếu tố vi mô (diện tích, giá thuê, tiện ích)

**Bước 5: Phân tích định lượng**
- Áp dụng Phương pháp Tải-Khoảng cách, Phân tích điểm hòa vốn, Phương pháp vận tải
- Sử dụng [[GIS]] để trực quan hóa

**Bước 6: Ra quyết định**
- Kết hợp phân tích định lượng với đánh giá định tính
- Có thể dùng **[[Weighted Scoring Method]]** (Phương pháp cho điểm có trọng số) để tổng hợp

### Ví dụ: Phương pháp cho điểm có trọng số

| Tiêu chí | Trọng số | Điểm VT A | Điểm VT B | Tổng A | Tổng B |
|----------|---------|-----------|-----------|--------|--------|
| Chi phí lao động | 0.30 | 8 | 6 | 2.40 | 1.80 |
| Gần thị trường | 0.25 | 6 | 9 | 1.50 | 2.25 |
| Hạ tầng | 0.20 | 7 | 7 | 1.40 | 1.40 |
| Ưu đãi thuế | 0.15 | 9 | 5 | 1.35 | 0.75 |
| Chất lượng sống | 0.10 | 5 | 8 | 0.50 | 0.80 |
| **Tổng** | **1.00** | | | **7.15** | **7.00** |

→ Chọn **Vị trí A** (7.15 > 7.00)

### Liên kết
- **[[Weighted Scoring Method]]** (Phương pháp cho điểm có trọng số)
- **[[Multi-Criteria Decision Making]]** (Ra quyết định đa tiêu chí)

---

## Công thức quan trọng (Key Formulas)

| Công thức | Ý nghĩa |
|-----------|---------|
| $d = \sqrt{(x_A - x_B)^2 + (y_A - y_B)^2}$ | Khoảng cách Euclid |
| $d = \|x_A - x_B\| + \|y_A - y_B\|$ | Khoảng cách Rectilinear |
| $ld = \sum_{i} l_i \times d_i$ | Điểm Tải-Khoảng cách |
| $x^* = \frac{\sum l_i x_i}{\sum l_i}$, $y^* = \frac{\sum l_i y_i}{\sum l_i}$ | **[[Center of Gravity]]** (Trọng tâm) |
| $TC = F + cQ$ | Tổng chi phí tại một vị trí |
| $Q^* = \frac{F_B - F_A}{c_A - c_B}$ | Điểm hòa vốn giữa hai vị trí |

---

## Từ khóa chính (Key Terms)

- **[[Location Decision]]** (Quyết định vị trí)
- **[[Load-Distance Method]]** (Phương pháp Tải-Khoảng cách)
- **[[Euclidean Distance]]** (Khoảng cách Euclid)
- **[[Rectilinear Distance]]** (Khoảng cách Rectilinear / Manhattan Distance)
- **[[Center of Gravity]]** (Trọng tâm)
- **[[Break-Even Analysis]]** (Phân tích điểm hòa vốn)
- **[[Fixed Cost]]** (Chi phí cố định)
- **[[Variable Cost]]** (Chi phí biến đổi)
- **[[Transportation Method]]** (Phương pháp vận tải)
- **[[Dummy Plant]]** / **[[Dummy Warehouse]]** (Nhà máy ảo / Kho hàng ảo)
- [[GIS]] (Geographical Information Systems)
- **[[Centralized Warehousing]]** (Kho tập trung)
- **[[Decentralized Warehousing]]** (Kho phân tán)
- **[[Autonomous Warehouse]]** (Kho hàng tự trị)
- [[Risk Pooling Effect]] (Hiệu ứng gộp rủi ro)
- **[[Weighted Scoring Method]]** (Phương pháp cho điểm có trọng số)
- [[AGV]] (Automated Guided Vehicles)
- [[WMS]] (Warehouse Management System)

---

> **Xem thêm**: [[CH12 - Supply Chain Design]] | [[CH14 - Supply Chain Integration]] | [[CH15 - Supply Chain Sustainability]]

