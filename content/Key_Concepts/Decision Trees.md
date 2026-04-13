---
tags: [key-concept, chapter-A, decision-tools]
aliases: [Decision Trees, Cây quyết định, Decision Tree Analysis, DTA]
---
# Decision Trees

## Định nghĩa (Definition)
**Decision Trees** (Cây quyết định) là công cụ ra quyết định dưới dạng **sơ đồ hình cây**, mô tả các **lựa chọn (decisions)**, **sự kiện không chắc chắn (events)**, và **kết quả (payoffs)**, giúp chọn phương án có **giá trị kỳ vọng (Expected Value)** tốt nhất.

## Giải thích chi tiết (Detailed Explanation)

### Các thành phần:

#### 1. Decision Node (Nút quyết định) — Hình vuông □
- Điểm mà **bạn phải chọn** giữa các phương án
- Bạn **kiểm soát** được lựa chọn

#### 2. Event/Chance Node (Nút sự kiện) — Hình tròn ○
- Điểm mà **tự nhiên/thị trường quyết định** → không kiểm soát được
- Mỗi nhánh có **xác suất** (probability) gắn kèm
- Tổng xác suất tại mỗi nút = 100%

#### 3. Branches (Nhánh) — Đường nối
- Nhánh từ □: Các lựa chọn (ví dụ: Mở rộng / Không mở rộng)
- Nhánh từ ○: Các kịch bản (ví dụ: Nhu cầu cao / thấp + xác suất)

#### 4. Payoff (Kết quả) — Giá trị cuối nhánh
- Lợi nhuận (hoặc chi phí) của mỗi kết quả cuối cùng

### Cách giải (Backward Induction — Tính ngược từ phải sang trái):
1. Bắt đầu từ **nhánh cuối** (payoffs)
2. Tại mỗi **○ (Event Node):** Tính Expected Value = Σ(Probability × Payoff)
3. Tại mỗi **□ (Decision Node):** Chọn nhánh có EV tốt nhất
4. Kết quả: Phương án tối ưu

### Ưu điểm so với [[Break-Even Analysis]]:
- Xử lý được **nhiều giai đoạn** quyết định (multi-stage)
- Xử lý được **rủi ro và không chắc chắn** (probability)
- Trực quan, dễ trình bày

## Ví dụ thực tế (Real-world Example)
**Quyết định mở rộng nhà máy:**

```
                            Nhu cầu cao (60%): +500 triệu
□ Mở rộng lớn ──── ○
  (đầu tư 200tr)       Nhu cầu thấp (40%): -100 triệu
                    
                            Nhu cầu cao (60%): +200 triệu
□ Mở rộng nhỏ ──── ○
  (đầu tư 50tr)         Nhu cầu thấp (40%): +50 triệu
                    
□ Không mở rộng ──── +0 triệu
```

**Tính toán:**
- **EV (Mở rộng lớn)** = 0.6 × 500 + 0.4 × (−100) − 200 = 300 − 40 − 200 = **60 triệu**
- **EV (Mở rộng nhỏ)** = 0.6 × 200 + 0.4 × 50 − 50 = 120 + 20 − 50 = **90 triệu**
- **EV (Không mở rộng)** = **0 triệu**

→ **Chọn: Mở rộng nhỏ** (EV = 90 triệu — cao nhất!)

**Giải thích cho người mới:**
Mở rộng lớn có thể lãi nhiều nhất (500tr) NHƯNG cũng có thể lỗ (−100tr), và chi phí đầu tư cao. Mở rộng nhỏ an toàn hơn: lúc nào cũng có lãi, EV tổng thể cao nhất.

## Mối liên hệ (Relationships)
- So sánh/bổ sung: [[Break-Even Analysis]] (BEA cho 1 kịch bản, DT cho nhiều kịch bản)
- Hỗ trợ quyết định: [[Capacity]], [[Operations Strategy]], [[Outsourcing]]
- Liên quan: [[Forecasting]] (ước tính xác suất)
- Thuộc chương: Supplement A — Decision Making

## Công thức (Formula)
**Expected Value (Giá trị kỳ vọng) tại Event Node:**
$$EV = \sum_{i=1}^{n} P_i \times Payoff_i$$

**Tại Decision Node:**
$$Chọn\ max(EV_1, EV_2, ..., EV_n)$$

Trong đó:
- $P_i$ = Xác suất của kịch bản i
- $Payoff_i$ = Kết quả (lợi nhuận/chi phí) của kịch bản i
- $\sum P_i = 1$ (tổng xác suất = 100%)
