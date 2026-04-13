---
tags: [key-concept, chapter-1, technology]
aliases: [Internet of Things, IoT, Kết nối vạn vật, Mạng lưới vạn vật kết nối, IIoT]
---
# Internet of Things (IoT)

## Định nghĩa (Definition)
**Internet of Things (IoT)** (Kết nối vạn vật) là mạng lưới các thiết bị vật lý được gắn **cảm biến, phần mềm, và kết nối mạng**, cho phép chúng **thu thập và trao đổi dữ liệu** với nhau và với hệ thống trung tâm mà không cần con người can thiệp.

## Giải thích chi tiết (Detailed Explanation)

### Cách hoạt động:
```
Cảm biến → Thu thập dữ liệu → Truyền qua mạng → Phân tích (AI/Cloud) → Hành động
(Sensor)    (nhiệt độ, vị trí,   (WiFi, 5G,      ([[Cloud Computing]])    (tự động
            rung động, áp suất)   Bluetooth)                            điều chỉnh)
```

### IIoT (Industrial IoT) — IoT trong sản xuất:
IoT ứng dụng đặc biệt cho nhà máy và [[Supply Chain|chuỗi cung ứng]], là trụ cột của [[Industry 4.0]].

### Ứng dụng trong Operations Management:

#### 1. Smart Manufacturing (Sản xuất thông minh)
- Cảm biến trên máy → giám sát hiệu suất thời gian thực
- **Predictive Maintenance:** Phát hiện máy sắp hỏng trước khi hỏng → bảo trì chủ động
- Tự động điều chỉnh thông số sản xuất → giảm [[Bottleneck]]

#### 2. Supply Chain Visibility (Minh bạch chuỗi cung ứng)
- GPS + cảm biến trên container → biết hàng đang ở đâu, tình trạng thế nào
- Cảm biến nhiệt độ → đảm bảo chuỗi lạnh cho thực phẩm, vaccine
- Giảm [[Bullwhip Effect]] nhờ dữ liệu thực tế

#### 3. Inventory Management (Quản lý tồn kho)
- RFID/cảm biến trên kệ → biết chính xác [[Inventory|tồn kho]] tại mọi thời điểm
- Tự động kích hoạt [[Reorder Point]] khi tồn kho thấp

#### 4. Quality Control (Kiểm soát chất lượng)
- Cảm biến đo lường liên tục → [[Statistical Process Control (SPC)]] tự động
- Camera AI kiểm tra bề mặt sản phẩm

#### 5. Energy Management
- Giám sát năng lượng từng máy → tối ưu chi phí → [[Sustainability]]

## Ví dụ thực tế (Real-world Example)
**Amazon Fulfillment Centers:**
- Hàng triệu cảm biến theo dõi vị trí mọi sản phẩm
- Robot Kiva tự di chuyển kệ hàng đến nhân viên đóng gói
- Dự báo nhu cầu + IoT → hàng được đặt sẵn tại kho gần bạn TRƯỚC khi bạn đặt hàng!

**Maersk — Vận chuyển container:**
- Mỗi container gắn cảm biến: vị trí GPS, nhiệt độ, độ ẩm, có bị mở không
- Khách hàng theo dõi hàng real-time
- Phát hiện ngay nếu container hàng lạnh bị tăng nhiệt → can thiệp kịp thời

**Ứng dụng tại Việt Nam:**
- Viettel IoT giám sát nông nghiệp: cảm biến độ ẩm đất → tưới tiêu tự động
- Vinamilk: IoT giám sát đàn bò sữa — sức khỏe, sản lượng, chu kỳ sinh sản

## Mối liên hệ (Relationships)
- Thuộc về: [[Industry 4.0]]
- Kết hợp với: [[Cloud Computing]] (xử lý dữ liệu), [[Blockchain]] (bảo mật)
- Ứng dụng trong: [[Supply Chain]], [[Inventory]], [[Statistical Process Control (SPC)]]
- Hỗ trợ: [[Lean Systems]], [[Sustainability]], [[Forecasting]]
- Thuộc chương: Chapter 1 — Using Operations to Create Value

## Công thức (Formula)
Không có công thức OM cụ thể. IoT là nền tảng công nghệ thu thập dữ liệu cho các công cụ phân tích OM khác.
