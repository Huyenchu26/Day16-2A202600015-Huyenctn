# Workshop 1 — Risk Governance | NestAI
## Day 21

---

## Risk được chọn

**AI Hallucination trong Medical Nutrition Advice cho bệnh lý thai kỳ**

> PRD ghi tường minh: *"Trade-off không chấp nhận: Sai lệch nghiêm trọng trong nutrition advice cho bệnh lý thai kỳ; hallucinate món không tồn tại."*

Đây là risk lớn nhất vì: severity cao nhất (ảnh hưởng sức khỏe mẹ và thai nhi), probability trung bình-cao (LLM vẫn hallucinate kể cả GPT-4o), và nếu xảy ra → pháp lý + mất trust toàn bộ cộng đồng mẹ bầu cùng lúc.

---

## R1 — RULES

**1. Cấm cụ thể**
Cấm GPT-4o (OpenAI) sinh free-form text nutrition recommendation trực tiếp cho user có bệnh lý thai kỳ (tiểu đường, thiếu máu, cao huyết áp) mà không đi qua validation layer với constrained whitelist. Cấm tuyệt đối bypass validation layer dù lý do là test, demo, hay deadline áp lực.

**2. Allowed alternative**
GPT-4o chỉ được dùng để **SELECT và RANK** từ whitelist 200 món Việt đã được dietitian partner verify dinh dưỡng value — output phải là structured JSON chọn từ enum hợp lệ, không sinh free-form tên món mới. Cost: ~$0.03/call × 1.000 user = ~$30/tháng.

**3. Hậu quả vi phạm**
Bypass validation layer hoặc push code skip whitelist check → founder 1:1 ngay trong 24h (lần 1, documented). Tái phạm → let go không cần performance plan. Zero tolerance vì một hallucination đến sai user có thể gây biến chứng thai kỳ và liability pháp lý không giới hạn.

**4. Update mechanism**
Notion doc: **"NestAI Clinical Safety Rulebook"** — review bắt buộc mỗi quý (Q1/Q2/Q3/Q4) hoặc trong vòng 48h khi có bất kỳ incident nào bị Guardrails flag. Mọi thay đổi whitelist phải có sign-off từ dietitian partner trước khi merge.

---

## R2 — RAILS

### Tool 1 · Guardrails AI
**guardrailsai.com** — Output validation tự động trước khi trả về client.

- **Cơ chế:** Mọi LLM output đi qua validator trước khi hiển thị. Validator check: (a) tên món có trong whitelist không, (b) nutrition values có nằm trong range WHO/Bộ Y tế cho GD/anemia không (GI < 55 cho tiểu đường; sắt ≥ 8mg/ngày cho thiếu máu), (c) không có từ khoá contraindicated ("kiêng" + tên thuốc, etc.).
- **Khi fail:** Trả về món thay thế an toàn nhất trong whitelist, không trả về output gốc.
- **Cost:** $0/tháng (open source, self-host) hoặc $29/tháng (hosted, không cần infra).

### Tool 2 · Sentry
**sentry.io** — Runtime monitoring và anomaly alerting.

- **Cơ chế:** Custom alert khi: (a) Guardrails flag rate > 5% trong bất kỳ 1 giờ nào, (b) compliance rate drop > 10% week-over-week (proxy signal rằng menu quality đang giảm), (c) user swap liên tiếp > 3 lần trong 1 thực đơn (signal thực đơn không thực tế).
- **Alert channel:** Slack #safety-alerts → founder + lead engineer nhận ngay.
- **Cost:** $26/tháng (Team plan, 1 project, 50K errors/tháng).

**Tổng cost R2: $29 + $26 = $55/tháng** — bảo vệ toàn bộ medical liability risk.

---

## R3 — RITUAL

### "Menu Safety Monday" — mỗi thứ Hai, 30 phút

**Ai tham gia:** Founder + 1 engineer + dietitian partner (async nếu cần).

**Quy trình:**
1. Pull Sentry dashboard: xem Guardrails flag rate và compliance rate 7 ngày qua.
2. Random sample 20 AI-generated menus từ tuần trước — đọc như một mẹ bầu có tiểu đường thai kỳ.
3. Check: có menu nào vượt GI threshold không? Có món nào không có trong whitelist không?
4. Log findings vào Notion "Weekly Safety Log" — kể cả khi không có issue (zero-incident cũng phải ghi).

**Question founder hỏi customer (2 user mỗi tuần):**
> *"Tuần này có món nào bạn nghi ngờ không phù hợp với bệnh lý của bạn không? Bạn có tự search Google để double-check bất kỳ gợi ý nào của NestAI không?"*

**Question founder hỏi team (mỗi standup thứ Hai):**
> *"Guardrails đã flag bao nhiêu output tuần này? Output nào bị flag và tại sao nó vượt qua được prompt engineering của chúng ta?"*

> Nếu câu trả lời là "không có gì để báo cáo" 2 tuần liên tiếp → đây là signal tốt, nhưng founder phải hỏi thêm: *"Guardrails có đang hoạt động không, hay chúng ta đang không detect được?"*
