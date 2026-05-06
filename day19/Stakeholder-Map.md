# Checkpoint 1 — Stakeholder Map
## NestAI | cuối Block 1

---

## Câu hỏi 1: Lead VC lý tưởng (specific name)

**→ Do Ventures (Partner: Vy Le)**

| Tiêu chí | Evidence |
|----------|----------|
| Vietnam-first fund | Tập trung thị trường nội địa, không cần exit sang US ngay |
| Portfolio tương tự | Đã invest Jio Health (telehealth Vietnam) → hiểu distribution qua phòng khám |
| Thesis match | Consumer × Health × AI — đúng thesis hiện tại của fund |
| Access | Có thể tiếp cận qua mạng lưới VinUni / startup ecosystem HCM |

**Plan nếu Do Ventures pass:**
- Wavemaker Partners (SEA digital health, có deal tương tự ở Indonesia)
- TNB Aura (focus maternal/women's health SEA)

---

## Câu hỏi 2: Foundation Model dependency + Plan B

**Primary stack:**
- Menu generation: **GPT-4o** (structured output phức tạp: trimester × bệnh lý × region)
- Food recognition: **Google Cloud Vision** + rule-based fallback cho món Việt chưa có trong model

**Rủi ro dependency:**
- OpenAI tăng giá API → unit economics sụp đổ (hiện ~10x GPT-3.5)
- OpenAI restrict medical/nutrition use case (đã từng xảy ra với một số vertical)
- Latency spike ảnh hưởng UX real-time

**Plan B — Multi-model routing:**

| Trigger | Fallback |
|---------|----------|
| OpenAI API down / rate limit | Switch sang **Claude Sonnet** (Anthropic) qua LiteLLM router |
| Chi phí/token vượt threshold | Downgrade menu generation sang **Gemini 1.5 Flash** cho user freemium |
| Vision API unavailable | **AWS Rekognition** + internal lookup table 200 món Việt đã tag sẵn |
| Toàn bộ AI fail | Rule-based engine: chọn thực đơn từ template có sẵn theo bệnh lý × trimester |

**Nguyên tắc:** Không single-vendor dependency. MVP đã thiết kế fallback rule-based để không bao giờ trả về màn hình trắng.

---

## Câu hỏi 3: Early Adopter community cụ thể

**Primary — Facebook Groups (Vietnam):**

| Community | Quy mô (ước tính) | Lý do chọn |
|-----------|-------------------|------------|
| **"Hội Mẹ Bầu Bị Tiểu Đường Thai Kỳ"** | ~30.000–50.000 thành viên | Exact-match pain point — đang tự hỏi "ăn gì" mỗi ngày |
| **"Mẹ Bầu Việt Nam"** | ~500.000 thành viên | Broad reach, filter bằng post tag bệnh lý |
| **"Hội Mẹ Bầu & Sau Sinh"** | ~200.000 thành viên | Active daily questions về dinh dưỡng thai kỳ |

**Secondary — Clinic channel:**
- Phòng khám sản tư tại HCM (Hạnh Phúc, Tâm Anh) → nurse/midwife là influencer thực sự
- OB-GYN groups trên Zalo (bác sĩ recommend → patient trust tăng ngay)

**Access strategy:**
1. Post case study thực tế ("mẹ bầu tuần 26 tiểu đường thai kỳ, đây là thực đơn 7 ngày") → value-first, không bán hàng
2. Partner với 2–3 dietitian có follower trên Facebook/TikTok để seed credibility
3. Pilot với 1 phòng khám sản → bác sĩ recommend → word-of-mouth trong group

---

## Pass/Fail self-check

| Tiêu chí | Status |
|----------|--------|
| Tên VC cụ thể, không generic | ✓ Do Ventures — Vy Le |
| Evidence quỹ đó invest startup tương tự | ✓ Jio Health (telehealth Vietnam) |
| Plan B realistic (multi-model, fallback) | ✓ LiteLLM router + rule-based engine |
| Community thực sự tồn tại, có thể access | ✓ Facebook groups có thể verify và join ngay |
