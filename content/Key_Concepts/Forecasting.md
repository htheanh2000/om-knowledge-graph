---
tags: [key-concept, chapter-13, forecasting]
aliases: [Forecasting, Dự báo, Demand Forecasting, Dự báo nhu cầu]
---
# Forecasting

## Định nghĩa (Definition)
**Forecasting** (Dự báo) là quá trình **ước tính nhu cầu tương lai** của sản phẩm/dịch vụ, sử dụng dữ liệu lịch sử, phán đoán chuyên gia, hoặc kết hợp cả hai, làm cơ sở cho các quyết định vận hành.

## Giải thích chi tiết (Detailed Explanation)

### Tại sao cần dự báo?
- Quyết định [[Capacity]] — cần bao nhiêu năng lực?
- Lập [[Sales and Operations Planning (S&OP)]] — sản xuất bao nhiêu?
- Quản lý [[Inventory]] — giữ bao nhiêu tồn kho?
- Lên lịch nhân sự — cần bao nhiêu nhân viên?

### Đặc điểm quan trọng:
1. **Dự báo luôn sai** — Câu hỏi là sai bao nhiêu, không phải có sai không
2. **Dự báo nhóm chính xác hơn cá nhân** — Dự báo tổng nhu cầu sữa dễ hơn dự báo nhu cầu 1 loại sữa cụ thể
3. **Dự báo ngắn hạn chính xác hơn dài hạn**
4. **Không có phương pháp dự báo hoàn hảo** — cần kết hợp nhiều phương pháp

### Hai nhóm phương pháp:

#### A. Qualitative Methods (Phương pháp định tính)
Dựa trên **phán đoán, kinh nghiệm, ý kiến chuyên gia:**
- **Executive Opinion:** Ý kiến ban lãnh đạo
- **Market Research:** Khảo sát thị trường
- **Delphi Method:** Lấy ý kiến chuyên gia nhiều vòng
- **Sales Force Estimates:** Ước tính của đội ngũ bán hàng

→ Phù hợp khi **không có dữ liệu lịch sử** (sản phẩm mới)

#### B. Quantitative Methods (Phương pháp định lượng)
Dựa trên **dữ liệu lịch sử và mô hình toán:**
- **Time Series:** Phân tích xu hướng, mùa vụ từ dữ liệu quá khứ
  - [[Moving Average]] (Trung bình trượt)
  - [[Exponential Smoothing]] (San bằng mũ)
  - Trend projection, Seasonal decomposition
- **Causal/Regression:** Tìm mối quan hệ nhân quả (ví dụ: doanh số kem ↔ nhiệt độ)

→ Phù hợp khi **có dữ liệu lịch sử** đủ lớn

### Đo lường sai số dự báo:
- **MAD** (Mean Absolute Deviation) = Trung bình giá trị tuyệt đối sai số
- **MAPE** (Mean Absolute Percentage Error) = MAD dưới dạng %
- **MSE** (Mean Squared Error) = Trung bình bình phương sai số

## Ví dụ thực tế (Real-world Example)
**Highlands Coffee dự báo nhu cầu cà phê tháng tới:**
- **Dữ liệu lịch sử:** Tháng trước bán 50,000 ly, cùng kỳ năm ngoái 45,000 ly
- **Yếu tố định tính:** Sắp có chương trình khuyến mãi, mở thêm 2 cửa hàng mới
- **Phương pháp:** Kết hợp [[Exponential Smoothing]] (dữ liệu) + điều chỉnh theo ý kiến quản lý
- **Dự báo:** 55,000 ly ± 5,000 ly

## Mối liên hệ (Relationships)
- Công cụ: [[Moving Average]], [[Exponential Smoothing]]
- Phục vụ cho: [[Demand Management]], [[Sales and Operations Planning (S&OP)]]
- Ảnh hưởng đến: [[Capacity]], [[Inventory]], [[Safety Stock]]
- Sai số dự báo gây ra: [[Bullwhip Effect]]
- Thuộc chương: Chapter 13 — Forecasting

## Công thức (Formula)
**MAD (Mean Absolute Deviation):**
$$MAD = \frac{\sum_{t=1}^{n} |A_t - F_t|}{n}$$

**MAPE (Mean Absolute Percentage Error):**
$$MAPE = \frac{\sum_{t=1}^{n} \frac{|A_t - F_t|}{A_t}}{n} \times 100\%$$

Trong đó:
- $A_t$ = Actual demand (Nhu cầu thực tế) tại thời điểm t
- $F_t$ = Forecast (Dự báo) tại thời điểm t
- n = Số kỳ quan sát
