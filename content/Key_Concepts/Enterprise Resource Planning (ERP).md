---
tags: [key-concept, chapter-15, planning, technology]
aliases: [Enterprise Resource Planning, ERP, Hoạch định nguồn lực doanh nghiệp, Hệ thống ERP]
---
# Enterprise Resource Planning (ERP)

## Định nghĩa (Definition)
**Enterprise Resource Planning (ERP)** (Hoạch định nguồn lực doanh nghiệp) là hệ thống phần mềm **tích hợp toàn diện** kết nối tất cả các bộ phận — sản xuất, tài chính, nhân sự, bán hàng, mua hàng, kho — vào **một cơ sở dữ liệu duy nhất**, cho phép chia sẻ thông tin theo thời gian thực.

## Giải thích chi tiết (Detailed Explanation)

### Vấn đề trước ERP:
- Mỗi bộ phận dùng phần mềm riêng → **thông tin cô lập** (silos)
- Kế toán không biết kho còn bao nhiêu hàng
- Sản xuất không biết bán hàng đã hứa giao khi nào
- → Sai sót, trùng lặp, chậm trễ

### ERP giải quyết bằng cách:
Tất cả bộ phận dùng **chung 1 hệ thống, 1 cơ sở dữ liệu:**
```
         ┌─── Bán hàng ────┐
         │                   │
Tài chính ─── CƠ SỞ DỮ ─── Sản xuất
         │    LIỆU CHUNG    │
 Nhân sự ───              ─── Mua hàng
         │                   │
         └─── Kho hàng ────┘
```

### Các module chính:
| Module | Chức năng |
|--------|-----------|
| Finance/Accounting | Kế toán, báo cáo tài chính |
| Human Resources | Quản lý nhân sự, tính lương |
| Manufacturing/Production | [[Material Requirements Planning (MRP)|MRP]], lập lịch sản xuất |
| Supply Chain Management | [[Supply Chain|Chuỗi cung ứng]], mua hàng, kho |
| Sales & Marketing | Quản lý đơn hàng, CRM |
| Quality Management | [[Total Quality Management (TQM)|Quản lý chất lượng]] |

### Nhà cung cấp ERP phổ biến:
- **SAP** — Lớn nhất thế giới, dùng nhiều ở Đức và châu Âu
- **Oracle** — Mạnh về tài chính và cloud
- **Microsoft Dynamics** — Dễ dùng, phổ biến SME
- **Odoo** — Mã nguồn mở, phổ biến ở Việt Nam

### Ưu và nhược điểm:
| Ưu điểm | Nhược điểm |
|---------|-----------|
| Thông tin tập trung, thời gian thực | Chi phí triển khai rất cao |
| Giảm lỗi, giảm trùng lặp | Thời gian triển khai dài (1-3 năm) |
| Hỗ trợ ra quyết định tốt hơn | Phức tạp, cần đào tạo nhiều |
| Tiêu chuẩn hóa quy trình | Phải thay đổi cách làm việc |

### Tiến hóa:
MRP → MRP II → **ERP** → ERP II (mở rộng ra đối tác bên ngoài) → [[Cloud Computing|Cloud ERP]]

## Ví dụ thực tế (Real-world Example)
**Vingroup triển khai SAP ERP:**
- Trước ERP: Mỗi công ty con (VinFast, Vinmart, Vinhomes) dùng hệ thống riêng → khó tổng hợp
- Sau ERP: Toàn bộ tập đoàn dùng SAP → ban lãnh đạo thấy tình hình tài chính, tồn kho, nhân sự toàn tập đoàn **theo thời gian thực**

**Ví dụ quy trình tích hợp:**
1. Khách đặt hàng trên website (module Sales)
2. Hệ thống tự kiểm tra tồn kho (module Warehouse)
3. Nếu thiếu → tự tạo lệnh sản xuất (module Manufacturing/[[Material Requirements Planning (MRP)|MRP]])
4. MRP tính nguyên liệu cần → tạo đơn mua hàng (module Procurement)
5. Kế toán ghi nhận tự động (module Finance)
6. Tất cả diễn ra **tự động, liền mạch** trong 1 hệ thống!

## Mối liên hệ (Relationships)
- Bao gồm: [[Material Requirements Planning (MRP)]], [[Master Production Schedule (MPS)]]
- Hỗ trợ: [[Sales and Operations Planning (S&OP)]], [[Inventory]], [[Supply Chain]]
- Công nghệ: [[Cloud Computing]], [[Internet of Things (IoT)]]
- Liên quan: [[Industry 4.0]] (ERP tích hợp IoT, AI)
- Thuộc chương: Chapter 15 — Resource Planning

## Công thức (Formula)
Không có công thức toán học. ERP là hệ thống phần mềm quản lý tích hợp.
