# Compliance Calendar — NestAI (MamaMenu AI)

**Ngày tạo:** 08/05/2026
**Owner:** Chu Thị Ngọc Huyền (Founder)
**Mục đích:** Theo dõi 4 mốc deadline pháp lý + lịch hành động 30 ngày sau Day 22

---

## 1. 4 MỐC DEADLINE CHÍNH

| # | Ngày | Sự kiện | Status hiện tại (08/05/2026) | Ưu tiên |
|---|------|---------|------------------------------|---------|
| 1 | **01/01/2026** | PDPL 91/2025/QH15 hiệu lực | 🔴 Đã qua 4 tháng — **đang vi phạm** | KHẨN CẤP |
| 2 | **01/03/2026** | Luật AI VN 134/2025/QH15 hiệu lực | 🔴 Đã qua 2 tháng — **đang vi phạm** | KHẨN CẤP |
| 3 | **02/08/2026** | EU AI Act high-risk hiệu lực đầy đủ | ⚪ Không áp dụng (NestAI không có user EU) | THEO DÕI |
| 4 | **01/09/2027** | Hết ân hạn 18 tháng tầng Cao y tế | 🟡 16 tháng nữa | LẬP KẾ HOẠCH |

**Deadline phái sinh đang đếm ngược:**

| Ngày | Mô tả | Còn lại |
|------|-------|---------|
| **07/06/2026** | Hạn nộp DPIA (60 ngày từ ngày bắt đầu xử lý pilot data) | ~30 ngày |
| **22/05/2026** | Hạn build Hồ sơ rà soát vendor ToS (theo document_trail.md) | 14 ngày |
| **15/05/2026** | Hạn build Nhật ký kiểm thử claim AI ("Menu Safety Monday" đầu tiên) | 7 ngày |

---

## 2. CHECKLIST 30 NGÀY (theo Day 22 Handbook §11)

### TUẦN 1 — 08/05/2026 → 14/05/2026 (HIỆN TẠI)

| ☐ | Task | Liên quan VP # | Owner |
|---|------|----------------|-------|
| ☐ | Hoàn thành 5 file Day 22 + nộp lên hệ thống | — | Founder |
| ☐ | Note 4 mốc deadline vào Notion + Google Calendar (recurring reminder) | — | Founder |
| ☐ | Chia sẻ `marketing_claims_audit.md` với team marketing/advisor | VP1, VP2, VP3 | Founder |
| ☐ | Sửa các câu Mức C trong Pitch Memo + Twitter + Script TRƯỚC bất kỳ pitch tiếp theo | VP1, VP2, VP3 | Founder |
| ☐ | Bắt đầu "Menu Safety Monday" — review 20 menu AI sinh ra mỗi thứ Hai | (Nhật ký kiểm thử AI) | Founder |

### TUẦN 2 — 15/05/2026 → 21/05/2026

| ☐ | Task | Liên quan VP # | Owner |
|---|------|----------------|-------|
| ☐ | Build TOP 1 hồ sơ chứng cứ từ WS3 = **DPIA + CTIA template** điền đầy đủ | VP4, VP5 | Founder |
| ☐ | Đọc OpenAI Usage Policies + Google Cloud DPA — lưu bản tóm tắt + ngày đọc + chữ ký | VP8 | Founder |
| ☐ | Pseudonymize dữ liệu trước khi gửi OpenAI: thay tên thật bằng `user_id_hash` | VP4, VP5 | Founder |
| ☐ | Bật OpenAI Zero Data Retention (Enterprise plan) hoặc nâng cấp plan | VP5, VP8 | Founder |
| ☐ | Soạn Privacy Policy theo template PDPL (5 loại dữ liệu, vendor, quyền user) | VP6 | Founder |

### TUẦN 3 — 22/05/2026 → 28/05/2026

| ☐ | Task | Liên quan VP # | Owner |
|---|------|----------------|-------|
| ☐ | Soạn document tự phân loại tầng Cao Luật AI VN (1 trang) | VP7 | Founder |
| ☐ | Gửi thông báo Bộ KH&CN bằng văn bản chính thức (nếu cổng AI quốc gia chưa go-live) | VP7 | Founder |
| ☐ | Triển khai abstraction layer (LLM Router) tách OpenAI khỏi business logic | VP8, Risk 3 | Founder + Tech advisor |
| ☐ | Tạo template "Founder ký phê duyệt marketing" — áp dụng từ launch tiếp theo | VP1, VP2, VP3 | Founder |
| ☐ | Chạy lại AI Compliance Audit sau khi đã sửa các vi phạm Tuần 1-2 | Tất cả | Founder |

### TUẦN 4 — 29/05/2026 → 04/06/2026

| ☐ | Task | Liên quan VP # | Owner |
|---|------|----------------|-------|
| ☐ | Review toàn bộ 5 file Day 22 + 4 file Day 21 với CTO/CMO/legal advisor | Tất cả | Founder |
| ☐ | Email luật sư bạn ngoài 5 file Day 22 để review độc lập (trước deadline DPIA) | VP4, VP5 | Founder |
| ☐ | **Nộp DPIA + CTIA chính thức** — TRƯỚC 07/06/2026 | VP4, VP5 | Founder + Luật sư |
| ☐ | Lên kế hoạch xử lý 5 vi phạm nghiêm trọng nhất theo `compliance_audit_v2.md` | VP1, VP2, VP4, VP5, VP7 | Founder |
| ☐ | Đặt lịch quarterly review compliance (mỗi 3 tháng) | — | Founder |

---

## 3. RECURRING RITUALS

| Tần suất | Ritual | File update | Owner |
|----------|--------|-------------|-------|
| **Hằng tuần (thứ Hai)** | Menu Safety Monday — review 20 menu AI | Nhật ký kiểm thử claim AI | Founder |
| **Hằng tuần** | Review log abuse / incident bất thường | (Khi có payment) Nhật ký giao dịch | Founder |
| **Trước mỗi launch / pitch** | Founder ký phê duyệt marketing content | marketing_claims_audit.md | Founder |
| **Hằng quý** | Review vendor ToS (OpenAI, Google Cloud) | Hồ sơ rà soát vendor | Founder |
| **Hằng quý** | Quarterly compliance review — chạy lại AI Compliance Audit | compliance_audit_v2.md | Founder |
| **Khi đổi luồng dữ liệu** | Update DPIA + CTIA | document_trail.md | Founder |
| **Khi thêm feature mới** | Update PRD + risk assessment | risk_register | Founder |

---

## 4. ESCALATION — KHI NÀO GỌI LUẬT SƯ NGAY

| Tình huống | Hành động |
|-----------|-----------|
| Phát hiện data leak (dù nhỏ) | Gọi luật sư trong 24h + chuẩn bị thông báo cơ quan có thẩm quyền theo PDPL |
| User báo phản ứng sức khỏe nghiêm trọng sau khi follow menu | Kích hoạt incident_playbook.md Day 21 + ghi log + gọi luật sư |
| OpenAI / Google suspend account | Chuyển sang fallback (Anthropic), gọi vendor + luật sư cùng lúc |
| Cơ quan công an / Bộ KH&CN / Bộ TT&TT liên hệ | Không trả lời ngay, gọi luật sư trước trong 4h |
| Báo chí / KOL bóc phốt sản phẩm | Crisis comm + luật sư review trước khi response |

---

## 5. NGÂN SÁCH TUÂN THỦ ƯỚC TÍNH (12 tháng đầu)

| Hạng mục | Chi phí ước tính | Ghi chú |
|----------|-----------------|---------|
| Luật sư review 5 file Day 22 (1 lần) | 5–15 triệu VND | Luật sư chuyên PDPL/AI |
| OpenAI Enterprise (Zero Data Retention) | ~$30–100/tháng | Thay vì plan thường |
| Lakera Guard / Bouncer (input sanitization) | ~$20–30/tháng | Risk Register Risk 5 |
| DPO as a Service (cố vấn part-time) | 3–8 triệu VND/quý | Ân hạn 5 năm theo PDPL nhưng nên có cố vấn |
| Privacy Policy + Terms (luật sư soạn) | 3–8 triệu VND (1 lần) | Chuẩn PDPL |
| **Tổng năm 1 (ước tính)** | **~50–100 triệu VND** | < 0.5% của 500K USD Seed nếu raise được |

> Đây là khoản đầu tư rẻ nhất so với phạt: PDPL Điều 8 phạt **5% doanh thu năm** hoặc **3 tỷ đồng**; Điều 198 BLHS = **tù 1-5 năm**.

---

## 6. LINK LIÊN QUAN

- 📄 [marketing_claims_audit.md](marketing_claims_audit.md) — WS1
- 📄 [territorial_scope.md](territorial_scope.md) — WS2
- 📄 [document_trail.md](document_trail.md) — WS3 (chứa template DPIA + CTIA)
- 📄 [compliance_audit_v2.md](compliance_audit_v2.md) — Lab 4 (8 vi phạm chi tiết)
- 📄 [Day22-AI-Product-Handbook.md](Day22-AI-Product-Handbook.md) — Handbook gốc
- 📄 [../day21/risk_register_v2.md](../day21/risk_register_v2.md) — Phanh nội bộ Day 21
- 📄 [../day21/incident_playbook.md](../day21/incident_playbook.md) — Quy trình xử lý sự cố
