# Hypothesis & PMF Scorecard — MamaMenu AI

---

### Riskiest Assumption

Mẹ bầu có bệnh lý thai kỳ (tiểu đường, thiếu máu) sẽ thực sự **follow thực đơn AI gợi ý ít nhất 3 ngày/tuần** — không phải chỉ xem rồi bỏ qua như tờ hướng dẫn bác sĩ cho. Nếu assumption này sai, sản phẩm không tạo ra outcome y tế nào, moat data flywheel không hình thành, và không có lý do gì để người dùng trả tiền.

---

### Hypothesis

Chúng tôi tin rằng **thực đơn AI cá nhân hóa theo bệnh lý thai kỳ + tuần thai, hiển thị rõ lý do dinh dưỡng và cho phép swap từng món ngay lập tức** sẽ giúp **mẹ bầu có tiểu đường thai kỳ hoặc thiếu máu** đạt được **tỷ lệ follow thực đơn ≥ 50% trong 2 tuần đầu, giảm được thời gian tự tra cứu thực đơn hằng ngày xuống dưới 5 phút**.

---

### Aha Moment

Lần đầu tiên user **swap một món không thích, nhận được gợi ý thay thế ngay lập tức kèm lý do dinh dưỡng cụ thể** ("Đổi bún bò → cháo thịt bằm + rau ngót vì cũng giàu sắt, GI thấp hơn"), và tiếp tục dùng thực đơn đó cho bữa ăn hôm đó — chứng minh user tin hệ thống đủ để hành động, không chỉ đọc.

---

### PMF Signal

**Menu compliance rate D14 ≥ 50%** — đo bằng tỷ lệ user báo cáo đã ăn đúng hoặc gần đúng thực đơn gợi ý ít nhất 7/14 ngày trong 2 tuần đầu, kết hợp với **D30 retention ≥ 35%** trong nhóm đã đạt compliance đó.

---

### Vì sao chọn metric này

Sign-up và số lượt xem không phản ánh gì — retention và compliance mới cho biết sản phẩm có tạo ra hành vi thay đổi thực sự không. Nếu user follow thực đơn ≥ 50% trong 2 tuần, có nghĩa là: (1) gợi ý đủ "Việt" và thực tế để thực hiện được; (2) user tin vào output AI đủ để không cần verify lại từng món trên Google; (3) habit loop đã bắt đầu hình thành. D30 retention sau compliance đo được liệu habit đó có bền không — đây là điều kiện cần trước khi chuyển sang monetization test. Metric này cũng trực tiếp falsify được Riskiest Assumption: nếu compliance < 30%, biết ngay là thực đơn gợi ý chưa đủ thực tế, không phải vấn đề marketing hay onboarding.
