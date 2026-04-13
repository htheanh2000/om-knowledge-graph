---
tags: [supplement-D, part3, linear-programming, optimization, LP, simplex, transportation-method]
aliases: [Quy hoạch tuyến tính, Linear Programming, LP, Tối ưu hóa tuyến tính]
---
# Supplement D - Linear Programming (Quy hoạch tuyến tính)

## Tổng quan (Overview)

[[Linear Programming]] (LP - Quy hoạch tuyến tính) là một phương pháp toán học mạnh mẽ để tìm **phương án tối ưu** (maximize hoặc minimize) một hàm mục tiêu tuyến tính, tuân theo một tập hợp các ràng buộc tuyến tính. Đây là công cụ quan trọng nhất trong [[Operations Management]] để giải các bài toán phân bổ nguồn lực, lập kế hoạch sản xuất, và vận chuyển.

LP được ứng dụng rộng rãi: từ [[S&OP - Sales and Operations Planning]] (lập kế hoạch sản xuất tối ưu chi phí), [[Supply Chain Management]] (phân bổ vận chuyển), [[Workforce Scheduling]] (lập lịch nhân viên), đến [[Product Mix]] (xác định sản phẩm nào sản xuất bao nhiêu). Phần mềm như Excel Solver, LINGO, CPLEX có thể giải hàng triệu biến và ràng buộc.

Supplement này bắt đầu từ cách nhận diện và xây dựng mô hình LP, giải bằng phương pháp đồ thị ([[Graphic Analysis]]) cho bài 2 biến, rồi giới thiệu [[Simplex Method]] cho bài toán lớn và [[Transportation Method]] cho bài toán vận chuyển.

---

## Characteristics of LP Models (Đặc điểm của mô hình LP)

### Định nghĩa (Definition)
Một bài toán [[Linear Programming]] phải có đầy đủ các đặc điểm sau:

### Giải thích chi tiết (Detailed Explanation)

1. **[[Objective Function]]** (Hàm mục tiêu): Một phương trình tuyến tính cần **maximize** (tối đa hóa lợi nhuận) hoặc **minimize** (tối thiểu hóa chi phí).
   - Ví dụ: Max Z = 5x₁ + 8x₂ (tối đa hóa lợi nhuận)

2. **[[Decision Variables]]** (Biến quyết định): Các đại lượng cần tìm, đại diện cho quyết định.
   - Ví dụ: x₁ = số sản phẩm A, x₂ = số sản phẩm B sản xuất

3. **[[Constraints]]** (Ràng buộc): Các giới hạn tuyến tính về nguồn lực.
   - Ví dụ: 2x₁ + 3x₂ ≤ 120 (giới hạn giờ lao động)

4. **[[Non-negativity Constraints]]** (Ràng buộc không âm): x₁ ≥ 0, x₂ ≥ 0

5. **Tính tuyến tính** ([[Linearity]]): Tất cả quan hệ đều tuyến tính (không có x², xy, sin(x)...)

6. **Tính xác định** ([[Certainty]]): Tất cả hệ số là hằng số đã biết

7. **Tính liên tục** ([[Divisibility]]): Biến có thể nhận giá trị thập phân (nếu phải nguyên → [[Integer Programming]])

8. **Tính cộng** ([[Additivity]]): Tổng đóng góp = tổng từng phần riêng lẻ

### Ví dụ thực tế (Real-world Example)
Vietnam Airlines muốn xác định [[Product Mix]] tối ưu: bao nhiêu ghế Economy (x₁) và Business (x₂) trên mỗi chuyến bay để tối đa doanh thu, với ràng buộc về số ghế, trọng lượng, và nhu cầu tối thiểu mỗi hạng.

### Liên kết (Related Concepts)
- [[Optimization]]
- [[Operations Research]]
- [[Integer Programming]]
- [[Decision Analysis]]

---

## Formulating an LP Model (Xây dựng mô hình LP)

### Định nghĩa (Definition)
Quy trình 4 bước để chuyển bài toán thực tế thành mô hình [[Linear Programming]] toán học.

### Giải thích chi tiết (Detailed Explanation)

#### Bước 1: Xác định [[Decision Variables]] (Biến quyết định)
- Hỏi: "Cần quyết định cái gì?"
- Đặt tên: x₁, x₂, ... hoặc tên có ý nghĩa

#### Bước 2: Viết [[Objective Function]] (Hàm mục tiêu)
- Max hay Min?
- Z = c₁x₁ + c₂x₂ + ... + cₙxₙ

#### Bước 3: Viết [[Constraints]] (Ràng buộc)
- Mỗi nguồn lực giới hạn → 1 ràng buộc
- Dạng: a₁x₁ + a₂x₂ ≤ b (hoặc ≥ hoặc =)

#### Bước 4: Thêm [[Non-negativity Constraints]]
- Tất cả biến ≥ 0

### Ví dụ thực tế (Real-world Example)

**Bài toán**: Xưởng mộc Bình Dương sản xuất 2 loại bàn:
- **Bàn A** (x₁): lợi nhuận 500K VND/cái, cần 4 giờ thợ mộc + 2 giờ sơn
- **Bàn B** (x₂): lợi nhuận 800K VND/cái, cần 3 giờ thợ mộc + 5 giờ sơn
- Thợ mộc: tối đa 120 giờ/tuần
- Thợ sơn: tối đa 100 giờ/tuần
- Gỗ: đủ cho tối đa 25 bàn A hoặc 20 bàn B (4x₁ + 5x₂ ≤ 100)

**Mô hình LP**:
```
Max Z = 500x₁ + 800x₂    (nghìn VND)

Ràng buộc:
4x₁ + 3x₂ ≤ 120          (giờ thợ mộc)
2x₁ + 5x₂ ≤ 100          (giờ thợ sơn)
4x₁ + 5x₂ ≤ 100          (gỗ)
x₁, x₂ ≥ 0               (không âm)
```

### Liên kết (Related Concepts)
- [[Decision Variables]]
- [[Objective Function]]
- [[Constraints]]
- [[Mathematical Modeling]]

---

## Graphic Analysis (Phân tích đồ thị)

### Định nghĩa (Definition)
[[Graphic Analysis]] (hay [[Graphical Method]]) giải bài LP 2 biến bằng cách vẽ đồ thị trên hệ trục tọa độ. Phương pháp này giúp hiểu trực quan các khái niệm LP.

### Giải thích chi tiết (Detailed Explanation)

#### Bước 1: Plot Constraints (Vẽ ràng buộc)

Mỗi ràng buộc là một đường thẳng trên mặt phẳng (x₁, x₂):
- Đổi bất đẳng thức thành đẳng thức
- Tìm 2 điểm (cho x₁=0 tìm x₂, cho x₂=0 tìm x₁)
- Nối 2 điểm thành đường thẳng
- Tô vùng thỏa mãn bất đẳng thức (≤ → phía dưới/trái đường)

**Ví dụ** (tiếp bài trên):
- 4x₁ + 3x₂ = 120: điểm (30, 0) và (0, 40)
- 2x₁ + 5x₂ = 100: điểm (50, 0) và (0, 20)
- 4x₁ + 5x₂ = 100: điểm (25, 0) và (0, 20)

#### Bước 2: Xác định [[Feasible Region]] (Vùng khả thi)

- [[Feasible Region]] = vùng giao nhau của TẤT CẢ các ràng buộc
- Mọi điểm trong vùng này đều thỏa mãn tất cả ràng buộc
- Vùng khả thi luôn là **đa giác lồi** ([[Convex Polygon]])

#### Bước 3: Vẽ [[Objective Function]] (Hàm mục tiêu)

- Vẽ đường Z = constant (ví dụ Z = 5.000, Z = 10.000...)
- Các đường Z song song nhau (cùng hệ số góc)
- Di chuyển đường Z theo hướng tăng Z (max) hoặc giảm Z (min)

#### Bước 4: Tìm [[Optimal Solution]] (Nghiệm tối ưu)

**[[Corner Point Theorem]]**: Nghiệm tối ưu luôn nằm tại một **đỉnh** (corner point / vertex) của [[Feasible Region]].

Cách tìm:
- **Phương pháp trực quan**: Di chuyển đường Z đến vị trí xa nhất còn chạm vùng khả thi
- **Phương pháp đại số**: Tính giá trị Z tại tất cả đỉnh, chọn lớn nhất (max) hoặc nhỏ nhất (min)

### Ví dụ thực tế (Real-world Example)

Tiếp bài xưởng mộc, các đỉnh vùng khả thi (tính bằng cách giải hệ phương trình):
- A(0, 0): Z = 0
- B(25, 0): Z = 500(25) = 12.500
- C(?, ?): Giao 4x₁+3x₂=120 và 4x₁+5x₂=100 → Giải hệ → (giả sử) C(20, 13.33): Z = 500(20)+800(13.33) = 20.667
- D(0, 20): Z = 800(20) = 16.000

→ Nghiệm tối ưu: Điểm C → sản xuất khoảng 20 bàn A và 13 bàn B, lợi nhuận tối đa ≈ **20.667K VND/tuần**.

### Liên kết (Related Concepts)
- [[Feasible Region]]
- [[Optimal Solution]]
- [[Corner Point Theorem]]
- [[Objective Function]]

---

## Slack and Surplus Variables (Biến bù và biến dư)

### Định nghĩa (Definition)
[[Slack Variable]] và [[Surplus Variable]] chuyển bất đẳng thức thành đẳng thức, giúp giải LP bằng đại số.

### Giải thích chi tiết (Detailed Explanation)

#### [[Slack Variable]] (Biến bù) -- cho ràng buộc ≤:
$$4x_1 + 3x_2 \leq 120 \quad \Rightarrow \quad 4x_1 + 3x_2 + s_1 = 120 \quad (s_1 \geq 0)$$

- $s_1$ = nguồn lực **chưa dùng hết** (slack = dư thừa)
- Nếu $s_1 = 0$: ràng buộc **chặt** ([[Binding Constraint]]) -- dùng hết nguồn lực
- Nếu $s_1 > 0$: ràng buộc **không chặt** -- còn dư nguồn lực

#### [[Surplus Variable]] (Biến dư) -- cho ràng buộc ≥:
$$3x_1 + 2x_2 \geq 60 \quad \Rightarrow \quad 3x_1 + 2x_2 - s_2 = 60 \quad (s_2 \geq 0)$$

- $s_2$ = lượng **vượt quá** yêu cầu tối thiểu

#### Ý nghĩa thực tế:
- Ràng buộc thợ mộc: 4(20) + 3(13.33) = 120 → s₁ = 0 → dùng hết giờ thợ mộc ([[Binding Constraint]])
- Ràng buộc thợ sơn: 2(20) + 5(13.33) = 106.65 > 100 → Cần kiểm tra! Nếu s₂ = 0 thì cũng binding.

### Liên kết (Related Concepts)
- [[Binding Constraint]]
- [[Sensitivity Analysis]]
- [[Simplex Method]]

---

## Sensitivity Analysis (Phân tích độ nhạy)

### Định nghĩa (Definition)
[[Sensitivity Analysis]] (hay [[Post-Optimality Analysis]]) trả lời câu hỏi: "Nếu các tham số thay đổi, nghiệm tối ưu có thay đổi không?"

### Giải thích chi tiết (Detailed Explanation)

#### 1. Thay đổi hệ số hàm mục tiêu ([[Objective Function Coefficient Range]])

Hỏi: Lợi nhuận bàn A thay đổi trong khoảng nào mà nghiệm tối ưu không đổi?
- Có một **khoảng cho phép** (allowable increase/decrease)
- Trong khoảng này: nghiệm tối ưu (x₁*, x₂*) giữ nguyên, chỉ Z thay đổi
- Ngoài khoảng: nghiệm tối ưu nhảy sang đỉnh khác

**Ví dụ**: Nếu lợi nhuận bàn A hiện = 500K, khoảng cho phép là [300K, 900K]:
- Nếu tăng lên 700K → vẫn sản xuất 20 bàn A, 13 bàn B, Z tăng
- Nếu tăng lên 1.000K → nghiệm tối ưu thay đổi (sản xuất nhiều bàn A hơn)

#### 2. Thay đổi vế phải ràng buộc ([[Right-Hand Side Range]])

Hỏi: Nếu có thêm giờ thợ mộc, Z tăng bao nhiêu?

**[[Shadow Price]]** (Giá bóng / Giá ẩn / [[Dual Price]]):
- = Giá trị biên của 1 đơn vị nguồn lực thêm
- Chỉ áp dụng cho [[Binding Constraint]]
- Ràng buộc không binding: shadow price = 0 (thêm nguồn lực cũng vô ích)

**Ví dụ**: Shadow price của giờ thợ mộc = 150K VND:
- Nghĩa là mỗi giờ thợ mộc thêm vào → Z tăng 150K
- Nếu thuê thêm thợ mộc giá 120K/giờ → **nên thuê** (lãi 30K/giờ)
- Nếu giá 180K/giờ → **không nên** (lỗ 30K/giờ)

#### 3. Ràng buộc mới

Thêm ràng buộc mới:
- Nếu nghiệm tối ưu hiện tại thỏa mãn → không thay đổi gì
- Nếu không thỏa mãn → cần giải lại

### Ví dụ thực tế (Real-world Example)
Giám đốc xưởng mộc hỏi: "Nếu thuê thêm thợ mộc part-time (thêm 10 giờ/tuần, giá 130K/giờ), có nên không?" → Kiểm tra shadow price: nếu > 130K → nên thuê.

### Liên kết (Related Concepts)
- [[Shadow Price]]
- [[Binding Constraint]]
- [[Optimal Solution]]
- [[Decision Making]]

---

## Simplex Method (Phương pháp Simplex)

### Định nghĩa (Definition)
[[Simplex Method]] là thuật toán chính để giải [[Linear Programming]] với nhiều biến (không thể vẽ đồ thị). Phát minh bởi George Dantzig (1947).

### Giải thích chi tiết (Detailed Explanation)

#### Ý tưởng cơ bản:
1. Bắt đầu từ một đỉnh khả thi (thường là gốc tọa độ)
2. Di chuyển sang đỉnh **kề** có giá trị Z tốt hơn
3. Lặp lại cho đến khi không thể cải thiện → đã đạt tối ưu

#### Trong thực tế:
- **Không cần giải bằng tay!** Dùng phần mềm:
  - **Excel Solver**: Miễn phí, đủ cho bài toán nhỏ-vừa
  - **LINGO/LINDO**: Chuyên dụng cho LP
  - **CPLEX/Gurobi**: Cho bài toán cực lớn (hàng triệu biến)
  - **Python**: thư viện `scipy.optimize.linprog` hoặc `PuLP`

#### Cách dùng Excel Solver:
1. Nhập mô hình vào bảng tính
2. Data → Solver
3. Set Objective: ô chứa Z
4. By Changing: ô chứa x₁, x₂, ...
5. Subject to Constraints: thêm từng ràng buộc
6. Chọn "Simplex LP"
7. Solve → kết quả + [[Sensitivity Analysis]] report

### Ví dụ thực tế (Real-world Example)
Vietnam Airlines dùng LP (giải bằng CPLEX) để tối ưu lịch bay hàng ngày với hàng nghìn biến (số chuyến mỗi tuyến, loại máy bay, phi hành đoàn) và hàng nghìn ràng buộc (số máy bay có sẵn, thời gian bảo trì, quy định hàng không). Không thể giải bằng tay hay đồ thị -- cần [[Simplex Method]] trên máy tính.

### Liên kết (Related Concepts)
- [[Linear Programming]]
- [[Feasible Region]]
- [[Corner Point Theorem]]
- [[Sensitivity Analysis]]
- [[Integer Programming]]

---

## Transportation Method (Phương pháp vận tải)

### Định nghĩa (Definition)
[[Transportation Method]] (hay [[Transportation Problem]]) là dạng đặc biệt của [[Linear Programming]] để tìm cách phân bổ vận chuyển hàng hóa từ nhiều nguồn ([[Supply Points]]) đến nhiều đích ([[Demand Points]]) với **tổng chi phí vận chuyển thấp nhất**.

### Giải thích chi tiết (Detailed Explanation)

#### Cấu trúc bài toán:
- m nguồn cung (nhà máy, kho): có sản lượng $s_1, s_2, ..., s_m$
- n điểm cầu (cửa hàng, đại lý): có nhu cầu $d_1, d_2, ..., d_n$
- Chi phí vận chuyển $c_{ij}$ từ nguồn i đến đích j
- Biến quyết định: $x_{ij}$ = số lượng vận chuyển từ i đến j

#### Mô hình LP:
$$\text{Min } Z = \sum_i \sum_j c_{ij} x_{ij}$$

Ràng buộc cung: $\sum_j x_{ij} \leq s_i$ (mỗi nguồn không vượt sản lượng)
Ràng buộc cầu: $\sum_i x_{ij} \geq d_j$ (mỗi đích đủ nhu cầu)

#### Bảng Transportation:

|  | Đại lý HN | Đại lý ĐN | Đại lý HCM | Cung |
|--|----------|----------|-----------|------|
| **NM Hà Nội** | 10K | 25K | 40K | 500 |
| **NM Đà Nẵng** | 20K | 8K | 15K | 300 |
| **NM HCM** | 35K | 18K | 5K | 400 |
| **Cầu** | 350 | 250 | 600 | 1.200 |

(Chi phí tính VND/đơn vị vận chuyển)

#### Các phương pháp giải:

1. **[[Northwest Corner Method]]** (Phương pháp góc Tây Bắc):
   - Bắt đầu từ ô trên-trái
   - Phân bổ tối đa có thể
   - Di chuyển sang phải hoặc xuống
   - **Nhanh nhưng thường xa tối ưu** (chỉ dùng để tìm nghiệm ban đầu)

2. **[[Vogel's Approximation Method]]** (VAM):
   - Tính "penalty" = chênh lệch 2 chi phí thấp nhất cho mỗi hàng/cột
   - Phân bổ vào ô có chi phí thấp nhất ở hàng/cột có penalty cao nhất
   - **Cho nghiệm gần tối ưu hơn nhiều** so với Northwest Corner

3. **[[MODI Method]]** (Modified Distribution):
   - Kiểm tra tối ưu và cải thiện nghiệm
   - Lặp cho đến khi tối ưu

#### Trường hợp đặc biệt:
- **Tổng cung ≠ Tổng cầu** → thêm nguồn/đích giả ([[Dummy]]) với chi phí = 0
- **[[Degeneracy]]**: Khi có quá ít ô phân bổ → thêm ε vào ô trống

### Ví dụ thực tế (Real-world Example)

Vinamilk có 3 nhà máy (Hà Nội, Đà Nẵng, HCM) và cần phân phối sữa đến 5 trung tâm phân phối. Mỗi nhà máy có công suất khác nhau, mỗi trung tâm có nhu cầu khác nhau, chi phí vận chuyển khác nhau tùy khoảng cách. [[Transportation Method]] giúp tìm phương án vận chuyển tổng chi phí thấp nhất.

### Liên kết (Related Concepts)
- [[Linear Programming]]
- [[Supply Chain Management]]
- [[Facility Location]]
- [[Distribution Network]]
- [[Logistics]]

---

## Công thức quan trọng (Key Formulas)

| Công thức | Ký hiệu | Mô tả |
|-----------|----------|-------|
| Max/Min Z = $\sum c_j x_j$ | [[Objective Function]] | Hàm mục tiêu |
| $\sum a_{ij} x_j \leq b_i$ | [[Constraints]] | Ràng buộc |
| $x_j \geq 0$ | [[Non-negativity Constraints]] | Ràng buộc không âm |
| Shadow Price | [[Shadow Price]] | Giá trị biên của 1 đơn vị nguồn lực |
| Min Z = $\sum\sum c_{ij}x_{ij}$ | [[Transportation Problem]] | Bài toán vận tải |

---

## Từ khóa chính (Key Terms)

- [[Linear Programming]] - Quy hoạch tuyến tính
- [[Objective Function]] - Hàm mục tiêu
- [[Decision Variables]] - Biến quyết định
- [[Constraints]] - Ràng buộc
- [[Non-negativity Constraints]] - Ràng buộc không âm
- [[Feasible Region]] - Vùng khả thi
- [[Optimal Solution]] - Nghiệm tối ưu
- [[Corner Point Theorem]] - Định lý điểm góc
- [[Slack Variable]] - Biến bù
- [[Surplus Variable]] - Biến dư
- [[Binding Constraint]] - Ràng buộc chặt
- [[Shadow Price]] - Giá bóng / Giá ẩn
- [[Sensitivity Analysis]] - Phân tích độ nhạy
- [[Simplex Method]] - Phương pháp Simplex
- [[Transportation Method]] - Phương pháp vận tải
- [[Transportation Problem]] - Bài toán vận tải
- [[Northwest Corner Method]] - Phương pháp góc Tây Bắc
- [[Vogel's Approximation Method]] - Phương pháp xấp xỉ Vogel
- [[MODI Method]] - Phương pháp phân phối cải tiến
- [[Dummy]] - Nguồn/đích giả
- [[Integer Programming]] - Quy hoạch nguyên
- [[Product Mix]] - Hỗn hợp sản phẩm
