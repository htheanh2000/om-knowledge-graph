---
tags: [key-concept, inventory, chapter-12]
aliases: [Service Level, Mức phục vụ, Cycle-Service Level, CSL]
---
# Service Level

## Định nghĩa (Definition)
**Service Level** (Mức phục vụ) là **xác suất không bị thiếu hàng** (stockout) trong một chu kỳ bổ sung tồn kho.

## Giải thích (Explanation)
Service Level = 95% nghĩa là: trong 100 chu kỳ đặt hàng, có **95 chu kỳ không bị hết hàng**.

Service Level quyết định lượng [[Safety Stock]] cần giữ thông qua hệ số z:
| Service Level | z |
|---|---|
| 90% | 1.28 |
| 95% | 1.65 |
| 99% | 2.33 |

$$Safety\ Stock = z \times \sigma_d \times \sqrt{L}$$

Trade-off: Service Level càng cao → [[Safety Stock]] càng lớn → [[Holding Cost]] càng cao. Cần cân bằng dựa trên [[ABC Analysis]] và chiến lược kinh doanh.

## Mối liên hệ (Relationships)
- Quyết định: [[Safety Stock]], [[Reorder Point]]
- Chi phí: [[Holding Cost]]
- Phân loại: [[ABC Analysis]]
- Hệ thống: [[Continuous Review System (Q System)]], [[Periodic Review System (P System)]]
- Thuộc chương: Chapter 12 — Inventory Management
