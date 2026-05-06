# Workshop 1 — RICE Prioritization & 2×2 Value-Effort
## NestAI | Day 20

> **Scope:** MVP pilot ~500 mẹ bầu tại TP.HCM/Hà Nội, đo theo quý.
> **Formula:** Score = (Reach × Impact × Confidence) / Effort

---

## Bước 1 — 5 Tính năng & Chấm RICE

### F1 · Onboarding & Profile Setup
Collect trimester, bệnh lý (tiểu đường / thiếu máu), vùng miền, dị ứng → personalize menu.

| Yếu tố | Giá trị | Lý do |
|--------|---------|-------|
| **Reach** | 500 user/quý | 100% user phải đi qua — gate bắt buộc |
| **Impact** | 0.5 | Không tạo WOW moment, chỉ enable các tính năng sau |
| **Confidence** | 100% | Certainty cao — đây là form thu thập data |
| **Effort** | 0.5 PM | Form + validation + lưu profile, không phức tạp |
| **Score** | **(500 × 0.5 × 1.0) / 0.5 = 500** | |

---

### F2 · AI Menu Generation (daily, bệnh lý × tuần thai × sở thích)
GPT-4o sinh thực đơn cả ngày (sáng/trưa/tối/snack) gồm món Việt, chuẩn GI, đúng trimester.

| Yếu tố | Giá trị | Lý do |
|--------|---------|-------|
| **Reach** | 500 user/quý | Core feature — toàn bộ user dùng hằng ngày |
| **Impact** | 3 | Giải quyết pain chính: "không biết ăn gì mỗi sáng" |
| **Confidence** | 80% | Riskiest assumption chưa validate: compliance ≥ 50% |
| **Effort** | 2 PM | GPT-4o prompt engineering + nutrition DB Việt + structured output + QA |
| **Score** | **(500 × 3 × 0.8) / 2 = 600** | |

---

### F3 · Instant Meal Swap + Nutrition Reasoning
User tap vào 1 món → nhận ngay món thay thế cùng lý do dinh dưỡng ("Đổi bún bò → cháo thịt bằm vì GI thấp hơn, cùng lượng sắt").

| Yếu tố | Giá trị | Lý do |
|--------|---------|-------|
| **Reach** | 400 user/quý | ~80% user dùng menu sẽ swap ít nhất 1 lần/tuần |
| **Impact** | 3 | ĐÂY LÀ AHA MOMENT — khi user swap và tin hệ thống, habit bắt đầu |
| **Confidence** | 80% | Aha moment được identify rõ, nhưng chưa validate quy mô |
| **Effort** | 1 PM | Extension của F2 — cùng model, thêm swap logic + UX |
| **Score** | **(400 × 3 × 0.8) / 1 = 960** | |

---

### F4 · Photo-based Meal Logging (Food Recognition)
Chụp ảnh bữa ăn → nhận ước tính kcal + sắt + folate so với target tuần thai. Dùng GCP Vision + fallback manual lookup.

| Yếu tố | Giá trị | Lý do |
|--------|---------|-------|
| **Reach** | 150 user/quý | Target: 30% user chụp ≥ 3 ảnh/tuần — ước tính thực tế thấp hơn |
| **Impact** | 2 | Valuable cho tracking, nhưng secondary — menu generation vẫn có giá trị không cần photo |
| **Confidence** | 50% | Kỹ thuật nhận diện món Việt chưa đủ mature; friction chụp ảnh chưa biết có vượt qua được không |
| **Effort** | 3 PM | GCP Vision integration + Vietnamese food dataset + fallback UI + correction flow |
| **Score** | **(150 × 2 × 0.5) / 3 = 50** | |

---

### F5 · Daily Nutrition Summary / Progress View
Hiển thị tổng kết cuối ngày: đã đạt bao nhiêu % target sắt, folate, kcal so với tuần thai. Visual chart đơn giản.

| Yếu tố | Giá trị | Lý do |
|--------|---------|-------|
| **Reach** | 350 user/quý | ~70% active user sẽ check cuối ngày khi đã có thói quen |
| **Impact** | 1 | Reinforcement loop tốt, nhưng không drive adoption đầu tiên |
| **Confidence** | 80% | Feature đơn giản, certainty cao về execution |
| **Effort** | 1 PM | Pull data từ menu + photo log, render chart — không cần AI mới |
| **Score** | **(350 × 1 × 0.8) / 1 = 280** | |

---

## Bước 2 — Bảng tổng hợp RICE (xếp hạng)

| # | Tính năng | Reach | Impact | Confidence | Effort (PM) | **RICE Score** |
|---|-----------|-------|--------|------------|-------------|----------------|
| 1 | F3 Instant Meal Swap | 400 | 3 | 80% | 1 | **960** |
| 2 | F2 AI Menu Generation | 500 | 3 | 80% | 2 | **600** |
| 3 | F1 Onboarding & Profile | 500 | 0.5 | 100% | 0.5 | **500** |
| 4 | F5 Nutrition Summary | 350 | 1 | 80% | 1 | **280** |
| 5 | F4 Photo Meal Logging | 150 | 2 | 50% | 3 | **50** |

---

## Bước 3 — 2×2 Value × Effort Matrix

> **Value** = Impact × Confidence | **Effort** = person-months

```
HIGH VALUE
(Impact × C)
    │
2.4 │   [F3 Meal Swap]  ║  [F2 Menu Gen]
    │    QUICK WIN      ║  STRATEGIC BET
    │                   ║
────┼───────────────────╬───────────────────
    │                   ║
0.8 │   [F5 Nutrition]  ║  [F4 Photo Log]
    │    Fill-in        ║  NON-STARTER
    │                   ║
    └───────────────────╨───────────────────
        Low Effort              High Effort
         (≤ 1 PM)               (≥ 2 PM)
```

*[F1 Onboarding: Value=0.5, Effort=0.5 → Table Stakes — làm đầu tiên vì prerequisite, không phải vì score cao]*

---

## Quyết định

### ✅ Quick Win — F3: Instant Meal Swap
**Làm ngay, trong sprint 1 cùng F2.**
- RICE cao nhất (960), effort chỉ 1 PM
- Đây là Aha Moment đã được identify trong PRD — nếu user swap và tin hệ thống, D30 retention theo sau
- Là extension của Menu Generation, không cần stack mới
- **Rủi ro:** Nếu swap logic không đủ nhanh (<2s), moment bị phá vỡ → cần SLA rõ ràng

### 🏰 Strategic Bet — F2: AI Menu Generation
**Core moat — xây để win dài hạn.**
- Effort cao (2 PM) nhưng đây là data flywheel: mỗi user compliance → ground truth → model tốt hơn → moat không ai copy được
- Cần Vietnamese nutrition DB + dietitian review → barrier to entry thực sự
- Không có F2, F3 và F5 đều không có giá trị
- **Rủi ro:** GPT-4o hallucinate món → cần guardrail bằng constrained output + whitelist 200 món Việt đã verify

### ❌ Non-starter — F4: Photo-based Meal Logging
**Bỏ khỏi MVP, xem xét lại sau quý 2.**
- RICE score thấp nhất (50) — gap quá lớn so với phần còn lại
- Confidence chỉ 50%: kỹ thuật nhận diện món Việt phức tạp chưa đủ mature cho MVP
- Effort cao nhất (3 PM) — chiếm toàn bộ bandwidth nếu đưa vào MVP
- Submission PRD đã note đây là "riskiest assumption" của Hypothesis 2
- **Nếu muốn giữ signal:** Thay bằng manual log (user gõ tên món) → validate behavior trước khi build Vision pipeline
