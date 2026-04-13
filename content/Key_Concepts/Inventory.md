---
tags: [key-concept, chapter-12, inventory]
aliases: [Inventory, Tồn kho, Hàng tồn kho, Stock]
---
# Inventory

## Định nghĩa (Definition)
**Inventory** (Tồn kho) là bất kỳ tài sản nào được doanh nghiệp **giữ lại để sử dụng hoặc bán trong tương lai**, bao gồm nguyên vật liệu, bán thành phẩm, và thành phẩm.

## Giải thích chi tiết (Detailed Explanation)

### 4 loại tồn kho theo mục đích:

#### 1. Cycle Inventory (Tồn kho chu kỳ)
- Tồn kho do **đặt hàng theo lô** (batch) thay vì từng cái
- Kích thước lô lớn → cycle inventory lớn
- Tối ưu bằng [[Economic Order Quantity (EOQ)]]
- Ví dụ: Đặt 500 lon bia mỗi lần thay vì mỗi ngày 50 lon

#### 2. Safety Stock (Tồn kho an toàn)
- Tồn kho **dự phòng** để đối phó với sự không chắc chắn
- Biến động nhu cầu hoặc thời gian giao hàng
- Chi tiết tại [[Safety Stock]]
- Ví dụ: Giữ thêm 100 lon bia phòng khi nhà cung cấp giao trễ

#### 3. Anticipation Inventory (Tồn kho dự trữ trước)
- Tích trữ **trước mùa cao điểm** hoặc sự kiện đặc biệt
- Ví dụ: Nhà máy bánh trung thu sản xuất trước 3 tháng, tích trữ dần

#### 4. Pipeline/Transit Inventory (Tồn kho trong đường ống)
- Hàng **đang vận chuyển** giữa các điểm trong [[Supply Chain]]
- Ví dụ: Container hàng đang trên tàu từ Trung Quốc sang Việt Nam (mất 5 ngày)
- Pipeline Inventory = d × L (nhu cầu/ngày × thời gian vận chuyển)

### Chi phí tồn kho:
| Loại chi phí | Mô tả | % ước tính |
|---|---|---|
| **Holding Cost (H)** | Chi phí giữ hàng: kho bãi, bảo hiểm, hao mòn, chi phí vốn | 20-40% giá trị/năm |
| **Ordering Cost (S)** | Chi phí đặt hàng: xử lý đơn, vận chuyển, nhận hàng | Cố định/lần đặt |
| **Shortage Cost** | Chi phí thiếu hàng: mất doanh thu, mất khách | Rất cao nhưng khó đo |

### Vấn đề cân bằng:
- Giữ **nhiều** tồn kho → chi phí holding cao, đọng vốn, rủi ro lỗi thời
- Giữ **ít** tồn kho → rủi ro thiếu hàng, mất khách, gián đoạn sản xuất
- → Cần tìm **điểm cân bằng tối ưu** → [[Economic Order Quantity (EOQ)]], [[ABC Analysis]]

## Ví dụ thực tế (Real-world Example)
**Cửa hàng Thế Giới Di Động:**
- **Cycle Inventory:** Đặt 200 chiếc iPhone mỗi lần nhập
- **Safety Stock:** Giữ thêm 30 chiếc phòng khi bán nhanh hơn dự kiến
- **Anticipation:** Nhập thêm 500 chiếc trước Tết (mùa cao điểm)
- **Pipeline:** 100 chiếc đang trên đường giao từ Apple Singapore

## Mối liên hệ (Relationships)
- Tối ưu bằng: [[Economic Order Quantity (EOQ)]], [[ABC Analysis]], [[Reorder Point]]
- Dự phòng: [[Safety Stock]]
- Giảm thiểu qua: [[Lean Systems]], [[Just-in-Time (JIT)]], [[Kanban]]
- Lập kế hoạch: [[Material Requirements Planning (MRP)]], [[Sales and Operations Planning (S&OP)]]
- Dự báo: [[Forecasting]], [[Demand Management]]
- Thuộc chương: Chapter 12 — Inventory Management

## Công thức (Formula)
**Average Cycle Inventory:**
$$Average\ Cycle\ Inventory = \frac{Q}{2}$$

**Pipeline Inventory:**
$$Pipeline\ Inventory = d \times L$$

**Inventory Turns (Vòng quay tồn kho):**
$$Inventory\ Turns = \frac{COGS}{Average\ Inventory}$$

**Days of Supply:**
$$Days\ of\ Supply = \frac{Average\ Inventory}{Daily\ Demand}$$

Trong đó: Q = Order quantity, d = demand/day, L = lead time
