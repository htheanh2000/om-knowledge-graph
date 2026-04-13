---
tags:
  - operations-management
  - queuing-theory
  - service
aliases:
  - Mô hình 1 server
  - M/M/1
---

# Single-Server Model

## Định nghĩa
**Mô hình 1 server (M/M/1)** là mô hình hàng đợi cơ bản với 1 server, arrival theo Poisson, service theo Exponential.

## Công thức chính
- Hệ số sử dụng: $\rho = \lambda / \mu$
- Số khách trung bình trong hệ thống: $L = \lambda / (\mu - \lambda)$
- Thời gian trung bình trong hệ thống: $W = 1 / (\mu - \lambda)$
- Số khách trung bình trong hàng đợi: $L_q = \rho^2 / (1 - \rho)$
- Thời gian trung bình chờ: $W_q = \rho / (\mu - \lambda)$

## Giải thích
- $\lambda$ = tốc độ đến, $\mu$ = tốc độ phục vụ
- Điều kiện ổn định: $\rho < 1$ (nếu không, hàng đợi tăng vô hạn)
- Khi $\rho$ tiến gần 1, thời gian chờ tăng phi tuyến rất nhanh

## Liên kết
- [[Waiting-Line Models]]
- [[Capacity]]
- [[Cycle Time]]
