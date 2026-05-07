# Incident Playbook: AI Hallucination & Viral Backlash

*Ngữ cảnh: 9h30 sáng. Customer tweet screenshot AI của NestAI nói sai 1 thông tin về sản phẩm (VD: gợi ý sai món cho tiểu đường thai kỳ). 200 retweets trong 30 phút. Signal viral.*

## Bước 1. Verify (3 phút)

**Bạn check log ở đâu?**
*   **Database (Supabase):** Truy vấn bảng `user_menus` hoặc `chat_history` của user đó để xem hệ thống có thực sự trả về kết quả như screenshot không.
*   **Sentry / Guardrails AI Logs:** Kiểm tra dashboard xem có spike nào về cảnh báo an toàn y tế hoặc flag bypass trong khung giờ đó không.
*   **Helicone (nếu có dùng):** Check raw prompt và raw completion của OpenAI để xem lỗi do LLM hallucinate hay do lỗi logic hiển thị ở frontend.

**Cách verify nhanh đó là AI thật vs photoshop?**
*   Tìm chuỗi text chính xác (exact match) từ screenshot trong Database log.
*   Khớp timestamp (thời gian) trên screenshot với thời gian request trong log của user.
*   Nếu có text match và timestamp khớp → **Thật**. Nếu không có bất kỳ log nào chứa text đó → **Khả năng cao là Photoshop/Fake**.

---

## Bước 2. Stop the bleeding (5 phút)

**Quyết định: Chọn SOFT (Soft Degradation / Tạm ngưng tính năng một phần)**

**Lý do:**
*   **Tại sao không Hard?** Đóng toàn bộ app sẽ gây hoang mang cho các user khác không bị ảnh hưởng, ảnh hưởng đến trust tổng thể.
*   **Tại sao không Block/Tighten ngay?** Sửa prompt hoặc update Guardrails cần thời gian test. Trong lúc test, nếu AI tiếp tục nói sai y tế cho mẹ bầu khác sẽ dẫn đến hậu quả nghiêm trọng hơn. 
*   **Hành động Soft cụ thể:** Lập tức toggle cờ (feature flag) để **tắt tính năng "AI Generate Menu"**. Giao diện sẽ tự động fallback về "Static Safe Menu" (thực đơn tĩnh, chuẩn y khoa 100% đã được chuyên gia dinh dưỡng duyệt sẵn). Hệ thống vẫn chạy, user vẫn có thực đơn an toàn, trong khi team có thời gian rà soát nguyên nhân gốc rễ.

---

## Bước 3. Customer Comm (5 phút)

*Gửi DM trực tiếp cho user bị ảnh hưởng từ tài khoản X (Twitter) của Founder.*

> "Chào bạn, mình là Huyền, Founder của NestAI. Cảm ơn bạn đã cảnh báo công khai về lỗi gợi ý thực đơn này.
>
> Mình thực sự xin lỗi vì sai sót này đã làm bạn lo lắng. Sức khỏe của mẹ và bé là lằn ranh đỏ của NestAI, và bọn mình đã thất bại trong việc bảo vệ lằn ranh đó ở trường hợp của bạn. 
>
> Bọn mình đã lập tức tạm ngưng tính năng AI sinh thực đơn tự động cho tất cả user để rà soát lại toàn bộ bộ lọc an toàn (whitelist). Bọn mình sẽ chỉ mở lại khi chuyên gia dinh dưỡng đã xác nhận không còn lỗ hổng.
>
> Để thể hiện sự chân thành, mình đã hoàn trả 100% phí đăng ký của bạn và gửi tặng bạn gói Premium trọn đời. Dù bạn có tiếp tục dùng NestAI hay không, mình vẫn muốn gửi lời xin lỗi sâu sắc nhất. Mình sẽ update công khai nguyên nhân và cách khắc phục trong hôm nay."

---

## Bước 4. Public Response (2 phút)

*Tweet từ tài khoản X của Founder (đăng dưới dạng Quote Tweet lại bài của user hoặc Reply trực tiếp):*

> Cảm ơn cộng đồng đã báo cáo lỗi gợi ý dinh dưỡng của NestAI. An toàn y tế của mẹ bầu là tối thượng. Chúng tôi đã tạm ngưng tính năng AI này và chuyển sang thực đơn tĩnh an toàn 100% để rà soát bộ lọc whitelist. Sẽ có báo cáo khắc phục minh bạch trong 24h tới. 🙏
