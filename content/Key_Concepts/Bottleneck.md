---
tags: [key-concept, chapter-6, capacity-constraints]
aliases: [Bottleneck, Nút thắt cổ chai, Nút cổ chai, Constraint, Điểm nghẽn]
---
# Bottleneck

## Định nghĩa (Definition)
**Bottleneck** (Nút thắt cổ chai) là công đoạn hoặc nguồn lực có [[Capacity|năng lực]] **thấp nhất** trong toàn bộ quy trình, quyết định **sản lượng tối đa** (throughput) của cả hệ thống.

## Giải thích chi tiết (Detailed Explanation)

### Nguyên lý cốt lõi:
> **Sản lượng của cả hệ thống = Sản lượng của nút thắt cổ chai**

Giống như một chuỗi xích — sức mạnh của cả chuỗi bằng sức mạnh của mắt xích yếu nhất.

### Cách nhận diện Bottleneck:
1. **Công đoạn có thời gian xử lý dài nhất**
2. **Công đoạn có hàng đợi (WIP) tích tụ nhiều nhất** phía trước
3. **Công đoạn luôn hoạt động 100%** trong khi các công đoạn khác có thời gian rảnh

### Tại sao quan trọng?
- Cải tiến bất kỳ công đoạn nào KHÁC nút thắt → **KHÔNG** tăng sản lượng hệ thống
- Chỉ cải tiến nút thắt → mới tăng được sản lượng
- Mất 1 giờ tại nút thắt = Mất 1 giờ sản lượng toàn hệ thống
- Tiết kiệm 1 giờ ở công đoạn không phải nút thắt = **Không có ý nghĩa gì**

### Sau khi giải quyết 1 bottleneck:
- Bottleneck **không biến mất** — nó chỉ **di chuyển** sang công đoạn khác
- Luôn có 1 bottleneck trong hệ thống → [[Theory of Constraints (TOC)]] giúp quản lý liên tục

### Giải pháp xử lý Bottleneck:
1. Tăng năng lực tại nút thắt (thêm máy, thêm ca)
2. Giảm thời gian xử lý (cải tiến quy trình)
3. Đảm bảo nút thắt **không bao giờ dừng** (bảo trì phòng ngừa, luôn có nguyên liệu)
4. Chuyển một phần công việc sang công đoạn khác
5. [[Outsourcing]] công đoạn nút thắt

## Ví dụ thực tế (Real-world Example)
**Nhà máy sản xuất bánh mì:**

| Công đoạn | Năng lực | Thời gian/cái |
|-----------|----------|---------------|
| Trộn bột | 120 cái/giờ | 30 giây |
| Nặn hình | 150 cái/giờ | 24 giây |
| **Nướng** | **80 cái/giờ** | **45 giây** |
| Đóng gói | 200 cái/giờ | 18 giây |

→ **Nướng là Bottleneck!** Dù trộn bột nhanh, nặn hình nhanh, đóng gói nhanh → cả nhà máy chỉ sản xuất được **80 cái/giờ** vì lò nướng giới hạn.

→ Mua thêm 1 lò nướng → năng lực nướng tăng lên 160 cái/giờ → Bottleneck mới di chuyển sang **Trộn bột** (120 cái/giờ)

**Giao thông:**
- Đường 4 làn xe bị thu hẹp thành 2 làn = Bottleneck → kẹt xe tại điểm thu hẹp

## Mối liên hệ (Relationships)
- Quản lý qua: [[Theory of Constraints (TOC)]]
- Ảnh hưởng: [[Capacity]] (giới hạn sản lượng hệ thống)
- Phát hiện qua: [[Value Stream Mapping]]
- Cải tiến qua: [[Lean Systems]], [[Continuous Improvement]]
- Thuộc chương: Chapter 6 — Capacity Planning

## Công thức (Formula)
**Throughput (Sản lượng hệ thống):**
$$Throughput = min(Capacity_{station\ 1}, Capacity_{station\ 2}, ..., Capacity_{station\ n})$$

**Bottleneck Rate:**
$$Bottleneck\ Rate = \frac{1}{Bottleneck\ Time\ per\ Unit}$$
