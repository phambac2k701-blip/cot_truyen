# PLAYER-FACING STORY

> **Status:** STORY DESIGN — STAGE 5 / DESIGN LOCK CANDIDATE  
> **Parent canon:** MASTER_GAME_BIBLE.md  
> **Stage 1:** BACKSTAGE_CRIME_TRUTH.md  
> **Stage 2:** CHARACTER_WEB.md  
> **Stage 3:** OBJECTIVE_TIMELINE.md  
> **Stage 4:** CLUE_GRAPH.md  
> **Repository:** phambac2k701-blip/cot_truyen  
> **Setting:** Hà Nội, 2026  
> **Scope:** story flow người chơi thực sự trải nghiệm qua Bắc, từ opening tới climax/endings  
> **Không bao gồm:** full dialogue line-by-line, puzzle implementation chi tiết, cinematic shot list, level scripting chi tiết

---

# 0. DESIGN CONTRACT

Stage 5 không thay đổi objective truth và không tạo clue mới để cứu một scene.

Xương sống bất biến:

- Phúc muốn rút là điểm khởi phát khủng hoảng.
- Hạnh vượt doctrine vì sợ thất bại.
- Huyền phát hiện anomaly bằng công việc hợp pháp.
- Khoa giấu độ sâu review.
- Hùng hạ gói nhạy cảm xuống luồng thường vì che sai phạm riêng.
- Bắc không được ai chọn. Cậu nhận một việc part-time hợp pháp vì thiếu tiền.
- Nam gặp Bắc như hàng xóm trước khi biết Bắc chạm Tân Lộ.
- Tuấn không biết core crime.
- Minh không phải member network.
- Tân Lộ và Minh Trạch chủ yếu là các institution hợp pháp.
- Vũ đã điều tra vụ Phúc trước Bắc.
- Không có single magic evidence.
- Boss reveal phải chứng minh quyền command hiện tại của Nam bằng corroboration, không phải biography hay villain monologue.
- True ending cần A+B+C+D và preservation timing.

Player-facing principle:

**Bắc không “đi tìm một vụ án”. Cậu chỉ liên tục gặp những thứ không khớp, cho tới lúc việc bỏ qua chúng trở nên khó hơn việc kiểm tra.**

---

## 0.1. Authored clock và source deadlines

OBJECTIVE_TIMELINE §0.1–0.2 là shared schedule: reading/inspect/phone UI/private hypotheses/hints/retries0; fixed committed dialogue groups, travel và deliberate wait mới tăng clock. Cost/finish or departure→arrival card trước confirm, charge once và persist clock/flags/receipts qua save-load. Play budget90m không fail timer. Source request≠receipt≠authentication; police đã có source/contact/context tự collect, không chờ request checkbox lần hai. Local11:00/11:30/12:30 không global CLEANUP lock17:00; fresh actual acceleration warning W đặt deadline=max(16:30,W+145m) chỉ nếu sớm hơn17:00 và còn saving action.

# 1. NHỊP TỔNG THỂ

Một run tập trung nhắm khoảng **90 phút ± 15 phút**.

- Người đi thẳng main route: khoảng 85–95 phút.
- Người quan sát, đọc notebook, theo red herring hoặc thử route mạnh: khoảng 95–110 phút.
- True route có thể dài hơn một chút vì cần thêm corroboration.
- Không dùng hard timer hiển thị.
- Thời gian objective vẫn đi qua D0 → D+1; gameplay dùng transition/fast travel hợp lý.

Đường cong cảm xúc:

**đời thường → hơi lệch → tò mò → chứng minh được một bất thường → nhận ra có vụ việc thật → nối nhiều institution → nghi sai → bị hệ thống phản ứng → hiểu command layer → lựa chọn preservation → consequence.**

Khoảng đầu game phải có đủ không gian để người chơi biết Bắc là ai trước khi biết vụ án là gì.

---

# 2. OPENING / NORMAL LIFE

## S01 — PHÒNG TRỌ MỚI
**Budget:** ~5 phút  
**Objective time:** D0,07:30–08:35 core65m; departure travel25m tới trường09:00
**Hub:** Dãy trọ

### Player-facing flow

Bắc kéo vali và vài thùng đồ vào dãy trọ. Bà Lan hướng dẫn tiền điện, khóa cổng, chỗ phơi đồ, giờ giấc và một vài chuyện nhỏ của khu trọ.

Phòng Bắc có một lỗi điện nhỏ hoặc quạt/ổ cắm hoạt động chập chờn. Nam xuất hiện vì nghe bà Lan gọi hoặc vì đang sửa đồ gần đó. Ông xử lý việc nhỏ rất bình thường, không hỏi điều gì kỳ lạ và không được quay như một nhân vật đáng ngờ.

Người chơi được tự do nhìn quanh một khoảng ngắn: bàn học, đồ điện tử, hành lang, khu sửa đồ của Nam ở khoảng cách hợp lý. Phần lớn đồ vật là noise đời thường.

Bắc nhận tin nhắn từ gia đình hoặc kiểm tra số dư. Không biến thành melodrama; chỉ đủ để thấy tiền đang là áp lực thực.

### Mục đích narrative

- Neo Bắc vào đời sống sinh viên trước plot.
- Giới thiệu Lan và Nam như hai người bình thường.
- Tạo cảm giác khu trọ là “nhà” trước khi nó trở nên bất an.
- Seed boss foreshadowing nhưng tuyệt đối không đánh dấu boss.

### Player biết trước đoạn

- Bắc mới lên Hà Nội.
- Bắc thiếu tiền.
- Không biết Tân Lộ, Phúc, Minh Trạch hay Hành Lang.

### Player có thể biết sau đoạn

- Nam khoảng 61 tuổi, sống/thường xuyên có mặt ở trọ.
- Nam từng làm việc gần kho vận/thiết bị hoặc dịch vụ y tế.
- Nam thực sự biết sửa đồ và giúp người.
- Lan tin Nam vì lịch sử đời thường lâu năm.

### Clue khả dụng

- **C27** — nghề cũ của Nam, guaranteed dưới dạng People note tự nhiên.
- **C29** — sự tử tế thật của Nam; không gắn nhãn clue.
- **C28** — optional inspect: một vật cũ hợp lý từ quan hệ nghề nghiệp Tân Lộ; không camera linger.

### Clue missable

- C28.
- Một vài noise item hoàn toàn vô nghĩa.

### NPC tham gia

- Bắc.
- Trần Thị Lan.
- Vũ Đức Nam.
- 1–2 hàng xóm nền nếu cần làm khu trọ sống.

### State có thể thay đổi

- Nam knowledge: Bắc = N0, hàng xóm mới.
- Notebook mở People: Lan, Nam.
- Không có suspicion state công khai.

### Mức căng thẳng

**1/10.** Hơi lạ vì nơi mới, nhưng an toàn.

### Hậu trường đang xảy ra đồng thời

- E19 đã xảy ra D−1.
- Hùng đã hạ gói xuống luồng thường.
- Khải vẫn đang audit Tân Lộ.
- Huyền vẫn giữ review.
- Vũ vẫn đang xử lý vụ Phúc.
- Không ai trong mạng lưới biết Bắc sẽ chạm sự cố.

---

## S02 — BUỔI HỌC ĐẦU / NHỊP SINH VIÊN
**Budget:** ~6 phút  
**Objective time:** D0, 09:00–11:15  
**Hub:** Trường và khu lân cận

### Player-facing flow

Bắc đi học, tìm phòng, ngồi lớp, gặp Linh và Minh. Scene có đủ chuyện nhỏ: đổi chỗ vì ổ cắm, ảnh bài giảng, deadline, chuyện ăn trưa, meme, sinh viên hỏi mượn sạc.

Linh được thiết lập là người phân biệt khá rõ “biết” với “đoán”. Minh dễ gần hơn, biết nhiều kênh việc làm part-time.

Bắc nhận một thông báo chi phí hoặc tự tính số tiền còn lại. Áp lực tiền dẫn tự nhiên sang câu chuyện việc làm, không phải plot prompt.

### Mục đích narrative

- Chứng minh trường là đời sống, không phải conspiracy.
- Giới thiệu Linh và Minh trước khi trust trở thành mechanic narrative.
- Đặt tiền là motive thật của Bắc.

### Player biết trước đoạn

- Nam/Lan là người ở khu trọ.
- Bắc đang thiếu tiền.

### Player có thể biết sau đoạn

- Linh đáng tin nhưng không thích suy diễn.
- Minh từng nhận/biết việc part-time qua Tân Lộ.
- Tân Lộ nhìn như một công ty logistics bình thường.

### Clue khả dụng

- **C01** — tin tuyển part-time Tân Lộ.
- **C07** — lịch sử Minh từng nhận ca Tân Lộ bình thường.
- Noise: thông báo trường, bài tập, job khác, quán ăn, sinh viên khác từng làm ship.

### Clue missable

- C07 nếu player không mở đoạn chat cũ/không hỏi thêm.
- Không clue nào ở đây được phép khóa main story.

### NPC tham gia

- Linh.
- Minh.
- Sinh viên nền.

### State có thể thay đổi

- Trust baseline: Linh cao; Minh khá cao.
- Tân Lộ được thêm như một employer bình thường.
- Bắc vẫn N0 với organization.

### Mức căng thẳng

**1/10.**

### Hậu trường đang xảy ra đồng thời

- Khải tiếp tục rà Tân Lộ.
- Tuấn chỉ biết có audit và nhóm đơn ưu tiên.
- Hùng vẫn tin việc hạ luồng có thể đi qua như một job bình thường.

---

# 3. INCITING INCIDENT

## S03 — MỘT CA NGẮN
**Budget:** ~4 phút  
**Objective time:** D0,11:15–11:49 core34m; travel35m tớiTân Lộ12:24/check-in6m tới12:30

### Player-facing flow

Trong lúc ăn trưa/đứng ở khu sinh viên, Minh gửi cho Bắc một ca ngắn của Tân Lộ. Việc trả cao hơn một ca lặt vặt thông thường một chút nhưng không tới mức đáng ngờ, lý do là cần giao đúng khung giờ và có proof-of-handover.

Bắc có thể từ chối ban đầu, xem ví/số dư, rồi nhận vì ca không đụng lịch học và đủ tiền cho vài chi phí trước mắt.

Không ai gọi riêng Bắc. Không có “người bí ẩn chọn cậu”. Bắc vào pool như một cộng tác viên mới.

### Mục đích narrative

Đây là **inciting incident chính thức**: đời thường, tiền bạc, hợp lý và không lộ conspiracy.

Về sau player hiểu rằng ca này tồn tại vì chuỗi:
Phúc → Huyền → Khoa → cleanup → audit → Hùng tự cứu → reclassification.

### Player biết trước đoạn

- Tân Lộ tuyển part-time thật.
- Minh có lịch sử dùng kênh này.
- Bắc cần tiền.

### Player có thể biết sau đoạn

- Bắc được phân một job thuộc nhóm khách hàng y tế/ưu tiên nhưng hiển thị như job thường.
- Job được tạo/đẩy vào pool sát D−1/D0.

### Clue khả dụng

- **C01** guaranteed.
- **C02** bắt đầu xuất hiện trong assignment UI dưới dạng field thô.

### Clue missable

- Chi tiết nhỏ trong C02 có thể bị bỏ qua lúc nhận job nhưng assignment vẫn được notebook/log giữ.
- Không có clue “tội phạm”.

### NPC tham gia

- Bắc.
- Minh.
- Nhân viên hỗ trợ/dispatch nền qua app nếu cần.

### State có thể thay đổi

- JOB_ACCEPTED = true.
- Bắc vẫn N0 trong mắt Nam/Khải.
- Không ai ở mạng lưới chủ động chọn Bắc.

### Mức căng thẳng

**1/10.**

### Hậu trường đang xảy ra đồng thời

- E21 xảy ra.
- Job E19 đã nằm trong pool thường do quyết định của Hùng.

---

# 4. FIRST ANOMALY

## S04 — GIAO XONG NHƯNG HƠI LỆCH
**Budget:** ~7 phút  
**Objective time:** D0, 12:30–14:10  
**Hub:** Tân Lộ → điểm nhận y tế/hành chính liên quan Minh Trạch

### Player-facing flow

Bắc tới Tân Lộ nhận gói. Không gian công ty phải trông thật: nhân viên bận, nhiều job bình thường, tài xế, hàng thương mại, hồ sơ doanh nghiệp.

Tuấn xuất hiện ngắn ở vai trò điều phối, không phải người trực tiếp “giao bí mật”. Cậu nhận một gói/túi hồ sơ kín, chỉ có routing bên ngoài.

Trong lúc nhận hoặc bàn giao, người chơi có thể thấy:

- assignment có trường “y tế/ưu tiên” dù nằm trong pool cộng tác viên;
- lớp routing ngoài có dấu đã đổi/dán lại;
- proof-of-handover dùng một account/client family liên quan Minh Trạch.

Ở đầu nhận, một thao tác scan hoặc xác nhận có một lỗi nhỏ: mã job hợp lệ nhưng nhóm phân loại không giống cách điểm nhận thường thấy ở cộng tác viên. Nhân viên xử lý được bằng quy trình bình thường và không coi đó là scandal.

Bắc giao xong. Không mở gói. Không có tài liệu “bằng chứng tội phạm” rơi ra.

### Mục đích narrative

- Cho player chạm mystery mà vẫn tin mình chỉ đang làm việc.
- Đặt ba delayed-value seed đầu tiên trong một scene hợp lý.
- Chứng minh Tân Lộ có nhiều hoạt động bình thường để RH6 không biến cả công ty thành ổ tội phạm.

### Player biết trước đoạn

- Đây là ca giao hồ sơ/hàng hành chính bình thường.
- Tân Lộ có khách y tế hợp pháp.

### Player có thể biết sau đoạn

- Ca của Bắc có vài chi tiết vận hành không khớp.
- Điểm nhận nằm trong chuỗi dịch vụ liên quan Minh Trạch.
- Chưa có lý do kết luận phạm pháp.

### Clue khả dụng

- **C02** guaranteed.
- **C03** inspect proof-of-handover.
- **C04** inspect routing layer.
- **C06** environmental noise: nhiều job y tế khác hoàn toàn bình thường.

### Clue missable

- C03.
- C04.
- Các clue miss vì player không inspect lúc còn cầm/nhìn chứng từ, không phải vì pixel hunt.

### NPC tham gia

- Bắc.
- Tuấn hoặc điều phối viên dưới Tuấn.
- Nhân viên Tân Lộ vô tội.
- Nhân viên đầu nhận vô tội.

### State có thể thay đổi

- E22_COMPLETE = true.
- P01 ghi nhận player có lưu C03/C04 hay không.
- Sau audit hậu trường, Bắc sẽ trở thành N1; nhưng tại khoảnh khắc player chưa biết.

### Mức căng thẳng

**2/10.** “Có gì đó hơi lệch”, chưa phải nguy hiểm.

### Hậu trường đang xảy ra đồng thời

- E22 hoàn tất.
- Sau đó E23 bắt đầu: Khải phát hiện luồng nhạy cảm đi qua pool thường.

---

# 5. FIRST BREATHER / NORMAL LIFE RETURNS

## S05 — ĂN TỐI, ĐỢI TIỀN, VỀ TRỌ
**Budget:** ~5 phút  
**Objective time:** D0,14:30–18:07; ordinary afternoon180m→17:30, return35m→18:05, room beat2m→audit18:07

### Player-facing flow

Game cố tình rời mystery.

Bắc có thể ăn một bữa rẻ, trả lời tin nhắn Linh, xem bài học, mua đồ lặt vặt hoặc về trọ. Một đoạn hài nhẹ có thể đến từ việc Bắc tính từng khoản chi hoặc bị Lan nhắc đồ để sai chỗ.

Khoản thanh toán ca làm vẫn ở trạng thái đang xử lý; điều này chưa phải “clue đỏ”.

Nam có thể xuất hiện lần hai trong một việc rất nhỏ: trả Bắc món đồ đã sửa, nhắc một chi tiết sinh hoạt hoặc giúp Lan. Ông không hỏi Tân Lộ và không lộ mình đã biết gì.

### Mục đích narrative

- Cắt nhịp “clue → clue”.
- Cho người chơi cảm giác game vẫn là đời sống sinh viên.
- Tạo replay payoff: ở hậu trường, Nam đã bắt đầu biết worker E22 là Bắc.

### Player biết trước đoạn

- Job hơi lạ nhưng đã hoàn tất.

### Player có thể biết sau đoạn

- Không có fact vụ án mới bắt buộc.
- Nam vẫn hoàn toàn có thể được đọc như người hàng xóm tử tế.

### Clue khả dụng

- C29 được củng cố ở mức characterization.
- Noise đời thường.

### Clue missable

- Không critical clue.

### NPC tham gia

- Lan.
- Nam.
- Linh qua chat/call.
- NPC quán ăn/hàng xóm.

### State có thể thay đổi

- E23 → E24 xảy ra ngoài màn hình.
- Nam knowledge: N0 → N1 chỉ sau actual E24 report nhận diện Bắc từ E23 audit được gửi tới ông.
- Player không được thông báo state này.

### Mức căng thẳng

**1–2/10.**

### Hậu trường đang xảy ra đồng thời

- Khải chất vấn Hùng.
- Worker E22 được tra.
- Nam nhận ra worker là sinh viên mới ở trọ.
- E25: Nam chọn quan sát, không xử lý mạnh.

---

# 6. SECOND ANOMALY

## S06 — JOB BỊ AUDIT
**Budget:** ~4 phút  
**Objective time:** D0, khoảng 18:00–20:00

### Player-facing flow

Tân Lộ gửi thông báo hoặc Tuấn gọi để xác nhận lại một số bước: thời gian nhận gói, người bàn giao, proof-of-handover, lý do một field không khớp. Khoản thanh toán có thể tạm chờ xác minh.

Tuấn phòng thủ hơn mức Bắc mong đợi nhưng vẫn nói theo kiểu quản lý vận hành: đúng quy trình, đừng tự liên hệ khách hàng thêm, chờ công ty xử lý.

Điều này tạo một câu hỏi rất đời thường:

**Nếu chỉ là một ca giao hồ sơ bình thường, tại sao cả công ty lại rà kỹ như vậy?**

### Mục đích narrative

- Tăng nghi ngờ mà vẫn giữ lời giải thích bình thường: audit nội bộ / sai quy trình / lỗi classification.
- Bắt đầu red herring Tuấn.

### Player biết trước đoạn

- Job có vài chi tiết lệch.

### Player có thể biết sau đoạn

- Tân Lộ đang xem chính job này là một incident.
- Tuấn có vẻ đang che điều gì đó, nhưng chưa biết là gì.

### Clue khả dụng

- **C05** — Tuấn defensive/procedural.
- C02 được re-read trong context mới.

### Clue missable

- C05 chỉ xuất hiện nếu Bắc hỏi đủ để Tuấn phản hồi; nhưng main story vẫn tiến qua trạng thái audit.

### NPC tham gia

- Tuấn.
- Minh có thể nhắn hỏi “xong việc chưa”.

### State có thể thay đổi

- TUAN_SUSPICION_SEEDED = true.
- Bắc vẫn chỉ N1 nếu không chủ động đào sâu.

### Mức căng thẳng

**3/10.**

### Hậu trường đang xảy ra đồng thời

- Khải/Hùng đang đánh giá breach.
- Nam vẫn ưu tiên “đừng dạy Bắc rằng thứ cậu thấy quan trọng”.

---

# 7. POINT OF CURIOSITY

## S07 — BẮC CHỈ MUỐN BIẾT MÌNH ĐANG BỊ DÍNH VÀO CÁI GÌ
**Budget:** ~5 phút  
**Objective time:** D0, 20:00–23:00

### Player-facing flow

Động cơ kiểm tra đầu tiên không phải anh hùng hay phá án.

Bắc muốn:

1. biết vì sao tiền bị giữ;
2. biết mình có làm sai gì không;
3. tránh bị công ty đổ trách nhiệm;
4. hiểu tại sao một job bình thường lại bị rà.

Player có thể so assignment với lịch sử ca bình thường Minh từng nhận. C07 cho thấy Minh thật sự chỉ là sinh viên từng kiếm việc qua Tân Lộ.

Bắc có thể hỏi Minh ít hoặc nhiều.

- Hỏi chung: không tạo leak đáng kể.
- Gửi screenshot/giả thuyết chi tiết và nhờ Minh hỏi công ty: có thể kích E26/C35.

Sau đó game cho một khoảng yên: Bắc ngồi trong phòng, nghe hành lang, xem bài học còn dang dở, có thể nhìn lại notebook. Đây là điểm save/day transition tự nhiên.

### Mục đích narrative

- Biến curiosity thành hành động có motive.
- Cho betrayal route tồn tại nhưng không bắt buộc.
- Không để Bắc “điều tra vì game bảo điều tra”.

### Player biết trước đoạn

- Job đang bị audit.
- Tuấn đáng ngờ ở mức nghề nghiệp.

### Player có thể biết sau đoạn

- Ca của Minh trước đây thực sự bình thường.
- Job của Bắc khác ở classification/timing, không chỉ vì cậu là worker mới.
- Player bắt đầu có một hypothesis, chưa có proof.

### Clue khả dụng

- **C07**.
- **C35/C36** chỉ được seed nếu player overshare.
- C02/C03 có thể được inspect trong live worker history còn access, kể cả chưa lưu ở S04; C03 cho same raw fields/original time với observed_at mới. C04 đọc từ direct observation đã giữ hoặc authored label-visible photo; default seal-only photo không có nhãn.

### Clue missable

- C35 nếu không kích betrayal; đây là đúng thiết kế, không phải nội dung bắt buộc.
- C03 chưa inspect ở S04 vẫn quan sát hợp lệ nếu receipt history còn. C04 trực tiếp mất sau handover, chỉ recover từ retained ảnh thật có nhãn rõ; không tự tạo fact từ seal-only photo.

### NPC tham gia

- Minh.
- Linh có thể có một đoạn chat hoàn toàn đời thường để giữ nhịp.

### State có thể thay đổi

- N1 → N2 chỉ nếu exact hành vi probing được witness/disclose rồi report tới Khải, có sender/payload/recipient/received_at. Private inspect, giữ copy và inference không tự tăng BARC.
- MINH_LEAK_POSSIBLE = true nếu overshare.
- Nếu player bỏ qua hoàn toàn: mở cửa **Neutral Ending — Một Ca Làm Thêm** sau một nhịp đời thường ngắn, phù hợp baseline Stage 3.

### Mức căng thẳng

**3/10.**

### Hậu trường đang xảy ra đồng thời

- E27: Huyền vẫn giữ review mở.
- E28: Vũ tiếp tục làm rõ timeline Phúc.
- E29/E30 chỉ xảy ra nếu Bắc để lại dấu tò mò.

---

# 8. FIRST REAL CONNECTION

## S08 — JOB KHÔNG “TỰ NHIÊN” LỌT VÀO POOL
**Budget:** ~6 phút  
**Objective time:** D+1,09:00–09:35 core35m (checkpoint09:25 notice); optional copy10m tới09:45, explicit police appointment10:00
**Hub:** Tân Lộ / kênh xử lý khiếu nại worker

### Player-facing flow

Sáng hôm sau Bắc đi trọ→Tân Lộ08:30–09:00 (30m), S08 core09:00–09:35 (35m) để xử lý payment/incident. Required notice09:25 nêu worker access/Đức willingness11:00 và finance12:30. Từ09:30 Đức thật sự offer copy giới hạn và contact; action nhận copy09:35–09:45 cost10m cho actual local receipt09:45, hoặc giữ đúng contact/copy/deadline để Vũ collect ở S09. Một bounded finance contact/group lead tới Yến được offer, không cho Bắc biết dòng tiền/Nam trước source. Không đợi S12/S13 mới đưa người chơi tới C18.

Qua một interaction hợp lệ với lịch sử assignment hoặc người vận hành, Bắc có thể thấy:

- job từng ở một luồng hạn chế;
- classification được đổi D−1;
- quyền thay classification nằm cao hơn phần xử lý thông thường của Tuấn.

Đây là lần đầu player có thể **chứng minh** hai sự việc tưởng rời nhau thực ra cùng một nguyên nhân:

**dấu routing lạ ở gói + audit sau giao hàng** không phải hai lỗi ngẫu nhiên; job đã được cố ý hạ xuống luồng thường.

Player vẫn chưa biết tại sao.

### Mục đích narrative

Đây là **FIRST REAL CONNECTION** chính thức.

Mystery chuyển từ “cảm giác lạ” sang “có một hành động có chủ ý trước khi Bắc xuất hiện”.

### Player biết trước đoạn

- Job có anomaly.
- Tân Lộ đang audit.
- Tuấn có vẻ phòng thủ.

### Player có thể biết sau đoạn

- **R1**: E22 vốn không phải job thường.
- Reclassification xảy ra trước khi Bắc nhận job.
- Tuấn có thể không phải người có authority tạo ra tình huống.

### Clue khả dụng

- **C17** — reclassification log / source tương đương.
- **C20** — permission chain.
- C21 optional procedural consistency.
- C22 có thể chỉ được seed, chưa cần fully verify ngay.

### Clue missable

- C21.
- Nếu C17 bị lỡ vì access sớm bị siết do Minh leak, main story có route phục hồi qua Đức/Vũ nhưng tốn timing.

### NPC tham gia

- Tuấn.
- Nhân viên vận hành.
- Đức source/contact giới hạn sáng; C18 direct receipt optional10m. Yến là bounded finance lead để police verify, không exposition toàn mạng.

### State có thể thay đổi

- R1_CONFIRMED = true nếu C17.
- TUAN_FALSE_THEORY có thể tăng hoặc bắt đầu sụp tùy player đọc C20.
- BARC chỉ actual received reports; source copy/request không tự đổi private understanding hoặc awareness.

### Mức căng thẳng

**4/10.**

### Hậu trường đang xảy ra đồng thời

- E31: ba hệ thống tiếp tục vận động.
- Khải bắt đầu siết access Tân Lộ.
- Đức biết cửa sổ của mình sắp đóng.

---

# 9. POLICE ENTRY

## S09 — LẦN ĐẦU BẮC CÓ THỨ ĐỦ CỤ THỂ ĐỂ BÁO
**Budget:** ~5 phút  
**Objective time:** D+1, khoảng 10:00

### Player-facing flow

Sau C17, Bắc không chỉ có “linh cảm”. Cậu có:

- một assignment cụ thể;
- proof-of-handover;
- một reclassification có chủ ý trước khi cậu nhận việc;
- một đầu nhận thuộc chuỗi dịch vụ y tế.

Main route dùng phone appointment10:00–10:15 tại Tân Lộ (15m), sau explicit wait tới10:00; không thêm morning police trip. Actual payload/group records received10:15. Nếu payload đã nêu Đức có copy/contact/deadline, Vũ contacts10:25 và receives10:35 tự động theo sourced request, không thêm xin lại. Chỉ một source address/context chưa shared mới có disclosure5m ở10:15–10:20; optional bounded Yến lead5m (hoặc second new lead tới10:25) cho collector10:40/actual receipt10:50. Queue chưa PRESERVED. Actual late source disclosures dùng q-relative receipt formulas OT §0.1, không fixed baseline10:35/10:50 nếu query chưa có lúc đó; police requests/receipts đã started vẫn độc lập với personal delay. Vũ acknowledge local hospital11:30 và finance12:30 trước departure; khi actual group bridge đủ anh tự request C11/C12 originals, receipt11:10, không chờ Bắc tới bệnh viện.

Thông tin được chuyển tới Vũ vì tên/đầu nhận Minh Trạch chạm một vụ việc anh đã xác minh từ trước. Vũ không kể ngay vụ Phúc. Anh chỉ hỏi:

- cái gì Bắc trực tiếp thấy;
- cái gì có record;
- cái gì là suy đoán.

Nếu source hợp lệ, Vũ nhận/copy phần cần thiết và dặn Bắc không tự biến mình thành người thực thi.

### Mục đích narrative

- Đưa cảnh sát vào tự nhiên.
- Chứng minh cảnh sát không bị viết ngu.
- Đổi fantasy từ “mình phải tự phá án” sang “mình phải tìm ra thứ gì đáng đưa cho người có thẩm quyền”.

### Player biết trước đoạn

- Tân Lộ có hành vi reclassification có chủ ý.
- Chưa biết đây là tội phạm gì.

### Player có thể biết sau đoạn

- Vũ đã có một vụ việc thật liên quan một người muốn rút khỏi một thỏa thuận y tế.
- Vụ đó có trước Bắc.
- Vũ chưa có link logistics.

### Clue khả dụng

- **C10** — police chronology, có thể chỉ mở phần đủ cần thiết.
- **C11A** — timestamp Phúc trình báo trước E22.
- C42 được foreshadow: evidence được Vũ tiếp nhận khác với note cá nhân của Bắc.

### Clue missable

- C08 direct withdrawal record có thể chưa xuất hiện nếu route Phúc chưa mở.
- Không được lộ tên/toàn bộ lời khai Phúc chỉ vì police exposition.

### NPC tham gia

- Đại úy Nguyễn Minh Vũ.
- Phúc chỉ có thể xuất hiện sau nếu có lý do và consent; không bắt buộc trong scene đầu.

### State có thể thay đổi

- POLICE_CONTACT = true.
- Actual source receipts: C17 payload10:15; C18 direct-copy handover10:15 hoặc police export10:35; finance10:50 nếu bounded lead actual shared. Verification riêng, không grant custody từ source-request checkbox.
- Vũ trust tăng theo source quality, không theo charm.

### Mức căng thẳng

**4/10**, nhưng cảm giác an toàn tăng nhẹ vì có người chuyên nghiệp vào cuộc.

### Hậu trường đang xảy ra đồng thời

- E34 mở cửa.
- Vũ tiếp tục independent A case và targeted group query/parallel source collection từ payload đã received; không chậm vì Bắc miss một action xin lại.
- Organization chưa biết chính xác Bắc đã nói gì với police trừ khi có observable consequence.

---

# 10. HOSPITAL LAYER / SECOND BOX

## S10 — MINH TRẠCH KHÔNG CHỈ CÓ MỘT LỖI
**Budget:** ~7 phút  
**Objective time:** D+1, arrive10:50/10:55; core20m và optional Thảo10m finish11:20/11:25 before11:30
**Hub:** Minh Trạch / tuyến xác minh hợp lệ

### Player-facing flow

Travel Tân Lộ→Minh Trạch30m: arrive10:50 hoặc10:55 sau tối đa hai genuinely new lead disclosures. S10 core20m tới11:10/11:15, optional Thảo10m tới11:20/11:25. Vũ đã request group review10:15 và nhận raw C11/C12 originals11:10; Bắc không hack/xông vào khu hạn chế. Required entrance notice11:30 trước lựa chọn core/Thảo; C12 knowledge+assistance được received thì không mất bởi scope lock, nếu fact còn thiếu thì Thảo alternative còn10m thật.

Huyền xuất hiện đầu tiên như một người khô và giữ quy trình. Nếu Bắc tự hỏi lung tung, bà không chia dữ liệu. Điều này có thể làm bà trông đáng ngờ.

Khi Vũ hoặc một lý do nghiệp vụ hợp lệ đặt đúng câu hỏi, Huyền xác nhận:

- review đã mở từ D−12;
- không chỉ một hồ sơ có anomaly;
- scope từng rộng hơn mức hiện tại.

Nếu route tốt, player có thể thấy version/scope history hoặc gặp Thảo trong phạm vi hợp lý. Thảo không kể conspiracy; bà chỉ có thể xác nhận rằng một số hồ sơ không phản ánh đầy đủ hoàn cảnh bên ngoài.

### Mục đích narrative

- Biến Minh Trạch từ “địa chỉ trên receipt” thành một nguồn độc lập.
- Tạo RH3 Huyền nhưng cho cách giải oan bằng hành vi/timestamp.
- Giữ bệnh viện là institution hợp pháp với cell nhỏ.

### Player biết trước đoạn

- Job E22 chạm chuỗi Minh Trạch.
- Police có một vụ y tế trước Bắc.

### Player có thể biết sau đoạn

- **R3** ở mức core: có pattern hospital thật.
- Huyền là người mở review, không phải người tạo anomaly.
- Có can thiệp quản trị sau khi review mở.
- Review predates E22.

### Clue khả dụng

- **C11** guaranteed trên route hospital.
- **C12** optional/strong.
- **C13** behavioral red herring.
- **C14/C15** nếu Thảo route mở.
- **C16** timing Khoa intervention.

### Clue missable

- C12.
- C15.
- Nếu player đến muộn hoặc leak sớm, access/scope có thể đã bị siết.

### NPC tham gia

- Huyền.
- Thảo.
- Khoa có thể xuất hiện bề mặt nhưng không exposition.
- Vũ.

### State có thể thay đổi

- B_HOSPITAL_PATTERN = true nếu C11 + corroborator.
- HUYEN_FALSE_THEORY có thể mở rồi được sửa.
- Khoa bắt đầu là manager đáng ngờ, không phải boss.

### Mức căng thẳng

**5/10.**

### Hậu trường đang xảy ra đồng thời

- E33.
- Khoa tiếp tục tự bảo vệ.
- Thảo bị ép giữa rationalization và lương tâm.
- Nam vẫn nhận hospital risk qua Khải bằng báo cáo không hoàn hảo.

---

# 11. MIDPOINT

## S11 — “CHUYỆN NÀY CÓ TRƯỚC MÌNH, VÀ LỚN HƠN MỘT JOB”
**Budget:** ~6 phút  
**Objective time:** D+1, 11:30–12:00 (30m compare tại hospital-area quiet point/phone); explicit wait tới11:30 nếu sớm, rồi travel Tân Lộ30m tới12:30

### Player-facing flow

Vũ đối chiếu những gì Bắc mang tới với timeline đã có.

Player lần đầu được đặt cạnh ba timestamp quan trọng:

1. Phúc muốn rút / trình báo trước D0.
2. Huyền mở review D−12.
3. Job của Bắc bị reclassify D−1 rồi mới tới tay cậu.

Nếu C03 còn tồn tại, account/client family trên receipt giờ đổi nghĩa khi so với phạm vi review.

Nếu route Phúc đủ mạnh, C08 cho thấy withdrawal có trước pressure. Phúc không biến thành người kể toàn conspiracy; anh chỉ củng cố source A.

Khoảnh khắc midpoint không phải một cutscene “đây là đường dây buôn nội tạng” từ miệng NPC. Nó là lúc player có thể hiểu:

**Bắc không gây ra vụ này. Cậu đã bước vào giữa một cleanup có sẵn.**

### Mục đích narrative

Đây là **MIDPOINT** chính thức.

Mental model đổi từ “job bẩn/công ty gian lận” sang “nhiều hệ thống đang phản ứng với cùng một thứ lớn hơn”.

### Player biết trước đoạn

- Job bị hạ luồng.
- Hospital có pattern.
- Police có vụ Phúc trước Bắc.

### Player có thể biết sau đoạn

- **R2**: withdrawal → pressure là thật.
- DV4/DV5 payoff: crisis predates Bắc và hospital pressure precedes logistics mistake.
- Có khả năng A+B+C đang thuộc cùng structure, nhưng chưa đủ proof.

### Clue khả dụng

- **C08**, **C09**, **C10**, **C11A**.
- C03 payoff từ receipt đã inspect sớm hoặc intentional later history inspect khi còn access; không early-save gate.
- C11 timestamp payoff.

### Clue missable

- C08 nếu không mở source direct.
- C03 chỉ mất khả năng quan sát khi live history thật sự hạn chế và chưa có retained observation; miss early click không làm mất receipt.
- Story vẫn tiến qua police chronology và hospital/logistics sources.

### NPC tham gia

- Vũ.
- Phúc optional/controlled.
- Bắc.

### State có thể thay đổi

- A_PLAYER_SEEN/A_PLAYER_UNDERSTOOD tăng theo nội dung được chia và explicit correct chronology/content inference. CASE.A=2 đã từ E28; encounter không cấp/reset police A.
- Player hypothesis NETWORK_POSSIBLE mở, nhưng notebook không tự ghi conclusion.
- Bắc tiến gần N3 nếu tiếp tục nối source.

### Mức căng thẳng

**6/10.**

### Hậu trường đang xảy ra đồng thời

- E32–E35 đang đồng thời mở/đóng.
- Đức, Huyền, Thảo, Yến không chờ Bắc; mỗi người có agenda riêng.

---

# 12. FALSE THEORY / WRONG DIRECTION

## S12 — TUẤN, RỒI HÙNG: HAI “BOSS” QUÁ HỢP LÝ
**Budget:** ~5 phút  
**Objective time:** D+1, 12:30–13:00 (30m retained verification); extra visits/waits cộng fixed cost đã show

### Player-facing flow

Ở thời điểm này player có rất nhiều lý do nghi Tuấn:

- quản lý điều phối;
- job đi qua bộ phận anh;
- biết đơn y tế ưu tiên;
- phòng thủ;
- Minh có thể liên hệ phía anh.

Nếu player chỉ nhìn chức vụ và thái độ, Tuấn là đáp án rất hấp dẫn.

Nhưng C20 cho thấy classification bị thay trước tầng xử lý của Tuấn. C21 cho thấy anh procedural cả ở việc không liên quan. C22 đưa quyền override lên Hùng.

Ngay khi Tuấn được “giải oan về core crime”, Hùng trở thành false apex thứ hai:

- founder Tân Lộ;
- biết hoạt động phi pháp;
- chính ông hạ luồng;
- có động cơ che audit.

Player có thể dừng ở Hùng và vẫn đúng một phần. Đây là điều làm false theory nguy hiểm: Hùng thật sự có tội.

### Mục đích narrative

- Cho player nghi sai hợp lý mà không game-cheat.
- Dạy distinction: access ≠ knowledge; culpable manager ≠ ultimate command.
- Cost chỉ cho observable extra visit/wait sau notice: Tuấn appointment15m hoặc chờ Hùng30m; private fixation/reading/retry0.

### Player biết trước đoạn

- Tân Lộ có intentional reclassification.
- Hospital có pattern.
- Có một vụ Phúc thật.

### Player có thể biết sau đoạn

- **R5** theo scope nguồn Vũ đã verify: Tuấn không phải reclassifier; không có cơ sở xếp anh vào core trong case này. Trách nhiệm làm ngơ ngoại lệ vẫn giữ; không từ permission suy anh chưa từng biết bí mật.
- **R4**: Tân Lộ leadership ở mức Hùng có chủ ý tham gia.
- Hùng vẫn chưa giải thích hospital/source branch.

### Clue khả dụng

- C20, C21, C22.
- C18/C19 bản đã received buổi sáng và limited callback/provenance; không fresh C18 pickup sau willingness11:00. C22 original packet received police13:00, match/auth riêng.

### Clue missable

- C21.
- Nếu C20/C22 miss, player có thể đuổi Tuấn quá lâu và mất source window.

### NPC tham gia

- Tuấn.
- Đức chỉ retained-copy/earlier testimony hoặc callback đúng scope; late conversation không invent morning receipt.
- Hùng có thể xuất hiện gián tiếp hoặc rất ngắn; không monologue.

### State có thể thay đổi

- TUAN_NOT_RECLASSIFIER từ actual C20; TUAN_CORE_SCOPE_VERIFIED chỉ khi Vũ so assignment/permissions, câu hỏi chưa được giải đáp và lời Tuấn giới hạn, nghĩa không có cơ sở xếp anh vào core trong hồ sơ này. Permission chain hoặc private innocence answer không cấp blanket exoneration.
- C_LOGISTICS_LEADERSHIP = true nếu C17 + corroborator + C22.
- Confirm quay lại hẹn Tuấn cùng việc+15m (5m move+10m appointment), hoặc chờ Hùng+30m, sau visible finish/deadline notice. Reread/incorrect hypothesis0; police copies và processing đã có không retime. Missing-source saving action là gửi đúng payload cho Vũ trước wait.

### Mức căng thẳng

**6/10.**

### Hậu trường đang xảy ra đồng thời

- Đức willingness11:00/Yến access12:30 đã đóng ở late S12, private export/originals vẫn có; retained receipts verify được.
- Police actual morning collections chạy độc lập với private theories Bắc.
- Khải nhận nhiều báo cáo hơn về incident.
- Nếu Minh đã leak, cleanup chạy nhanh hơn.

---

# 13. ESCALATION / THREE-BOX CONNECTION

## S13 — CÙNG MỘT NGƯỜI QUẢN RỦI RO
**Budget:** ~7 phút  
**Objective time:** D+1, 13:35–14:00 (25m compare/callback), sau30m Tân Lộ→hospital area +5m local micro-set

### Player-facing flow

Player không cần tự chạy gặp tất cả nguồn.

Một strong route chỉ cần Bắc trực tiếp mở đủ bridge; Vũ có thể xác minh phần khác.

Hai nhánh có thể song song:

**Logistics route**
- Retained C18 actual local receipt09:45/police10:35 và limited earlier testimony; fields check10:45/match C22 at13:55. Không late pickup khi willingness11:00 đã đóng.
- Retained C19 actual10:50 receipt nếu new finance lead thật shared; verification/match13:55 không invent pre12:30 acquisition.
- C22/C25 actual police packet13:00; account lock không xóa private/police copies.

**Hospital route**
- Huyền + C12 hoặc Thảo C15 củng cố B.
- C24 cần actual Khoa→Khải incident request/response, endpoint, current role/scope và crisis Phúc context; timing intervention chỉ lead.

C25 từ original logistics incident/escalation request và response cùng crisis, có scope/role Khải được giao. Same transaction/account ABC hay call timestamp đơn lẻ không chứng minh common current risk authority.

Player có thể tự nối C24 + C25:

**Khải đang đứng ở giao điểm của hai scandal tưởng độc lập.**

Điều này không tự chứng minh organ network; A+B+C vẫn phải tồn tại độc lập.

### Mục đích narrative

- Hoàn thành **R7**: ba hộp bắt đầu trở thành một network.
- Nâng conspiracy từ manager riêng lẻ lên architecture.
- Đưa Khải vào truyện đúng vai: risk manager, không phải action villain.

### Player biết trước đoạn

- A, B, C có thể đang liên quan.
- Hùng và Khoa đều có lỗi riêng.

### Player có thể biết sau đoạn

- C24/C25 hội tụ vào Khải.
- **R8**: Hùng/Khoa/Hạnh có tội nhưng không ai giải thích toàn bộ.
- A+B+C có thể được hiểu như cùng network.

### Clue khả dụng

- **C18/C19**.
- **C24/C25/C26**.
- **C26A** optional behavioral clue Khải.

### Clue missable

- C18/C19 missing morning actual receipts vẫn thiếu; S13 chỉ retained verification.
- Callback riêng không backdate một request thành receipt.
- Một nửa C24/C25 có thể miss; main story vẫn tiến nhưng command layer yếu.

### NPC tham gia

- Đức.
- Yến optional/mostly police verified.
- Huyền/Thảo.
- Vũ.
- Khải có thể chỉ xuất hiện qua contact/meeting ngắn trước khi player hiểu vai trò.

### State có thể thay đổi

- X_PLAYER_CONNECTED chỉ khi player có đủ observed C24/C25 role/scope/crisis context và inference đúng; sai/thiếu giữ hypothesis.
- N3_UNDERSTANDING chỉ khi enough observed A/B/C facts + explicit correct risk-structure inference; CASE/X police đã verify không tự cấp player certainty.
- KHẢI_LAYER chỉ khi actual endpoint identity/role đã quan sát và nối đúng.
- X_VERIFIED: Vũ verify complete raw sources/context đã intake dù teen inference sai; không chỉ same account/transaction.
- E37/BARC chỉ từ received reports đủ về observable cross-cell behavior, không private flags.

### Mức căng thẳng

**7/10.**

### Hậu trường đang xảy ra đồng thời

- Nếu actual received reports đủ, Khải cross-report xác nhận cùng Bắc probing nhiều cell; thiếu reports giữ awareness trước đó, không đọc notebook.
- Nam chuyển từ “thằng sinh viên tò mò” sang “nguy cơ nghiêm trọng” nếu dấu đủ.

---

# 14. DANGER ESCALATION

## S14 — HỆ THỐNG BẮT ĐẦU KHÉP CỬA
**Budget:** ~5 phút  
**Objective time:** D+1, 14:00–14:20 (20m status/notice); extra committed actions cộng đúng cost

### Player-facing flow

Danger không bắt đầu bằng một đội người đuổi Bắc.

Nó bắt đầu bằng bureaucracy đổi trạng thái:

- tài khoản worker bị khóa;
- Đức mất quyền truy cập;
- một source không còn trả lời;
- review bị thu hẹp;
- Tân Lộ yêu cầu Bắc không tự liên hệ khách hàng;
- một cuộc hẹn bị hủy;
- hồ sơ trước đó xem được giờ cần quyền khác.

Nếu Minh leak đã xảy ra, player có thể nhận ra timing của việc các cửa đóng bám sát lần Minh “hỏi hộ”. C35–C37 biến betrayal thành hậu quả thật.

Minh không lộ thành phản diện. Khi bị hỏi, cậu giảm nhẹ việc đã nói và rõ ràng chính cậu cũng không hiểu chuyện đã lớn tới đâu.

### Mục đích narrative

- Chuyển threat từ abstract sang personal.
- Cho thấy organization competent bằng cách cắt access, không bằng bạo lực ngu.
- Payoff betrayal nếu player tạo điều kiện cho nó.

### Player biết trước đoạn

- Route mạnh có thể đã hiểu network/current risk role Khải; partial giữ facts/hypothesis chưa đủ.
- Organization chỉ có mức awareness từ actual received reports; closure không tự chứng minh họ biết private inference.

### Player có thể biết sau đoạn

- **R6** nếu route leak: Minh phản bội lòng tin nhưng không phải member.
- Cleanup là process đang diễn ra, không phải event cuối game.
- Evidence tồn tại ≠ player còn quyền chạm nó.

### Clue khả dụng

- C35, C36, C37.
- C43 access closure.

### Clue missable

- C35 message/trail.
- Nếu player không trigger betrayal, đoạn vẫn có access closures do cleanup objective.

### NPC tham gia

- Minh.
- Đức/Tuấn/Huyền tùy source đóng.
- Vũ qua điện thoại.

### State có thể thay đổi

- MINH_BETRAYAL_REVEALED.
- CLEANUP_ACCELERATED nếu leak sớm.
- Organization knowledge N3 nếu cross-report đủ.

### Mức căng thẳng

**8/10.**

### Hậu trường đang xảy ra đồng thời

- E37 chỉ nếu reports đủ, ghi payload/recipient/received_at. S14 reinforcement không thay pre-loss notices S08/S09/S10; required global notice14:00 nêu17:00, late broker availability-only và actual saving intake. Nếu acceleration, fresh warningW trước global=max(16:30,W+145m)<17:00; canonicalW14:00→16:30.
- Nam chỉ xem phần actual Khải forward tới ông; baseline closures không tự sinh report Bắc/N3.
- Khải vẫn có thể co access theo baseline crisis, giữ prior BARC nếu không nhận dấu mới.
- Nam vẫn ưu tiên giảm dấu hơn là tạo một vụ việc công khai mới.

---

# 15. POINT OF NO RETURN

## S15 — TỪ “TÔI BIẾT” SANG “HỌ BIẾT TÔI ĐANG BIẾT”
**Budget:** ~4 phút  
**Objective time:** D+1, 14:20–15:00 (40m actual sourced intake/coordination); E38 actual baseline14:55 nếu source threshold đã authenticate, không chờ scene end

### Player-facing flow

Point of no return không phải lúc Bắc nhận E22.

S15 mở từ sourced case/intake hiện tại và raw sources/context cần receipt, verification hoặc preservation. Bắc có thể đưa nguồn dù chưa nối đúng network; Vũ tiếp nhận và verify phần đủ nguồn độc lập với N3_UNDERSTANDING.

Nguy cơ không thể đơn giản quay về đời thường được kiểm riêng: actual received cross-cell reports đã đưa BARC≥N3 và police preservation còn thiếu. Private understanding không mở/đóng police intake hoặc thay report tới organization.

Vũ nói rõ ở mức chức năng: nếu Bắc có source, lúc này giữ tất cả một mình là rủi ro; evidence cần được tiếp nhận đúng cách.

Player có ba kiểu lựa chọn:

- **đưa source đủ mạnh cho Vũ** → mở preservation route;
- **giữ lại vì muốn tự tìm boss trước** → tăng cleanup/exposure risk;
- **cố bỏ hết khi BARC≥N3 và police chưa đủ preservation** → mở Avoidance route vì received cross-cell reports đã khiến organization coi Bắc là unresolved risk; private N3_UNDERSTANDING một mình không đủ.

### Mục đích narrative

- Định nghĩa “không thể quay về bình thường” bằng received organization awareness và custody thực; private understanding không là điều kiện tiếp nhận nguồn.
- Trả lời canon Avoidance: bỏ từ N1 có thể an toàn; bỏ sau N3 là chuyện khác.

### Player biết trước đoạn

- Có network nhiều cell.
- Organization đang khép access.

### Player có thể biết sau đoạn

- Vũ cần source, không cần theory dài.
- Police preservation là một hành động có consequence.
- Bắc không còn là người duy nhất kiểm soát nhịp sự việc.

### Clue khả dụng

- **C42** bắt đầu trở thành active requirement.
- C43 tiếp tục telegraph timing.

### Clue missable

- Preservation window có thể bị lỡ, nhưng không vì UI timer.

### NPC tham gia

- Vũ.
- Bắc.
- Có thể Linh xuất hiện ngắn như reminder đời sống bình thường đang bị bỏ lại, nhưng không được kéo vào mystery knowledge.

### State có thể thay đổi

- A_PRESERVED đã đúng từ E28 và không lùi; B/C/source còn thiếu tăng custody chỉ theo actual receipt/authentication.
- N3_UNDERSTANDING không auto confirm tại intake; BARC derive reports riêng; Vũ verify complete raw risk context độc lập.
- Nếu police preservation đủ: E38 có thể mở.
- AVOIDANCE_BAD_ROUTE_ARMED chỉ theo received-report BARC≥N3, police preservation còn thiếu và actual abandonment; private N3_UNDERSTANDING không tự arm route.

### Mức căng thẳng

**8/10.**

### Hậu trường đang xảy ra đồng thời

- Khải đánh giá Bắc theo exact received reports; Nam chỉ nhận scope Khải actual forward.
- Protect-core theo baseline crisis vẫn có thể xảy ra với prior BARC, không tự chứng minh Bắc là threat mới.

---

# 16. LATE INVESTIGATION

## S16 — TỪ MANAGER TỚI COMMAND
**Budget:** ~7 phút  
**Objective time:** D+1, 15:00–16:25 presentation/group85m; full D actual baseline16:10, professional offsets từ actual E38

### Player-facing flow

Sau khi A+B+C đủ mạnh, Vũ chủ động hơn. Bắc không phải tự chạy đi lấy hết mọi hồ sơ.

Investigation late game tập trung vào một câu hỏi mới:

**Ai có quyền khiến nhiều nhánh cùng đổi trạng thái?**

Player nhìn lại:

- Hạnh giải thích source/coercion nhưng không biết full hospital/logistics.
- Khoa giải thích hospital cell nhưng không biết dispatch sự cố.
- Hùng giải thích logistics nhưng không biết review chi tiết.
- Khải biết nhiều cell và quản risk, nhưng cần chứng minh ai ở trên hắn có quyền decision.

C30 xác nhận Nam có quan hệ kinh doanh cũ với Hùng/Tân Lộ. Đây vẫn chỉ là relationship.

C31 xuất hiện khi current crisis contact cho thấy Khải báo/trao đổi với Nam sau các mốc cross-cell quan trọng.

Current records có issue trước intake theo OT §0.2: L logistics Nam issue13:20/execution13:25 và H hospital Nam issue13:45/execution13:50 là hai decisions khác nhau. Broker giữ actual forwarded case request13:00 cùng L13:30/receipt13:32 và H14:00/receipt14:05. Hùng firsthand L pairs hospital H original C33_AUTH; Khoa firsthand H pairs logistics L original C34_AUTH, cùng source-annex match exact chosen D2. Original receiver-side Nam reply/authorship phải verify, contact metadata không đủ.

Sau actual E38=t0, Vũ tự request known manager+5m (baseline15:00), other-branch originals+10m (15:05), broker annex+15m (15:10). Manager actual receipt+25m=15:20; other-branch+40m/+45m=15:35/15:40; annex+55m=15:50; final exact origin/content/scope match+75m=16:10. Source availability warning14:00/late reminder15:00 trước deadline; không intake future annex ởE28 hoặc chờ Bắc xin lại. Missing actual cooperation/originals không được grant từ queue.

### Mục đích narrative

- Đưa player từ “ai đáng ngờ” sang “ai có command”.
- Không cho C27/C28/C30 tự biến thành proof.
- Chuẩn bị boss realization bằng source hiện tại.

### Player biết trước đoạn

- Hùng/Khoa/Hạnh đều culpable nhưng có knowledge limit.
- Khải nối nhiều cell.
- Nam có background cũ liên quan logistics/y tế.

### Player có thể biết sau đoạn

- Có current command relation Khải → Nam.
- Nam không còn chỉ là “ông chú từng quen Hùng”.
- D bắt đầu có thể chứng minh.

### Clue khả dụng

- **C30**.
- **C31**.
- **C32** hoặc **C33/C34**.
- C27/C28 chỉ recontextualize, không score D.

### Clue missable

- C31 context có thể khó preserve nếu cleanup đi trước.
- C32 source có thể rút.
- Recovery C32K+C34_AUTH nếu Hùng unavailable, cùng matching late source annex. Timely professional requests/receipts giữ fairness; không record-only D1.

### NPC tham gia

- Vũ.
- Hùng hoặc source manager phù hợp.
- Khoa/Thảo tùy route.
- Khải.
- Nam chưa cần confrontation.

### State có thể thay đổi

- D1 current command.
- D2 independent corroboration.
- Nếu A+B+C đã police-preserved và D đủ: TRUE_ROUTE_AVAILABLE.
- Nếu D thiếu: CLEANUP_PARTIAL_ROUTE.

### Mức căng thẳng

**8–9/10.**

### Hậu trường đang xảy ra đồng thời

- E38 nếu police threshold đạt.
- Nam/Khải bắt đầu đóng nhánh và cắt quyền.
- Hùng/Khoa/Hạnh tự cứu theo động cơ riêng, không hành động như một hive mind.

---

# 17. BOSS REALIZATION

## S17 — NAM KHÔNG “LỘ MẶT”; PLAYER CHỨNG MINH ÔNG CÓ QUYỀN
**Budget:** ~5 phút  
**Objective time:** D+1,optional post-intake travel35m→17:00, ordinary contact15m→17:15; professional custody already held is not retimed

### Player-facing flow

Boss realization phải xảy ra trong hai lớp.

### Lớp 1 — recontextualization

Player nhìn lại các fact đầu game:

- Nam từng làm kho vận + dịch vụ/thiết bị y tế: C27.
- Optional: vật cũ liên hệ Tân Lộ: C28.
- Nam thực sự tử tế: C29.
- Quan hệ Nam–Hùng có lịch sử: C30.

Những fact này làm Nam trở thành một hypothesis hợp lý.

**Nhưng chưa đủ kết luận.**

### Lớp 2 — proof

- C31 cho thấy Khải báo Nam trong current crisis.
- C32 hoặc C33/C34 cho thấy các thay đổi cross-cell hiện tại chịu decision authority của Nam.

Đây mới là **R9 / Proposition D**.

Game không hiện màn “Chọn thủ phạm: NAM”.
Notebook không tự viết “Boss”.

Bắc có thể hiểu trước khi một NPC nói tên chức năng của Nam.

### Scene tại khu trọ

Một scene ngắn ở khu trọ được phép xảy ra sau khi Bắc đã gần hoặc vừa hiểu D.

Nam vẫn cư xử bình thường. Không villain monologue. Không đe dọa lộ liễu. Không hỏi đúng clue Bắc vừa lấy nếu ông chưa có report.

Căng thẳng đến từ việc player biết:

- Nam đã gặp Bắc trước mọi chuyện.
- Sau E24, Nam biết Bắc là worker.
- Bây giờ Nam có thể biết Bắc đã chạm nhiều cell.
- Hai người vẫn đứng trong cùng không gian từng rất bình thường.

Nếu player tiết lộ quá nhiều hoặc đối đầu trực tiếp trước preservation, Exposure/Cleanup risk tăng.

Nếu player giữ calm và đưa D qua Vũ, true route sống.

### Mục đích narrative

- Đạt “fair but invisible”.
- Giữ Nam là con người có đời sống thật, không reset thành caricature.
- Cho replay value mạnh mà không làm opening retroactively giả.

### Player biết trước đoạn

- Nam có relation + current contact.
- Cần proof command, không cần villain confession.

### Player có thể biết sau đoạn

- **R9 hoàn chỉnh:** Nam là command core.
- Sự tử tế đầu game và trách nhiệm đạo đức của Nam cùng tồn tại.

### Clue khả dụng

- C27–C34 theo route.
- C28 vẫn optional.
- Không thêm “boss file”.

### Clue missable

- C28.
- Một trong C32/C33 có thể miss nếu source đóng; cần route thay thế để D2.

### NPC tham gia

- Nam.
- Lan có thể xuất hiện rất ngắn như đời sống nền, nhưng không biết sự thật.
- Vũ qua kênh liên lạc trước/sau scene.

### State có thể thay đổi

- NAM_HYPOTHESIS ≠ NAM_PROVEN.
- NAM_PROVEN chỉ khi D1+D2.
- Exposure risk tăng nếu player confrontation trước preservation.

### Mức căng thẳng

**9/10**, dù gần như không có action.

### Hậu trường đang xảy ra đồng thời

- Nam cân giữa giữ Bắc như một vấn đề có thể cô lập và bảo vệ system.
- Khải ưu tiên đóng source.
- Police đang chạy đua preservation.

---

# 18. CLIMAX

## S18 — AI GIỮ ĐƯỢC SỰ THẬT TRƯỚC?
**Budget:** ~6 phút  
**Objective time:** D+1, khoảng 17:00–20:00

### Player-facing flow

Climax không phải Bắc đánh thắng tổ chức.

Nó là cuộc đua giữa:

**corroboration + preservation**  
và  
**cleanup + source isolation**.

Player phải quyết định trên những gì mình thực sự hiểu:

- source nào là fact trực tiếp;
- source nào chỉ là relationship;
- cái gì phải đưa Vũ ngay;
- ai không nên được báo thêm;
- có dừng ở Hùng/Khải hay đi tới command proof Nam.

Trong true route:

1. A được preserve: withdrawal trước pressure + police chronology.
2. B được preserve: Huyền review + C12 hoặc C15.
3. C được preserve: C17 + corroborator + C22.
4. X được xác minh: các box không độc lập.
5. D1 + D2 đủ: Nam có current command, không chỉ quan hệ cũ.
6. C42 xảy ra trước cleanup lock.

Vũ và lực lượng phù hợp chuyển sang hành động phần lõi. Game chỉ cần thể hiện hậu quả ở mức narrative: records được bảo toàn, các đầu mối bị giữ trong quy trình điều tra phù hợp, các institution hợp pháp tách người/cell liên quan khỏi phần bình thường.

Bắc không tự đột kích.

Trong route xấu/partial, cùng một climax cho kết quả khác vì source đã đóng, evidence chưa rời tay Bắc, hoặc player dừng ở sai tầng.

### Mục đích narrative

- Thưởng reasoning, trust và timing.
- Biến “biết đáp án” và “chứng minh đáp án” thành hai việc khác nhau.
- Giữ cảnh sát có năng lực khi threshold đạt.

### Player biết trước đoạn

- Có hoặc không đủ A/B/C/D.
- Organization đang cleanup.

### Player có thể biết sau đoạn

- Outcome phản ánh chính xác thứ player đã hiểu, preserve và làm lộ.

### Clue khả dụng

- C42 là gate chính.
- C43 là consequence signal.

### Clue missable

- Không có “clue cuối cùng rơi ra” ở climax.
- Climax chỉ kiểm tra những gì player đã xây trước đó.

### NPC tham gia

- Vũ.
- Nam/Khải/Hùng/Khoa/Hạnh theo consequence, không cần cùng một phòng.
- Bắc.
- Các source phù hợp.

### State có thể thay đổi

- E39 True.
- E40 Cleanup/Partial.
- E41 Delay/Missed.
- E42 Wrong Trust/Exposure.
- Avoidance nếu player dừng sau N3.

### Mức căng thẳng

**10/10 về consequence, không phải combat.**

### Hậu trường đang xảy ra đồng thời

- Nam ưu tiên đóng nhánh/bảo toàn lõi.
- Khải cắt access.
- Các manager tự bảo vệ.
- Vũ bảo toàn source đã đủ chuẩn.

---

# 19. ENDING ENTRY POINTS

## G0 — Sau S07: chưa hề bước sang N2
### Neutral Ending — MỘT CA LÀM THÊM

Điều kiện:

- Bắc không chủ động đào sâu.
- Không tạo source leak.
- Không mang anomaly sang cell thứ hai.

Kết quả:

- Bắc được thanh toán hoặc sự cố được xử lý như một vấn đề vận hành.
- Nam/Khải hạ đánh giá Bắc xuống exposure thấp.
- Cuộc đời sinh viên tiếp tục.
- Phía sau, baseline Stage 3 diễn ra: network co lại rồi có khả năng sống sót.

Đây là neutral/short ending, không phải “boss giết Bắc vì cậu nhận một job”.

---

## G1 — Sau S10/S11: A hoặc B có nhưng thiếu bridge cần thiết
### Bad/Partial — QUÁ MUỘN

Điều kiện:

- miss C11/C17 và không có route thay;
- source windows đóng;
- player hiểu có vấn đề nhưng không đủ independent corroboration.

Kết quả:

- Vũ xử lý được phần vụ Phúc hoặc một scandal hẹp.
- Vụ lớn chưa mở trong game window.
- Investigation có thể tiếp tục sau ending, nhưng không có breakthrough miễn phí.

---

## G2 — S07/S14: chia quá nhiều cho Minh hoặc sai đầu mối trước preservation
### Bad — SAI NGƯỜI

Điều kiện:

- C35 leak đủ chi tiết.
- Organization biết sớm các nhánh Bắc đang chạm.
- Source access bị đóng trước khi Vũ preserve.

Kết quả:

- Minh hiểu quá muộn rằng mình không chỉ “báo cho người phụ trách”.
- Một phần evidence vẫn có thể sống, nhưng core route yếu hoặc đóng.
- Không biến Minh thành mastermind.

---

## G3 — Sau N3: cố bỏ toàn bộ
### Bad — QUAY LƯNG QUÁ MUỘN

Điều kiện:

- Bắc đã bị cross-report xác nhận N3.
- Chưa đưa đủ source ra khỏi tay mình.
- Player cố quay về sinh hoạt bình thường và bỏ mọi contact.

Kết quả:

- Organization vẫn phải coi Bắc là unresolved risk.
- Bắc bị cô lập khỏi source và không còn khả năng tự quyết như trước.
- Không mô tả bằng bạo lực phô trương; trọng tâm là consequence của việc đã đi quá sâu rồi mới giả vờ không biết.

---

## G4 — A+B+C đủ nhưng D chưa được preserve
### Bad/Partial — DỌN SẠCH

Điều kiện:

- Police hiểu network nhiều cell.
- Hùng/Khoa/Hạnh có thể bị xử lý theo phần đã chứng minh.
- Current command Nam chưa đủ D1+D2 hoặc tới quá muộn.

Kết quả:

- Operation hiện tại bị thiệt hại nặng.
- Nam/Khải có cơ hội tách khỏi phần đã lộ.
- Player có thể hiểu đúng hơn mức hồ sơ kịp chứng minh.
- Đây là ending dễ khiến player replay vì họ nhận ra mình dừng ở “boss giả” hoặc chậm một bước.

---

## G5 — Player tự confront / giữ evidence một mình ở N3–N4
### Bad — BỊ NHÌN THẤY

Điều kiện:

- Bắc để organization biết chính xác mình có gì trước khi source được preserve.
- Hoặc player đi vào một cuộc hẹn/đối đầu không an toàn thay vì đưa evidence sang Vũ.

Kết quả:

- Bắc bị loại khỏi vai trò điều tra hoặc bị cô lập đủ để chain evidence gãy.
- Organization cleanup đi trước.
- Không biến thành combat ending.

---

## G6 — A+B+C+D + T đúng timing
### TRUE ENDING — NHỮNG MẢNH KHỚP LẠI

Điều kiện:

- Slot A1 đủ.
- Slot B1 đủ.
- Slot C1 đủ.
- X được Vũ verify.
- D1 + D2 đủ.
- C42 xảy ra trước cleanup lock.
- Không cần C28.
- Không cần mọi optional clue.
- Không cần accusation quiz.

Kết quả:

- Vũ chuyển điều tra lên phần lõi.
- Mạng chính bị phá ở mức thỏa mãn.
- Bắc sống và trở lại đời sống sinh viên.
- Tân Lộ/Minh Trạch không bị narrative coi toàn bộ là tội phạm; phần hợp pháp tiếp tục xử lý hậu quả.
- Lan/Linh chỉ biết mức cần thiết, không bị biến thành người biết toàn conspiracy.
- Nam không được “minh oan vì cấp dưới làm hết”; architecture tồn tại vì ông.

### Dư âm tinh tế

Ở epilogue, khi khu trọ dần trở lại bình thường, một vật đời thường cũ của Nam được bà Lan gom lại cùng đồ sửa chữa. Trên đó có một tên/đơn vị nghề nghiệp cũ chưa từng xuất hiện trong hồ sơ 2026.

Game không giải thích nó.

Nó không phủ định việc main network đã bị phá và không phải hook sequel bắt buộc. Nó chỉ nhắc rằng lịch sử nghề nghiệp của Nam dài hơn phần vụ án mà Bắc vừa nhìn thấy.

---

# 20. STORY FLOW TÓM GỌN

**Bắc chuyển vào trọ, gặp Nam như một người bình thường  
→ đi học, gặp Linh/Minh, thiếu tiền  
→ Minh đưa kênh việc part-time hợp pháp  
→ Bắc nhận E22  
→ job có vài chi tiết lệch nhưng vẫn hoàn tất  
→ game quay lại ăn/học/về trọ  
→ Tân Lộ audit job  
→ Bắc tò mò chủ yếu để tự bảo vệ và lấy tiền  
→ D+1 chứng minh job đã bị cố ý hạ classification  
→ lần đầu có fact đủ cụ thể để báo Vũ  
→ Vũ nối bridge với vụ Phúc đã tồn tại trước Bắc  
→ Huyền cho thấy hospital pattern đã tồn tại trước E22  
→ timestamps recontextualize opening: Bắc bước vào một cleanup có sẵn  
→ player có thể nghi Tuấn, rồi Hùng  
→ Đức/Yến/Huyền/Thảo tạo các nguồn độc lập  
→ Khoa và Hùng cùng dẫn tới Khải  
→ A+B+C thành một network nhiều cell  
→ organization nhận ra Bắc đang nối các cell  
→ access khép, Minh betrayal có thể nở hậu quả  
→ Bắc phải đưa evidence ra khỏi tay mình  
→ late investigation chuyển từ managers sang command  
→ C31 + C32/C33/C34 chứng minh Nam có quyền hiện tại  
→ scene khu trọ đổi nghĩa nhưng Nam không monologue  
→ climax là preservation vs cleanup  
→ ending phản ánh understanding + trust + timing.**

---

# 21. STATE MODEL TỐI THIỂU CHO STORY SCRIPTING

Không hiển thị meter cho player.

Các state narrative cần đủ để script consequence:

- BARC_N0 / N1 / N2 / N3 / N4 — organization knowledge về Bắc.
- JOB_E22_SEEN.
- C03_SAVED.
- C04_SEEN.
- MINH_LEAK.
- TUAN_FALSE_THEORY.
- TUAN_NOT_RECLASSIFIER / TUAN_CORE_SCOPE_VERIFIED (professional case-scope, không private innocence quiz).
- A_PROVEN (institutional authentication từ E28); A_PLAYER_SEEN/A_PLAYER_UNDERSTOOD riêng.
- B_PROVEN.
- C_PROVEN.
- X_PLAYER_CONNECTED / X_VERIFIED (private inference khác police verification).
- KHẢI_LAYER.
- D1_COMMAND.
- D2_CORROBORATED.
- A_PRESERVED / B_PRESERVED / C_PRESERVED / D_PRESERVED.
- CLEANUP_ACCELERATED.
- TRUE_ROUTE_AVAILABLE.

Không có:

- suspicion meter hiện UI;
- “boss confidence %”;
- evidence score công khai;
- auto-link graph.

---

# 22. PACING AUDIT

## 22.1. 20 phút đầu có thật sự đời thường không?

**PASS sau chỉnh.**

Trước khi first anomaly có trọng lượng, player đã:

- chuyển trọ;
- gặp Lan/Nam;
- đi học;
- gặp Linh/Minh;
- xử lý chuyện tiền;
- ăn/trò chuyện;
- nhận việc vì lý do đời thường.

Inciting xảy ra sớm nhưng không mang tone “vụ án”.

## 22.2. Có bị clue → clue → clue không?

**PASS sau chỉnh.**

Các breather bắt buộc:

- S05 trả hẳn game về ăn/uống/chat/trọ.
- Cuối S07 có khoảng yên trước D+1.
- Linh/Lan tiếp tục tồn tại như đời sống không biết conspiracy.
- Noise ở Tân Lộ/Minh Trạch chứng minh phần lớn institution bình thường.

## 22.3. Midpoint có tới quá sớm không?

**PASS.**

Player chỉ có thể hiểu crisis lớn hơn job sau:

- anomaly;
- reclassification;
- police timeline;
- hospital pattern.

Không ai nói đáp án ở phút đầu.

## 22.4. Late game có quá nhiều source để Bắc tự gặp không?

**PASS.**

D+1 source windows chạy song song. Bắc mở bridge; Vũ xác minh một phần. True route không yêu cầu đi hết Đức + Yến + Huyền + Thảo bằng chân.

---

# 23. MYSTERY FAIRNESS AUDIT

## 23.1. R1 — job bị hạ luồng

Seed C02/C03/C04 xuất hiện trước C17. C20/C22 sửa false interpretation Tuấn.

**PASS.**

## 23.2. R2 — Phúc

C08/C10/C11A chứng minh chronology. Phúc vẫn có omission C09, không biến thành perfect victim/exposition machine.

**PASS.**

## 23.3. R3 — hospital

C11 + C12/C15. Huyền có thể bị nghi nhưng timestamp và behavior giải oan.

**PASS.**

## 23.4. R4/R5 — Tân Lộ và Tuấn

Tân Lộ leadership culpability cần C17 + independent corroborator + C22. Tuấn bị loại bằng permission/timing, không bằng “NPC bảo anh vô tội”.

**PASS.**

## 23.5. R7/R8 — network / manager layers

Khải chỉ trở thành cross-cell inference sau C24+C25; Hùng/Khoa/Hạnh không bị flatten thành một villain.

**PASS.**

## 23.6. R9 — Nam

C27/C28/C29/C30 chỉ cho plausibility/recontextualization.

D chỉ được chứng minh bằng current command:
C31 + C32 hoặc C33/C34.

Không có villain monologue.

**PASS.**

## 23.7. True ending

Không cần một pixel hoặc một clue duy nhất. Có redundancy cho B/C/D. C28 không mandatory.

**PASS.**

---

# 24. CHARACTER MOTIVATION AUDIT

## Bắc

Chuỗi motive:

**thiếu tiền → bảo vệ mình khỏi bị đổ lỗi → tò mò vì fact không khớp → nhận ra có người thật đang bị ảnh hưởng → hiểu việc mình biết tạo trách nhiệm.**

Không có bước “tự nhiên muốn phá tổ chức”.

**PASS.**

## Nam

- N0: không quan tâm đặc biệt.
- N1: quan sát, vì hành động mạnh tạo rủi ro lớn hơn.
- N2: Khải theo dõi consequences.
- BARC N3: Nam trực tiếp quan tâm sau actual cross-cell report được forward tới ông; private N3_UNDERSTANDING không báo tới Nam.
- N4: ưu tiên cleanup/protect core.

Thiện cảm cá nhân với Bắc có thể tồn tại nhưng không override system.

**PASS.**

## Vũ

Phản ứng tăng theo evidence:

- weird story → ghi nhận;
- source record → kiểm tra;
- independent corroboration → mở rộng;
- A+B+C → preservation;
- D đủ → hành động lên lõi.

**PASS.**

## Minh

Betrayal chỉ xảy ra nếu Bắc cho cậu thông tin để leak. Động cơ là sợ mất việc và tin công ty đang xử lý issue bình thường.

**PASS.**

## Tuấn

Che vùng xám nghề nghiệp, không che core crime. Vì vậy vừa đáng nghi vừa có thể giải oan.

**PASS.**

## Huyền / Thảo / Đức / Yến

Mỗi người cung cấp đúng phần họ biết và có motive độc lập:

- Huyền: làm đúng compliance.
- Thảo: giằng co giữa tự biện minh và trách nhiệm.
- Đức: tự bảo hiểm.
- Yến: sợ dấu chân tài chính.

Không ai trở thành exposition machine.

**PASS.**

---

# 25. “WHY DOESN’T PLAYER JUST CALL POLICE?” AUDIT

## Trước S08

Bắc chỉ có:

- một job hơi lạ;
- một field y tế/ưu tiên;
- routing có thể là lỗi kho;
- payment/audit issue.

Đây chưa phải một vụ án rõ.

## Sau S08

Bắc có record cho thấy một job bị cố ý hạ classification trước khi cậu nhận.

Đây là điểm hợp lý để gọi/đến police.

Stage 5 **chủ động cho Vũ vào ngay ở S09**, không kéo mystery bằng cách bắt Bắc ngu hoặc cảnh sát không nghe.

## Sau S09

Bắc tiếp tục tham gia không phải vì police từ chối, mà vì:

- cậu đang là người có bridge giữa các source;
- Vũ chưa thể tự biết những observation Bắc chưa đưa;
- source windows đang đóng;
- Vũ cần facts/source để mở rộng hợp pháp.

## Sau E38

Bắc không còn tự làm “cảnh sát phụ”. Vũ chủ động điều phối preservation và phần lõi.

**PASS.**

---

# 26. “WHY DOESN’T NAM ELIMINATE THE PROBLEM IMMEDIATELY?” AUDIT

## N0

Bắc chỉ là hàng xóm.

Không có problem.

## N1

Bắc là worker vô tình chạm job.

Nam không biết cậu hiểu gì.

Đánh động Bắc sẽ biến một exposure hành chính thành một sự kiện xã hội/cảnh sát.

## N2

Bắc tò mò.

Curiosity vẫn chưa bằng proof. Khải theo dõi và cắt access là rẻ, kín và hợp doctrine hơn.

## N3

BARC N3 nghĩa organization đã nhận đủ reports Bắc chạm/nối nguồn ở nhiều cell; private inference đúng/sai riêng. Nam biết mức actual Khải forward.

Organization bắt đầu phản ứng mạnh hơn theo nhận thức đó, nhưng ưu tiên:

- source isolation;
- access lock;
- framing sự cố như administrative;
- cleanup.

## N4

Nếu evidence đã vào tay Vũ, “xử Bắc” không giải quyết được gì; nó chỉ tạo thêm vụ án.

Nam phải bảo toàn lõi và rút nhánh.

Đây cũng phù hợp với tính cách Nam: bạo lực là phương án cuối vì tạo witness, attention và phản ứng khó kiểm soát.

**PASS.**

---

# 27. REPLAY FORESHADOWING AUDIT

Khi replay, các điểm sau đổi nghĩa mà không đổi fact:

1. **Nam giúp Bắc ở S01** — kindness là thật.
2. **C27** — background logistics/y tế nằm ở giao điểm của hai cell, nhưng run đầu không đủ proof.
3. **C28** — vật Tân Lộ cũ chỉ là junk nghề nghiệp lần đầu.
4. **S05** — Nam gặp Bắc bình thường sau khi hậu trường E24 đã khiến ông biết Bắc là worker E22; ông vẫn không “diễn villain”.
5. **C02/C04** — job nhìn như lỗi vận hành, nhưng player replay biết Hùng đã hạ luồng D−1.
6. **C11A/C11** — tất cả crisis quan trọng đều bắt đầu trước Bắc.
7. **Tuấn procedural** — lần đầu đáng ngờ, replay lại cho thấy behavior nhất quán.
8. **Minh giới thiệu job** — lần đầu có thể bị đọc như setup; replay hiểu đó thật sự là một lời giúp việc bình thường.
9. **Bureaucratic cleanup** — lần đầu giống thủ tục; replay thấy đó là defense mechanism của network.
10. **Khu trọ** — không phải “hang ổ”; chính vì nó thật sự bình thường nên final Nam scene có trọng lượng.

**PASS.**

---

# 28. SELF-CORRECTIONS ĐÃ ÁP DỤNG TRƯỚC KHI KHÓA BẢN

1. Không cho Vũ xuất hiện do coincidence kiểu “đứng đúng chỗ Bắc giao hàng”. Police entry chỉ mở khi Bắc có C17/source đủ cụ thể để báo và overlap với vụ Phúc được Vũ xác minh.
2. Không biến first anomaly thành bằng chứng phạm tội. Nó chỉ là mismatch vận hành.
3. Không cho Bắc gặp mọi source D+1. Vũ gánh phần xác minh chuyên nghiệp.
4. Không biến C28 thành clue bắt buộc cho Nam.
5. Thêm neutral route nếu Bắc thật sự bỏ qua từ N1, giữ đúng baseline Stage 3.
6. Chỉ dùng Avoidance bad ending theo received-report BARC N3/N4, preservation còn thiếu và actual abandonment; không lấy private N3_UNDERSTANDING thay awareness.
7. Không cho confrontation với Nam là điều kiện true ending; thực tế confrontation sớm còn làm route xấu hơn.
8. Climax được chuyển từ physical danger sang preservation race.
9. Minh betrayal được giữ hoàn toàn conditional.
10. Nam không được “hỏi trúng clue” ở khu trọ nếu chưa có report observable.
11. Hospital investigation không yêu cầu Bắc hack/trộm hồ sơ.
12. Hùng là false apex có tội thật; Tuấn là innocent suspect có vùng xám thật.
13. True ending giữ requirement source + command + timing, không thành checklist mọi clue.

---

# 29. STAGE 6 HANDOFF

Stage tiếp theo có thể chia file này thành:

- chapter/scene IDs;
- dialogue beats;
- interaction opportunities;
- fail-forward transitions;
- level/hub routing;
- scripted state triggers;
- notebook copy;
- ending scripts.

Nhưng không được:

- thay causal order để scene “cool” hơn;
- thêm clue chứng minh D chỉ vì late game thiếu thời gian;
- cho Nam confession;
- cho Vũ chậm sau A+B+C;
- cho Bắc combat giải climax;
- biến Tân Lộ/Minh Trạch thành toàn người xấu;
- cho một source kể quá knowledge state;
- bỏ các breather đời thường và biến 20 phút đầu thành foreshadow liên tục.

**END — PLAYER-FACING STORY / STAGE 5**
