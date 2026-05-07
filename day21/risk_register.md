# Risk Register | NestAI

## Bước 1 & Bước 2 & Bước 3: Phân tích 3 rủi ro cốt lõi

### 1. Vendor Risk (OpenAI Dependency)
*   **If:** OpenAI bất ngờ cập nhật Terms of Service (ToS) cấm sử dụng API cho các ứng dụng có tính chất tư vấn y tế/sức khỏe (hoặc tăng giá API đột ngột gấp nhiều lần như case của nhiều API provider khác).
*   **Then:** Tính năng cốt lõi "Menu Generation" dựa trên GPT-4o bị sập hoàn toàn, buộc team phải khẩn cấp chuyển đổi (migrate) sang một LLM khác (như Claude 3.5 Sonnet hoặc self-host Llama 3).
*   **Leading to:** **Mất 2 tháng runway** (Toàn bộ team phải ngưng phát triển tính năng mới để viết lại prompt, setup lại Guardrails, test lại dataset lâm sàng và migrate hệ thống).
*   **Đánh giá:**
    *   Likelihood: 3/5 (Khả năng update ToS siết chặt y tế là khá thực tế).
    *   Impact: 4/5 (Mất 2 tháng runway ở giai đoạn MVP là chí mạng).
    *   **Score:** 12

### 2. Customer-Facing AI Risk (Medical Hallucination)
*   **If:** Model GPT-4o bị hallucinate (ảo giác), tự ý bịa ra các lời khuyên dinh dưỡng sai lệch và nguy hiểm (VD: gợi ý món ăn có chỉ số đường huyết GI rất cao cho mẹ bầu bị tiểu đường thai kỳ).
*   **Then:** Một mẹ bầu làm theo, gặp vấn đề sức khỏe, chụp ảnh màn hình bóc phốt trên các hội nhóm mẹ bỉm sữa gây ra viral backlash, đồng thời app bị report hàng loạt.
*   **Leading to:** **Mất 4 tháng runway** (Chi phí đền bù sự cố, thuê chuyên gia xử lý khủng hoảng truyền thông PR, tư vấn pháp lý, cộng thêm sự sụt giảm doanh thu do user churn và mất niềm tin hoàn toàn).
*   **Đánh giá:**
    *   Likelihood: 4/5 (Bản chất LLM là xác suất, hallucination chắc chắn sẽ xảy ra dù có prompt tốt đến đâu).
    *   Impact: 5/5 (Mất 4 tháng runway + Rủi ro sập tiệm vĩnh viễn vì mất chữ "Tín" trong y tế).
    *   **Score:** 20

### 3. Founder Bandwidth Risk (Single Point of Failure)
*   **If:** Founder (người duy nhất nắm toàn bộ kiến trúc hệ thống, prompt engineering và database) bị ốm nặng hoặc kiệt sức không thể mở máy tính trong 3-5 ngày.
*   **Then:** Nếu có critical bug (ví dụ: server sập, lỗi thanh toán, API OpenAI trả về lỗi 500), sẽ không có bất kỳ ai trong team có khả năng fix.
*   **Leading to:** **Mất 1 tháng runway** (Tiến độ ra mắt bị đình trệ, phải hoàn tiền cho các user đang bị lỗi không dùng được app trong tuần đó).
*   **Đánh giá:**
    *   Likelihood: 4/5 (Founder kiệt sức ở giai đoạn đầu MVP là chuyện xảy ra như cơm bữa).
    *   Impact: 2/5 (Chỉ ảnh hưởng tiến độ ngắn hạn, không phá hủy cấu trúc công ty).
    *   **Score:** 8

---

## Bước 4: Ma trận 2x2 & Phân tích KILL ZONE

| Impact (Tháng Runway) \ Likelihood | Low (1-2) | High (3-5) |
| :--- | :--- | :--- |
| **High (3-5 tháng runway)** | | ** KILL ZONE** <br> Risk 2: Medical Hallucination (Score: 20) <br> Risk 1: Vendor Risk (Score: 12) |
| **Low (1-2 tháng runway)** | | Risk 3: Founder Bandwidth (Score: 8) |

### Ưu tiên cho Block 3:
Rủi ro nằm sâu nhất trong **KILL ZONE** là **Risk 2 (Customer-Facing AI Risk: Medical Hallucination)**. 

Đối với NestAI, làm mảng y tế và sức khỏe thai kỳ thì "do no harm" (không gây hại) phải là nguyên tắc sống còn. Việc AI gợi ý sai thực đơn bệnh lý có thể đẩy dự án vào chỗ chết ngay lập tức. Do đó, đây là **priority số 1 cho Block 3** — Cần phải có các giải pháp kỹ thuật cụ thể (như Guardrails AI, Validator layer, Fail-safe UI chuyển sang thực đơn tĩnh) để bẻ gãy rủi ro này trước khi scale.
