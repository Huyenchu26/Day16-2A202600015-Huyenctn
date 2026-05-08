# Compliance Audit v2 — NestAI (MamaMenu AI)

**Ngày audit:** 08/05/2026
**Người audit:** Chu Thị Ngọc Huyền (Founder) + AI Compliance Officer (GPT-4o với prompt Day 22 §8)
**Sản phẩm:** NestAI — Trợ lý dinh dưỡng AI cho phụ nữ mang thai có bệnh lý tại Việt Nam
**Tài liệu đầu vào:** PRD Day 17, Pitch Memo Day 19, Twitter Pitch, Script 45s, Risk Register v2 Day 21, Day 16 Customer Card

**Sơ đồ luồng dữ liệu (vẽ nhanh):**
```
User (mẹ bầu VN) → App (iOS) → Backend NestAI (VN cloud)
                                  ├─ Profile bệnh lý + tuần thai → OpenAI GPT-4o (Mỹ) → Menu trả về
                                  ├─ Ảnh bữa ăn → Google Cloud Vision (Mỹ) → Nhận diện món
                                  └─ Compliance log + ảnh → Database (VN, chưa pseudonymize)
```

---

## TỔNG QUAN

| Chỉ số | Số lượng |
|--------|----------|
| Tổng vi phạm tìm thấy | **8** |
| Marketing claim (Kera pattern, Điều 198) | 3 |
| Dữ liệu cá nhân (PDPL Điều 30, CIC pattern) | 3 |
| Phân loại rủi ro AI (Điều 9 Luật AI VN) | 1 |
| Vendor / Payment (Pips pattern) | 1 |

**Mức độ rủi ro tổng thể:** 🔴 **RẤT CAO** — có 5 vi phạm vùng đỏ, 2 trong số đó đã xảy ra (PDPL hiệu lực 1/1/2026).

---

## VI PHẠM 1 — Compliance D14 ≥ 50% trình bày như traction đã đạt

- **Luật áp dụng:** Bộ luật Hình sự VN
- **Điều:** Điều 198 Khoản 2 (Lừa dối khách hàng — thu lợi từ 50 triệu đồng trở lên → tù 1-5 năm)
- **Bằng chứng trong sản phẩm:**
  > Pitch Memo Day 19, Section 5: *"Trong tập người dùng thử nghiệm ban đầu, tỷ lệ tuân thủ thực đơn (Compliance Rate D14) đạt ≥ 50%."*
  > Twitter Pitch: *"Pilot: compliance D14 >50%, retention 35%."*
  >
  > Tuy nhiên, Day 17 PRD Section 4: *"Primary metric: Menu compliance rate D14... **Ngưỡng thành công: ≥ 50%**."* — đây là TARGET, không phải số đo thực tế.
- **Pattern khớp với:** **Vụ kẹo Kera** — pattern *"biết rõ là không biết"*. Founder biết 50% là threshold đặt ra, vẫn marketing như achieved. Tương đồng với Kera: biết kiểm nghiệm 0.935% nhưng vẫn nói "1 viên = 1 đĩa rau".
- **Hành động sửa (3 bước, 1 tuần):**
  1. Sửa ngay Pitch Memo + Twitter Pitch + Script: thêm **sample size thực** (n=?) và phân biệt giữa "ngưỡng mục tiêu" vs "đo được trong pilot"
  2. Đặt định nghĩa tracking event chính xác: "compliance" = user báo cáo đã ăn đúng/gần đúng thực đơn ≥7/14 ngày (theo PRD), không phải chỉ "open app"
  3. Lưu raw data pilot (tên user mã hóa, ngày báo cáo, % compliance) trong file Notion có timestamp — làm bằng chứng "biết rõ" sau này
- **Deadline:** Ngay tuần này — TRƯỚC bất kỳ lần pitch tiếp theo nào.

---

## VI PHẠM 2 — "Chuẩn phác đồ của Bộ Y tế" mà không có sign-off

- **Luật áp dụng:** Bộ luật Hình sự VN + Luật AI Việt Nam
- **Điều:** Điều 198 Khoản 2 BLHS + Điều 9 Luật AI VN 134/2025 (tầng Cao y tế chưa được kiểm định)
- **Bằng chứng trong sản phẩm:**
  > Script 45 giây Day 19: *"AI sẽ tính vi chất và sinh thực đơn món Việt **chuẩn phác đồ của Bộ Y tế** cho từng tuần thai."*
  > Pitch Memo Section 3: *"NestAI **nhúng trực tiếp phác đồ của Bộ Y tế** vào cơ sở dữ liệu ẩm thực Việt Nam."*
  > Twitter Pitch: *"AI sinh thực đơn món Việt và tracking qua ảnh **khớp phác đồ y khoa**."*
- **Pattern khớp với:** **Vụ kẹo Kera** — claim thẩm quyền y tế không có evidence. Tương tự Kera dùng từ "công bố 28.43% bột rau củ" — ngụ ý có cơ sở nhưng thực tế không có kiểm nghiệm độc lập.
- **Hành động sửa:**
  1. Đổi tất cả wording sang: *"dựa trên khuyến nghị dinh dưỡng thai kỳ của Bộ Y tế VN và WHO"* — không phải "chuẩn" hoặc "nhúng trực tiếp phác đồ"
  2. Thêm disclaimer rõ ràng: *"NestAI không phải phần mềm y tế được Bộ Y tế cấp phép. Không thay thế tư vấn của bác sĩ chuyên khoa."* — bắt buộc click đồng ý lúc onboarding (theo Risk 4 Risk Register)
  3. Đính kèm link nguồn các văn bản BYT đã dùng (phác đồ quản lý tiểu đường thai kỳ) trong Privacy Policy / Terms để chứng minh "có dùng nguồn chính thống nhưng không tự xưng được cấp phép"
- **Deadline:** Trước launch MVP — vì khi user mất tiền hoặc ảnh hưởng sức khỏe, claim này là vùng đỏ Điều 198.

---

## VI PHẠM 3 — "Hoàn toàn yên tâm trong vòng 10 giây" + "Zero guesswork"

- **Luật áp dụng:** Bộ luật Hình sự VN
- **Điều:** Điều 198 Khoản 1-2 BLHS (lừa dối khách hàng — thủ đoạn gian dối)
- **Bằng chứng trong sản phẩm:**
  > Pitch Memo Section 3: *"AI tự động tính toán bù trừ vi chất sau mỗi bức ảnh chụp, giúp mẹ bầu chuyển từ trạng thái 'đoán mò, sợ hãi' sang **'hoàn toàn yên tâm' trong vòng 10 giây**."*
  > Early Adopter Hook: *"Bạn sợ ăn sai hại con — NestAI **không để bạn phải đoán**."* (Zero guesswork)
- **Pattern khớp với:** **Vụ kẹo Kera** — claim tuyệt đối hóa kết quả ("1 viên = 1 đĩa rau" → "10 giây yên tâm"). Cả hai là superlative claim không thể đo, dùng để dụ user mua/dùng.
- **Hành động sửa:**
  1. Thay "hoàn toàn yên tâm" → "có thông tin cụ thể để quyết định" (kết quả concrete thay vì cảm xúc tuyệt đối)
  2. Thay "Zero guesswork" → "Giảm đáng kể phần đoán mò so với tự tra Google" (so sánh tương đối, có baseline)
  3. Bỏ "10 giây" — không có benchmark thời gian; nếu giữ phải chứng minh được P95 latency
- **Deadline:** Ngay tuần này.

---

## VI PHẠM 4 — Chưa nộp DPIA cho dữ liệu y tế nhạy cảm

- **Luật áp dụng:** PDPL 91/2025/QH15 (đã hiệu lực 1/1/2026)
- **Điều:** Điều 30 Khoản 5 (DPIA bắt buộc trong 60 ngày kể từ khi bắt đầu xử lý)
- **Bằng chứng trong sản phẩm:**
  > Day 17 PRD Section 2: *"trimester, bệnh lý kèm, vùng miền và dị ứng"* + *"chẩn đoán tiểu đường thai kỳ hoặc thiếu máu"* — đây là **dữ liệu y tế nhạy cảm đặc biệt** theo PDPL
  > Day 16 Customer Card: pilot đã chạy với mẹ bầu thực tế → đã thu thập dữ liệu thực
  > Risk Register v2 Risk 8: *"vi phạm Nghị định 13"* — vẫn viện dẫn văn bản đã hết hiệu lực, chứng tỏ founder chưa cập nhật PDPL
  > **territorial_scope.md (vừa tạo):** xác nhận chưa có DPIA nào được nộp.
- **Pattern khớp với:** **Vụ rò rỉ CIC** — *"xử lý dữ liệu cá nhân thiếu kiểm soát bảo mật"* và pattern Bộ Công an cảnh báo "110+ triệu hồ sơ bị bán" trong 6 tháng đầu 2025.
- **Hành động sửa:**
  1. Sử dụng template DPIA trong `document_trail.md` — điền và nộp trong **2 tuần tới** (deadline pháp lý là 07/06/2026 = 60 ngày từ khi bắt đầu xử lý)
  2. Pseudonymize dữ liệu trước khi gửi OpenAI: thay tên thật bằng `user_id_hash`, gộp bệnh lý vào enum cố định thay vì free-text
  3. Thiết lập data retention policy: xóa ảnh bữa ăn sau 90 ngày, xóa dữ liệu y tế khi user xóa tài khoản trong 30 ngày
- **Deadline:** **07/06/2026** (60 ngày — đã cận deadline).

---

## VI PHẠM 5 — Chưa nộp CTIA (Cross-border Transfer Impact Assessment)

- **Luật áp dụng:** PDPL 91/2025/QH15
- **Điều:** Điều 30 + quy định về chuyển dữ liệu xuyên biên giới
- **Bằng chứng trong sản phẩm:**
  > Day 17 PRD: *"Model: GPT-4o for menu generation; Google Cloud Vision/custom fine-tuned image model cho food recognition"* — cả hai vendor đều có server ngoài VN
  > Sơ đồ data flow ở đầu file: dữ liệu y tế + ảnh đang chuyển sang Mỹ mỗi lần gọi API
- **Pattern khớp với:** **Vụ rò rỉ CIC** + Day 22 handbook §6.4: *"Engineer paste customer data lên ChatGPT public = chuyển dữ liệu ra nước ngoài = phải có CTIA + có thể vi phạm Điều 8"*
- **Hành động sửa:**
  1. Sử dụng template CTIA trong `document_trail.md` — đánh giá riêng cho OpenAI và Google Cloud Vision
  2. Ký Data Processing Agreement (DPA) chính thức với cả hai vendor; bật **Zero Data Retention** trên OpenAI Enterprise API (không cho dùng data train model)
  3. Kích hoạt Google Cloud region `asia-southeast1` (Singapore) thay vì US default — giảm khoảng cách chuyển; strip metadata GPS khỏi ảnh trước upload
- **Deadline:** Cùng deadline DPIA — 07/06/2026.

---

## VI PHẠM 6 — Privacy Policy chưa cập nhật theo PDPL (consent dữ liệu y tế)

- **Luật áp dụng:** PDPL 91/2025/QH15
- **Điều:** Điều về consent + xử lý dữ liệu nhạy cảm đặc biệt
- **Bằng chứng trong sản phẩm:**
  > Không tìm thấy Privacy Policy nào trong thư mục dự án
  > Day 17 PRD không có section nào về consent flow cho dữ liệu y tế nhạy cảm
  > Day 22 handbook §6.6 yêu cầu: *"Cập nhật Privacy Policy theo PDPL (consent rõ ràng, đầy đủ thông tin)"* — chưa làm
- **Pattern khớp với:** **Vụ rò rỉ CIC** + cảnh báo Bộ Công an 2025-2026 về thiếu kiểm soát dữ liệu.
- **Hành động sửa:**
  1. Soạn Privacy Policy theo template PDPL: liệt kê 5 loại dữ liệu (territorial_scope.md đã có), mục đích xử lý, vendor nước ngoài, quyền của user (xem/sửa/xóa)
  2. Tạo **consent checkbox tách riêng** cho dữ liệu y tế nhạy cảm — không gộp vào Terms chung
  3. Thêm nút "Xóa toàn bộ dữ liệu của tôi" trong Settings — tuân thủ quyền xóa dữ liệu theo PDPL
- **Deadline:** Trước launch MVP.

---

## VI PHẠM 7 — Chưa tự phân loại tầng Cao + chưa thông báo Bộ KH&CN

- **Luật áp dụng:** Luật AI Việt Nam 134/2025/QH15 (đã hiệu lực 1/3/2026)
- **Điều:** Điều 9 (phân loại tầng rủi ro) + nghĩa vụ thông báo qua cổng AI quốc gia
- **Bằng chứng trong sản phẩm:**
  > Sản phẩm hoạt động trong **lĩnh vực y tế** (gợi ý dinh dưỡng cho phụ nữ mang thai có bệnh lý) → tầng Cao theo Điều 9
  > Risk Register v2 Risk 4 (SaMD Classification) công nhận rủi ro phân loại y tế nhưng **không có hành động đăng ký** với Bộ KH&CN
  > territorial_scope.md (vừa tạo): xác nhận status "✗ Chưa có" cho đăng ký CSDL AI quốc gia
- **Pattern khớp với:** Pattern compliance failure tổng quát — không có VN case cụ thể vì Luật AI VN mới hiệu lực 1/3/2026, nhưng Day 22 handbook §6.6 cảnh báo cần thông báo ngay.
- **Hành động sửa:**
  1. Soạn document tự phân loại tầng Cao (1 trang): mô tả use case, lý do xếp tầng Cao, các biện pháp giám sát con người đã có (badge "Ước tính (~)", hotline bác sĩ, fallback từ PRD)
  2. Đăng ký với Bộ KH&CN qua cổng AI quốc gia khi cổng go-live; trong khi chờ, gửi thông báo bằng văn bản chính thức tới Bộ
  3. Build conformity assessment package: log đầy đủ mỗi AI decision, audit trail, danh sách edge case đã test — chuẩn bị cho deadline ân hạn 18 tháng (01/09/2027)
- **Deadline:** Tự phân loại trong 30 ngày; đăng ký Bộ KH&CN khi cổng có sẵn.

---

## VI PHẠM 8 — Sử dụng OpenAI API cho medical context có thể vi phạm vendor ToS

- **Luật áp dụng:** OpenAI Usage Policies (có thể kích hoạt Điều 324 BLHS nếu founder "biết dấu hiệu" mà vẫn dùng để hưởng lợi) + rủi ro vendor suspend
- **Điều:** OpenAI Usage Policies §"Don't perform or facilitate... providing tailored medical advice without proper review"; Điều 324 BLHS (Rửa tiền — pattern Pips về "biết dấu hiệu vẫn vận hành để hưởng lợi") — áp dụng tương tự nếu vi phạm vendor ToS được biết trước
- **Bằng chứng trong sản phẩm:**
  > Risk Register v2 Risk 3: *"OpenAI đột ngột thay đổi Terms of Service (ToS), cấm tuyệt đối việc dùng API để cung cấp tư vấn y tế/sức khỏe mà không có chứng chỉ bác sĩ."* → Founder **đã biết** rủi ro này
  > Day 17 PRD: dùng GPT-4o để gợi ý menu cho người tiểu đường thai kỳ — đây chính là "tailored medical advice"
  > Vẫn deploy mà không có (a) đọc ToS đầy đủ, (b) mua plan Enterprise có exception, (c) abstraction layer fallback — chưa được build (Risk 3 mitigation chưa triển khai)
- **Pattern khớp với:** **Vụ Mr Pips / Shark Bình** — *"biết rõ có dấu hiệu, vẫn vận hành vì hưởng lợi"*. Tại Shark Bình, biết Mr Pips đáng ngờ nhưng vẫn xử lý thanh toán hưởng phí. Tại NestAI, biết OpenAI ToS có thể cấm medical use nhưng vẫn dùng vì là vendor rẻ/tốt nhất.
- **Hành động sửa:**
  1. **Đọc và lưu trữ** OpenAI Usage Policies (link, ngày đọc, founder ký xác nhận hiểu) — bằng chứng "đã thẩm định" theo Day 22 §4.6 (3 bài học cốt lõi từ Pips)
  2. Triển khai abstraction layer (LLM Router) **ngay** theo Risk 3 mitigation: code tách OpenAI khỏi business logic, sẵn sàng switch sang Anthropic nếu cần
  3. Đăng ký OpenAI API plan có Business Associate Agreement (BAA) hoặc liên hệ OpenAI sales để xác nhận medical use case được approve — lưu email confirmation làm bằng chứng
- **Deadline:** ToS audit trong 1 tuần; abstraction layer trong 2 tuần.

---

## TOP 5 VI PHẠM NGHIÊM TRỌNG NHẤT — 3 hành động cụ thể mỗi vi phạm

| Rank | Vi phạm | Lý do top | Hành động ưu tiên |
|------|---------|----------|-------------------|
| 🔴 #1 | **VP4 — Chưa DPIA** | PDPL đã hiệu lực 4 tháng, dữ liệu y tế nhạy cảm đang chuyển ra nước ngoài, phạt 5% doanh thu | Xem 3 hành động ở mục Vi phạm 4 |
| 🔴 #2 | **VP5 — Chưa CTIA** | Đi kèm VP4, vendor nước ngoài chính của sản phẩm | Xem 3 hành động ở mục Vi phạm 5 |
| 🔴 #3 | **VP1 — Compliance D14 ≥50% giả traction** | "Biết rõ là không biết" rõ rệt nhất; rủi ro hình sự khi có revenue | Xem 3 hành động ở mục Vi phạm 1 |
| 🔴 #4 | **VP2 — "Chuẩn phác đồ BYT"** | Clinical claim không có sign-off, double risk: Điều 198 + Điều 9 Luật AI VN | Xem 3 hành động ở mục Vi phạm 2 |
| 🔴 #5 | **VP7 — Chưa đăng ký tầng Cao** | Luật AI VN đã hiệu lực, ân hạn chỉ còn 16 tháng (đến 01/09/2027) | Xem 3 hành động ở mục Vi phạm 7 |

---

## Bảng đối chiếu với Workshop 1, 2, 3

| Workshop | Trùng khớp với vi phạm AI | Khác biệt |
|----------|---------------------------|-----------|
| WS1 (Marketing audit) | VP1, VP2, VP3 — đều đã được flag trong WS1 | AI audit nâng cấp: gắn với pattern VN cụ thể (Kera, Pips) và đề xuất hành động chống Điều 198 |
| WS2 (Territorial scope) | VP4, VP5, VP6, VP7 — phù hợp 100% với phân tích PDPL + Luật AI VN | AI audit cụ thể hóa thành vi phạm có Điều luật + deadline |
| WS3 (Document trail) | VP4, VP5, VP8 — DPIA/CTIA và vendor review đều là TOP 1 ưu tiên | AI audit thêm pattern Pips cho VP8 — không có trong WS3 |

**Vi phạm AI tìm thêm mà 3 Workshop chưa cover:**
- **VP8** (OpenAI ToS / Pips pattern) — WS3 mention vendor review nhưng chưa nối với Điều 324 BLHS
- **VP6** (Privacy Policy chưa update PDPL) — WS2 nhắc đến nhưng chưa cụ thể hóa thành vi phạm độc lập

---

## Tiêu chí đạt (rubric Day 22 §9)

- ✅ Có **8 vi phạm** (≥ 7 yêu cầu) — đủ 4 nhóm
- ✅ Mỗi vi phạm có **Điều luật cụ thể** (Điều 198 BLHS, Điều 30 PDPL, Điều 9 Luật AI VN, Điều 324 BLHS)
- ✅ Mỗi vi phạm có **bằng chứng trích nguyên văn** từ tài liệu NestAI
- ✅ Mỗi vi phạm có **vụ Việt Nam khớp pattern** (Kera 3 vi phạm, CIC 3 vi phạm, Pips 1 vi phạm, Luật AI VN compliance 1 vi phạm)
- ✅ Top 5 nghiêm trọng nhất có **3 hành động sửa** mỗi cái
- ✅ Toàn bộ output **tiếng Việt** — sẵn sàng email luật sư

---

## Câu chốt nguyên lý Day 22 (lặp lại để nhớ)

> *"Quang Linh, Hằng Du Mục, Thùy Tiên, Shark Bình — không phải tội phạm chuyên nghiệp. Họ là founder và KOL Việt Nam đang ngồi tù hoặc bị truy tố. Khác biệt giữa họ và bạn = 5 file bạn vừa làm hôm nay."*

NestAI vào hôm nay (08/05/2026) đang nằm trong vùng đỏ ở **5/8 vi phạm**. Hai trong số đó (DPIA + CTIA) đã quá hạn theo PDPL. Action ngay tuần này: nộp DPIA + CTIA template, sửa 3 claim mức C trong materials, đọc OpenAI ToS và ký xác nhận.
