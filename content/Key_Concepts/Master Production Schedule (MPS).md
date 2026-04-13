---
tags: [key-concept, chapter-15, planning]
aliases: [Master Production Schedule, MPS, Lịch trình sản xuất chính, Kế hoạch sản xuất chính]
---
# Master Production Schedule (MPS)

## Định nghĩa (Definition)
**Master Production Schedule (MPS)** (Lịch trình sản xuất chính) là kế hoạch chi tiết xác định **sản phẩm cụ thể nào** sẽ được sản xuất, **số lượng bao nhiêu**, và **khi nào** trong từng tuần/giai đoạn, dựa trên kế hoạch tổng thể từ [[Sales and Operations Planning (S&OP)]].

## Giải thích chi tiết (Detailed Explanation)

### So sánh S&OP vs MPS:
| [[Sales and Operations Planning (S&OP)|S&OP]] | MPS |
|---|---|
| Trung hạn (3-18 tháng) | Ngắn hạn (tuần - vài tháng) |
| Mức tổng (product families) | Mức chi tiết (từng sản phẩm cụ thể) |
| "Sản xuất 10,000 áo/tháng" | "Tuần 1: 2000 áo đỏ size M, 1500 áo xanh size L..." |

### Vai trò của MPS:
- **Cầu nối** giữa S&OP (tổng thể) và [[Material Requirements Planning (MRP)]] (chi tiết linh kiện)
- Là **đầu vào chính** cho MRP
- Xác định những **cam kết giao hàng** cụ thể

### Các thành phần chính của MPS:

#### 1. Projected On-Hand Inventory (Tồn kho dự kiến)
- Dự báo tồn kho cuối mỗi tuần
- = Tồn kho trước + MPS − max(Forecast, Customer Orders)

#### 2. Available-to-Promise (ATP)
- Số lượng có thể **hứa giao** cho khách hàng mới
- Quan trọng cho bộ phận bán hàng

#### 3. MPS Quantity (Sản lượng MPS)
- Số lượng quyết định sản xuất trong mỗi kỳ
- Phải tôn trọng giới hạn [[Capacity]]

### Time Fences (Hàng rào thời gian):
- **Frozen Zone (Vùng đóng băng):** 1-2 tuần đầu → KHÔNG thay đổi MPS (đã mua nguyên liệu, đã lên lịch)
- **Slushy Zone (Vùng nửa đông):** 3-8 tuần → thay đổi được nhưng cần phê duyệt
- **Liquid Zone (Vùng linh hoạt):** >8 tuần → tự do thay đổi theo dự báo mới

## Ví dụ thực tế (Real-world Example)
**Nhà máy sản xuất giày Nike Vietnam:**

S&OP nói: "Tháng 4 sản xuất 100,000 đôi giày running"

MPS chi tiết hóa:
| Tuần | Air Max 90 (Đen) | Air Max 90 (Trắng) | Pegasus 40 | Free Run |
|------|-----------------|-------------------|------------|----------|
| Tuần 1 | 8,000 | 5,000 | 7,000 | 5,000 |
| Tuần 2 | 6,000 | 7,000 | 8,000 | 4,000 |
| Tuần 3 | 7,000 | 6,000 | 6,000 | 6,000 |
| Tuần 4 | 9,000 | 4,000 | 7,000 | 5,000 |

→ MPS này sẽ là đầu vào cho [[Material Requirements Planning (MRP)]] để tính cần bao nhiêu đế giày, bao nhiêu vải, bao nhiêu dây giày...

## Mối liên hệ (Relationships)
- Đầu vào từ: [[Sales and Operations Planning (S&OP)]], [[Forecasting]]
- Đầu ra cho: [[Material Requirements Planning (MRP)]]
- Giới hạn bởi: [[Capacity]]
- Sử dụng: [[Bill of Materials (BOM)]] (để tính nguyên vật liệu)
- Thuộc hệ thống: [[Enterprise Resource Planning (ERP)]]
- Thuộc chương: Chapter 15 — Resource Planning

## Công thức (Formula)
**Projected On-Hand Inventory:**
$$POH_t = POH_{t-1} + MPS_t - max(Forecast_t, Customer\ Orders_t)$$

**Available-to-Promise (ATP) — Tuần đầu:**
$$ATP_1 = On\text{-}Hand + MPS_1 - Customer\ Orders\ (before\ next\ MPS)$$
