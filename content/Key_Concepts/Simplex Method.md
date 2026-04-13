---
tags:
  - operations-management
  - linear-programming
  - optimization
aliases:
  - Phương pháp đơn hình
  - LP Algorithm
---

# Simplex Method

## Định nghĩa
**Phương pháp đơn hình (Simplex Method)** là thuật toán giải bài toán quy hoạch tuyến tính (LP) bằng cách di chuyển giữa các đỉnh của [[Feasible Region]].

## Giải thích
- Bắt đầu từ một đỉnh khả thi, di chuyển sang đỉnh lân cận có giá trị hàm mục tiêu tốt hơn
- Lặp lại cho đến khi không thể cải thiện → đạt nghiệm tối ưu
- Hiệu quả hơn phương pháp đồ thị khi có nhiều biến (>2)
- Phần mềm: Excel Solver, LINGO, CPLEX

## Đầu ra quan trọng
- Giá trị tối ưu của hàm mục tiêu
- Giá trị các biến quyết định
- Shadow price và [[Sensitivity Analysis]]

## Liên kết
- [[Feasible Region]]
- [[Binding Constraint]]
- [[Product Mix]]
- [[Sensitivity Analysis]]
