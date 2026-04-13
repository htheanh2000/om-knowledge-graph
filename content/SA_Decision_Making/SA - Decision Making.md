---
tags: [supplement-A, decision-making, quantitative-methods, break-even, decision-theory]
aliases: [Ra quyết định, Decision Making, Supplement A, Phụ lục A]
---
# Supplement A - Decision Making

## Tổng quan (Overview)

Phụ lục A cung cấp các công cụ định lượng hỗ trợ ra quyết định trong [[Operations Management]]. Đây là những công cụ toán học cơ bản nhưng cực kỳ hữu ích mà nhà quản lý vận hành sử dụng hàng ngày. Từ việc quyết định nên sản xuất hay thuê ngoài, nên đầu tư máy mới hay không, cho đến việc lựa chọn giữa nhiều phương án kinh doanh.

Các công cụ chính bao gồm: [[Break-Even Analysis]] (phân tích hòa vốn), [[Preference Matrix]] (ma trận ưu tiên), [[Decision Theory]] (lý thuyết quyết định), và [[Decision Tree]] (cây quyết định). Mỗi công cụ phù hợp với một loại quyết định khác nhau tùy thuộc vào mức độ thông tin và rủi ro.

Hiểu các công cụ này giúp bạn ra quyết định dựa trên dữ liệu thay vì cảm tính, giảm thiểu rủi ro và tối ưu hóa kết quả kinh doanh.

---

## Break-Even Analysis (Phân tích hòa vốn)

### Định nghĩa (Definition)
[[Break-Even Analysis]] là phương pháp xác định điểm mà tại đó tổng doanh thu bằng tổng chi phí, tức là doanh nghiệp không lãi không lỗ. Điểm này gọi là [[Break-Even Point]] (điểm hòa vốn).

### Giải thích chi tiết

Phân tích hòa vốn dựa trên ba yếu tố:
- **[[Fixed Cost]] (F)** - Chi phí cố định: Chi phí không đổi dù sản xuất bao nhiêu. Ví dụ: tiền thuê nhà xưởng, lương quản lý, khấu hao máy móc.
- **[[Variable Cost]] (c)** - Chi phí biến đổi: Chi phí thay đổi theo sản lượng. Ví dụ: nguyên vật liệu, lương công nhân theo sản phẩm, điện sản xuất.
- **[[Revenue]] (p)** - Doanh thu trên mỗi đơn vị sản phẩm (giá bán).

### Công thức

$$Q_{BEP} = \frac{F}{p - c}$$

Trong đó:
- $Q_{BEP}$ = Sản lượng hòa vốn (Break-Even Quantity)
- $F$ = Tổng [[Fixed Cost|chi phí cố định]]
- $p$ = Giá bán mỗi đơn vị ([[Price]])
- $c$ = [[Variable Cost|Chi phí biến đổi]] mỗi đơn vị

**Lợi nhuận/Lỗ:**
$$\text{Profit (or Loss)} = pQ - (F + cQ) = (p - c)Q - F$$

Trong đó $Q$ là sản lượng thực tế.

### Ví dụ thực tế
Bạn mở quán trà sữa:
- Chi phí cố định (F): 30 triệu VNĐ/tháng (thuê mặt bằng, lương nhân viên cố định)
- Chi phí biến đổi (c): 15.000 VNĐ/ly (trà, sữa, topping, ly nhựa)
- Giá bán (p): 40.000 VNĐ/ly

$$Q_{BEP} = \frac{30.000.000}{40.000 - 15.000} = \frac{30.000.000}{25.000} = 1.200 \text{ ly/tháng}$$

Vậy bạn cần bán ít nhất **1.200 ly/tháng** (khoảng 40 ly/ngày) để hòa vốn. Bán hơn 1.200 ly thì có lãi, dưới 1.200 ly thì lỗ.

### Liên kết
- [[Fixed Cost]]
- [[Variable Cost]]
- [[Contribution Margin]]
- [[Make-or-Buy Decision]]
- [[CH05 - Capacity Planning]]

---

## Preference Matrix (Ma trận ưu tiên)

### Định nghĩa (Definition)
[[Preference Matrix]] là công cụ đánh giá và so sánh nhiều phương án dựa trên nhiều tiêu chí khác nhau, mỗi tiêu chí có trọng số (weight) phản ánh mức độ quan trọng.

### Giải thích chi tiết

Các bước thực hiện:
1. **Liệt kê các tiêu chí** đánh giá (criteria)
2. **Gán trọng số** cho mỗi tiêu chí (tổng = 1.0 hoặc 100%)
3. **Chấm điểm** mỗi phương án theo từng tiêu chí (ví dụ: thang 1-10)
4. **Tính điểm có trọng số**: Weighted Score = Weight × Score
5. **Tổng hợp**: Phương án có tổng điểm cao nhất được chọn

$$\text{Total Weighted Score} = \sum_{i=1}^{n} w_i \times s_i$$

Trong đó $w_i$ là trọng số tiêu chí $i$ và $s_i$ là điểm của phương án theo tiêu chí $i$.

### Ví dụ thực tế
Chọn địa điểm mở cửa hàng giữa 2 vị trí:

| Tiêu chí | Trọng số | Vị trí A (điểm) | Vị trí B (điểm) |
|-----------|----------|-----------------|-----------------|
| Giá thuê | 0.30 | 8 | 5 |
| Lưu lượng người | 0.35 | 6 | 9 |
| Đỗ xe | 0.15 | 7 | 4 |
| Đối thủ gần | 0.20 | 5 | 7 |

- **Vị trí A**: 0.30(8) + 0.35(6) + 0.15(7) + 0.20(5) = 2.4 + 2.1 + 1.05 + 1.0 = **6.55**
- **Vị trí B**: 0.30(5) + 0.35(9) + 0.15(4) + 0.20(7) = 1.5 + 3.15 + 0.6 + 1.4 = **6.65**

→ Vị trí B thắng với điểm cao hơn (6.65 > 6.55)

### Liên kết
- [[Weighted Scoring Model]]
- [[Multi-Criteria Decision Analysis]]
- [[Operations Strategy]]

---

## Decision Theory (Lý thuyết quyết định)

### Định nghĩa (Definition)
[[Decision Theory]] là phương pháp có hệ thống để phân tích và lựa chọn giữa các phương án khi kết quả phụ thuộc vào các yếu tố không chắc chắn (gọi là [[State of Nature]] - trạng thái tự nhiên).

### Giải thích chi tiết

Có ba tình huống ra quyết định tùy thuộc vào mức độ thông tin:

#### 1. Decision Making Under Certainty (Ra quyết định trong điều kiện chắc chắn)
[[Decision Under Certainty]]: Biết chắc điều gì sẽ xảy ra. Chỉ cần chọn phương án có kết quả tốt nhất.
- Ví dụ: Biết chắc nhu cầu là 1.000 sản phẩm/tháng → Chọn phương án sản xuất chi phí thấp nhất cho 1.000 sản phẩm.

#### 2. Decision Making Under Uncertainty (Ra quyết định trong điều kiện không chắc chắn)
[[Decision Under Uncertainty]]: Không biết xác suất của các trạng thái tự nhiên. Có nhiều quy tắc:

- **[[Maximin]]** (Bi quan / Pessimistic): Chọn phương án có kết quả xấu nhất TỐT NHẤT. Tư duy: "Giả sử điều tệ nhất xảy ra, tôi vẫn muốn kết quả tốt nhất có thể."
- **[[Maximax]]** (Lạc quan / Optimistic): Chọn phương án có kết quả tốt nhất CAO NHẤT. Tư duy: "Tôi tin vào điều tốt nhất sẽ xảy ra."
- **[[Laplace]]** (Trung bình): Giả sử mỗi trạng thái có xác suất bằng nhau, chọn phương án có giá trị kỳ vọng cao nhất.
- **[[Minimax Regret]]**: Chọn phương án có mức "hối tiếc" (regret/opportunity loss) tối đa nhỏ nhất.

#### 3. Decision Making Under Risk (Ra quyết định trong điều kiện rủi ro)
[[Decision Under Risk]]: Biết xác suất của mỗi trạng thái tự nhiên. Sử dụng [[Expected Value]] (giá trị kỳ vọng):

$$EV = \sum_{j=1}^{n} p_j \times V_j$$

Trong đó $p_j$ là xác suất trạng thái $j$ và $V_j$ là giá trị kết quả trong trạng thái $j$.

### Ví dụ thực tế
Bạn đang quyết định có nên mở quán ăn lớn hay nhỏ:

| Phương án | Nhu cầu cao (p=0.6) | Nhu cầu thấp (p=0.4) |
|-----------|---------------------|----------------------|
| Quán lớn | 500 triệu | -200 triệu |
| Quán nhỏ | 200 triệu | 100 triệu |

- **EV(Quán lớn)** = 0.6(500) + 0.4(-200) = 300 - 80 = **220 triệu**
- **EV(Quán nhỏ)** = 0.6(200) + 0.4(100) = 120 + 40 = **160 triệu**
- **Maximin**: Quán nhỏ (min = 100 triệu > min quán lớn = -200 triệu)
- **Maximax**: Quán lớn (max = 500 triệu)
- **Expected Value**: Quán lớn (220 > 160 triệu)

### Liên kết
- [[Payoff Table]]
- [[Expected Value]]
- [[Decision Tree]]
- [[Risk Management]]

---

## Decision Trees (Cây quyết định)

### Định nghĩa (Definition)
[[Decision Tree]] là sơ đồ hình cây biểu diễn các quyết định tuần tự, các sự kiện ngẫu nhiên, và kết quả tương ứng. Đặc biệt hữu ích khi có nhiều quyết định phải đưa ra theo trình tự.

### Giải thích chi tiết

Các thành phần:
- **□ Decision Node** (Nút quyết định - hình vuông): Điểm bạn phải chọn giữa các phương án
- **○ Chance Node** (Nút cơ hội - hình tròn): Điểm xảy ra sự kiện ngẫu nhiên với xác suất
- **Branches** (Nhánh): Các phương án hoặc kết quả có thể xảy ra
- **Payoff** (Kết quả): Giá trị tại cuối mỗi nhánh

**Cách giải - Phương pháp lùi ([[Rollback Method]]):**
1. Bắt đầu từ bên PHẢI (kết quả cuối cùng)
2. Tại **nút cơ hội** (○): Tính [[Expected Value]] = Σ(xác suất × kết quả)
3. Tại **nút quyết định** (□): Chọn nhánh có giá trị cao nhất (nếu tối đa hóa) hoặc thấp nhất (nếu tối thiểu hóa)
4. Tiếp tục lùi về bên TRÁI đến nút gốc

### Ví dụ thực tế
Công ty phần mềm quyết định: phát triển App A hoặc App B?
- Sau khi phát triển, mỗi app có thể thành công (60%) hoặc thất bại (40%)
- Nếu App A thành công: lãi 2 tỷ; thất bại: lỗ 500 triệu
- Nếu App B thành công: lãi 1.5 tỷ; thất bại: lãi 200 triệu

```
          Thành công (0.6) → +2.000 triệu
□ → App A ─○
          Thất bại (0.4)  → -500 triệu
          
          Thành công (0.6) → +1.500 triệu
    App B ─○
          Thất bại (0.4)  → +200 triệu
```

- **EV(App A)** = 0.6(2.000) + 0.4(-500) = 1.200 - 200 = **1.000 triệu**
- **EV(App B)** = 0.6(1.500) + 0.4(200) = 900 + 80 = **980 triệu**

→ Chọn App A (EV = 1.000 triệu > 980 triệu)

Tuy nhiên nếu bạn sợ rủi ro ([[Risk-Averse]]), có thể chọn App B vì kết quả xấu nhất vẫn lãi 200 triệu thay vì lỗ 500 triệu.

### Liên kết
- [[Expected Value]]
- [[Decision Theory]]
- [[Risk Management]]
- [[CH05 - Capacity Planning]]
- [[CH07 - Project Management]]

---

## Expected Value Calculations (Tính giá trị kỳ vọng)

### Định nghĩa (Definition)
[[Expected Value]] (EV - Giá trị kỳ vọng) là giá trị trung bình có trọng số của tất cả kết quả có thể, với trọng số là xác suất xảy ra.

### Công thức

$$EV = \sum_{j=1}^{n} p_j \times V_j$$

**Các khái niệm liên quan:**

- **[[Expected Value of Perfect Information]] (EVPI)**: Giá trị tối đa bạn sẵn sàng trả để biết chắc điều gì sẽ xảy ra.

$$EVPI = EV_{\text{with perfect info}} - EV_{\text{best alternative without info}}$$

- **[[Expected Value of Sample Information]] (EVSI)**: Giá trị của thông tin không hoàn hảo (ví dụ: khảo sát thị trường).

### Ví dụ thực tế
Tiếp tục ví dụ quán ăn:
- EV tốt nhất không có thông tin = 220 triệu (Quán lớn)
- Nếu biết chắc nhu cầu cao → chọn Quán lớn: 500 triệu
- Nếu biết chắc nhu cầu thấp → chọn Quán nhỏ: 100 triệu
- EV với thông tin hoàn hảo = 0.6(500) + 0.4(100) = 300 + 40 = 340 triệu

$$EVPI = 340 - 220 = 120 \text{ triệu VNĐ}$$

→ Bạn sẵn sàng trả tối đa **120 triệu** cho nghiên cứu thị trường hoàn hảo.

### Liên kết
- [[Decision Tree]]
- [[Decision Theory]]
- [[Probability]]
- [[Risk Analysis]]

---

## Công thức quan trọng (Key Formulas)

| Công cụ | Công thức | Khi nào dùng |
|---------|-----------|-------------|
| [[Break-Even Point]] | $Q = \frac{F}{p-c}$ | Xác định sản lượng cần bán để hòa vốn |
| [[Profit]] | $(p-c)Q - F$ | Tính lãi/lỗ tại sản lượng Q |
| [[Expected Value]] | $\sum p_j \times V_j$ | Ra quyết định khi biết xác suất |
| [[Preference Matrix]] | $\sum w_i \times s_i$ | So sánh nhiều phương án, nhiều tiêu chí |
| [[EVPI]] | $EV_{perfect} - EV_{best}$ | Đánh giá giá trị của thông tin hoàn hảo |

---

## Từ khóa chính (Key Terms)

- [[Break-Even Analysis]] - Phân tích hòa vốn
- [[Break-Even Point]] - Điểm hòa vốn
- [[Fixed Cost]] - Chi phí cố định
- [[Variable Cost]] - Chi phí biến đổi
- [[Contribution Margin]] - Biên đóng góp (p - c)
- [[Preference Matrix]] - Ma trận ưu tiên
- [[Decision Theory]] - Lý thuyết quyết định
- [[Decision Under Certainty]] - Quyết định trong chắc chắn
- [[Decision Under Uncertainty]] - Quyết định trong không chắc chắn
- [[Decision Under Risk]] - Quyết định trong rủi ro
- [[Maximin]] - Tiêu chí bi quan
- [[Maximax]] - Tiêu chí lạc quan
- [[Laplace]] - Tiêu chí trung bình
- [[Minimax Regret]] - Tiêu chí hối tiếc tối thiểu
- [[Expected Value]] - Giá trị kỳ vọng
- [[Decision Tree]] - Cây quyết định
- [[Rollback Method]] - Phương pháp lùi
- [[EVPI]] - Giá trị thông tin hoàn hảo
- [[Payoff Table]] - Bảng kết quả
- [[State of Nature]] - Trạng thái tự nhiên

---

> **Ghi chú ôn tập**: Supplement A là công cụ được sử dụng xuyên suốt khóa học. Break-Even Analysis xuất hiện lại trong [[CH05 - Capacity Planning]], Decision Trees trong [[CH07 - Project Management]]. Hãy thành thạo các công thức này!
