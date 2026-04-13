---
tags:
  - operations-management
  - constraints
  - scheduling
aliases:
  - DBR
  - Trống-Đệm-Dây
---

# Drum-Buffer-Rope

## Định nghĩa
**Drum-Buffer-Rope (Trống-Đệm-Dây)** là phương pháp điều độ sản xuất theo [[Theory of Constraints (TOC)]].

## Ba thành phần
1. **Drum (Trống)** — Nhịp sản xuất của bottleneck, quyết định throughput toàn hệ thống
2. **Buffer (Đệm)** — Tồn kho đệm trước bottleneck, đảm bảo bottleneck không bị đói hàng
3. **Rope (Dây)** — Tín hiệu kéo nguyên liệu vào hệ thống theo nhịp của Drum

## Giải thích
- Mục tiêu: bảo vệ bottleneck khỏi bị gián đoạn
- Toàn bộ hệ thống hoạt động theo nhịp của bottleneck (Drum)
- Rope kiểm soát input → tránh WIP quá tải ở các công đoạn trước bottleneck
- Kết hợp với 5 bước TOC để cải tiến liên tục

## Liên kết
- [[Theory of Constraints (TOC)]]
- [[Bottleneck]]
- [[WIP]]
- [[Lean Systems]]
