---
tags: [key-concept, chapter-12, inventory]
aliases: [Economic Order Quantity, EOQ, Lượng đặt hàng kinh tế, Sản lượng đặt hàng tối ưu]
---
# Economic Order Quantity (EOQ)

## Định nghĩa (Definition)
**Economic Order Quantity (EOQ)** (Lượng đặt hàng kinh tế) là **số lượng đặt hàng tối ưu** giúp **tổng chi phí tồn kho thấp nhất**, cân bằng giữa chi phí đặt hàng (ordering cost) và chi phí giữ hàng (holding cost).

## Giải thích chi tiết (Detailed Explanation)

### Vấn đề cần giải quyết:
- Đặt hàng **nhiều lần, mỗi lần ít** → Chi phí đặt hàng CAO, chi phí giữ hàng THẤP
- Đặt hàng **ít lần, mỗi lần nhiều** → Chi phí đặt hàng THẤP, chi phí giữ hàng CAO
- EOQ tìm **điểm cân bằng** → Tổng chi phí THẤP NHẤT

### Các giả định của mô hình EOQ:
1. Nhu cầu (D) **không đổi** và biết trước
2. Thời gian giao hàng (L) **không đổi** và biết trước
3. Toàn bộ lô hàng giao **cùng một lúc** (không giao dần)
4. Không cho phép thiếu hàng (no stockouts)
5. Chi phí đặt hàng (S) và chi phí giữ hàng (H) **không đổi**
6. Không có chiết khấu theo số lượng

### Trực giác:
Tại điểm EOQ: **Tổng chi phí đặt hàng/năm = Tổng chi phí giữ hàng/năm**

$$\frac{D}{Q} \times S = \frac{Q}{2} \times H$$

Giải ra → EOQ!

### Đặc điểm quan trọng:
- Đường tổng chi phí có dạng **chữ U phẳng** (flat bottom)
- Sai lệch ±20% so với EOQ → tổng chi phí chỉ tăng ~2%
- → EOQ là **hướng dẫn tốt**, không cần chính xác tuyệt đối

## Ví dụ thực tế (Real-world Example)
**Cửa hàng văn phòng phẩm đặt giấy A4:**
- D = 10,000 ram/năm
- S = 200,000 đồng/lần đặt hàng
- H = 50,000 đồng/ram/năm

$$EOQ = \sqrt{\frac{2 \times 10000 \times 200000}{50000}} = \sqrt{80000} ≈ 283\ ram$$

**Diễn giải:**
- Đặt mỗi lần **283 ram**
- Số lần đặt/năm = 10,000 / 283 ≈ **35 lần/năm** (khoảng mỗi 10 ngày)
- Tồn kho trung bình = 283/2 ≈ **142 ram**
- Tổng chi phí = (10000/283)×200000 + (283/2)×50000 ≈ **14.14 triệu đồng/năm**

## Mối liên hệ (Relationships)
- Thuộc về: [[Inventory]] (tối ưu cycle inventory)
- Kết hợp với: [[Reorder Point]] (khi nào đặt hàng)
- Bổ sung bởi: [[Safety Stock]] (dự phòng biến động)
- Phân loại ưu tiên: [[ABC Analysis]]
- Liên quan: [[Lean Systems]] (JIT hướng đến Q nhỏ nhất có thể)
- Thuộc chương: Chapter 12 — Inventory Management

## Công thức (Formula)
**EOQ:**
$$EOQ = \sqrt{\frac{2DS}{H}}$$

**Tổng chi phí tồn kho hàng năm (Total Annual Cost):**
$$TC = \frac{D}{Q} \times S + \frac{Q}{2} \times H$$

**Số lần đặt hàng/năm:**
$$N = \frac{D}{EOQ}$$

**Thời gian giữa các lần đặt (Time Between Orders):**
$$TBO = \frac{EOQ}{D} \times 365\ ngày$$

Trong đó:
- D = Nhu cầu hàng năm (Annual Demand)
- S = Chi phí đặt hàng/lần (Ordering Cost per order)
- H = Chi phí giữ hàng/đơn vị/năm (Holding Cost per unit per year)
- Q = Số lượng đặt hàng
