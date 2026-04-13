---
tags: [key-concept, chapter-15, planning]
aliases: [Bill of Materials, BOM, Định mức vật tư, Cấu trúc sản phẩm, Product Structure Tree]
---
# Bill of Materials (BOM)

## Định nghĩa (Definition)
**Bill of Materials (BOM)** (Định mức vật tư) là danh sách đầy đủ tất cả **nguyên vật liệu, linh kiện, và bán thành phẩm** cần thiết để sản xuất **một đơn vị thành phẩm**, thể hiện dưới dạng **cây cấu trúc sản phẩm (Product Structure Tree)** theo các cấp (levels).

## Giải thích chi tiết (Detailed Explanation)

### Cấu trúc cây (Product Structure Tree):
```
Level 0:        Xe đạp (1)
                /    |    \
Level 1:   Khung(1) Bánh(2) Yên(1)
              |      /   \
Level 2:   Sơn(0.5L) Vành(1) Lốp(1)
                        |
Level 3:             Nan hoa(36)
```

### Các khái niệm:
- **Level 0:** Thành phẩm (finished product)
- **Level 1, 2, 3...:** Các cấp linh kiện con, càng xuống càng chi tiết
- **Parent (Cha):** Sản phẩm ở cấp trên
- **Child/Component (Con):** Linh kiện ở cấp dưới
- **Quantity per parent:** Số lượng linh kiện con cần cho 1 đơn vị cha

### Vai trò trong [[Material Requirements Planning (MRP)]]:
BOM là **bản thiết kế** cho MRP biết:
- Để làm 1 xe đạp cần CHÍNH XÁC những gì
- Bao nhiêu mỗi thứ
- Thứ tự lắp ráp (từ level thấp nhất lên)

### Loại BOM:
1. **Single-level BOM:** Chỉ liệt kê cấp 1 (linh kiện trực tiếp)
2. **Multi-level BOM (Indented BOM):** Tất cả các cấp, có thụt đầu dòng
3. **Planning BOM:** Dùng cho [[Sales and Operations Planning (S&OP)|S&OP]], gom nhóm sản phẩm

### Lưu ý quan trọng:
- **Low-Level Coding:** Mỗi linh kiện được gán level thấp nhất mà nó xuất hiện → tránh tính trùng trong MRP
- BOM phải **luôn cập nhật** — nếu sai → MRP tính sai → đặt thừa hoặc thiếu nguyên liệu

## Ví dụ thực tế (Real-world Example)
**BOM của 1 chiếc bánh mì sandwich:**

```
Level 0:    Bánh mì Sandwich (1)
            /       |       \
Level 1: Vỏ bánh(2) Nhân(1) Rau sống(1 phần)
           |         |        |
Level 2: Bột mì   Thịt     Xà lách(2 lá)
         (100g)   nguội     Cà chua(2 lát)
         Men(5g)  (50g)     Dưa chuột(3 lát)
         Nước(50ml) Phô mai
         Muối(2g)  (1 lát)
```

**MRP cho 100 sandwich:**
- Vỏ bánh: 100 × 2 = 200 vỏ → Bột mì: 200 × 100g = 20kg
- Thịt nguội: 100 × 50g = 5kg
- Xà lách: 100 × 2 = 200 lá
- v.v.

## Mối liên hệ (Relationships)
- Đầu vào cho: [[Material Requirements Planning (MRP)]]
- Kết hợp với: [[Master Production Schedule (MPS)]] (MPS nói bao nhiêu sản phẩm, BOM nói cần gì)
- Quản lý trong: [[Enterprise Resource Planning (ERP)]]
- Liên quan: [[Inventory]] (kiểm tra tồn kho từng linh kiện)
- Thuộc chương: Chapter 15 — Resource Planning

## Công thức (Formula)
**Gross Requirements (Nhu cầu gộp) cho linh kiện con:**
$$Gross\ Req_{child} = Planned\ Order\ Release_{parent} \times Qty\ per\ Parent$$

**Ví dụ:**
- Cần sản xuất 100 xe đạp (parent)
- Mỗi xe cần 2 bánh xe (qty per parent = 2)
- Gross Requirement bánh xe = 100 × 2 = **200 bánh**
- Mỗi bánh cần 36 nan hoa → Gross Requirement nan hoa = 200 × 36 = **7,200 nan hoa**
