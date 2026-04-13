---
tags: [key-concept, chapter-7, project-management]
aliases: [Critical Path, Đường găng, Đường tới hạn, Critical Path Method, CPM]
---
# Critical Path

## Định nghĩa (Definition)
**Critical Path** (Đường găng/Đường tới hạn) là **chuỗi các hoạt động dài nhất** xuyên qua mạng lưới dự án (project network), xác định **thời gian ngắn nhất** để hoàn thành toàn bộ dự án. Bất kỳ sự chậm trễ nào trên đường găng đều làm **trễ cả dự án**.

## Giải thích chi tiết (Detailed Explanation)

### Khái niệm cốt lõi:
- Một dự án có nhiều đường đi từ đầu → cuối
- **Đường dài nhất = Critical Path** = Thời gian hoàn thành dự án
- Hoạt động trên Critical Path gọi là **Critical Activities** — không có thời gian chờ (slack = 0)

### Các thuật ngữ quan trọng:
| Thuật ngữ | Ý nghĩa |
|-----------|---------|
| **ES** (Early Start) | Thời điểm sớm nhất có thể bắt đầu |
| **EF** (Early Finish) | Thời điểm sớm nhất có thể kết thúc = ES + Duration |
| **LS** (Late Start) | Thời điểm muộn nhất được bắt đầu mà không trễ dự án |
| **LF** (Late Finish) | Thời điểm muộn nhất được kết thúc |
| **Slack/Float** | Thời gian có thể trễ mà không ảnh hưởng dự án = LS − ES |

### Các bước tìm Critical Path:
1. **Vẽ project network** từ [[Work Breakdown Structure (WBS)]]
2. **Forward Pass (Lượt xuôi):** Tính ES, EF cho mỗi hoạt động (từ đầu → cuối)
3. **Backward Pass (Lượt ngược):** Tính LS, LF từ cuối → đầu
4. **Tính Slack:** Slack = LS − ES (hoặc LF − EF)
5. **Critical Path:** Tất cả hoạt động có **Slack = 0**

### Tại sao quan trọng?
- Biết **thời gian dự án**: Hứa khách hàng khi nào xong
- Biết **hoạt động nào KHÔNG ĐƯỢC TRỄ**: Tập trung quản lý
- Biết **hoạt động nào có thể trễ**: Linh hoạt phân bổ nguồn lực
- **Crashing:** Nếu muốn rút ngắn dự án → phải rút ngắn hoạt động trên Critical Path

## Ví dụ thực tế (Real-world Example)
**Xây nhà (đơn giản hóa):**

| Hoạt động | Thời gian | Phải sau |
|-----------|-----------|----------|
| A: Đào móng | 2 tuần | - |
| B: Đổ móng | 3 tuần | A |
| C: Xây tường | 4 tuần | B |
| D: Lắp điện | 2 tuần | C |
| E: Lắp nước | 2 tuần | C |
| F: Trát + Sơn | 3 tuần | D, E |

**Các đường đi:**
- A → B → C → D → F: 2+3+4+2+3 = **14 tuần** ← **CRITICAL PATH!**
- A → B → C → E → F: 2+3+4+2+3 = **14 tuần** ← Cũng critical!

→ Thời gian dự án = **14 tuần**
→ Mọi hoạt động đều critical (slack = 0)
→ Nếu đổ móng trễ 1 tuần → cả nhà trễ 1 tuần!

## Mối liên hệ (Relationships)
- Đầu vào từ: [[Work Breakdown Structure (WBS)]]
- Liên quan: [[Capacity]] (phân bổ nguồn lực)
- Công cụ phân tích: [[Decision Trees]] (nếu dự án có rủi ro)
- Thuộc chương: Chapter 7 — Project Management

## Công thức (Formula)
**Early Start & Early Finish (Forward Pass):**
$$ES = max(EF\ of\ all\ predecessors)$$
$$EF = ES + Duration$$

**Late Start & Late Finish (Backward Pass):**
$$LF = min(LS\ of\ all\ successors)$$
$$LS = LF - Duration$$

**Slack (Thời gian dự trữ):**
$$Slack = LS - ES = LF - EF$$

**Project Duration = EF của hoạt động cuối cùng trên Forward Pass**

**Critical Path = Đường đi mà TẤT CẢ hoạt động có Slack = 0**
