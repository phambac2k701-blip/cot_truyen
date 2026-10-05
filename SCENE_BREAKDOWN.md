# SCENE BREAKDOWN

> **Status:** STORY DESIGN — STAGE 7 / PRODUCTION BLUEPRINT  
> **Parent canon:** MASTER_GAME_BIBLE.md  
> **Stage 1:** BACKSTAGE_CRIME_TRUTH.md  
> **Stage 2:** CHARACTER_WEB.md  
> **Stage 3:** OBJECTIVE_TIMELINE.md  
> **Stage 4:** CLUE_GRAPH.md  
> **Stage 5:** PLAYER_STORY.md  
> **Stage 6:** ENDING_LOGIC.md  
> **Repository:** phambac2k701-blip/cot_truyen  
> **Setting:** Hà Nội, 2026  
> **Target focused run:** ~93 phút main route; ~95–105 phút strong/true route tùy mức inspect  
> **Design rule:** file này chia story đã khóa thành production scenes. Không thay objective truth, không thêm magic evidence, không viết full dialogue.

---

# 0. PRODUCTION PRINCIPLES

## 0.1. Scene identity

Giữ nguyên scene IDs S01–S18 từ PLAYER_STORY.md để tránh tạo hai hệ ID cho cùng một beat.

Mỗi scene là một đơn vị production có thể:

- load/reuse một hub;
- kích một nhóm authored events;
- cập nhật state;
- mở/đóng source window;
- lưu checkpoint;
- chuyển sang scene kế tiếp bằng travel/time transition.

Scene không đồng nghĩa một map riêng.

## 0.2. Hub / level plan

### HUB A — Trường và khu lân cận
Dùng cho S02, S03 và các đoạn đời thường ngắn về sau.

Core reusable spaces:
- lớp học;
- hành lang;
- bãi xe;
- quán ăn/điểm sinh viên;
- đầu đường/điểm đón xe.

### HUB B — Dãy trọ
Dùng cho S01, S05, S07, S17 và epilogue.

Core reusable spaces:
- phòng Bắc;
- hành lang;
- không gian chung;
- góc sửa đồ của Nam;
- khu bà Lan;
- lối ra ngõ.

Mục tiêu visual progression:
- S01: mới, bình thường;
- S05: quen thuộc;
- S07: nơi nghỉ và suy nghĩ;
- S17: cùng geometry nhưng tension hoàn toàn đổi do knowledge của player;
- epilogue: trở lại đời thường nhưng không còn vô nghĩa.

### SITE C — Tân Lộ
Không cần xây thành hub khổng lồ.

Dùng lại ở S04, S06, S08, S12, S13/S14 qua các phần khác nhau:
- quầy/dispatch;
- khu chờ worker;
- hành lang/văn phòng vận hành;
- một góc records/workstation có access hợp lệ.

Phần lớn Tân Lộ phải trông như công ty logistics thật.

### HUB C — Minh Trạch
Dùng cho S04 ở đầu nhận nếu phù hợp, S10, S13/S14.

Reusable spaces:
- sảnh;
- khu hành chính;
- hành lang;
- phòng compliance/meeting;
- không cần “dungeon bệnh viện”.

### POLICE MICRO-SET — tuyến của Vũ
Dùng cho S09, S11, S15, S18 bằng cùng một phòng tiếp nhận/phòng làm việc + phone calls.
Không cần xây sở cảnh sát lớn.

### HUB D / cơ sở bí mật
Không bắt buộc player phải vào trong run 90 phút.
Nếu dùng ở consequence cinematic, chỉ thể hiện qua exterior/brief authored shots.
Không biến climax thành raid do Bắc thực hiện.

## 0.3. Single authored clock / fast travel

OBJECTIVE_TIME/costs tại OT §0.1–0.2 là source duy nhất. UI/reading/inspect/private hypotheses/hints/retries0. Fixed dialogue groups khi commit, real travel và deliberate wait có visible cost/arrival; charged flags/clock/actual receipts persist save-load, không charge revisit lần hai. Load pre-event restores entire pre-event state, không giữ future evidence. A 5–15 second montage không phải objective travel cost. Cross-hub departures/arrivals dùng fixed bounds; local actual visit5–15m, không per footstep. No automatic exit from wall-clock idle.

| Main-route card | Fixed event/travel |
|---|---|
| S08 morning09:00–09:35 | Trọ→Tân Lộ30m; CORE_A25m→09:25 warning/read0, CORE_B10m→09:35; optional C18 copy10m→09:45 |
| S09 phone10:00–10:15 | Explicit wait to appointment; intake15m; truly new source lead5m each, max departure10:25 |
| S10 arrive10:50/55 | Travel30m; core20m, Thảo alternative10m→11:20/25 before local11:30 |
| S11 11:30–12:00; S12 12:30–13:00 | Explicit wait then compare30m; hospital→Tân Lộ30m; retained verify30m |
| S13 13:35–14:00 | Tân Lộ→hospital area30m+local micro-set5m; compare25m |
| S14 14:00–14:20; S15 14:20–15:00 | Notices20m, sourced intake/coordination40m; E38 baseline actual14:55 from source authentication |
| S16 15:00–16:25 | Professional requests/receipt offsets OT §0.2; full D actual16:10, group85m does not defer custody |
| Optional S17 after intake | Hospital-area→trọ35m to17:00, ordinary group15m; if return police35m to17:50, without required re-delivery |

Local willingness11:00/hospital11:30/finance12:30 are separate from global E40 LOCKED17:00. Actual accelerated report requires fresh warningW; global=max(16:30,W+145m) only if earlier17:00, canonical14:00 warning→16:30. Each last-needed-path warning must precede close with actual saving action still feasible: missing-source remote intake gồm ALL remaining authentication đủ actual E38 trong40m + professional D75m +buffer10m. Longer actual remainder phải qua OT §0.1 feasibility check hoặc giữ baseline17:00; receipt/queue không grant E38. Read time never consumes this opportunity. Police already holding source contacts/context collects proactively; a late personal scene cannot retime completed receipts. S08/S09/S10 warnings precede local losses; S14 is reinforcement/global notice, not the first warning after morning sources expired.

---

## 0.4. Puzzle policy

Puzzle chính là reasoning interaction, không phải mật mã arcade.

Các pattern được phép:
- đối chiếu timestamp;
- so version history;
- xếp authority chain;
- chọn source có provenance để bàn giao;
- xác định fact nào là direct observation và fact nào là interpretation.

Không có:
- hack database kiểu hacker;
- code dài;
- câu đố vô lý chặn evidence;
- một puzzle duy nhất khóa true ending.

Hint theo 3 cấp:
1. nhắc fact;
2. gợi vùng cần đối chiếu;
3. chỉ bước kế tiếp.

## 0.5. Dream sequence

Chỉ dùng **một micro-dream transition** cuối S07, khoảng 30–40 giây, nằm trong budget scene.

Chức năng:
- chuyển D0 → D+1;
- cho thấy anxiety của Bắc về việc bị đổ lỗi;
- remix những hình/âm thanh player đã thực sự thấy: field assignment, nhãn routing, tiếng scan, hành lang trọ.

Cấm:
- thêm fact mới;
- cho Nam xuất hiện như quỷ/villain;
- tiết lộ organ network;
- biến dream thành prophecy.

Nếu pacing test cho thấy dream làm nhịp quá “ma”, có thể bỏ mà không ảnh hưởng clue graph.

## 0.6. Cinematic policy

Cinematic ngắn và có chức năng:
- arrival/transition;
- đóng một beat tâm lý;
- thể hiện access closure;
- climax consequence.

Không dùng cutscene dài để NPC giải thích mystery.
Chase/physical danger nếu có chỉ là scripted beat ngắn ở late route xấu; không thay reasoning bằng action.

## 0.7. Fail-forward

Không scene nào game-over vì player suy luận sai một lần.

Private mistake/retry0. Actual new visits/waits/disclosures có fixed cost/report và có thể khiến source chưa received mất timely access sau prior warning. Source withdrawals, leaks và route consequences phải ghi causal event; không tự penalty từ interpretation.

Permanent last-needed-path loss chỉ xảy ra sau actual warning receipt BEFORE, saving action đủ authored cost và causal closure; gồm accelerated cleanup/broker channel.

---

# ACT I — ĐỜI SỐNG TRƯỚC KHI CÓ VỤ ÁN

## CHAPTER 1 — NGƯỜI MỚI

---

# S01 — PHÒNG TRỌ MỚI

## P5 PLAYABLE EVENT CONTRACT — S01

- **ENTRY CONDITION:** D0 07:30, Bắc nhận phòng trọ; Lan đang kiểm điện và đưa chìa.
- **ENVIRONMENTAL SETUP:** Hành lang có tiếng quạt, ổ điện chập chờn trong phòng Bắc, góc Nam sửa đồ nằm trong tầm nhìn nhưng không được đóng khung đáng ngờ.
- **CURIOSITY FUNNEL:** Đèn bàn chớp khi Bắc cắm ổ kéo; tiếng Lan gọi Nam từ hành lang.
- **PLAYER ACTION:** Player đặt vali, thử công tắc/ổ, mở cửa cho Nam; có thể liếc card cũ C28 hoặc đọc hợp đồng thuê.
- **PLAYABLE DISCOVERY:** Lỗi điện là việc thật; Nam giúp đúng nghề. C27 chỉ background; C28 optional không chứng minh current command.
- **AUTOMATIC EVENTS:** Lan đưa chìa sau khi Bắc nhận phòng; Nam tới vì lời Lan gọi, sửa ổ và về góc đồ.
- **MICRO EVENTS:** Tiếng quạt ngừng rồi chạy; điện thoại báo số dư/tiền trọ.
- **SIGNATURE / SET-PIECE EVENT:** S01_POWER_REPAIR: player giữ góc nhìn và thử điện trước/sau sửa, không cắt sang exposition.
- **NPC ROUTINE:** Lan kiểm công tơ; Nam tiếp tục sửa món khác nếu Bắc chưa ra.
- **WORLD STATE CHANGES:** Ổ chuyển FAULT→WORKING do Nam xử lý; đồ cũ vẫn ở đó, không tự xuất hiện.
- **OPTIONAL MISSED DETAIL:** C28/card Tân Lộ cũ và một cử chỉ tử tế C29.
- **RETURN / PAYOFF:** Khi S17 recontextualizes Nam, vật cũ vẫn chỉ là quan hệ nghề nghiệp.
- **FAIL-FORWARD:** Không xem card vẫn tới lớp; thao tác thử ổ có hint không tốn thời gian.
- **EXIT CONDITION:** Đồ được đặt, điện ổn, player xác nhận rời trọ 08:35.
- **IMPLEMENTATION HOOKS:** DoorInteractable, socket state, Nam route, phone balance, C27/C28 observation flags.


## VỊ TRÍ TRONG STORY
Opening / normal life. Production entry point của game.

## ESTIMATED PLAY TIME
~5 phút.

## LOCATION
HUB B — dãy trọ; phòng Bắc, hành lang, không gian chung, góc sửa đồ Nam.

## TIME / STATE
D0, 07:30–08:35; fixed core65m rồi travel25m→09:00.


## CHARACTERS PRESENT
Bắc, Trần Thị Lan, Vũ Đức Nam, 1–2 NPC nền không cần tên riêng.

## PLAYER ENTRY CONDITION
New Game.

## PRIMARY OBJECTIVE
Mang đồ vào phòng, nghe hướng dẫn sinh hoạt, xử lý một lỗi điện nhỏ, chuẩn bị đi học.

## NARRATIVE PURPOSE
- Cho player sống như Bắc trước khi điều tra.
- Establish khu trọ là “nhà”.
- Cho Nam xuất hiện tự nhiên trước khi ông biết gì về E22.
- Seed C27/C28/C29 mà không villain-code.

## PLAYER ACTIONS
- đi và nhìn quanh;
- đặt/inspect vài đồ cá nhân;
- nghe Lan hướng dẫn;
- thử quạt/ổ điện;
- tương tác với Nam khi ông sửa lỗi;
- mở điện thoại xem tin gia đình/số dư;
- optional inspect góc sửa đồ.

## REQUIRED EVENTS
1. Bắc nhận phòng.
2. Lan giải thích sinh hoạt.
3. Lỗi điện nhỏ xảy ra.
4. Nam giúp xử lý bình thường.
5. C27 được ghi như People note, không như evidence.
6. Bắc nhìn thấy áp lực tiền đủ để đặt motive.

## OPTIONAL EVENTS
- Inspect các vật đời thường.
- C28 ở góc sửa đồ.
- Hàng xóm nền.
- Một mẩu hội thoại Lan–Nam chứng minh họ quen lâu và bình thường.

## CLUES
- **Mandatory/progression:** C27 ở mức biography.
- **Optional:** C28.
- **Red herring:** không.
- **True-ending:** không; C27/C28 không được count D.
- **Delayed-value:** C27, C28, C29.
- **Noise:** phần lớn vật trong trọ.

## NPC INFORMATION
**Lan**
- Biết: Nam sống quanh đây lâu, nghề cũ chung chung, Bắc là người thuê mới.
- Nội dung nói: điện nước, cổng, sinh hoạt, chuyện Nam biết sửa đồ.
- Giấu: không plot secret.

**Nam**
- Biết: Bắc là sinh viên mới ở trọ.
- Nội dung nói: chuyện sửa điện, sinh hoạt, vài fact nghề cũ vô hại.
- Giấu: toàn bộ command role.
- Không được biết: E22/Bắc worker, vì chưa xảy ra.

## BACKSTAGE EVENTS
E19 đã xảy ra D−1.  
Khải audit Tân Lộ.  
Huyền giữ review.  
Vũ xử lý vụ Phúc.  
Không ai chờ Bắc xuất hiện.

## STATE CHANGES
- BARC giữ N0.
- People entries: Lan, Nam.
- C27_SEEN = true.
- C28_SEEN optional.

## BRANCHES
Không route ending.
Optional C28 chỉ ảnh hưởng recontextualization, không khóa gì.

## FAILURE / CONSEQUENCE
Không có fail. Nếu player bỏ inspect, game vẫn tiến.

## AUDIO ATMOSPHERE
Âm ngõ sáng, xe xa, tiếng chổi, cửa sắt, quạt/điện lạch cạch, giọng người ở trọ. Không nhạc ominous riêng cho Nam.

## CINEMATIC NOTES
First-person gần như toàn bộ.
Có thể dùng 2–3 giây authored camera khi Bắc đặt vali xuống và lần đầu nhìn căn phòng.
Không linger vào C28.

## TRANSITION OUT
Điện thoại báo giờ học → player rời ngõ → travel card/ngắn sang trường.

## REPLAY VALUE
Player biết Nam là command core nhưng thấy rõ:
- ông chưa hề chọn Bắc;
- việc giúp Bắc là thật;
- C27/C28 đã tồn tại nhưng không đủ buộc tội.

---

# S02 — BUỔI HỌC ĐẦU / NHỊP SINH VIÊN

## P5 PLAYABLE EVENT CONTRACT — S02

- **ENTRY CONDITION:** S01 rời trọ; tới trường 09:00.
- **ENVIRONMENTAL SETUP:** Bảng phòng học, ghế có ổ hỏng, file bài giảng và bảng thông báo việc làm trong một ngày bình thường.
- **CURIOSITY FUNNEL:** Linh chỉ chỗ ngồi có ổ điện; thông báo chi phí sáng màn hình, Minh đưa link công việc.
- **PLAYER ACTION:** Player tìm lớp, đổi chỗ, chụp bài hoặc nhận file; tự mở listing khi cần tiền.
- **PLAYABLE DISCOVERY:** Linh phân biệt thấy với đoán qua bài tập; Minh từng nhận ca thường C07 nếu hỏi/xem lịch sử được phép.
- **AUTOMATIC EVENTS:** Giờ học và bữa trưa tiến theo nhóm hành động đã định, không vì đọc UI lâu.
- **MICRO EVENTS:** Ổ cạnh ghế tắt; điện thoại rung bởi deadline lớp.
- **SIGNATURE / SET-PIECE EVENT:** S02_CLASS_ROUTINE: player tìm đúng phòng và chỗ học trong sinh hoạt đang diễn ra, áp lực tiền hiện qua thao tác điện thoại.
- **NPC ROUTINE:** Linh học, Minh đi ngang rồi nhắn link; không nhân vật nào biết crime.
- **WORLD STATE CHANGES:** Thông báo chi phí nằm lại trong phone; lớp tan và bảng việc vẫn có.
- **OPTIONAL MISSED DETAIL:** C07 lịch sử ca cũ, không là chứng cứ mạng lưới.
- **RETURN / PAYOFF:** S07 so ca bình thường với assignment mới.
- **FAIL-FORWARD:** Bỏ qua mọi thoại tùy chọn vẫn có link và lý do xem việc.
- **EXIT CONDITION:** Lớp/bữa trưa kết thúc 11:15; listing có thể mở.
- **IMPLEMENTATION HOOKS:** Class schedule, interactable seating, phone listing, optional C07.


## VỊ TRÍ TRONG STORY
Opening / social baseline.

## ESTIMATED PLAY TIME
~5 phút.

## LOCATION
HUB A — trường: hành lang, lớp, khu chung.

## TIME / STATE
D0, 09:00–11:15.  
E21 chuẩn bị hình thành.

## CHARACTERS PRESENT
Bắc, Nguyễn Ngọc Linh, Lê Gia Minh, sinh viên nền.

## PLAYER ENTRY CONDITION
S01 hoàn tất.

## PRIMARY OBJECTIVE
Tìm lớp, ổn định buổi học, làm quen bạn học, tính chuyện kiếm thêm tiền.

## NARRATIVE PURPOSE
- Neo trường vào đời sống.
- Establish Linh là nguồn đáng tin về fact nhưng không biết mystery.
- Establish Minh là bạn thật, không phải plant.
- Đưa Tân Lộ vào thế giới dưới dạng employer bình thường.

## PLAYER ACTIONS
- tìm phòng;
- chọn/chuyển chỗ;
- inspect lịch học/ảnh bài giảng;
- nói chuyện Linh/Minh;
- dùng phone;
- optional xem chat/job history.

## REQUIRED EVENTS
1. Linh và Minh được giới thiệu.
2. Bắc có một beat tiền/chi phí.
3. C01 xuất hiện.
4. Tân Lộ được frame như công ty logistics hợp pháp.

## OPTIONAL EVENTS
- C07 qua chat cũ/trao đổi.
- Các job part-time khác.
- Meme/deadline/đời sống sinh viên.

## CLUES
- **Mandatory:** C01.
- **Optional:** C07.
- **Red herring:** chưa.
- **True-ending:** không.
- **Delayed-value:** C07.
- **Noise:** nhiều job/quán/việc học không liên quan.

## NPC INFORMATION
**Linh**
- Biết: chuyện lớp, Bắc thiếu tiền ở mức bạn bè nếu Bắc nói.
- Nói: fact đời thường, phân biệt biết/đoán.
- Giấu: không plot secret.

**Minh**
- Biết: Tân Lộ có kênh part-time thật.
- Nói: đã từng/biết người nhận ca bình thường.
- Giấu: không gì ở thời điểm này.
- Không biết: core crime, Nam, Hùng/Khải thật.

## BACKSTAGE EVENTS
Khải tiếp tục audit.  
Tuấn chỉ biết nhóm job ưu tiên ở mức vận hành.  
Hùng tin reclassification có thể đi qua hệ thống thường.

## STATE CHANGES
- Trust baseline Linh high.
- Trust baseline Minh fairly high.
- C01 seen; C07 optional.
- Tân Lộ added to notebook as employer, không phải suspect.

## BRANCHES
Không route lock.

## FAILURE / CONSEQUENCE
Không.

## AUDIO ATMOSPHERE
Tiếng lớp, hành lang, ghế kéo, thông báo trường, xe ngoài cổng. Không tension music.

## CINEMATIC NOTES
Không cần cinematic; player control là ưu tiên.

## TRANSITION OUT
Tan lớp/ra khu ăn trưa; S03 bắt đầu ngay trong cùng HUB A.

## REPLAY VALUE
Minh giới thiệu job vẫn rõ ràng là hành động giúp bạn bình thường, bảo vệ fairness của betrayal sau này.

---

## CHAPTER 2 — MỘT CA NGẮN

# S03 — MỘT CA NGẮN

## P5 PLAYABLE EVENT CONTRACT — S03

- **ENTRY CONDITION:** S02 11:15, Bắc ở khu ăn sinh viên.
- **ENVIRONMENTAL SETUP:** Nhiều listing bình thường; ca TL-2604-117 có tiền nhỉnh hơn vì khung giờ và proof-of-handover.
- **CURIOSITY FUNNEL:** Minh chuyển link đúng lúc Bắc xem số dư; phone rung cạnh hóa đơn bữa ăn.
- **PLAYER ACTION:** Player so giờ học/tiền/đầu việc, chấp nhận ca hoặc do dự; không ai gọi chọn riêng Bắc.
- **PLAYABLE DISCOVERY:** C02 là assignment và nhóm khách y tế, chỉ bề mặt công việc.
- **AUTOMATIC EVENTS:** Nhận ca phát assignment; xác nhận di chuyển tính authored 34m nhóm và 35m tới Tân Lộ.
- **MICRO EVENTS:** Màn hình số dư; app báo hạn nhận ca.
- **SIGNATURE / SET-PIECE EVENT:** S03_JOB_ACCEPT: quyết định được đặt trong ngân sách và lịch học có thể xem, không lời độc thoại lý giải.
- **NPC ROUTINE:** Minh trở lại việc riêng, không theo player điều tra.
- **WORLD STATE CHANGES:** Assignment vào lịch sử; trạng thái job ACCEPTED một lần.
- **OPTIONAL MISSED DETAIL:** C07 đối chiếu ca cũ nếu đã xem.
- **RETURN / PAYOFF:** S07/S08 so lịch sử với routing của ca này.
- **FAIL-FORWARD:** Đã từ chối ban đầu vẫn có một lần nhận lại trong window; không rơi vào bế tắc.
- **EXIT CONDITION:** Job accepted; đi Tân Lộ theo travel card tới12:24.
- **IMPLEMENTATION HOOKS:** Phone job app, budget card, once-charge accept and travel.


## VỊ TRÍ TRONG STORY
Inciting incident.

## ESTIMATED PLAY TIME
~4 phút.

## LOCATION
HUB A — quán/khu sinh viên + phone UI.

## TIME / STATE
D0, 11:15–11:49 core34m; travel35m→12:24, check-in6m→12:30.


## CHARACTERS PRESENT
Bắc, Minh; nhân viên hỗ trợ Tân Lộ qua app nếu cần.

## PLAYER ENTRY CONDITION
S02 hoàn tất và beat tiền đã established.

## PRIMARY OBJECTIVE
Quyết định nhận ca Tân Lộ và đến điểm lấy hàng.

## NARRATIVE PURPOSE
Kéo Bắc vào sự cố vì tiền và timing, không vì định mệnh.

## PLAYER ACTIONS
- xem assignment;
- kiểm tra thời gian/lịch;
- xem số dư;
- accept job;
- optional đọc field chi tiết.

## REQUIRED EVENTS
1. Minh gửi/nhắc ca.
2. Player thấy reward và khung giờ hợp lý.
3. Job vào pool bình thường.
4. Bắc accept.
5. C02 xuất hiện ở mức raw field.

## OPTIONAL EVENTS
- So sánh với ca cũ của Minh.
- Một lựa chọn “để sau/nhận” chỉ thay nhịp vài chục giây; story reconverge nếu player muốn tiếp tục main route.

## CLUES
- **Mandatory:** C01, C02 seed.
- **Optional:** đọc kỹ C02 ngay.
- **Red herring:** không.
- **True-ending:** C02 hỗ trợ hiểu R1 nhưng không là slot độc lập.
- **Delayed-value:** C02.

## NPC INFORMATION
**Minh**
- Biết: job bình thường, trả khá.
- Nói: thông tin ca và kinh nghiệm công việc.
- Giấu: không.

## BACKSTAGE EVENTS
Job E19 đã bị Hùng hạ xuống luồng thường từ D−1. Không ai chỉ định Bắc.

## STATE CHANGES
- JOB_ACCEPTED = true.
- JOB_E22_SEEN = true.
- BARC vẫn N0.

## BRANCHES
Nếu player muốn bỏ job, game cho một beat xác nhận practical consequence và quay lại lựa chọn; đây chưa phải Neutral Ending G0 vì story chưa tới curiosity gate.

## FAILURE / CONSEQUENCE
Không fail vì đọc thiếu field.

## AUDIO ATMOSPHERE
Không khí trưa, quán ăn, phone vibration, tiếng đường phố.

## CINEMATIC NOTES
Không “zoom bí ẩn” vào assignment.

## TRANSITION OUT
First-time travel tới Tân Lộ; dùng short city montage/time card để establish khoảng cách.

## REPLAY VALUE
Player hiểu ca không phải bait được tạo cho Bắc; Hùng chỉ tạo điều kiện để hệ thống thường chọn bất kỳ worker phù hợp.

---

# S04 — GIAO XONG NHƯNG HƠI LỆCH

## P5 PLAYABLE EVENT CONTRACT — S04

- **ENTRY CONDITION:** Tân Lộ check-in12:24; pickup12:30 rồi tới đầu nhận.
- **ENVIRONMENTAL SETUP:** Quầy dispatch với nhiều gói thật, máy quét, printer, nhân viên bận; pouch kín đi qua luồng thường.
- **CURIOSITY FUNNEL:** Scanner báo mismatch nhẹ, nhãn routing có mép dán lại, giấy proof-of-handover ló khỏi khay.
- **PLAYER ACTION:** Player nhận pouch, giữ nguyên niêm, giao và xem lịch sử/biên nhận sau scan; có thể nhìn C04 nếu nhãn thực sự lộ.
- **PLAYABLE DISCOVERY:** C03 đầu nhận/account family; mismatch không phải bằng chứng crime, C04 chỉ từ vật/ảnh nhìn rõ nhãn.
- **AUTOMATIC EVENTS:** Nhân viên xử lý mã hợp lệ theo quy trình; Tuấn đi qua kiểm công việc khác, không chọn Bắc.
- **MICRO EVENTS:** Máy quét beep hai nhịp; printer kéo giấy; xe đẩy đi ngang.
- **SIGNATURE / SET-PIECE EVENT:** S04_SCAN_MISMATCH: player tự đưa gói vào scanner và thấy hai trường không khớp rồi nhân viên sửa bằng thao tác thường.
- **NPC ROUTINE:** Tuấn phân ca, đầu nhận xác minh, không ai giải thích conspiracy.
- **WORLD STATE CHANGES:** Job DELIVERED, C03 original13:52 lưu lịch sử; later observed_at khi player mở lại, không rewrite source time.
- **OPTIONAL MISSED DETAIL:** Dấu routing C04 và tiếng đầu nhận hỏi mã.
- **RETURN / PAYOFF:** S06 audit và S08 reclassification giải nghĩa mismatch.
- **FAIL-FORWARD:** Không inspect nhãn vẫn có biên nhận/history và audit.
- **EXIT CONDITION:** Proof-of-handover hoàn tất 13:52; đóng ca14:10.
- **IMPLEMENTATION HOOKS:** Scanner, printer, sealed pouch, receipt UI, persistent original/observed timestamps.


## VỊ TRÍ TRONG STORY
First anomaly.

## ESTIMATED PLAY TIME
~6 phút.

## LOCATION
SITE C — Tân Lộ → điểm nhận y tế/hành chính liên quan Minh Trạch.

## TIME / STATE
D0, 12:30–14:10.  
E22.

## CHARACTERS PRESENT
Bắc, Tuấn hoặc điều phối dưới Tuấn, nhân viên Tân Lộ vô tội, nhân viên đầu nhận vô tội.

## PLAYER ENTRY CONDITION
JOB_ACCEPTED.

## PRIMARY OBJECTIVE
Nhận gói, giao đúng địa điểm, lấy proof-of-handover.

## NARRATIVE PURPOSE
Cho player chạm mystery lần đầu nhưng chưa có crime proof.

## PLAYER ACTIONS
- đi tới quầy;
- nhận item;
- inspect label nếu muốn;
- theo authored travel transition;
- scan/bàn giao;
- ký/xác nhận;
- inspect receipt;
- xử lý một mismatch nhỏ ở đầu nhận.

## REQUIRED EVENTS
1. Tân Lộ hiện như business thật.
2. C02 được thể hiện trong assignment.
3. Bàn giao hoàn tất.
4. Scan/confirmation có mismatch classification nhỏ nhưng được xử lý bình thường.
5. E22_COMPLETE.

## OPTIONAL EVENTS
- C03 receipt/account family.
- C04 routing layer.
- C06 background job noise.
- Quan sát Tuấn bận xử lý nhiều việc thường.

## CLUES
- **Mandatory:** C02.
- **Optional:** C03, C04.
- **Red herring:** Tuấn có thể bắt đầu trông đáng chú ý chỉ vì vị trí.
- **True-ending:** C03 là transaction/group bridge lead, không tự X current risk authority; C04 không bắt buộc.
- **Delayed-value:** C02/C03/C04.
- **Noise:** C06.

## NPC INFORMATION
**Tuấn**
- Biết: đơn thuộc nhóm y tế/ưu tiên và quy trình vận hành.
- Nói: hướng dẫn worker, không giải thích core.
- Giấu: mức anh từng làm ngơ với ngoại lệ doanh nghiệp.
- Không biết: organ network, Nam.

**Nhân viên đầu nhận**
- Biết: procedure tại điểm nhận.
- Nói: classification hơi khác cách thường thấy.
- Giấu: không.

## BACKSTAGE EVENTS
E22 hoàn tất → E23 bắt đầu.  
Khải phát hiện job nhạy cảm đã đi qua pool thường.

## STATE CHANGES
- E22_COMPLETE = true.
- C03_SAVED optional.
- C04_SEEN optional.
- BARC sẽ chuyển N1 ở hậu trường sau audit, nhưng player không biết.

## BRANCHES
Không branch immediate.

## FAILURE / CONSEQUENCE
C03 intentional later inspect live history còn access cho same raw fields với observed_at mới; không early-save gate. C04 trực tiếp mất sau handover nếu chưa quan sát, nhưng có thể inspect retained authored label-visible photo; default seal-only photo không cho label fact.

## AUDIO ATMOSPHERE
Kho vận thật: xe kéo, scanner, điện thoại, tiếng máy in; đầu nhận y tế sạch, busy, không horror.

## CINEMATIC NOTES
Travel giữa Tân Lộ và đầu nhận dùng short montage, không lái xe tự do.
Không quay gói như “MacGuffin tội phạm”.

## TRANSITION OUT
Job complete → reward pending → player tự do rời về quán/trọ → S05.

## REPLAY VALUE
Những thứ “lỗi kho” ban đầu hiện rõ là sản phẩm của E19 nhưng không hề nói ra crime.

---

# S05 — ĂN TỐI, ĐỢI TIỀN, VỀ TRỌ

## P5 PLAYABLE EVENT CONTRACT — S05

- **ENTRY CONDITION:** S04 đóng ca, bữa ăn gần đầu nhận14:30; trở về trọ18:05.
- **ENVIRONMENTAL SETUP:** Quán ăn và phòng trọ sinh hoạt bình thường; thanh toán job còn PENDING.
- **CURIOSITY FUNNEL:** Phone đợi tiền và tin Linh; Nam trả món đồ điện hoặc Lan nhắc chỗ để đồ.
- **PLAYER ACTION:** Player chọn bữa rẻ, xem bài, đi về; có thể nhận món Nam sửa và đặt lại.
- **PLAYABLE DISCOVERY:** Nam tử tế trong chuyện nhỏ C29; khoản pending chưa phải dấu tội phạm.
- **AUTOMATIC EVENTS:** Bữa/việc học cho tới17:30 rồi travel về trọ; audit đến sau ordinary beat18:07.
- **MICRO EVENTS:** Âm quán ăn thay bằng tiếng ngõ; quạt phòng chạy; phone không báo tiền.
- **SIGNATURE / SET-PIECE EVENT:** S05_ORDINARY_RETURN: một đoạn thở do player điều khiển, căn phòng cũ thay âm và vị trí vật để tạo cảm giác sống.
- **NPC ROUTINE:** Nam sửa đồ, Lan làm việc nhà, không chất vấn Tân Lộ.
- **WORLD STATE CHANGES:** Vật đã sửa chuyển về phòng Bắc, payment PENDING; không tăng BARC.
- **OPTIONAL MISSED DETAIL:** Một câu nói đời thường của Nam/Lan.
- **RETURN / PAYOFF:** S17 cùng hành lang đổi nghĩa bằng hiểu biết player, không cần biến Nam thành quái.
- **FAIL-FORWARD:** Bỏ qua chuyện phụ không ảnh hưởng audit.
- **EXIT CONDITION:** Ordinary room beat xong 18:07, S06 notification.
- **IMPLEMENTATION HOOKS:** Ambient zone, repaired prop A/B, payment flag, authored meal/travel.


## VỊ TRÍ TRONG STORY
First breather.

## ESTIMATED PLAY TIME
~4 phút.

## LOCATION
Quán bình dân gần tuyến Minh Trạch→trọ + HUB B; không extra school trip.

## TIME / STATE
D0, 14:30–18:07; ordinary afternoon group180m, về trọ35m, last room beat2m.


## CHARACTERS PRESENT
Bắc, Lan, Nam, Linh qua chat/call, NPC quán.

## PLAYER ENTRY CONDITION
E22_COMPLETE.

## PRIMARY OBJECTIVE
Ăn, về trọ, chờ thanh toán, xử lý việc học/sinh hoạt.

## NARRATIVE PURPOSE
Cố tình cắt mystery; đồng thời tạo replay tension vì Nam đã biết worker E22 là Bắc.

## PLAYER ACTIONS
- mua/ăn đồ;
- trả lời Linh;
- xem bài;
- kiểm tra payment;
- về phòng;
- optional tương tác Nam/Lan.

## REQUIRED EVENTS
1. Payment còn pending.
2. Một beat đời thường với Lan hoặc Linh.
3. Nam xuất hiện ngắn và bình thường.
4. Không có clue lớn.

## OPTIONAL EVENTS
- Nam trả đồ đã sửa/giúp việc nhỏ.
- C29 được reinforce.
- Noise items ở phòng.

## CLUES
- **Mandatory:** không.
- **Optional:** không critical.
- **Red herring:** không.
- **True-ending:** không.
- **Delayed-value:** C29 characterization.
- **Noise:** nhiều.

## NPC INFORMATION
**Nam**
- Biết hậu trường: Bắc chính là worker E22, N1.
- Nói: chỉ chuyện đời thường.
- Giấu: việc đã biết E22 liên quan Bắc.
- Không được hỏi trúng clue.

**Lan/Linh**
- Không biết plot.

## BACKSTAGE EVENTS
E23: Khải chất vấn Hùng.  
E24: Nam nhận ra worker là Bắc.  
E25: Nam chọn quan sát.

## STATE CHANGES
- BARC N1 sau actual E23 audit/worker report tới Khải; Nam knowledge N1 sau E24 forwarding/receipt, không vì player hoàn tất scene.
- Player-facing state không thông báo.
- C29 reinforced.

## BRANCHES
Không.

## FAILURE / CONSEQUENCE
Không.

## AUDIO ATMOSPHERE
Quán ăn, xe ngoài ngõ, TV/radio xa, hành lang trọ. Nhạc nhẹ/không nhạc.

## CINEMATIC NOTES
Có thể dùng match cut từ receipt pending → điện thoại trên bàn trọ để nhấn đời thường tiếp diễn.

## TRANSITION OUT
Notification/call audit từ Tân Lộ → S06.

## REPLAY VALUE
Một trong các scene replay mạnh nhất: Nam biết Bắc là worker nhưng không biết Bắc hiểu gì, nên việc ông không “ra tay” là logic chứ không phải plot armor.

---

# ACT II — TÒ MÒ CÓ GIÁ

## CHAPTER 3 — JOB BỊ AUDIT

# S06 — JOB BỊ AUDIT

## P5 PLAYABLE EVENT CONTRACT — S06

- **ENTRY CONDITION:** Audit18:07 sau S05 ordinary beat.
- **ENVIRONMENTAL SETUP:** Trong phòng, job app bất ngờ yêu cầu đối lại thời gian/đầu nhận, payment giữ chờ.
- **CURIOSITY FUNNEL:** Phone rung hai lần; form hỏi field mà player vừa thấy scanner xử lý.
- **PLAYER ACTION:** Player mở history, so biên nhận, trả lời chỉ phần trực tiếp thấy; có thể gọi Tuấn theo option có cost.
- **PLAYABLE DISCOVERY:** Audit hướng tới routing; Tuấn phòng thủ trong giới hạn vận hành, không thú nhận hoặc đọc notebook.
- **AUTOMATIC EVENTS:** Form xác nhận sau S06 15m; explicit chờ kết quả tới20:00 hiển thị trước commit.
- **MICRO EVENTS:** Tin payment đổi trạng thái; tiếng khu trọ tiếp tục ngoài cửa.
- **SIGNATURE / SET-PIECE EVENT:** S06_AUDIT_FORM: player đối chiếu record thay cho nghe NPC kể toàn bộ lỗi.
- **NPC ROUTINE:** Tuấn đang xử lý audit khác; chỉ phản hồi câu hỏi có trong work ticket.
- **WORLD STATE CHANGES:** Payment HOLD, audit receipt; phone giữ original job history.
- **OPTIONAL MISSED DETAIL:** Một field scan bất thường đã quan sát ở S04.
- **RETURN / PAYOFF:** S07 curiosity bắt đầu từ bất nhất cụ thể.
- **FAIL-FORWARD:** Trả lời tối thiểu vẫn mở S07; không gây LEAK tự động.
- **EXIT CONDITION:** Đã xem form và chọn explicit wait tới20:00.
- **IMPLEMENTATION HOOKS:** Phone diff UI, audit flags, Tuấn response scope, once-charge wait.


## VỊ TRÍ TRONG STORY
Second anomaly.

## ESTIMATED PLAY TIME
~4 phút.

## LOCATION
HUB B phòng Bắc + phone; có thể optional short return/voice call với Tân Lộ.

## TIME / STATE
D0, 18:07–18:22 audit15m; explicit wait kết quả98m→20:00.


## CHARACTERS PRESENT
Bắc, Tuấn qua call/chat; Minh có thể nhắn.

## PLAYER ENTRY CONDITION
S05 complete.

## PRIMARY OBJECTIVE
Trả lời audit để lấy tiền và tránh bị quy lỗi.

## NARRATIVE PURPOSE
Biến “hơi lạ” thành câu hỏi thực tế: tại sao job bình thường bị soi kỹ vậy?

## PLAYER ACTIONS
- mở audit message;
- đối chiếu assignment;
- trả lời factual prompts;
- optional hỏi Tuấn;
- xem payment status.

## REQUIRED EVENTS
1. Audit nhắm đúng E22.
2. Tuấn yêu cầu đúng quy trình, không tự liên hệ khách.
3. Bắc nhận ra mức quan tâm của công ty cao hơn mong đợi.

## OPTIONAL EVENTS
- C05 nếu hỏi sâu.
- So lại C02.

## CLUES
- **Mandatory:** audit state.
- **Optional:** C05.
- **Red herring:** C05 hỗ trợ nghi Tuấn.
- **True-ending:** không.
- **Delayed-value:** C05 về sau được recontextualize.

## NPC INFORMATION
**Tuấn**
- Biết: job đang bị internal review; worker phải giữ quy trình.
- Nói: fact vận hành.
- Giấu: anh sợ bị làm scapegoat và từng làm ngơ ngoại lệ.
- Không biết core crime.

## BACKSTAGE EVENTS
Khải/Hùng đánh giá breach.  
Nam vẫn cho rằng curiosity chưa được chứng minh.

## STATE CHANGES
- TUAN_SUSPICION_SEEDED.
- BARC giữ prior value; probing chỉ nâng awareness khi exact hành vi/payload được report và Khải nhận. Private inspect/giữ copy không tự nâng BARC.

## BRANCHES
Không ending lock.

## FAILURE / CONSEQUENCE
Player trả lời “sai tone” không game-over; chỉ nội dung fact/source mới quan trọng.

## AUDIO ATMOSPHERE
Phòng trọ tối dần; quạt, tiếng ngõ; phone call khô, không nhạc thriller quá mạnh.

## CINEMATIC NOTES
Không cần cutscene.

## TRANSITION OUT
Audit đóng → player chủ động quyết định có kiểm tra thêm không → S07.

## REPLAY VALUE
Tuấn trông đáng ngờ vì đúng lý do nghề nghiệp, không vì game cố đánh lạc hướng bằng giả fact.

---

# S07 — BẮC CHỈ MUỐN BIẾT MÌNH ĐANG BỊ DÍNH VÀO CÁI GÌ

## P5 PLAYABLE EVENT CONTRACT — S07

- **ENTRY CONDITION:** 20:00, job audit đang chờ; lựa chọn early exit còn mở ở N1.
- **ENVIRONMENTAL SETUP:** Phòng yên, lịch sử ca Minh C07 và TL-2604-117 hiện trong app; hành lang vẫn sống.
- **CURIOSITY FUNNEL:** Hai dòng assignment có nhãn khác nhau; Minh nhắn hỏi đã nhận tiền chưa.
- **PLAYER ACTION:** Player đặt hai record cạnh nhau; hỏi Minh chung hoặc gửi exact screenshot/theory. Confirm stop nếu muốn G0.
- **PLAYABLE DISCOVERY:** Khác biệt ca không chứng minh crime; disclosure ledger chỉ ghi phần Bắc thật sự gửi.
- **AUTOMATIC EVENTS:** Nếu Minh hỏi hộ company, E26 chỉ sau actual message/report receipt; phone gửi không đồng nghĩa Khải/Nam biết ngay.
- **MICRO EVENTS:** Tin nhắn rung; đèn hành lang tắt theo giờ.
- **SIGNATURE / SET-PIECE EVENT:** S07_COMPARE_AND_CHOOSE: thao tác so ca rồi chọn kênh tin trước day transition.
- **NPC ROUTINE:** Minh trả lời theo thứ được hỏi; Lan khóa cổng, Nam không có magic awareness.
- **WORLD STATE CHANGES:** Disclosure payload hoặc NONE, BARC theo report thật; G0 chỉ nếu early stop đủ điều kiện.
- **OPTIONAL MISSED DETAIL:** C07 không bắt buộc, so tối thiểu từ field job app.
- **RETURN / PAYOFF:** S14 nếu có leak, timestamp report khớp cửa đóng, không auto betrayal.
- **FAIL-FORWARD:** Không so vẫn có audit cụ thể dẫn tới S08; early stop là lựa chọn rõ.
- **EXIT CONDITION:** Continue và explicit ngủ/chờ tới D+1 08:30, hoặc G0.
- **IMPLEMENTATION HOOKS:** Two-record compare UI, disclosure receipt ledger, early resolver, save at day transition.


## VỊ TRÍ TRONG STORY
Point of curiosity / early branch gate.

## ESTIMATED PLAY TIME
~5 phút, gồm micro-dream 30–40 giây nếu dùng.

## LOCATION
HUB B — phòng Bắc; phone/laptop.

## TIME / STATE
D0, từ20:00; contact group20m, genuinely new disclosure5m; explicit sleep/wait tới08:30 D+1, không private reading timer.


## CHARACTERS PRESENT
Bắc; Minh qua chat/call; Linh optional đời thường.

## PLAYER ENTRY CONDITION
Audit E22 đã rõ.

## PRIMARY OBJECTIVE
Kiểm tra mình có làm sai gì không và có bị công ty đẩy trách nhiệm không.

## NARRATIVE PURPOSE
Chuyển curiosity thành player agency.
Đặt Neutral route và betrayal seed.

## PLAYER ACTIONS
- so assignment với job cũ;
- hỏi Minh;
- chọn mức thông tin chia sẻ;
- inspect C02/C03 live history còn access hoặc retained entries; C04 từ actual observation/ảnh nhãn rõ, không seal-only photo;
- dùng laptop/notebook;
- chọn “thôi, không dính nữa” hoặc tiếp tục.

## REQUIRED EVENTS
1. C07 hoặc equivalent chứng minh Minh từng dùng kênh bình thường.
2. Player được một lựa chọn rõ về mức đào sâu.
3. Nếu tiếp tục, Bắc tạo ít nhất một hành vi vượt worker bình thường.
4. Save/day transition.

## OPTIONAL EVENTS
- Overshare screenshot/theory cho Minh.
- Linh nhắn chuyện học.
- Micro-dream transition.

## CLUES
- **Mandatory:** C07 ở mức fair correction nếu Minh later leaks.
- **Optional:** C35/C36 chỉ tồn tại nếu player tạo điều kiện.
- **Red herring:** Minh có thể bị hiểu là plant nếu player bỏ qua C07.
- **True-ending:** không.
- **Delayed-value:** C07; C35 nếu leak.
- **Noise:** chat học tập.

## NPC INFORMATION
**Minh**
- Biết: job channel, những gì Bắc tự nói cho cậu.
- Nói: muốn dập chuyện, có thể đề nghị hỏi “người phụ trách”.
- Giấu: nếu đã liên hệ Tân Lộ, có thể giảm nhẹ mức đã nói.
- Không biết network.

**Linh**
- Chỉ neo đời sống, không đưa theory plot.

## BACKSTAGE EVENTS
E27 Huyền giữ review.  
E28 Vũ kiểm chứng Phúc.  
Nếu player đào: E29 rồi E30.  
Nếu overshare: E26.

## STATE CHANGES
- BARC N1→N2 chỉ nếu report exact disclosed/witnessed probing đã tới recipient, ghi received_at; private reading/inference không đổi awareness.
- MINH_LEAK possible.
- Nếu bỏ sớm đúng điều kiện: arm G0 Neutral.

## BRANCHES
- **G0 Neutral** nếu player chủ động dừng ở N1, không leak, không chạm cell thứ hai.
- Continue main route nếu chọn kiểm tra.
- Overshare mở causal possibility G2 later, chưa auto-lock.

## FAILURE / CONSEQUENCE
Không có “sai câu thoại = bad ending”.
Leak chỉ thành route xấu nếu nó thực sự làm alternate/source cuối gãy.

## AUDIO ATMOSPHERE
Đêm trọ, xe thưa, tiếng phòng bên, laptop fan.
Micro-dream dùng scan beep/tiếng giấy/âm môi trường đã nghe, không jumpscare.

## CINEMATIC NOTES
Dream nếu dùng: abstract, 30–40 giây, không new info.
Kết bằng alarm/ánh sáng sáng D+1.

## TRANSITION OUT
D0 → D+1.  
Nếu continue: S08.  
Nếu G0: short epilogue “Một Ca Làm Thêm”.

## REPLAY VALUE
Player hiểu chính việc mình chọn đào sâu mới biến Bắc từ accidental exposure thành risk; Nam không “định sẵn” cuộc đối đầu.

---

# S08 — JOB KHÔNG “TỰ NHIÊN” LỌT VÀO POOL

## P5 PLAYABLE EVENT CONTRACT — S08

- **ENTRY CONDITION:** D+1 09:00 Tân Lộ; xử lý payment/incident hợp lệ.
- **ENVIRONMENTAL SETUP:** Máy printer và terminal dispatch mở cùng job; Đức cầm bản snapshot cá nhân; notice đóng worker access11:00.
- **CURIOSITY FUNNEL:** Printer trả một bản Internal/Priority cũ trong khi app hiển thị Standard; Đức chú ý Bắc nhìn thấy.
- **PLAYER ACTION:** Player so bản in C17 với assignment, hỏi quyền classification; 09:35 có thể nhận C18 copy từ Đức trong10m hoặc giữ contact/deadline đưa Vũ.
- **PLAYABLE DISCOVERY:** E19 reclassification D−1 bởi tầng trên Tuấn; không suy từ pattern rằng Đức biết organ crime.
- **AUTOMATIC EVENTS:** Warning09:25 trước closure; Đức offer copy thực tế từ09:30, không chờ scene S12.
- **MICRO EVENTS:** Printer feed; badge beep; worker app quyền truy cập đổi màu ở giờ đóng.
- **SIGNATURE / SET-PIECE EVENT:** S08_PRINT_COMPARE: player tự đặt bản Internal và Standard song song trong khoảng cửa còn mở.
- **NPC ROUTINE:** Đức tránh lộ danh tính nhưng giữ private phone copy; Tuấn vận hành không tự reclassify.
- **WORLD STATE CHANGES:** C17 observed, C18 local receipt09:45 nếu chọn; notice và contact tồn tại đến11:00.
- **OPTIONAL MISSED DETAIL:** Bounded finance lead Yến; alternate police route nếu không nhận trực tiếp.
- **RETURN / PAYOFF:** S09 Vũ bắt đầu requests từ actual group/contact, S12 verify retained copies.
- **FAIL-FORWARD:** Không nhận C18 vẫn có scoped contact và C19 alternate; local lock không erase copy.
- **EXIT CONDITION:** Core09:35, optional copy09:45; explicit hẹn S09 10:00.
- **IMPLEMENTATION HOOKS:** Versioned document UI, printer, source availability/warning, C18 custody.


## VỊ TRÍ TRONG STORY
First real connection.

## ESTIMATED PLAY TIME
~6 phút.

## LOCATION
SITE C — Tân Lộ, kênh khiếu nại/worker records.

## TIME / STATE
D+1, 09:00–09:35 core35m; optional direct C18 copy10m→09:45; explicit hẹn police10:00.


## CHARACTERS PRESENT
Bắc, Tuấn, nhân viên vận hành; Đức actual morning limited source offer/contact.

## PLAYER ENTRY CONDITION
Player chọn tiếp tục sau S07.

## PRIMARY OBJECTIVE
Giải quyết payment/audit và xác định job đã bị đổi classification hay không.

## NARRATIVE PURPOSE
Chuyển mystery từ cảm giác sang fact có chủ ý: R1.

## PLAYER ACTIONS
- yêu cầu xem lịch sử assignment hợp lệ;
- so C02/C04 với log;
- puzzle nhẹ: align “current class” với previous state/timestamp;
- hỏi authority chain;
- optional quan sát Đức/C21.

## REQUIRED EVENTS
1. C17 được mở trên main route hoặc một equivalent recoverable route.
2. Player thấy reclassification xảy ra trước Bắc.
3. C20 cho thấy Tuấn không có authority tạo reclassification.
4. C22 được seed/đặt hướng lên Hùng.
5. Required notice09:25: worker/Đức11:00, finance12:30; actual Đức offer/contact từ09:30. Có copy10m→receipt09:45 hoặc actual contact/copy/deadline cho police collection10:35; bounded Yến lead cho10:50 actual receipt. Warning trước lựa chọn tiết kiệm hoặc deliberately delay.

## OPTIONAL EVENTS
- C21.
- Actual C18 direct copy09:35–09:45 (10m), hoặc retain source address/contact để share S09; không late pickup after11:00.
- Nếu leak từ S07, một phần access đã khó hơn.

## CLUES
- **Mandatory:** C17, C20.
- **Optional:** C21.
- **Red herring:** Tuấn bắt đầu được correction; Hùng thành suspect hợp lý.
- **True-ending:** C17 là core slot C; C22 cần được hoàn thiện.
- **Delayed-value:** payoff C02/C04.
- **Noise:** records/job bình thường.

## NPC INFORMATION
**Tuấn**
- Biết: authority chain trong Tân Lộ.
- Nói: classification không do mình đổi; quy trình operation.
- Giấu: mức đã làm ngơ.
- Không biết mục đích organ network.

**Đức**
- Nếu xuất hiện: biết Hùng đã sửa dấu và có bất thường leadership-level.
- Chưa exposition toàn bộ.

## BACKSTAGE EVENTS
Khải siết access.  
Đức biết cửa sổ tự bảo hiểm sắp đóng.  
Ba hệ thống E31 vẫn vận động.

## STATE CHANGES
- R1_CONFIRMED.
- C17 acquired/preserved locally.
- TUAN_NOT_RECLASSIFIER nếu actual C20 chỉ đúng origin/authority; chưa cấp core-scope verdict từ permission hoặc private innocence answer.
- BARC N2 chỉ khi received reports xác nhận probing; visible action chưa được report tới Nam không tự cấp knowledge Nam.

## BRANCHES
Nếu C17 access bị hạn chế do leak, route recover qua Đức/Vũ vẫn tồn tại nhưng tốn timing.

## FAILURE / CONSEQUENCE
Sai puzzle không mất clue; hint tăng dần.
Wrong inference/reading/hint0. Confirm extra Tuấn appointment+15m (5m move+10m talk) hoặc Hùng wait+30m mới tăng clock, với cost/finish/deadline notice và saving source-share action trước confirm. Existing police custody không lùi.

## AUDIO ATMOSPHERE
Office business ambience. Khi reveal C17, không sting “villain”; dùng sound focus nhẹ.

## CINEMATIC NOTES
Không cutscene reveal. Fact phải được player đọc/đối chiếu.

## TRANSITION OUT
Bắc giờ có source cụ thể đủ để báo → S09.

## REPLAY VALUE
C17 làm rõ toàn chuỗi E19 nhưng vẫn không nói tội gì đang xảy ra.

---

# ACT III — BA HỘP SỰ THẬT

## CHAPTER 4 — TỪ MỘT JOB TỚI MỘT VỤ VIỆC

# S09 — LẦN ĐẦU BẮC CÓ THỨ ĐỦ CỤ THỂ ĐỂ BÁO

## P5 PLAYABLE EVENT CONTRACT — S09

- **ENTRY CONDITION:** S08 C17/source lead và lịch hẹn phone Vũ 10:00.
- **ENVIRONMENTAL SETUP:** Bắc đứng ở Tân Lộ; trên phone có assignment, receipt và bản in; Vũ ở đầu dây trong micro-set.
- **CURIOSITY FUNNEL:** Tin hẹn từ Vũ và trường đầu nhận Minh Trạch khiến cuộc gọi có mục tiêu.
- **PLAYER ACTION:** Player chọn gửi original record/contact/group/deadline và phân loại thấy hay suy; optional disclose lead mới có 5m cost.
- **PLAYABLE DISCOVERY:** Vũ đã có vụ Phúc A=2 từ E28; anh hỏi raw scope, không kể toàn vụ; request B/C khởi từ actual payload.
- **AUTOMATIC EVENTS:** C17/group payload receipt10:15; Vũ contact Đức10:25/receipt10:35 nếu đủ contact và tự request hospital review khi group có.
- **MICRO EVENTS:** Phone ring; message acknowledgment; tín hiệu office nền.
- **SIGNATURE / SET-PIECE EVENT:** S09_SCOPED_INTAKE: player gửi source có timestamp và thấy police receipt tách khỏi queued query.
- **NPC ROUTINE:** Vũ làm việc song song, không đợi Bắc đi từng nơi; Nam không nghe private call.
- **WORLD STATE CHANGES:** Police custody mới chỉ cho actual received/authenticated sources; warnings hospital11:30/finance12:30.
- **OPTIONAL MISSED DETAIL:** C18/C19 scoped leads có thể gửi trong kênh hợp lệ.
- **RETURN / PAYOFF:** S10 review và S12 C22 matched từ đúng request sáng.
- **FAIL-FORWARD:** Chậm disclosure dùng q-relative receipts, không backdate; police A vẫn an toàn.
- **EXIT CONDITION:** Cuộc gọi15m hoàn tất, travel hospital30m tới10:50/10:55.
- **IMPLEMENTATION HOOKS:** Phone source-selection, receipt ledger, parallel police timers, q-relative schedule.


## VỊ TRÍ TRONG STORY
Police entry.

## ESTIMATED PLAY TIME
~5 phút.

## LOCATION
Phone appointment tại Tân Lộ; existing police micro-set only later, không morning physical police trip.

## TIME / STATE
D+1, 10:00–10:15 phone intake15m; new source disclosures5m each nếu cần, depart10:20/10:25.


## CHARACTERS PRESENT
Bắc, Đại úy Nguyễn Minh Vũ. Phúc chưa cần xuất hiện trực tiếp.

## PLAYER ENTRY CONDITION
Có C17/equivalent source cụ thể.

## PRIMARY OBJECTIVE
Trình bày fact có nguồn thay vì theory.

## NARRATIVE PURPOSE
Đưa police vào sớm và có năng lực.

## PLAYER ACTIONS
- chọn records muốn trình;
- provenance interaction: “tôi thấy trực tiếp / log công ty / suy đoán”;
- nghe Vũ đặt câu hỏi timeline;
- bàn giao/copy source hợp lệ.

## REQUIRED EVENTS
1. Vũ phân biệt fact với inference.
2. C10/C11A được mở ở mức cần thiết.
3. Player được xem phần hồ sơ hợp lệ: A đã authenticate/preserve E28, không chờ cậu giao lại chronology.
4. Actual C17/group payload received10:15. Enough C18 contact/copy/deadline in this payload khiến Vũ tự contact10:25/receive10:35; không đợi second request click.
5. Chỉ genuinely new missing source address/context có disclosure5m; bounded Yến lead actual contact10:40/receipt10:50. Query hospital group10:15→originals11:10; prior narrow visit confirmation vẫn riêng.
6. Source acknowledgments nêu hospital11:30/finance12:30 trước departure; queue≠received≠auth.
7. q-late formulas OT §0.1 apply actual contact/receipt/check times; no retroactive10:35/10:50 from a late query. Once collection started, personal travel/delay không retime it.

## OPTIONAL EVENTS
- Hỏi thêm về Phúc; Vũ giữ boundary.
- C42 foreshadow qua intake/provenance; genuinely new source disclosure5m, không re-delivery nguồn đã trong payload.

## CLUES
- **Mandatory:** C10, C11A.
- **Optional:** C08 chưa bắt buộc ở scene này.
- **Red herring:** Vũ không xác nhận Tuấn/Huyền chỉ vì chức vụ.
- **True-ending:** C08+C10 đã authenticate/preserve ở E28; S09 mở player observation/intake bridge còn thiếu, không initial A custody.
- **Delayed-value:** C11A payoff “crisis predates Bắc”.

## NPC INFORMATION
**Vũ**
- Biết: A=2 từ E28 exact originals Phúc/counterpart + independent visit confirmation; trước Bắc đã narrow-query hospital và đang verify. Chưa biết group/Tân Lộ/risk X/Nam D nếu chưa có sources.
- Nói: chỉ những gì đã verify.
- Giấu: chi tiết nghiệp vụ/danh tính chưa nên chia.
- Không biết: Nam, full Tân Lộ network.

## BACKSTAGE EVENTS
Vũ tiếp tục investigation E12/E28 và test group/logistics bridge mới; prior narrow visit/request confirmation không chứa multi-case review scope. C03/C17 cho group/account/routing lead để hỏi Huyền đúng scope; không chờ Bắc mới hỏi hospital.
Organization không tự biết Bắc đã nói gì nếu không có observable consequence.

## STATE CHANGES
- POLICE_CONTACT = true.
- CASE.A=2 từ E28 giữ nguyên; A_PLAYER_SEEN/UNDERSTOOD riêng theo fields/inference được chia.
- Source delivered có actual custodian/received_at/authentication; đủ raw risk context cho Vũ verify dù private inference sai.
- Organization chỉ biết exact report thật sự received, không auto police-contact leak.

## BRANCHES
Player có thể kể theory dài nhưng Vũ chỉ dùng sourced facts.
Không branch ending trực tiếp.

## FAILURE / CONSEQUENCE
Nếu player chỉ mang suy đoán, Vũ không mở rộng; main route yêu cầu sourced bridge và fail-forward cho player quay lại source.

## AUDIO ATMOSPHERE
Không gian cơ quan yên, tiếng giấy/bàn phím/điện thoại. Nhịp bình tĩnh, tạo cảm giác chuyên nghiệp.

## CINEMATIC NOTES
No police montage heroic. Camera first-person, Vũ hỏi ngắn.

## TRANSITION OUT
Vũ xác nhận cần kiểm tra Minh Trạch → contextual fast travel S10.

## REPLAY VALUE
Vũ đã làm đúng từ đầu; replay loại trope “police ngu để plot tồn tại”.

---

# S10 — MINH TRẠCH KHÔNG CHỈ CÓ MỘT LỖI

## P5 PLAYABLE EVENT CONTRACT — S10

- **ENTRY CONDITION:** S09 xong; hospital arrival10:50/10:55, notice review11:30.
- **ENVIRONMENTAL SETUP:** Quầy Huyền có khay form hai version; hành lang công khai, không vào phòng hạn chế.
- **CURIOSITY FUNNEL:** Printer nhả bản scope thu hẹp, version cũ còn ở khay được phép xem khi Vũ đã request đúng nhóm.
- **PLAYER ACTION:** Player so consent và review tại quầy theo quyền cho phép; có thể hỏi Thảo về phần bà trực tiếp xử lý nếu C12 thiếu.
- **PLAYABLE DISCOVERY:** C11 discrepancy về money/withdrawal; C12 receipt Khoa biết và vẫn giữ consent, hoặc C15 firsthand cùng case. Huyền không tự biết cả mạng.
- **AUTOMATIC EVENTS:** Vũ nhận originals11:10, authenticate11:20 nếu actual request; optional Thảo10m tới11:20/11:25.
- **MICRO EVENTS:** Hành lang bớt tiếng khi cửa khép; máy in và bánh xe đẩy.
- **SIGNATURE / SET-PIECE EVENT:** S10_FORM_VERSION: player tự đối chiếu hai version; nhân viên chỉ phản ứng đúng phần đã hỏi.
- **NPC ROUTINE:** Huyền tiếp bệnh án hợp pháp; Thảo chỉ có mặt trong window, Khoa ở cell riêng.
- **WORLD STATE CHANGES:** Document version/scope hiển thị; police B chỉ tăng sau original fact/authentication; local11:30 không erase receipt.
- **OPTIONAL MISSED DETAIL:** C15 alternative; C14 framing chỉ hỗ trợ suspicion.
- **RETURN / PAYOFF:** S11 thời điểm review D−12 đặt bên cạnh Phúc/job.
- **FAIL-FORWARD:** Không gặp Thảo khi C12 đủ vẫn sống; nếu source cuối mất, warning đã có và G1 sau closure.
- **EXIT CONDITION:** Core11:10/11:15, optional11:20/11:25; S11 quiet point11:30.
- **IMPLEMENTATION HOOKS:** DocumentCompare, NPC bounded testimony, receipt/auth, version state.


## VỊ TRÍ TRONG STORY
Hospital layer / second box.

## ESTIMATED PLAY TIME
~6 phút.

## LOCATION
HUB C — Minh Trạch, sảnh + compliance room.

## TIME / STATE
D+1, arrive10:50/10:55; core20m→11:10/11:15, Thảo alternative10m→11:20/11:25 before11:30.


## CHARACTERS PRESENT
Bắc, Vũ, Hoàng Huyền, Lâm Thảo; Khoa có thể bề mặt.

## PLAYER ENTRY CONDITION
Police bridge S09 mở hospital verification.

## PRIMARY OBJECTIVE
Xác minh liệu Minh Trạch có pattern thật hay chỉ là một mismatch đơn lẻ.

## NARRATIVE PURPOSE
Tạo independent box B và red herring Huyền hợp lý.

## PLAYER ACTIONS
- đi qua bệnh viện bình thường;
- nghe Huyền đặt boundary access;
- inspect version/scope history nếu được chia;
- puzzle nhẹ: compare creation timestamp vs later scope;
- optional talk Thảo trong phạm vi hợp lý.

## REQUIRED EVENTS
1. C11: Huyền đã mở review nhiều hồ sơ từ D−12.
2. Player hiểu review predates E22.
3. Có dấu quản trị can thiệp sau review.
4. Hospital vẫn hiện đa số hoạt động bình thường.
5. Required entrance notice10:50/10:55 nêu channel11:30 trước core20m/Thảo10m. Actual police C11/C12 receipt11:10, checked11:20; selected Thảo receipt11:20/11:25 còn feasible. Received copies survive local scope lock.

## OPTIONAL EVENTS
- C12.
- C13 red herring.
- C14/C15 route Thảo.
- C16.
- C16A noise.

## CLUES
- **Mandatory:** C11.
- **Optional:** C12, C14, C15, C16.
- **Red herring:** C13 → Huyền trông như đang che.
- **True-ending:** B cần C11 + C12 hoặc C15.
- **Delayed-value:** DV5 / timestamp review.
- **Noise:** C16A.

## NPC INFORMATION
**Huyền**
- Biết: pattern compliance, review history.
- Nói: fact trong scope.
- Giấu: không conspiracy; chỉ giữ dữ liệu đúng quy trình.
- Không biết Nam/Tân Lộ.

**Thảo**
- Biết: một số case có hoàn cảnh ngoài hồ sơ không sạch.
- Nói: chỉ phần trực tiếp biết nếu trust/pressure hợp lý.
- Giấu: mức complicity và self-rationalization.
- Không biết Nam.

**Khoa**
- Biết: hospital cell và risk.
- Nói bề mặt quy trình.
- Giấu: đã thu hẹp review/báo thiếu.

## BACKSTAGE EVENTS
Khoa tự bảo vệ.  
Nam chỉ nhận báo cáo đã lọc qua Khải.  
E33 window đang hẹp.

## STATE CHANGES
- B_HOSPITAL_PATTERN possible/proven.
- HUYEN_FALSE_THEORY can open/correct.
- Source B flags.

## BRANCHES
- Nếu C12 miss, C15 là alternate.
- Nếu cả hai miss và window đóng, G1 Delay risk tăng.

## FAILURE / CONSEQUENCE
Không hack hồ sơ.
Player đến quá muộn có thể mất scope access nhưng institutional history không “biến mất”; police route sau game vẫn có thể tiếp tục.

## AUDIO ATMOSPHERE
Bệnh viện hoạt động thật: loa nhẹ, xe đẩy, điều hòa, footsteps; tension đến từ phòng compliance yên hơn, không horror.

## CINEMATIC NOTES
Khoa nếu xuất hiện chỉ qua một interruption ngắn/doorway beat, không villain introduction.

## TRANSITION OUT
Vũ hẹn đối chiếu timeline/source → S11.

## REPLAY VALUE
Huyền từ “người giữ hồ sơ đáng ngờ” trở thành một trong những người vô tội quan trọng nhất.

---

# S11 — CHUYỆN NÀY CÓ TRƯỚC MÌNH, VÀ LỚN HƠN MỘT JOB

## P5 PLAYABLE EVENT CONTRACT — S11

- **ENTRY CONDITION:** S10 trong hospital area, quiet point11:30.
- **ENVIRONMENTAL SETUP:** Ba timeline cards là raw timestamps: Phúc, Huyền, E19 job; điện thoại của Bắc đặt cạnh police scoped summary.
- **CURIOSITY FUNNEL:** Tin Vũ chứa một timeline field mới; ngày D−12 nổi khác với D−1 của job.
- **PLAYER ACTION:** Player kéo/đặt đúng thứ tự ba bản gốc; có thể xem exact A content ở mức Vũ cho phép, không giao lại A.
- **PLAYABLE DISCOVERY:** Vụ Phúc/review có trước Bắc; C03 client family đổi nghĩa khi so provenance, không phải nguyên nhân crime.
- **AUTOMATIC EVENTS:** Vũ nhận ý kiến qua phone; A đã custody E28 không phụ thuộc player drag đúng.
- **MICRO EVENTS:** Âm bút gạch thời gian; phone hạ âm khi mở document.
- **SIGNATURE / SET-PIECE EVENT:** S11_TIME_COMPARE: player tự xếp nguồn theo time, một inference về vị trí Bắc trong cleanup.
- **NPC ROUTINE:** Vũ tiếp tục professional match, Phúc chỉ biết chuyện mình.
- **WORLD STATE CHANGES:** Private inference nếu đúng mới ghi; CASE không bị hạ vì xếp sai.
- **OPTIONAL MISSED DETAIL:** C09 hỗ trợ chronology, không là gate A.
- **RETURN / PAYOFF:** S12 false apex có thể được bác bằng thứ tự E19/assignment.
- **FAIL-FORWARD:** Sai xếp vẫn có raw records để xem lại miễn phí; progression không đòi quiz.
- **EXIT CONDITION:** Compare/wait tới12:00; travel Tân Lộ30m tới12:30.
- **IMPLEMENTATION HOOKS:** Timeline UI, source provenance, private inference flag, zero-cost retry.


## VỊ TRÍ TRONG STORY
Midpoint.

## ESTIMATED PLAY TIME
~5 phút.

## LOCATION
POLICE MICRO-SET hoặc quiet public meeting point gần hospital.

## TIME / STATE
D+1, 11:30–12:00 compare30m; no second police trip; travel Tân Lộ30m→12:30.


## CHARACTERS PRESENT
Bắc, Vũ; Phúc optional/controlled.

## PLAYER ENTRY CONDITION
Có logistics anomaly + hospital pattern.

## PRIMARY OBJECTIVE
Đặt các nguồn cạnh nhau và xác định chronology.

## NARRATIVE PURPOSE
Mental-model flip: Bắc bước vào một cleanup đã có trước.

## PLAYER ACTIONS
- timeline board/notebook authored interaction;
- xếp ba timestamp theo thứ tự;
- phân loại direct source / corroboration;
- optional nghe Phúc xác nhận withdrawal.

## REQUIRED EVENTS
1. Phúc timeline predates E22.
2. Huyền review predates E22.
3. E19/E22 đến sau.
4. Player có cơ hội hiểu R2.
5. Notebook giữ facts nhưng không auto-write “network”.

## OPTIONAL EVENTS
- C08 direct withdrawal.
- C09 omission/context.
- C03 payoff nếu inspect sớm hoặc muộn từ live history còn access; raw fields/original time như nhau.

## CLUES
- **Mandatory:** C10/C11A + C11 chronology.
- **Optional:** C08, C09, C03 payoff.
- **Red herring:** RH5 Phúc có thể trông không hoàn hảo.
- **True-ending:** A content/authentication C08+C10 đã giữ từ E28; player chưa được xem C08 chỉ thiếu understanding, không mất institution custody.
- **Delayed-value:** C03, DV4, DV5 payoff.

## NPC INFORMATION
**Phúc**
- Biết: mình đồng ý ban đầu, muốn rút, bị pressure, đã kiểm tra hospital.
- Nói: chronology trực tiếp.
- Giấu/omits: phần xấu hổ/tiền ban đầu nếu chưa trust.
- Không biết Tân Lộ/Nam.

**Vũ**
- Biết: ba timeline có thể liên quan nhưng chưa được phép tự nhảy tới network nếu bridge thiếu.

## BACKSTAGE EVENTS
E32–E35 source windows chạy song song.  
Đức/Yến/Huyền/Thảo không chờ player.

## STATE CHANGES
- A_PLAYER_SEEN/UNDERSTOOD possible theo actual observation/inference; CASE.A=2 không lùi vì miss scene.
- NETWORK_POSSIBLE hypothesis.
- Bắc tiến gần N3 nhưng chưa auto.

## BRANCHES
Nếu source A/B thiếu alternate và player trì hoãn, G1 risk.
Nếu route mạnh, mở S12/S13 với đủ thời gian.

## FAILURE / CONSEQUENCE
Sai ordering puzzle có hint; không game-over.
Hiểu sai Phúc chỉ tốn route/timing nếu player bỏ source thật.

## AUDIO ATMOSPHERE
Tĩnh, tiếng bút/giấy/điện thoại; giảm nhạc để reasoning có trọng lượng.

## CINEMATIC NOTES
Midpoint không có montage “conspiracy reveal”. Player phải tự thấy ba timestamps.

## TRANSITION OUT
Vũ cho player quay lại logistics với câu hỏi authority, không với “đáp án” → S12.

## REPLAY VALUE
Opening được recontextualize: mọi crisis đã chạy trước khi Bắc đặt chân vào.

---

## CHAPTER 5 — SAI NGƯỜI, ĐÚNG DỮ KIỆN

# S12 — TUẤN, RỒI HÙNG: HAI “BOSS” QUÁ HỢP LÝ

## P5 PLAYABLE EVENT CONTRACT — S12

- **ENTRY CONDITION:** S11 và retained police packets; Tân Lộ12:30.
- **ENVIRONMENTAL SETUP:** Cùng dispatch terminal nay hiển thị audit trail; C17, C20, C21 và C22 đã được request/received theo lịch, không source mới từ worker lock.
- **CURIOSITY FUNNEL:** Tuấn đi qua bảng phân công như hôm qua; timestamp override nằm trước ca anh trực.
- **PLAYER ACTION:** Player mở fast recap hai field C20/C22 thay vì làm lại interrogation; có thể xem C21 routine từ job thường.
- **PLAYABLE DISCOVERY:** Tuấn không reclassify E19; C22 Hùng đã nhận purpose và approve, nhưng statement Hùng một mình chưa chứng minh Nam.
- **AUTOMATIC EVENTS:** Police C22 packet receipt13:00; content match không trước14:55 và retained C18/C19 verification13:55.
- **MICRO EVENTS:** Máy quét lặp đúng âm S04; hình ca thường song song ca 117.
- **SIGNATURE / SET-PIECE EVENT:** S12_FALSE_APEX_SWAP: cùng quầy S04, player tự lật audit trail, nghi ngờ đổi từ Tuấn sang Hùng bằng evidence.
- **NPC ROUTINE:** Tuấn xử lý ca khác, không bất ngờ biết Bắc nghi ai; Hùng không cần monologue.
- **WORLD STATE CHANGES:** TUAN_NOT_RECLASSIFIER riêng TUAN_CORE_SCOPE_VERIFIED; Hùng culpable knowledge chỉ từ verified C22.
- **OPTIONAL MISSED DETAIL:** C21 hành vi nhất quán; optional conversation không gate.
- **RETURN / PAYOFF:** S16 Hùng D1 chỉ khi firsthand actual statement, không suy từ title.
- **FAIL-FORWARD:** Nếu đã thấy C20, dùng recap ngắn; nếu chưa, phiên bản full inspect vẫn cho cùng fact.
- **EXIT CONDITION:** Retained verification tới13:00, travel hospital area13:30/micro-set13:35.
- **IMPLEMENTATION HOOKS:** Fast recap, permission log viewer, versioned audit, no new source pickup.


## VỊ TRÍ TRONG STORY
False theory / wrong direction.

## ESTIMATED PLAY TIME
~5 phút.

## LOCATION
SITE C — Tân Lộ; quầy/office records.

## TIME / STATE
D+1, 12:30–13:00 retained verification30m; extras fixed warned cost, no fresh morning source pickup.


## CHARACTERS PRESENT
Bắc, Tuấn, Đức; Hùng gián tiếp/brief appearance.

## PLAYER ENTRY CONDITION
R1 + hospital timeline đủ để đặt câu hỏi authority.

## PRIMARY OBJECTIVE
Xác định ai có quyền đổi classification và Tuấn thực sự biết tới đâu.

## NARRATIVE PURPOSE
Dạy player: access ≠ knowledge; culpable manager ≠ apex.

## PLAYER ACTIONS
- inspect permission chain;
- hỏi Tuấn về override;
- compare procedural behavior;
- review morning received C18/testimony hoặc limited callback, không fresh copy sau willingness11:00;
- follow Hùng-level approval trail.

## REQUIRED EVENTS
1. C20 loại Tuấn khỏi quyền reclass.
2. C22 đặt quyết định ở Hùng-level.
3. Player thấy Hùng thật sự culpable.
4. Không có fact nào cho phép dừng ở Hùng như command toàn mạng.

## OPTIONAL EVENTS
- C21.
- C18/C19 retained morning copy verification; actual receipt09:45/10:35 hoặc10:50 phải đã ghi.
- Brief visual Hùng nhưng không monologue.

## CLUES
- **Mandatory:** C20, C22.
- **Optional:** C21, C18.
- **Red herring:** RH1 Tuấn; RH2 Hùng.
- **True-ending:** C22 cần cho C; C18 là corroborator.
- **Delayed-value:** DV6 procedural Tuấn.

## NPC INFORMATION
**Tuấn**
- Biết: vận hành, ngoại lệ y tế bề mặt, Hùng là authority trên mình.
- Nói: chain thực.
- Giấu: đã làm ngơ.
- Không biết core.

**Đức**
- Biết: Hùng sửa dấu/ngoại lệ leadership-level, giữ snapshot.
- Nói: phần logistics trực tiếp.
- Giấu: mức mình đã lưu để tự bảo hiểm.
- Không biết Nam.

**Hùng**
- Biết: core logistics complicity và breach.
- Nói nếu xuất hiện: framing business/audit.
- Giấu: E19 self-protection và relation command.
- Có thể nghĩ tự cứu bằng cách đẩy trách nhiệm.

## BACKSTAGE EVENTS
Đức willingness11:00/Yến access12:30 đã đóng; private/received copies còn và source verification dùng actual custody.

Khải thấy incident ngày càng khó cô lập.

## STATE CHANGES
- TUAN_CORE_SCOPE_VERIFIED chỉ sau Vũ verify assignment/permissions, unanswered purpose questions và lời Tuấn giới hạn; nghĩa case-scope không có cơ sở xếp core, không blanket innocence.
- C_LOGISTICS_LEADERSHIP possible/proven.
- HUNG_FALSE_APEX can arm if player stops reasoning.

## BRANCHES
Observable extra Tuấn visit+15m, Hùng wait+30m hoặc dời new intake+20m có visible finish/deadline warning. Private false apex/retry0; chỉ source thật chưa received có thể lỡ, existing police processing không retime.

## FAILURE / CONSEQUENCE
Không có accusation quiz.
Player được phép tin sai/đọc chậm mà clock không tăng; committed dialogue/travel/wait mới tăng đúng fixed cost.

## AUDIO ATMOSPHERE
Office gấp hơn buổi sáng; máy in, điện thoại, người gọi nhau; access door beep có thể telegraph closure.

## CINEMATIC NOTES
Hùng nếu seen: framing như lãnh đạo công ty bận, không boss shot.

## TRANSITION OUT
Source chỉ lên cross-cell risk endpoint → S13.

## REPLAY VALUE
Player thấy mỗi false boss đều “đúng một phần”; mystery không dựa vào người vô tội giả ác.

---

# S13 — CÙNG MỘT NGƯỜI QUẢN RỦI RO

## P5 PLAYABLE EVENT CONTRACT — S13

- **ENTRY CONDITION:** S12 source receipts đã có; police micro-set13:35.
- **ENVIRONMENTAL SETUP:** Hai request/response packets hospital/logistics với endpoint Khải có thể đặt cạnh nhau; paper custody tags khác private notebook.
- **CURIOSITY FUNNEL:** Hai thẻ escalation có cùng người nhận nhưng scope khác, điện thoại Vũ báo callback.
- **PLAYER ACTION:** Player so current case, endpoint, role và response; có thể chọn giả thuyết sai về Khải mà vẫn giao raw packets cho Vũ.
- **PLAYABLE DISCOVERY:** X_RISK chỉ khi request/response/auth current Phúc crisis matched; same account/transaction không đủ; N3_UNDERSTANDING private conditional.
- **AUTOMATIC EVENTS:** Vũ verify C18/C19 match13:55, C content14:55 nếu actual packets complete; X police không đợi player suy đúng.
- **MICRO EVENTS:** Phone callback; bàn giấy lật, âm phòng nhỏ hơn hành lang.
- **SIGNATURE / SET-PIECE EVENT:** S13_TWO_DESKS: player nối hai hồ sơ từ hai cơ sở trong không gian chung, phản hồi của Vũ giới hạn vào source đã thấy.
- **NPC ROUTINE:** Vũ kiểm provenance, Khải chỉ biết report đã nhận; Nam chỉ sau forward thực.
- **WORLD STATE CHANGES:** X_VERIFIED raw source, X_PLAYER_CONNECTED private tách; no auto N3/BARC on completion.
- **OPTIONAL MISSED DETAIL:** Khải false apex theory; không chặn custody.
- **RETURN / PAYOFF:** S16 X_COMMAND có thể hoàn chỉnh X nếu Khải remit còn thiếu.
- **FAIL-FORWARD:** Sai inference không time/route penalty; raw source vẫn được kiểm.
- **EXIT CONDITION:** Callback/compare13:35–14:00, S14 notice.
- **IMPLEMENTATION HOOKS:** Dual packet compare, police verifier, private inference, report receipt ledger.


## VỊ TRÍ TRONG STORY
Escalation / three-box connection.

## ESTIMATED PLAY TIME
~6 phút.

## LOCATION
Existing police micro-set trong hospital area, sau Tân Lộ→area30m +local move5m; retained-source callbacks, không source tour mới.

## TIME / STATE
D+1, 13:35–14:00 compare/callback25m; preceding travel30m+5m local.


## CHARACTERS PRESENT
Bắc, Vũ, Đức; Huyền/Thảo via verified source; Yến optional mostly police; Khải direct/indirect.

## PLAYER ENTRY CONDITION
A/B/C có đủ mảnh để cross-compare.

## PRIMARY OBJECTIVE
Xác định liệu các scandal có chung risk-management endpoint.

## NARRATIVE PURPOSE
Đạt R7/R8 và N3 understanding.

## PLAYER ACTIONS
- review two contact trails;
- puzzle compare endpoints/timestamps C24/C25;
- chọn bridge gửi Vũ;
- optional retained-source Đức/Yến/Thảo verification từ actual morning receipt; không new acquisition sau local closure;
- nghe Vũ xác minh phần player không cần tự đi.

## REQUIRED EVENTS
1. C24 hospital→Khải có actual endpoint, incident request/response scope, current role và crisis context.
2. C25 logistics→Khải có independent same-risk-context payload; transaction/account group match ABC chỉ lead.
3. Player tự nối C26 nếu facts/inference đúng; sai/thiếu giữ hypothesis, không cấp certainty.
4. Vũ set X_VERIFIED khi complete raw risk sources/context đã intake/authenticate dù private inference sai, không yêu cầu teen giải hộ police.
5. Hùng/Khoa/Hạnh được giữ là culpable nhưng knowledge-limited.

## OPTIONAL EVENTS
- C18/C19.
- C26A Khải behavior.
- Additional corroborator B/C.

## CLUES
- **Mandatory:** C24, C25; C26 as inference.
- **Optional:** C18/C19/C26A.
- **Red herring:** Khải hoặc Hùng có thể trông như apex.
- **True-ending:** X requires verified cross-cell relation.
- **Delayed-value:** prior timestamps become network architecture.

## NPC INFORMATION
**Khải**
- Biết: gần toàn network/risk picture.
- Nói: narrow accurate facts, tránh scope quyền.
- Giấu: Nam/command flow và cleanup coordination.

**Vũ**
- Biết tăng theo corroboration.
- Nói: nguồn nào đã verify, nguồn nào chưa.
- Raw risk sources/context thiếu thì X chưa đủ; full retained sources/context đã intake cho Vũ verify current shared risk role độc lập, không cần private inference Bắc đúng.

**Yến**
- Nếu route dùng: biết financial anomalies only.
- Không biết Nam/full network.

## BACKSTAGE EVENTS
E36: N3_UNDERSTANDING theo observed facts + đúng inference, không scene award.
E37: chỉ actual received reports đủ mới nâng BARC; Nam chỉ nhận exact Khải forward. Baseline cleanup và teen knowledge riêng.

## STATE CHANGES
- X_PLAYER_CONNECTED chỉ khi actual observed C24/C25 identity/role/scope/crisis context đủ và explicit inference đúng.
- N3_UNDERSTANDING chỉ khi observed A/B/C facts đủ + successful risk-structure inference; fragments/miss/failed attempt giữ hypothesis.
- KHẢI_LAYER chỉ khi endpoint và current role được actual source nhận diện và player nối đúng.
- X_VERIFIED riêng: Vũ verify full raw risk custody dù teen inference sai; không auto từ same transaction.
- BARC N3 chỉ theo E37 actual received cross-cell reports; private flags không thay report.

## BRANCHES
- Nếu source đủ: preservation path S15 mạnh.
- Nếu thiếu B/C alternate: Delay risk.
- Nếu player dùng unsafe channel: leak consequences S14.

## FAILURE / CONSEQUENCE
Inference/retry0. Chỉ actual extra appointment/visit/wait sau visible cost/deadline warning mới advance clock; police raw-custody verification vẫn chủ động dù private theory sai.

## AUDIO ATMOSPHERE
Cross-cut sound design giữa office/hospital/police, nhưng không montage giải thích. Tension tăng bằng notification/access sounds.

## CINEMATIC NOTES
Có thể dùng 10–15 giây transition montage khi Vũ xác minh off-screen, tránh fetch-quest.

## TRANSITION OUT
Một hoặc nhiều access/source bắt đầu đóng → S14.

## REPLAY VALUE
Player thấy compartmentalization sụp không phải vì một whistleblower biết tất cả, mà vì các endpoint xác nhận nhau.

---

# ACT IV — HỆ THỐNG PHẢN ỨNG

## CHAPTER 6 — CỬA ĐANG KHÉP

# S14 — HỆ THỐNG BẮT ĐẦU KHÉP CỬA

## P5 PLAYABLE EVENT CONTRACT — S14

- **ENTRY CONDITION:** S13 callback hoặc clock tới14:00; notices từ morning đã nhận.
- **ENVIRONMENTAL SETUP:** Một worker screen khóa, quầy hospital đổi biển quyền, tin hẹn biến mất theo closure đã xảy ra ở 11:00/11:30/12:30.
- **CURIOSITY FUNNEL:** Player trở lại cùng điện thoại/hành lang, thấy trạng thái vật khác lần trước; nếu Minh đã hỏi hộ, timestamp report có thể so.
- **PLAYER ACTION:** Player kiểm what actually closed, hỏi Minh phần cậu nói, chuyển ngay retained source còn thiếu cho Vũ hoặc chọn delay có card.
- **PLAYABLE DISCOVERY:** Cửa access/willingness đóng riêng; copies ở phone Đức/police không biến mất. BARC chỉ từ actual received reports.
- **AUTOMATIC EVENTS:** Global command notice14:00 trước deadline17:00; acceleration chỉ nếu report, fresh warning và feasible save plan OT §0.1.
- **MICRO EVENTS:** Badge denied; phone vibration; đèn quầy off khi hết ca, không supernatural.
- **SIGNATURE / SET-PIECE EVENT:** S14_RETURN_CHANGED: tái thăm các vật quen cho thấy hệ thống khép cửa bằng state thực, không chase.
- **NPC ROUTINE:** Minh giảm nhẹ đúng payload đã gửi; Khải xử lý report thật, Lan/Nam không biết private note.
- **WORLD STATE CHANGES:** Actual access states và warning receipts; no baseline BARC=N3, no deletion of custody.
- **OPTIONAL MISSED DETAIL:** C35–C37 conditional leak trace, không tạo proof giả.
- **RETURN / PAYOFF:** S18 causal attribution dùng earliest last-path loss, không dùng cảm giác phản bội.
- **FAIL-FORWARD:** Local locks không chặn professional copies; player vẫn chuyển nguồn đã giữ.
- **EXIT CONDITION:** 20m authored notices/action group tới14:20.
- **IMPLEMENTATION HOOKS:** Prop/access variants, notification ledger, warning card, causal report.


## VỊ TRÍ TRONG STORY
Danger escalation.

## ESTIMATED PLAY TIME
~5 phút.

## LOCATION
Multi-hub state change: phone + Tân Lộ + Minh Trạch status. Player có thể bắt đầu ở transit/police point.

## TIME / STATE
D+1, 14:00–14:20 notices20m; global warning14:00, local pre-loss notices already delivered.


## CHARACTERS PRESENT
Bắc, Minh, Vũ qua phone; Tuấn/Đức/Huyền tùy source.

## PLAYER ENTRY CONDITION
N3/cross-cell pressure hoặc cleanup objective đạt threshold.

## PRIMARY OBJECTIVE
Nhận ra source windows đang đóng và xác định nguyên nhân nếu có leak.

## NARRATIVE PURPOSE
Biến threat thành bureaucracy có hậu quả, không “đội sát thủ”.

## PLAYER ACTIONS
- thử access source đã dùng;
- nhận cancel/lock notifications;
- confront Minh ở mức thông tin;
- compare timing leak vs closure;
- gọi Vũ.

## REQUIRED EVENTS
1. Ít nhất một C43 access-closure event.
2. Required global notice14:00: baseline command deadline17:00, availability-only broker notice, actual missing-source intake saving action; không annex receipt trước E38. Fresh acceleration warningW phải để40m intake/authentication đủ actual E38+75m D pipeline+10m buffer trước max(16:30,W+145m)<17:00. Nếu actual remainder dài hơn, OT §0.1 feasibility check bắt buộc hoặc giữ baseline17:00; queue/receipt chưa authenticated không grant E38.
3. Local pre-loss notices S08/S09/S10 đã xảy ra; S14 morning-lock explanation không được dùng thay prior warning.
4. Cleanup được thể hiện như process; local willingness/access closure không global CLEANUP=LOCKED.

## OPTIONAL EVENTS
- C35/C36/C37 nếu Minh leak.
- Một source nói rõ “tôi sắp mất access”.
- Player có thể không biết nguyên nhân exact nếu không giữ trail.

## CLUES
- **Mandatory:** C43 consequence signal.
- **Optional:** C35/C36/C37.
- **Red herring:** RH4 Minh là plant nếu player suy quá.
- **True-ending:** reinforce existing local warnings và global14:00 notice; saving action vẫn feasible trước global lock17:00/canonical acceleration16:30.
- **Delayed-value:** C07 giải thích Minh không phải member.

## NPC INFORMATION
**Minh**
- Biết: chính những gì Bắc đã chia.
- Nói: “chỉ hỏi người phụ trách” ở mức nội dung.
- Giấu: lượng chi tiết đã nói.
- Không biết hậu quả thật cho tới khi quá muộn.

**Vũ**
- Biết: source closure là risk.
- Nói: custody/provenance quan trọng hơn Bắc giữ screenshot.

## BACKSTAGE EVENTS
Khải cắt access.  
Nam xem report Bắc/N3 chỉ nếu E37 đủ và actual forward tới ông; baseline cleanup không sinh report.
Managers vẫn tự bảo vệ dù Bắc private route giữ prior BARC.

## STATE CHANGES
- CLEANUP_ACCELERATED conditional.
- MINH_BETRAYAL_REVEALED conditional.
- BARC derive actual received reports; S14 vào do baseline cleanup giữ prior BARC, không auto N3.
- LEAK_PATH = MINH only if causal chain thật sự đủ.

## BRANCHES
- G2 Wrong Trust chỉ arm nếu leak làm unique/last route mất trước preservation.
- Không leak vẫn có cleanup closures objective.
- Continue → S15.

## FAILURE / CONSEQUENCE
Không auto-bad-ending vì nhắn Minh.
Nếu source vẫn còn alternate hoặc đã preserve, true route sống.

## AUDIO ATMOSPHERE
Notifications, line disconnect, access denied beep, urban daytime continuing normally. Không action music liên tục.

## CINEMATIC NOTES
Có thể dùng one-shot ngắn: cửa access đóng trước mặt/employee badge fail.
Không chase.

## TRANSITION OUT
Vũ yêu cầu quyết định custody → S15.

## REPLAY VALUE
Player thấy “kẻ địch” mạnh nhất của run là timing + information leakage, không phải physical monster.

---

# S15 — TỪ “TÔI BIẾT” SANG “HỌ BIẾT TÔI ĐANG BIẾT”

## P5 PLAYABLE EVENT CONTRACT — S15

- **ENTRY CONDITION:** S14 notices xong14:20, Vũ đang intake/coordinate.
- **ENVIRONMENTAL SETUP:** Bàn nhận evidence có khay source với provenance và pending authentication; không bảng suspects.
- **CURIOSITY FUNNEL:** Một item giữ riêng trên phone Bắc đối chiếu được với khay police; dấu received chưa phải verified.
- **PLAYER ACTION:** Player chọn gửi bản gốc/custodian/contact và scope, có thể giữ lại, delay20m hoặc abandon khi actual N3 report.
- **PLAYABLE DISCOVERY:** A đã Vũ giữ từ E28; B/C/X tăng chỉ sau receipt + independent checks; private N3 understanding không quyết định threshold.
- **AUTOMATIC EVENTS:** E38 actual baseline14:55 khi đủ raw/auth, không auto từ scene completion; custody-first cho command requests S16.
- **MICRO EVENTS:** Scan giấy, phone receipt, tem ngày/giờ; city outside continues.
- **SIGNATURE / SET-PIECE EVENT:** S15_CUSTODY_DESK: thao tác phân nguồn gốc cụ thể thay cho lời thuyết phục Vũ.
- **NPC ROUTINE:** Vũ tự request đủ scope đã biết, không đợi một accusation quiz.
- **WORLD STATE CHANGES:** Actual custody monotonic, E38 if threshold; ABANDON_AFTER_N3 only on explicit choice + received reports.
- **OPTIONAL MISSED DETAIL:** Không cần private correct Khải/true boss inference.
- **RETURN / PAYOFF:** S16 professional collection chạy sau actual E38.
- **FAIL-FORWARD:** Thử lại provenance không cost; missing source thật đóng thì G1/G2/G5 theo cause.
- **EXIT CONDITION:** Intake/coordination tới15:00; S16 chỉ theo actual E38 hoặc partial path.
- **IMPLEMENTATION HOOKS:** Evidence tray, provenance verifier, E38 timer, abandonment condition.


## VỊ TRÍ TRONG STORY
Point of no return.

## ESTIMATED PLAY TIME
~4 phút.

## LOCATION
POLICE MICRO-SET / secure intake.

## TIME / STATE
D+1, 14:20–15:00 sourced intake/coordination40m; E38 actual baseline14:55 if source authentication sufficient, not scene award.


## CHARACTERS PRESENT
Bắc, Vũ; Linh optional 15–20 sec đời thường outside mystery.

## PLAYER ENTRY CONDITION
Sourced case/intake hiện tại có raw sources/context cần receipt, verification hoặc preservation. Không yêu cầu N3_UNDERSTANDING đúng; Vũ nhận/verify đủ raw sources độc lập. BARC và organization response được derive riêng từ actual received reports, không chặn police intake vì private inference sai.

## PRIMARY OBJECTIVE
Quyết định evidence nào cần bàn giao/preserve ngay.

## NARRATIVE PURPOSE
Đổi game từ “thu thập” sang “custody”.
Khóa logic Avoidance đúng thời điểm.

## PLAYER ACTIONS
- review sourced items;
- chọn source có provenance;
- handover to Vũ;
- giữ/copy personal notes;
- có thể chọn abandon.

## REQUIRED EVENTS
1. Vũ giải thích ở mức chức năng: source cần được tiếp nhận.
2. C42 preservation event có thể bắt đầu.
3. Player thấy preservation không đồng nghĩa mất quyền hiểu.
4. Nếu A/B/C đủ, E38 mở.

## OPTIONAL EVENTS
- Linh nhắn về lớp/đời sống để nhắc Bắc đang bỏ lại bình thường.
- Player giữ lại non-critical note.

## CLUES
- **Mandatory:** C42 as event/gate.
- **Optional:** không new evidence.
- **Red herring:** không.
- **True-ending:** giữ A đang safe và intake/preserve B/C còn thiếu; raw risk X và D có verification riêng.
- **Delayed-value:** toàn bộ “giữ ảnh = an toàn” bị đảo nghĩa.

## NPC INFORMATION
**Vũ**
- Biết: đủ để chuyển investigation nếu A/B/C sourced.
- Nói: chỉ source/provenance.
- Giấu: tactical details của police response.

## BACKSTAGE EVENTS
Khải/Nam chuyển sang protect core nếu E38 observable.
Các branch bắt đầu close nhanh hơn.

## STATE CHANGES
- A_PRESERVED từ E28 giữ nguyên; B/C/source còn thiếu theo actual receipt/authentication individually.
- X_VERIFIED khi common current risk sources/context đủ trong custody; competent Vũ verify dù player inference sai. Không same-account auto X.
- E38 if threshold.
- ABANDON_AFTER_N3 chỉ khi BARC≥N3 từ received reports, police preservation còn thiếu và player thật sự rời route; private understanding riêng.

## BRANCHES
- **Continue preservation:** mở S16.
- **Abandon with BARC≥N3:** G3 armed nếu police chưa đủ tự giữ case; thiếu/sai private inference không thay exact adversary reports.
- **Giữ tất cả một mình:** exposure/cleanup risk tăng nhưng chưa auto-resolve.

## FAILURE / CONSEQUENCE
Player có thể preserve chưa đủ; route vẫn tiến tới partial ending.
Không cho UI “true ending unlocked”.

## AUDIO ATMOSPHERE
Rất ít nhạc; tiếng scan/copy/biên nhận custody tạo motif “giữ được sự thật”.

## CINEMATIC NOTES
Short close-up authored on receipt/intake stamp only if không quá gamey.

## TRANSITION OUT
Vũ chuyển câu hỏi sang “ai có quyền làm nhiều branch cùng đổi trạng thái?” → S16.

## REPLAY VALUE
Player hiểu true ending không thưởng người giữ nhiều collectible nhất, mà người biết lúc nào phải chuyển evidence ra khỏi tay mình.

---

## CHAPTER 7 — AI CÓ QUYỀN?

# S16 — TỪ MANAGER TỚI COMMAND

## P5 PLAYABLE EVENT CONTRACT — S16

- **ENTRY CONDITION:** Actual E38=t0 (baseline14:55), police mở source requests sau đó.
- **ENVIRONMENTAL SETUP:** Ba station nguồn: manager, original institution reply, broker annex; bản gốc L/H issue trước intake, không future record ở E28.
- **CURIOSITY FUNNEL:** Một stamp decision trên reply cho branch kia không giống statement manager; broker receipt có cùng directive scope.
- **PLAYER ACTION:** Player xem ba nguồn Vũ được phép hiển thị, so quyết định khác nhau và annex cùng case; không tự đi ép Hạnh/Nam.
- **PLAYABLE DISCOVERY:** C32H+C33_AUTH hoặc C32K+C34_AUTH và C10_SOURCE_LINK exact D2. Original receiver-side Nam reply phải verify; X_COMMAND có thể sinh từ raw facts này.
- **AUTOMATIC EVENTS:** Request t0+5/+10/+15; receipts +25/+40 or45/+55; authentication/full match +75 baseline16:10, chỉ khi nguồn hợp tác và window mở.
- **MICRO EVENTS:** Điện thoại báo receipt, printer annex nhả trang, bút ký custodial seal.
- **SIGNATURE / SET-PIECE EVENT:** S16_THREE_ORIGINS: player đối chiếu manager firsthand, reply phía branch kia và source execution mà không trộn một forward làm ba chứng cứ.
- **NPC ROUTINE:** Vũ intake chuyên nghiệp; manager chỉ branch mình, broker chỉ received directive, Nam không đọc scene completion.
- **WORLD STATE CHANGES:** COMMAND C3/C4 chỉ từ raw verified/preserved; X normalize trước resolver; unavailable route có manager alternate.
- **OPTIONAL MISSED DETAIL:** C31 contact chỉ lead, C30 history không gate.
- **RETURN / PAYOFF:** S17 Nam recontextualized, S18 consequence đúng source.
- **FAIL-FORWARD:** Mất Hùng dùng Khoa+logistics original; mất cả managers không record-only magic D1.
- **EXIT CONDITION:** Actual D verified nếu đủ; scene presentation tới16:25, no forced extra travel.
- **IMPLEMENTATION HOOKS:** Source request scheduler, original reply verifier, broker annex UI, custody variants.


## VỊ TRÍ TRONG STORY
Late investigation.

## ESTIMATED PLAY TIME
~7 phút.

## LOCATION
Police micro-set + selected manager source + authored records; không cần tour toàn Hà Nội.

## TIME / STATE
D+1, 15:00–16:25 presentation/group85m; full D actual baseline16:10, professional offsets from actual E38.


## CHARACTERS PRESENT
Bắc, Vũ, Khải/Hùng hoặc manager source phù hợp; Khoa/Thảo route-dependent.

## PLAYER ENTRY CONDITION
A+B+C đủ mạnh hoặc đủ để late route tiếp tục.

## PRIMARY OBJECTIVE
Chứng minh command authority hiện tại, không chỉ tìm người “trông giống boss”.

## NARRATIVE PURPOSE
Tách relationship evidence khỏi command evidence.

## PLAYER ACTIONS
- inspect C30 relationship record;
- compare C31 current contact timing;
- obtain/verify C32 hoặc C33/C34;
- reasoning interaction: “history / current contact / decision authority / independent corroboration”;
- send sources to Vũ.

## REQUIRED EVENTS
1. C30 chỉ được frame là history.
2. C31 opens current Khải→Nam contact.
3. Current L issue13:20/execution13:25 và H issue13:45/execution13:50 theo OT §0.2, khác request/decision. Hùng firsthand L pairs hospital H; Khoa firsthand H pairs logistics L.
4. Sau actual E38=t0, professional manager request+5/receipt+25, OTHER-branch originals+10/receipt+40 hoặc+45, broker request+15/receipt+55/final match+75. Baseline actual15:20/15:35–40/15:50/16:10; receiver-side Nam originals authenticate, no display-name inference. Source annex matches exact selected D2, not independent duplicate proof.
5. Availability warning14:00/reminder15:00 và actual saving intake trước known global deadline; queued request không custody. Vũ tự collect once sourced context held, không second click.
6. Game không cho C27/C28/C30 count D.

## OPTIONAL EVENTS
- C33/C34 alternate.
- Một manager source rút nếu timing xấu.
- Additional corroborator.

## CLUES
- **Mandatory for strong/true:** accepted manager own-branch + authenticated distinct OTHER-branch record + matched late source-annex actual receipts, theo OT §0.2/P1 contract. C31 chỉ identity/contact lead.
- **Optional:** C30, C33/C34 depending route.
- **Red herring:** Khải/Hùng as apex.
- **True-ending:** D1 + D2.
- **Delayed-value:** C27/C28/C30 recontextualize but do not prove.

## NPC INFORMATION
**Hùng**
- Biết: Nam has authority over his branch.
- Nói nếu source route mở: đúng phạm vi mình trực tiếp biết.
- Giấu: own culpability/self-protection.

**Khải**
- Biết: Nam command, cross-cell risk.
- Nói: narrow framing.
- Giấu: scope and decision chain.

**Khoa/Thảo**
- Chỉ cung cấp branch-specific facts, không biết logistics details vượt canon.

**Vũ**
- Kiểm tra independence giữa D sources; không nhận “Nam quen Hùng” làm proof.

## BACKSTAGE EVENTS
Nam/Khải đóng nhánh.  
Hùng/Khoa/Hạnh tự cứu, không hive mind.
Global baseline17:00/canonical warned16:30, không các local closures. Requests/receipts/auth từ OT §0.2; full custody16:10 trước group end16:25.

## STATE CHANGES
- COMMAND D1.
- COMMAND D2.
- D_PRESERVED nếu chuyển kịp.
- TRUE_ROUTE_AVAILABLE chỉ derived khi A/B/C/X/D/T đủ.

## BRANCHES
- D đủ + timing tốt → S17/S18 true-capable.
- A+B+C safe nhưng D thiếu/late → G4 Cleanup trajectory.
- Direct confrontation/unsafe handling có thể arm G5.

## FAILURE / CONSEQUENCE
Nếu Hùng C32H mất, Khoa C32K + C34_AUTH là alternate có manager firsthand. Mất cả hai managers thì C33/C34 record-only không thay D1.
Nếu mọi D corroboration đóng, player có thể hiểu Nam nhưng không chứng minh → G4.

## AUDIO ATMOSPHERE
Nhịp gấp nhưng cerebral. Phone calls overlap nhẹ, printer/scanner, external traffic.

## CINEMATIC NOTES
Có thể cross-cut 2–3 authored shots của branch status đổi sau same decision window, nhưng player phải có source trước; cinematic không được tạo proof mới.

## TRANSITION OUT
Sau S16, offer return HUB B as an optional ordinary reason → S17; police custody and consequence may go directly → S18. No proof is re-delivered at the boarding house.

## REPLAY VALUE
Player thấy boss reveal là product của current command records, không phải “ông già có background đáng ngờ”.

---

# S17 — NAM KHÔNG “LỘ MẶT”; PLAYER CHỨNG MINH ÔNG CÓ QUYỀN

## P5 PLAYABLE EVENT CONTRACT — S17

- **ENTRY CONDITION:** Sau S16; optional về trọ16:25→17:00 hoặc bypass tới police/consequence.
- **ENVIRONMENTAL SETUP:** Hành lang S01 và góc sửa đồ vẫn thường; cửa phòng Nam chỉ mở với lý do đời thường được Lan/Nam mời hoặc trả món đồ.
- **CURIOSITY FUNNEL:** Radio rít nhẹ, một ổ điện lỗi làm chốt cửa kẹt; từ bàn có sổ ghi các mảnh “K. báo lại”, “MT giữ nguyên”, “117”.
- **PLAYER ACTION:** Nếu chọn vào, player thử tay nắm, gõ/gọi, xem đồ hợp lệ; giữ control, có thể rời khi chốt được Lan xử lý từ ngoài. Không bắt đọc sổ.
- **PLAYABLE DISCOVERY:** Fragments là context/hypothesis, không Nam-boss proof; command chỉ từ S16 professional sources.
- **AUTOMATIC EVENTS:** Door jam do chốt cũ/điện, Lan nghe tiếng gõ hoặc chốt tự reset sau mechanic beat; không ba clue mở phép. Nam chỉ biết xáo trộn nếu trực tiếp thấy dấu cụ thể.
- **MICRO EVENTS:** Static radio, bước chân ngoài cửa, đèn buzz; môi trường phản hồi nhẹ nhưng có nguồn vật lý.
- **SIGNATURE / SET-PIECE EVENT:** S17_ROOM_JAM: 1–3 phút khám phá có lối thoát causal, player giữ quyền điều khiển; optional unsafe confrontation riêng.
- **NPC ROUTINE:** Lan đi cầu thang rồi hỗ trợ; Nam về theo lịch, không telepathy; có thể không gặp.
- **WORLD STATE CHANGES:** Door JAMMED→RELEASED vì latch reset/Lan; disturbed object flag chỉ nếu player thật sự chuyển vật và Nam nhìn thấy.
- **OPTIONAL MISSED DETAIL:** Notebook fragments/C28; toàn bộ S17 có thể bỏ qua nếu custody đã an toàn.
- **RETURN / PAYOFF:** Epilogue vật cũ S01; encounter thay sắc thái theo knowledge, không thêm gate True.
- **FAIL-FORWARD:** Bỏ về trọ vẫn tới S18; nếu door jam, gõ/gọi hoặc chờ authored release không tốn missing-source window bất ngờ.
- **EXIT CONDITION:** Door released, optional conversation xong; đi police35m nếu cần, hoặc direct S18.
- **IMPLEMENTATION HOOKS:** DoorInteractable JAMMED, light/radio, document pages, Lan NPC route, bypass.


## VỊ TRÍ TRONG STORY
Boss realization / emotional confrontation without required accusation.

## ESTIMATED PLAY TIME
~5 phút.

## LOCATION
HUB B — cùng hành lang/góc sinh hoạt S01/S05.

## TIME / STATE
D+1, optional after D intake: travel35m16:25→17:00, ordinary contact15m→17:15; custody held survives global lock.


## CHARACTERS PRESENT
Bắc, Nam, Lan rất ngắn; Vũ qua phone trước/sau.

## PLAYER ENTRY CONDITION
Nam hypothesis mạnh; ideally D1/D2 đang được verify hoặc vừa đủ.

## PRIMARY OBJECTIVE
Đi qua một tương tác đời thường với Nam mà không tự phá custody; hoàn tất proof qua Vũ nếu cần.

## NARRATIVE PURPOSE
Payoff toàn bộ location reuse và “fair but invisible”.

## PLAYER ACTIONS
- về phòng/lấy một vật đời thường hoặc đổi đồ;
- nói chuyện Nam ở mức normal;
- optional inspect C28 nếu trước đây chưa và access vẫn hợp lý;
- chọn calm / hỏi vòng / confront;
- dùng phone gửi D source cho Vũ khi an toàn.

## REQUIRED EVENTS
1. Recontextualize C27/C29/C30.
2. Nam cư xử bình thường, không confession.
3. Nếu D1+D2 đã đủ, NAM_PROVEN state đến từ evidence, không dialogue.
4. Scene phải cho player cảm giác knowledge asymmetry: hai người có thể đứng cùng chỗ S01 nhưng ý nghĩa đã đảo.

## OPTIONAL EVENTS
- C28 nếu còn hợp lý.
- Lan đi ngang nói chuyện đời thường.
- Nam thể hiện kindness thật một lần cuối, không redemption.

## CLUES
- **Mandatory:** không clue mới.
- **Optional:** C28.
- **Red herring:** history/relationship alone.
- **True-ending:** chỉ D sources đã có mới count.
- **Delayed-value:** C27/C28/C29/C30 payoff.

## NPC INFORMATION
**Nam**
- Biết tùy BARC: Bắc đã chạm nhiều cell/possibly police bridge.
- Không biết: exact notebook hoặc source police đã giữ trừ khi observable.
- Nói: chuyện sinh hoạt/đời thường; có thể framing chung về “đừng dính việc người khác”.
- Giấu: command role.
- Không confession/đe dọa lộ liễu.

**Lan**
- Không biết truth; presence chứng minh khu trọ không phải lair.

## BACKSTAGE EVENTS
Khải đang đóng source.
Police đang race preservation.
Nam cân protect core, không “đấu tay đôi” với Bắc.

## STATE CHANGES
- NAM_HYPOTHESIS distinct from NAM_PROVEN.
- Direct LEAK_PATH nếu player thật sự cho Nam biết unique unpreserved source.
- D_PRESERVED nếu player chuyển evidence đúng cách.

## BRANCHES
- Calm/preserve → S18.
- Premature direct exposure làm unique chain gãy → G5 possible.
- Confront sau khi mọi proof đã preserve không xóa true route.

## FAILURE / CONSEQUENCE
Không có “bấm nhầm một câu là chết”.
Causal consequence chỉ khi disclosure làm organization act trước preservation.

## AUDIO ATMOSPHERE
Âm thanh HUB B gần giống S01: quạt, ngõ, trà, đồ điện. Tension đến từ silence và player knowledge; không villain theme.

## CINEMATIC NOTES
Cực tiết chế.
Có thể dùng một shot third-person rất ngắn sau interaction để nhấn khoảng cách hai người, nhưng first-person tốt hơn nếu production muốn giữ intimacy.

## TRANSITION OUT
Vũ liên lạc: command window đang đóng / cần final preservation → S18.

## REPLAY VALUE
Đây là payoff location lớn nhất: cùng không gian, cùng con người, fact không đổi; chỉ hiểu biết player đổi.

---

# ACT V — AI GIỮ ĐƯỢC SỰ THẬT TRƯỚC?

## CHAPTER 8 — PRESERVATION

# S18 — AI GIỮ ĐƯỢC SỰ THẬT TRƯỚC?

## P5 PLAYABLE EVENT CONTRACT — S18

- **ENTRY CONDITION:** S16 actual command result hoặc S17 return/bypass; terminal only after real closure/committed exit.
- **ENVIRONMENTAL SETUP:** Police evidence tray và phone status đặt cạnh nhau, exterior Hà Nội vẫn tiếp tục; không gói clue mới.
- **CURIOSITY FUNNEL:** Một custody receipt hoặc warned source closure cuối hiện rõ trước khi player xác nhận bước tiếp.
- **PLAYER ACTION:** Player review provenance/source paths, chuyển item còn thiếu nếu window open; xác nhận exit hoặc nhìn timeline consequence.
- **PLAYABLE DISCOVERY:** Outcome do CASE/X/COMMAND + earliest DECISIVE_LOSS/abandon, không suspect selection.
- **AUTOMATIC EVENTS:** Resolver P4 xử lý receipts trước closure; G6/G3/G5/G2/G4/G1 exhaustive. A/B/C police held stay held ở mọi cinematic.
- **MICRO EVENTS:** Printer seal, phone ngừng rung, ambience ngõ trở lại ở epilogue.
- **SIGNATURE / SET-PIECE EVENT:** S18_TWO_TRAYS: cùng bố cục police tray và screen closure, nội dung/sound đổi theo phần thật đã giữ và nguyên nhân mất.
- **NPC ROUTINE:** Vũ hành động trên proof thực; Nam/Khải chỉ phản ứng reports/custody họ có thể biết.
- **WORLD STATE CHANGES:** Ending ID and locked snapshot persisted once; no magically refreshed records.
- **OPTIONAL MISSED DETAIL:** Optional old object epilogue không đổi proof.
- **RETURN / PAYOFF:** Mọi seed vật/âm từ S04/S14 được trả lại qua consequence.
- **FAIL-FORWARD:** Nếu còn last saving path, không resolve; cho player quay lại nguồn hợp lệ.
- **EXIT CONDITION:** Cinematic ngắn và ending screen sau confirmed terminal state.
- **IMPLEMENTATION HOOKS:** Total resolver, causal-loss snapshot, custody UI, ending variants, idempotent save/load.


## VỊ TRÍ TRONG STORY
Climax + ending resolver.

## ESTIMATED PLAY TIME
~6 phút main resolution; epilogue 1–2 phút nằm trong budget tùy ending.

## LOCATION
Police micro-set + phone/records + short consequence montage across Tân Lộ, Minh Trạch, HUB B.

## TIME / STATE
D+1, consequence from17:50 if return police35m after S17; remote/safe branch reads custody already held, no required proof re-delivery.


## CHARACTERS PRESENT
Bắc, Vũ; Nam/Khải/Hùng/Khoa/Hạnh/Phúc/Huyền/Thảo/Đức/Yến chỉ xuất hiện theo consequence, không gom vào một phòng.

## PLAYER ENTRY CONDITION
Late resolver threshold reached.

## PRIMARY OBJECTIVE
Chuyển đúng source còn cần thiết sang custody, không để cleanup thắng race.

## NARRATIVE PURPOSE
Kiểm tra understanding + provenance + trust + timing.
Không thêm “clue cuối”.

## PLAYER ACTIONS
- final evidence review;
- choose which sourced records/contact trails to preserve;
- xác nhận source provenance;
- không cần accusation quiz;
- observe consequence.

## REQUIRED EVENTS
1. Resolver đọc state theo causal priority.
2. C42 success/failure được thể hiện.
3. Vũ phản ứng có năng lực với evidence đã đủ.
4. No combat/raid by Bắc.
5. Ending cinematic phản ánh đúng route cause.

## OPTIONAL EVENTS
Không có optional clue mới.
Một số epilogue detail phụ thuộc C28/C29/character routes nhưng không đổi ending logic.

## CLUES
- **Mandatory:** không new clue.
- **True-ending gate:** A/B/C preserved + X verified + D1/D2 preserved before cleanup lock.
- **Timing:** C42/C43.
- **Red herring:** không.

## NPC INFORMATION
**Vũ**
- Biết đúng phần đã corroborate.
- Nếu threshold đủ, chủ động hành động; không chờ Bắc “thuyết phục”.

**Nam/Khải**
- Hành động theo risk state: protect core/close branches.
- Không được omniscient.

**Các source**
- Chỉ góp phần họ trực tiếp biết.

## BACKSTAGE EVENTS
- E39 True nếu preservation thắng.
- E40 Cleanup nếu A+B+C safe nhưng D late.
- E41 Delay nếu source window hết trước đủ A/B/C.
- E42 Wrong Trust/Exposure nếu causal leak làm chain gãy.
- E43/E44 hậu ending.

## STATE CHANGES
Resolver cuối (terminal only; receipts/authentication before closure):
1. G6 khi A/B/C=2, X sourced và C4 đã preserve trước lock.
2. G3 khi explicit abandonment sau received N3 report mà police chưa tự hoàn tất đường thiếu.
3. G5/G2 theo earliest immutable DECISIVE_LOSS cause DIRECT/MINH, kể cả D-only.
4. G4 khi ABCX safe nhưng D/C4 thiếu hoặc muộn.
5. G1 cho mọi terminal còn lại, gồm ABC=2/X=false và weak two-slot routes. Hiện đúng custody đã giữ.
G0 đã resolve ở S07.

## BRANCHES

### G6 — NHỮNG MẢNH KHỚP LẠI
- Police giữ A/B/C/X/D.
- Core network bị phá ở mức thỏa mãn.
- Bắc sống và trở lại đời sinh viên.
- Tân Lộ/Minh Trạch không bị viết thành toàn bộ tội phạm.
- Epilogue HUB B có subtle old-object detail; không giải thích.

### G4 — DỌN SẠCH
- A+B+C được giữ.
- Hùng/Khoa/Hạnh có thể bị xử lý theo proof.
- Nam/Khải chưa bị nối command đủ mạnh trong game window.

### G1 — QUÁ MUỘN
- Vũ xử lý phần có proof.
- Mystery lớn chưa breakthrough trong run.
- Không cho “phép màu” sau credit.

### G2 — SAI NGƯỜI
- Minh hiểu hậu quả việc leak.
- Core source đóng vì trust channel sai.
- Minh không thành mastermind.

### G5 — BỊ NHÌN THẤY
- Direct exposure làm chain/source mất trước preservation.
- Bắc bị cô lập khỏi khả năng tiếp tục, không cần combat ending.

### G3 — QUAY LƯNG QUÁ MUỘN
- Bắc đã N3 nhưng bỏ contact khi case chưa an toàn.
- Organization vẫn coi cậu unresolved risk.
- Consequence tập trung vào isolation/loss of agency, không phô bạo lực.

### G0 — MỘT CA LÀM THÊM
- Đã resolve ở S07, không chạy S18.

## FAILURE / CONSEQUENCE
Mọi ending là consequence, không “Mission Failed”.
Credits/ending screen chỉ sau cinematic ngắn.

## AUDIO ATMOSPHERE
Climax dựa vào:
- notification;
- phone call;
- paper/scan/custody;
- city continuing outside;
- sound motifs từ S04/S14.
True ending có thể giảm tension và trả lại ambience Hà Nội, không cần anthem thắng trận.

## CINEMATIC NOTES
Dùng intercut ngắn để cho thấy:
- record được preserve;
- access bị khóa;
- institution tách người liên quan;
- Nam/Khải phản ứng qua consequence.
Không mô tả/diễn bạo lực chi tiết.
Không villain arrest monologue.

## TRANSITION OUT
Ending screen + epilogue theo route → credits/menu.

## REPLAY VALUE
Player nhìn lại toàn game và nhận ra:
- sự thật ở đó từ đầu;
- mistake không phải “không đoán ra Nam sớm”;
- difference giữa routes là evidence custody, trust và timing.

---

# 1. ACT / CHAPTER MAP

| ACT | CHAPTER | SCENES | Chức năng |
|---|---|---|---|
| ACT I — Đời sống trước khi có vụ án | Ch.1 Người mới | S01–S02 | Bắc, trọ, trường, Nam/Lan/Linh/Minh |
| ACT I | Ch.2 Một ca ngắn | S03–S05 | Inciting E22, first anomaly, breather |
| ACT II — Tò mò có giá | Ch.3 Job bị audit | S06–S08 | Audit, curiosity gate, R1 |
| ACT III — Ba hộp sự thật | Ch.4 Từ một job tới một vụ việc | S09–S11 | Vũ, hospital, midpoint |
| ACT III | Ch.5 Sai người, đúng dữ kiện | S12–S13 | Tuấn/Hùng false apex, Khải layer |
| ACT IV — Hệ thống phản ứng | Ch.6 Cửa đang khép | S14–S15 | Cleanup pressure, preservation |
| ACT IV | Ch.7 Ai có quyền? | S16–S17 | Command proof, Nam payoff |
| ACT V — Ai giữ được sự thật trước? | Ch.8 Preservation | S18 | Climax + endings |

---

# 2. FULL GAME FLOW TABLE

| Scene | Location | Approx Time | Main Event | Major Clue | Branch | Tension |
|---|---|---:|---|---|---|---:|
| S01 | HUB B Trọ | 5m | Bắc chuyển trọ, gặp Nam | C27; C28 opt | — | 1/10 |
| S02 | HUB A Trường | 5m | Đời sinh viên, gặp Linh/Minh | C01; C07 opt | — | 1/10 |
| S03 | HUB A | 4m | Nhận ca Tân Lộ | C02 seed | — | 1/10 |
| S04 | Tân Lộ → đầu nhận | 6m | E22 hoàn tất, mismatch | C02; C03/C04 opt | — | 2/10 |
| S05 | Quán + HUB B | 4m | Breather; Nam biết Bắc là worker ở hậu trường | C29 char | — | 1–2/10 |
| S06 | HUB B / phone | 4m | Job bị audit | C05 opt | — | 3/10 |
| S07 | HUB B | 5m | Curiosity gate / day transition | C07; C35 conditional | G0 / leak seed | 3/10 |
| S08 | Tân Lộ | 6m | Reclassification được chứng minh | C17, C20, C22 seed | Delay risk | 4/10 |
| S09 | Police micro-set | 5m | Police entry | C10, C11A | preservation begins | 4/10 |
| S10 | Minh Trạch | 6m | Hospital pattern | C11 + C12/C15 | Delay risk | 5/10 |
| S11 | Police/meeting | 5m | Midpoint chronology | C08/C10/C11A | A route | 6/10 |
| S12 | Tân Lộ | 5m | Tuấn corrected, Hùng false apex | C20/C22; C18 opt | extra visit15m / wait30m after notice; private0 | 6/10 |
| S13 | Multi-source | 6m | A+B+C nối qua Khải | C24/C25/C26 | N3 / X | 7/10 |
| S14 | Multi-hub/phone | 5m | Access closures | C35–C37 opt; C43 | G2 risk | 8/10 |
| S15 | Police micro-set | 4m | Point of no return / custody | C42 | G3 / preservation | 8/10 |
| S16 | Police + manager source | 7m | Current command proof | C31 + C32 or C33/C34 | G4/G5/G6 setup | 8–9/10 |
| S17 | HUB B Trọ | 5m | Nam recontextualized | no new magic clue | exposure risk | 9/10 |
| S18 | Police + consequence montage | 6m | Preservation vs cleanup | C42 gate | G1–G6 | 10/10 |

**Focused main-route total: 93 phút.**

Notes:
- Strong/True route có thể lên ~98–105 phút vì inspect/source corroboration.
- Neutral G0 ngắn hơn đáng kể vì kết thúc ở S07.
- Không cộng thêm thời gian dream ngoài S07.
- Không cộng “đi bộ filler”; first-arrival travel đã nằm trong scene budgets.

---

# 3. CLUE DENSITY MAP

## Low clue / breathing
- S01: 1 biography seed + optional object.
- S02: employer/social seed.
- S05: intentionally no major clue.
- S06: one behavioral red herring.
- S17: no new proof, only recontextualization.

## Medium clue
- S03, S04, S07, S09, S11, S14, S15.

## High clue / reasoning
- S08: R1.
- S10: B.
- S12: C + innocent suspect correction.
- S13: X / Khải.
- S16: D.
- S18: no new evidence but high state density.

Rule: không thêm clue lớn vào S05/S17 chỉ vì production thấy “thiếu gameplay”.

---

# 4. CHARACTER SCREEN-TIME PLAN

## Bắc
100% playable perspective trừ short authored transitions.

## Nam
- S01: meaningful normal introduction.
- S05: brief normal reinforcement.
- S17: major payoff.
- S18: consequence only.
Không cần xuất hiện dày để “nhắc boss”.

## Lan
- S01 strong.
- S05 brief.
- S17 cameo.
- true epilogue.
Giữ hoàn toàn đời thường.

## Linh
- S02 strong.
- S05/S07/S15 short remote beats.
Không biến thành investigation sidekick.

## Minh
- S02/S03 normal.
- S07 trust decision.
- S14 betrayal payoff nếu conditional.
Không xuất hiện như villain.

## Vũ
- S09 entry.
- S10–S11 verify.
- S13–S18 tăng agency theo evidence.
Sau E38 phải chủ động hơn Bắc về police work.

## Tuấn
- S04, S06, S08, S12.
Arc: normal gatekeeper → suspicious → authority correction → still morally gray.

## Đức/Yến/Huyền/Thảo
Dùng như source windows, không ai phải có full subplot trong 90 phút.

## Khải/Hùng/Khoa/Hạnh
Screen time tiết chế.
Họ quan trọng vì causal role, không cần mỗi người một “boss scene”.

---

# 5. LOCATION REUSE AUDIT

## HUB B
S01 → S05 → S07 → S17 → epilogue.

Đây là reuse quan trọng nhất và phải được ưu tiên production quality.

Pass condition:
- geometry recognizable;
- lighting/time-of-day thay;
- props không tự đổi vô cớ;
- emotional meaning đổi vì context.

## HUB A
S02/S03 + optional Linh callbacks.
Không kéo conspiracy vào trường.

## Tân Lộ
S04/S08/S12 và state closures S14.
Dùng cùng shell, mở dần office/access area thay vì làm map mới.

## Minh Trạch
S10 + callbacks S13/S14.
Một institution bình thường, không dungeon.

## Police micro-set
S09/S11/S15/S18.
Rất production-efficient; value đến từ changing evidence state.

**Audit: PASS.** Không cần fifth major player map.

---

# 6. FAST TRAVEL AUDIT

Fast travel được mở sau khi player đã tới location ít nhất một lần.

Production rule:
- hub-to-hub transition = 5–15 giây authored;
- arrival card có time-of-day;
- only committed fixed-cost event groups/travel/deliberate waits advance objective clock once; reading/inspect/retries0;
- actual extra trip has visible departure/arrival cost; revisit inspection0 and charged trip/group not double-billed on save-load;
- S13+ ưu tiên phone/police verification để tránh fetch-quest.

**Audit: PASS.**

---

# 7. PUZZLE RHYTHM AUDIT

Puzzle-like interactions:

1. S08 — compare classification history.
2. S10 — compare review creation/scope versions.
3. S11 — timeline ordering.
4. S13 — match cross-cell endpoints/timing.
5. S15 — evidence provenance/custody choice.
6. S16 — distinguish relationship vs command + corroboration.

Khoảng cách giữa puzzle đủ có traversal/dialogue/breather.

Không dùng puzzle trong:
- S01/S02/S05;
- S14 danger beat;
- S17 emotional payoff;
- S18 như “final code”.

**Audit: PASS.**

---

# 8. DREAM FUNCTION AUDIT

Một dream duy nhất ở S07 là đủ.

Nó:
- đánh dấu D0→D+1;
- phản ánh anxiety;
- remix fact đã thấy.

Nó không:
- tạo clue;
- giải mystery;
- foreshadow boss bằng imagery gian lận;
- làm player không biết reality nào thật.

Nếu playtest thấy dream thừa, cut hoàn toàn không ảnh hưởng story state.

**Audit: PASS / OPTIONAL IMPLEMENTATION.**

---

# 9. CINEMATIC DENSITY AUDIT

Cinematic đáng làm:
- S03/S04 first travel/arrival.
- S07 micro-dream optional.
- S13 verification montage rất ngắn.
- S14 one access-closure beat.
- S18 consequence montage.

Cinematic không nên làm:
- monologue ở S11;
- boss reveal cutscene ở S17;
- raid playable/cinematic dài ở S18.

Target:
- phần lớn run vẫn là player-controlled first-person.
- không quá ~8–10 phút authored non-interactive tổng cộng.

**Audit: PASS.**

---

# 10. PACING AUDIT

## Opening
S01–S05 ≈ 24 phút.
Mystery có incident nhưng tone vẫn đời thường/operational.
Đạt yêu cầu opening đủ bình thường.

## Curiosity
S06–S08 ≈ 15 phút.
Player tự chọn bước từ audit issue sang chứng minh anomaly.

## Investigation build
S09–S13 ≈ 27 phút.
Tăng theo A/B/C/X; có false theory ở giữa để không thành exposition conveyor belt.

## Escalation/command
S14–S17 ≈ 21 phút.
Threat tăng qua access + custody + command, không qua combat.

## Climax
S18 ≈ 6 phút.
Ngắn, consequence-focused.

Total ≈ 93 phút.

**Audit: PASS.**

---

# 11. REPETITION AUDIT

Potential repetition:
- nhiều scene đọc record;
- nhiều NPC “không biết đủ”;
- nhiều access closure.

Mitigation:
- S08 = workplace classification;
- S10 = institutional review;
- S11 = chronology reasoning;
- S13 = relationship graph;
- S15 = custody decision;
- S16 = authority/corroboration.

Mỗi interaction có cognitive verb khác nhau:
**compare → verify → order → connect → preserve → prove.**

**Audit: PASS nếu UI/interaction không dùng cùng một panel copy-paste cho mọi scene.**

---

# 12. EXPOSITION AUDIT

Không NPC nào được kể toàn vụ.

- Vũ: procedure + verified facts.
- Phúc: source/coercion chronology.
- Huyền: hospital pattern.
- Thảo: insider hospital acknowledgment.
- Tuấn: operation/authority boundary.
- Đức: logistics irregularity.
- Yến: financial pattern.
- Khải: narrow risk facts.
- Hùng/Khoa/Hạnh: branch-specific.
- Nam: không confession.

Player hiểu network vì nguồn độc lập xác nhận nhau.

**Audit: PASS.**

---

# 13. PRODUCTION FEASIBILITY AUDIT

## Core environment count
1. HUB A school micro-hub.
2. HUB B boarding house.
3. Tân Lộ operational site.
4. Minh Trạch hospital micro-hub.
5. Police micro-set.
6. A few transition/exterior cards.

Không cần:
- full Hanoi;
- full hospital;
- full police station;
- full secret base;
- free-drive vehicles.

## Core systemic requirements
- dialogue/phone authored flow;
- notebook facts/sources;
- inspect;
- scene state manager;
- source-window state;
- evidence custody state;
- conditional access closures;
- fast travel/time transition;
- ending resolver.

## High-cost content to avoid
- large crowds;
- bespoke cinematic for every clue;
- complex stealth AI;
- combat;
- full-city simulation;
- unique map per source.

## Production risk
Cao nhất:
1. branching state QA;
2. making causal closures readable without UI timer;
3. making record interactions legible and not repetitive;
4. ensuring Vũ reacts correctly to actual evidence state.

Mitigation:
- data-driven clue/source state;
- automated resolver tests;
- scene-specific state fixtures;
- playtest matrix for G0–G6;
- provenance logs in debug build.

**Audit: FEASIBLE for a focused narrative game if environment scope is kept disciplined.**

---

# 14. ENDING QA MATRIX

| Route | Must test | Must NOT happen |
|---|---|---|
| G0 Neutral | player stops at S07 N1 | organization suddenly attacks |
| G1 Delay | last alternate A/B/C window closes | Vũ magically fills missing proof |
| G2 Wrong Trust | Minh leak causally closes last route | Minh revealed as secret member |
| G3 Avoidance | abandon after N3 before case safe | trigger from early N1 exit |
| G4 Cleanup | A+B+C safe, D late | game pretends police has nothing |
| G5 Exposure | direct disclosure breaks unpreserved chain | one harmless confront line instant-fails |
| G6 True | A+B+C+X+D1+D2 preserved in time | require C28/all optional clues |

---

# 15. FINAL STAGE 7 LOCKS

Stage 8 / Full Production Script được phép:
- viết full dialogue;
- viết stage direction;
- chia interaction beats;
- ghi exact authored phone UI copy;
- ghi cinematic shot intent;
- ghi NPC barks;
- ghi fail-forward response;
- ghi implementation hooks.

Stage 8 không được:
- đổi causal order;
- thêm boss confession;
- thêm magic file;
- biến Minh thành member;
- biến Tuấn thành core criminal;
- cho Huyền biết network trước evidence;
- cho Nam omniscient;
- để Vũ trì trệ sau threshold;
- biến S18 thành combat raid;
- thêm clue lớn vào S05 chỉ vì sợ “ít gameplay”;
- bắt player vào secret base để true ending;
- cho dream cung cấp fact;
- để fast travel phá source-window logic.

---

# 16. HANDOFF SUMMARY

Production spine:

**S01–S05: player sống trước khi player điều tra.  
S06–S08: một vấn đề công việc trở thành fact có chủ ý.  
S09–S11: police + hospital chứng minh crisis có trước Bắc.  
S12–S13: false apex bị sửa; three-box network hình thành.  
S14–S15: system reacts; custody trở thành gameplay.  
S16–S17: relationship được tách khỏi command; Nam được chứng minh chứ không “lộ mặt”.  
S18: preservation thắng hoặc thua cleanup theo causal state.**

Target focused runtime: **~93 phút**.

**END — CHAPTER / SCENE BREAKDOWN / STAGE 7**

### P4 S16/S18 state contract

S16 intake order: original receiver-side D2 reply, distinct D1 manager decision, execution and same-case broker annex authentication → normalize X_COMMAND (or independently X_RISK from C24/C25) → calculate C3/C4 from actual custody. A D source is never rejected because X was false before intake. S18 reads immutable earliest DECISIVE_LOSS only after real closure; two-slot partial states continue while a saving path exists. On terminal lock ABC=2/X=false is G1; ABCX=2/D-only ordinary loss is G4; decisive MINH or DIRECT loss of last D path is G2 or G5. Show preserved case records and source-specific consequences; a later harmless disclosure cannot change the culprit. Save/load persists event sequence, warning receipt, source paths, DECISIVE_LOSS and all custody flags atomically.
