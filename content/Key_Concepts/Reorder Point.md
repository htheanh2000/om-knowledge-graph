---
tags: [key-concept, chapter-12, inventory]
aliases: [Reorder Point, ROP, Điểm đặt hàng lại, Điểm tái đặt hàng, R]
---
# Reorder Point

## Định nghĩa (Definition)
**Reorder Point (R)** (Điểm đặt hàng lại) là **mức tồn kho** mà tại đó doanh nghiệp cần **đặt hàng bổ sung**, đảm bảo hàng mới về kịp trước khi hết hàng, có tính đến [[Safety Stock|tồn kho an toàn]].

## Giải thích chi tiết (Detailed Explanation)

### Ý tưởng:
- Khi tồn kho giảm dần → đến mức R → **đặt hàng ngay!**
- Trong thời gian chờ hàng (lead time L) → dùng tồn kho còn lại
- Hàng về đúng lúc → không bị hết hàng

### Hai thành phần:
1. **Nhu cầu trong thời gian giao hàng** (d × L): Lượng hàng cần dùng từ lúc đặt đến lúc hàng về
2. **[[Safety Stock]]**: Dự phòng cho biến động

### Minh họa trực quan:
```
Tồn kho
  |
Q |\.
  | \.
  |  \.
R |---\. ← Đặt hàng tại đây!
  |    \.
SS|-----\. ← Safety Stock
  |      |←L→|
  |____________→ Thời gian
         ↑
     Hàng về
```

### Hệ thống kiểm soát tồn kho:

#### Continuous Review (Q System):
- Theo dõi tồn kho **liên tục** (thời gian thực)
- Khi tồn kho chạm R → đặt đúng Q đơn vị (thường là [[Economic Order Quantity (EOQ)|EOQ]])
- **Q cố định, thời gian đặt hàng thay đổi**

#### Periodic Review (P System):
- Kiểm tra tồn kho **định kỳ** (mỗi tuần, mỗi tháng)
- Đặt hàng đủ để nâng tồn kho lên mức mục tiêu T
- **Thời gian cố định, Q thay đổi**

## Ví dụ thực tế (Real-world Example)
**Cửa hàng giày thể thao:**
- Nhu cầu trung bình: d = 10 đôi/ngày
- Lead time: L = 5 ngày
- Safety Stock: SS = 20 đôi (đã tính dựa trên biến thiên nhu cầu)

$$R = d \times L + SS = 10 \times 5 + 20 = 70\ đôi$$

→ Khi tồn kho giảm xuống còn **70 đôi** → đặt hàng ngay!
→ Trong 5 ngày chờ hàng: bán ~50 đôi → còn ~20 đôi (Safety Stock)
→ Hàng mới về → tiếp tục bán

**Nếu không có Safety Stock (SS = 0):**
- R = 50 đôi
- Nếu tuần đó nhu cầu tăng đột ngột (12 đôi/ngày) → cần 60 đôi trong 5 ngày → **hết hàng 10 đôi!**

## Mối liên hệ (Relationships)
- Bao gồm: [[Safety Stock]]
- Kết hợp với: [[Economic Order Quantity (EOQ)]] (Q system: đặt EOQ khi chạm R)
- Phân loại qua: [[ABC Analysis]] (nhóm A cần R chính xác nhất)
- Dữ liệu từ: [[Forecasting]] (dự báo d), [[Demand Management]]
- Thuộc về: [[Inventory]]
- Thuộc chương: Chapter 12 — Inventory Management

## Công thức (Formula)
**Reorder Point (nhu cầu ổn định, lead time ổn định):**
$$R = d \times L + Safety\ Stock$$

**Với Safety Stock:**
$$R = d \times L + z \times \sigma_d \times \sqrt{L}$$

**Periodic Review System — Order-Up-To Level (T):**
$$T = d(L + P) + Safety\ Stock_{P+L}$$
$$Safety\ Stock_{P+L} = z \times \sigma_d \times \sqrt{P + L}$$

Trong đó:
- d = Nhu cầu trung bình/ngày
- L = Lead time (thời gian giao hàng)
- z = Hệ số an toàn (service level)
- σ_d = Độ lệch chuẩn nhu cầu
- P = Chu kỳ kiểm tra (periodic review)
