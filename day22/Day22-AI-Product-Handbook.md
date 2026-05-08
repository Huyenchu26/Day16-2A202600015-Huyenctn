# Day 22 Handbook — AI Compliance: Luật chơi trên đường cao tốc

**Course:** AI Product Strategy / Chương 5: Quản trị AI
**Day:** 22 / 30
**Duration:** 4 giờ (240 phút)
**Audience:** Founder startup AI Việt Nam giai đoạn early/seed
**Pre-requisite:** Hoàn thành Day 21 (Risk Register, Incident Playbook, 3 R's framework)

---

## 1. MỤC TIÊU NGÀY HỌC

Sau Day 22, founder sẽ:

1. **Hiểu rõ pattern pháp lý** áp dụng vào AI startup qua 3 vụ enforcement Việt Nam (Kera, Pips, CIC)
2. **Tự rà soát claim marketing** theo Điều 198 BLHS — không còn "biết rõ là không biết"
3. **Phân loại tầng rủi ro AI** theo Luật AI Việt Nam Điều 9 + xác định luật áp dụng
4. **Build hồ sơ chứng cứ 5 loại** để bảo vệ founder cá nhân khỏi truy tố hình sự
5. **Dùng AI để rà soát toàn bộ sản phẩm** với output tiếng Việt sẵn sàng đưa luật sư

---

## 2. CONCEPTS NỀN TẢNG

### 2.1. Phanh trong xe vs Giấy phép lưu hành

Day 21 = phanh nội bộ. Day 22 = giấy phép lưu hành.

| Day | Loại phanh | Mục tiêu | Output chính |
|-----|------------|----------|--------------|
| 21 | Phanh nội bộ | Tránh tai nạn nội bộ | Risk Register, 3 R's |
| 22 | Phanh ngoài (pháp luật) | Tránh đi tù | 5 file compliance |

**Nguyên lý cốt lõi Day 22:**

> *Phanh giữ bạn không đâm vào gốc cây. Giấy phép giữ bạn không vào đồn.*

3 thứ cần ngoài phanh:
- **Giấy phép lái xe** = Bằng pháp lý: được phép vận hành AI ở thị trường này không?
- **Đăng kiểm xe** = Hồ sơ tuân thủ: AI đã đánh giá rủi ro chưa? Đăng ký với cơ quan?
- **Bảo hiểm** = Hồ sơ chứng cứ: khi sự cố xảy ra, chứng minh được mình không cố ý?

### 2.2. "Biết rõ là không biết" — câu cốt lõi cấu thành tội

Cụm từ trích nguyên văn từ cáo trạng vụ kẹo Kera 11/2025:

> *"Các bị cáo BIẾT RÕ kết quả kiểm nghiệm chất xơ trong kẹo Kera chỉ chiếm 0.935%. Thực tế LÀ KHÔNG BIẾT kẹo Kera được sản xuất từ nguyên liệu nào... nhưng với mục đích bán được nhiều sản phẩm, đã thống nhất xây dựng kịch bản giới thiệu, đưa ra các thông tin không đúng sự thật, thổi phồng tính năng, công dụng."*

**Phân tích cụm "biết rõ là không biết":**
- "Biết rõ" = họ có document/data chứng minh số liệu kiểm nghiệm 0.935%
- "Là không biết" = họ KHÔNG kiểm tra thực tế sản phẩm sản xuất từ gì
- Cộng lại = đủ cấu thành tội Lừa dối khách hàng (Điều 198)

**Áp dụng startup AI:**
- "Biết rõ" = AI làm sai 15% trên benchmark
- "Là không biết" = chưa test edge case, chưa biết cụ thể sai ở đâu
- Vẫn marketing "AI đáng tin" → đủ cấu thành tội

### 2.3. Pattern 3 vụ Việt Nam ánh xạ vào AI startup

| Vụ Việt Nam | Pattern cốt lõi | Pattern AI startup tương ứng | Điều luật |
|-------------|-----------------|------------------------------|-----------|
| **Kẹo Kera** (11/2025) | Marketing thổi phồng claim không có evidence | "AI tăng năng suất 10x" không A/B test | Điều 198 BLHS — Lừa dối khách hàng |
| **Mr Pips / Shark Bình** (2/2026) | Cung cấp hạ tầng cho khách hàng có dấu hiệu phạm tội | AI agent cho khách hàng spam/lừa đảo, có abuse report nhưng vẫn process | Điều 324 BLHS — Rửa tiền |
| **Rò rỉ CIC** (9/2025) | Xử lý dữ liệu cá nhân thiếu kiểm soát bảo mật | Engineer paste data lên ChatGPT công cộng | PDPL Điều 8 & 30 |

---

## 3. CASE 1 — VỤ KẸO KERA

### 3.1. Timeline đầy đủ

| Mốc | Sự kiện |
|------|---------|
| 7/2024 | Quang Linh Vlogs + Hằng Du Mục lập **CER Group** (Công ty Cổ phần Tập đoàn Chị Em Rọt). 6 người góp vốn |
| 11/2024 | Hoa hậu Thùy Tiên tham gia với ý tưởng kẹo rau củ. Phân chia: Thùy Tiên 30%, CER 70% |
| 11/2024 | CER thuê Công ty Asia Life (Đắk Lắk, ông Nguyễn Phong Chủ tịch) sản xuất "SuperGreens Gummies" |
| 12/12/2024 | Thùy Tiên ra mắt thương hiệu Kera. Bản tự công bố ghi 28.43% bột rau củ |
| 12/12/2024 - 16/1/2025 | 6 buổi livestream: Hằng 5 lần, Quang Linh 6 lần, Thùy Tiên 3 lần |
| Đầu 3/2025 | Khách hàng kiểm nghiệm — phát hiện chất xơ chỉ 0.935% (không phải 28%) |
| 6/3/2025 | Thùy Tiên đăng bài xin lỗi "đây là bài học lớn" |
| 14/3/2025 | Quang Linh + Hằng họp báo cùng CER, xin lỗi công chúng |
| 24/3/2025 | Sở An toàn thực phẩm TP.HCM phạt CER 125 triệu đồng + thu hồi sản phẩm |
| 3/4/2025 | Bộ Công an khởi tố hình sự. Bắt tạm giam Quang Linh + Hằng + 3 người khác |
| 15/5/2025 | Thùy Tiên bị bắt |
| 11/2025 | TAND TP.HCM xét xử và tuyên án |

### 3.2. Bản án tháng 11/2025

| Bị cáo | Vai trò | Tội danh | Án phạt |
|--------|---------|----------|---------|
| Lê Tuấn Linh | Giám đốc CER | Lừa dối khách hàng | **3 năm 3 tháng tù** |
| Lê Thành Công | Cổ đông CER | Lừa dối khách hàng | **3 năm tù** |
| Hằng Du Mục | Chủ tịch HĐQT CER | Lừa dối khách hàng | **2 năm tù** |
| Hoa hậu Thùy Tiên | KOL + cổ đông | Lừa dối khách hàng | **2 năm tù** |
| Quang Linh Vlogs | Thành viên HĐQT CER | Lừa dối khách hàng | **2 năm tù** |

### 3.3. Số liệu thiệt hại

- 56,385 khách hàng bị lừa
- 160,127 hộp kẹo Kera bán ra
- Doanh thu 17.5 tỷ đồng
- **Lợi nhuận bất chính 12.4 tỷ đồng** (trên ngưỡng 50 triệu của Khoản 2 Điều 198)

### 3.4. Sự thật về kẹo Kera

Bản công bố ghi:
- 10 loại bột rau củ chiếm 28.43% (cải bó xôi 5.63%, rau má 4.69%, chùm ngây 3.75%...)
- 22 thành phần tổng cộng

Sự thật theo kiểm nghiệm:
- Chất xơ chỉ 0.935% (KHÔNG phải 28%)
- Mỗi viên chỉ chứa 0.03g chất xơ
- Nền sản phẩm: Sorbitol syrup 70% + đường cát + gelatin + phụ gia tạo gel
- 29 thành phần thực tế (không phải 22), đa số là phụ gia

### 3.5. 3 câu nguyên văn từ livestream (cấu thành tội)

1. *"1 viên kẹo này tương đương 1 đĩa rau luộc."*
2. *"Một ngày chỉ cần ăn 2-3 viên là đủ chất xơ cho người bình thường."*
3. *"Sản phẩm có thể thay rau xanh trong bữa ăn cho cả trẻ nhỏ."*

### 3.6. Pattern Kera vs Pattern AI startup

```
┌─────────────────────────────┐  ┌────────────────────────────┐
│   PATTERN KERA              │  │   PATTERN AI STARTUP        │
├─────────────────────────────┤  ├────────────────────────────┤
│ 1. Founder không kiểm tra   │  │ 1. Founder không test AI    │
│    nguyên liệu thật         │  │    ở edge case              │
│ 2. Marketing: "1 viên =     │  │ 2. Marketing: "AI thay 1    │
│    1 đĩa rau"               │  │    nhân viên"               │
│ 3. Thực tế: 0.935% rau,     │  │ 3. Thực tế: AI làm 30%      │
│    70% sorbitol             │  │    việc, sai 15%            │
│ 4. KH tin, mua hàng         │  │ 4. KH B2B mua, dùng thật    │
│ 5. Phát hiện → Điều 198     │  │ 5. Phát hiện → Điều 198     │
│ 6. Đi tù 2-3 năm            │  │ 6. Đi tù 1-5 năm            │
└─────────────────────────────┘  └────────────────────────────┘
```

### 3.7. Điểm fail có thể tránh

1. **Founder không kiểm tra nguyên liệu Asia Life:** Lẽ ra nên gửi sample đi 3 đơn vị kiểm nghiệm độc lập trước khi launch
2. **Không có template xác nhận từng câu marketing:** Lẽ ra mỗi câu trong livestream phải có ít nhất 1 evidence
3. **Không lưu log buổi livestream:** Lẽ ra nên có recording + script để rà soát
4. **Phản ứng chậm với kiểm nghiệm khách hàng:** Lẽ ra ngày đầu tháng 3 đã phải triệu hồi, không phải đợi đến 24/3 mới có quyết định

---

## 4. CASE 2 — VỤ MR PIPS / SHARK BÌNH

### 4.1. Quy mô vận hành

**Phó Đức Nam** (Mr Pips, sinh 1994, TP.HCM) + **Isik Uran** (Thổ Nhĩ Kỳ) lập từ 2018:

| Hạng mục | Con số |
|----------|--------|
| Website giả mạo (GKFX, ZenoMarkets, DK Trade...) | **36 trang** |
| Văn phòng (Hà Nội 24, TP.HCM, Đà Nẵng, Bình Dương) | **44 văn phòng** |
| Nhân viên (marketing, CSKH, kỹ thuật, "tổ tư vấn pháp chế") | **1,918 người** |
| Cựu công an được thuê làm tư vấn | 2 người |
| Công ty bình phong ("công ty ma") | **85 công ty** |

### 4.2. Hậu quả (Kết luận điều tra 12/2/2026)

- 738 vụ lừa đảo toàn quốc
- 2,661 nạn nhân nạp tiền lần đầu (~50 triệu USD)
- Mr Pips chịu trách nhiệm: 1,301 tỷ đồng
- Nạn nhân lớn nhất mất 35 tỷ đồng

### 4.3. Tài sản công an thu giữ: 5,200 tỷ đồng

- 246kg vàng nguyên khối
- 31 siêu xe + 7 mô tô hạng sang
- 59 đồng hồ giới hạn (~300 tỷ đồng)
- 84 trang sức vàng kim cương
- Phong tỏa 125 bất động sản

### 4.4. Vai trò của Shark Bình

**Nguyễn Hòa Bình** = Chủ tịch HĐQT NextTech + Chủ tịch HĐQT Công ty Cổ phần Ngân Lượng.

**Tội danh:** Rửa tiền theo Khoản 3 Điều 324 BLHS.

**Lý do truy tố** (nguyên văn cáo trạng):

> *"Từ tháng 6/2020, Nguyễn Hòa Bình cùng các nhân viên Công ty Ngân Lượng — gồm Nguyễn Thị Nam và Trần Thị Thanh Tâm — biết rõ các sàn giao dịch DK Trade, ASX, ACX, Sea Investing, Honor, ScopeMarkets do Phó Đức Nam vận hành có dấu hiệu phạm tội, đang bị cơ quan công an xác minh. Tuy nhiên, để hưởng lợi từ phí giao dịch qua ví Ngân Lượng, Bình vẫn chỉ đạo tiếp tục vận hành hệ thống."*

### 4.5. Số liệu thiệt hại qua Ngân Lượng

Từ 15/6/2020 đến 23/9/2022:
- 150 nạn nhân chuyển vào ví Ngân Lượng
- Tổng **213.4 tỷ đồng**
- Để nạp tiền vào các sàn forex của Mr Pips

### 4.6. Bài học cho founder AI

**Pattern Shark Bình → Pattern AI startup:**

```
┌──────────────────────────┐  ┌──────────────────────────┐
│  SHARK BÌNH              │  │  STARTUP AI ĐIỂN HÌNH    │
├──────────────────────────┤  ├──────────────────────────┤
│ Cung cấp ví điện tử      │  │ Cung cấp AI tạo content  │
│ Mr Pips dùng nhận tiền   │  │ Customer dùng spam/lừa   │
│ CÓ DẤU HIỆU CẢNH BÁO     │  │ CÓ DẤU HIỆU CẢNH BÁO     │
│ Tiếp tục vì hưởng phí    │  │ Tiếp tục vì doanh thu    │
│ → Tội Rửa tiền (Điều 324)│  │ → Có thể bị áp Điều 324  │
└──────────────────────────┘  └──────────────────────────┘
```

**3 bài học cốt lõi:**

1. **Founder không cần là kẻ chính phạm.** Vai trò "ngân hàng", "nền tảng", "vendor" đủ.
2. **"Tôi không biết" không phải lý do biện hộ** khi có dấu hiệu rõ ràng (báo cáo lạm dụng, lưu lượng bất thường, khách hàng phản ánh).
3. **Hồ sơ chứng cứ là bảo hiểm.** Phải chứng minh: thấy dấu hiệu → điều tra → chặn user → báo cáo cơ quan có thẩm quyền.

---

## 5. CASE 3 — VỤ RÒ RỈ CIC + CƠN BÃO DỮ LIỆU 2025-2026

### 5.1. Vụ CIC tháng 9/2025

**Trung tâm Thông tin tín dụng quốc gia (CIC)** — thuộc Ngân hàng Nhà nước Việt Nam:
- 52 triệu khách hàng cá nhân
- 1.2 triệu khách hàng doanh nghiệp
- Thu thập từ TOÀN BỘ ngân hàng, quỹ tín dụng, công ty tài chính

Đầu 9/2025: dữ liệu xuất hiện trên diễn đàn hacker quốc tế.

### 5.2. Các vụ rò rỉ liên tiếp 2025-2026

| Vụ | Mô tả | Quy mô |
|----|-------|--------|
| Giao Hàng Nhanh (GHN) | Tên KH, SĐT, địa chỉ, mã vận đơn | Bị rao bán |
| Sapo | Dữ liệu mua sắm + thông tin KH | Bị rao bán |
| Tuyên Quang (1/2026) | Nhóm bán email người dùng toàn cầu | **8.4 tỷ email** |
| Quảng Nam | Nhân viên Mirae Asset bán hồ sơ | **150,000 hồ sơ** người Việt |

### 5.3. Bức tranh tổng thể (Bộ Công an)

- 6 tháng đầu 2025: 56 vụ mua bán dữ liệu xử lý
- 110+ triệu hồ sơ bị bán
- 191 vụ rao bán (gấp 3 lần cùng kỳ 2024)
- Năm 2024: 14.5 triệu tài khoản VN bị rò rỉ (12% toàn cầu)

---

## 6. KHUNG PHÁP LÝ ĐANG ÁP DỤNG

### 6.1. Bộ luật Hình sự Việt Nam — Điều 198 (Lừa dối khách hàng)

**Trích nguyên văn:**

> *"Người nào trong việc mua, bán hàng hóa hoặc cung cấp dịch vụ mà cân, đong, đo, đếm, tính gian hàng hóa, dịch vụ — hoặc dùng thủ đoạn gian dối khác — thu lợi bất chính, thì bị phạt:"*

| Khoản | Hành vi | Hình phạt |
|-------|---------|-----------|
| 1 | Vi phạm cơ bản | Cảnh cáo / phạt tiền 10-100 triệu / cải tạo không giam giữ đến 3 năm |
| 2 | **Thu lợi từ 50 triệu đồng trở lên** | **Phạt tù từ 1 năm đến 5 năm** |

**4 yếu tố cấu thành tội với startup AI:**

1. Có hoạt động bán hàng/dịch vụ (SaaS, API, subscription AI)
2. Có thông tin sai sự thật (marketing nói AI làm X, thực tế làm 30%)
3. Khách hàng tin và mua dựa vào đó
4. Founder "biết rõ" hoặc "biết rõ là không biết"

→ Đủ 4 → truy tố. Thu lợi >50 triệu → tù 1-5 năm.

### 6.2. Bộ luật Hình sự Việt Nam — Điều 324 (Rửa tiền)

**Cấu thành tội:**
- Người nào thực hiện một trong các hành vi sau đối với tiền, tài sản do mình hoặc biết rõ là do người khác phạm tội mà có
- Bao gồm: tham gia trực tiếp/gián tiếp giao dịch tài chính, ngân hàng để che giấu nguồn gốc bất chính

**Hình phạt:**
- Khoản 1: 1-5 năm tù
- Khoản 2: 5-10 năm tù
- **Khoản 3** (vụ Shark Bình): **10-15 năm tù**
- Khoản 4: 15-20 năm tù

### 6.3. Luật AI Việt Nam — 134/2025/QH15

- Thông qua: 10/12/2025
- Hiệu lực: **1/3/2026**
- Phạm vi: 35 điều, 8 chương
- Là luật AI standalone đầu tiên của Việt Nam

**Phân loại 3 tầng theo Điều 9:**

| Tầng | Đặc điểm | Lĩnh vực | Nghĩa vụ chính |
|------|----------|----------|----------------|
| **Cao** | Tác động đáng kể tới sức khỏe, an toàn, quyền cơ bản, an ninh quốc gia | Y tế, giáo dục, tài chính, tuyển dụng, hành pháp | Đánh giá phù hợp + Đăng ký CSDL AI quốc gia + Giám sát con người + Báo cáo sự cố + Lưu log |
| **Trung bình** | Có thể gây nhầm lẫn cho người dùng | Chatbot, deepfake, gen AI | Phải dán nhãn ("đây là AI") + Thông báo Bộ KH&CN |
| **Thấp** | AI nội bộ, không tác động lớn | Lọc spam, gợi ý, tự động hóa | Tự nguyện công khai |

**Lưu ý quan trọng:**
- Bên cung cấp tự phân loại trước khi deploy
- Tầng Cao + Trung bình phải thông báo Bộ KH&CN qua cổng AI quốc gia
- Vendor AI nước ngoài phải có đại diện pháp lý tại VN
- Phạt: tới 2 tỷ đồng cho tổ chức (~75,800 USD)
- **Ân hạn:** 18 tháng cho health/edu/finance, 12 tháng cho lĩnh vực khác

### 6.4. Luật Bảo vệ dữ liệu cá nhân (PDPL) — 91/2025/QH15

- Thông qua: 26/6/2025
- Hiệu lực: **1/1/2026**
- 39 điều
- Là luật BVDLCN standalone đầu tiên (thay Nghị định 13/2023)

#### Điều 8 — Phạt vi phạm

| Loại vi phạm | Mức phạt |
|--------------|----------|
| Mua bán dữ liệu cá nhân | **Đến 10 lần khoản thu từ vi phạm** |
| Vi phạm nghiêm trọng | **Đến 5% doanh thu năm trước** |
| Phạt hành chính | Đến 3 tỷ đồng |
| Đủ cấu thành tội phạm | Truy cứu hình sự + bồi thường thiệt hại |

#### Điều 30 — Chuyên biệt cho AI / Dữ liệu lớn / Điện toán đám mây / Blockchain

5 yêu cầu:
1. Tuân thủ pháp luật + đạo đức
2. **Kiểm soát bảo mật ngay từ thiết kế** (security by design)
3. **Phải kiểm toán được** (auditable)
4. Có **nhân sự bảo vệ dữ liệu (DPO)** — startup ân hạn 5 năm
5. Đánh giá tác động (DPIA) trong **60 ngày** kể từ khi bắt đầu xử lý

**Áp dụng startup AI:**
- Engineer paste customer data lên ChatGPT public = chuyển dữ liệu ra nước ngoài = phải có CTIA (Cross-border Transfer Impact Assessment) + có thể vi phạm Điều 8
- Phạt = 10 lần doanh thu sản phẩm liên quan đến vi phạm

### 6.5. EU AI Act + Italy Luật 132/2025

#### EU AI Act timeline

| Mốc | Yêu cầu | Hậu quả |
|------|---------|---------|
| 1/8/2024 | Có hiệu lực | -- |
| 2/2/2025 | Cấm tuyệt đối (chấm điểm xã hội, thao túng) | €35 triệu hoặc 7% doanh thu |
| 2/8/2025 | Nghĩa vụ AI đa năng (GPAI) + Cơ chế phạt + Văn phòng AI EU | €15 triệu hoặc 3% doanh thu |
| **2/8/2026** | **Hệ thống tầng cao hiệu lực đầy đủ** | Cùng mức |
| 2/8/2027 | Mô hình ra mắt trước phải tuân thủ | -- |

#### Italy Luật 132/2025 (hiệu lực 10/10/2025)

- Phạt hình sự kèm phạt tiền đến **€774,685**
- Tình tiết tăng nặng cho tội phạm có AI hỗ trợ
- **Phát tán deepfake bất hợp pháp = 1-5 năm tù**
- Thao túng thị trường tài chính có AI hỗ trợ = phạt tăng nặng

#### Ưu đãi cho startup early-stage

- EU AI Act: phạt áp dụng MỨC THẤP HƠN trong hai cách tính (số tuyệt đối hoặc % doanh thu) — thay vì cao hơn như tập đoàn lớn
- PDPL: ân hạn 5 năm cho startup chưa cần DPO

### 6.6. Lịch tuân thủ Việt Nam — 4 mốc deadline

```
Hôm nay (5/2026)
   │
   ├─ 1/1/2026 [đã qua] PDPL + DTI Law hiệu lực
   ├─ 1/3/2026 [đã qua] Luật AI Việt Nam 134/2025
   ├─ 2/8/2026 [3 tháng nữa] EU AI Act high-risk hiệu lực đầy đủ
   └─ 1/3/2027 [10 tháng nữa] Hết ân hạn cho startup non-health/edu/finance
```

**5 việc cần làm ngay tuần này:**
1. Nộp DPIA trong 60 ngày từ khi bắt đầu xử lý dữ liệu cá nhân
2. Nộp CTIA nếu dùng vendor AI nước ngoài (OpenAI, Anthropic)
3. Tự phân loại tầng rủi ro AI và thông báo Bộ KH&CN qua cổng AI quốc gia (medium/high)
4. Nếu có user EU: chỉ định đại diện pháp lý EU
5. Cập nhật Privacy Policy theo PDPL (consent rõ ràng, đầy đủ thông tin)

---

## 7. WORKSHOP DETAILED INSTRUCTIONS

### 7.1. Workshop 1 — Rà soát claim marketing (15 phút)

**Tình huống:** Bạn là Quang Linh Vlogs vào tháng 2/2025 — chưa bị bắt. Có 15 phút để rà soát mọi câu marketing và sửa trước khi quá muộn.

**Vật liệu cần (1 phút):**
- Trang giới thiệu (landing page) chính
- Bài đăng pin trên Twitter/Facebook/LinkedIn
- Slide "What we do" trong pitch deck Day 19

**4 bước (14 phút):**

#### Bước 1 (3 phút) — Highlight

Mở từng tài liệu. Đánh dấu mọi câu nói về AI:
- "AI làm được X"
- "Tăng năng suất Y%"
- "Thay thế Z"
- "Tự động hóa W"
- "AI thông minh hơn..."

#### Bước 2 (5 phút) — Phân loại 3 mức

| Mức | Ý nghĩa | Ví dụ |
|------|---------|-------|
| **A** | Chứng minh được — có data, demo, case study thật | "AI tăng productivity 35% theo A/B test trên 200 user" |
| **B** | Chưa chứng minh nhưng có thể — cần test thêm | "AI tăng productivity đáng kể (đang đo lường)" |
| **C** | Thổi phồng — không có evidence (vùng Điều 198) | "AI tăng năng suất 10x" — không có data |

#### Bước 3 (4 phút) — Viết lại honest version

Mỗi câu Mức C, viết phiên bản trung thực:

| Câu Mức C | Honest version |
|-----------|----------------|
| "AI thay thế 1 nhân viên CSKH" | "AI tự động hóa 30% câu hỏi đơn giản, đội ngũ CSKH có thể tập trung case phức tạp" |
| "AI hiểu mọi khách hàng" | "AI hiểu được 75% câu hỏi tiếng Việt phổ thông; câu phức tạp chuyển sang con người" |
| "AI giảm 50% chi phí" | "Customer trung bình giảm 20-30% chi phí; ROI tùy use case (range 10-40%)" |

#### Bước 4 (2 phút) — Tự kiểm tra

- Landing page mới có còn convert được không?
- Nếu không, vấn đề không phải honest version — vấn đề là product-market fit yếu

#### Output: file `marketing_claims_audit.md`

**Template:**

```markdown
# Marketing Claims Audit — [Tên startup]

**Ngày rà soát:** [DD/MM/YYYY]
**Người rà soát:** [Founder name]

## Bảng claim audit

| # | Câu gốc | Vị trí | Mức | Evidence hiện có | Honest version | Action |
|---|---------|--------|-----|------------------|----------------|--------|
| 1 | "AI tăng năng suất 10x" | Landing hero | C | Không có A/B test | "AI giúp 30% user hoàn thành nhanh hơn 2x" | Fix tuần này |

## Thống kê
- Tổng số claim: __
- Mức A: __ Mức B: __ Mức C: __

## TOP 3 priority sửa ngay
1. ...
2. ...
3. ...
```

### 7.2. Workshop 2 — 3 câu hỏi 30 phút (15 phút)

**Vật liệu:** PRD Day 17 + Danh sách khách hàng Day 16 + Công nghệ đang dùng hiện tại

#### Bước 1 (3 phút) — Câu hỏi 1: User EU?

- Có 1 user EU không? Kiểm tra customer list
- Có kế hoạch mở rộng EU 12 tháng tới không?
- Output: YES/NO

#### Bước 2 (3 phút) — Câu hỏi 2: Dữ liệu Việt Nam?

- Liệt kê 5 loại dữ liệu cá nhân đang xử lý:
  - Tên / SĐT / Email
  - Hành vi (browsing, click)
  - Vị trí (IP, GPS)
  - Biometric (face, voice)
  - Tài chính (giao dịch, thẻ)
- Có chuyển dữ liệu ra nước ngoài không?
  - Dùng AI nước ngoài (OpenAI, Anthropic API) = CHUYỂN
  - Cloud Mỹ (AWS US, Azure US) = CHUYỂN
- Output: PDPL áp dụng + cần CTIA hay không

#### Bước 3 (5 phút) — Câu hỏi 3: Tầng rủi ro Luật AI VN?

| Lĩnh vực | Tầng |
|----------|------|
| Y tế, giáo dục, tài chính, tuyển dụng, hành pháp | **Cao** |
| Chatbot, deepfake, gen AI tạo content | **Trung bình** |
| Còn lại | **Thấp** |

Viết 1 câu lập luận tại sao xếp tầng đó.

#### Bước 4 (3 phút) — Lịch deadlines

Note 4 mốc vào Notion:
- 1/1/2026: PDPL + DTI Law
- 1/3/2026: Luật AI Việt Nam
- 2/8/2026: EU AI Act high-risk
- 1/3/2027: Hết ân hạn

#### Output: file `territorial_scope.md`

**Template:**

```markdown
# Territorial Scope — [Tên startup]
**Date:** [DD/MM/YYYY]

## Câu hỏi 1: User EU?
- Có user EU hiện tại: __ (count)
- Kế hoạch mở rộng EU 12 tháng: YES/NO
- **Kết luận:** EU AI Act áp dụng = YES/NO

## Câu hỏi 2: Dữ liệu Việt Nam?
### Loại dữ liệu cá nhân đang xử lý:
1. ...
### Có chuyển ra nước ngoài: ...
### Kết luận: PDPL áp dụng = YES (gần như chắc chắn) + CTIA = YES/NO

## Câu hỏi 3: Tầng rủi ro Luật AI VN?
- Phân loại: Cao / Trung bình / Thấp
- Lập luận: ...
- Nghĩa vụ tương ứng: ...

## 4 deadlines đã note vào Notion
- [ ] 1/1/2026 — PDPL hiệu lực (đã qua)
- [ ] 1/3/2026 — Luật AI VN hiệu lực (đã qua)
- [ ] 2/8/2026 — EU AI Act high-risk (3 tháng nữa)
- [ ] 1/3/2027 — Hết ân hạn (10 tháng nữa)
```

### 7.3. Workshop 3 — Hồ sơ chứng cứ founder (15 phút)

**Tình huống:** Bạn là Shark Bình tháng 5/2020 — chưa bị truy tố. Build hồ sơ để khi cơ quan điều tra hỏi "anh có biết dấu hiệu không?", chứng minh được mình đã thẩm định.

#### Bước 1 (5 phút) — Đối chiếu 5 loại hồ sơ

| # | Loại hồ sơ | Mục đích | Cập nhật khi |
|---|-----------|----------|--------------|
| 1 | Nhật ký kiểm thử claim AI | Chống Điều 198 (Kera) | Mỗi feature mới + hằng quý |
| 2 | Hồ sơ rà soát điều khoản vendor | Chống vendor risk | Hằng quý + khi vendor đổi |
| 3 | Nhật ký giám sát giao dịch bất thường | Chống Điều 324 (Pips) | Hằng tuần |
| 4 | DPIA / CTIA đã nộp | Tuân thủ PDPL Điều 30 | 1 lần + khi đổi luồng dữ liệu |
| 5 | Phê duyệt nội dung marketing | Chống Điều 198 (founder ký) | Trước mỗi launch / livestream |

Tick: ✓ ĐÃ có (link đến file hiện tại) / ✗ CHƯA có (viết deadline khi sẽ build)

#### Bước 2 (5 phút) — Chọn TOP 1 ưu tiên

Trong các ô ✗:
- Cái nào rủi ro cao nhất với startup mình hiện tại?
- Lý do (1 câu)

#### Bước 3 (5 phút) — Hành động 1 tuần

Cho TOP 1:
- Template tài liệu (mẫu 3-5 dòng)
- Người chịu trách nhiệm
- Tần suất cập nhật (hằng tuần / hằng quý / mỗi feature)

#### Output: file `document_trail.md`

**Template:**

```markdown
# Document Trail — [Tên startup]
**Date:** [DD/MM/YYYY]

## Bảng đối chiếu 5 loại hồ sơ

| # | Loại | Status | Link/Path | Deadline build |
|---|------|--------|-----------|----------------|
| 1 | Nhật ký kiểm thử claim AI | ✓/✗ | ... | ... |
| 2 | Hồ sơ rà soát điều khoản vendor | ✓/✗ | ... | ... |
| 3 | Nhật ký giám sát giao dịch bất thường | ✓/✗ | ... | ... |
| 4 | DPIA / CTIA | ✓/✗ | ... | ... |
| 5 | Phê duyệt nội dung marketing | ✓/✗ | ... | ... |

## TOP 1 ưu tiên
**Loại:** [#X - Tên loại]
**Lý do:** [1 câu]

## Template build trong 1 tuần
### Người chịu trách nhiệm: [Name + Role]
### Tần suất cập nhật: [...]
### Sample 3-5 dòng:
[Example template content]
```

### 7.4. Lab 4 — AI Compliance Audit (50 phút)

**Khác Lab Day 21:**
- Day 21: AI tìm rủi ro tài chính (đo bằng tháng runway)
- Day 22: AI tìm vi phạm pháp lý cụ thể (kèm Điều luật + cách sửa)

**5 bước (10 phút mỗi bước):**

#### Bước 1: Chuẩn bị tài liệu đầu vào

- PRD Day 17
- Marketing materials (landing page, pitch deck)
- Sơ đồ luồng dữ liệu — vẽ nhanh nếu chưa có:
  ```
  Data từ user → đến đâu → xử lý gì → lưu đâu → chia sẻ ai
  ```

#### Bước 2: Chạy prompt AI Compliance Officer

Copy prompt ở phần 8.

#### Bước 3: Đối chiếu thủ công

So sánh AI output với output Workshop 1, 2, 3:

| Loại vi phạm | Workshop liên quan | Đối chiếu |
|--------------|-------------------|-----------|
| Marketing thổi phồng (Kera) | WS1 — rà soát claim | AI tìm cái nào bạn bỏ sót? |
| Tầng rủi ro AI | WS2 — 3 câu hỏi | AI có xếp cùng tầng không? |
| Rủi ro vendor/thanh toán | WS3 — hồ sơ chứng cứ | AI thấy thiếu sót nào? |
| Dữ liệu cá nhân | Tất cả + Tech stack | Vi phạm Điều 30 nào ẩn? |

#### Bước 4: Ưu tiên TOP 5

Mỗi vi phạm viết 3 hành động sửa cụ thể.

#### Bước 5: Tổng hợp file cuối — `compliance_audit_v2.md`

**Tiêu chí đạt:**

1. ✓ Có ≥7 vi phạm (đủ 4 loại)
2. ✓ Mỗi vi phạm có Điều luật cụ thể (không generic "vi phạm pháp luật")
3. ✓ Mỗi vi phạm có trích nguyên văn bằng chứng từ tài liệu của bạn
4. ✓ Mỗi vi phạm có vụ Việt Nam khớp pattern (Kera / Pips / CIC)
5. ✓ Top 5 nghiêm trọng nhất có 3 hành động sửa mỗi cái
6. ✓ Tất cả output tiếng Việt — có thể email luật sư đọc trực tiếp

---

## 8. PROMPT AI COMPLIANCE OFFICER (TIẾNG VIỆT)

Copy nguyên văn prompt này khi chạy Lab 4:

```
Bạn là Chuyên viên Tuân thủ pháp lý chuyên về startup AI Việt Nam. Nắm vững:
- Luật AI Việt Nam 134/2025/QH15 (hiệu lực 1/3/2026)
- Luật BVDLCN 91/2025/QH15 (hiệu lực 1/1/2026)
- Bộ luật Hình sự VN: Điều 174 (Lừa đảo), 198 (Lừa dối khách hàng), 324 (Rửa tiền)
- EU AI Act + GDPR

3 vụ enforcement Việt Nam cần áp dụng pattern:
- Vụ kẹo Kera 11/2025 (3 KOL — Quang Linh, Hằng Du Mục, Thùy Tiên — đi tù theo Điều 198)
- Vụ Mr Pips 2/2026 (Shark Bình bị đề nghị truy tố theo Điều 324)
- Vụ rò rỉ CIC 9/2025 (PDPL Điều 8 phạt 10x doanh thu)

Hãy rà soát sản phẩm sau để tìm vi phạm pháp lý tiềm năng:

[paste PRD + marketing materials + tech stack + data flow]

Format mỗi vi phạm tìm thấy:

VI PHẠM N: [tên ngắn]
- Luật áp dụng: [Luật AI VN / PDPL / BLHS / EU AI Act]
- Điều: [số điều + khoản cụ thể]
- Bằng chứng trong sản phẩm: [trích nguyên văn từ tài liệu]
- Pattern khớp với: [vụ Việt Nam tương tự — Kera/Pips/CIC]
- Hành động sửa: [founder làm trong 1 tuần]
- Deadline: [theo grace period luật]

Yêu cầu tối thiểu tìm:
- 3 vi phạm về marketing claim (kiểu Kera)
- 2 vi phạm về dữ liệu cá nhân (PDPL Điều 30)
- 1 vi phạm về phân loại rủi ro AI (Điều 9 Luật AI VN)
- 1 vi phạm về vendor/payment (kiểu Pips)

Output toàn bộ bằng tiếng Việt. Trả lời thẳng thắn, không né tránh.
```

---

## 9. RUBRIC ĐÁNH GIÁ — 5 FILE NỘP BÀI

| Tiêu chí | Excellent (10) | Pass (7) | Fail (≤4) |
|----------|----------------|----------|-----------|
| `marketing_claims_audit.md` | Có ≥10 claim, đủ Mức A/B/C, mọi Mức C có honest version chi tiết | Có 5+ claim, có honest version | <5 claim hoặc không có honest version |
| `territorial_scope.md` | 3 câu trả lời rõ ràng + lập luận + 4 deadline note vào Notion | Trả lời cơ bản, có deadline | Trả lời mơ hồ, thiếu deadline |
| `document_trail.md` | Đối chiếu đủ 5 loại + TOP 1 + template chi tiết | Đối chiếu cơ bản, có TOP 1 | Thiếu TOP 1 hoặc template |
| `compliance_audit_v2.md` | ≥7 vi phạm + Điều luật cụ thể + bằng chứng + pattern VN + 3 hành động | 5-6 vi phạm + Điều luật | <5 vi phạm hoặc generic |
| `compliance_calendar.xlsx` | (Cấp sẵn) + Note vào lịch cá nhân | -- | -- |

---

## 10. 12 KEY QUOTES TỪ 3 VỤ VIỆT NAM

### Vụ kẹo Kera

1. *"Mình lập công ty livestream bán hàng nhé. Lên TikTok bán còn dễ hơn vlog."* — Quang Linh & Hằng Du Mục, 7/2024

2. *"Em làm kẹo rau củ. Bây giờ ai cũng quan tâm sức khỏe. 1 viên kẹo = 1 đĩa rau. Bán chạy lắm."* — Thùy Tiên, 11/2024

3. *"1 viên kẹo này tương đương 1 đĩa rau luộc."* — Slogan livestream

4. *"Sản phẩm có thể thay rau xanh trong bữa ăn cho cả trẻ nhỏ."* — Quảng cáo livestream

5. *"đây là bài học lớn"* — Thùy Tiên xin lỗi 6/3/2025 (không cứu được)

6. *"Các bị cáo BIẾT RÕ kết quả kiểm nghiệm chất xơ trong kẹo Kera chỉ chiếm 0.935%. Thực tế LÀ KHÔNG BIẾT kẹo Kera được sản xuất từ nguyên liệu nào... nhưng với mục đích bán được nhiều sản phẩm, đã thống nhất xây dựng kịch bản giới thiệu, đưa ra các thông tin không đúng sự thật, thổi phồng tính năng, công dụng."* — Cáo trạng

### Vụ Mr Pips / Shark Bình

7. *"Từ tháng 6/2020, Nguyễn Hòa Bình cùng các nhân viên Công ty Ngân Lượng biết rõ các sàn DK Trade, ASX, ACX, Sea Investing, Honor, ScopeMarkets do Phó Đức Nam vận hành có dấu hiệu phạm tội, đang bị cơ quan công an xác minh."* — Cáo trạng 12/2/2026

8. *"Tuy nhiên, để hưởng lợi từ phí giao dịch qua ví Ngân Lượng, Bình vẫn chỉ đạo tiếp tục vận hành hệ thống."* — Cáo trạng

9. **Founder pattern:** *"Biết dấu hiệu, vẫn xử lý thanh toán → Rửa tiền."*

### Vụ rò rỉ CIC

10. **Bộ Công an 6 tháng đầu 2025:** "56 vụ mua bán dữ liệu xử lý, 110+ triệu hồ sơ bị bán, 191 vụ rao bán (gấp 3 lần cùng kỳ 2024)."

### Câu cốt lõi nguyên lý Day 22

11. *"Phanh giữ bạn không đâm vào gốc cây. Giấy phép giữ bạn không vào đồn."*

12. *"Quang Linh, Hằng Du Mục, Thùy Tiên, Shark Bình — không phải tội phạm chuyên nghiệp. Họ là founder và KOL Việt Nam đang ngồi tù hoặc bị truy tố. Khác biệt giữa họ và bạn = 5 file bạn vừa làm hôm nay."*

---

## 11. CHECKLIST TUÂN THỦ — 30 NGÀY ĐẦU SAU DAY 22

### Tuần 1
- [ ] Hoàn thành 5 file Day 22 + nộp lên hệ thống
- [ ] Note 4 mốc deadline vào Notion + Calendar
- [ ] Chia sẻ `marketing_claims_audit.md` với team marketing
- [ ] Sửa các câu Mức C trên landing page trước khi launch tiếp

### Tuần 2
- [ ] Build TOP 1 hồ sơ chứng cứ từ Workshop 3
- [ ] Lên kế hoạch nộp DPIA (60 ngày)
- [ ] Audit vendor: AI nào đang dùng? Có đại diện pháp lý VN chưa?
- [ ] Cập nhật Privacy Policy theo PDPL

### Tuần 3
- [ ] Tự phân loại tầng rủi ro AI Điều 9 + thông báo Bộ KH&CN (medium/high)
- [ ] Thiết lập abuse monitoring (cho founder Pattern Pips)
- [ ] Tạo template phê duyệt marketing — founder ký mỗi launch
- [ ] Chạy lại AI Compliance Audit sau khi sửa

### Tuần 4
- [ ] Review toàn bộ với CTO/CMO/legal advisor
- [ ] Email luật sư bạn ngoài 5 file để review
- [ ] Lên kế hoạch xử lý 5 vi phạm nghiêm trọng nhất
- [ ] Đặt lịch quarterly review

---

## 12. NGUỒN THAM KHẢO

### Văn bản pháp luật
- Luật AI Việt Nam số 134/2025/QH15 (Quốc hội, 10/12/2025)
- Luật Bảo vệ dữ liệu cá nhân số 91/2025/QH15 (Quốc hội, 26/6/2025)
- Bộ luật Hình sự Việt Nam (đang hiệu lực) — Điều 174, 198, 324
- EU AI Act (Regulation 2024/1689)
- Italy Law 132/2025

### Cáo trạng & kết luận điều tra
- Cáo trạng vụ kẹo Kera (TAND TP.HCM, 11/2025)
- Kết luận điều tra vụ Mr Pips (Bộ Công an, 12/2/2026)
- Báo cáo Bộ Công an về vụ rò rỉ dữ liệu 2024-2025

### Tài liệu tham chiếu cho founder
- Day 21 handbook — Phanh nội bộ + 3 R's
- Day 17 PRD template
- Day 19 pitch deck template
- Day 20 financial model

### Liên hệ chuyên gia
- Luật sư AI/PDPL Việt Nam — Trao đổi với mentor để có recommendation
- Cổng thông tin AI quốc gia — Bộ KH&CN (đang xây dựng, hiệu lực 1/3/2026)
- DPO consultant — DPO as a Service (cho startup chưa cần full-time DPO)

---

## 13. TỔNG KẾT DAY 22

Sau 4 tiếng học, founder đã có:

**5 deliverables cụ thể:**
1. `marketing_claims_audit.md` — Bằng chứng founder đã rà soát claim, tránh Điều 198
2. `territorial_scope.md` — Xác định chính xác luật nào áp dụng + 4 deadline
3. `document_trail.md` — 5 loại hồ sơ chứng cứ bảo vệ founder cá nhân
4. `compliance_audit_v2.md` — Audit toàn diện theo từng Điều luật cụ thể
5. `compliance_calendar.xlsx` — Lịch tuân thủ + checklist 4 mốc deadline

**Ghép với Day 21 → Hồ sơ Tuân thủ Toàn diện (9 file):**

Khi gọi vốn 3-6 tháng tới, kẹp toàn bộ 9 file vào hồ sơ nhà đầu tư. Đây là tín hiệu raise quality cực mạnh — vì 95% startup VC gặp KHÔNG có bộ này.

**Câu chốt cốt lõi cần nhớ:**

> *Quang Linh, Hằng Du Mục, Thùy Tiên, Shark Bình — không phải tội phạm chuyên nghiệp.*
> *Họ là founder/KOL Việt Nam đang ngồi tù hoặc bị truy tố.*
> *Khác biệt giữa họ và bạn = 5 file bạn vừa làm hôm nay.*

---

*Hết Day 22 Handbook.*
