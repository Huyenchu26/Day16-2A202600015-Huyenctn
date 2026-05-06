# Workshop 4 — Risk Dependencies + Critical Path
## NestAI | Investor Package — tài liệu cuối

---

## 3 External Dependencies có thể giết dự án trong 30 ngày

---

### D1 · OpenAI API — Pricing & Availability

| | |
|--|--|
| **Worst case** | OpenAI tăng giá GPT-4o hoặc áp rate limit nghiêm → chi phí per-user vượt ngưỡng unit economics, toàn bộ menu generation bị chặn. |
| **Plan B** | Switch sang Claude Sonnet (Anthropic) qua LiteLLM router — prompt đã chuẩn hoá theo structured output, chỉ cần thay endpoint và test nutrition output format trên staging. |
| **Cost** | $0 setup + **3–5 ngày kỹ thuật** để validate output quality với nutrition test cases. |

---

### D2 · Apple App Store Review — Health/Medical Category

| | |
|--|--|
| **Worst case** | App bị reject vì claim "hỗ trợ tiểu đường thai kỳ" bị Apple classify là medical device → không thể launch iOS trong 30 ngày. |
| **Plan B** | Launch Progressive Web App (PWA) phân phối qua link trực tiếp trong Facebook groups mẹ bầu — user cài bằng "Add to Home Screen", không cần App Store. |
| **Cost** | $0 + **2 ngày kỹ thuật**; đánh đổi: mất push notification native nhưng đủ để chạy pilot 500 user đầu tiên. |

---

### D3 · Viện Dinh dưỡng Quốc gia — Data Access & Legal Basis

| | |
|--|--|
| **Worst case** | Không ký được thoả thuận sử dụng dữ liệu → nutrition DB thiếu legal backing, không thể publish bất kỳ nutrition claim nào cho bệnh lý. |
| **Plan B** | Dùng USDA FoodData Central (public domain) làm base + thuê 1 dietitian freelance build và verify Vietnamese food mapping cho 150 món phổ biến nhất. |
| **Cost** | **$2,000–3,000 USD** + **10 ngày** để build mapping table đủ cho MVP; dietitian sign-off đồng thời tạo credibility signal với bác sĩ sản. |

---

## Critical Path — NOW Tasks

> `→` = task sau không bắt đầu được nếu task trước chưa xong.

```
CRITICAL PATH (chuỗi dài nhất):

 [T1 Nutrition DB] → [T2 Menu Generation] → [T3 Meal Swap] → [T4 App Build] → [T5 Launch]
      10 ngày              14 ngày               7 ngày           5 ngày        7–14 ngày
      ★ BLOCK              ★ BLOCK               ★ BLOCK          ★ BLOCK

PARALLEL (không blocking critical path):

 [T0 Onboarding & Profile] ──────────────────────────────────────→ merge vào T4
       5 ngày (chạy cùng T1)

 [T6 Pilot Recruitment — 500 mẹ bầu via Facebook groups] ══════════ chạy suốt
       Không blocking, nhưng nếu trễ → launch không có user
```

**Tổng thời gian Critical Path:**

| Kịch bản | Thời gian |
|----------|-----------|
| App Store approve nhanh | 10+14+7+5+7 = **43 ngày** |
| App Store reject → PWA Plan B | 10+14+7+5+2 = **38 ngày** |

---

### Task nào slip = toàn bộ slip

| Task | Blocking | Hậu quả nếu trễ 1 tuần |
|------|----------|------------------------|
| **T1 Nutrition DB** | T2 → T3 → T4 → T5 | Không có data → không có menu → không có gì để launch |
| **T2 Menu Generation** | T3 → T4 → T5 | Core feature chưa xong → Aha Moment không xảy ra |
| **T3 Meal Swap** | T4 → T5 | Pilot không validate được PMF — KR1 không đo được |
| **T5 App Store Review** | Launch | Kích hoạt D2 Plan B (PWA) trong 2 ngày — không chờ |

**T0 và T6 không blocking** — ưu tiên song song ngay từ ngày 1 để tiết kiệm tổng thời gian.

---

*Trigger rule: Nếu D3 (Nutrition DB) không resolve trong **7 ngày đầu** → kích hoạt USDA Plan B ngay, không chờ đàm phán tiếp.*
