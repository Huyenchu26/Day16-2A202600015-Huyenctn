# MVP Boundary — MamaMenu AI

> **Phạm vi MVP:** Validate được core assumption trong 8–12 tuần với ~200–500 mẹ bầu tại TP.HCM / Hà Nội, không cần bất kỳ tích hợp bệnh viện nào.

---

## In-Scope (MVP phải có để validate được)

### 1. Onboarding & Profile
- Thu thập thông tin cơ bản: tuần thai hiện tại (hoặc trimester), tình trạng bệnh lý kèm theo (tiểu đường thai kỳ / thiếu máu / không có / khác), số bữa chính mỗi ngày
- Ghi nhận sở thích ẩm thực tối thiểu: khu vực địa lý (Bắc / Trung / Nam), có bếp nấu không, dị ứng thực phẩm chính (nếu có)
- Không yêu cầu đăng nhập phức tạp — phone number + OTP là đủ cho MVP

### 2. Menu Generation (Need #1 — priority need)
- AI sinh thực đơn ngày (3 bữa + 1–2 snack) cá nhân hóa theo:
  - Trimester hiện tại
  - Bệnh lý kèm (tiểu đường thai kỳ → ưu tiên low GI; thiếu máu → ưu tiên thực phẩm giàu sắt)
  - Ẩm thực Việt: tất cả món gợi ý phải là món Việt quen thuộc, có thể mua ở chợ hoặc quán cơm
- Hiển thị lý do ngắn gọn tại sao món này phù hợp (ví dụ: "Rau muống giàu folate — tốt cho tuần 16–20")
- Cho phép swap từng món ("Không thích bún bò → gợi ý món khác")

### 3. Photo-based Meal Logging (Need #2 — barrier reduction)
- Chụp ảnh bữa ăn → hệ thống nhận diện món và ước tính kcal + 4 vi chất chính (sắt, folate, canxi, DHA)
- Hiển thị progress bar vi chất so với target của tuần thai hiện tại
- Cho phép user sửa tên món nếu AI nhận diện sai (→ thu thập ground truth label)
- **Accuracy yêu cầu MVP:** ±20% kcal là chấp nhận được trong giai đoạn đầu; cần benchmark với 50–100 ảnh bữa ăn Việt trước khi launch

### 4. Vietnamese Food Database (hạ tầng cốt lõi)
- Minimum viable database: 150–200 món Việt phổ biến nhất với macro + 4 vi chất thai kỳ (sắt, folate, canxi, DHA/omega-3)
- Tập trung vào các món phổ biến trong cộng đồng mẹ bầu: cơm tấm, bún bò, phở, canh rau, trứng, thịt heo/gà/bò, các loại rau xanh thông thường
- Không cần đủ 100% chính xác ngay — ưu tiên coverage (có đủ món) hơn precision

### 5. Feedback Loop cơ bản
- Sau mỗi ngày: "Hôm nay bạn có theo thực đơn không?" (Yes / Một phần / Không)
- Nếu không: ghi nhận lý do đơn giản (Không có nguyên liệu / Không thích / Không có thời gian)
- Dữ liệu này là input để cải thiện recommendation — không cần dashboard phức tạp

---

## Out-of-Scope (không build trong MVP)

| Feature | Lý do loại khỏi MVP |
|---|---|
| Tích hợp dữ liệu xét nghiệm từ bệnh viện (HbA1c, hemoglobin) | Đòi hỏi partnership lâm sàng — quá dài để setup trong MVP timeline |
| Theo dõi cân nặng thai kỳ và tính BMI gestational | Secondary need — không validate được core assumption nhanh hơn |
| Gợi ý supplement (loại, liều lượng, brand) | Rủi ro y-pháp cao nếu tư vấn sai; cần medical review board trước |
| Chat / hỏi đáp tự do với AI về dinh dưỡng | Scope rộng, khó kiểm soát safety; ngoài phạm vi meal planning |
| Tích hợp với app theo dõi thai kỳ khác (Ovia, BabyCenter) | API không có sẵn; không cần thiết để validate core assumption |
| Tính năng cộng đồng / forum / chia sẻ thực đơn | Nice-to-have; có thể add sau khi retention được validate |
| Thanh toán trong app | MVP có thể free hoàn toàn để tối đa hóa data collection và validate WTP qua survey |
| Android + iOS cùng lúc | Ra mắt trên 1 platform (iOS ưu tiên — demographics mẹ bầu VN) |
| Hỗ trợ giai đoạn cho con bú | Scope thêm; focus vào mang thai trước |
| Đa ngôn ngữ (English, Tiếng Anh) | Chỉ Tiếng Việt cho MVP tại thị trường VN |

---

## Non-Goals (không phải mục tiêu, kể cả dài hạn nếu không có evidence)

### 1. Thay thế bác sĩ hoặc dietitian lâm sàng
MamaMenu không phải và không được định vị như công cụ chẩn đoán hoặc điều trị. Mọi output đều là gợi ý dinh dưỡng dựa trên hướng dẫn y tế chuẩn, không phải chỉ định của bác sĩ. Disclaimer này phải hiện diện rõ ràng trong UI.

### 2. Tối ưu hóa cho thị trường ngoài Việt Nam trong 12 tháng đầu
Toàn bộ ưu tiên — food database, UX copy, distribution channel — được thiết kế cho người dùng Việt Nam. Mở rộng SEA (Thailand, Philippines) chỉ xảy ra sau khi có product-market fit tại VN.

### 3. Trở thành app dinh dưỡng đa năng (general population)
MamaMenu không phục vụ người dùng không mang thai / không cho con bú. Mở rộng sang general wellness sau này đòi hỏi repositioning hoàn toàn và có thể loãng moat thai kỳ.

### 4. Xây real-time blood glucose monitoring integration
Dù hấp dẫn về mặt kỹ thuật, việc tích hợp CGM (continuous glucose monitor) hoặc dữ liệu xét nghiệm lab là out-of-scope cho ít nhất 18–24 tháng đầu do rào cản regulatory và chi phí partnership.

### 5. Cung cấp kế hoạch ăn kiêng để giảm cân trong thai kỳ
Giảm cân khi mang thai là medically contraindicated trong hầu hết trường hợp. MamaMenu không hỗ trợ caloric restriction; mục tiêu là đủ chất, không phải ít calo.

---

## MVP Success Criteria (để biết có nên build tiếp không)

| Metric | Target sau 8 tuần | Ý nghĩa |
|---|---|---|
| D14 retention | ≥ 40% | User thấy giá trị đủ để quay lại sau 2 tuần |
| Menu compliance rate | ≥ 50% | Gợi ý đủ thực tế để user thực sự thực hiện |
| Photo logging D7 | ≥ 30% user chụp ≥ 3 ảnh/tuần | Photo barrier không quá cao để duy trì |
| WTP signal | ≥ 25% sẵn sàng trả ≥ 49k VND/tháng | Validate monetization trước khi freemium → paid |
| NPS | ≥ 40 | Đủ để word-of-mouth tự nhiên trong cộng đồng mẹ bầu |

---

## 📋 Key Assumptions MVP Này Cần Validate

1. **Mẹ bầu VN sẽ chụp ảnh bữa ăn thường xuyên** — nếu không, core mechanic của Need #2 không hoạt động và cần pivot sang text-based logging hoặc pre-set meal selection
2. **AI menu generation từ LLM đủ accurate và "Việt" để user follow được** — nếu gợi ý vẫn "lạ" dù đã prompt engineering, cần human dietitian curate bộ 500–1000 "safe meal templates" trước
3. **Bệnh lý thai kỳ là trigger đủ mạnh để khiến user onboard và trả tiền** — nếu chỉ mẹ bầu khỏe mạnh dùng, segment có thể đúng nhưng WTP thấp hơn kỳ vọng

