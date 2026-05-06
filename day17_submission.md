# Day 17 Submission
**Student:** Chu Thị Ngọc Huyền 
**Date:** 24 April 2026
**Product idea:** NestAI — Ứng dụng gợi ý thực đơn dinh dưỡng theo từng giai đoạn thai kỳ, cá nhân hóa theo bệnh lý, tuần thai và sở thích ăn uống, đồng thời cho phép log ảnh bữa ăn để theo dõi vi chất.

---

## 1. MVP Boundary Sheet

**Riskiest Assumption:**
> Phụ nữ mang thai (hoặc có bệnh lý thai kỳ tiểu đường, thiếu máu) sẽ thực sự follow thực đơn AI gợi ý ít nhất 3 ngày/tuần, không chỉ xem rồi bỏ qua như tờ hướng dẫn.

**In-Scope** (tối đa 3):
- [ ] Onboarding & Profile — test giả định: user chấp nhận cung cấp trimester, bệnh lý kèm, vùng miền và dị ứng để nhận menu cá nhân hóa.
- [ ] Menu Generation — test giả định: AI có thể cung cấp thực đơn Việt phù hợp bệnh lý và tuần thai đủ thực tế để user follow.
- [ ] Photo-based Meal Logging — test giả định: user sẽ chụp ảnh bữa ăn và hệ thống có thể ước tính nhanh kcal + vi chất với độ chính xác chấp nhận được.

**Out-of-Scope:**
- Tích hợp dữ liệu xét nghiệm từ bệnh viện — lý do bỏ: partnership lâm sàng quá dài hạn cho MVP.
- Theo dõi cân nặng thai kỳ và BMI gestational — lý do bỏ: secondary need, không validate core assumption.
- Gợi ý supplement cụ thể — lý do bỏ: rủi ro y tế và compliance cao.
- Chat / hỏi đáp tự do với AI — lý do bỏ: scope rộng, khó kiểm soát safety.
- Thanh toán trong app — lý do bỏ: cần validate value trước khi test monetization.
- Android + iOS cùng lúc — lý do bỏ: tập trung 1 platform iOS cho MVP.

**Non-Goals:**
- Thay thế bác sĩ hoặc dietitian lâm sàng.
- Tối ưu hóa cho thị trường ngoài Việt Nam trong 12 tháng đầu.
- Trở thành app dinh dưỡng đa năng cho general population.
- Xây real-time blood glucose monitoring integration.
- Cung cấp kế hoạch ăn kiêng giảm cân trong thai kỳ.

---

## 2. PRD Skeleton

### Problem Statement
> Phụ nữ mang thai hoặc cho con bú không có công cụ tin cậy để biết hôm nay nên ăn gì — thực đơn phù hợp bệnh lý, đúng giai đoạn thai, và là món Việt thực tế có thể mua được ngay.

### Target User
> Phụ nữ mang thai lần đầu tại Việt Nam (22–35 tuổi), đang ở trimester 2 hoặc 3, vừa nhận chẩn đoán tiểu đường thai kỳ hoặc thiếu máu thiếu sắt, có smartphone và đang tự tra cứu thực đơn hàng ngày.

### User Stories
**Story 1:**
> As a mother diagnosed with gestational diabetes at week 26, I want to receive a full-day Vietnamese menu with low-GI dishes suitable for trimester 2, so that I do not have to search Google every morning and can reduce anxiety about blood sugar control.

**Story 2:**
> As a pregnant woman eating lunch at a street food stall, I want to take a photo of my plate and instantly know how much iron and folate I have consumed relative to my weekly target, so that I can decide what to eat for dinner without manually entering each ingredient.

### AI-Specific

**Model Selection:**
- Model: GPT-4o for menu generation; Google Cloud Vision/custom fine-tuned image model cho food recognition.
- Lý do chọn: GPT-4o xử lý tốt structured output với nhiều điều kiện (trimester × bệnh lý × region × preference); Vision API là baseline nhanh và đủ để MVP nhận diện món ăn phổ biến.
- Trade-offs chấp nhận: Chi phí cao hơn GPT-3.5 nhưng cần thiết để giảm rủi ro sai sót khi gợi ý dinh dưỡng cho thai kỳ.
- Trade-offs không chấp nhận: Sai lệch nghiêm trọng trong nutrition advice cho bệnh lý thai kỳ; hallucinate món không tồn tại.

**Data Requirements:**
- Nguồn: Bảng dinh dưỡng thực phẩm Việt Nam (Viện Dinh dưỡng Quốc gia); hướng dẫn dinh dưỡng thai kỳ của WHO/FAO; phác đồ quản lý tiểu đường thai kỳ Bộ Y tế VN; dữ liệu ảnh bữa ăn và corrections từ user.
- Owner: Dietitian nội bộ/partner chịu trách nhiệm nutrition database; product team chịu trách nhiệm quality control với user data.
- Update frequency: Nutrition DB review mỗi 6 tháng; clinical rule update khi phác đồ mới xuất hiện; food recognition retrain mỗi quý với labels user verified.

**Fallback UX:**
- Chiến lược: Human-in-the-loop với expectation management cho những trường hợp chưa đủ tin cậy.
- Trigger: Khi confidence score nhận diện món < 60% hoặc khi model gợi ý món/drug chưa có trong database.
- Hành động: Hiển thị badge "Ước tính (~)" thay vì số tuyệt đối; yêu cầu user xác nhận tên món hoặc chọn món tương tự; nếu user báo triệu chứng bất thường thì hiển thị hotline bác sĩ.
- User options: User có thể sửa tên món, chọn món thay thế, hoặc yêu cầu hệ thống tạo lại thực đơn mới.

### Success Metrics
- Primary metric: Menu compliance rate D14 (tỷ lệ user thực hiện đúng/gần đúng thực đơn ít nhất 7/14 ngày trong 2 tuần đầu).
- Ngưỡng thành công: ≥ 50%.
- Timeframe đo lường: 14 ngày đầu cho compliance; 30 ngày cho retention follow-up.

### Dependencies & Constraints
- Cần source nutrition database Việt Nam valid.
- Cần hệ thống nhận diện món Việt bằng ảnh hoặc fallback lookup.
- Timeline MVP: validate trong 8–12 tuần với 200–500 mẹ bầu tại TP.HCM/Hà Nội.
- Không cần integration bệnh viện hoặc thanh toán trong giai đoạn này.

---

## 3. Hypothesis Table

### Hypothesis 1 (cho tính năng In-Scope #2 — Menu Generation)
> "Chúng tôi tin rằng thực đơn AI cá nhân hóa theo bệnh lý thai kỳ, tuần thai và sở thích sẽ giúp mẹ bầu có tiểu đường hoặc thiếu máu đạt được tỷ lệ follow thực đơn ≥ 50% trong 2 tuần đầu. Chúng tôi sẽ biết mình đúng khi thấy menu compliance rate D14 ≥ 50% trong vòng 14 ngày." 

Riskiest assumption: User sẽ tin tưởng thực đơn AI đủ để thực hiện và không tự bỏ qua vì nghi ngờ tính thực tế.

Cách test cheapest: Launch landing page + survey với sample menu AI mẫu và khảo sát mức độ sẵn sàng thử; dùng Wizard of Oz để đưa các menu gợi ý qua manual editing trước khi có model hoàn chỉnh.

### Hypothesis 2 (cho tính năng In-Scope #3 — Photo-based Meal Logging)
> "Chúng tôi tin rằng việc chụp ảnh bữa ăn và nhận được ước tính nhanh về kcal + vi chất sẽ giúp mẹ bầu quyết định bữa tối bổ sung hơn, giúp ≥ 30% user chụp ≥ 3 ảnh/tuần trong 7 ngày đầu." 

Riskiest assumption: User cảm thấy hành động chụp ảnh bữa ăn là đủ nhẹ nhàng để làm thường xuyên, không phải quá rườm rà.

Cách test cheapest: Tạo prototype landing page mô phỏng flow chụp ảnh và hỏi user xem họ sẵn lòng chụp bao nhiêu ảnh/tuần; chạy thử với 10–20 mẹ bầu để kiểm tra friction.

---

## 4. PMF Scorecard

**Aha Moment:**
> Khi user swap một món không thích và ngay lập tức nhận được món thay thế khác phù hợp bệnh lý kèm lý do dinh dưỡng cụ thể, rồi tiếp tục thực hiện thực đơn đó cho bữa ăn hôm đó.

**Actionable Metric:**
> Menu compliance rate D14 = % user báo cáo đã ăn đúng/gần đúng thực đơn ít nhất 7/14 ngày.

**PMF Method:**
> Sean Ellis + retention tracking
> Ngưỡng thành công: >40% user trả lời "Very disappointed" nếu mất sản phẩm và D30 retention ≥ 35% trong nhóm đạt compliance.

**Vanity Metrics tôi sẽ không dùng:**
- Số lượt tải app.
- Số lần xem thực đơn.
- Tổng số profile created.

---

## 5. AI Critique Log

**Điểm AI chỉ ra:**
1. In-Scope có thể bị scope creep nếu photo-based meal logging được hiểu quá rộng — Action: Partial — giữ tính năng nhưng giới hạn MVP chỉ nhận diện món phổ biến và cho phép user sửa lại.
2. Fallback UX chưa đủ cụ thể về trigger confidence score và edge case khi món không nằm trong database — Action: Accept — bổ sung trigger < 60% và flow yêu cầu user xác nhận/chọn món tương tự.
3. Metric D14 compliance có nguy cơ trở thành vanity nếu chỉ đo "open app" thay vì hành vi thực tế — Action: Accept — định nghĩa rõ metric là user báo cáo đã ăn đúng/gần đúng thực đơn.

**Thay đổi lớn nhất giữa Version A và Version B:**
> Từ phiên bản draft tập trung vào menu generation, tôi mở rộng rõ ràng hơn về cơ chế photo logging và fallback UX, đồng thời định nghĩa metric PMF bằng hành vi thực tế (compliance + retention) thay vì chỉ retention đơn thuần.

---

## 6. Self-assessment

Mắt xích yếu nhất trong [MVP Boundary → PRD → Hypothesis → PMF] là **Hypothesis testing**. Cụ thể, tôi cần rõ hơn cách test riskiest assumption của photo logging và menu generation trước khi build MVP.

Open questions bạn muốn giải đáp tiếp:
1. User có thật sự muốn chụp ảnh bữa ăn mỗi ngày hay chỉ cần lịch ăn sẵn và reminders không?
2. Nếu GPT-4o gợi ý một món không thuần Việt, làm sao hệ thống kịp chuyển sang template "safe Vietnamese meal" cho MVP?
3. Kênh distribution hiệu quả nhất để tiếp cận mẹ bầu bệnh lý thai kỳ ở VN là phòng khám sản hoặc cộng đồng online nào?
