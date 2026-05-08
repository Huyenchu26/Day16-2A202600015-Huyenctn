# Document Trail — NestAI (MamaMenu AI)
**Date:** 08/05/2026
**Founder:** Chu Thị Ngọc Huyền

---

## Bảng đối chiếu 5 loại hồ sơ

| # | Loại hồ sơ | Status | Bằng chứng hiện tại | Deadline build |
|---|-----------|--------|---------------------|----------------|
| 1 | Nhật ký kiểm thử claim AI | ✗ CHƯA CÓ | marketing_claims_audit.md (WS1) là lần đầu tiên rà soát — chưa có log testing định kỳ, chưa có benchmark accuracy; Risk Register v2 đề cập "Menu Safety Monday" nhưng chưa triển khai | **15/05/2026** |
| 2 | Hồ sơ rà soát điều khoản vendor | ✗ CHƯA CÓ | Risk Register v2 Risk 3 nhận diện rủi ro OpenAI ToS ban nhưng không có review chính thức ToS; OpenAI Terms of Use cấm dùng API cho medical advice chưa được đọc và ký xác nhận hiểu | **22/05/2026** |
| 3 | Nhật ký giám sát giao dịch bất thường | — CHƯA CẦN (MVP pre-revenue) | Day 17 PRD Non-Goals: "Không cần thanh toán trong giai đoạn này" — không có payment flow nên chưa có transaction để monitor; **CẦN BUILD TRƯỚC KHI thêm payment** | Trước khi tích hợp payment gateway |
| 4 | DPIA / CTIA đã nộp | ✗ CHƯA CÓ — **KHẨN CẤP** | PDPL hiệu lực 1/1/2026 (đã qua); NestAI đang xử lý dữ liệu y tế nhạy cảm (tuần thai, bệnh lý) và chuyển sang OpenAI + Google Cloud Vision; Risk 8 Risk Register đề cập privacy risk nhưng vẫn viện dẫn "Nghị định 13" đã hết hiệu lực — chưa có DPIA hay CTIA nào được nộp | **07/06/2026** (60 ngày từ ngày bắt đầu xử lý pilot data) |
| 5 | Phê duyệt nội dung marketing (founder ký) | ✗ CHƯA CÓ | Pitch Memo, Twitter Pitch, Script 45s, Hook đều được tạo không qua quy trình review có chữ ký; WS1 tìm thấy 9/12 claim Mức C không có evidence; không có template "founder ký trước khi phát hành" | **Ngay tuần này — trước bất kỳ pitch/post nào tiếp theo** |

---

## TOP 1 ưu tiên

**Loại:** #4 — DPIA / CTIA

**Lý do (1 câu):** NestAI đã thu thập dữ liệu y tế nhạy cảm nhất của phụ nữ mang thai (tuần thai, bệnh lý tiểu đường, thiếu máu) và đang chuyển toàn bộ sang server nước ngoài (OpenAI Mỹ, Google Cloud) mà không có đánh giá tác động nào được nộp — trong khi PDPL đã có hiệu lực từ 1/1/2026, mức phạt là 5% doanh thu năm hoặc 3 tỷ đồng, và mỗi ngày trì hoãn là thêm 1 ngày vi phạm đã xảy ra.

**Tại sao không chọn #5 (marketing approval)?**
Hồ sơ #5 cũng khẩn cấp (vùng Điều 198), nhưng NestAI chưa có revenue — nên ngưỡng truy cứu hình sự chưa kích hoạt. DPIA/CTIA áp dụng ngay từ ngày đầu xử lý dữ liệu, không cần chờ có doanh thu.

---

## Template build trong 1 tuần — DPIA + CTIA cho NestAI

### Người chịu trách nhiệm
**Founder kiêm Data Controller:** Chu Thị Ngọc Huyền
**DPO tạm thời:** Founder (ân hạn 5 năm cho startup theo PDPL) — có thể thuê DPO as a Service khi có nguồn lực

### Tần suất cập nhật
- **DPIA:** Lần đầu nộp trong 60 ngày từ ngày xử lý dữ liệu đầu tiên → review lại mỗi khi thêm luồng dữ liệu mới (ví dụ: thêm tính năng xét nghiệm, tích hợp bệnh viện)
- **CTIA:** Mỗi khi thêm vendor nước ngoài mới hoặc vendor hiện tại thay đổi data processing terms

---

### DPIA — Data Protection Impact Assessment (Đánh giá tác động bảo vệ dữ liệu)

```markdown
## DPIA — NestAI
**Ngày lập:** [DD/MM/YYYY]
**Phiên bản:** 1.0
**Người lập:** Chu Thị Ngọc Huyền (Founder / Data Controller)

### 1. Mô tả xử lý dữ liệu
- Loại dữ liệu: Thông tin thai kỳ (tuần thai, trimester), bệnh lý (tiểu đường thai kỳ,
  thiếu máu, dị ứng), ảnh bữa ăn, hành vi sử dụng app
- Chủ thể dữ liệu: Phụ nữ mang thai 22-35 tuổi tại Việt Nam
- Mục đích xử lý: Sinh thực đơn cá nhân hóa, track vi chất từ ảnh, đo compliance

### 2. Đánh giá sự cần thiết và tính tương xứng
- Dữ liệu bệnh lý: CẦN THIẾT để cá nhân hóa thực đơn (tiểu đường → thực đơn low-GI)
- Ảnh bữa ăn: CẦN THIẾT cho tính năng core (photo logging)
- Dữ liệu thu thập tối thiểu: [liệt kê các trường thực sự cần, loại bỏ trường không cần]

### 3. Đánh giá rủi ro
| Rủi ro | Xác suất | Tác động | Biện pháp |
|--------|----------|---------|-----------|
| Lộ dữ liệu y tế nhạy cảm | Trung bình | Rất cao | Mã hóa E2E, pseudonymization khi gửi API |
| AI xử lý sai dữ liệu y tế | Cao | Cao | Guardrails, human-in-the-loop |
| Vendor nước ngoài rò rỉ | Thấp-Trung bình | Rất cao | CTIA, Data Processing Agreement với vendor |

### 4. Biện pháp giảm thiểu đã áp dụng
- [ ] Pseudonymize dữ liệu trước khi gửi OpenAI API (bỏ tên thật, thay bằng user_id)
- [ ] Không gửi ảnh gốc sang Google Vision — chỉ gửi crop cần phân tích
- [ ] Data retention policy: xóa ảnh sau [X] ngày, không lưu vĩnh viễn
- [ ] Consent rõ ràng khi onboarding: checkbox riêng cho dữ liệu y tế nhạy cảm

### 5. Kết luận
- Xử lý dữ liệu: Cần thiết và tương xứng với mục đích
- Rủi ro tồn dư sau biện pháp: [Thấp/Trung bình/Cao]
- Quyết định: Tiếp tục xử lý với điều kiện [list điều kiện]

**Chữ ký Founder / Data Controller:** _________________ Ngày: _______
```

---

### CTIA — Cross-border Transfer Impact Assessment (Đánh giá tác động chuyển dữ liệu xuyên biên giới)

```markdown
## CTIA — NestAI
**Ngày lập:** [DD/MM/YYYY]
**Phiên bản:** 1.0
**Người lập:** Chu Thị Ngọc Huyền

### Vendor 1: OpenAI (GPT-4o)
- Dữ liệu chuyển: Thông tin thai kỳ, bệnh lý, sở thích ăn uống (trong prompt)
- Máy chủ nhận: Mỹ (OpenAI Inc.)
- Cơ sở pháp lý chuyển: [Standard Contractual Clauses / Adequacy Decision]
- Data Processing Agreement: [Đã ký / Chưa ký — link DPA của OpenAI]
- Rủi ro: OpenAI có thể dùng data để train model (cần tắt training opt-out)
- Biện pháp: Kích hoạt Enterprise API (Zero Data Retention) hoặc pseudonymize trước khi gửi

### Vendor 2: Google Cloud Vision
- Dữ liệu chuyển: Ảnh bữa ăn (có thể chứa metadata GPS)
- Máy chủ nhận: Google (Mỹ/EU)
- Data Processing Agreement: [Đã ký / Chưa ký — Google Cloud DPA]
- Biện pháp: Strip metadata GPS trước khi upload, dùng region cụ thể (asia-southeast1)

### Kết luận
- CTIA hoàn thành: CÓ
- Biện pháp bổ sung cần thiết: [list]
- Review định kỳ: [Hằng năm hoặc khi vendor thay đổi terms]

**Chữ ký Founder / Data Controller:** _________________ Ngày: _______
```

---

## Ghi chú về 4 hồ sơ còn lại (ưu tiên sau DPIA/CTIA)

### #5 Phê duyệt marketing — Bắt đầu ngay tuần này
Dùng kết quả WS1 (`marketing_claims_audit.md`) làm checklist: mỗi lần tạo content mới,
founder ký xác nhận không có Mức C nào chưa có evidence. Template 3 dòng:

```
[YYYY-MM-DD] Content: [mô tả] | Người tạo: | Claim A: | Claim B: | Claim C: 0 | Founder ký: ___
```

### #1 Nhật ký kiểm thử claim AI — Bắt đầu từ "Menu Safety Monday" đầu tiên
Mỗi thứ Hai, review 20 menus AI tạo ra. Log:
```
[Date] | Menu #: | Bệnh lý: | Lỗi phát hiện: | Hành động sửa: | Reviewer: Founder
```

### #2 Hồ sơ rà soát vendor ToS — Deadline 22/05
Đọc và tóm tắt 3 điều khoản quan trọng nhất của OpenAI ToS + Google Cloud ToS liên quan đến
medical/health data. Lưu bản tóm tắt + ngày đọc + chữ ký founder.

### #3 Nhật ký giao dịch bất thường — Build trước khi có payment
Khi thêm payment (Stripe/VNPay), thiết lập ngay: threshold alert >10 giao dịch/giờ từ 1 IP,
flag tài khoản mới thanh toán ngay > 500K, weekly review log bất thường.
