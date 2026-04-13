---
tags: [key-concept, chapter-15, planning]
aliases: [Material Requirements Planning, MRP, Hoạch định nhu cầu vật tư, MRP I]
---
# Material Requirements Planning (MRP)

## Định nghĩa (Definition)
**Material Requirements Planning (MRP)** (Hoạch định nhu cầu vật tư) là hệ thống tính toán **số lượng, loại** nguyên vật liệu/linh kiện cần thiết và **thời điểm** cần đặt hàng, dựa trên [[Master Production Schedule (MPS)]] và [[Bill of Materials (BOM)]].

## Giải thích chi tiết (Detailed Explanation)

### MRP trả lời 3 câu hỏi:
1. **Cần gì?** → Từ [[Bill of Materials (BOM)]]
2. **Cần bao nhiêu?** → Từ MPS và tồn kho hiện có
3. **Cần khi nào?** → Tính ngược từ ngày cần (backward scheduling)

### 3 đầu vào chính:
1. **[[Master Production Schedule (MPS)]]:** Sản phẩm gì, bao nhiêu, khi nào
2. **[[Bill of Materials (BOM)]]:** Cấu trúc sản phẩm — cần linh kiện gì, bao nhiêu
3. **Inventory Records (Hồ sơ tồn kho):** Tồn kho hiện có, đang đặt, lead time

### Quá trình MRP — Explosion & Netting:

#### Bước 1: Explosion (Phân rã)
- Dùng BOM để "phân rã" thành phẩm thành tất cả linh kiện cần thiết
- Ví dụ: 100 xe đạp → cần 100 khung, 200 bánh, 200 lốp, 100 yên...

#### Bước 2: Netting (Khấu trừ)
- Trừ đi tồn kho hiện có và đơn hàng đang đến
- Net Requirements = Gross Requirements − On-Hand − Scheduled Receipts

#### Bước 3: Lot Sizing (Xác định cỡ lô)
- Quyết định đặt bao nhiêu mỗi lần (Lot-for-Lot, [[Economic Order Quantity (EOQ)|EOQ]], Period Order Quantity...)

#### Bước 4: Time Phasing (Lập lịch thời gian)
- Tính ngược từ ngày cần → ngày phải đặt hàng (trừ lead time)
- Planned Order Release = Planned Receipt − Lead Time

### Đầu ra của MRP:
- **Planned Order Releases:** Đơn đặt hàng cần phát ra
- **Rescheduling Notices:** Thông báo điều chỉnh đơn đang có
- **Cancellation Notices:** Thông báo hủy đơn không cần nữa

## Ví dụ thực tế (Real-world Example)
**Nhà máy lắp ráp bàn học:**

MPS: Cần 200 bàn học vào tuần 8

BOM bàn học:
- 1 mặt bàn (lead time: 2 tuần)
- 4 chân bàn (lead time: 1 tuần)
- 1 bộ ốc vít 8 con (lead time: 1 tuần)

Tồn kho: 50 mặt bàn, 100 chân bàn, 300 bộ ốc vít

**MRP tính:**
| Linh kiện | Gross | On-Hand | Net | Lead Time | Order Release |
|-----------|-------|---------|-----|-----------|--------------|
| Mặt bàn | 200 | 50 | 150 | 2 tuần | **Tuần 6** |
| Chân bàn | 800 | 100 | 700 | 1 tuần | **Tuần 7** |
| Bộ ốc vít | 200 | 300 | 0 | - | **Không cần đặt!** |

## Mối liên hệ (Relationships)
- Đầu vào từ: [[Master Production Schedule (MPS)]], [[Bill of Materials (BOM)]]
- Sử dụng: [[Inventory]] records, [[Economic Order Quantity (EOQ)]]
- Thuộc hệ thống: [[Enterprise Resource Planning (ERP)]]
- Liên quan: [[Capacity]] (CRP — Capacity Requirements Planning)
- Thuộc chương: Chapter 15 — Resource Planning

## Công thức (Formula)
**Net Requirements:**
$$Net\ Req_t = Gross\ Req_t - Projected\ On\text{-}Hand_{t-1} - Scheduled\ Receipts_t$$

**Planned Order Release:**
$$Planned\ Order\ Release = Planned\ Receipt\ Date - Lead\ Time$$

**Gross Requirements (cấp con):**
$$Gross\ Req_{child} = Planned\ Order\ Release_{parent} \times Quantity\ per\ Parent$$
