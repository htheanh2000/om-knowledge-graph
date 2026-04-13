---
tags: [key-concept, process-analysis, chapter-3]
aliases: [Little's Law, Định luật Little]
---
# Little's Law

## Định nghĩa (Definition)
**Little's Law** (Định luật Little) là công thức nền tảng trong phân tích quy trình:

$$L = \lambda \times W$$

## Giải thích (Explanation)
Trong đó:
- **L** = số đơn vị trung bình trong hệ thống (WIP - Work in Process)
- **lambda** = tốc độ đến trung bình (throughput rate)
- **W** = thời gian trung bình một đơn vị ở trong hệ thống (flow time)

Ví dụ: Quán cà phê có trung bình 10 khách (L), mỗi khách ở 30 phút (W):
$$\lambda = \frac{L}{W} = \frac{10}{0.5\ giờ} = 20\ khách/giờ$$

Tính chất mạnh mẽ:
- Áp dụng cho **mọi hệ thống ổn định** (stable system)
- Không cần biết phân phối xác suất
- Kết nối 3 chỉ số quan trọng nhất của quy trình

Khi [[Utilization]] tăng gần 100%, W (thời gian chờ) tăng phi tuyến → [[Lead Time]] bị kéo dài.

## Mối liên hệ (Relationships)
- Liên quan: [[Process]], [[Bottleneck]], [[Utilization]]
- Ứng dụng: [[Capacity Planning]], [[Lean Systems]]
- Kết hợp: [[Theory of Constraints (TOC)]]
- Thuộc chương: Chapter 3 — Process Strategy
