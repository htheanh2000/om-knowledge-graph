---
tags: [chapter-11, part3, MRP, MPS, BOM, ERP, resource-planning, dependent-demand]
aliases: [Hoạch định nguồn lực, Resource Planning, MRP, ERP]
---
# Chapter 11 - Resource Planning (Hoạch định nguồn lực)

## Tổng quan (Overview)

[[Resource Planning]] là quá trình xác định **chính xác** cần những gì, bao nhiêu, và khi nào để đáp ứng kế hoạch sản xuất. Nếu [[S&OP - Sales and Operations Planning]] (Chapter 10) trả lời "sản xuất bao nhiêu sản phẩm cuối?", thì chương này trả lời "cần bao nhiêu linh kiện, nguyên vật liệu, và khi nào phải đặt hàng?"

Trung tâm của chương là [[Material Requirements Planning (MRP)]] -- hệ thống tính toán nhu cầu [[Dependent Demand]] (nhu cầu phụ thuộc) cho tất cả linh kiện và nguyên vật liệu dựa trên [[Master Production Schedule (MPS)]]. MRP là bước đột phá so với các phương pháp tồn kho truyền thống ([[EOQ]], [[Reorder Point]]) vốn được thiết kế cho [[Independent Demand]].

Chương cũng giới thiệu [[Enterprise Resource Planning (ERP)]] -- hệ thống phần mềm tích hợp toàn diện mở rộng từ MRP, kết nối tất cả bộ phận trong doanh nghiệp: từ sản xuất, tồn kho, tài chính, nhân sự, đến bán hàng.

---

## Dependent Demand Concept (Khái niệm nhu cầu phụ thuộc)

### Định nghĩa (Definition)
[[Dependent Demand]] (Nhu cầu phụ thuộc) là nhu cầu cho một mặt hàng được **suy ra trực tiếp** từ nhu cầu của mặt hàng khác (thường là sản phẩm cuối).

### Giải thích chi tiết (Detailed Explanation)

#### So sánh [[Independent Demand]] vs [[Dependent Demand]]:

| | [[Independent Demand]] | [[Dependent Demand]] |
|--|----------------------|---------------------|
| **Định nghĩa** | Nhu cầu từ khách hàng bên ngoài | Nhu cầu suy ra từ sản phẩm cấp trên |
| **Ví dụ** | Xe máy Honda Wave (khách mua) | Piston, xích, nhông (để lắp xe) |
| **Dự báo** | Phải dự báo ([[Forecasting]]) | **Tính toán** chính xác từ MPS |
| **Mẫu nhu cầu** | Liên tục, tương đối đều | Gián đoạn, theo lô (lumpy) |
| **Quản lý** | [[EOQ]], [[Reorder Point]] | [[Material Requirements Planning (MRP)]] |

**Tại sao quan trọng?**
- Nếu biết cần sản xuất 1.000 xe máy, ta BIẾT CHÍNH XÁC cần 1.000 piston, 1.000 xích, 2.000 bánh xe...
- Không cần dự báo! Chỉ cần **tính toán** → chính xác hơn, ít tồn kho hơn
- Nhu cầu phụ thuộc thường "lumpy" (gián đoạn): cần 0 đơn vị nhiều tuần, rồi đột ngột cần 500 đơn vị

### Ví dụ thực tế (Real-world Example)
Nhà máy Samsung lắp ráp điện thoại Galaxy S25:
- [[Independent Demand]]: 100.000 chiếc Galaxy S25 (từ dự báo thị trường)
- [[Dependent Demand]]: 100.000 màn hình AMOLED, 100.000 chip Snapdragon, 100.000 pin, 200.000 camera (vì mỗi máy có 2 camera)...
- Tất cả được **tính toán** chính xác từ [[Bill of Materials (BOM)]]

### Liên kết (Related Concepts)
- [[Material Requirements Planning (MRP)]]
- [[Independent Demand]]
- [[Bill of Materials (BOM)]]
- [[Inventory Management]]

---

## Master Production Scheduling (MPS)

### Định nghĩa (Definition)
[[Master Production Schedule (MPS)]] là kế hoạch sản xuất chi tiết cho **từng sản phẩm cuối** (hoặc module chính) theo **từng tuần**, cho biết sản xuất bao nhiêu và khi nào. MPS là "đầu vào" chính của [[Material Requirements Planning (MRP)]].

### Giải thích chi tiết (Detailed Explanation)

#### Vị trí của MPS trong hệ thống kế hoạch:
```
S&OP (product family, tháng)
    ↓ Phân rã (Disaggregation)
MPS (sản phẩm cụ thể, tuần)
    ↓ 
MRP (linh kiện, tuần)
```

#### Developing MPS (Xây dựng MPS):

MPS cân bằng giữa:
- **Nhu cầu**: Dự báo ([[Forecasting]]) + Đơn hàng thực tế ([[Customer Orders]])
- **Cung**: Công suất sản xuất, tồn kho hiện có, hàng đang sản xuất

**Quy tắc**: MPS sử dụng giá trị LỚN HƠN giữa Forecast và Customer Orders cho mỗi tuần (hoặc logic phức tạp hơn tùy chiến lược [[Make-to-Stock]] vs [[Make-to-Order]]).

#### [[Available-to-Promise (ATP)]]

[[Available-to-Promise (ATP)]] cho biết số lượng sản phẩm **có thể hứa giao** cho khách hàng mới mà không ảnh hưởng đơn hàng đã nhận.

$$ATP_t = \text{MPS}_t - \text{Customer Orders đã nhận cho các tuần tới}$$

**Ví dụ**:
| Tuần | 1 | 2 | 3 | 4 |
|------|---|---|---|---|
| Forecast | 30 | 30 | 30 | 30 |
| Customer Orders | 35 | 20 | 10 | 5 |
| MPS | 40 | 0 | 40 | 0 |
| Projected On-Hand (bắt đầu = 10) | 15 | -15→ cần MPS | ... | ... |

ATP tuần 1 = MPS(40) - Đơn hàng tuần 1&2 (35+20) = Cần tính lại theo logic cụ thể.

#### [[MPS Freezing]] (Đóng băng MPS)

- **[[Frozen Zone]]** (Vùng đóng băng): Vài tuần đầu, KHÔNG được thay đổi MPS (đã mua nguyên liệu, đã lên lịch). Thường 1-2 tuần.
- **[[Slushy Zone]]** (Vùng bán đóng): Có thể thay đổi nhưng cần phê duyệt
- **[[Liquid Zone]]** (Vùng linh hoạt): Thay đổi tự do

```
|←— Frozen —→|←— Slushy —→|←— Liquid —→|
   Tuần 1-2      Tuần 3-4      Tuần 5+
   Không đổi     Cần duyệt     Tự do đổi
```

### Ví dụ thực tế (Real-world Example)
Toyota Việt Nam có MPS cho Vios: tuần 15 sản xuất 200 chiếc Vios 1.5G (trắng 80, đen 60, bạc 60). MPS đã frozen cho tuần 15-16 (nguyên liệu đã đặt), slushy cho tuần 17-18, liquid từ tuần 19.

### Liên kết (Related Concepts)
- [[S&OP - Sales and Operations Planning]]
- [[Material Requirements Planning (MRP)]]
- [[Available-to-Promise (ATP)]]
- [[Rough-Cut Capacity Planning]]
- [[Make-to-Stock]]
- [[Make-to-Order]]

---

## Bill of Materials (BOM)


### Định nghĩa (Definition)
[[Bill of Materials (BOM)]] (Bảng kê vật liệu / Cấu trúc sản phẩm) liệt kê **tất cả** linh kiện, bộ phận, và nguyên vật liệu cần thiết để sản xuất **một đơn vị** sản phẩm cuối, cùng với số lượng mỗi loại.

### Giải thích chi tiết (Detailed Explanation)

#### [[Product Structure Tree]] (Cây cấu trúc sản phẩm):

Biểu diễn trực quan BOM theo các cấp (Level):

```
Level 0:         [Xe đạp] (1)
                 /        \
Level 1:    [Khung] (1)   [Bộ bánh xe] (2)
            /    \              |
Level 2: [Ống thép](3) [Yên](1)  [Vành](1) [Lốp](1) [Nan hoa](36)
```

- **Level 0**: Sản phẩm cuối ([[End Item]] / [[Finished Good]])
- **Level 1**: Cụm lắp ráp chính ([[Subassembly]])
- **Level 2**: Linh kiện/nguyên liệu thô ([[Component]] / [[Raw Material]])
- Có thể nhiều level hơn tùy độ phức tạp sản phẩm

#### Quy tắc quan trọng:
- **[[Usage Quantity]]**: Số lượng cần cho MỘT đơn vị cấp trên
  - 1 xe đạp cần 2 bộ bánh xe → usage = 2
  - 1 bộ bánh xe cần 36 nan hoa → usage = 36
  - → 1 xe đạp cần 2 × 36 = **72 nan hoa**

- **[[Low-Level Coding]]**: Mỗi item chỉ xuất hiện ở MỘT level (level thấp nhất mà nó xuất hiện). Điều này đảm bảo MRP tính toán đúng khi một linh kiện dùng ở nhiều sản phẩm.

- **[[Parent-Component Relationship]]**: Item cấp trên = Parent, item cấp dưới = Component

### Ví dụ thực tế (Real-world Example)
BOM của một ly trà sữa Gong Cha:
```
Level 0: Trà sữa trân châu đường nâu (1 ly)
├── Level 1: Trà pha (1 phần) 
│   ├── Level 2: Trà đen (10g)
│   └── Level 2: Nước nóng (200ml)
├── Level 1: Sữa tươi (100ml)
├── Level 1: Trân châu đường nâu (1 phần)
│   ├── Level 2: Bột trân châu (30g)
│   └── Level 2: Đường nâu (15g)
├── Level 1: Đá (150g)
└── Level 1: Ly + nắp + ống hút (1 bộ)
```

### Liên kết (Related Concepts)
- [[Material Requirements Planning (MRP)]]
- [[Product Structure Tree]]
- [[Dependent Demand]]
- [[MRP Explosion]]

---

## MRP Explosion Process (Quy trình bung MRP)

### Định nghĩa (Definition)
[[MRP Explosion]] là quá trình tính toán nhu cầu cho TẤT CẢ linh kiện và nguyên vật liệu, bắt đầu từ [[Master Production Schedule (MPS)]] và "bung" (explode) xuống qua từng cấp của [[Bill of Materials (BOM)]].

### Giải thích chi tiết (Detailed Explanation)

#### 3 đầu vào chính của MRP:
1. **[[Master Production Schedule (MPS)]]**: Sản xuất bao nhiêu sản phẩm cuối, khi nào
2. **[[Bill of Materials (BOM)]]**: Cấu trúc sản phẩm, số lượng linh kiện
3. **[[Inventory Record]]**: Tồn kho hiện có, hàng đã đặt, lead time

#### Quy trình bung:
1. Bắt đầu từ Level 0 (sản phẩm cuối) theo MPS
2. Tính [[Gross Requirements]] cho mỗi component ở Level 1
3. Trừ tồn kho và hàng đã đặt → [[Net Requirements]]
4. Xác định [[Planned Order Releases]] (khi nào phải đặt, dựa trên [[Lead Time]])
5. Planned Order Releases ở Level 1 → trở thành Gross Requirements ở Level 2
6. Lặp lại xuống các level thấp hơn

**Ví dụ đơn giản**:
- MPS: 100 xe đạp tuần 8
- BOM: 1 xe đạp cần 2 bánh xe, lead time bánh xe = 2 tuần
- → Gross Requirement bánh xe: 200 cái tuần 8
- Tồn kho bánh xe: 50 cái → Net Requirement: 150 cái tuần 8
- Lead time = 2 tuần → Planned Order Release: 150 cái tuần **6**

### Liên kết (Related Concepts)
- [[Material Requirements Planning (MRP)]]
- [[Bill of Materials (BOM)]]
- [[Inventory Record]]
- [[Lead Time]]
- [[Lot Sizing]]

---

## Inventory Record (Bản ghi tồn kho)


### Định nghĩa (Definition)
[[Inventory Record]] (MRP Record / MRP Grid) là bảng tính chi tiết cho MỖI item, theo dõi tình trạng tồn kho và nhu cầu theo tuần.

### Giải thích chi tiết (Detailed Explanation)

#### Cấu trúc bảng MRP Record:

**Item: Bánh xe | Lead Time: 2 tuần | Lot Size: L4L | Safety Stock: 0**

| | Tuần 1 | Tuần 2 | Tuần 3 | Tuần 4 | Tuần 5 | Tuần 6 | Tuần 7 | Tuần 8 |
|--|--------|--------|--------|--------|--------|--------|--------|--------|
| **[[Gross Requirements]]** | 0 | 0 | 40 | 0 | 60 | 0 | 0 | 200 |
| **[[Scheduled Receipts]]** | 0 | 50 | 0 | 0 | 0 | 0 | 0 | 0 |
| **[[Projected On-Hand Inventory]]** | 70 | 120 | 80 | 80 | 20 | 20 | 20 | 0 |
| **[[Net Requirements]]** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 180 |
| **[[Planned Order Receipts]]** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 180 |
| **[[Planned Order Releases]]** | 0 | 0 | 0 | 0 | 0 | **180** | 0 | 0 |

#### Giải thích từng hàng:

1. **[[Gross Requirements]]** (Nhu cầu thô): Tổng nhu cầu cho item này mỗi tuần (từ MPS hoặc từ Planned Order Releases của parent)

2. **[[Scheduled Receipts]]** (Lượng nhận dự kiến): Đơn hàng ĐÃ đặt, đang trên đường → sẽ nhận ở tuần nào

3. **[[Projected On-Hand Inventory]]** (Tồn kho dự kiến): 
$$POH_t = POH_{t-1} + SR_t + POR_t - GR_t$$
(Tồn kho kỳ trước + Nhận dự kiến + Nhận theo kế hoạch - Nhu cầu thô)

4. **[[Net Requirements]]** (Nhu cầu ròng):
$$NR_t = GR_t - POH_{t-1} - SR_t$$
(Chỉ khi > 0, nếu ≤ 0 thì NR = 0)

5. **[[Planned Order Receipts]]** (Lượng nhận theo kế hoạch): Lượng hàng dự kiến nhận để đáp ứng NR (tùy [[Lot Sizing]])

6. **[[Planned Order Releases]]** (Lệnh đặt hàng theo kế hoạch): = Planned Order Receipts nhưng **lùi lại Lead Time tuần**. Đây là OUTPUT quan trọng nhất! Cho biết phải đặt hàng KHI NÀO.

### Ví dụ thực tế (Real-world Example)
Tuần 8 cần 200 bánh xe, tồn kho đến tuần 7 còn 20 → Net Requirement = 180. Lead time = 2 tuần → phải đặt 180 bánh xe ở tuần 6 (2 tuần trước tuần 8). Planned Order Release tuần 6 = 180.

### Liên kết (Related Concepts)
- [[Material Requirements Planning (MRP)]]
- [[MRP Explosion]]
- [[Lead Time]]
- [[Lot Sizing]]
- [[Safety Stock]]

---

## Planning Factors (Các yếu tố lập kế hoạch)

### Định nghĩa (Definition)
Các yếu tố ảnh hưởng đến cách MRP tính toán, đặc biệt là [[Lead Time]] và [[Lot Sizing]].

### Giải thích chi tiết (Detailed Explanation)

#### [[Lead Time]] (Thời gian giao hàng / Thời gian chờ)
- Cho mua hàng: Thời gian từ đặt hàng → nhận hàng (bao gồm xử lý đơn, sản xuất bên NCC, vận chuyển)
- Cho sản xuất: Thời gian từ bắt đầu → hoàn thành lô sản xuất (bao gồm chờ, setup, gia công, di chuyển)
- **MRP offset (lùi) Planned Order Release theo Lead Time**

#### [[Lot Sizing]] (Xác định kích thước lô)

Ba phương pháp phổ biến:

**1. [[Lot-for-Lot (L4L)]]** (Đặt đúng nhu cầu)
- Đặt **chính xác** bằng Net Requirement mỗi tuần
- Tồn kho = 0 → [[Holding Cost]] = 0
- Nhưng số lần đặt hàng nhiều → [[Ordering Cost]] cao
- **Phù hợp**: Item đắt tiền (nhóm A), nhu cầu lumpy

| Tuần | NR | Planned Order |
|------|-----|--------------|
| 3 | 40 | 40 |
| 5 | 60 | 60 |
| 8 | 180 | 180 |

**2. [[Fixed Order Quantity (FOQ)]]** (Lượng đặt cố định)
- Đặt một lượng Q cố định mỗi lần (thường = [[EOQ]] hoặc bội số container)
- Có thể thừa (để lại cho tuần sau)
- **Phù hợp**: Item có EOQ rõ ràng, nhà cung cấp yêu cầu đặt theo lô

| Tuần | NR | Planned Order (Q=100) | Thừa |
|------|-----|----------------------|------|
| 3 | 40 | 100 | 60 |
| 5 | 60 | 0 (dùng thừa) | 0 |
| 8 | 180 | 200 (2×100) | 20 |

**3. [[Periodic Order Quantity (POQ)]]** (Đặt theo chu kỳ)
- Đặt đủ cho P tuần tới (P = EOQ/nhu cầu trung bình/tuần)
- Kết hợp ưu điểm L4L (ít tồn kho) và FOQ (ít lần đặt)
- **Phù hợp**: Item có nhu cầu tương đối đều

| Tuần | NR | Planned Order (P=3 tuần) |
|------|-----|--------------------------|
| 3 | 40 | 40+60 = 100 (đủ tuần 3-5) |
| 8 | 180 | 180 |

### Liên kết (Related Concepts)
- [[Material Requirements Planning (MRP)]]
- [[Economic Order Quantity (EOQ)]]
- [[Holding Cost]]
- [[Ordering Cost]]

---

## Outputs from MRP: Action Notices (Đầu ra MRP: Thông báo hành động)

### Định nghĩa (Definition)
[[Action Notices]] (hay [[Exception Reports]]) là các thông báo từ hệ thống MRP yêu cầu người lập kế hoạch thực hiện hành động cụ thể.

### Giải thích chi tiết (Detailed Explanation)

#### Các loại Action Notice:

| Thông báo | Ý nghĩa | Hành động |
|-----------|---------|----------|
| **Release Order** | Đến lúc phải đặt hàng | Phát lệnh đặt hàng/sản xuất |
| **Expedite** | Cần hàng sớm hơn dự kiến | Liên hệ NCC giao sớm, tăng ca |
| **De-expedite** | Không cần sớm như đã đặt | Hoãn đơn hàng, giảm tồn kho |
| **Cancel** | Không cần nữa | Hủy đơn hàng chưa giao |
| **Increase Quantity** | Cần nhiều hơn | Tăng số lượng đơn hàng |
| **Decrease Quantity** | Cần ít hơn | Giảm số lượng đơn hàng |

#### [[Capacity Requirements Planning (CRP)]]:
- MRP tính nhu cầu vật liệu nhưng **không kiểm tra công suất**
- CRP kiểm tra: MRP plan có vượt quá [[Capacity]] tại các [[Work Center]] không?
- Nếu vượt → cần điều chỉnh MPS hoặc tăng công suất

### Ví dụ thực tế (Real-world Example)
Hệ thống MRP của nhà máy VinFast phát thông báo: "Expedite đơn hàng pin LFP #4523 -- cần nhận tuần 12 thay vì tuần 14 do MPS tăng sản lượng VF5." Bộ phận mua hàng liên hệ nhà cung cấp CATL để đẩy nhanh giao hàng.

### Liên kết (Related Concepts)
- [[Material Requirements Planning (MRP)]]
- [[Capacity Requirements Planning (CRP)]]
- [[Purchasing Management]]
- [[Shop Floor Control]]

---

## Enterprise Resource Planning (ERP)


### Định nghĩa (Definition)
[[Enterprise Resource Planning (ERP)]] là hệ thống phần mềm **tích hợp toàn diện** quản lý TẤT CẢ quy trình kinh doanh trong một tổ chức trên **một cơ sở dữ liệu duy nhất**. ERP phát triển từ MRP → MRP II → ERP.

### Giải thích chi tiết (Detailed Explanation)

#### Lịch sử phát triển:
```
MRP (1960s-70s)     → Chỉ tính nhu cầu vật liệu
    ↓
MRP II (1980s)      → Thêm capacity planning, shop floor, purchasing
    ↓
ERP (1990s-nay)     → Tích hợp toàn bộ: finance, HR, CRM, SCM...
    ↓
ERP II / Cloud ERP  → Mở rộng ra ngoài doanh nghiệp (nhà cung cấp, khách hàng)
```

#### Các module chính của ERP:

| Module | Chức năng | Liên kết OM |
|--------|----------|-------------|
| **[[Manufacturing-Production|Manufacturing/Production]]** | MRP, MPS, Shop Floor | [[Material Requirements Planning (MRP)]], [[Scheduling]] |
| **[[Finance-Accounting|Finance/Accounting]]** | Sổ cái, công nợ, ngân sách | [[Cost Management]] |
| **[[Human Resources]]** | Tuyển dụng, lương, đào tạo | [[Workforce Planning]] |
| **[[Supply Chain Management]]** | Mua hàng, logistics | [[Supply Chain Management]], [[Inventory Management]] |
| **[[Customer Relationship Management (CRM)]]** | Bán hàng, dịch vụ KH | [[Demand Management]] |
| **[[Business Intelligence]]** | Báo cáo, phân tích | [[Data Analytics]] |

#### Cách ERP hoạt động:
- **Một cơ sở dữ liệu duy nhất** ([[Single Database]]): Tất cả phòng ban dùng chung → không có "ốc đảo thông tin" ([[Information Silos]])
- **Real-time**: Khi Sales nhập đơn hàng → Finance thấy doanh thu → Production thấy nhu cầu → Warehouse thấy lệnh xuất kho → tất cả đồng thời

#### Lợi ích:
- Loại bỏ dữ liệu trùng lặp và mâu thuẫn
- Thông tin real-time cho quyết định nhanh hơn
- Tự động hóa quy trình (giảm giấy tờ, sai sót)
- Chuẩn hóa quy trình ([[Best Practices]])
- [[Visibility]] xuyên suốt chuỗi cung ứng

#### Thách thức:
- **Chi phí rất cao**: SAP, Oracle ERP tốn hàng triệu USD + tư vấn
- **Thời gian triển khai**: 1-3 năm (thậm chí lâu hơn)
- **Thay đổi tổ chức**: Nhân viên phải thay đổi cách làm việc → phản kháng
- **Rủi ro thất bại**: ~50% dự án ERP không đạt kỳ vọng ban đầu

#### Nhà cung cấp ERP phổ biến:
- **[[SAP]]**: Lớn nhất thế giới, mạnh về manufacturing (SAP S/4HANA)
- **[[Oracle]]**: Mạnh về finance và database
- **[[Microsoft Dynamics]]**: Phù hợp SME
- **Odoo**: Mã nguồn mở, phổ biến ở Việt Nam cho SME

### Ví dụ thực tế (Real-world Example)
Vinamilk triển khai SAP ERP cho toàn bộ hệ thống: từ quản lý 13 nhà máy (production planning), 200.000+ điểm bán (distribution), nguyên liệu từ 10.000+ hộ nông dân (procurement), đến tài chính và nhân sự 10.000+ nhân viên. Khi đại lý tại Cần Thơ bán 100 thùng sữa, hệ thống tự động cập nhật tồn kho kho miền Tây, trigger MRP tính lại nhu cầu sản xuất, và cập nhật doanh thu real-time.

### Liên kết (Related Concepts)
- [[Material Requirements Planning (MRP)]]
- [[Supply Chain Management]]
- [[Information Systems]]
- [[Digital Transformation]]
- [[Cloud Computing]]

---

## Resource Planning for Service Providers (Hoạch định nguồn lực cho nhà cung cấp dịch vụ)

### Định nghĩa (Definition)
Dịch vụ cũng cần hoạch định nguồn lực, nhưng thay vì [[Bill of Materials (BOM)]], dùng **[[Bill of Resources]]** -- liệt kê các nguồn lực (nhân lực, thiết bị, vật tư) cần cho mỗi dịch vụ.

### Giải thích chi tiết (Detailed Explanation)

#### So sánh Manufacturing vs Service:

| | Sản xuất | Dịch vụ |
|--|----------|---------|
| BOM | Linh kiện, nguyên liệu | Nhân lực, phòng, thiết bị |
| MPS | Số sản phẩm/tuần | Số khách/ca trực/phòng mổ |
| MRP | Nhu cầu vật liệu | Nhu cầu nhân lực + vật tư |
| Tồn kho | Linh kiện, thành phẩm | Vật tư tiêu hao, thuốc |
| Lead Time | Mua hàng + sản xuất | Đào tạo + chuẩn bị |

#### [[Bill of Resources]] cho dịch vụ:

**Ví dụ: 1 ca phẫu thuật nội soi**
```
Level 0: Phẫu thuật nội soi (1 ca)
├── Nhân lực: 1 bác sĩ phẫu thuật (2 giờ)
├── Nhân lực: 1 bác sĩ gây mê (2.5 giờ)
├── Nhân lực: 2 y tá phụ mổ (2 giờ)
├── Phòng mổ: 1 phòng (3 giờ, gồm chuẩn bị)
├── Thiết bị: 1 bộ nội soi
└── Vật tư tiêu hao: bộ dụng cụ mổ, thuốc, băng gạc...
```

#### [[Dependent Demand]] trong dịch vụ:
- Nếu lịch mổ tuần tới có 20 ca nội soi → cần 20 bộ dụng cụ, 40 y tá-ca, 20 bác sĩ phẫu thuật-ca...
- Tính toán giống MRP!

### Ví dụ thực tế (Real-world Example)
Bệnh viện Chợ Rẫy dùng hệ thống ERP y tế (HIS - Hospital Information System) để lập kế hoạch: lịch mổ tuần tới → tính nhu cầu phòng mổ, nhân lực, thuốc gây mê, vật tư. Hệ thống tự động đặt thêm vật tư từ nhà cung cấp nếu tồn kho không đủ -- giống MRP cho sản xuất!

### Liên kết (Related Concepts)
- [[Service Operations]]
- [[Bill of Resources]]
- [[Capacity Planning]]
- [[Workforce Scheduling]]
- [[Healthcare Operations]]

---

## Công thức quan trọng (Key Formulas)

| Công thức | Ký hiệu | Mô tả |
|-----------|----------|-------|
| $GR = \text{Parent POR} \times \text{Usage Qty}$ | [[Gross Requirements]] | Nhu cầu thô = Lệnh SX cha × Số lượng BOM |
| $NR_t = GR_t - POH_{t-1} - SR_t$ | [[Net Requirements]] | Nhu cầu ròng (khi > 0) |
| $POH_t = POH_{t-1} + SR_t + POR_t - GR_t$ | [[Projected On-Hand Inventory]] | Tồn kho dự kiến |
| POR lùi Lead Time → Planned Order Release | [[Planned Order Releases]] | Thời điểm phải đặt hàng |
| $POQ = \text{round}(EOQ / \bar{d})$ | [[Periodic Order Quantity (POQ)]] | Chu kỳ đặt hàng (tuần) |

---

## Từ khóa chính (Key Terms)

- [[Resource Planning]] - Hoạch định nguồn lực
- [[Material Requirements Planning (MRP)]] - Hoạch định nhu cầu vật liệu
- [[Dependent Demand]] - Nhu cầu phụ thuộc
- [[Independent Demand]] - Nhu cầu độc lập
- [[Master Production Schedule (MPS)]] - Lịch trình sản xuất chính
- [[Available-to-Promise (ATP)]] - Lượng có thể hứa giao
- [[MPS Freezing]] - Đóng băng MPS
- [[Bill of Materials (BOM)]] - Bảng kê vật liệu
- [[Product Structure Tree]] - Cây cấu trúc sản phẩm
- [[MRP Explosion]] - Bung MRP
- [[Gross Requirements]] - Nhu cầu thô
- [[Scheduled Receipts]] - Lượng nhận dự kiến
- [[Projected On-Hand Inventory]] - Tồn kho dự kiến
- [[Net Requirements]] - Nhu cầu ròng
- [[Planned Order Releases]] - Lệnh đặt hàng theo kế hoạch
- [[Planned Order Receipts]] - Lượng nhận theo kế hoạch
- [[Lead Time]] - Thời gian chờ
- [[Lot-for-Lot (L4L)]] - Đặt đúng nhu cầu
- [[Fixed Order Quantity (FOQ)]] - Lượng đặt cố định
- [[Periodic Order Quantity (POQ)]] - Đặt theo chu kỳ
- [[Action Notices]] - Thông báo hành động
- [[Capacity Requirements Planning (CRP)]] - Hoạch định nhu cầu công suất
- [[Enterprise Resource Planning (ERP)]] - Hoạch định nguồn lực doanh nghiệp
- [[SAP]] - Nhà cung cấp ERP hàng đầu
- [[Bill of Resources]] - Bảng kê nguồn lực (dịch vụ)
- [[Low-Level Coding]] - Mã hóa cấp thấp
- [[Usage Quantity]] - Số lượng sử dụng


---
## Hình minh họa từ sách (Textbook Figures)

![Figure 11.1](/images/figures/ch11_fig11.1.jpg)
> *Figure 11.1*

![Figure 11.10](/images/figures/ch11_fig11.10.jpg)
> *Figure 11.10*

![Figure 11.11](/images/figures/ch11_fig11.11.jpg)
> *Figure 11.11*

![Figure 11.12](/images/figures/ch11_fig11.12.jpg)
> *Figure 11.12*

![Figure 11.13](/images/figures/ch11_fig11.13.jpg)
> *Figure 11.13*

![Figure 11.14](/images/figures/ch11_fig11.14.jpg)
> *Figure 11.14*

![Figure 11.15](/images/figures/ch11_fig11.15.jpg)
> *Figure 11.15*

![Figure 11.16](/images/figures/ch11_fig11.16.jpg)
> *Figure 11.16*

![Figure 11.17](/images/figures/ch11_fig11.17.jpg)
> *Figure 11.17*

![Figure 11.18](/images/figures/ch11_fig11.18.jpg)
> *Figure 11.18*

![Figure 11.19](/images/figures/ch11_fig11.19.jpg)
> *Figure 11.19*

![Figure 11.2](/images/figures/ch11_fig11.2.jpg)
> *Figure 11.2*

![Figure 11.20](/images/figures/ch11_fig11.20.jpg)
> *Figure 11.20*

![Figure 11.21](/images/figures/ch11_fig11.21.jpg)
> *Figure 11.21*

![Figure 11.22](/images/figures/ch11_fig11.22.jpg)
> *Figure 11.22*

![Figure 11.23](/images/figures/ch11_fig11.23.jpg)
> *Figure 11.23*

![Figure 11.24](/images/figures/ch11_fig11.24.jpg)
> *Figure 11.24*

![Figure 11.25](/images/figures/ch11_fig11.25.jpg)
> *Figure 11.25*

![Figure 11.26](/images/figures/ch11_fig11.26.jpg)
> *Figure 11.26*

![Figure 11.27](/images/figures/ch11_fig11.27.jpg)
> *Figure 11.27*

![Figure 11.28](/images/figures/ch11_fig11.28.jpg)
> *Figure 11.28*

![Figure 11.29](/images/figures/ch11_fig11.29.jpg)
> *Figure 11.29*

![Figure 11.3](/images/figures/ch11_fig11.3.jpg)
> *Figure 11.3*

![Figure 11.30](/images/figures/ch11_fig11.30.jpg)
> *Figure 11.30*

![Figure 11.31](/images/figures/ch11_fig11.31.jpg)
> *Figure 11.31*

![Figure 11.32](/images/figures/ch11_fig11.32.jpg)
> *Figure 11.32*

![Figure 11.33](/images/figures/ch11_fig11.33.jpg)
> *Figure 11.33*

![Figure 11.34](/images/figures/ch11_fig11.34.jpg)
> *Figure 11.34*

![Figure 11.35](/images/figures/ch11_fig11.35.jpg)
> *Figure 11.35*

![Figure 11.36](/images/figures/ch11_fig11.36.jpg)
> *Figure 11.36*

![Figure 11.37](/images/figures/ch11_fig11.37.jpg)
> *Figure 11.37*

![Figure 11.38](/images/figures/ch11_fig11.38.jpg)
> *Figure 11.38*

![Figure 11.39](/images/figures/ch11_fig11.39.jpg)
> *Figure 11.39*

![Figure 11.4](/images/figures/ch11_fig11.4.jpg)
> *Figure 11.4*

![Figure 11.40](/images/figures/ch11_fig11.40.jpg)
> *Figure 11.40*

![Figure 11.41](/images/figures/ch11_fig11.41.jpg)
> *Figure 11.41*

![Figure 11.42](/images/figures/ch11_fig11.42.jpg)
> *Figure 11.42*

![Figure 11.43](/images/figures/ch11_fig11.43.jpg)
> *Figure 11.43*

![Figure 11.44](/images/figures/ch11_fig11.44.jpg)
> *Figure 11.44*

![Figure 11.45](/images/figures/ch11_fig11.45.jpg)
> *Figure 11.45*

![Figure 11.46](/images/figures/ch11_fig11.46.jpg)
> *Figure 11.46*

![Figure 11.47](/images/figures/ch11_fig11.47.jpg)
> *Figure 11.47*

![Figure 11.48](/images/figures/ch11_fig11.48.jpg)
> *Figure 11.48*

![Figure 11.49](/images/figures/ch11_fig11.49.jpg)
> *Figure 11.49*

![Figure 11.5](/images/figures/ch11_fig11.5.jpg)
> *Figure 11.5*

![Figure 11.6](/images/figures/ch11_fig11.6.jpg)
> *Figure 11.6*

![Figure 11.7](/images/figures/ch11_fig11.7.jpg)
> *Figure 11.7*

![Figure 11.8](/images/figures/ch11_fig11.8.jpg)
> *Figure 11.8*

![Figure 11.9](/images/figures/ch11_fig11.9.jpg)
> *Figure 11.9*

