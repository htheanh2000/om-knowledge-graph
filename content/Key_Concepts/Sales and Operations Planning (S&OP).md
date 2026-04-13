---
tags: [key-concept, chapter-14, planning]
aliases: [Sales and Operations Planning, S&OP, Hoạch định bán hàng và vận hành, Aggregate Planning]
---
# Sales and Operations Planning (S&OP)

## Định nghĩa (Definition)
**Sales and Operations Planning (S&OP)** (Hoạch định bán hàng & vận hành) là quy trình lập kế hoạch **trung hạn** (thường 3-18 tháng) nhằm **cân bằng cung và cầu** ở mức tổng thể, kết nối kế hoạch bán hàng với kế hoạch sản xuất/vận hành.

## Giải thích chi tiết (Detailed Explanation)

### Vị trí trong hệ thống lập kế hoạch:
```
Chiến lược dài hạn (3-5 năm)
    ↓
[[Operations Strategy]]
    ↓
S&OP (3-18 tháng) ← BẠN ĐANG Ở ĐÂY
    ↓
[[Master Production Schedule (MPS)]] (tuần-tháng)
    ↓
[[Material Requirements Planning (MRP)]] (ngày-tuần)
```

### Mục tiêu:
- Đảm bảo **đủ năng lực** ([[Capacity]]) đáp ứng nhu cầu dự báo
- Tối ưu chi phí: nhân công, tồn kho, thuê ngoài
- Đồng bộ mọi bộ phận: Bán hàng, Marketing, Sản xuất, Tài chính, Nhân sự

### Ba chiến lược S&OP chính:

#### 1. Chase Strategy (Chiến lược đuổi theo)
- **Điều chỉnh sản lượng** theo nhu cầu mỗi kỳ
- Thuê/sa thải nhân viên theo mùa, tăng/giảm ca
- **Ưu:** Tồn kho thấp
- **Nhược:** Chi phí thuê/sa thải cao, nhân viên bất ổn
- Ví dụ: Resort biển tăng nhân viên mùa hè, giảm mùa đông

#### 2. Level Strategy (Chiến lược ổn định)
- Giữ **sản lượng ổn định**, dùng [[Inventory|tồn kho]] để đệm
- Sản xuất thừa mùa vắng → tồn trữ → bán mùa đông
- **Ưu:** Nhân lực ổn định, năng suất đều
- **Nhược:** Chi phí tồn kho cao
- Ví dụ: Nhà máy bánh trung thu sản xuất đều quanh năm

#### 3. Mixed Strategy (Chiến lược hỗn hợp)
- Kết hợp cả hai → linh hoạt, thực tế nhất
- Phần lớn doanh nghiệp dùng chiến lược này

### Các công cụ điều chỉnh:
**Phía cung (Supply):** Thay đổi lực lượng lao động, tăng ca, [[Outsourcing|thuê ngoài]], tồn kho
**Phía cầu (Demand):** Giảm giá, khuyến mãi, backorder (giao sau)

## Ví dụ thực tế (Real-world Example)
**Nhà máy kem Tràng Tiền:**
- **Mùa hè:** Nhu cầu gấp 3 lần mùa đông
- **S&OP quyết định:**
  - Tháng 1-3: Sản xuất ổn định, tồn trữ dần (Level)
  - Tháng 4-5: Tăng ca, thuê thêm lao động thời vụ (Chase)
  - Tháng 6-8: Chạy tối đa công suất + thuê ngoài một phần
  - Tháng 9-12: Giảm dần, tận dụng tồn kho còn lại

## Mối liên hệ (Relationships)
- Đầu vào: [[Forecasting]], [[Demand Management]]
- Đầu ra cho: [[Master Production Schedule (MPS)]]
- Ảnh hưởng: [[Capacity]], [[Inventory]]
- Chiến lược: [[Operations Strategy]]
- Sử dụng: [[Outsourcing]] (khi cần linh hoạt)
- Thuộc chương: Chapter 14 — Sales and Operations Planning

## Công thức (Formula)
**Tổng chi phí S&OP plan:**
$$Total\ Cost = Hiring\ Cost + Firing\ Cost + Inventory\ Holding\ Cost + Overtime\ Cost + Subcontracting\ Cost + Backorder\ Cost$$

Mục tiêu: Tìm kế hoạch có **Total Cost thấp nhất** qua các kỳ.
