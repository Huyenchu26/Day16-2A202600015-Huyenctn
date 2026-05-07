# Risk Register v2 (AI-Augmented) | NestAI

*Document này tổng hợp 10+ rủi ro hệ thống đã được scan bằng AI CRO Prompt, bao phủ cả 5 type (Vendor, Customer, Founder, Regulatory, Reputational). Top 5 rủi ro nằm trong vùng KILL ZONE (Score ≥ 15) được trang bị Mitigation Plan cụ thể, khả thi cho Founder thực hiện với chi phí < $500/tháng.*

---

## 🔴 TOP 5 RISKS IN KILL ZONE (Priority Mitigation)

### RISK 1: Medical Hallucination (Score: 20)
*   **Type:** Customer-facing
*   **If:** GPT-4o hallucinate (ảo giác), gợi ý sai món ăn cấm kỵ hoặc chỉ số GI cao cho mẹ bầu mắc tiểu đường thai kỳ.
*   **Then:** Bệnh nhân gặp biến chứng đường huyết, bóc phốt trên hội nhóm mẹ bỉm (viral backlash), nguy cơ kiện cáo.
*   **Leading to:** 4 tháng runway lost (đền bù, xử lý khủng hoảng PR, mất sạch user trust).
*   **Likelihood:** 4/5 (Hallucination luôn xảy ra).
*   **Impact:** 5/5 (>6 tháng runway hoặc phá sản).
*   **Mitigation (Cost: ~$30/mo):**
    1.  Tích hợp Guardrails AI (hoặc Bouncer validator) để map output LLM với một whitelist thực phẩm tĩnh chuẩn y khoa ($30/mo).
    2.  Code nút "Soft Kill" bằng feature flag, cho phép chuyển ngay lập tức sang Static Safe Menu chỉ với 1 click ($0/mo).
    3.  Ritual: Founder review 20 AI-generated menus mỗi thứ Hai ("Menu Safety Monday") ($0/mo).

### RISK 2: Founder Hospitalization (Score: 16)
*   **Type:** Founder-bandwidth
*   **If:** Founder (Single point of failure) bị ốm/nhập viện 1 tuần vào đúng lúc server sập hoặc có lỗi thanh toán critical.
*   **Then:** App chết 1 tuần, user auto-renew bị trừ tiền mà không dùng được app.
*   **Leading to:** 2 tháng runway lost (hoàn tiền hàng loạt, user churn vĩnh viễn, đứt gãy tiến độ tung ra sản phẩm).
*   **Likelihood:** 4/5 (Overwork ở startup Seed cực kỳ phổ biến).
*   **Impact:** 4/5 (3-6 tháng runway lost nếu đúng dịp peak).
*   **Mitigation (Cost: ~$10/mo):**
    1.  Viết 1 trang "Emergency Break-Glass" trên Notion chứa hướng dẫn restart server + thông tin account ($0/mo).
    2.  Cấp quyền truy cập dự phòng (AWS/Vercel/Supabase) cho 1 Technical Advisor thân tín ($0/mo).
    3.  Setup UptimeRobot/BetterStack alert: nếu web down 15 phút mà Founder không ACK, tự động gọi điện (phone call) cho Technical Advisor ($10/mo).

### RISK 3: Vendor ToS Ban (Score: 15)
*   **Type:** Vendor
*   **If:** OpenAI đột ngột thay đổi Terms of Service (ToS), cấm tuyệt đối việc dùng API để cung cấp tư vấn y tế/sức khỏe mà không có chứng chỉ bác sĩ.
*   **Then:** Account NestAI bị suspend ngay trong đêm không báo trước, tính năng generate thực đơn sập hoàn toàn.
*   **Leading to:** 3 tháng runway lost (ngưng phát triển tính năng, viết lại code sang nhà cung cấp LLM khác).
*   **Likelihood:** 3/5 (Trào lưu thắt chặt AI safety của các big tech).
*   **Impact:** 5/5 (Core feature tê liệt).
*   **Mitigation (Cost: ~$25/mo):**
    1.  Code một Abstraction Layer (LLM Router) trên backend, không hard-code thư viện OpenAI ($0/mo).
    2.  Setup sẵn account backup ở Anthropic (Claude 3.5 Sonnet) và build 1 fallback prompt cơ bản ($25/mo pay-as-you-go credit standby).
    3.  Lưu cache các thực đơn tốt nhất vào database để làm fallback menu dài hạn ($0/mo).

### RISK 4: SaMD Classification (Score: 15)
*   **Type:** Regulatory
*   **If:** Bộ Y tế hoặc Apple App Store phân loại tính năng "AI tư vấn thực đơn tiểu đường thai kỳ" là Software as a Medical Device (SaMD) do tính chất điều trị bệnh.
*   **Then:** NestAI bị gỡ khỏi App Store và bị cấm hoạt động cho đến khi có chứng chỉ lâm sàng (tốn hàng tỷ đồng và vài năm).
*   **Leading to:** 6 tháng runway lost (chấm dứt hoạt động MVP hiện tại, pivot hoàn toàn).
*   **Likelihood:** 3/5 (Ranh giới giữa "wellness app" và "medical app" rất mỏng).
*   **Impact:** 5/5 (>6 tháng runway lost).
*   **Mitigation (Cost: $0/mo):**
    1.  Chèn disclaimer bắt buộc click đồng ý lúc Onboarding: *"NestAI là công cụ tham khảo dinh dưỡng, KHÔNG thay thế phác đồ điều trị của bác sĩ"* ($0/mo).
    2.  Trong PRD và Marketing, tuyệt đối tránh các từ "chữa", "điều trị", "phác đồ" (chỉ dùng "hỗ trợ", "gợi ý", "tham khảo") ($0/mo).
    3.  Update Prompt hệ thống: Cấm AI không bao giờ được đưa ra chẩn đoán bệnh hay khuyên dùng thuốc ($0/mo).

### RISK 5: Toxic Prompt Injection (Score: 15)
*   **Type:** Reputational
*   **If:** Một user ác ý nhập "prompt injection", lừa chatbot gọi user là "đồ béo ú" hoặc xúi giục nhịn ăn giảm cân trong thai kỳ.
*   **Then:** User quay video màn hình đăng TikTok, chê trách NestAI miệt thị ngoại hình (body-shaming) mẹ bầu.
*   **Leading to:** 3 tháng runway lost (Khủng hoảng truyền thông, bị tẩy chay trên các group mẹ bỉm, tốn tiền đền bù/PR).
*   **Likelihood:** 3/5 (Bảo mật prompt rất khó lường trước người dùng cố tình tìm lỗi).
*   **Impact:** 5/5 (Mất trust hoàn toàn ở tệp mẹ bầu).
*   **Mitigation (Cost: ~$20/mo):**
    1.  Cài đặt Input Sanitization bằng regex hoặc dùng Lakera Guard chặn các prompt có chứa từ khóa bạo lực, miệt thị ($20/mo).
    2.  Add strict system guardrail: "Bạn là AI tử tế. Không bao giờ nhận xét về cân nặng hoặc vóc dáng người dùng" ($0/mo).
    3.  Dùng Helicone (Free tier) để review định kỳ các session chat dài bất thường (dấu hiệu user đang cố jailbreak) ($0/mo).

---

## 🟡 CÁC RISKS CẦN THEO DÕI (WATCH & MITIGATE GRADUALLY)

### RISK 6: Inaccurate Image Logging (Score: 12)
*   **Type:** Customer-facing
*   **If:** AI nhận diện ảnh sai bét (VD: nhận nhầm bánh mì ngọt thành bánh mì nguyên cám), báo sai lượng Carb.
*   **Then:** User tiểu đường tin tưởng ăn theo, đường huyết vọt lên; user giận dữ report app và uninstall.
*   **Leading to:** 1 tháng runway lost (Tụt giảm Retention nghiêm trọng, tốn tiền thu hút user mới bù vào lỗ hổng).
*   **Likelihood:** 4/5
*   **Impact:** 3/5

### RISK 7: Feature Creep & Burnout (Score: 12)
*   **Type:** Founder-bandwidth
*   **If:** Founder cố gắng đắp thêm tính năng tích hợp dữ liệu xét nghiệm viện (Out-of-scope) để làm hài lòng một vài nhà đầu tư.
*   **Then:** Code core feature bị lơi lỏng, MVP bị delay ra mắt 2 tháng, Founder kiệt sức.
*   **Leading to:** 2 tháng runway lost (Burn rate đốt không ra kết quả launch).
*   **Likelihood:** 4/5
*   **Impact:** 3/5

### RISK 8: Decree 13 Privacy Violation (Score: 12)
*   **Type:** Regulatory
*   **If:** App gửi thẳng các dữ liệu y tế nhạy cảm (tuần thai, bệnh lý thai kỳ, tên thật) qua API của OpenAI qua dạng plain text mà không ẩn danh (anonymize), vi phạm Nghị định 13 bảo vệ dữ liệu cá nhân VN.
*   **Then:** Nếu có data leak hoặc regulator thanh tra, startup chịu phạt nặng.
*   **Leading to:** 3 tháng runway lost (Phạt hành chính + chi phí thuê luật sư + audit lại hệ thống).
*   **Likelihood:** 3/5
*   **Impact:** 4/5

### RISK 9: OpenAI API Rate Limit Hit (Score: 8)
*   **Type:** Vendor
*   **If:** Vào giờ vàng ăn trưa (11h-12h), lượng mẹ bầu truy cập quá tải, chạm ngưỡng OpenAI Rate Limit.
*   **Then:** App văng lỗi 500 timeout cho 30% active users.
*   **Leading to:** <1 tháng runway lost (Churn rate tăng nhẹ, trải nghiệm tệ cục bộ).
*   **Likelihood:** 4/5
*   **Impact:** 2/5

### RISK 10: Third-party Image API Price Hike (Score: 4)
*   **Type:** Vendor
*   **If:** Google Cloud Vision (hoặc vendor nhận diện ảnh) tăng giá API call lên 3x vào năm tới.
*   **Then:** Unit economics của feature Photo Logging bị âm, startup lỗ trên mỗi user scan ảnh.
*   **Leading to:** <1 tháng runway lost (Phải tạm tắt tính năng hoặc giới hạn số lần chụp ảnh mỗi ngày).
*   **Likelihood:** 2/5
*   **Impact:** 2/5
