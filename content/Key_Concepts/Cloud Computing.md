---
tags: [key-concept, chapter-1, technology]
aliases: [Cloud Computing, Điện toán đám mây, Cloud, SaaS, IaaS, PaaS]
---
# Cloud Computing

## Định nghĩa (Definition)
**Cloud Computing** (Điện toán đám mây) là mô hình cung cấp tài nguyên CNTT (máy chủ, lưu trữ, phần mềm, phân tích dữ liệu) **qua internet** theo nhu cầu, thay vì doanh nghiệp phải tự đầu tư và vận hành hạ tầng IT.

## Giải thích chi tiết (Detailed Explanation)

### Ba mô hình dịch vụ Cloud:

| Mô hình | Cung cấp gì | Ví dụ | Ai dùng |
|---------|-------------|-------|---------|
| **IaaS** (Infrastructure) | Máy chủ, lưu trữ, mạng | AWS EC2, Azure VM | IT team |
| **PaaS** (Platform) | Nền tảng phát triển ứng dụng | Google App Engine, Heroku | Developers |
| **SaaS** (Software) | Phần mềm dùng ngay | Gmail, Salesforce, SAP Cloud | End users |

### Ứng dụng trong Operations Management:

#### 1. Cloud ERP
- [[Enterprise Resource Planning (ERP)]] trên cloud thay vì on-premise
- Không cần đầu tư máy chủ hàng tỷ đồng
- Cập nhật tự động, truy cập từ mọi nơi
- Ví dụ: SAP S/4HANA Cloud, Oracle Cloud ERP, Odoo Online

#### 2. Supply Chain Collaboration
- Chia sẻ thông tin [[Supply Chain]] giữa nhiều đối tác trên cùng 1 nền tảng cloud
- Giảm [[Bullwhip Effect]] nhờ minh bạch thông tin

#### 3. Analytics & [[Forecasting]]
- Xử lý Big Data trên cloud → dự báo chính xác hơn
- Machine Learning as a Service → AI không cần chuyên gia

#### 4. [[Internet of Things (IoT)|IoT]] Data Processing
- Hàng triệu cảm biến gửi dữ liệu → Cloud xử lý → Insight thời gian thực

### Ưu điểm cho doanh nghiệp:
| Trước Cloud | Sau Cloud |
|---|---|
| Đầu tư máy chủ lớn (CapEx) | Trả theo dùng (OpEx) |
| Mất 6-12 tháng triển khai | Sẵn sàng trong vài giờ |
| Tự bảo trì, nâng cấp | Nhà cung cấp lo mọi thứ |
| Giới hạn năng lực | Linh hoạt tăng/giảm (scalable) |
| Mất dữ liệu nếu hỏng server | Backup tự động |

### Rủi ro:
- Phụ thuộc internet
- Bảo mật dữ liệu (dữ liệu nằm ở server bên ngoài)
- Vendor lock-in (khó chuyển đổi nhà cung cấp)

## Ví dụ thực tế (Real-world Example)
**Netflix — Cloud Computing kinh điển:**
- Chạy toàn bộ trên AWS (Amazon Web Services)
- 200+ triệu khách hàng, hàng tỷ giờ streaming
- Tự động tăng server khi nhiều người xem, giảm khi vắng → tối ưu chi phí

**Doanh nghiệp nhỏ Việt Nam:**
- Quán cà phê dùng KiotViet (SaaS) quản lý bán hàng, tồn kho → không cần IT team
- Startup dùng Google Workspace (email, drive, meet) → không cần mua server

## Mối liên hệ (Relationships)
- Thuộc về: [[Industry 4.0]]
- Hỗ trợ: [[Enterprise Resource Planning (ERP)]], [[Internet of Things (IoT)]]
- Ứng dụng: [[Forecasting]] (cloud analytics), [[Supply Chain]] (collaboration)
- Kết hợp: [[Blockchain]] (blockchain-as-a-service)
- Thuộc chương: Chapter 1 — Using Operations to Create Value

## Công thức (Formula)
Không có công thức OM. Cloud Computing là mô hình triển khai CNTT.

**So sánh chi phí:**
- On-premise: High CapEx + ongoing maintenance
- Cloud: Pay-as-you-go (OpEx) → biến chi phí cố định thành chi phí biến đổi
