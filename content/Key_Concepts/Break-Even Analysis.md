---
tags: [key-concept, chapter-A, decision-tools]
aliases: [Break-Even Analysis, Phân tích hòa vốn, BEA, Break-Even Point, Điểm hòa vốn]
---
# Break-Even Analysis

## Định nghĩa (Definition)
**Break-Even Analysis** (Phân tích hòa vốn) là công cụ xác định **sản lượng hoặc doanh thu tối thiểu** mà tại đó **tổng doanh thu bằng tổng chi phí** — tức là không lãi, không lỗ. Đây là điểm mà doanh nghiệp bắt đầu **có lãi**.

## Giải thích chi tiết (Detailed Explanation)

### Ba yếu tố:
1. **Fixed Costs (FC — Chi phí cố định):** Không thay đổi theo sản lượng — thuê nhà, lương quản lý, khấu hao máy
2. **Variable Cost per unit (c — Chi phí biến đổi/đơn vị):** Thay đổi theo sản lượng — nguyên liệu, lao động trực tiếp
3. **Price per unit (p — Giá bán/đơn vị):** Giá bán sản phẩm

### Đồ thị:
```
Tiền ($)
  |        /  Total Revenue (p×Q)
  |       / /
  |      / / Total Cost (FC + c×Q)
  |     / /
  |    /×/ ← Break-Even Point!
  |   //
  |  //
  | /
FC|/____________→ Sản lượng (Q)
  |  Q*
  |←Lỗ→|←─── Lãi ──→|
```

### Ý nghĩa:
- **Q < Q*** → **Lỗ** (doanh thu chưa đủ bù chi phí cố định)
- **Q = Q*** → **Hòa vốn** (vừa đủ)
- **Q > Q*** → **Lãi** (mỗi sản phẩm thêm đóng góp lợi nhuận)

### Ứng dụng trong OM:
- Quyết định [[Capacity]] — cần bán bao nhiêu để hòa vốn với nhà máy mới?
- Quyết định [[Outsourcing]] — Make vs Buy: tại sản lượng nào thì tự làm rẻ hơn?
- Đánh giá sản phẩm mới — có khả thi không?
- So sánh phương án đầu tư — phương án nào hòa vốn nhanh hơn?

### Contribution Margin (Biên đóng góp):
- **p − c** = Phần mỗi sản phẩm đóng góp để bù chi phí cố định
- Contribution margin càng lớn → hòa vốn càng nhanh

## Ví dụ thực tế (Real-world Example)
**Mở quán trà sữa:**
- FC (Chi phí cố định/tháng): Thuê mặt bằng 20 triệu + Lương 15 triệu + Khác 5 triệu = **40 triệu đồng**
- c (Chi phí biến đổi/ly): Nguyên liệu 15,000đ + Ly + ống hút 3,000đ = **18,000đ/ly**
- p (Giá bán): **35,000đ/ly**

$$Q^* = \frac{40,000,000}{35,000 - 18,000} = \frac{40,000,000}{17,000} ≈ 2,353\ ly/tháng$$

→ Cần bán **~2,353 ly/tháng** ≈ **~79 ly/ngày** để hòa vốn
→ Nếu bán 100 ly/ngày → Lãi = (100-79) × 17,000 × 30 = **10.7 triệu đồng/tháng**

**So sánh Make vs Buy (liên quan [[Outsourcing]]):**
- Make: FC = 500 triệu, c = 50,000đ/sp
- Buy: Giá mua = 80,000đ/sp (không có FC)
- Q* = 500,000,000 / (80,000 − 50,000) = **16,667 sản phẩm**
- Dưới 16,667 sp → Buy rẻ hơn. Trên 16,667 sp → Make rẻ hơn.

## Mối liên hệ (Relationships)
- Hỗ trợ quyết định: [[Capacity]], [[Outsourcing]], [[Operations Strategy]]
- So sánh với: [[Decision Trees]] (khi có nhiều kịch bản)
- Liên quan: [[Economies of Scale]] (Q lớn → lợi nhuận tăng)
- Thuộc chương: Supplement A — Decision Making

## Công thức (Formula)
**Break-Even Quantity (Sản lượng hòa vốn):**
$$Q^* = \frac{F}{p - c}$$

**Break-Even Revenue (Doanh thu hòa vốn):**
$$Revenue^* = Q^* \times p = \frac{F}{1 - \frac{c}{p}}$$

**Profit at quantity Q:**
$$Profit = (p - c) \times Q - F$$

Trong đó:
- F (FC) = Fixed Cost (Chi phí cố định)
- p = Price per unit (Giá bán/đơn vị)
- c = Variable cost per unit (Chi phí biến đổi/đơn vị)
- Q = Quantity (Sản lượng)
- (p − c) = Contribution margin (Biên đóng góp)
