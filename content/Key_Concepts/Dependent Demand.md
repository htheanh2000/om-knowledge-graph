---
tags: [key-concept, inventory, chapter-13]
aliases: [Dependent Demand, Nhu cầu phụ thuộc]
---
# Dependent Demand

## Định nghĩa (Definition)
**Dependent Demand** (Nhu cầu phụ thuộc) là nhu cầu **phát sinh trực tiếp** từ nhu cầu của sản phẩm cha (parent item) trong [[Bill of Materials (BOM)]].

## Giải thích (Explanation)
Ví dụ: Nhu cầu về **bánh xe** phụ thuộc vào nhu cầu **xe đạp** (1 xe = 2 bánh).
- Nếu cần sản xuất 100 xe → cần chính xác 200 bánh xe
- Nhu cầu bánh xe **không cần dự báo** — tính trực tiếp từ BOM

So sánh:
| | Independent Demand | Dependent Demand |
|---|---|---|
| Nguồn gốc | Thị trường/khách hàng | Sản phẩm cha (BOM) |
| Phương pháp | [[Forecasting]], [[Economic Order Quantity (EOQ)]] | [[Material Requirements Planning (MRP)]] |
| Ví dụ | Xe đạp thành phẩm | Bánh xe, xích, pedal |

[[Material Requirements Planning (MRP)]] là hệ thống quản lý Dependent Demand, sử dụng BOM và [[Master Production Schedule (MPS)]].

## Mối liên hệ (Relationships)
- Quản lý bởi: [[Material Requirements Planning (MRP)]]
- Cấu trúc: [[Bill of Materials (BOM)]]
- Kế hoạch: [[Master Production Schedule (MPS)]]
- Đối lập: Independent Demand → [[Inventory Management]]
