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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** D0 07:30, Bắc nhận phòng trọ; Lan đang kiểm điện và đưa chìa. Hành lang có tiếng quạt, ổ điện chập chờn trong phòng Bắc, góc Nam sửa đồ nằm trong tầm nhìn nhưng không được đóng khung đáng ngờ.

**CURIOSITY → ACTION:** Đèn bàn chớp khi Bắc cắm ổ kéo; tiếng Lan gọi Nam từ hành lang. Player đặt vali, thử công tắc/ổ, mở cửa cho Nam; có thể liếc card cũ C28 hoặc đọc hợp đồng thuê.

**DISCOVERY → RESPONSE:** Lỗi điện là việc thật; Nam giúp đúng nghề. C27 chỉ background; C28 optional không chứng minh current command. Lan đưa chìa sau khi Bắc nhận phòng; Nam tới vì lời Lan gọi, sửa ổ và về góc đồ. NPC: Lan kiểm công tơ; Nam tiếp tục sửa món khác nếu Bắc chưa ra.

**SIGNATURE:** S01_POWER_REPAIR: player giữ góc nhìn và thử điện trước/sau sửa, không cắt sang exposition. Micro events: Tiếng quạt ngừng rồi chạy; điện thoại báo số dư/tiền trọ.

**PERSISTENCE / RETURN:** Ổ chuyển FAULT→WORKING do Nam xử lý; đồ cũ vẫn ở đó, không tự xuất hiện. Optional: C28/card Tân Lộ cũ và một cử chỉ tử tế C29. Return payoff: Khi S17 recontextualizes Nam, vật cũ vẫn chỉ là quan hệ nghề nghiệp.

**FAIL-FORWARD / EXIT:** Không xem card vẫn tới lớp; thao tác thử ổ có hint không tốn thời gian. Đồ được đặt, điện ổn, player xác nhận rời trọ 08:35.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S01 rời trọ; tới trường 09:00. Bảng phòng học, ghế có ổ hỏng, file bài giảng và bảng thông báo việc làm trong một ngày bình thường.

**CURIOSITY → ACTION:** Linh chỉ chỗ ngồi có ổ điện; thông báo chi phí sáng màn hình, Minh đưa link công việc. Player tìm lớp, đổi chỗ, chụp bài hoặc nhận file; tự mở listing khi cần tiền.

**DISCOVERY → RESPONSE:** Linh phân biệt thấy với đoán qua bài tập; Minh từng nhận ca thường C07 nếu hỏi/xem lịch sử được phép. Giờ học và bữa trưa tiến theo nhóm hành động đã định, không vì đọc UI lâu. NPC: Linh học, Minh đi ngang rồi nhắn link; không nhân vật nào biết crime.

**SIGNATURE:** S02_CLASS_ROUTINE: player tìm đúng phòng và chỗ học trong sinh hoạt đang diễn ra, áp lực tiền hiện qua thao tác điện thoại. Micro events: Ổ cạnh ghế tắt; điện thoại rung bởi deadline lớp.

**PERSISTENCE / RETURN:** Thông báo chi phí nằm lại trong phone; lớp tan và bảng việc vẫn có. Optional: C07 lịch sử ca cũ, không là chứng cứ mạng lưới. Return payoff: S07 so ca bình thường với assignment mới.

**FAIL-FORWARD / EXIT:** Bỏ qua mọi thoại tùy chọn vẫn có link và lý do xem việc. Lớp/bữa trưa kết thúc 11:15; listing có thể mở.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S02 11:15, Bắc ở khu ăn sinh viên. Nhiều listing bình thường; ca TL-2604-117 có tiền nhỉnh hơn vì khung giờ và proof-of-handover.

**CURIOSITY → ACTION:** Minh chuyển link đúng lúc Bắc xem số dư; phone rung cạnh hóa đơn bữa ăn. Player so giờ học/tiền/đầu việc, chấp nhận ca hoặc do dự; không ai gọi chọn riêng Bắc.

**DISCOVERY → RESPONSE:** C02 là assignment và nhóm khách y tế, chỉ bề mặt công việc. Nhận ca phát assignment; xác nhận di chuyển tính authored 34m nhóm và 35m tới Tân Lộ. NPC: Minh trở lại việc riêng, không theo player điều tra.

**SIGNATURE:** S03_JOB_ACCEPT: quyết định được đặt trong ngân sách và lịch học có thể xem, không lời độc thoại lý giải. Micro events: Màn hình số dư; app báo hạn nhận ca.

**PERSISTENCE / RETURN:** Assignment vào lịch sử; trạng thái job ACCEPTED một lần. Optional: C07 đối chiếu ca cũ nếu đã xem. Return payoff: S07/S08 so lịch sử với routing của ca này.

**FAIL-FORWARD / EXIT:** Đã từ chối ban đầu vẫn có một lần nhận lại trong window; không rơi vào bế tắc. Job accepted; đi Tân Lộ theo travel card tới12:24.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** Tân Lộ check-in12:24; pickup12:30 rồi tới đầu nhận. Quầy dispatch với nhiều gói thật, máy quét, printer, nhân viên bận; pouch kín đi qua luồng thường.

**CURIOSITY → ACTION:** Scanner báo mismatch nhẹ, nhãn routing có mép dán lại, giấy proof-of-handover ló khỏi khay. Player nhận pouch, giữ nguyên niêm, giao và xem lịch sử/biên nhận sau scan; có thể nhìn C04 nếu nhãn thực sự lộ.

**DISCOVERY → RESPONSE:** C03 đầu nhận/account family; mismatch không phải bằng chứng crime, C04 chỉ từ vật/ảnh nhìn rõ nhãn. Nhân viên xử lý mã hợp lệ theo quy trình; Tuấn đi qua kiểm công việc khác, không chọn Bắc. NPC: Tuấn phân ca, đầu nhận xác minh, không ai giải thích conspiracy.

**SIGNATURE:** S04_SCAN_MISMATCH: player tự đưa gói vào scanner và thấy hai trường không khớp rồi nhân viên sửa bằng thao tác thường. Micro events: Máy quét beep hai nhịp; printer kéo giấy; xe đẩy đi ngang.

**PERSISTENCE / RETURN:** Job DELIVERED, C03 original13:52 lưu lịch sử; later observed_at khi player mở lại, không rewrite source time. Optional: Dấu routing C04 và tiếng đầu nhận hỏi mã. Return payoff: S06 audit và S08 reclassification giải nghĩa mismatch.

**FAIL-FORWARD / EXIT:** Không inspect nhãn vẫn có biên nhận/history và audit. Proof-of-handover hoàn tất 13:52; đóng ca14:10.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S04 đóng ca, bữa ăn gần đầu nhận14:30; trở về trọ18:05. Quán ăn và phòng trọ sinh hoạt bình thường; thanh toán job còn PENDING.

**CURIOSITY → ACTION:** Phone đợi tiền và tin Linh; Nam trả món đồ điện hoặc Lan nhắc chỗ để đồ. Player chọn bữa rẻ, xem bài, đi về; có thể nhận món Nam sửa và đặt lại.

**DISCOVERY → RESPONSE:** Nam tử tế trong chuyện nhỏ C29; khoản pending chưa phải dấu tội phạm. Bữa/việc học cho tới17:30 rồi travel về trọ; audit đến sau ordinary beat18:07. NPC: Nam sửa đồ, Lan làm việc nhà, không chất vấn Tân Lộ.

**SIGNATURE:** S05_ORDINARY_RETURN: một đoạn thở do player điều khiển, căn phòng cũ thay âm và vị trí vật để tạo cảm giác sống. Micro events: Âm quán ăn thay bằng tiếng ngõ; quạt phòng chạy; phone không báo tiền.

**PERSISTENCE / RETURN:** Vật đã sửa chuyển về phòng Bắc, payment PENDING; không tăng BARC. Optional: Một câu nói đời thường của Nam/Lan. Return payoff: S17 cùng hành lang đổi nghĩa bằng hiểu biết player, không cần biến Nam thành quái.

**FAIL-FORWARD / EXIT:** Bỏ qua chuyện phụ không ảnh hưởng audit. Ordinary room beat xong 18:07, S06 notification.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** Audit18:07 sau S05 ordinary beat. Trong phòng, job app bất ngờ yêu cầu đối lại thời gian/đầu nhận, payment giữ chờ.

**CURIOSITY → ACTION:** Phone rung hai lần; form hỏi field mà player vừa thấy scanner xử lý. Player mở history, so biên nhận, trả lời chỉ phần trực tiếp thấy; có thể gọi Tuấn theo option có cost.

**DISCOVERY → RESPONSE:** Audit hướng tới routing; Tuấn phòng thủ trong giới hạn vận hành, không thú nhận hoặc đọc notebook. Form xác nhận sau S06 15m; explicit chờ kết quả tới20:00 hiển thị trước commit. NPC: Tuấn đang xử lý audit khác; chỉ phản hồi câu hỏi có trong work ticket.

**SIGNATURE:** S06_AUDIT_FORM: player đối chiếu record thay cho nghe NPC kể toàn bộ lỗi. Micro events: Tin payment đổi trạng thái; tiếng khu trọ tiếp tục ngoài cửa.

**PERSISTENCE / RETURN:** Payment HOLD, audit receipt; phone giữ original job history. Optional: Một field scan bất thường đã quan sát ở S04. Return payoff: S07 curiosity bắt đầu từ bất nhất cụ thể.

**FAIL-FORWARD / EXIT:** Trả lời tối thiểu vẫn mở S07; không gây LEAK tự động. Đã xem form và chọn explicit wait tới20:00.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** 20:00, job audit đang chờ; lựa chọn early exit còn mở ở N1. Phòng yên, lịch sử ca Minh C07 và TL-2604-117 hiện trong app; hành lang vẫn sống.

**CURIOSITY → ACTION:** Hai dòng assignment có nhãn khác nhau; Minh nhắn hỏi đã nhận tiền chưa. Player đặt hai record cạnh nhau; hỏi Minh chung hoặc gửi exact screenshot/theory. Confirm stop nếu muốn G0.

**DISCOVERY → RESPONSE:** Khác biệt ca không chứng minh crime; disclosure ledger chỉ ghi phần Bắc thật sự gửi. Nếu Minh hỏi hộ company, E26 chỉ sau actual message/report receipt; phone gửi không đồng nghĩa Khải/Nam biết ngay. NPC: Minh trả lời theo thứ được hỏi; Lan khóa cổng, Nam không có magic awareness.

**SIGNATURE:** S07_COMPARE_AND_CHOOSE: thao tác so ca rồi chọn kênh tin trước day transition. Micro events: Tin nhắn rung; đèn hành lang tắt theo giờ.

**PERSISTENCE / RETURN:** Disclosure payload hoặc NONE, BARC theo report thật; G0 chỉ nếu early stop đủ điều kiện. Optional: C07 không bắt buộc, so tối thiểu từ field job app. Return payoff: S14 nếu có leak, timestamp report khớp cửa đóng, không auto betrayal.

**FAIL-FORWARD / EXIT:** Không so vẫn có audit cụ thể dẫn tới S08; early stop là lựa chọn rõ. Continue và explicit ngủ/chờ tới D+1 08:30, hoặc G0.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** D+1 09:00 Tân Lộ; xử lý payment/incident hợp lệ. Máy printer và terminal dispatch mở cùng job; Đức cầm bản snapshot cá nhân; notice đóng worker access11:00.

**CURIOSITY → ACTION:** Printer trả một bản Internal/Priority cũ trong khi app hiển thị Standard; Đức chú ý Bắc nhìn thấy. Player so bản in C17 với assignment, hỏi quyền classification; 09:35 có thể nhận C18 copy từ Đức trong10m hoặc giữ contact/deadline đưa Vũ.

**DISCOVERY → RESPONSE:** E19 reclassification D−1 bởi tầng trên Tuấn; không suy từ pattern rằng Đức biết organ crime. Warning09:25 trước closure; Đức offer copy thực tế từ09:30, không chờ scene S12. NPC: Đức tránh lộ danh tính nhưng giữ private phone copy; Tuấn vận hành không tự reclassify.

**SIGNATURE:** S08_PRINT_COMPARE: player tự đặt bản Internal và Standard song song trong khoảng cửa còn mở. Micro events: Printer feed; badge beep; worker app quyền truy cập đổi màu ở giờ đóng.

**PERSISTENCE / RETURN:** C17 observed, C18 local receipt09:45 nếu chọn; notice và contact tồn tại đến11:00. Optional: Bounded finance lead Yến; alternate police route nếu không nhận trực tiếp. Return payoff: S09 Vũ bắt đầu requests từ actual group/contact, S12 verify retained copies.

**FAIL-FORWARD / EXIT:** Không nhận C18 vẫn có scoped contact và C19 alternate; local lock không erase copy. Core09:35, optional copy09:45; explicit hẹn S09 10:00.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S08 C17/source lead và lịch hẹn phone Vũ 10:00. Bắc đứng ở Tân Lộ; trên phone có assignment, receipt và bản in; Vũ ở đầu dây trong micro-set.

**CURIOSITY → ACTION:** Tin hẹn từ Vũ và trường đầu nhận Minh Trạch khiến cuộc gọi có mục tiêu. Player chọn gửi original record/contact/group/deadline và phân loại thấy hay suy; optional disclose lead mới có 5m cost.

**DISCOVERY → RESPONSE:** Vũ đã có vụ Phúc A=2 từ E28; anh hỏi raw scope, không kể toàn vụ; request B/C khởi từ actual payload. C17/group payload receipt10:15; Vũ contact Đức10:25/receipt10:35 nếu đủ contact và tự request hospital review khi group có. NPC: Vũ làm việc song song, không đợi Bắc đi từng nơi; Nam không nghe private call.

**SIGNATURE:** S09_SCOPED_INTAKE: player gửi source có timestamp và thấy police receipt tách khỏi queued query. Micro events: Phone ring; message acknowledgment; tín hiệu office nền.

**PERSISTENCE / RETURN:** Police custody mới chỉ cho actual received/authenticated sources; warnings hospital11:30/finance12:30. Optional: C18/C19 scoped leads có thể gửi trong kênh hợp lệ. Return payoff: S10 review và S12 C22 matched từ đúng request sáng.

**FAIL-FORWARD / EXIT:** Chậm disclosure dùng q-relative receipts, không backdate; police A vẫn an toàn. Cuộc gọi15m hoàn tất, travel hospital30m tới10:50/10:55.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S09 xong; hospital arrival10:50/10:55, notice review11:30. Quầy Huyền có khay form hai version; hành lang công khai, không vào phòng hạn chế.

**CURIOSITY → ACTION:** Printer nhả bản scope thu hẹp, version cũ còn ở khay được phép xem khi Vũ đã request đúng nhóm. Player so consent và review tại quầy theo quyền cho phép; có thể hỏi Thảo về phần bà trực tiếp xử lý nếu C12 thiếu.

**DISCOVERY → RESPONSE:** C11 discrepancy về money/withdrawal; C12 receipt Khoa biết và vẫn giữ consent, hoặc C15 firsthand cùng case. Huyền không tự biết cả mạng. Vũ nhận originals11:10, authenticate11:20 nếu actual request; optional Thảo10m tới11:20/11:25. NPC: Huyền tiếp bệnh án hợp pháp; Thảo chỉ có mặt trong window, Khoa ở cell riêng.

**SIGNATURE:** S10_FORM_VERSION: player tự đối chiếu hai version; nhân viên chỉ phản ứng đúng phần đã hỏi. Micro events: Hành lang bớt tiếng khi cửa khép; máy in và bánh xe đẩy.

**PERSISTENCE / RETURN:** Document version/scope hiển thị; police B chỉ tăng sau original fact/authentication; local11:30 không erase receipt. Optional: C15 alternative; C14 framing chỉ hỗ trợ suspicion. Return payoff: S11 thời điểm review D−12 đặt bên cạnh Phúc/job.

**FAIL-FORWARD / EXIT:** Không gặp Thảo khi C12 đủ vẫn sống; nếu source cuối mất, warning đã có và G1 sau closure. Core11:10/11:15, optional11:20/11:25; S11 quiet point11:30.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S10 trong hospital area, quiet point11:30. Ba timeline cards là raw timestamps: Phúc, Huyền, E19 job; điện thoại của Bắc đặt cạnh police scoped summary.

**CURIOSITY → ACTION:** Tin Vũ chứa một timeline field mới; ngày D−12 nổi khác với D−1 của job. Player kéo/đặt đúng thứ tự ba bản gốc; có thể xem exact A content ở mức Vũ cho phép, không giao lại A.

**DISCOVERY → RESPONSE:** Vụ Phúc/review có trước Bắc; C03 client family đổi nghĩa khi so provenance, không phải nguyên nhân crime. Vũ nhận ý kiến qua phone; A đã custody E28 không phụ thuộc player drag đúng. NPC: Vũ tiếp tục professional match, Phúc chỉ biết chuyện mình.

**SIGNATURE:** S11_TIME_COMPARE: player tự xếp nguồn theo time, một inference về vị trí Bắc trong cleanup. Micro events: Âm bút gạch thời gian; phone hạ âm khi mở document.

**PERSISTENCE / RETURN:** Private inference nếu đúng mới ghi; CASE không bị hạ vì xếp sai. Optional: C09 hỗ trợ chronology, không là gate A. Return payoff: S12 false apex có thể được bác bằng thứ tự E19/assignment.

**FAIL-FORWARD / EXIT:** Sai xếp vẫn có raw records để xem lại miễn phí; progression không đòi quiz. Compare/wait tới12:00; travel Tân Lộ30m tới12:30.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S11 và retained police packets; Tân Lộ12:30. Cùng dispatch terminal nay hiển thị audit trail; C17, C20, C21 và C22 đã được request/received theo lịch, không source mới từ worker lock.

**CURIOSITY → ACTION:** Tuấn đi qua bảng phân công như hôm qua; timestamp override nằm trước ca anh trực. Player mở fast recap hai field C20/C22 thay vì làm lại interrogation; có thể xem C21 routine từ job thường.

**DISCOVERY → RESPONSE:** Tuấn không reclassify E19; C22 Hùng đã nhận purpose và approve, nhưng statement Hùng một mình chưa chứng minh Nam. Police C22 packet receipt13:00; content match không trước14:55 và retained C18/C19 verification13:55. NPC: Tuấn xử lý ca khác, không bất ngờ biết Bắc nghi ai; Hùng không cần monologue.

**SIGNATURE:** S12_FALSE_APEX_SWAP: cùng quầy S04, player tự lật audit trail, nghi ngờ đổi từ Tuấn sang Hùng bằng evidence. Micro events: Máy quét lặp đúng âm S04; hình ca thường song song ca 117.

**PERSISTENCE / RETURN:** TUAN_NOT_RECLASSIFIER riêng TUAN_CORE_SCOPE_VERIFIED; Hùng culpable knowledge chỉ từ verified C22. Optional: C21 hành vi nhất quán; optional conversation không gate. Return payoff: S16 Hùng D1 chỉ khi firsthand actual statement, không suy từ title.

**FAIL-FORWARD / EXIT:** Nếu đã thấy C20, dùng recap ngắn; nếu chưa, phiên bản full inspect vẫn cho cùng fact. Retained verification tới13:00, travel hospital area13:30/micro-set13:35.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S12 source receipts đã có; police micro-set13:35. Hai request/response packets hospital/logistics với endpoint Khải có thể đặt cạnh nhau; paper custody tags khác private notebook.

**CURIOSITY → ACTION:** Hai thẻ escalation có cùng người nhận nhưng scope khác, điện thoại Vũ báo callback. Player so current case, endpoint, role và response; có thể chọn giả thuyết sai về Khải mà vẫn giao raw packets cho Vũ.

**DISCOVERY → RESPONSE:** X_RISK chỉ khi request/response/auth current Phúc crisis matched; same account/transaction không đủ; N3_UNDERSTANDING private conditional. Vũ verify C18/C19 match13:55, C content14:55 nếu actual packets complete; X police không đợi player suy đúng. NPC: Vũ kiểm provenance, Khải chỉ biết report đã nhận; Nam chỉ sau forward thực.

**SIGNATURE:** S13_TWO_DESKS: player nối hai hồ sơ từ hai cơ sở trong không gian chung, phản hồi của Vũ giới hạn vào source đã thấy. Micro events: Phone callback; bàn giấy lật, âm phòng nhỏ hơn hành lang.

**PERSISTENCE / RETURN:** X_VERIFIED chỉ khi raw risk source đủ/authenticated (hoặc late X_COMMAND ở S16), X_PLAYER_CONNECTED private tách; no auto N3/BARC on completion. Optional: Khải false apex theory; không chặn custody. Return payoff: S16 X_COMMAND có thể hoàn chỉnh X nếu Khải remit còn thiếu.

**FAIL-FORWARD / EXIT:** Sai inference không time/route penalty; raw source vẫn được kiểm. Callback/compare13:35–14:00, S14 notice.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S13 callback hoặc clock tới14:00; notices từ morning đã nhận. Một worker screen khóa, quầy hospital đổi biển quyền, tin hẹn biến mất theo closure đã xảy ra ở 11:00/11:30/12:30.

**CURIOSITY → ACTION:** Player trở lại cùng điện thoại/hành lang, thấy trạng thái vật khác lần trước; nếu Minh đã hỏi hộ, timestamp report có thể so. Player kiểm what actually closed, hỏi Minh phần cậu nói, chuyển ngay retained source còn thiếu cho Vũ hoặc chọn delay có card.

**DISCOVERY → RESPONSE:** Cửa access/willingness đóng riêng; copies ở phone Đức/police không biến mất. BARC chỉ từ actual received reports. Global command notice14:00 trước deadline17:00; acceleration chỉ nếu report, fresh warning và feasible save plan OT §0.1. NPC: Minh giảm nhẹ đúng payload đã gửi; Khải xử lý report thật, Lan/Nam không biết private note.

**SIGNATURE:** S14_RETURN_CHANGED: tái thăm các vật quen cho thấy hệ thống khép cửa bằng state thực, không chase. Micro events: Badge denied; phone vibration; đèn quầy off khi hết ca, không supernatural.

**PERSISTENCE / RETURN:** Actual access states và warning receipts; no baseline BARC=N3, no deletion of custody. Optional: C35–C37 conditional leak trace, không tạo proof giả. Return payoff: S18 causal attribution dùng earliest last-path loss, không dùng cảm giác phản bội.

**FAIL-FORWARD / EXIT:** Local locks không chặn professional copies; player vẫn chuyển nguồn đã giữ. 20m authored notices/action group tới14:20.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S14 notices xong14:20, Vũ đang intake/coordinate. Bàn nhận evidence có khay source với provenance và pending authentication; không bảng suspects.

**CURIOSITY → ACTION:** Một item giữ riêng trên phone Bắc đối chiếu được với khay police; dấu received chưa phải verified. Player chọn gửi bản gốc/custodian/contact và scope, có thể giữ lại, delay20m hoặc abandon khi actual N3 report.

**DISCOVERY → RESPONSE:** A đã Vũ giữ từ E28; B/C/X tăng chỉ sau receipt + independent checks; private N3 understanding không quyết định threshold. E38 actual baseline14:55 khi đủ raw/auth, không auto từ scene completion; custody-first cho command requests S16. NPC: Vũ tự request đủ scope đã biết, không đợi một accusation quiz.

**SIGNATURE:** S15_CUSTODY_DESK: thao tác phân nguồn gốc cụ thể thay cho lời thuyết phục Vũ. Micro events: Scan giấy, phone receipt, tem ngày/giờ; city outside continues.

**PERSISTENCE / RETURN:** Actual custody monotonic, E38 if threshold; ABANDON_AFTER_N3 only on explicit choice + received reports. Optional: Không cần private correct Khải/true boss inference. Return payoff: S16 professional collection chạy sau actual E38.

**FAIL-FORWARD / EXIT:** Thử lại provenance không cost; missing source thật đóng thì G1/G2/G5 theo cause. Intake/coordination tới15:00; S16 chỉ theo actual E38 hoặc partial path.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** Actual E38=t0 (baseline14:55), police mở source requests sau đó. Ba station nguồn: manager, original institution reply, broker annex; bản gốc L/H issue trước intake, không future record ở E28.

**CURIOSITY → ACTION:** Một stamp decision trên reply cho branch kia không giống statement manager; broker receipt có cùng directive scope. Player xem ba nguồn Vũ được phép hiển thị, so quyết định khác nhau và annex cùng case; không tự đi ép Hạnh/Nam.

**DISCOVERY → RESPONSE:** C32H+C33_AUTH hoặc C32K+C34_AUTH và C10_SOURCE_LINK exact D2. Original receiver-side Nam reply phải verify; X_COMMAND có thể sinh từ raw facts này. Request t0+5/+10/+15; receipts +25/+40 or45/+55; authentication/full match +75 baseline16:10, chỉ khi nguồn hợp tác và window mở. NPC: Vũ intake chuyên nghiệp; manager chỉ branch mình, broker chỉ received directive, Nam không đọc scene completion.

**SIGNATURE:** S16_THREE_ORIGINS: player đối chiếu manager firsthand, reply phía branch kia và source execution mà không trộn một forward làm ba chứng cứ. Micro events: Điện thoại báo receipt, printer annex nhả trang, bút ký custodial seal.

**PERSISTENCE / RETURN:** COMMAND C3/C4 chỉ từ raw verified/preserved; X normalize trước resolver; unavailable route có manager alternate. Optional: C31 contact chỉ lead, C30 history không gate. Return payoff: S17 Nam recontextualized, S18 consequence đúng source.

**FAIL-FORWARD / EXIT:** Mất Hùng dùng Khoa+logistics original; mất cả managers không record-only magic D1. Actual D verified nếu đủ; scene presentation tới16:25, no forced extra travel.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** Sau S16; optional về trọ16:25→17:00 hoặc bypass tới police/consequence. Hành lang S01 và góc sửa đồ vẫn thường; cửa phòng Nam chỉ mở với lý do đời thường được Lan/Nam mời hoặc trả món đồ.

**CURIOSITY → ACTION:** Radio rít nhẹ, một ổ điện lỗi làm chốt cửa kẹt; từ bàn có sổ ghi các mảnh “K. báo lại”, “MT giữ nguyên”, “117”. Nếu chọn vào, player thử tay nắm, gõ/gọi, xem đồ hợp lệ; giữ control, có thể rời khi chốt được Lan xử lý từ ngoài. Không bắt đọc sổ.

**DISCOVERY → RESPONSE:** Fragments là context/hypothesis, không Nam-boss proof; command chỉ từ S16 professional sources. Door jam do chốt cũ/điện, Lan nghe tiếng gõ hoặc chốt tự reset sau mechanic beat; không ba clue mở phép. Nam chỉ biết xáo trộn nếu trực tiếp thấy dấu cụ thể. NPC: Lan đi cầu thang rồi hỗ trợ; Nam về theo lịch, không telepathy; có thể không gặp.

**SIGNATURE:** S17_ROOM_JAM: 1–3 phút khám phá có lối thoát causal, player giữ quyền điều khiển; optional unsafe confrontation riêng. Micro events: Static radio, bước chân ngoài cửa, đèn buzz; môi trường phản hồi nhẹ nhưng có nguồn vật lý.

**PERSISTENCE / RETURN:** Door JAMMED→RELEASED vì latch reset/Lan; disturbed object flag chỉ nếu player thật sự chuyển vật và Nam nhìn thấy. Optional: Notebook fragments/C28; toàn bộ S17 có thể bỏ qua nếu custody đã an toàn. Return payoff: Epilogue vật cũ S01; encounter thay sắc thái theo knowledge, không thêm gate True.

**FAIL-FORWARD / EXIT:** Bỏ về trọ vẫn tới S18; nếu door jam, gõ/gọi hoặc chờ authored release không tốn missing-source window bất ngờ. Door released, optional conversation xong; đi police35m nếu cần, hoặc direct S18.

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

### Player-facing flow — playable sequence

**ENTRY / WORLD:** S16 actual command result hoặc S17 return/bypass; terminal only after real closure/committed exit. Police evidence tray và phone status đặt cạnh nhau, exterior Hà Nội vẫn tiếp tục; không gói clue mới.

**CURIOSITY → ACTION:** Một custody receipt hoặc warned source closure cuối hiện rõ trước khi player xác nhận bước tiếp. Player review provenance/source paths, chuyển item còn thiếu nếu window open; xác nhận exit hoặc nhìn timeline consequence.

**DISCOVERY → RESPONSE:** Outcome do CASE/X/COMMAND + earliest DECISIVE_LOSS/abandon, không suspect selection. Resolver P4 xử lý receipts trước closure; G6/G3/G5/G2/G4/G1 exhaustive. A/B/C police held stay held ở mọi cinematic. NPC: Vũ hành động trên proof thực; Nam/Khải chỉ phản ứng reports/custody họ có thể biết.

**SIGNATURE:** S18_TWO_TRAYS: cùng bố cục police tray và screen closure, nội dung/sound đổi theo phần thật đã giữ và nguyên nhân mất. Micro events: Printer seal, phone ngừng rung, ambience ngõ trở lại ở epilogue.

**PERSISTENCE / RETURN:** Ending ID and locked snapshot persisted once; no magically refreshed records. Optional: Optional old object epilogue không đổi proof. Return payoff: Mọi seed vật/âm từ S04/S14 được trả lại qua consequence.

**FAIL-FORWARD / EXIT:** Nếu còn last saving path, không resolve; cho player quay lại nguồn hợp lệ. Cinematic ngắn và ending screen sau confirmed terminal state.

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

### P4 handoff into the playable climax

At S16 police may authenticate a D1/D2/source-annex package in the same current case even if Khải risk remit is incomplete; this raw package itself establishes X_COMMAND before C4 is evaluated. Bắc sees the sourced scope Vũ may disclose, not an automatic notebook revelation. At S18 distinguish an **ongoing** weak route from a terminal one: A+B, A+C, B+C and ABC/X=false can still collect alternatives while windows remain open. At final lock they map G1 with exact preserved slots visible; ABCX with missing D maps G4; a documented earliest irreversible D-only MINH/DIRECT loss maps G2/G5. A later harmless attempt changes reaction, not outcome. C42 never retracts already received A/B/C.
