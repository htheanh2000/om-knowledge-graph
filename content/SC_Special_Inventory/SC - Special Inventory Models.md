---
tags: [supplement-C, part3, inventory, newsvendor, quantity-discounts, noninstantaneous-replenishment]
aliases: [Mô hình tồn kho đặc biệt, Special Inventory Models, Supplement C]
---
# Supplement C - Special Inventory Models (Mô hình tồn kho đặc biệt)

## Tổng quan (Overview)

Supplement C mở rộng các mô hình tồn kho từ [[CH09 - Inventory Management]] cho các tình huống thực tế mà mô hình [[Economic Order Quantity (EOQ)]] cơ bản không áp dụng được. Ba mô hình quan trọng: (1) [[Noninstantaneous Replenishment]] khi hàng được giao/sản xuất dần dần thay vì một lúc, (2) [[Quantity Discounts]] khi nhà cung cấp giảm giá theo số lượng mua, và (3) [[One-Period Decision]] (bài toán báo bán) khi chỉ có một cơ hội đặt hàng duy nhất.

Các mô hình này phản ánh thực tế tốt hơn mô hình EOQ cơ bản. Trong thực tế, nhà máy sản xuất và tiêu thụ đồng thời (không phải nhận cả lô cùng lúc), nhà cung cấp luôn đưa ra bảng giá bậc thang, và nhiều sản phẩm có vòng đời ngắn chỉ bán được một mùa (áo thời trang, vé máy bay, phòng khách sạn).

Hiểu các mô hình này giúp nhà quản lý đưa ra quyết định tối ưu hơn về [[Lot Size]], thời điểm đặt hàng, và quản lý rủi ro trong [[Supply Chain Management]].

---

## Noninstantaneous Replenishment (Bổ sung hàng không tức thời)

### Định nghĩa (Definition)
[[Noninstantaneous Replenishment]] (còn gọi là [[Production Order Quantity Model]] hay [[Economic Production Lot Size]]) áp dụng khi hàng được **sản xuất/giao dần dần** trong một khoảng thời gian, thay vì nhận cả lô cùng một lúc như giả định của [[EOQ]] cơ bản.

### Giải thích chi tiết (Detailed Explanation)

#### Khi nào cần mô hình này?
- Nhà máy tự sản xuất: vừa sản xuất vừa tiêu thụ đồng thời
- Nhà cung cấp giao hàng nhiều đợt (ví dụ: mỗi ngày giao một xe tải thay vì một container)

#### Sự khác biệt với [[EOQ]] cơ bản:
- EOQ cơ bản: tồn kho tăng từ 0 lên Q ngay lập tức
- Noninstantaneous: tồn kho tăng **dần** (vì đang sản xuất với tốc độ p, nhưng tiêu thụ với tốc độ d)
- Tồn kho tối đa < Q (vì trong lúc sản xuất, hàng cũng đang được tiêu thụ)

#### Các ký hiệu:
- $p$ = tốc độ sản xuất (đơn vị/ngày)
- $d$ = tốc độ tiêu thụ / nhu cầu (đơn vị/ngày), với $p > d$
- $D$ = nhu cầu hàng năm
- $H$ = [[Holding Cost]] /đơn vị/năm
- $S$ = [[Setup Cost]] /lần sản xuất

#### Tồn kho tối đa:
$$I_{max} = \frac{Q}{p}(p - d) = Q\left(1 - \frac{d}{p}\right)$$

#### Tồn kho trung bình:
$$\bar{I} = \frac{I_{max}}{2} = \frac{Q}{2}\left(1 - \frac{d}{p}\right)$$

#### Tổng chi phí:
$$TC = \frac{Q}{2}\left(1 - \frac{d}{p}\right)H + \frac{D}{Q}S$$

#### Công thức [[Economic Production Lot Size]] (ELS):
$$ELS = Q^* = \sqrt{\frac{2DS}{H\left(1 - \frac{d}{p}\right)}}$$

**Nhận xét**: So với [[EOQ]], ELS có thêm $(1 - d/p)$ ở mẫu → ELS > EOQ. Điều này hợp lý: vì tồn kho trung bình thấp hơn (do tiêu thụ đồng thời), ta có thể sản xuất lô lớn hơn mà chi phí lưu giữ vẫn chấp nhận được.

### Ví dụ thực tế (Real-world Example)

**Bài toán**: Nhà máy sản xuất nước đóng chai:
- $D$ = 50.000 thùng/năm
- $p$ = 300 thùng/ngày (công suất máy)
- $d$ = 200 thùng/ngày (nhu cầu, giả sử 250 ngày/năm)
- $H$ = 5.000 VND/thùng/năm
- $S$ = 500.000 VND/lần setup máy

$$ELS = \sqrt{\frac{2 \times 50.000 \times 500.000}{5.000 \times (1 - 200/300)}} = \sqrt{\frac{50 \times 10^9}{5.000 \times 0.333}} = \sqrt{\frac{50 \times 10^9}{1.667}} = \sqrt{30 \times 10^6} \approx 5.477 \text{ thùng}$$

So sánh: EOQ bình thường = $\sqrt{\frac{2 \times 50.000 \times 500.000}{5.000}}$ = $\sqrt{10 \times 10^6}$ ≈ 4.472 thùng.

ELS (5.477) > EOQ (4.472) → lô sản xuất lớn hơn vì tồn kho thực sự thấp hơn do tiêu thụ đồng thời.

$I_{max} = 5.477 \times (1 - 200/300) = 5.477 \times 0.333 ≈ $ **1.826 thùng** (thay vì 5.477 nếu nhận cả lô)

### Liên kết (Related Concepts)
- [[Economic Order Quantity (EOQ)]]
- [[Setup Cost]]
- [[Cycle Inventory]]
- [[Lean Operations]]
- [[Batch Production]]

---

## Quantity Discounts (Chiết khấu số lượng)

### Định nghĩa (Definition)
[[Quantity Discounts]] xảy ra khi nhà cung cấp đưa ra **bảng giá bậc thang**: mua càng nhiều, giá mỗi đơn vị càng rẻ. Bài toán là tìm kích thước lô tối ưu khi giá thay đổi theo số lượng.

### Giải thích chi tiết (Detailed Explanation)

#### Tổng chi phí (bao gồm chi phí mua hàng):
$$TC = \frac{Q}{2}H + \frac{D}{Q}S + P \times D$$

Trong đó:
- $P$ = giá mua/đơn vị (thay đổi theo bậc chiết khấu)
- $P \times D$ = tổng chi phí mua hàng/năm
- Nếu $H$ tính theo % giá: $H = P \times h$ (h = % chi phí lưu giữ)

#### Quy trình giải bài toán [[Quantity Discounts]]:

**Bước 1**: Tính [[EOQ]] cho mỗi mức giá
$$EOQ_i = \sqrt{\frac{2DS}{H_i}} = \sqrt{\frac{2DS}{P_i \times h}}$$

**Bước 2**: Kiểm tra tính khả thi (feasibility)
- Nếu $EOQ_i$ nằm trong khoảng số lượng của mức giá $i$ → khả thi
- Nếu $EOQ_i$ < số lượng tối thiểu của mức giá $i$ → điều chỉnh lên mức tối thiểu
- Nếu $EOQ_i$ > số lượng tối đa → loại bỏ

**Bước 3**: Tính TC cho mỗi mức giá khả thi (dùng Q khả thi)

**Bước 4**: Chọn Q có TC thấp nhất

### Ví dụ thực tế (Real-world Example)

**Bài toán**: Nhà hàng mua gạo, D = 10.000 kg/năm, S = 200.000 VND/đơn hàng, h = 20%/năm.

| Mức | Số lượng (kg) | Giá (VND/kg) |
|-----|-------------|-------------|
| 1 | 0 - 499 | 15.000 |
| 2 | 500 - 999 | 14.000 |
| 3 | ≥ 1.000 | 13.000 |

**Tính EOQ cho mỗi mức**:
- Mức 1: H₁ = 15.000 × 0.2 = 3.000 → EOQ₁ = √(2×10.000×200.000/3.000) = √(1.333.333) ≈ **1.155 kg** → KHÔNG khả thi (1.155 > 499)
- Mức 2: H₂ = 14.000 × 0.2 = 2.800 → EOQ₂ = √(2×10.000×200.000/2.800) ≈ **1.195 kg** → KHÔNG khả thi (1.195 > 999)
- Mức 3: H₃ = 13.000 × 0.2 = 2.600 → EOQ₃ = √(2×10.000×200.000/2.600) ≈ **1.240 kg** → Khả thi (≥ 1.000)

**Tính TC cho các Q khả thi**: Q = 500 (tối thiểu mức 2), Q = 1.000 (tối thiểu mức 3), Q = 1.240 (EOQ mức 3)

| Q | Giá P | Holding | Ordering | Mua hàng | **TC** |
|---|-------|---------|----------|----------|--------|
| 500 | 14.000 | 500/2×2.800 = 700K | 10.000/500×200K = 4.000K | 140.000K | **144.700K** |
| 1.000 | 13.000 | 1.000/2×2.600 = 1.300K | 10.000/1.000×200K = 2.000K | 130.000K | **133.300K** |
| 1.240 | 13.000 | 1.240/2×2.600 = 1.612K | 10.000/1.240×200K = 1.613K | 130.000K | **133.225K** |

→ Chọn Q = **1.240 kg** (TC thấp nhất). Lưu ý: mua giá rẻ nhất không phải lúc nào cũng tối ưu vì [[Holding Cost]] tăng!

### Liên kết (Related Concepts)
- [[Economic Order Quantity (EOQ)]]
- [[Holding Cost]]
- [[Total Cost]]
- [[Supplier Selection]]
- [[Purchasing Management]]

---

## One-Period Decisions - Newsvendor Problem (Bài toán một giai đoạn / Bài toán người bán báo)

### Định nghĩa (Definition)
[[One-Period Decision]] (hay [[Newsvendor Problem]] / [[Single-Period Model]]) áp dụng cho sản phẩm chỉ bán được trong **một mùa/giai đoạn duy nhất**. Hàng thừa cuối kỳ bị mất giá trị hoặc phải xử lý. Bài toán: **Đặt bao nhiêu để cân bằng giữa rủi ro thừa và thiếu?**

### Giải thích chi tiết (Detailed Explanation)

#### Tại sao gọi là "Newsvendor" (người bán báo)?
Người bán báo mỗi sáng phải quyết định mua bao nhiêu tờ báo. Báo thừa cuối ngày = giấy vụn (lỗ). Báo thiếu = mất doanh thu. Không thể đặt thêm giữa ngày.

#### Ứng dụng thực tế:
- Quần áo thời trang theo mùa (Zara, H&M)
- Vé máy bay cho một chuyến bay cụ thể
- Phòng khách sạn cho một đêm cụ thể
- Hoa tươi, báo ngày, vé sự kiện
- Sản phẩm công nghệ ra mắt (iPhone mới)

#### Hai loại chi phí:
1. **[[Cost of Understocking]] ($C_u$)**: Chi phí cơ hội khi thiếu hàng
   - $C_u$ = Giá bán - Giá mua (= lợi nhuận mất đi cho mỗi đơn vị thiếu)
   - Có thể bao gồm cả [[Goodwill Loss]] (mất uy tín)

2. **[[Cost of Overstocking]] ($C_o$)**: Chi phí khi thừa hàng
   - $C_o$ = Giá mua - Giá xử lý/thanh lý ([[Salvage Value]])
   - Lỗ ròng cho mỗi đơn vị thừa

#### [[Critical Ratio]] (Tỷ lệ phục vụ tối ưu):
$$CR = \frac{C_u}{C_u + C_o}$$

**Ý nghĩa**: CR cho biết [[Service Level]] tối ưu. Đặt hàng sao cho xác suất bán hết ≤ CR.

- Nếu $C_u$ rất lớn so với $C_o$ → CR gần 1 → đặt nhiều (vì thiếu hàng tốn kém)
- Nếu $C_o$ rất lớn so với $C_u$ → CR gần 0 → đặt ít (vì thừa hàng tốn kém)

#### Tìm Q tối ưu:
1. Tính CR
2. Tra bảng phân phối chuẩn tìm z ứng với CR
3. $Q^* = \mu + z\sigma$

(Với $\mu$ = nhu cầu trung bình, $\sigma$ = độ lệch chuẩn nhu cầu)

### Ví dụ thực tế (Real-world Example)

**Bài toán**: Cửa hàng hoa ở Đà Lạt bán hoa hồng dịp Valentine.
- Giá mua: 30.000 VND/bó
- Giá bán: 80.000 VND/bó
- Giá thanh lý (sau Valentine): 10.000 VND/bó
- Nhu cầu ~ Normal($\mu$ = 300, $\sigma$ = 50 bó)

**Tính toán**:
- $C_u$ = 80.000 - 30.000 = **50.000 VND** (lợi nhuận mất nếu thiếu 1 bó)
- $C_o$ = 30.000 - 10.000 = **20.000 VND** (lỗ nếu thừa 1 bó)
- $CR = \frac{50.000}{50.000 + 20.000} = \frac{50}{70} = 0.714$

Tra bảng z: P(Z ≤ z) = 0.714 → z ≈ **0.57**

$Q^* = 300 + 0.57 \times 50 = 300 + 28.5 ≈$ **329 bó**

**Giải thích**: Nên đặt 329 bó. Vì thiếu hàng tốn kém hơn thừa hàng (mất 50K vs lỗ 20K), nên đặt **trên** mức trung bình. Có 71.4% khả năng bán hết toàn bộ hoặc thiếu hàng.

### Liên kết (Related Concepts)
- [[Service Level]]
- [[Risk Management]]
- [[Revenue Management]]
- [[Demand Variability]]
- [[Normal Distribution]]
- [[Inventory Management]]

---

## Công thức quan trọng (Key Formulas)

| Công thức | Ký hiệu | Mô tả |
|-----------|----------|-------|
| $ELS = \sqrt{\frac{2DS}{H(1-d/p)}}$ | [[Economic Production Lot Size]] | Lô sản xuất tối ưu |
| $I_{max} = Q(1 - d/p)$ | Tồn kho tối đa | Khi bổ sung không tức thời |
| $TC = \frac{Q}{2}H + \frac{D}{Q}S + PD$ | [[Total Cost]] với chiết khấu | Bao gồm chi phí mua hàng |
| $CR = \frac{C_u}{C_u + C_o}$ | [[Critical Ratio]] | Tỷ lệ phục vụ tối ưu (Newsvendor) |
| $Q^* = \mu + z\sigma$ | Lượng đặt tối ưu | Bài toán một giai đoạn |

---

## Từ khóa chính (Key Terms)

- [[Noninstantaneous Replenishment]] - Bổ sung hàng không tức thời
- [[Economic Production Lot Size]] - Lô sản xuất kinh tế
- [[Quantity Discounts]] - Chiết khấu số lượng
- [[One-Period Decision]] - Quyết định một giai đoạn
- [[Newsvendor Problem]] - Bài toán người bán báo
- [[Critical Ratio]] - Tỷ lệ phục vụ tối ưu
- [[Cost of Understocking]] - Chi phí thiếu hàng
- [[Cost of Overstocking]] - Chi phí thừa hàng
- [[Salvage Value]] - Giá trị thanh lý
- [[Setup Cost]] - Chi phí thiết lập
- [[Holding Cost]] - Chi phí lưu giữ
- [[Service Level]] - Mức phục vụ
- [[Normal Distribution]] - Phân phối chuẩn
