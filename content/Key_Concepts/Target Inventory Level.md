---
tags:
  - operations-management
  - inventory
  - periodic-review
aliases:
  - Mức tồn kho mục tiêu
  - Order-Up-To Level
  - T Level
---

# Target Inventory Level

## Định nghĩa
**Mức tồn kho mục tiêu (Target Inventory Level)** là mức tồn kho tối đa cần đạt được trong hệ thống P (Periodic Review System).

## Công thức
$$T = \bar{d}(P + L) + Safety\ Stock$$
- $\bar{d}$ = nhu cầu trung bình/ngày
- $P$ = chu kỳ kiểm kê (review period)
- $L$ = lead time
- Safety Stock = $z \times \sigma_{P+L}$

## Giải thích
- Mỗi kỳ kiểm kê, đặt hàng bổ sung lên đến mức T
- Lượng đặt = T - Tồn kho hiện tại (On-Hand + On-Order)
- Bảo vệ nhu cầu trong cả khoảng P + L (khác Q System chỉ bảo vệ L)

## Liên kết
- [[Safety Stock]]
- [[Reorder Point]]
- [[Independent Demand]]
- [[Stockout]]
- [[Inventory]]
