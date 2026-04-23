# Day 16 Submission — Team [Your Team Name]

## Members
- Chu Thị Ngọc Huyền

---

## 1. Idea reframed

Original idea:
> Hệ thống AI tự động sinh thực đơn phù hợp với từng giai đoạn cụ thể trong thai kỳ và cho con bú, cá nhân hoá sở thích, bệnh lý, tự động tính toán kcal từ hình ảnh và gợi ý thực đơn.

Reframed as a product opportunity:
> Thay vì chỉ cung cấp một công cụ tạo thực đơn cứng nhắc, đây là cơ hội xây dựng một "Trợ lý dinh dưỡng AI 24/7", giúp phụ nữ mang thai và cho con bú tự tin quản lý bữa ăn mà không phải đối mặt với nỗi lo tính toán phức tạp, nỗi sợ thực đơn nhàm chán, hay các rủi ro từ bệnh lý thai kỳ.

---

## 2. Customer / Segment Card

- **Segment name:** Phụ nữ mang thai và mẹ bỉm sữa đang cho con bú tại đô thị có vấn đề về dinh dưỡng/bệnh lý (như tiểu đường thai kỳ) hoặc bĩu nghén/sợ tăng cân mất kiểm soát.
- **Operational context:** Phải quyết định một ngày 3-5 bữa ăn gì, mua thực phẩm gì, giữa một lịch trình bận rộn và môi trường thay đổi sở thích ăn uống liên tục.
- **Recurring workflow:** Mua sắm nguyên liệu -> Nấu nướng -> Ăn (hoặc đi ăn nhà hàng) -> Cập nhật/Theo dõi calo, dưỡng chất hằng ngày.
- **Pain moment:** Khi đứng trước mâm cơm hoặc thực đơn quán ăn mà không biết khẩu phần này cung cấp bao nhiêu calo, hoặc bị stress cực độ khi phải ngồi nhập liệu từng gram thức ăn lên các app theo dõi calo mỗi ngày.
- **Why now:** Các mô hình GenAI và AI Vision hiện nay đủ trưởng thành để hiểu bối cảnh cá nhân hóa sâu và nhận diện thức ăn phức tạp (đặc biệt qua ảnh) một cách nhanh chóng. Xu hướng chăm sóc sức khoẻ cá nhân ở phân khúc trung lưu đang tăng.
- **Access path:** Hợp tác với phòng khám sản khoa, các cộng đồng mẹ bỉm sữa lớn (Facebook, Zalo), hoặc KOL/KOC mảng mẹ bé.

One-sentence description:
> Những bà mẹ sống ở đô thị, mong muốn một chế độ dinh dưỡng thai kỳ chuẩn khoa học, phù hợp bệnh lý nền nhưng mệt mỏi với việc nhập liệu thủ công các app theo dõi theo chuẩn rập khuôn.

---

## 3. Need Map (2–3 needs)

### Need #1 (priority)
- **Statement (JTBD):** When chuẩn bị thưởng thức một bữa ăn, I want biết chính xác mức năng lượng và độ an toàn của nó, so I can quản lý cân nặng và đường huyết một cách thoải mái mà không tốn công tra cứu.
- **Current workaround:** Tự ước lượng bằng mắt, đọc nhãn thực phẩm (rất mệt), tra cứu Google từng nguyên liệu hoặc hỏi xin tư vấn từ các hội nhóm Facebook.
- **Pain signal:** Tốn ít nhất 5-10 phút mỗi bữa để tra cứu hoặc bị lo âu do thông tin trên mạng mâu thuẫn khuyên "kiêng cái này, kiêng cái kia".
- **Evidence / proxy evidence:** Tỉ lệ bỏ ứng dụng theo dõi calo sau 1 tuần dùng thử rất cao do chán nản việc phải nhập từng nguyên liệu con cá, lá rau. Vô vàn bài đăng như "Bầu tháng 5 ăn món này có được không?" với câu trả lời mâu thuẫn.
- **Why underserved:** Các app track calo hiện tại hầu hết bắt nhập text thủ công từng món (database cứng). Các thực đơn mẫu thường nhàm chán và không phản ánh kịp thời sự thay đổi khẩu vị do ốm nghén của mẹ bầu.

### Need #2
- **Statement (JTBD):** When bước vào một giai đoạn mới của thai kỳ/cho con bú, I want một thực đơn chi tiết được tư duy sẵn cho vừa túi tiền, vừa khẩu vị của riêng mình, so I can đi chợ/mua sắm và vào bếp một cách dễ dàng, an tâm tuyệt đối về sức khỏe thai nhi.
- **Current workaround:** Thuê chuyên gia dinh dưỡng (phí rất cao) hoặc tự copy/paste các thực đơn mẫu trên mạng, chắp vá với các công thức nấu ăn.
- **Pain signal:** Sợ hãi vào nhóm bà bầu xin thực đơn nhưng lúc nấu lại không kiếm thấy nguyên liệu, hoặc thức ăn bị lập lại dẫn đến mất cảm giác ngon miệng.
- **Evidence / proxy evidence:** Việc theo dõi nhóm Facebook/Tiktok ăn uống dinh dưỡng thai kỳ luôn hút traffic cao nhưng việc apply vào thực tế bếp núc rất khó.
- **Why underserved:** Các nội dung mạng là nội dung chung (one-size-fits-all), không tính tới yếu tố như dị ứng cá nhân, tình trạng khó tiêu, hay kinh phí đi chợ của từng người.

---

## 4. Strategy Statement

For phụ nữ mang thai và sau sinh bận rộn tại đô thị
who struggle with việc tính toán kcal thủ công, lập thực đơn an toàn tuân thủ các quy tắc bệnh lý (vd: tiểu đường thai kỳ),
our product helps them tự tin theo dõi dinh dưỡng và luôn có những ý tưởng bữa ăn ngon miệng khoa học
through việc AI tự động phân tích kcal bằng qua hình ảnh và GenAI tự động sinh thực đơn thay đổi theo khẩu vị hằng ngày,
unlike các ứng dụng đếm calo bằng tay truyền thống hoặc các website cung cấp bảng thực đơn mẫu thiếu tính linh hoạt cá nhân,
because we can leverage công nghệ Computer Vision để lượng hóa thức ăn ngay tức khắc và LLM để cá nhân hoá tư vấn logic phức tạp từ dữ kiện y tế.

---

## 5. Moat Hypothesis

**Moat mechanism:** Data compounding & Workflow embedding

If we deploy 10,000 times in bối cảnh dinh dưỡng riêng biệt của mẹ bầu nước ta, the following improve:
1. Hệ thống AI Vision nhận diện các món ăn hỗn hợp/truyền thống của Việt Nam (canh chua, cá kho tộ, bún bò,..) ngày càng tăng độ chính xác vượt trội mà các mô hình global chưa làm tốt được tỷ lệ dinh dưỡng.
2. Hệ thống dữ liệu hành vi (VD: thai ốm nghén tháng 2 chuộng ăn vị chua/mặn, hay món gì tránh dị ứng) ngày một dày lênh giúp AI recommend bữa ăn ngày càng sắc bén hơn.
3. Sự gắn kết người dùng (workflow embedding): Việc chụp hình món ăn trước khi ăn sẽ sớm trở thành một thói quen "check-in" bắt buộc giúp giữ chân người dùng trong ít nhất là 15-20 tháng (quá trình mang thai đến cai sữa).

Why competitors cannot easily replicate this:
> Các nhà phát triển GenAI nói chung không có được bộ database hình ảnh thức ăn đặc thù văn hoá của Việt Nam với đầy đủ gán nhãn calo. Các app bệnh viện/startup y tế thường thiếu tư duy luồng người dùng (workflow) để kéo họ mở app mỗi ngày (chỉ mở lúc bệnh).

---

## 6. Initial TAM / SAM / SOM view

| Layer | Estimate | Key assumptions | Confidence |
|---|---|---|---|
| TAM | $60M - $100M/year | 1.5 triệu ca sinh x ~100$/user ARPPU/năm (nếu tính được cả subscription lẫn ecosystem đi kèm). | Medium |
| SAM | $6M - $12M/year | 10-15% tổng ca sinh (tầng lớp trung lưu thành thị) quan tâm đặc biệt tới thai kỳ và chịu chi. | Medium |
| SOM | $500K - $1M/year | Capture 10k-20k người dùng trả phí trong năm đầu (x ~$50 subscription fee) qua KOL và partner. | Low |

**Top 3 unknowns requiring further research:**
1. Giới hạn độ chính xác và mức sai số có thể chấp nhận được của AI Computer Vision trên các món ăn phức tạp ở Việt Nam là bao nhiêu? (Tránh để người bị tiểu đường thai kỳ bị tư vấn sai).
2. Willingness to Pay (WTP) của các bà mẹ ở Việt Nam cho một app/AI tư vấn dinh dưỡng là bao nhiêu khi so với việc mua trực tiếp 1 gói thực phẩm định lượng sẵn?
3. Tính tuân thủ và tần suất chụp ảnh mâm cơm mỗi ngày của người dùng kéo dài được bao lâu?

**Judgment:**
- [ ] Worth pursuing now
- [x] Worth pursuing but not now (need to validate độ hạn chế của AI Vision nhận diện món ăn thực tế Việt vs sai số trước)
- [ ] Not worth pursuing as currently framed

---

## 7. Positioning Note (2 sentences)

**What we are:**
> Chúng tôi là người bạn AI đồng hành dinh dưỡng bằng hình ảnh trong suốt quá trình thai kỳ và sau sinh, giúp mẹ an tâm ăn đúng chuẩn mà không phải tốn công tính toán.

**What we are not / not yet:**
> Chúng tôi không phải là cơ sở y tế hay đưa ra phác đồ thay thế bác sĩ điều trị, và chưa phục vụ việc giảm mỡ định hình cho người dùng không phải đối tượng sinh nở.

---

## 8. Self-assessment before Day 17

Trong 6 mắt xích (Idea → Customer → Need → Strategy → Moat → Market Size), mắt xích nào team đang yếu nhất?

> Market Size và Moat. Team giả định nhiều về willingness to pay của tệp người dùng VN và về khả năng kỹ thuật AI Vision (sai số nhận diện món trộn).

Open questions chúng tôi muốn khám phá thêm ở Day 17:
1. MVP nên bao gồm cả tính năng chụp ảnh và sinh thực đơn, hay chỉ cần validate một trong hai trước tiên?
2. Có thể sử dụng kỹ thuật fake-AI/Wizard of Oz để test ý định sử dụng của tập user 50 người dùng đầu tiên ở khâu chụp hình đồ ăn tính calo không?
3. Thiết kế prototype PRD thế nào để người dùng không cảm thấy ứng dụng mang tính y tế khô khan?
```
