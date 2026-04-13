---
tags:
  - operations-management
  - mrp
  - planning
aliases:
  - Nhu cầu gộp
  - Gross Demand
---

# Gross Requirements

## Định nghĩa
**Nhu cầu gộp (Gross Requirements)** là tổng nhu cầu cho một item trong mỗi kỳ, trước khi trừ tồn kho hiện có.

## Giải thích
- Đối với thành phẩm: lấy từ [[Master Production Schedule (MPS)]]
- Đối với nguyên vật liệu/bán thành phẩm: lấy từ [[Planned Order Releases]] của item cha × số lượng trong [[Bill of Materials (BOM)]]
- Là bước đầu tiên trong quy trình tính MRP
- Chưa xét đến tồn kho → cần tính [[Net Requirements]] để biết nhu cầu thực

## Ví dụ
Nếu item cha có POR = 100 và BOM yêu cầu 2 item con → Gross Req item con = 200.

## Liên kết
- [[Net Requirements]]
- [[Planned Order Releases]]
- [[Master Production Schedule (MPS)]]
- [[Bill of Materials (BOM)]]
- [[MRP Explosion]]
