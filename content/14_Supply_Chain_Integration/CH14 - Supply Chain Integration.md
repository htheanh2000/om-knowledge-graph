---
tags: [chapter-14, part3, supply-chain-integration, bullwhip-effect, risk-management, blockchain, cloud-computing, VMI, order-fulfillment]
aliases: [Tích hợp chuỗi cung ứng, Supply Chain Integration, CH14]
---
# Chapter 14 - Supply Chain Integration (Tích hợp chuỗi cung ứng)

## Tổng quan (Overview)

Chương 14 bàn về việc tích hợp các quy trình và đối tác trong [[chuỗi cung ứng]] để tạo ra một hệ thống hoạt động đồng bộ và hiệu quả. Trong thực tế, các công ty không hoạt động một mình — họ là một phần của mạng lưới phức tạp gồm [[nhà cung cấp]], [[nhà phân phối]], [[nhà bán lẻ]], và [[khách hàng]]. [[Tích hợp chuỗi cung ứng]] nghĩa là kết nối và phối hợp tất cả các mắt xích này.

Chương đặc biệt quan trọng vì đề cập đến [[Hiệu ứng Bullwhip]] — một hiện tượng gây ra sự biến động nhu cầu ngày càng lớn khi đi ngược lên chuỗi cung ứng, dẫn đến lãng phí khổng lồ. Ngoài ra, chương cũng phân tích [[quản lý rủi ro chuỗi cung ứng]], vai trò của [[công nghệ đám mây]] và [[blockchain]], cùng bốn quy trình cốt lõi: [[phát triển sản phẩm mới]], [[quản lý nhà cung cấp]], [[thực hiện đơn hàng]], và [[quản lý quan hệ khách hàng]].

Trong bối cảnh sau đại dịch COVID-19 và các [[gián đoạn chuỗi cung ứng]] toàn cầu, kiến thức về tích hợp và quản lý rủi ro chuỗi cung ứng trở nên quan trọng hơn bao giờ hết.

---

## 1. Gián đoạn chuỗi cung ứng (Supply Chain Disruptions)

### Định nghĩa (Definition)
[[Gián đoạn chuỗi cung ứng]] (Supply Chain Disruption) là sự kiện bất ngờ làm gián đoạn dòng chảy bình thường của hàng hóa, thông tin, hoặc tài chính trong [[chuỗi cung ứng]], gây ra tác động tiêu cực đến hiệu suất kinh doanh.

### 1.1 Nguyên nhân gián đoạn (Causes)

| Loại nguyên nhân | Ví dụ cụ thể |
|-----------------|-------------|
| **[[Thiên tai]]** (Natural Disasters) | Động đất Nhật Bản 2011 → gián đoạn chuỗi cung ứng ô tô toàn cầu; Lũ lụt miền Trung VN |
| **[[Đại dịch]]** (Pandemic) | COVID-19 → đóng cửa nhà máy, tắc nghẽn cảng, thiếu container |
| **[[Sự cố công nghệ]]** | Tấn công mạng (cyberattack) vào Colonial Pipeline 2021 → thiếu xăng tại Mỹ |
| **[[Bất ổn chính trị]]** | Chiến tranh thương mại Mỹ-Trung → thuế quan tăng, doanh nghiệp phải chuyển đổi nhà cung cấp |
| **[[Sự cố vận tải]]** | Tàu Ever Given mắc kẹt tại kênh Suez 2021 → tắc nghẽn thương mại toàn cầu |
| **[[Phá sản nhà cung cấp]]** | Nhà cung cấp linh kiện phá sản → dây chuyền sản xuất phải dừng |
| **[[Sai sót chất lượng]]** | Thu hồi sản phẩm hàng loạt → gián đoạn sản xuất và phân phối |

### 1.2 Động lực gián đoạn (Dynamics)

**Hiệu ứng domino**: Gián đoạn tại một điểm có thể lan truyền ra toàn bộ chuỗi cung ứng:

```
Nhà cung cấp cấp 2 bị ảnh hưởng
        ↓
Nhà cung cấp cấp 1 thiếu nguyên liệu
        ↓
Nhà sản xuất không thể sản xuất
        ↓
Nhà phân phối hết hàng
        ↓
Khách hàng không mua được sản phẩm
```

**Thời gian phục hồi** (Recovery Time): Phụ thuộc vào:
- [[Khả năng phục hồi]] (Resilience) của chuỗi cung ứng
- Có [[nhà cung cấp dự phòng]] (backup suppliers) hay không
- [[Tồn kho an toàn]] (Safety Stock) có đủ để "cầm cự" trong thời gian gián đoạn không
- [[Tính linh hoạt]] (Flexibility) trong chuyển đổi nguồn cung

### Ví dụ thực tế
- **COVID-19 và ngành ô tô**: Đại dịch → nhà máy chip đóng cửa → thiếu [[chip bán dẫn]] → Toyota, Ford, VinFast đều phải giảm sản lượng trong 2021-2022.
- **Kênh Suez 2021**: Tàu Ever Given mắc kẹt 6 ngày → ~$9.6 tỷ hàng hóa/ngày bị tắc nghẽn → ảnh hưởng chuỗi cung ứng toàn cầu trong nhiều tuần sau đó.

### Liên kết
- [[Hiệu ứng Bullwhip]] — Gián đoạn làm tăng hiệu ứng Bullwhip
- [[Quản lý rủi ro chuỗi cung ứng]] — Cách ứng phó
- [[CH15 - Supply Chain Sustainability]] — Chuỗi cung ứng cứu trợ thiên tai

---

## 2. [[Chuỗi cung ứng tích hợp]] (Integrated Supply Chains)

> ![Figure 14.3 - Chuỗi cung ứng tích hợp](/images/figures/ch14_fig14.3.jpg)
> *Figure 14.3: Tích hợp nội bộ + bên ngoài để đồng bộ thông tin & vật liệu*

### Định nghĩa (Definition)
[[Chuỗi cung ứng tích hợp]] là chuỗi cung ứng trong đó tất cả các thành viên chia sẻ thông tin, phối hợp quyết định, và cùng hướng đến mục tiêu chung — tối đa hóa giá trị cho [[khách hàng cuối cùng]] (end customer).

### Giải thích chi tiết

**Các mức độ tích hợp**:

1. **Không tích hợp** (Silos): Mỗi bộ phận/công ty hoạt động độc lập, không chia sẻ thông tin → Hiệu ứng Bullwhip mạnh, tồn kho cao, phản ứng chậm.

2. **[[Tích hợp nội bộ]]** (Internal Integration): Các bộ phận trong cùng một công ty (mua hàng, sản xuất, logistics, bán hàng) phối hợp chặt chẽ.
   - Dùng hệ thống [[ERP]] (Enterprise Resource Planning) như SAP, Oracle
   - Dùng quy trình [[S&OP]] ([[Sales and Operations Planning]])

3. **[[Tích hợp bên ngoài]]** (External Integration): Phối hợp với [[nhà cung cấp]] và [[khách hàng]] bên ngoài.
   - Chia sẻ [[dữ liệu bán hàng]] (POS data) với nhà cung cấp
   - [[CPFR]] ([[Collaborative Planning, Forecasting, and Replenishment]]): Cùng lập kế hoạch, dự báo, và bổ sung hàng
   - [[VMI]] ([[Vendor Managed Inventory]]): Nhà cung cấp tự quản lý tồn kho cho khách hàng

**Lợi ích của tích hợp**:
- Giảm [[Hiệu ứng Bullwhip]]
- Giảm tổng [[tồn kho]] trong toàn chuỗi
- Tăng [[mức phục vụ khách hàng]] (service level)
- Phản ứng nhanh hơn với thay đổi nhu cầu
- Giảm [[chi phí vận hành]] tổng thể

### Ví dụ thực tế
- **Walmart + P&G**: Một trong những ví dụ kinh điển về tích hợp chuỗi cung ứng. Walmart chia sẻ dữ liệu bán hàng thời gian thực với P&G, P&G tự quản lý tồn kho sản phẩm của mình tại kho Walmart ([[VMI]]).
- **Toyota và nhà cung cấp**: Toyota chia sẻ kế hoạch sản xuất với nhà cung cấp cấp 1 và cấp 2, hỗ trợ kỹ thuật để nâng cao năng lực → quan hệ [[đối tác chiến lược]] (Strategic Partnership).

### Liên kết
- [[ERP]] — Hệ thống hoạch định nguồn lực doanh nghiệp
- [[S&OP]] — Hoạch định bán hàng và vận hành
- [[CPFR]] — Phối hợp lập kế hoạch

---

## 3. [[Hiệu ứng Bullwhip]] (Bullwhip Effect / Hiệu ứng roi da)

> ![Figure 14.2 - Hiệu ứng roi da](/images/figures/ch14_fig14.2.jpg)
> *Figure 14.2: Bullwhip Effect - biến động nhu cầu khuếch đại khi đi ngược chuỗi cung ứng*

### Định nghĩa (Definition)
[[Hiệu ứng Bullwhip]] (tiếng Việt: **hiệu ứng roi da** hay **hiệu ứng cái roi**) là hiện tượng mà **sự biến động của đơn đặt hàng ngày càng tăng** khi di chuyển ngược lên chuỗi cung ứng, từ [[khách hàng]] → [[nhà bán lẻ]] → [[nhà phân phối]] → [[nhà sản xuất]] → [[nhà cung cấp nguyên liệu]].

### Giải thích chi tiết

**Hình dung**: Giống như khi bạn vẫy một chiếc roi — tay bạn chỉ di chuyển nhẹ, nhưng đầu roi quật mạnh hơn rất nhiều.

```
Nhu cầu khách hàng:      ~~~~ (biến động nhẹ)
Đơn hàng nhà bán lẻ:     ~~~~~ (biến động hơn)
Đơn hàng nhà phân phối:  ~~~~~~~~ (biến động nhiều)
Đơn hàng nhà sản xuất:   ~~~~~~~~~~~~ (biến động rất nhiều)
Đơn hàng NCC nguyên liệu: ~~~~~~~~~~~~~~~~ (biến động cực lớn)
```

**Nguyên nhân chính**:

1. **[[Dự báo nhu cầu]]** (Demand Forecast Updating): Mỗi mắt xích tự dự báo dựa trên đơn hàng nhận được (không phải nhu cầu thực), thêm [[tồn kho an toàn]] → khuếch đại biến động.
   - *Ví dụ*: Khách mua 100 SP → Cửa hàng đặt 120 (thêm 20 phòng ngừa) → Phân phối đặt 150 → Nhà máy sản xuất 200.

2. **[[Đặt hàng theo lô]]** (Order Batching): Thay vì đặt hàng liên tục, mỗi mắt xích gom đơn hàng theo lô (batch) để tiết kiệm chi phí vận chuyển và đặt hàng → tạo ra mô hình nhu cầu "nhảy cóc".
   - *Ví dụ*: Thay vì đặt 10 SP mỗi ngày, đặt 70 SP mỗi tuần một lần.

3. **[[Biến động giá]]** (Price Fluctuations): Khi có khuyến mãi, khách hàng mua tích trữ (forward buying), tạo ra nhu cầu ảo lớn. Sau khuyến mãi, nhu cầu giảm mạnh.
   - *Ví dụ*: Khuyến mãi dầu ăn giảm 30% → người tiêu dùng mua gấp 3-4 lần bình thường → tuần sau gần như không mua.

4. **[[Thiếu hụt và phân phối theo tỷ lệ]]** (Shortage Gaming): Khi sản phẩm thiếu hụt, khách hàng đặt hàng nhiều hơn cần (để đảm bảo nhận đủ khi bị cắt giảm) → tạo nhu cầu ảo.
   - *Ví dụ*: Chip bán dẫn thiếu → Các hãng ô tô đặt hàng gấp đôi nhu cầu thực → Nhà sản xuất chip tưởng nhu cầu tăng vọt.

**Hậu quả**:
- [[Tồn kho]] quá mức hoặc thiếu hụt
- [[Công suất]] sản xuất không ổn định
- Chi phí vận chuyển tăng (giao hàng khẩn cấp)
- [[Mức phục vụ khách hàng]] giảm
- Lãng phí tài nguyên

**Giải pháp giảm Bullwhip Effect**:
- **Chia sẻ thông tin nhu cầu thực** (Share POS data): Cho tất cả mắt xích thấy nhu cầu thực của khách hàng cuối
- **[[CPFR]]**: Cùng lập kế hoạch và dự báo
- **[[VMI]]**: Nhà cung cấp theo dõi tồn kho và tự bổ sung
- **[[EDLP]]** ([[Every Day Low Pricing]]): Giá ổn định hàng ngày thay vì khuyến mãi lớn → giảm forward buying
- **Giảm kích thước lô hàng**: Đặt hàng thường xuyên hơn với số lượng nhỏ hơn
- **Phân phối dựa trên nhu cầu thực**: Không phân phối theo tỷ lệ đặt hàng khi thiếu hụt

### Ví dụ thực tế
- **Procter & Gamble (P&G)**: P&G phát hiện hiệu ứng Bullwhip khi nghiên cứu tã giấy Pampers — nhu cầu của em bé rất ổn định, nhưng đơn hàng từ nhà phân phối biến động cực lớn. Giải pháp: chia sẻ dữ liệu POS với Walmart.
- **COVID-19 và giấy vệ sinh**: Người tiêu dùng hoảng loạn mua gấp → kệ hàng trống → nhà bán lẻ đặt hàng gấp 10 lần → nhà sản xuất tăng ca → sau đó nhu cầu sụt giảm mạnh. Ví dụ kinh điển về shortage gaming.

### Liên kết
- [[Chuỗi cung ứng tích hợp]] — Giải pháp tích hợp giảm Bullwhip
- [[VMI]] — Quản lý tồn kho bởi nhà cung cấp
- [[CPFR]] — Phối hợp lập kế hoạch
- [[CH09 - Forecasting]] — Dự báo nhu cầu

---

## 4. [[Quản lý rủi ro chuỗi cung ứng]] (Supply Chain Risk Management)

### Định nghĩa (Definition)
[[Quản lý rủi ro chuỗi cung ứng]] (SCRM - Supply Chain Risk Management) là quá trình nhận diện, đánh giá, và giảm thiểu các rủi ro có thể gây gián đoạn hoặc tác động tiêu cực đến chuỗi cung ứng.

### 4.1 [[Rủi ro vận hành]] (Operational Risks)

Rủi ro liên quan đến hoạt động hàng ngày của chuỗi cung ứng:

- **[[Rủi ro chất lượng]]**: Sản phẩm lỗi, nguyên liệu không đạt tiêu chuẩn
  - *Ví dụ*: Sữa nhiễm melamine tại Trung Quốc 2008 → gián đoạn toàn bộ ngành sữa
- **[[Rủi ro giao hàng]]**: Nhà cung cấp giao trễ, thiếu số lượng
  - *Ví dụ*: Tắc nghẽn cảng Cát Lái 2021 → hàng container chờ cả tuần
- **[[Rủi ro năng lực]]**: Nhà cung cấp không đủ công suất đáp ứng nhu cầu tăng đột biến
- **[[Rủi ro tồn kho]]**: Hàng hết hạn, hao hụt, hoặc lỗi thời (obsolescence)
- **[[Rủi ro công nghệ]]**: Hệ thống IT gặp sự cố, mất dữ liệu

### 4.2 [[Rủi ro tài chính]] (Financial Risks)

- **[[Rủi ro tỷ giá]]**: Biến động tỷ giá ảnh hưởng đến chi phí nhập khẩu
  - *Ví dụ*: VND mất giá so với USD → chi phí nhập khẩu linh kiện điện tử tăng
- **[[Rủi ro giá nguyên liệu]]**: Giá dầu, thép, chip biến động
- **[[Rủi ro thanh toán]]**: Khách hàng/nhà phân phối chậm trả tiền hoặc phá sản
- **[[Rủi ro chi phí vận chuyển]]**: Giá cước container tăng vọt (như năm 2021-2022)

### 4.3 [[Rủi ro an ninh]] (Security Risks)

- **[[Trộm cắp hàng hóa]]**: Mất mát trong quá trình vận chuyển hoặc lưu kho
- **[[Tấn công mạng]]** (Cyberattack): Ransomware, đánh cắp dữ liệu khách hàng
  - *Ví dụ*: Tấn công SolarWinds 2020 ảnh hưởng hàng ngàn doanh nghiệp
- **[[Hàng giả]]** (Counterfeiting): Sản phẩm giả mạo xâm nhập chuỗi cung ứng
- **[[Tuân thủ pháp luật]]**: Vi phạm quy định xuất nhập khẩu, hải quan
- **[[Khủng bố]]**: Tấn công vào cơ sở hạ tầng quan trọng (cảng, sân bay)

### Chiến lược giảm thiểu rủi ro

| Chiến lược | Mô tả |
|-----------|-------|
| **[[Đa dạng hóa nhà cung cấp]]** (Multi-sourcing) | Không phụ thuộc vào một nhà cung cấp duy nhất |
| **[[Tồn kho an toàn]]** (Safety Stock) | Giữ hàng dự phòng để đối phó gián đoạn |
| **[[Nearshoring]]** | Chuyển sản xuất gần hơn để giảm rủi ro vận chuyển |
| **[[Bảo hiểm chuỗi cung ứng]]** | Mua bảo hiểm cho rủi ro thiên tai, gián đoạn |
| **[[Kế hoạch dự phòng]]** (Contingency Plan) | Lập kế hoạch ứng phó cho các tình huống xấu |
| **[[Audit nhà cung cấp]]** | Kiểm tra định kỳ năng lực, tài chính, chất lượng của NCC |

### Liên kết
- [[Gián đoạn chuỗi cung ứng]] — Nguyên nhân và hậu quả
- [[CH15 - Supply Chain Sustainability]] — Rủi ro liên quan đến bền vững
- [[Quản lý rủi ro]] (Risk Management)

---

## 5. [[Điện toán đám mây]] và [[Blockchain]] trong chuỗi cung ứng

### 5.1 [[Điện toán đám mây]] (Cloud Computing)

**Định nghĩa**: Sử dụng hạ tầng CNTT (máy chủ, lưu trữ, phần mềm) qua internet, thay vì tự đầu tư và vận hành.

**Ứng dụng trong chuỗi cung ứng**:
- **[[SaaS]] (Software as a Service)**: Phần mềm quản lý chuỗi cung ứng trên cloud (SAP S/4HANA Cloud, Oracle SCM Cloud)
  - Lợi ích: Không cần đầu tư hạ tầng, cập nhật tự động, truy cập mọi nơi
- **Chia sẻ dữ liệu thời gian thực**: Tất cả đối tác chuỗi cung ứng truy cập cùng một nền tảng → giảm [[Hiệu ứng Bullwhip]]
- **[[AI/ML trên cloud]]**: Dự báo nhu cầu, tối ưu hóa tuyến đường bằng AI mà không cần đầu tư phần cứng đắt đỏ
- **Khả năng mở rộng** (Scalability): Tăng/giảm tài nguyên IT linh hoạt theo mùa kinh doanh

### 5.2 [[Blockchain]]

> ![Figure 14.6 - Blockchain trong chuỗi cung ứng](/images/figures/ch14_fig14.6.jpg)
> *Figure 14.6: Blockchain tăng tính minh bạch và truy xuất nguồn gốc*

**Định nghĩa**: Công nghệ sổ cái phân tán (distributed ledger) lưu trữ giao dịch theo các khối (blocks) được liên kết bằng mật mã, không thể sửa đổi hoặc xóa.

**Ứng dụng trong chuỗi cung ứng**:

1. **[[Truy xuất nguồn gốc]]** (Traceability): Theo dõi sản phẩm từ nguyên liệu đến tay người tiêu dùng
   - *Ví dụ*: Walmart dùng blockchain của IBM (Food Trust) để truy xuất nguồn gốc rau xanh — từ trang trại → nhà đóng gói → kho → cửa hàng. Thời gian truy xuất giảm từ 7 ngày xuống 2.2 giây.

2. **[[Hợp đồng thông minh]]** (Smart Contracts): Tự động thực hiện thanh toán khi điều kiện giao hàng được đáp ứng
   - *Ví dụ*: Khi cảm biến IoT xác nhận hàng đến kho đúng số lượng và chất lượng → tự động chuyển tiền cho nhà cung cấp

3. **Chống [[hàng giả]]**: Mỗi sản phẩm có mã định danh duy nhất trên blockchain
   - *Ví dụ*: Thuốc, thực phẩm chức năng sử dụng blockchain để xác minh nguồn gốc

4. **[[Tài chính chuỗi cung ứng]]** (Supply Chain Finance): Xác nhận giao dịch nhanh hơn, giảm rủi ro gian lận

### Ví dụ thực tế
- **Maersk + IBM (TradeLens)**: Nền tảng blockchain cho vận tải container — tất cả bên liên quan (hãng tàu, cảng, hải quan, shipper) xem cùng dữ liệu → giảm giấy tờ, tăng tốc thông quan.
- **De Beers**: Dùng blockchain để theo dõi kim cương từ mỏ → nhà máy cắt → cửa hàng, đảm bảo không phải "kim cương máu" (conflict diamonds).
- **VeChain tại Việt Nam**: Một số doanh nghiệp cà phê Việt Nam sử dụng blockchain VeChain để truy xuất nguồn gốc, tăng giá trị xuất khẩu.

### Liên kết
- [[CH12 - Supply Chain Design]] — Chuỗi cung ứng tự trị
- [[IoT]] — Internet vạn vật
- [[Digital Transformation]] — Chuyển đổi số

---

## 6. Quy trình phát triển sản phẩm/dịch vụ mới (New Service or Product Development Process)

### Định nghĩa (Definition)
Quy trình [[phát triển sản phẩm mới]] (New Product Development - [[NPD]]) là chuỗi các bước biến ý tưởng thành sản phẩm/dịch vụ hoàn chỉnh sẵn sàng ra thị trường. Đây là một quy trình cốt lõi của chuỗi cung ứng vì sản phẩm mới ảnh hưởng đến toàn bộ chuỗi (nguyên liệu mới, quy trình mới, nhà cung cấp mới).

### Các giai đoạn

#### Giai đoạn 1: [[Thiết kế]] (Design)
- Tạo ra khái niệm sản phẩm (concept)
- Nghiên cứu nhu cầu thị trường
- Thiết kế sơ bộ (preliminary design)
- Xem xét [[khả năng sản xuất]] (manufacturability) — liên kết với [[Design for Manufacturing]] ([[DFM]])
- **Quan trọng**: Phải cân nhắc chuỗi cung ứng ngay từ giai đoạn này — nguyên liệu có sẵn không? Nhà cung cấp nào có thể cung cấp?

#### Giai đoạn 2: [[Phân tích]] (Analysis)
- Phân tích tài chính: [[ROI]], [[NPV]], [[điểm hòa vốn]]
- Phân tích thị trường: Quy mô thị trường, đối thủ, giá cả
- Phân tích rủi ro: Rủi ro công nghệ, thị trường, chuỗi cung ứng
- Ra quyết định: Tiếp tục hay dừng dự án ([[Stage-Gate Process]])

#### Giai đoạn 3: [[Phát triển]] (Development)
- Thiết kế chi tiết sản phẩm
- Tạo [[prototype]] (sản phẩm mẫu)
- Thử nghiệm và kiểm tra chất lượng
- Phát triển quy trình sản xuất
- Chọn và phát triển nhà cung cấp cho linh kiện/nguyên liệu mới

#### Giai đoạn 4: [[Ra mắt toàn diện]] (Full Launch)
- Sản xuất hàng loạt
- Phân phối ra thị trường
- Chiến dịch marketing
- Thu thập phản hồi khách hàng và liên tục cải tiến
- Đánh giá hiệu suất chuỗi cung ứng cho sản phẩm mới

### Ví dụ thực tế
- **Apple iPhone**: Mỗi iPhone mới cần thiết kế chuỗi cung ứng từ sớm — đặt hàng chip từ TSMC 2 năm trước, tìm nguồn kính Gorilla Glass từ Corning, lắp ráp tại Foxconn. [[Thiết kế đồng thời]] (Concurrent Engineering) giúp rút ngắn thời gian ra mắt.
- **VinFast VF8/VF9**: Phát triển xe điện đòi hỏi chuỗi cung ứng hoàn toàn mới — pin từ Gotion, chip từ nhiều nhà cung cấp, động cơ điện từ đối tác. Mỗi lựa chọn nhà cung cấp ảnh hưởng đến thiết kế và chi phí sản phẩm.

### Liên kết
- [[CH03 - Process Strategy]] — Chiến lược quy trình
- [[Design for Manufacturing]] (DFM)
- [[Stage-Gate Process]]
- [[Concurrent Engineering]]

---

## 7. Quy trình quản lý nhà cung cấp (Supplier Relationship Process)

### Định nghĩa (Definition)
[[Quy trình quản lý nhà cung cấp]] (Supplier Relationship Process / [[SRM]] - Supplier Relationship Management) là chuỗi hoạt động nhằm lựa chọn, phát triển, và duy trì mối quan hệ với nhà cung cấp để tối ưu hóa giá trị cho chuỗi cung ứng.

### Các hoạt động chính

#### 7.1 [[Tìm nguồn cung]] (Sourcing)
- Xác định nhu cầu mua hàng
- Tìm kiếm và đánh giá nhà cung cấp tiềm năng
- Phương pháp đánh giá: [[Scorecard nhà cung cấp]] — chấm điểm theo chất lượng, giá cả, giao hàng, dịch vụ
- Quyết định [[single sourcing]] (một nhà cung cấp) vs [[multiple sourcing]] (nhiều nhà cung cấp)
  - *Single sourcing*: Quan hệ sâu hơn, giá tốt hơn, nhưng rủi ro cao nếu NCC gặp sự cố
  - *Multiple sourcing*: An toàn hơn, cạnh tranh giá tốt, nhưng quản lý phức tạp hơn

#### 7.2 [[Hợp tác thiết kế]] (Design Collaboration)
- Mời nhà cung cấp tham gia từ giai đoạn [[thiết kế sản phẩm]] ([[Early Supplier Involvement]] - ESI)
- Nhà cung cấp đóng góp chuyên môn về vật liệu, công nghệ, khả năng sản xuất
- Giúp giảm chi phí, rút ngắn thời gian phát triển, tăng chất lượng

- *Ví dụ*: Toyota mời nhà cung cấp tham gia thiết kế linh kiện ngay từ đầu — nhà cung cấp đề xuất vật liệu và quy trình tối ưu.

#### 7.3 [[Đàm phán]] (Negotiation)
- Đàm phán giá, điều khoản thanh toán, [[lead time]], chất lượng
- Các phương pháp đàm phán:
  - **Đấu thầu cạnh tranh** (Competitive Bidding): Nhiều NCC cùng báo giá
  - **Đàm phán trực tiếp** (Direct Negotiation): Thương lượng 1-1, thường cho quan hệ dài hạn
  - **[[Đấu giá ngược]]** (Reverse Auction): NCC cạnh tranh giảm giá trực tuyến
- [[Hợp đồng dài hạn]] vs [[Hợp đồng ngắn hạn]]

#### 7.4 [[Quản lý tồn kho bởi nhà cung cấp]] (VMI - Vendor Managed Inventory)
**Định nghĩa**: Nhà cung cấp chịu trách nhiệm theo dõi mức tồn kho tại kho/cửa hàng của khách hàng và tự quyết định khi nào, bao nhiêu hàng cần bổ sung.

**Cách hoạt động**:
1. Khách hàng chia sẻ dữ liệu tồn kho và bán hàng thời gian thực
2. Nhà cung cấp theo dõi và phân tích dữ liệu
3. Nhà cung cấp tự ra quyết định bổ sung hàng
4. Hàng được giao và lập hóa đơn

**Lợi ích**:
- Giảm [[Hiệu ứng Bullwhip]] (NCC thấy nhu cầu thực, không phải đơn hàng)
- Giảm tồn kho cho cả hai bên
- Tăng [[mức phục vụ]] (ít hết hàng hơn)
- Giảm chi phí đặt hàng cho khách hàng

**Ví dụ**: Coca-Cola quản lý tồn kho sản phẩm của mình tại các siêu thị lớn — nhân viên Coca-Cola tự kiểm tra kệ hàng và bổ sung khi cần.

### Liên kết
- [[CH12 - Supply Chain Design]] — Outsourcing và Make-or-Buy
- [[Hiệu ứng Bullwhip]] — VMI giảm Bullwhip
- [[Quản lý chất lượng]] (Quality Management)

---

## 8. Quy trình thực hiện đơn hàng (Order Fulfillment Process)

### Định nghĩa (Definition)
[[Quy trình thực hiện đơn hàng]] (Order Fulfillment Process) bao gồm tất cả hoạt động từ khi nhận đơn hàng từ khách hàng đến khi giao hàng thành công. Đây là "xương sống" của chuỗi cung ứng.

### Các bước chính

#### 8.1 [[Hoạch định nhu cầu khách hàng]] (Customer Demand Planning)
- Thu thập và phân tích dữ liệu nhu cầu khách hàng
- Dự báo nhu cầu ngắn hạn và dài hạn
- Xác định mô hình nhu cầu (trend, [[seasonality]], cyclical)
- Chia sẻ thông tin nhu cầu với các bộ phận liên quan

#### 8.2 [[Hoạch định cung ứng]] (Supply Planning)
- Lập kế hoạch sản xuất dựa trên dự báo nhu cầu
- Xác định nhu cầu [[nguyên vật liệu]] ([[MRP]] — Material Requirements Planning)
- Phối hợp với nhà cung cấp để đảm bảo nguyên liệu đầu vào
- Cân bằng giữa [[năng lực sản xuất]] và nhu cầu

#### 8.3 [[Sản xuất]] (Production)
- Thực hiện kế hoạch sản xuất
- Kiểm soát chất lượng trong quá trình sản xuất
- Quản lý [[Work-in-Process]] (WIP) inventory
- Đảm bảo hoàn thành đúng thời hạn

#### 8.4 [[Logistics]] (Logistics)
- **Đóng gói** (Packaging): Bảo vệ sản phẩm, tuân thủ quy định
- **Lưu kho** (Warehousing): Lưu trữ thành phẩm trong kho
- **Vận chuyển** (Transportation): Chọn phương thức vận chuyển (đường bộ, biển, hàng không, đường sắt)
- **Giao hàng chặng cuối** ([[Last-Mile Delivery]]): Giao hàng đến tay khách hàng — thường là phần tốn kém nhất
- **Xác nhận giao hàng** và xử lý [[trả hàng]] (returns)

### Ví dụ thực tế
- **Amazon Prime**: Đặt hàng → Hệ thống AI xác định kho gần nhất có hàng → Robot lấy hàng → Đóng gói → Xe tải/drone giao hàng → Giao trong 1-2 ngày (hoặc trong ngày).
- **Shopee Express**: Người bán gửi hàng vào hub → Phân loại tự động → Vận chuyển liên tỉnh → Hub địa phương → Shipper giao tận nhà.

### Liên kết
- [[CH09 - Forecasting]] — Dự báo nhu cầu
- [[MRP]] — Hoạch định nhu cầu vật liệu
- [[CH13 - Supply Chain Logistics Networks]] — Mạng lưới logistics
- [[Last-Mile Delivery]] — Giao hàng chặng cuối

---

## 9. Quy trình quản lý quan hệ khách hàng (Customer Relationship Process)

### Định nghĩa (Definition)
[[Quy trình quản lý quan hệ khách hàng]] (Customer Relationship Process / [[CRM]] — Customer Relationship Management) bao gồm các hoạt động nhằm thu hút, phục vụ, và duy trì mối quan hệ với khách hàng trong suốt vòng đời.

### Các hoạt động chính

#### 9.1 [[Marketing]]
- Phân tích và phân khúc thị trường
- Xác định [[khách hàng mục tiêu]] (target customers)
- Phát triển chiến lược giá, sản phẩm, phân phối, truyền thông ([[Marketing Mix]] — [[4P]])
- Sử dụng [[dữ liệu lớn]] (big data) để cá nhân hóa marketing
- **Liên kết với chuỗi cung ứng**: Chiến lược marketing (ví dụ: khuyến mãi lớn) ảnh hưởng trực tiếp đến nhu cầu → cần phối hợp với [[hoạch định cung ứng]]

#### 9.2 [[Đặt hàng]] (Order Placement)
- Tiếp nhận đơn hàng qua nhiều kênh: trực tiếp, điện thoại, website, app, marketplace
- Xác nhận đơn hàng: kiểm tra tồn kho, xác nhận thời gian giao, xác nhận giá
- Xử lý thanh toán
- **[[Omnichannel]]**: Khách hàng đặt hàng qua bất kỳ kênh nào cũng có trải nghiệm nhất quán
- Hệ thống [[Order Management System]] (OMS) tự động hóa quy trình

#### 9.3 [[Dịch vụ khách hàng]] (Customer Service)
- **Trước bán hàng**: Tư vấn sản phẩm, giải đáp thắc mắc
- **Trong bán hàng**: Theo dõi đơn hàng (order tracking), thông báo tình trạng giao hàng
- **Sau bán hàng**: Xử lý khiếu nại, đổi trả hàng, bảo hành, thu thập phản hồi
- **[[Service Level Agreement]] (SLA)**: Cam kết chất lượng dịch vụ (ví dụ: giao hàng trong 24h, phản hồi khiếu nại trong 2h)
- Sử dụng [[chatbot]] AI để hỗ trợ khách hàng 24/7

### Ví dụ thực tế
- **The Gioi Di Dong**: Hệ thống CRM tích hợp — nhân viên cửa hàng thấy lịch sử mua hàng, sở thích, điểm tích lũy của khách → tư vấn cá nhân hóa. Dịch vụ hậu mãi (bảo hành, sửa chữa) được quản lý xuyên suốt.
- **Tiki**: Hệ thống đặt hàng đa kênh (app, web, Zalo), theo dõi đơn hàng thời gian thực, chatbot hỗ trợ 24/7, dịch vụ TikiNOW giao trong 2h.

### Liên kết
- [[CRM]] — Hệ thống quản lý quan hệ khách hàng
- [[Omnichannel]] — Chiến lược đa kênh
- [[CH12 - Supply Chain Design]] — Thiết kế chuỗi cung ứng theo nhu cầu khách hàng
- [[Hiệu ứng Bullwhip]] — Marketing (khuyến mãi) có thể gây Bullwhip

---

## Công thức quan trọng (Key Formulas)

Chương này ít công thức toán học, tập trung vào khung khái niệm và quy trình. Tuy nhiên, cần nhớ:

| Khái niệm | Công thức/Mô hình |
|-----------|-------------------|
| [[Hiệu ứng Bullwhip]] | $\frac{\text{Variance of Orders}}{\text{Variance of Demand}} > 1$ (Tỷ lệ biến động đơn hàng / biến động nhu cầu > 1 nghĩa là có Bullwhip) |
| [[VMI]] hiệu quả khi | Tồn kho giảm + Mức phục vụ tăng + Chi phí đặt hàng giảm |

---

## Từ khóa chính (Key Terms)

- [[Gián đoạn chuỗi cung ứng]] (Supply Chain Disruption)
- [[Chuỗi cung ứng tích hợp]] (Integrated Supply Chain)
- [[Hiệu ứng Bullwhip]] (Bullwhip Effect / Hiệu ứng roi da)
- [[Quản lý rủi ro chuỗi cung ứng]] (SCRM)
- [[Rủi ro vận hành]] (Operational Risk)
- [[Rủi ro tài chính]] (Financial Risk)
- [[Rủi ro an ninh]] (Security Risk)
- [[Điện toán đám mây]] (Cloud Computing)
- [[Blockchain]]
- [[Hợp đồng thông minh]] (Smart Contracts)
- [[Phát triển sản phẩm mới]] (NPD)
- [[VMI]] (Vendor Managed Inventory)
- [[CPFR]] (Collaborative Planning, Forecasting, and Replenishment)
- [[ERP]] (Enterprise Resource Planning)
- [[S&OP]] (Sales and Operations Planning)
- [[CRM]] (Customer Relationship Management)
- [[Omnichannel]]
- [[Last-Mile Delivery]]
- [[MRP]] (Material Requirements Planning)
- [[Tìm nguồn cung]] (Sourcing)
- [[Hợp tác thiết kế]] (Design Collaboration)

---

> **Xem thêm**: [[CH12 - Supply Chain Design]] | [[CH13 - Supply Chain Logistics Networks]] | [[CH15 - Supply Chain Sustainability]]
