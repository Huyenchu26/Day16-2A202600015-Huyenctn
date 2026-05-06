# PRD Skeleton — MamaMenu AI

---

### Problem

Phụ nữ mang thai tại Việt Nam vừa được chẩn đoán bệnh lý thai kỳ (tiểu đường, thiếu máu) không có công cụ nào đủ tin cậy để biết hôm nay nên ăn gì — thực đơn phù hợp bệnh lý, đúng giai đoạn thai, và là món Việt thực tế có thể mua được ngay.

---

### Target User

Phụ nữ mang thai lần đầu tại Việt Nam (22–35 tuổi), đang ở trimester 2 hoặc 3, vừa nhận chẩn đoán tiểu đường thai kỳ hoặc thiếu máu thiếu sắt, có smartphone và đang tự tra cứu thực đơn hằng ngày.

---

### User Story #1

**As a** mẹ bầu vừa được chẩn đoán tiểu đường thai kỳ ở tuần 26,  
**I want** nhận được thực đơn cả ngày gồm các món Việt có chỉ số GI thấp, phù hợp với tam cá nguyệt thứ hai,  
**so that** tôi không phải tự tra Google mỗi sáng và giảm được lo âu về việc "ăn thế này có tăng đường huyết không" — đo được bằng: compliance rate ≥ 50% và anxiety self-report giảm sau 2 tuần dùng.

---

### User Story #2

**As a** mẹ bầu đang ăn trưa tại quán cơm,  
**I want** chụp ảnh bữa ăn và biết ngay mình đã nạp được bao nhiêu sắt và folate so với target của tuần thai này,  
**so that** tôi có thể quyết định bữa tối cần bổ sung thêm gì mà không cần nhập tay từng nguyên liệu — đo được bằng: ≥ 30% user chụp ≥ 3 ảnh/tuần trong 7 ngày đầu.

---

### AI-Specific

**Model Selection**
- **Chọn model:** GPT-4o (menu generation) + Google Cloud Vision / custom fine-tuned model cho food recognition
- **Lý do:** GPT-4o xử lý tốt structured output có điều kiện phức tạp (trimester × bệnh lý × region × preference); Vision API có pre-trained food detection đủ làm baseline nhanh cho MVP
- **Trade-off:** GPT-4o đắt hơn GPT-3.5 ~10x nhưng cần thiết vì sai sót trong nutrition advice cho bệnh lý thai kỳ có hậu quả y tế; fine-tuned food model cần dataset Việt riêng — chưa có ngay, dùng fallback rule-based lookup trong MVP

**Data Source**
- **Nguồn dữ liệu:** (1) Bảng dinh dưỡng thực phẩm Việt Nam — Viện Dinh dưỡng Quốc gia (2007, 2017); (2) WHO/FAO dietary guidelines cho pregnancy; (3) Phác đồ quản lý tiểu đường thai kỳ — Bộ Y tế VN (2018); (4) User-contributed meal photos + corrections (ground truth tích lũy)
- **Loại dữ liệu:** Structured nutrition DB (macro + micro cho 150–200 món Việt); clinical guidelines dạng rule; unstructured image data từ user
- **Cách cập nhật:** Nutrition DB: review bán niên bởi dietitian cộng tác; clinical rules: cập nhật khi có phác đồ mới từ Bộ Y tế; food recognition model: retrain mỗi quý với batch user corrections đã được verify

**Fallback UX**
- **Khi AI không chắc chắn:** Nếu confidence score nhận diện món < 60%, không hiển thị kcal estimate — thay bằng "Tôi chưa chắc đây là món gì, bạn có thể cho tôi biết tên món không?"
- **Thông báo cho người dùng:** Hiển thị badge "Ước tính (~)" thay vì con số tuyệt đối khi sai số ước tính > ±25%; khi gợi ý thực đơn liên quan đến bệnh lý, luôn kèm disclaimer "Gợi ý dựa trên hướng dẫn dinh dưỡng chung — vui lòng xác nhận với bác sĩ của bạn"
- **Hành động thay thế:** Nếu món không có trong database → cho phép user chọn từ danh sách món tương tự; nếu profile bệnh lý không rõ ràng → mặc định về thực đơn thai kỳ khỏe mạnh chuẩn, không apply bất kỳ restriction nào
- **Khi nào chuyển sang con người / rule-based:** (1) User nhập bệnh lý ngoài 3 loại đã có protocol (tiểu đường, thiếu máu, cao huyết áp) → chuyển sang rule-based "thực đơn an toàn chung" + prompt liên hệ dietitian; (2) User báo cáo triệu chứng bất thường (đau bụng, ra máu) → ngắt flow dinh dưỡng, hiển thị hotline bác sĩ ngay lập tức; (3) Sau 3 lần swap liên tiếp → gợi ý "Bạn muốn tôi tạo lại thực đơn hoàn toàn mới không?"

---

### 3 câu hỏi phản biện

1. **Nếu mẹ bầu không chụp ảnh bữa ăn sau tuần đầu**, toàn bộ Need #2 (tracking vi chất) sụp đổ — MVP có đủ giá trị chỉ với menu generation một chiều, hay cần một mechanism khác để user cảm nhận được tiến độ dinh dưỡng của mình?

2. **LLM sinh thực đơn có kiểm soát được khi model "hallucinate" một món không tồn tại hoặc gợi ý sai chế độ ăn cho tiểu đường thai kỳ không** — và nếu xảy ra, ai chịu trách nhiệm pháp lý?

3. **Nếu bác sĩ sản không recommend app**, liệu mẹ bầu vừa nhận chẩn đoán bệnh lý có tự tìm đến app không — hay distribution channel thực sự là phòng khám và team chưa có kế hoạch cụ thể để vào được kênh đó?
