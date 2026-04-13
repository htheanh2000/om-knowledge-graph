---
tags: [key-concept, chapter-8, quality-improvement, lean]
aliases: [Kanban, Hệ thống kéo, Pull System, Hệ thống Kanban, Thẻ Kanban]
---
# Kanban

## Định nghĩa (Definition)
**Kanban** (看板 — "biển hiệu" trong tiếng Nhật) là hệ thống tín hiệu (thường dùng thẻ) để kiểm soát dòng chảy sản xuất theo nguyên tắc **kéo (pull)** — chỉ sản xuất khi có tín hiệu nhu cầu thực tế từ công đoạn sau.

## Giải thích chi tiết (Detailed Explanation)

### Push vs Pull System:

| Push System (Hệ thống đẩy) | Pull System (Hệ thống kéo — Kanban) |
|---|---|
| Sản xuất theo dự báo | Sản xuất theo nhu cầu thực |
| "Làm xong rồi đẩy đi" | "Chỉ làm khi được yêu cầu" |
| Tồn kho lớn | Tồn kho tối thiểu |
| Rủi ro hàng thừa | Giảm lãng phí |

### Cách hoạt động:
1. Công đoạn B dùng hết linh kiện trong container
2. Thẻ Kanban từ container rỗng được gửi về công đoạn A
3. Công đoạn A nhận thẻ → bắt đầu sản xuất đúng số lượng ghi trên thẻ
4. Khi hoàn thành → gắn thẻ Kanban vào container đầy → gửi đến B
5. **Không có thẻ = Không sản xuất!**

### Hai loại thẻ Kanban:
- **Production Kanban (Thẻ sản xuất):** Ra lệnh cho công đoạn trước sản xuất thêm
- **Withdrawal Kanban (Thẻ rút hàng):** Cho phép công đoạn sau lấy hàng từ kho

### Tính số container Kanban:
Số container cần thiết để duy trì dòng chảy liên tục giữa các công đoạn.

## Ví dụ thực tế (Real-world Example)
**Siêu thị — Nguồn cảm hứng ban đầu của Kanban:**
- Taiichi Ohno (Toyota) quan sát siêu thị Mỹ: khi kệ hàng vơi → nhân viên bổ sung
- Áp dụng cho sản xuất: khi container linh kiện hết → tín hiệu sản xuất thêm

**Kanban trong đời thường:**
- Bình nước uống văn phòng: Khi bình cuối cùng được lắp → gọi điện đặt thêm (tín hiệu kéo)
- Nếu không dùng Kanban: Đặt sẵn 100 bình → chiếm không gian, đọng tiền, nước hết hạn

**Kanban trong phần mềm (hiện đại):**
- Bảng Kanban: To Do → In Progress → Done
- Giới hạn WIP (Work In Progress): mỗi cột chỉ được có tối đa N task

## Mối liên hệ (Relationships)
- Thuộc về: [[Lean Systems]], [[Just-in-Time (JIT)]]
- Liên quan đến: [[Inventory]] (kiểm soát tồn kho)
- Hỗ trợ: [[Continuous Improvement]]
- Giảm thiểu: [[Bullwhip Effect]] (tín hiệu nhu cầu thực)
- Thuộc chương: Chapter 8 — Lean Systems

## Công thức (Formula)
**Số container Kanban cần thiết:**

$$k = \frac{d(w + p)(1 + c)}{n}$$

Trong đó:
- **k** = Số container (thẻ) Kanban
- **d** = Nhu cầu trung bình trong 1 đơn vị thời gian
- **w** = Thời gian chờ trung bình (waiting time)
- **p** = Thời gian xử lý trung bình (processing time)
- **c** = Hệ số an toàn (safety factor), phản ánh mức không chắc chắn (thường 0 đến 1)
- **n** = Số đơn vị trong mỗi container

**Ví dụ tính toán:**
- d = 200 đơn vị/ngày, w = 0.5 ngày, p = 0.25 ngày, c = 0.1, n = 50
- k = 200 × (0.5 + 0.25) × (1 + 0.1) / 50 = 200 × 0.75 × 1.1 / 50 = **3.3 → 4 container**
