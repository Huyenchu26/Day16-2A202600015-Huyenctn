# Territorial Scope — NestAI (MamaMenu AI)
**Date:** 08/05/2026
**Founder:** Chu Thị Ngọc Huyền
**Product:** NestAI — Ứng dụng gợi ý thực đơn dinh dưỡng cá nhân hóa cho phụ nữ mang thai tại Việt Nam

---

## Câu hỏi 1: User EU? (3 phút)

- **Có user EU hiện tại:** 0 (không có)
- **Kế hoạch mở rộng EU 12 tháng tới:** KHÔNG

**Bằng chứng từ tài liệu:**
- Day 17 PRD — Non-Goals ghi rõ: *"Tối ưu hóa cho thị trường ngoài Việt Nam trong 12 tháng đầu"*
- Day 16 Customer Card: Segment = *"Phụ nữ lần đầu mang thai tại Việt Nam, 22–35 tuổi"*; kênh phân phối = Facebook/Zalo VN, phòng khám sản TP.HCM + Hà Nội
- Day 16 TAM/SAM/SOM: Mở rộng chỉ nhắm SEA (Thailand, Philippines, Indonesia) — không có EU trong kế hoạch

**Kết luận:** EU AI Act **KHÔNG áp dụng** tại thời điểm này.
> Lưu ý: Nếu app xuất hiện trên App Store EU hoặc có người dùng EU đăng ký sau này, phải đánh giá lại ngay — EU AI Act có hiệu lực territorial (áp dụng khi deploy ở EU, không cần văn phòng).

---

## Câu hỏi 2: Dữ liệu Việt Nam? (3 phút)

### 5 loại dữ liệu cá nhân đang xử lý:

| # | Loại dữ liệu | Nguồn | Mức độ nhạy cảm |
|---|--------------|-------|-----------------|
| 1 | **Thông tin định danh** (tên, tuổi, email, SĐT) | Onboarding đăng ký | Thông thường |
| 2 | **Dữ liệu y tế / bệnh lý** (tuần thai, trimester, tiểu đường thai kỳ, thiếu máu, dị ứng) | Profile bệnh lý | **Nhạy cảm đặc biệt** — cần xử lý theo PDPL Điều 9 |
| 3 | **Hình ảnh bữa ăn** (photo logging, chứa metadata GPS tiềm ẩn) | Camera user | Nhạy cảm |
| 4 | **Hành vi sử dụng** (menu đã xem, món đã swap, compliance log, ngày follow thực đơn) | App analytics | Thông thường |
| 5 | **Vị trí địa lý gián tiếp** (vùng miền: HCM/HN, khu vực chợ/quán ăn quen dùng) | Preference profile | Thông thường |

### Có chuyển dữ liệu ra nước ngoài: **CÓ**

| Vendor | Dữ liệu chuyển | Máy chủ |
|--------|---------------|---------|
| **OpenAI (GPT-4o)** | Thông tin thai kỳ + bệnh lý + sở thích → prompt menu generation | Mỹ |
| **Google Cloud Vision** | Ảnh bữa ăn → food recognition | Mỹ/EU |

> Theo PDPL Điều 30 và hướng dẫn Day 22: *"Dùng AI nước ngoài (OpenAI, Anthropic API) = CHUYỂN"* — dữ liệu y tế nhạy cảm của phụ nữ mang thai đang chuyển ra nước ngoài mỗi lần gọi API.

### Kết luận:
- **PDPL áp dụng = YES** (chắc chắn — xử lý dữ liệu cá nhân người Việt Nam, bao gồm dữ liệu y tế nhạy cảm đặc biệt)
- **CTIA (Cross-border Transfer Impact Assessment) = YES** (vắc-xin bắt buộc vì dùng OpenAI + Google Cloud)
- **DPIA (Data Protection Impact Assessment) = YES** — phải nộp trong **60 ngày** kể từ khi bắt đầu xử lý dữ liệu theo PDPL Điều 30

**Mức phạt tiềm năng nếu vi phạm:**
- PDPL Điều 8: đến 5% doanh thu năm trước hoặc 3 tỷ đồng
- Dữ liệu y tế nhạy cảm vi phạm → rủi ro hình sự nếu đủ cấu thành tội

---

## Câu hỏi 3: Tầng rủi ro Luật AI VN (Điều 9 — Luật 134/2025/QH15)? (5 phút)

### Phân loại: **TẦNG CAO**

**Lập luận (1 câu):**
NestAI đưa ra gợi ý dinh dưỡng cá nhân hóa trực tiếp ảnh hưởng đến quyết định ăn uống của phụ nữ mang thai có bệnh lý y tế (tiểu đường thai kỳ, thiếu máu thiếu sắt) — nhóm người dùng đặc biệt dễ bị tổn thương mà một gợi ý sai có thể gây hậu quả sức khỏe nghiêm trọng cho cả mẹ và thai nhi — đủ điều kiện xếp vào **tầng Cao** theo Điều 9 Luật AI VN vì "tác động đáng kể tới sức khỏe và quyền cơ bản" trong lĩnh vực **y tế**.

**Nghĩa vụ của tầng Cao (phải thực hiện):**

| Nghĩa vụ | Trạng thái hiện tại | Ghi chú |
|----------|-------------------|---------|
| Đánh giá phù hợp (conformity assessment) | ✗ Chưa có | Cần build trước khi deploy |
| Đăng ký CSDL AI quốc gia (Bộ KH&CN) | ✗ Chưa có | Cổng AI quốc gia — Bộ KH&CN |
| Giám sát con người (human-in-the-loop) | ✓ CÓ — đã thiết kế | PRD Day 17: badge "Ước tính (~)" + hotline bác sĩ + user xác nhận |
| Báo cáo sự cố | ✗ Chưa có | Cần quy trình báo cáo khi AI sai nghiêm trọng |
| Lưu log AI decision | ✗ Chưa có | Cần audit trail mỗi lần gợi ý menu |

---

## 4 Deadlines — Note vào Notion/Calendar

| # | Deadline | Sự kiện | Trạng thái | Hành động cụ thể |
|---|----------|---------|-----------|-----------------|
| 1 | **01/01/2026** | PDPL 91/2025/QH15 hiệu lực | ✗ **Đã qua — chưa tuân thủ** | Nộp DPIA + CTIA ngay trong vòng 60 ngày kể từ ngày xử lý dữ liệu đầu tiên |
| 2 | **01/03/2026** | Luật AI VN 134/2025/QH15 hiệu lực | ✗ **Đã qua — chưa tuân thủ** | Tự phân loại tầng Cao + thông báo Bộ KH&CN qua cổng AI quốc gia |
| 3 | **02/08/2026** | EU AI Act high-risk hiệu lực đầy đủ | — Không áp dụng (chưa có user EU) | Theo dõi nếu có kế hoạch App Store EU |
| 4 | **01/09/2027** | Hết ân hạn 18 tháng cho tầng Cao y tế | 16 tháng nữa | Phải tuân thủ đầy đủ: conformity assessment + đăng ký CSDL AI quốc gia + log đầy đủ |

> **Lưu ý quan trọng:** Deadline 1 và 2 đã qua. NestAI đang trong tình trạng chưa tuân thủ kể từ 01/01/2026 và 01/03/2026. Ưu tiên số 1 là nộp DPIA + CTIA trong 2 tuần tới và thông báo Bộ KH&CN về phân loại tầng Cao.

---

## Tóm tắt rủi ro theo mức độ ưu tiên

| Ưu tiên | Rủi ro | Luật | Hành động |
|---------|--------|------|-----------|
| 🔴 Cao nhất | Chưa nộp DPIA/CTIA — dữ liệu y tế nhạy cảm đang chuyển sang OpenAI | PDPL Điều 30 | Nộp trong 2 tuần |
| 🔴 Cao | Chưa đăng ký tầng Cao với Bộ KH&CN | Luật AI VN Điều 9 | Thông báo Bộ KH&CN |
| 🟡 Trung bình | Chưa có log audit trail cho mỗi AI recommendation | Luật AI VN — tầng Cao | Build trước MVP |
| 🟡 Trung bình | Privacy Policy chưa cập nhật theo PDPL (consent, data flow rõ ràng) | PDPL | Cập nhật trước launch |
| 🟢 Thấp | EU AI Act — hiện chưa áp dụng | EU AI Act | Theo dõi, đánh giá lại khi có kế hoạch EU |
