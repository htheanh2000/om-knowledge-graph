---
tags: [key-concept, chapter-6, capacity-constraints]
aliases: [Theory of Constraints, TOC, Lý thuyết ràng buộc, Lý thuyết giới hạn]
---
# Theory of Constraints (TOC)

## Định nghĩa (Definition)
**Theory of Constraints (TOC)** (Lý thuyết ràng buộc) là phương pháp quản lý do Eliyahu Goldratt phát triển, tập trung vào việc **xác định và quản lý [[Bottleneck|nút thắt cổ chai]]** — ràng buộc (constraint) giới hạn hiệu suất của toàn hệ thống — thông qua **5 bước tập trung (5 Focusing Steps)**.

## Giải thích chi tiết (Detailed Explanation)

### Triết lý cốt lõi:
> "Một chuỗi chỉ mạnh bằng mắt xích yếu nhất."

Thay vì cố cải tiến mọi thứ cùng lúc (tốn nguồn lực), TOC tập trung **100% nỗ lực vào ràng buộc** — nơi mang lại hiệu quả lớn nhất.

### 5 Focusing Steps (5 Bước Tập Trung):

#### Bước 1: IDENTIFY (Xác định ràng buộc)
- Tìm ra [[Bottleneck]] — công đoạn/nguồn lực hạn chế sản lượng
- Dấu hiệu: WIP tích tụ trước đó, luôn chạy 100%, các công đoạn khác phải chờ

#### Bước 2: EXPLOIT (Khai thác tối đa ràng buộc)
- Đảm bảo ràng buộc **không bao giờ lãng phí** — luôn hoạt động, không dừng
- Không cho phép ràng buộc nghỉ (bố trí ăn ca tại chỗ), giảm setup time, loại bỏ sản phẩm lỗi trước khi đến ràng buộc

#### Bước 3: SUBORDINATE (Đồng bộ mọi thứ khác theo ràng buộc)
- Các công đoạn khác **phục vụ** cho ràng buộc
- Không sản xuất nhanh hơn ràng buộc (tránh tạo WIP thừa)
- Drum-Buffer-Rope: Ràng buộc là "trống" (drum) đặt nhịp cho cả hệ thống

#### Bước 4: ELEVATE (Nâng cao năng lực ràng buộc)
- Đầu tư để tăng [[Capacity]] tại ràng buộc: thêm máy, thêm ca, nâng cấp công nghệ
- Chỉ thực hiện nếu bước 2 và 3 chưa đủ

#### Bước 5: REPEAT (Lặp lại)
- Sau khi ràng buộc cũ được giải quyết → ràng buộc MỚI xuất hiện ở nơi khác
- Quay lại bước 1 → Chu trình [[Continuous Improvement|cải tiến liên tục]]
- **Đừng để quán tính (inertia)** trở thành ràng buộc — luôn sẵn sàng thay đổi

### TOC vs Lean vs Six Sigma:
| | TOC | [[Lean Systems\|Lean]] | [[Six Sigma]] |
|---|---|---|---|
| Tập trung | Ràng buộc | Lãng phí | Biến thiên |
| Câu hỏi | "Cái gì cản trở?" | "Cái gì lãng phí?" | "Cái gì biến thiên?" |
| Cách tiếp cận | 5 Focusing Steps | 7 Wastes elimination | DMAIC |

## Ví dụ thực tế (Real-world Example)
**Nhà hàng lẩu vào tối thứ 7:**
1. **IDENTIFY:** Bếp chỉ nấu được 20 nồi lẩu/giờ, nhưng phòng có 30 bàn → Bếp là ràng buộc
2. **EXPLOIT:** Chuẩn bị nguyên liệu sẵn, nấu nước dùng trước → bếp không phải chờ
3. **SUBORDINATE:** Nhân viên phục vụ gọi món theo tốc độ bếp, không nhận quá 20 order/giờ
4. **ELEVATE:** Mua thêm 1 bếp + thuê thêm đầu bếp → nấu 35 nồi/giờ
5. **REPEAT:** Giờ bếp nhanh rồi, nhưng phòng chỉ 30 bàn → ràng buộc mới là số bàn!

**Sách "The Goal" (Mục tiêu) — Eliyahu Goldratt:**
Cuốn tiểu thuyết kinh doanh nổi tiếng giải thích TOC qua câu chuyện cứu nhà máy sắp đóng cửa. Rất nên đọc!

## Mối liên hệ (Relationships)
- Xử lý: [[Bottleneck]]
- Ảnh hưởng: [[Capacity]] (tối ưu sử dụng)
- So sánh với: [[Lean Systems]], [[Six Sigma]]
- Liên quan: [[Continuous Improvement]] (bước 5 — lặp lại)
- Thuộc chương: Chapter 6 — Capacity Planning

## Công thức (Formula)
**Throughput Accounting (Kế toán thông lượng) — TOC approach:**
- **Throughput (T)** = Doanh thu - Chi phí nguyên vật liệu trực tiếp
- **Operating Expense (OE)** = Tất cả chi phí khác
- **Net Profit** = T - OE
- **ROI** = (T - OE) / Investment

→ TOC tập trung **tăng Throughput** (qua ràng buộc) thay vì chỉ **giảm chi phí**.
