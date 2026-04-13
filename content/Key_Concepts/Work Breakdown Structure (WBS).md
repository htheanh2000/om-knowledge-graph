---
tags: [key-concept, chapter-7, project-management]
aliases: [Work Breakdown Structure, WBS, Cấu trúc phân chia công việc, Cấu trúc phân rã công việc]
---
# Work Breakdown Structure (WBS)

## Định nghĩa (Definition)
**Work Breakdown Structure (WBS)** (Cấu trúc phân chia công việc) là phương pháp **phân rã toàn bộ dự án** thành các **gói công việc nhỏ hơn** (work packages) có thể quản lý, lập lịch, phân công, và theo dõi được, tổ chức dưới dạng **cấu trúc cây phân cấp**.

## Giải thích chi tiết (Detailed Explanation)

### Nguyên tắc:
> "Ăn cả con voi? → Cắt thành từng miếng nhỏ!"

Dự án lớn, phức tạp → chia nhỏ → dễ quản lý, dễ ước tính thời gian và chi phí.

### Cấu trúc phân cấp:
```
Level 0: Dự án tổng thể
    Level 1: Giai đoạn chính (Major Phases)
        Level 2: Công việc chính (Major Tasks)
            Level 3: Công việc con (Subtasks)
                Level 4: Gói công việc (Work Packages)
```

### Quy tắc xây dựng WBS:
1. **100% Rule:** WBS phải bao gồm 100% công việc cần thiết — không thiếu, không thừa
2. **Mutually Exclusive:** Các gói công việc không chồng chéo
3. **Outcome-oriented:** Tập trung vào **kết quả** (deliverables), không phải hành động
4. **Work Package** là cấp thấp nhất: đủ nhỏ để ước tính thời gian, chi phí, phân công cho 1 người/nhóm

### WBS → [[Critical Path]]:
1. WBS phân chia công việc
2. Xác định thứ tự phụ thuộc giữa các work packages
3. Ước tính thời gian mỗi work package
4. Vẽ project network → Tìm Critical Path

## Ví dụ thực tế (Real-world Example)
**WBS cho dự án "Mở quán cà phê mới":**

```
1. Mở quán cà phê
   1.1 Lập kế hoạch
       1.1.1 Nghiên cứu thị trường (2 tuần)
       1.1.2 Lập kế hoạch kinh doanh (1 tuần)
       1.1.3 Xin giấy phép (3 tuần)
   1.2 Xây dựng & Thiết kế
       1.2.1 Tìm mặt bằng (4 tuần)
       1.2.2 Thiết kế nội thất (2 tuần)
       1.2.3 Thi công (6 tuần)
   1.3 Mua sắm thiết bị
       1.3.1 Mua máy pha cà phê (2 tuần)
       1.3.2 Mua bàn ghế (3 tuần)
       1.3.3 Mua nguyên liệu ban đầu (1 tuần)
   1.4 Nhân sự
       1.4.1 Tuyển barista (3 tuần)
       1.4.2 Đào tạo (2 tuần)
   1.5 Marketing
       1.5.1 Thiết kế thương hiệu (2 tuần)
       1.5.2 Quảng cáo khai trương (1 tuần)
   1.6 Khai trương (1 ngày)
```

→ Từ WBS này → xác định thứ tự → tìm [[Critical Path]] → biết khi nào khai trương được!

## Mối liên hệ (Relationships)
- Đầu ra cho: [[Critical Path]] (xác định các hoạt động và thứ tự)
- Tương tự với: [[Bill of Materials (BOM)]] (BOM cho sản phẩm, WBS cho dự án)
- Hỗ trợ: Ước tính chi phí, thời gian, phân bổ [[Capacity|nguồn lực]]
- Thuộc chương: Chapter 7 — Project Management

## Công thức (Formula)
Không có công thức toán học. WBS là công cụ cấu trúc hóa (decomposition tool).

**Ước tính thời gian cho work package (PERT):**
$$t_e = \frac{a + 4m + b}{6}$$

Trong đó:
- a = Thời gian lạc quan nhất (optimistic)
- m = Thời gian khả năng nhất (most likely)
- b = Thời gian bi quan nhất (pessimistic)
