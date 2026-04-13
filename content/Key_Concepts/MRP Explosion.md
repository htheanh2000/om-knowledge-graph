---
tags:
  - operations-management
  - mrp
  - planning
aliases:
  - Khai triển MRP
  - BOM Explosion
---

# MRP Explosion

## Định nghĩa
**Khai triển MRP (MRP Explosion)** là quá trình tính toán nhu cầu vật liệu từ thành phẩm (cha) xuống các linh kiện (con) theo cấu trúc [[Bill of Materials (BOM)]].

## Giải thích
- Bắt đầu từ [[Master Production Schedule (MPS)]] cho thành phẩm
- Tính [[Gross Requirements]] → [[Net Requirements]] → [[Lot Sizing]] → [[Planned Order Releases]]
- POR của item cha × số lượng BOM = Gross Requirements của item con
- Lặp lại cho mỗi cấp trong BOM (level-by-level)

## Quy trình
1. Xác định nhu cầu thành phẩm từ MPS
2. Tính nhu cầu ròng cho từng item
3. Áp dụng lot sizing
4. Offset theo lead time → POR
5. Khai triển xuống cấp tiếp theo

## Liên kết
- [[Material Requirements Planning (MRP)]]
- [[Bill of Materials (BOM)]]
- [[Planned Order Releases]]
- [[Net Requirements]]
- [[Gross Requirements]]
