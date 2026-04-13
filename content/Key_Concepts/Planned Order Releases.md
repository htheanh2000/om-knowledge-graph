---
tags:
  - operations-management
  - mrp
  - planning
aliases:
  - Kế hoạch phát lệnh sản xuất
  - POR
---

# Planned Order Releases

## Định nghĩa
**Kế hoạch phát lệnh sản xuất (Planned Order Releases)** là output chính của hệ thống MRP, cho biết thời điểm và số lượng cần đặt hàng hoặc bắt đầu sản xuất.

## Giải thích
- POR = Planned Order Receipts lùi lại theo lead time
- Là đầu vào cho [[Gross Requirements]] của item cấp dưới trong [[Bill of Materials (BOM)]]
- Quá trình tính: Gross Req → [[Net Requirements]] → Lot Sizing → POR
- Khi POR được xác nhận → trở thành Scheduled Receipts

## Ví dụ
Nếu cần nhận hàng tuần 5, lead time = 2 tuần → POR ở tuần 3.

## Liên kết
- [[Material Requirements Planning (MRP)]]
- [[Net Requirements]]
- [[Gross Requirements]]
- [[Lot Sizing]]
- [[MRP Explosion]]
