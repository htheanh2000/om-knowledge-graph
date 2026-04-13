---
tags: [key-concept, chapter-12, inventory]
aliases: [ABC Analysis, Phân tích ABC, ABC Classification, Pareto Analysis for Inventory]
---
# ABC Analysis

## Định nghĩa (Definition)
**ABC Analysis** (Phân tích ABC) là phương pháp phân loại [[Inventory|tồn kho]] thành 3 nhóm (A, B, C) dựa trên **nguyên tắc Pareto 80/20** — một số ít mặt hàng chiếm phần lớn giá trị tồn kho, giúp doanh nghiệp **tập trung nguồn lực quản lý** vào những mặt hàng quan trọng nhất.

## Giải thích chi tiết (Detailed Explanation)

### Nguyên tắc Pareto 80/20:
> Khoảng 20% mặt hàng chiếm ~80% tổng giá trị tồn kho

### 3 nhóm ABC:

| Nhóm | % Số mặt hàng | % Giá trị | Mức quản lý |
|------|---------------|-----------|-------------|
| **A** | ~20% | ~80% | **Chặt chẽ nhất** |
| **B** | ~30% | ~15% | Trung bình |
| **C** | ~50% | ~5% | Đơn giản nhất |

#### Nhóm A — "Kim cương" (Few but vital)
- Ít mặt hàng nhưng giá trị rất cao
- Quản lý chặt: đếm thường xuyên, [[Forecasting|dự báo]] chính xác, [[Safety Stock]] tính toán kỹ
- Đàm phán giá với nhà cung cấp, kiểm soát chặt [[Reorder Point]]
- Ví dụ: iPhone trong cửa hàng điện thoại, chip bán dẫn trong nhà máy

#### Nhóm B — "Bạc" (Moderate)
- Quản lý vừa phải
- Kiểm kê định kỳ (hàng tháng)
- Ví dụ: Phụ kiện điện thoại, linh kiện phụ

#### Nhóm C — "Đồng" (Many but trivial)
- Rất nhiều mặt hàng nhưng giá trị thấp
- Quản lý đơn giản: đặt hàng lô lớn, ít kiểm kê
- Ví dụ: Ốc vít, bao bì, văn phòng phẩm

### Các bước thực hiện:
1. Tính **giá trị sử dụng hàng năm** = Nhu cầu/năm × Giá/đơn vị
2. Sắp xếp từ cao đến thấp
3. Tính % tích lũy
4. Phân nhóm A, B, C

## Ví dụ thực tế (Real-world Example)
**Quán trà sữa phân tích ABC:**

| Nguyên liệu | Nhu cầu/năm | Giá/kg | Giá trị/năm | Nhóm |
|---|---|---|---|---|
| Trà Oolong cao cấp | 500kg | 800k | 400 triệu | **A** |
| Sữa tươi | 2000L | 100k | 200 triệu | **A** |
| Trân châu | 1000kg | 50k | 50 triệu | **B** |
| Đường | 800kg | 20k | 16 triệu | **B** |
| Ly nhựa | 50000 cái | 1k | 50 triệu | **B** |
| Ống hút | 50000 cái | 0.2k | 10 triệu | **C** |
| Giấy ăn | 10000 gói | 0.5k | 5 triệu | **C** |

→ Trà Oolong và sữa (nhóm A) cần quản lý chặt nhất: chọn nhà cung cấp uy tín, đàm phán giá tốt, theo dõi tồn kho hàng ngày.

## Mối liên hệ (Relationships)
- Thuộc về: [[Inventory]] (phương pháp phân loại)
- Ảnh hưởng đến: [[Safety Stock]], [[Reorder Point]], [[Economic Order Quantity (EOQ)]]
- Hỗ trợ: [[Demand Management]] (ưu tiên dự báo cho nhóm A)
- Thuộc chương: Chapter 12 — Inventory Management

## Công thức (Formula)
**Giá trị sử dụng hàng năm:**
$$Annual\ Value = Annual\ Demand \times Unit\ Price$$

**Phân loại:**
- Sắp xếp giảm dần theo Annual Value
- Tính % tích lũy
- A: ~0-80% giá trị tích lũy
- B: ~80-95% giá trị tích lũy
- C: ~95-100% giá trị tích lũy
