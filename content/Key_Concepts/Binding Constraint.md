---
tags:
  - operations-management
  - linear-programming
  - optimization
aliases:
  - Ràng buộc chặt
  - Active Constraint
---

# Binding Constraint

## Định nghĩa
**Ràng buộc chặt (Binding Constraint)** là ràng buộc mà tại nghiệm tối ưu, nguồn lực được sử dụng hết hoàn toàn (slack = 0).

## Giải thích
- Slack = 0 nghĩa là ràng buộc đang "chặt", không còn dư thừa nguồn lực
- Ràng buộc không chặt (non-binding) có slack > 0 → còn nguồn lực dư
- Thêm nguồn lực cho binding constraint → có thể cải thiện hàm mục tiêu
- Giá trị thêm mỗi đơn vị nguồn lực = **shadow price** (dual value)

## Ứng dụng
- Xác định nguồn lực nào đang giới hạn lợi nhuận
- Hỗ trợ quyết định đầu tư mở rộng nguồn lực

## Liên kết
- [[Feasible Region]]
- [[Simplex Method]]
- [[Sensitivity Analysis]]
- [[Product Mix]]
- [[Bottleneck]]
