# Marketing Claims Audit — NestAI (MamaMenu AI)

**Ngày rà soát:** 08/05/2026
**Người rà soát:** Chu Thị Ngọc Huyền
**Nguồn tài liệu:** Pitch Memo Day 19, Twitter Pitch, Script 45s, Early Adopter Hook

---

## Bảng claim audit

| # | Câu gốc | Vị trí | Mức | Evidence hiện có | Honest version | Action |
|---|---------|--------|-----|-----------------|----------------|--------|
| 1 | *"AI tự động tính toán bù trừ vi chất... giúp mẹ bầu chuyển sang 'hoàn toàn yên tâm' trong vòng 10 giây"* | Pitch Memo — Section 3 | **C** | Không có: không có benchmark thời gian xử lý, không có thang đo cảm xúc user | "AI ước tính vi chất sau mỗi ảnh chụp bữa ăn trong vòng vài giây; độ chính xác và cảm nhận user đang được đo lường trong pilot" | Sửa ngay trước khi pitch |
| 2 | *"Computer Vision đủ trưởng thành để nhận diện **chính xác** các nguyên liệu phức tạp trong món ăn châu Á"* | Pitch Memo — Section 4 (Why Now) | **C** | Không có: không có accuracy % benchmark cho món Việt cụ thể (phở, bún bò, cơm tấm) | "Computer Vision đã cải thiện đủ để nhận diện nhiều món Á đông; với món Việt phức tạp chúng tôi có fallback để user xác nhận — đây là bài toán đang được giải quyết" | Sửa + ghi benchmark test plan |
| 3 | *"Compliance Rate D14 đạt ≥ 50%"* (trình bày như traction đã đạt được) | Pitch Memo — Section 5 (Traction), Twitter Pitch | **C** | Pilot group kích thước không xác định; trong Day 17 đây là ngưỡng SUCCESS TARGET, không phải số đo được — VC critique đã flag vấn đề này | "Trong nhóm pilot nhỏ ban đầu (n=[điền số thực]), compliance D14 đạt X%; đang thiết kế đo lường có đối chứng cho 200–500 user tại TP.HCM/HN" | **Ưu tiên cao nhất** — gây rủi ro Điều 198 nếu claim traction giả |
| 4 | *"D30 Retention vững chắc ở mức 35%"* | Pitch Memo — Section 5 (Traction) | **C** | Cùng vấn đề: pilot size không rõ; "vững chắc" là từ chủ quan khi n chưa đủ statistical significance | "Pilot ghi nhận D30 retention ~35% (n=[số thực]); cần 200+ user để xác nhận trend và loại bỏ novelty effect" | Sửa + công khai sample size |
| 5 | *"LTV/CAC dự kiến ~4.2x với thời gian hoàn vốn chỉ 3 tháng"* | Pitch Memo — Section 5 (Traction) | **C** | Không có: con số "dự kiến" (projection) nhưng đặt trong mục Traction — gây hiểu nhầm là đã đo được. Chưa có CAC thực vì chưa paid acquisition | "LTV/CAC mô hình tài chính dự phóng: ~4x dựa trên giả định [list assumptions]; chưa có paid acquisition data để đo CAC thực" | Tách projection ra khỏi mục Traction |
| 6 | *"NestAI nhúng trực tiếp phác đồ của Bộ Y tế vào cơ sở dữ liệu ẩm thực Việt Nam"* | Pitch Memo — Section 3, Script 45s | **B** | Có ý định thiết kế (Day 17 PRD: dùng phác đồ quản lý tiểu đường thai kỳ Bộ Y tế VN); chưa có bằng chứng integration đã được dietitian review hoặc BYT xác nhận | "NestAI sử dụng phác đồ dinh dưỡng thai kỳ của Bộ Y tế VN làm nền tảng thiết kế, được rà soát bởi dietitian nội bộ — không phải công cụ được BYT cấp phép" | Bổ sung disclaimer + link source BYT |
| 7 | *"chuẩn phác đồ của Bộ Y tế cho từng tuần thai"* | Script 45s | **C** | "Chuẩn" = compliance claim mạnh → ngụ ý được BYT kiểm định; chưa có bất kỳ clinical validation hay BYT sign-off | "Dựa trên khuyến nghị dinh dưỡng của Bộ Y tế VN và WHO — không phải phần mềm y tế được cấp phép" | Sửa ngay — "chuẩn BYT" không có bằng chứng = vùng Điều 198 |
| 8 | *"workflow ràng buộc lâm sàng chặt chẽ"* | Script 45s | **C** | Không có: không có tài liệu mô tả clinical workflow cụ thể; "chặt chẽ" không được định nghĩa; PRD chỉ có fallback UX (badge "Ước tính") | "NestAI có fallback UX khi confidence thấp: hiển thị badge '~Ước tính', yêu cầu user xác nhận, và chuyển hotline bác sĩ khi cần — không phải quy trình lâm sàng được kiểm định" | Sửa + tài liệu hóa fallback logic |
| 9 | *"Thực đơn đúng bệnh lý, đúng tuần thai, ngay hôm nay"* | Early Adopter Hook | **C** | "Đúng bệnh lý" = clinical accuracy claim. Không có evidence nào về accuracy khi AI gợi ý thực đơn cho người có tiểu đường thai kỳ (failure rate chưa đo) | "Thực đơn cá nhân hóa theo bệnh lý và tuần thai — dựa trên khuyến nghị dinh dưỡng có chuyên môn, không phải chỉ định y tế" | Bổ sung "theo khuyến nghị dinh dưỡng" thay vì "đúng bệnh lý" |
| 10 | *"NestAI không để bạn phải đoán" / "Zero guesswork"* | Early Adopter Hook | **C** | Tuyệt đối hóa: hệ thống photo logging đang ở giai đoạn MVP, confidence < 60% vẫn hiển thị "Ước tính (~)" theo PRD → vẫn còn một phần đoán | "NestAI giảm đáng kể phần đoán mò so với tra Google — với món phổ biến, AI ước tính vi chất ngay; với món phức tạp, AI hướng dẫn bạn xác nhận" | Đổi thành claim tương đối thay vì tuyệt đối |
| 11 | *"AI tự động tính toán bù trừ vi chất sau mỗi bức ảnh chụp"* | Pitch Memo — Section 3 | **B** | Có thiết kế trong PRD (photo logging → kcal + vi chất); chưa có accuracy benchmark và chưa build MVP | "AI ước tính vi chất từ ảnh bữa ăn; trong MVP, món phổ biến được nhận diện trực tiếp — món phức tạp user được hỗ trợ xác nhận thủ công" | Thêm scope giới hạn của MVP |
| 12 | *"Hơn 25% phụ nữ mang thai tại Việt Nam mắc tiểu đường thai kỳ hoặc thiếu máu"* | Pitch Memo — Section 1, Twitter Pitch | **A** | Có nguồn: tỷ lệ tiểu đường thai kỳ ~20–25% (BVPSTW 2022); thiếu máu ~40% (WHO Southeast Asia) — đã cited trong Day 16 | Giữ nguyên — đây là claim hợp lệ với nguồn rõ ràng | Thêm citation footnote vào materials |

---

## Thống kê

- **Tổng số claim rà soát:** 12
- **Mức A (chứng minh được):** 1 — số liệu dịch tễ học tiểu đường thai kỳ VN
- **Mức B (chưa chứng minh, có thể làm được):** 2 — tích hợp phác đồ BYT + photo vi chất tracking
- **Mức C (thổi phồng — vùng Điều 198):** 9

---

## TOP 3 priority sửa ngay

### 1. KHẨN CẤP — "Compliance D14 ≥ 50%" và "D30 Retention 35%" trình bày như traction đã đạt
**Lý do:** Đây là mức C nguy hiểm nhất — trong Day 17, 50% là **success threshold** (ngưỡng mục tiêu), không phải số đo thực tế. Nếu VC hoặc khách hàng B2B hiểu đây là số đã validated trên sample lớn, cấu thành "cung cấp thông tin sai sự thật để người khác tin và quyết định" — đủ điều kiện Điều 198 nếu có giao dịch phát sinh.
**Sửa:** Thêm sample size thực (n=?), đổi từ "đạt" sang "ghi nhận trong pilot n=[X]", tách hẳn khỏi mục Traction chính.

### 2. KHẨN CẤP — "chuẩn phác đồ của Bộ Y tế" và "chuẩn y khoa"
**Lý do:** Claim về clinical compliance mà không có BYT sign-off. Với sản phẩm liên quan y tế, đây là claim nhạy cảm. Nếu user bị ảnh hưởng sức khỏe và kiện, claim "chuẩn BYT" mà không có bằng chứng = lừa dối khách hàng theo Điều 198.
**Sửa:** Đổi thành "dựa trên khuyến nghị dinh dưỡng của Bộ Y tế VN và WHO" + thêm disclaimer "không phải phần mềm y tế được cấp phép".

### 3. QUAN TRỌNG — "hoàn toàn yên tâm trong vòng 10 giây"
**Lý do:** Absolute emotional guarantee + specific time claim = không thể chứng minh và không thể kiểm soát. Nếu user dùng và không "yên tâm hoàn toàn" hoặc app mất > 10 giây → mismatch kỳ vọng, complaint, và rủi ro pháp lý.
**Sửa:** "AI trả kết quả ước tính vi chất nhanh chóng; nhiều user báo cáo cảm thấy tự tin hơn khi có thông tin cụ thể thay vì tự tra Google".

---

## Ghi chú compliance

Toàn bộ 9 claim Mức C đang trong vùng rủi ro **Điều 198 BLHS** (Lừa dối khách hàng) nếu:
- Khách hàng (B2C mẹ bầu hoặc B2B phòng khám) tin vào các claim này và ký hợp đồng / trả tiền
- Revenue vượt 50 triệu VND từ sản phẩm có claim chưa chứng minh
- Founder "biết rõ" (có PRD, có pilot data thật) nhưng marketing nói khác — đúng pattern *"biết rõ là không biết"* trong cáo trạng vụ Kera

**Pattern tương tự Kera:** *"1 viên = 1 đĩa rau"* → *"hoàn toàn yên tâm trong 10 giây"* / *"chuẩn phác đồ BYT"*
