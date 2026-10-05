# FULL PRODUCTION SCRIPT

> **Status:** STORY DESIGN — STAGE 8 / IN PROGRESS  
> **Completed in this revision:** ACT I — S01 đến S05  
> **Repository:** phambac2k701-blip/cot_truyen  
> **Setting:** Hà Nội, 2026  
> **Production rule:** triển khai trực tiếp từ SCENE_BREAKDOWN.md; không thay objective truth, clue graph, character knowledge hoặc ending logic.

## CANON PIN

Bản script này được viết sau khi đối chiếu toàn bộ các nguồn Stage 0–7:

- MASTER_GAME_BIBLE.md — c54f045db49e1523edf304165d2a8af09f5a45b2
- BACKSTAGE_CRIME_TRUTH.md — be6d0e99a961945849543db13212c4f23c60a60b
- CHARACTER_WEB.md — ce95ed982f7f45955c347b1e5b9499f9bd984bab
- OBJECTIVE_TIMELINE.md — ac7736c732fe36e5774d31a6630d39811eeb3ee8
- CLUE_GRAPH.md — 34f662d29487248a1c869ae180c2f83a7fb51e13
- PLAYER_STORY.md — 4e4dd484522d893ede0906ab11831f89fa12e081
- ENDING_LOGIC.md — 1bef4a82b6b9a0f6c7d47fe637773caf8783685c
- SCENE_BREAKDOWN.md — 5181bf635732db6c7571370a2f88371ebe55ffc6

## SCRIPT NOTATION

- [AUTO] = event tự chạy khi điều kiện đã đủ.
- [PLAYER] = hành động vẫn nằm trong quyền điều khiển của player.
- [CHOICE] = lựa chọn authored; chỉ thay state khi có ghi rõ.
- [PHONE] = nội dung hiển thị nguyên văn trên điện thoại.
- [NOTEBOOK] = nội dung notebook nguyên văn; chỉ ghi fact, source, thời gian, không suy luận thay player.
- [SFX] = âm thanh authored.
- [STATE] = thay đổi state ẩn.
- [CAMERA] = chỉ dẫn camera/cinematic ngắn.
- [DEV] = implementation note, không hiển thị cho player.

Không dùng cold open về tội phạm. Game bắt đầu ở đời sống của Bắc.

[DEV / CLOCK] OT §0.1–0.2 single OBJECTIVE_TIME: reading/inspect/phone UI/hints/retries/private hypotheses0. Fixed committed groups, real travel và deliberate wait have visible cost/arrival and persistent charged flag; save-load resumes without double charge/future receipts. Fixed montage seconds are presentation, not source deadline cost. The clock never advances because a reader waits on text.

---

# ACT I — ĐỜI SỐNG TRƯỚC KHI CÓ VỤ ÁN

# CHAPTER 1 — NGƯỜI MỚI

---

# S01 — PHÒNG TRỌ MỚI

## SCENE HEADER

- **Scene ID:** S01
- **Location:** HUB B — dãy trọ; phòng Bắc, hành lang, không gian chung, góc sửa đồ của Nam
- **Time:** D0,07:30–08:35 core65m, then explicit travel25m→school09:00
- **Required state:** New Game; BARC = N0; E19 đã xảy ra D−1 nhưng player không biết
- **Characters:** Bắc, Trần Thị Lan, Vũ Đức Nam, 1–2 hàng xóm nền không tên

## OPENING STAGE DIRECTION

Màn hình đen khoảng một giây. Âm thanh vào trước hình: tiếng xe máy ngoài ngõ, tiếng chổi quét nền xi măng, một cánh cửa sắt kéo nhẹ, tiếng quạt cũ quay lệch trục ở đâu đó.

Không nhạc bí ẩn.

Hình lên ở góc nhìn thứ nhất. Bắc đứng ngay cửa dãy trọ với một vali kéo, ba lô và một thùng carton nhỏ. Hành lang hẹp nhưng sạch ở mức bình thường; có vài đôi dép, móc áo, một chậu cây hơi héo và dây phơi chưa khô hẳn. Không gian không được dựng như nơi đáng sợ.

Ánh sáng sáng sớm đi từ đầu ngõ vào, hơi lạnh và phẳng. Trong phòng Bắc, ánh sáng tự nhiên đủ nhìn nhưng góc cuối phòng tối hơn vì cửa sổ nhỏ.

Bà Lan đang mở khóa phòng. Nam ngồi cách đó một đoạn ở góc sửa đồ chung, lưng hơi quay về phía Bắc, đang tháo vỏ một chiếc quạt bàn. Không có camera linger, music cue hoặc framing tách ông khỏi đời sống nền.

Điểm player spawn: ngưỡng cửa phòng, tay đang giữ quai thùng carton.

## PLAYER FLOW

### Beat 1 — Nhận phòng

[AUTO] Lan đẩy cửa, thử tay nắm rồi tránh sang một bên cho Bắc vào.

**LAN:**  
Phòng số ba. Khóa dưới hơi rít, kéo cửa sát vào rồi mới xoay. Không thì đứng vặn đến trưa cũng không mở được.

**BẮC:**  
Vâng.

**LAN:**  
Nhà tắm cuối hành lang. Rác để ngoài cổng trước tám giờ tối. Điện theo công tơ riêng, nước chia đầu người. Cái gì hỏng thì báo cô, đừng tự tháo xong lại bảo nó tự hỏng.

Nếu player nhìn sang chiếc tua vít đang thò khỏi ba lô:

**LAN:**  
Nhất là mấy đứa biết cầm tua vít ấy.

**BẮC:**  
Cháu chỉ sửa đồ của cháu thôi ạ.

**LAN:**  
Câu đấy cô nghe nhiều rồi.

Hài chỉ dừng ở đó, không kéo dài.

[PLAYER] Player có thể đặt vali, thùng carton và ba lô vào ba vị trí đánh dấu mềm. Không có reward khác nhau.

### Beat 2 — Hướng dẫn sinh hoạt

Khi player đi ra hành lang hoặc đứng quá lâu trong phòng, Lan tiếp tục.

**LAN:**  
Cổng tối mười một giờ cô khóa. Về muộn thì nhắn trước. Với dép để sát tường hộ cô, hành lang có tí thế này thôi.

**BẮC:**  
Cháu nhớ rồi ạ.

**LAN:**  
Mới lên Hà Nội à?

**BẮC:**  
Vâng. Hôm qua cháu mới chuyển đồ lên được một nửa.

**LAN:**  
Thế từ từ mà sắm. Phòng bé, mua nhiều rồi lại không có chỗ mà thở.

Lan chỉ vào công tơ, vòi nước và chỗ phơi. Không có thông tin plot.

### Beat 3 — Lỗi điện nhỏ

[PLAYER] Khi Bắc cắm sạc điện thoại hoặc bật quạt nhỏ trong phòng, nguồn chập chờn một lần. Đèn báo sạc tắt rồi sáng. Không có tia lửa lớn.

[SFX] Một tiếng “tạch” rất nhỏ.

**BẮC:**  
Ơ...

Lan từ ngoài cửa quay lại.

**LAN:**  
Lại cái ổ đấy à?

Lan cúi nhìn nhưng không chạm.

**LAN, gọi ra hành lang:**  
Chú Nam ơi, chú rảnh tay xem hộ tôi cái ổ phòng ba với.

Nam không xuất hiện theo kiểu entrance. Ông chỉ đặt chiếc vỏ quạt xuống, lau tay vào khăn cũ rồi đi sang.

**NAM:**  
Cắm cái gì thì nó mất điện?

**BẮC:**  
Sạc điện thoại thôi ạ.

**NAM:**  
Thế không phải quá tải.

Ông ngồi xuống, thử mặt ổ, nhìn đầu cắm của dây nối Bắc mang theo.

**NAM:**  
Ổ tường hơi lỏng. Cái ổ kéo của cháu cũng lỏng đầu cắm luôn.

**BẮC:**  
Cháu quấn tạm băng dính rồi ạ.

Nam nhìn lớp băng dính, không phán xét.

**NAM:**  
Ừ. “Tạm” nhìn khá lâu rồi đấy.

Lan cười khẽ.

**LAN:**  
Chú sửa hộ nó được thì sửa. Nó mới vào hôm nay, đừng để tối đầu tiên đã ngồi quạt bằng tay.

Nam siết lại mặt ổ tường, thử điện bằng dụng cụ nhỏ. Ông không diễn thao tác kỹ thuật quá lâu.

**NAM:**  
Ổ tường dùng được. Còn cái ổ kéo, nếu chưa cần ngay thì để chú thay đầu cắm. Chiều lấy.

**BẮC:**  
Có phiền chú không ạ?

**NAM:**  
Không. Mấy phút thôi.

Nam cầm ổ kéo cũ đi ra. Item chuyển location sang góc sửa đồ của Nam.

### Beat 4 — C27, biography tự nhiên

C27 phải guaranteed. Nếu player chủ động hỏi Nam “Chú làm điện à?”, dùng nhánh A. Nếu player không hỏi trong 6 giây, Lan tự nói nhánh B để fact vẫn xuất hiện.

#### Nhánh A — player hỏi

**BẮC:**  
Chú làm điện ạ?

**NAM:**  
Không hẳn. Trước chú làm kho vận. Có mấy năm công việc dính sang thiết bị với dịch vụ y tế. Nguồn, dây, máy móc hỏng vặt nhìn nhiều thì biết chút thôi.

**LAN:**  
Ông ấy nói “chút” thế thôi. Quạt nhà cô, nồi cơm phòng hai, cái khóa cổng... cái gì hỏng cũng bị kéo sang đây.

**NAM:**  
Thế nên người ta mới không cho chú nghỉ hẳn.

Nam nói như đùa nhẹ, trở về góc sửa đồ.

#### Nhánh B — player không hỏi

**LAN:**  
Cứ có gì điện đóm nhỏ thì hỏi chú Nam. Chú ấy trước làm kho vận, bên thiết bị y tế các kiểu, giờ rảnh tay hay sửa hộ mọi người.

**NAM:**  
Kho vận là chính. Đừng quảng cáo quá, lát lại có người bê tủ lạnh sang.

**LAN:**  
Tủ lạnh thì tôi gọi thợ.

C27 hoàn tất bằng fact đời thường, không nhấn mạnh.

### Beat 5 — Điện thoại và áp lực tiền

[PLAYER] Sau khi Lan rời phòng, điện thoại rung.

[PHONE — CHAT: Mẹ]

**07:18 — Mẹ:**  
Đến phòng chưa con?

**07:41 — Bắc:**  
Con đến rồi. Phòng ổn ạ.

**07:42 — Mẹ:**  
Thiếu gì thì bảo mẹ. Đừng tiết kiệm quá rồi ăn linh tinh.

Player có hai response flavor. Không thay state.

[CHOICE A] “Con đủ mà. Mẹ đi làm đi.”  
[CHOICE B] “Vâng. Con biết rồi.”

Nếu A:

**07:43 — Bắc:**  
Con đủ mà. Mẹ đi làm đi.

Nếu B:

**07:43 — Bắc:**  
Vâng. Con biết rồi.

Ngay sau đó, player có thể mở app ngân hàng.

[PHONE — NGÂN HÀNG]

**Số dư khả dụng: 1.386.000 ₫**

Không có popup bi kịch. Đây chỉ là con số.

[INNER MONOLOGUE — chỉ khi player nhìn số dư ít nhất 2 giây]

**BẮC:**  
Một triệu ba. Không đến mức hết tiền. Nhưng tiêu như ở nhà thì cuối tháng biết ngay.

Không thêm lời than.

### Beat 6 — Tự do inspect ngắn

Player có 60–90 giây tự do trước khi điện thoại báo giờ đi học.

## DIALOGUE

Ngoài các beat trên, bark tự nhiên:

Nếu Bắc chắn hành lang lúc Lan bê chổi:

**LAN:**  
Né cô tí nào. Phòng mới nhưng hành lang vẫn là của chung nhé.

Nếu Bắc nhìn Nam sửa quạt nhưng không tương tác:

**NAM:**  
Cái này không có gì hay đâu. Chỉ là bụi với hai con ốc lì thôi.

Nếu Bắc hỏi Nam sống phòng nào:

**NAM:**  
Chú ở phía trong. Có gì thì cứ gọi, nhưng nửa đêm mà là Wi‑Fi chậm thì chú chịu.

Nếu Bắc hỏi Lan về Nam:

**BẮC:**  
Chú Nam ở đây lâu chưa cô?

**LAN:**  
Lâu hơn mấy đứa thuê trọ bây giờ nhiều. Ít gây chuyện nhất dãy. Trừ chuyện để vít với dây điện đầy bàn.

Không dùng câu “chú ấy bí ẩn lắm” hoặc bất kỳ villain hint nào.

## INNER MONOLOGUE

Chỉ có hai line authored:

1. Khi nhìn số dư đủ lâu:  
   **“Một triệu ba. Không đến mức hết tiền. Nhưng tiêu như ở nhà thì cuối tháng biết ngay.”**

2. Khi đứng giữa phòng lần đầu sau khi Lan đi:  
   **“Ít nhất cũng có chỗ để đồ. Còn lại tính sau.”**

Không phát voice/text nếu player đang nói chuyện với NPC.

## PHONE CONTENT

Ngoài chat với Mẹ và app ngân hàng:

[PHONE — LỊCH]

**08:35 — Nhắc lịch:**  
Tiết đầu — 09:15  
Phòng học: A3-204  
Di chuyển dự kiến: 25 phút

[PHONE — NHÓM LỚP, chỉ là noise]

**08:01 — Nguyễn Ngọc Linh:**  
Ai tới A3 rồi cho hỏi cửa bên nào mở vậy 😭

**08:04 — Sinh viên ẩn danh:**  
Bên cầu thang B nhé.

Không tự động giới thiệu Linh bằng message; tên chỉ trở nên có nghĩa ở S02.

## INSPECTABLE OBJECTS

### O-S01-01 — Ổ cắm tường

- **Mô tả lần đầu:** Mặt ổ hơi xệ, có vết dùng lâu nhưng không cháy đen.
- **Observation:** Lỗi tiếp xúc nhỏ, Nam siết lại; không liên quan plot.
- **Notebook:** Không.
- **Clue value:** Environmental noise.
- **Revisit:** Sau Nam sửa: “Chắc hơn lúc nãy. Sạc không còn chập chờn.”

### O-S01-02 — Ổ kéo cũ của Bắc

- **Mô tả lần đầu:** Dây đã cũ, đầu cắm có một vòng băng dính đen do Bắc tự quấn.
- **Observation:** Nam xác định đầu cắm lỏng và mang đi thay.
- **Notebook:** Không.
- **Clue value:** Character grounding; tạo continuity item cho S05.
- **Item location:** Cuối S01 nằm ở góc sửa đồ Nam.
- **Revisit:** Không còn trong phòng cho tới S05.

### O-S01-03 — Góc sửa đồ của Nam

- **Mô tả lần đầu:** Bàn nhỏ có đồng hồ đo điện, hộp ốc, hai bo mạch cũ, cốc trà, vỏ quạt và vài hóa đơn gấp làm giấy kê. Phần lớn là đồ sửa thật.
- **Observation:** Nam có một hoạt động sửa đồ đời thường nhất quán.
- **Notebook:** Không.
- **Clue value:** C29 ở mức characterization, không đánh dấu clue.
- **Revisit:** S05 thêm ổ kéo của Bắc đã sửa; S17 giữ cùng geometry theo canon.

### O-S01-04 — Card cũ Tân Lộ, C28, OPTIONAL

Không highlight. Chỉ có prompt inspect nếu player chủ động nhìn gần bàn sửa.

- **Mô tả lần đầu:** Một card nhựa cũ đang kê dưới hộp ốc. Chữ còn đọc được: “TÂN LỘ LOGISTICS — Kho vận & giao nhận”. Thiết kế cũ, mép mòn, một số điện thoại đã bị gạch bút.
- **Observation:** Đây là vật nghề nghiệp cũ nằm lẫn trong nhiều giấy/card vô nghĩa khác. Không có tên Nam trên đó.
- **Notebook nếu player inspect:**  
  **People — Vũ Đức Nam / Ghi chú:**  
  “Ở góc sửa đồ có một card Tân Lộ Logistics cũ. Không rõ của chú Nam hay đồ dùng lại.”  
  **Source:** Quan sát trực tiếp, S01, buổi sáng.
- **Clue ID:** C28.
- **Clue value:** Delayed-value / relationship seed only. Không tăng COMMAND quá C1 về sau và tuyệt đối không chứng minh D.
- **Missable:** Có.
- **Mất lúc:** Không mất trong Act I; có thể vẫn ở đó về sau nếu scene access hợp lý.
- **Revisit trước khi biết Tân Lộ:** “Một card công ty cũ. Đang được dùng làm miếng kê.”
- **Revisit sau S03/S04 nếu player đã biết tên Tân Lộ:** “Cùng tên công ty mình vừa nhận ca. Có thể chỉ là đồ cũ từ công việc trước của chú Nam.” Không notebook auto-link mới.

### O-S01-05 — Hợp đồng/phong bì thuê trọ

- **Mô tả:** Hợp đồng thuê đơn giản, biên nhận cọc, số điện nước.
- **Observation:** Bà Lan quản lý trọ, Nam không phải chủ trọ.
- **Notebook:** Không.
- **Clue value:** Canon grounding / noise.
- **Revisit:** Không đổi.

## PUZZLE

Không có puzzle authored.

Không khóa scene bằng việc tìm C28 hoặc bất kỳ vật inspect nào.

## CINEMATIC

### Opening micro-cinematic

- **Trigger:** New Game.
- **Camera:** Black → first-person fade-in ở ngưỡng dãy trọ; 2–3 giây authored ổn định khung rồi trả toàn quyền nhìn cho player.
- **Blocking:** Lan mở cửa phòng; Nam ở nền, không quay đầu đúng lúc camera lên.
- **Animation:** Vali/thùng carton đặt xuống khi player bấm interact đầu tiên.
- **Dialogue:** Lan bắt đầu bằng “Phòng số ba...”
- **Audio:** Ambience ngõ vào trước hình. Không musical sting.
- **Transition:** Không title-card tội phạm; nếu game có logo/title, chỉ dùng rất nhỏ sau khi player đặt thùng xuống, không kèm tone ominous.

## BRANCH VARIANTS

### BV-S01-A — Player thân thiện với Nam

Nếu player chọn cảm ơn rõ ràng:

**BẮC:**  
Chiều cháu qua lấy. Cảm ơn chú ạ.

**NAM:**  
Ừ. Đi học đi, trễ tiết đầu lại đổ tại cái ổ cắm.

Không tăng special trust state; chỉ flavor.

### BV-S01-B — Player ít nói

Nếu player chỉ gật:

**NAM:**  
Chiều chú để ngoài bàn. Nhớ lấy.

Không diễn giải im lặng của Bắc như nghi ngờ.

### BV-S01-C — C28 seen

Chỉ set C28_SEEN. Nam không phản ứng vì Bắc nhìn thấy một card cũ nằm công khai.

## CLUE HANDLING

### C27 — nghề cũ của Nam

- **Lúc nhận:** Beat 4.
- **Source:** Nam tự nói + Lan xác nhận bề mặt.
- **Notebook update:**  
  **People — Vũ Đức Nam**  
  “Khoảng 60 tuổi. Ở dãy trọ lâu năm. Từng làm kho vận; có thời gian làm việc liên quan thiết bị/dịch vụ y tế. Hiện hay sửa đồ điện, điện tử nhỏ.”
- **Missable:** Không.
- **Mất lúc:** Không.
- **Giá trị:** Delayed-value; không phải command proof.

### C28 — vật Tân Lộ cũ

- **Lúc nhận:** Optional inspect Beat 6.
- **Notebook:** raw observation như O-S01-04.
- **Missable:** Có.
- **Mất lúc:** Không trong Act I; về late game access có thể không còn tự do.
- **Giá trị:** Delayed-value relationship seed only.

### C29 — kindness/ordinary life của Nam

- **Lúc nhận:** Toàn scene.
- **Notebook:** Không tạo clue card.
- **Missable:** Không về mặt characterization.
- **Giá trị:** Thematic delayed-value.

## SCENE EXIT

Khi player hoàn tất required ordinary beats và confirm departure: commit S01_CORE once65m07:30→08:35. Reading/inspect/idle không fire exit. [CLOCK CARD] **08:35 → 09:00 — tới trường, 25 phút.** Travel event charged once khi departure commit; các beats đã charged không lặp cost sau save-load.

[PHONE — LỊCH] rung một lần.

**Tiết đầu — 09:15. Đi ngay để kịp giờ.**

Primary objective đổi thành: **Đi tới trường.**

Lan đang quét hành lang.

**LAN:**  
Đi học đi cháu. Cửa cứ kéo lại là được.

Nếu Bắc đi ngang Nam:

**NAM:**  
Chiều chú để ổ kéo ở đây.

Bắc ra khỏi ngõ.

[CAMERA] First-person không cắt ngay. Đi được khoảng 3–4 mét, âm thanh dãy trọ lùi dần. Sau đó transition city 6–8 giây sang HUB A.

## CONTINUITY CHECK

- Bắc chỉ biết Nam là hàng xóm lớn tuổi có quá khứ kho vận/thiết bị y tế.
- Nam chỉ biết Bắc là sinh viên mới; BARC = N0.
- Nam chưa biết E22 liên quan Bắc vì E22 chưa xảy ra.
- Lan không biết network.
- Ổ kéo của Bắc đang ở bàn sửa Nam.
- C27 đã xuất hiện; C28 chỉ nếu inspect.
- C28 không được frame như evidence mạnh.
- Không có NPC nào nói Tân Lộ có vấn đề.
- Objective time đủ 20–30 phút để trọ → trường.

---

# S02 — BUỔI HỌC ĐẦU / NHỊP SINH VIÊN

## SCENE HEADER

- **Scene ID:** S02
- **Location:** HUB A — hành lang, lớp học, khu chung của trường
- **Time:** D0, 09:00–11:15
- **Required state:** S01 complete; C27 seen; BARC = N0
- **Characters:** Bắc, Nguyễn Ngọc Linh, Lê Gia Minh, sinh viên nền

## OPENING STAGE DIRECTION

Arrival ở cổng/khu hành lang trường, không phải establishing shot hoành tráng. Trường đông vừa phải: sinh viên dò phòng, tiếng dép/giày, cửa lớp, thông báo từ loa hoặc màn hình, xe ngoài cổng.

Ánh sáng buổi sáng đã sáng hơn S01. Không gian mở hơn dãy trọ để player cảm thấy nhịp “đời sống thật” bắt đầu.

NPC state:

- Linh đã vào gần cửa lớp, đang thử ổ cắm cạnh dãy ghế.
- Minh đến sau vài chục giây, cầm chai nước và sạc dự phòng.
- Cả hai chưa có quan hệ đặc biệt với Bắc.
- Không ai biết conspiracy.

Player spawn ở hành lang, cách cửa lớp khoảng 10–15 mét.

## PLAYER FLOW

### Beat 1 — Tìm phòng

[PLAYER] Player dò số phòng A3-204 bằng biển hành lang. Không có puzzle.

Khi Bắc tới cửa, Linh đang cúi cắm sạc laptop. Ổ điện không hoạt động.

**LINH:**  
Cậu ngồi đây à? Báo trước nhé, ổ này chỉ có tác dụng trang trí.

**BẮC:**  
Hỏng à?

**LINH:**  
Tôi cắm từ nãy. Nó nhìn tôi, tôi nhìn nó. Không ai có điện.

Bắc có thể chọn ngồi cạnh hoặc ghế phía sau; conversation vẫn trigger.

**LINH:**  
Nguyễn Ngọc Linh.

**BẮC:**  
Bắc.

**LINH:**  
Mới lên à? Nhìn cái mặt dò phòng là biết.

**BẮC:**  
Rõ thế à?

**LINH:**  
Tôi sáng nay đi nhầm một tầng rồi. Người cùng cảnh nhận ra nhau nhanh lắm.

Hài dừng tự nhiên.

### Beat 2 — Minh vào lớp

Minh đi tới, nhìn quanh.

**MINH:**  
Ở đây còn chỗ không?

**LINH:**  
Còn. Nhưng không có điện.

**MINH:**  
Tuyệt. Tôi mang sạc dự phòng để làm cảnh.

Minh ngồi.

**MINH:**  
Minh. Ông là Bắc đúng không? Nãy nhóm lớp có người gọi tên.

**BẮC:**  
Ừ.

**MINH:**  
Mới chuyển trọ lên à?

**BẮC:**  
Sáng nay mới nhận phòng.

**MINH:**  
Nhanh thế. Tôi lên trước ba ngày còn chưa biết quán cơm nào không làm mình phá sản.

**LINH:**  
Quán dưới ngõ sau. Cơm bình thường, giá cũng bình thường. Đấy là review tốt nhất tôi có.

### Beat 3 — Class-life montage interactive

[AUTO] Giảng viên vào. Không cần viết bài giảng dài. Chỉ dùng 2–3 short barks và player interaction:

- mở file bài học;
- chụp/nhận ảnh slide nếu cần;
- chuyển sang chế độ note;
- một thông báo deadline.

[PHONE — NHÓM LỚP]

**10:12 — Nguyễn Ngọc Linh:**  
Ai chụp được slide cuối gửi với, máy chiếu vừa nuốt mất nửa dòng.

**10:13 — Lê Gia Minh:**  
Tôi chụp được đúng cái đầu người ngồi trước.

**10:13 — Nguyễn Ngọc Linh:**  
Rất có giá trị học thuật.

Bắc có thể gửi ảnh nếu player chụp.

Không có clue plot.

### Beat 4 — Tiền và việc làm

Sau tiết, ba người ra khu chung/quán nhỏ.

Bắc nhìn menu rồi chọn món rẻ hơn. Không ép camera vào giá.

**MINH:**  
Ông mới lên mà đã nhìn bảng giá như đang kiểm toán thế?

**BẮC:**  
Tính xem sống được tới cuối tháng không thôi.

**LINH:**  
Ngày đầu đại học, mục tiêu khiêm tốn ghê.

**BẮC:**  
Sống được rồi tính mục tiêu lớn sau.

Minh uống nước.

**MINH:**  
Ông có kiếm việc theo ca không? Bên Tân Lộ thỉnh thoảng thiếu người. Kho, giấy tờ, giao mấy cuốc ngắn. Rảnh thì nhận, không rảnh thì thôi.

**BẮC:**  
Tân Lộ?

**MINH:**  
Logistics. Công ty thật, không phải cái nhóm “việc nhẹ lương cao inbox riêng” đâu.

**LINH:**  
Câu “công ty thật” nghe đáng tin một cách rất cố gắng.

**MINH:**  
Tôi làm rồi mà. Chán thôi, chứ trả đúng.

C01 mở.

[PHONE — LINK MINH GỬI]

**TÂN LỘ LOGISTICS — CỘNG TÁC VIÊN THEO CA**  
Công việc thường gặp: phân loại, hỗ trợ kho, bàn giao hồ sơ/hàng nhẹ.  
Đăng ký theo ca.  
Thanh toán sau đối soát.  
Yêu cầu: xác minh tài khoản và tuân thủ hướng dẫn bàn giao.

Không có wording mờ ám.

### Beat 5 — C07 optional trong S02

Nếu player chọn “Ông làm bên này rồi à?”:

**BẮC:**  
Ông làm bên này rồi à?

**MINH:**  
Hai ca. Một ca đóng sách, một ca phụ kho. Muốn xem không?

Minh cho Bắc nhìn lịch sử một ca.

[PHONE — MÀN HÌNH MINH, C07]

**TÂN LỘ CTV — 15/09**  
Ca: 18:00–21:00  
Khu: Kho C2  
Việc: Đóng gói tài liệu / hàng nhẹ  
Công: 180.000 ₫  
Trạng thái: Đã thanh toán — 21:26

**MINH:**  
Đấy. Không có bí mật gì. Có mỗi bí mật là ba tiếng đứng nhiều hơn tưởng tượng.

**LINH:**  
Thế mà vẫn quảng cáo cho người khác.

**MINH:**  
Chia sẻ cơ hội phát triển cột sống.

Nếu player không hỏi, C07 chưa được ghi ở đây; S07 sẽ có route guaranteed/equivalent để fairness betrayal.

### Beat 6 — Kết

Minh gửi link. Bắc lưu lại.

**MINH:**  
Có ca hợp thì app nó hiện. Ông đừng nhận giờ trùng học là được.

**LINH:**  
Tôi xin bổ sung: đừng nhận giờ trùng ngủ nữa.

**BẮC:**  
Ngủ cũng có lịch à?

**LINH:**  
Từ tuần sau sẽ có.

## DIALOGUE

Barks nền:

Sinh viên nền 1:  
“Phòng này chiều học tiếp không nhỉ?”

Sinh viên nền 2:  
“Không biết. Nhóm lớp im như chưa từng tồn tại.”

Nếu player hỏi Linh có từng làm Tân Lộ:

**LINH:**  
Chưa. Tôi mới lo nổi lịch học thôi. Việc làm thêm để tương lai Linh giải quyết.

Nếu player hỏi Minh có quen quản lý:

**MINH:**  
Không. App với người điều phối thôi. Tôi đi ca xong là về.

Quan trọng: Minh không có “connection” bí mật.

## INNER MONOLOGUE

Khi Bắc nhìn link tuyển hơn 2 giây:

**BẮC:**  
Theo ca thì đỡ vướng lịch. Thử xem có gì hợp.

Không có inner monologue nghi ngờ Tân Lộ.

## PHONE CONTENT

### C01 — listing

Nội dung như Beat 4.

### School notification, noise

**10:48 — Cổng sinh viên:**  
Học phần nhập môn — tài liệu tuần 1 đã được cập nhật.

### Linh gửi file

**11:02 — Linh:**  
File slide sáng nay. Tôi chụp hơi lệch trang 6.

**11:03 — Bắc:**  
Cảm ơn nhé.

Nếu player chọn response vui:

**11:03 — Bắc:**  
Trang 6 nhìn vẫn sống được.

**11:03 — Linh:**  
Tiêu chuẩn hôm nay của ông thấp thật.

## INSPECTABLE OBJECTS

### O-S02-01 — Ổ điện chết cạnh ghế

- **Mô tả:** Ổ cắm cũ không có điện.
- **Observation:** Dùng cho đời sống, không plot.
- **Notebook:** Không.
- **Clue value:** Noise / character banter.
- **Revisit:** Không đổi.

### O-S02-02 — Bảng thông báo việc làm sinh viên

- **Mô tả:** Có nhiều tin gia sư, phục vụ quán, nhập liệu, CTV sự kiện; Tân Lộ chỉ là một trong nhiều lựa chọn.
- **Observation:** Tân Lộ không được đặt riêng giữa màn hình.
- **Notebook:** Không.
- **Clue value:** Environmental noise bảo vệ fairness.
- **Revisit:** Không đổi trong Act I.

### O-S02-03 — Link Tân Lộ CTV

- **Mô tả:** Listing công việc chuẩn, ngắn, không hứa hẹn vô lý.
- **Observation:** C01.
- **Notebook:**  
  **Organization — Tân Lộ Logistics**  
  “Công ty logistics có kênh tuyển cộng tác viên theo ca cho kho, hồ sơ và hàng nhẹ. Minh từng biết/nhận việc qua kênh này.”  
- **Clue ID:** C01.
- **Clue value:** Mandatory fairness clue: công ty part-time là thật.
- **Missable:** Không.
- **Revisit:** S03 thêm assignment cụ thể; không đổi nghĩa thành “front company”.

### O-S02-04 — Lịch sử ca cũ của Minh

- **Mô tả:** Ca kho bình thường, đã thanh toán đúng.
- **Observation:** Minh có lịch sử dùng kênh part-time thật.
- **Notebook nếu inspect:**  
  “Minh từng nhận ít nhất một ca Tân Lộ bình thường và được thanh toán.”  
- **Clue ID:** C07.
- **Clue value:** Delayed correction cho RH4; không chứng minh Minh luôn đáng tin.
- **Missable:** Có ở S02.
- **Revisit:** Nếu chưa seen, S07 phải cung cấp equivalent.

## PUZZLE

Không có puzzle authored.

## CINEMATIC

Không có cutscene riêng.

First arrival transition kết thúc bằng 1–2 giây wide first-person look ở hành lang rồi trả control. Không dùng montage dài.

## BRANCH VARIANTS

### BV-S02-A — Bắc không nói mình thiếu tiền

Nếu player né:

**MINH:**  
Ông có kiếm việc theo ca không? Tôi thấy ông vừa save cái bảng tuyển kia.

Bắc vẫn có motive thể hiện qua hành vi/menu/balance, không cần confession.

### BV-S02-B — C07 seen

Set C07_SEEN. S07 không cần lặp full historical screen; chỉ có thể nhắc “ca cũ của Minh trông hoàn toàn bình thường.”

### BV-S02-C — C07 not seen

Không phạt. S07 sẽ mở lại bằng việc Bắc hỏi trực tiếp khi audit xảy ra.

## CLUE HANDLING

### C01

- **Lúc nhận:** Beat 4.
- **Notebook:** Organization entry raw fact.
- **Missable:** Không.
- **Mất lúc:** Không.
- **Giá trị:** Fairness; chứng minh Bắc có lý do bình thường nhận việc.

### C07

- **Lúc nhận:** Beat 5 nếu hỏi.
- **Notebook:** Raw work-history note.
- **Missable:** Có ở S02; recover guaranteed/equivalent ở S07.
- **Mất lúc:** Không.
- **Giá trị:** Delayed-value; chống interpretation “Minh là plant”.

## SCENE EXIT

Khi required class/meal group đã hoàn tất và player confirm rời khu ăn, commit S02_CORE once135m09:00→11:15; queued phone/Minh beat chạy từ event completion, không UI idle hoặc mở phone sau elapsed11:10. Reading/phone review0. Minh nói:

**MINH:**  
Nếu lát có ca nào gần đây tôi gửi. Ông tự xem giờ nhé.

**BẮC:**  
Ừ.

Primary objective chuyển: **Ăn trưa / xem lịch trước tiết sau.**

S03 bắt đầu trong cùng HUB A, không loading scene cứng nếu production có thể nối liền.

## CONTINUITY CHECK

- Bắc biết Tân Lộ là employer logistics bình thường.
- Minh chỉ biết kênh part-time.
- Linh không biết mystery.
- Nam không xuất hiện và chưa biết Bắc liên quan Tân Lộ.
- BARC vẫn N0.
- C01 guaranteed, C07 optional.
- Không clue nào nói job nhạy cảm.
- Objective time vẫn đủ để Bắc ở trường tới khoảng 11:15.

---

# CHAPTER 2 — MỘT CA NGẮN

# S03 — MỘT CA NGẮN

## SCENE HEADER

- **Scene ID:** S03
- **Location:** HUB A — khu ăn/quán sinh viên + phone UI; transition tới Tân Lộ
- **Time:** D0, core11:15–11:49; travel35m→12:24/check-in6m→12:30
- **Required state:** S02 complete; C01 seen; BARC = N0
- **Characters:** Bắc, Minh; nhân viên hỗ trợ Tân Lộ chỉ qua app nếu cần

## OPENING STAGE DIRECTION

Bắc ngồi ở bàn nhỏ ngoài khu ăn hoặc đứng ở hành lang có ghế. Lớp đã tan. Âm thanh trưa: xe cộ rõ hơn, quạt quán, tiếng khay/đũa, sinh viên gọi món.

Ánh sáng trưa gắt hơn nhưng không stylized.

Minh ở bàn gần đó, đang lướt điện thoại. Linh đã rời đi hoặc đang ở xa, không cần ở scene để tránh mọi beat đều có đủ nhóm bạn.

Điểm player spawn: điện thoại để trên bàn, màn hình khóa.

## PLAYER FLOW

### Beat 1 — Ca xuất hiện

Điện thoại rung.

[PHONE — CHAT: Minh]

**11:18 — Minh:**  
Có ca ngắn bên Tân Lộ này. 12:30 nhận, tầm 2h xong. Ông rảnh thì hốt.

**11:18 — Minh:**  
[Chia sẻ ca TL-2604-117]

Player mở card.

[PHONE — TÂN LỘ WORKER]

**Mã ca:** TL-2604-117  
**Thời gian:** 12:30–14:10  
**Điểm nhận:** Tân Lộ — Điểm điều phối 2  
**Công việc:** Bàn giao hồ sơ / hàng hành chính kín  
**Nhóm khách hàng:** Y tế / Ưu tiên  
**Yêu cầu:** Giao đúng người nhận; proof-of-handover; không mở kiện  
**Thù lao:** 240.000 ₫ + hỗ trợ di chuyển  
**Trạng thái:** Mở cho CTV  
**Tạo lúc:** D−1, 18:42

C02 seed. UI không đổi màu field “Y tế / Ưu tiên”.

### Beat 2 — Practical check

Player có thể:

- mở lịch học;
- mở ngân hàng;
- hỏi Minh;
- accept ngay;
- chọn “Để tôi xem đã”.

Nếu hỏi Minh:

**BẮC:**  
Ca này giao cái gì?

**MINH:**  
Ghi hồ sơ/hàng hành chính thì chắc phong bì hoặc túi tài liệu. Tôi chưa nhận ca kiểu này, nhưng app có thì cứ theo app thôi.

**BẮC:**  
Hai trăm bốn mươi cho hơn tiếng rưỡi?

**MINH:**  
Có chạy đường với giao đúng giờ nữa. Cao hơn kho tí chứ chưa tới mức ông đổi đời.

Nếu player hỏi “Y tế / Ưu tiên là gì?”:

**MINH:**  
Nhóm khách hàng thôi chắc. Bên logistics có khách bệnh viện, phòng khám suốt mà.

Minh không biết hơn.

### Beat 3 — Hesitation branch

Nếu player chọn “Để tôi xem đã”:

[PHONE] Card thu nhỏ, vẫn hiện “Còn 1 vị trí”.

Bắc có thể mở app ngân hàng: số dư vẫn khoảng 1.386.000 ₫ trừ chi tiêu buổi sáng, tùy hệ thống kinh tế nếu có. Script không bắt UI phải trừ chính xác từng bữa nếu game không simulation.

[INNER MONOLOGUE]

**BẮC:**  
Không trùng tiết. Làm xong vẫn về kịp.

Khi player intentional quay lại card sau hesitation choice, Minh nói; wall-clock20–30 giây không trigger event/clock. Revisit card và đọc ngân hàng0 phút thêm:

**MINH:**  
Không nhận thì thôi nhé, ca kiểu này lát có người khác lấy.

Không pressure bí ẩn.

[DEV] Player có thể từ chối tạm, nhưng Stage 8 không tạo ending tại đây. Để tiếp tục main story, assignment còn mở đủ lâu cho player reconsider. Nếu production muốn không có pseudo-choice, biến “Để tôi xem đã” thành flavor rồi yêu cầu accept để rời scene.

### Beat 4 — Accept

[PLAYER] Tap “Nhận ca”.

[PHONE — TÂN LỘ WORKER]

**Đã nhận ca TL-2604-117.**  
Check-in tại Điểm điều phối 2 trước 12:30.  
Mang theo điện thoại có ứng dụng Worker.  
Không tự mở kiện/hồ sơ.

**MINH:**  
Xong nhớ chụp proof đủ. Bên đấy thiếu một ảnh là đối soát lâu lắm.

**BẮC:**  
Ông từng bị rồi à?

**MINH:**  
Một lần. Mất hai ngày mới về tiền. Bài học rất đắt giá: chụp cả mấy thứ mình nghĩ không cần chụp.

Câu này chỉ về quy trình, không foreshadow “evidence”.

## DIALOGUE

Nếu player nhận ngay:

**MINH:**  
Nhanh thế.

**BẮC:**  
Không trùng lịch.

**MINH:**  
Tốt. Tôi mà có lịch trống là tôi nhận rồi.

Nếu player nói “Tôi cần tiền”:

**BẮC:**  
Có thêm hai trăm cũng đỡ.

**MINH:**  
Chuẩn. Tháng đầu cái gì cũng “có thêm hai trăm cũng đỡ”.

Không có thoại về tội phạm.

## INNER MONOLOGUE

Khi accept:

**BẮC:**  
Một ca thôi. Làm xong về học tiếp.

Không dùng “có gì đó lạ”.

## PHONE CONTENT

Toàn bộ assignment card ở Beat 1 là canonical exact UI copy của S03.

[PHONE — LỊCH, nếu mở]

**14:30–16:00:** Trống  
**19:00:** Tự học / chưa có lịch cố định

Không tạo continuity với user’s real timetable; đây là timetable nhân vật trong fiction, không phải dữ liệu người dùng.

## INSPECTABLE OBJECTS

### O-S03-01 — Assignment TL-2604-117

- **Mô tả lần đầu:** Job card như một ca CTV bình thường, có field y tế/ưu tiên.
- **Observation:** C02.
- **Notebook auto:**  
  **Event — Ca TL-2604-117**  
  “12:30–14:10. Tân Lộ. Bàn giao hồ sơ/hàng hành chính kín. Nhóm khách hàng: Y tế / Ưu tiên. Ca nằm trong pool CTV. Tạo lúc D−1, 18:42.”  
- **Clue ID:** C02.
- **Clue value:** Mandatory delayed-value seed.
- **Missable:** Ý nghĩa có thể bị bỏ qua, nhưng raw assignment vẫn nằm trong app/notebook.
- **Mất lúc:** Không trong game window; access về sau có thể thay, nhưng notebook raw fact còn.
- **Revisit ở S04:** Giữ nguyên.
- **Revisit sau audit:** Player có thể thấy cùng fact nhưng context thay; notebook không auto kết luận.

### O-S03-02 — Balance screen

- **Mô tả:** Số dư sau các chi tiêu đầu ngày.
- **Observation:** Motive tiền.
- **Notebook:** Không.
- **Clue value:** Character only.
- **Revisit:** Có thể thay theo economy UI, không plot-critical.

## PUZZLE

Không có puzzle.

Đọc kỹ assignment không phải puzzle và không yêu cầu memorization; notebook giữ raw fields.

## CINEMATIC

### First travel to Tân Lộ

- **Trigger:** Player accept job và confirm “Đi tới điểm nhận”; S03_CORE charged once34m11:15→11:49; visible travel **11:49→12:24,35 phút**, rồi check-in6m→12:30. Phone inspect/hesitation reading0, không hidden acceptance timer.
- **Camera:** First-person leave khu sinh viên → 6–10 giây authored travel montage: vạch đường, xe buýt/xe máy ngoài cửa kính tùy phương tiện production chọn, biển đường không cần đọc rõ.
- **Blocking:** Không có NPC plot trong montage.
- **Animation:** Bắc cất điện thoại, chỉnh ba lô.
- **Dialogue:** Không.
- **Audio:** City traffic; không thriller cue.
- **Transition:** Time card nhỏ: “12:24 — Tân Lộ, Điểm điều phối 2.”

## BRANCH VARIANTS

### BV-S03-A — C07 đã seen

Nếu player mở profile Minh trong lúc xem job, notebook có thể hiển thị ca cũ đã thanh toán. Không dialogue mới.

### BV-S03-B — C07 chưa seen

Không thêm. Main fairness vẫn được xử lý ở S07.

### BV-S03-C — Player hỏi quá kỹ về “Y tế”

Minh chỉ biết interpretation bình thường:

**MINH:**  
Ông đang hỏi tôi như tôi làm kế toán bên đấy ấy. Tôi chỉ từng đóng hàng thôi.

Giới hạn knowledge rõ, tự nhiên.

## CLUE HANDLING

### C02

- **Lúc nhận:** mở assignment.
- **Notebook:** Event raw fact.
- **Missable:** Không ở mức existence; player có thể không chú ý.
- **Mất lúc:** Raw assignment không mất trước S08; access có thể bị hạn chế sau cleanup.
- **Giá trị:** Seed R1; không chứng minh crime.

## SCENE EXIT

Sau accept, objective:

**Tới Tân Lộ trước 12:30.**

Transition first-arrival chạy.

Scene kết ở thời điểm Bắc bước vào khu điều phối, trả control trực tiếp cho S04.

## CONTINUITY CHECK

- Hùng đã reclass job từ D−1; Bắc không biết.
- Minh không biết lý do job tồn tại.
- Không ai gọi riêng Bắc.
- Bắc vào pool vì thiếu tiền + ca hợp lịch.
- Nam vẫn chưa biết Bắc là worker E22; E22 chưa hoàn tất.
- C02 đã xuất hiện, chưa có C03/C04.
- Travel buffer từ trường tới Tân Lộ được giữ.

---

# S04 — GIAO XONG NHƯNG HƠI LỆCH

## SCENE HEADER

- **Scene ID:** S04
- **Location:** SITE C — Tân Lộ / Điểm điều phối 2 → điểm nhận hành chính thuộc chuỗi Minh Trạch
- **Time:** D0, 12:30–14:10
- **Required state:** JOB_ACCEPTED = true; JOB_E22_SEEN = true; BARC = N0 lúc bắt đầu
- **Characters:** Bắc, Đỗ Minh Tuấn, nhân viên Tân Lộ vô tội, nhân viên đầu nhận vô tội

## OPENING STAGE DIRECTION

Tân Lộ phải trông như một công ty thật đang làm việc thật.

Khu điều phối không sạch bóng như văn phòng quảng cáo: có xe đẩy, scanner, bảng chuyến, thùng carton, túi hồ sơ, nhân viên gọi nhau xác nhận ca. Phần lớn đơn nhìn bình thường. Một thùng thiết bị văn phòng, vài kiện vật tư y tế có nhãn hợp pháp, túi tài liệu doanh nghiệp.

Ánh sáng trắng thực dụng. Không có khu “bí mật” nhìn thấy được.

Tuấn đứng sau quầy phụ, vừa nghe điện thoại vừa kiểm tra danh sách. Anh bận và hơi thiếu kiên nhẫn nhưng không hostily watch Bắc.

Player spawn ngay sau cửa check-in.

## PLAYER FLOW

### Beat 1 — Check-in

[PLAYER] Quét QR/check-in.

[SFX] Scanner beep bình thường.

Nhân viên quầy:

**NHÂN VIÊN TÂN LỘ:**  
Bắc, mã 117 đúng không? Đợi em một tí.

Tuấn nhìn màn hình.

**TUẤN:**  
CTV mới?

**BẮC:**  
Vâng.

**TUẤN:**  
Mã 117. Nhận ở quầy ba. Chụp tình trạng niêm phong trước khi đi, giao đúng người hệ thống chỉ định, đủ proof rồi mới bấm hoàn tất.

**BẮC:**  
Trên app ghi “Y tế / Ưu tiên” mà vẫn là ca CTV ạ?

Tuấn liếc nhanh field.

**TUẤN:**  
Hệ thống đã đẩy vào pool thì cứ theo assignment. Nhóm khách hàng không đổi cách em giao. Có gì lệch ở điểm nhận thì gọi điều phối, đừng tự xử.

Đây là fact từ layer của Tuấn, không phải cover-up core crime.

### Beat 2 — Nhận pouch

Nhân viên quầy đặt một túi hồ sơ kín cỡ A4 dày, niêm phong bằng dải keo bảo mật. Không có máu, vật y tế ghê rợn, organ imagery.

[PLAYER] Player xác nhận mã TL-2604-117.

C02 hiện lại.

Optional inspect C04 ở mép routing label.

Nếu player xoay item:

- nhãn hiện tại: “CTV / GIAO TRỰC TIẾP — ƯU TIÊN”
- dưới mép nhãn mới có một phần nhãn cũ màu nhạt: “NỘI BỘ — ƯU TIÊN”

Không có chữ “bí mật”, “cấm”, “organ”.

Nếu player hỏi nhân viên quầy về nhãn:

**BẮC:**  
Nhãn này dán lại à anh?

**NHÂN VIÊN TÂN LỘ:**  
Chắc đổi tuyến. Bên điều phối in lại suốt. Mã hệ thống khớp là được.

Nếu Tuấn nghe:

**TUẤN:**  
Chụp trước khi đi. Có chuyện gì thì ảnh còn đó.

Câu này là quy trình bình thường.

[PHONE / MEDIA — PROOF PHOTO] Ảnh proof mặc định authored chỉ chụp dải niêm phong và mặt túi trống; routing label nằm ngoài khung nên không đọc được. Ảnh này không recover C04. Optional action **Chụp thêm nhãn vận hành** tạo ảnh authored rõ nhãn CTV và phần nhãn Nội bộ bên dưới, không cần pixel aim; giữ content cố định trong Media. Direct inspect hoặc intentional later mở ảnh nhãn này cho cùng C04 raw fact/observed_at; chỉ save ảnh mà chưa đọc không tự cấp inference. Cùng ảnh trên replay luôn cùng facts.

### Beat 3 — C06 noise

Trước khi rời, player có thể nhìn bảng job gần quầy:

- “Phòng khám An Tâm — vật tư văn phòng — hoàn tất”
- “Công ty Thiên Hà — hợp đồng giấy — đang giao”
- “Kho D2 — phụ kiện máy in — chờ tài xế”
- một đơn y tế khác do tài xế thường xử lý

Không có clue hidden trong các dòng này.

### Beat 4 — Travel

[CAMERA] Short authored travel 8–12 giây, đủ giữ 25+ phút objective time bằng time card.

**12:47 — Đang di chuyển**  
**13:24 — Điểm tiếp nhận hành chính Minh Trạch**

Không bắt player lái xe.

### Beat 5 — Bàn giao và mismatch nhỏ

Điểm nhận là khu hành chính/giao nhận, không phải phòng mổ. Nhân viên tiếp nhận mặc đồng phục hành chính, đang xử lý nhiều hồ sơ.

**NHÂN VIÊN TIẾP NHẬN:**  
Mã đơn?

**BẮC:**  
TL-2604-117.

Nhân viên scan.

[SFX] Beep, rồi một âm báo khác rất ngắn, không horror.

Nhân viên nhìn màn hình.

**NHÂN VIÊN TIẾP NHẬN:**  
Ơ... nhóm nội bộ à?

**BẮC:**  
Trên app của em là giao CTV.

Nhân viên kiểm tra lại.

**NHÂN VIÊN TIẾP NHẬN:**  
Ừm. Mã vẫn hợp lệ. Đợi chị một tí.

Cô gọi một cuộc nội bộ ngắn, player chỉ nghe một phía.

**NHÂN VIÊN TIẾP NHẬN, qua điện thoại:**  
Em có mã 117... vâng... hệ thống bên em đang hiện nhóm nội bộ cũ. Bên giao là CTV... dạ... rồi, em nhận.

Cúp máy.

**NHÂN VIÊN TIẾP NHẬN:**  
Xong rồi. Chắc bên điều phối đổi luồng mà hệ bên chị cập nhật chậm. Em ký trên máy này nhé.

Nếu player hỏi:

**BẮC:**  
Có vấn đề gì không chị?

**NHÂN VIÊN TIẾP NHẬN:**  
Không. Khác nhóm xử lý thôi. Hệ thống cho nhận là được.

Không ai hoảng.

### Beat 6 — Proof-of-handover, C03

Sau chữ ký điện tử:

[PHONE — TÂN LỘ WORKER]

**TL-2604-117 — HOÀN TẤT BÀN GIAO**  
Khách hàng: **Minh Trạch — Hành chính**  
Điểm nhận: **Bàn giao nội bộ B**  
Thời gian: **13:52**  
Người nhận: **NV Q.H.**  
Tình trạng: **Niêm phong nguyên vẹn**  
Đối soát: **Đang xử lý**

Player có thể mở “Chi tiết” để C03 vào notebook. Không bắt chụp màn hình pixel-perfect.

Nếu chưa mở Chi tiết, C03_SAVED còn false vì chưa intentional inspect; receipt vẫn tồn tại trong worker history. Later mở cùng live receipt khi access còn đặt C03_SAVED/OBSERVED_AT với cùng raw client/account/recipient và original handover time 13:52, chỉ thời điểm quan sát mới. Không auto-award khi mở app, không early-click gate.

### Beat 7 — Hoàn tất

Bắc bước ra khu nhận.

[INNER MONOLOGUE, chỉ nếu player đã thấy C04 hoặc hỏi về mismatch]

**BẮC:**  
Chắc họ đổi tuyến thật. Giao xong là xong.

Nếu player không inspect gì, không phát line này.

## DIALOGUE

### Tuấn bark nếu Bắc quay lại hỏi trước khi rời

**BẮC:**  
Anh có cần em hỏi lại chỗ nhận gì không?

**TUẤN:**  
Không. Em làm đúng app là được. Có lỗi hệ thống thì bên anh xử.

### Tuấn nếu player hỏi tên người đổi tuyến

**BẮC:**  
Ai đổi luồng thì anh có biết không?

**TUẤN:**  
Anh không xem lịch sử phân quyền ngay ở quầy. Với ca của em, việc cần làm là giao đúng và đủ proof.

Không phải evasive villain line; đúng vai trò.

### Nhân viên tiếp nhận nếu player nhìn xung quanh lâu

**NHÂN VIÊN TIẾP NHẬN:**  
Em cần biên nhận giấy không? Không thì app có bản điện tử rồi.

## INNER MONOLOGUE

Chỉ line normalization ở Beat 7 khi player có lý do nhận thấy mismatch.

Không voice “có gì đó sai” mạnh.

## PHONE CONTENT

### Assignment, updated

**TL-2604-117**  
Trạng thái: Đã nhận hàng → Đang giao → Đã bàn giao

### Proof-of-handover

Nội dung Beat 6 là canonical.

### Payment status

**Đối soát: Đang xử lý**  
**Dự kiến: trong 24 giờ sau khi xác minh proof**

## INSPECTABLE OBJECTS

### O-S04-01 — Túi hồ sơ kín

- **Mô tả lần đầu:** Túi tài liệu A4 dày, niêm phong nguyên, không nhìn thấy nội dung.
- **Observation:** Bắc không được mở và không có lý do hợp pháp để mở.
- **Notebook:** Không.
- **Clue value:** Container của E22, không magic evidence.
- **Item location:** Bắc giữ từ 12:30 tới 13:52; sau đó thuộc điểm nhận.
- **Revisit:** Không thể inspect sau bàn giao.

### O-S04-02 — Routing label, C04

- **Mô tả lần đầu:** Nhãn “CTV / Giao trực tiếp — Ưu tiên” hơi mới hơn túi; mép dưới lộ một phần nhãn cũ “Nội bộ — Ưu tiên”.
- **Observation:** Có dấu đổi lớp routing ngoài.
- **Notebook nếu inspect:**  
  **Evidence — TL-2604-117 / Nhãn vận hành**  
  “Nhãn CTV được dán trên một nhãn cũ có chữ ‘Nội bộ — Ưu tiên’. Chưa rõ đổi khi nào hoặc vì sao.”  
  **Source:** Quan sát trực tiếp trước bàn giao.
- **Clue ID:** C04.
- **Clue value:** Delayed-value; chỉ có ý nghĩa mạnh sau C17.
- **Missable:** Có.
- **Mất trực tiếp lúc:** 13:52 khi pouch bàn giao; không inspect lại item trên tay.
- **Revisit:** Retained authored ảnh nhãn rõ có thể inspect muộn cho same fact; default seal-only photo không chứa nhãn và không recover C04.

### O-S04-03 — Proof-of-handover, C03

- **Mô tả lần đầu:** Receipt điện tử bình thường sau giao hàng.
- **Observation:** Client/account family đọc được là “Minh Trạch — Hành chính”; điểm nhận “Bàn giao nội bộ B”.
- **Notebook nếu inspect:**  
  **Evidence — TL-2604-117 / Biên nhận**  
  “Khách hàng: Minh Trạch — Hành chính. Điểm nhận: Bàn giao nội bộ B. Bàn giao lúc 13:52, niêm phong nguyên vẹn.”  
  **Source:** Tân Lộ Worker / proof-of-handover.
- **Clue ID:** C03.
- **Clue value:** Early bridge; không tự chứng minh wrongdoing.
- **Missable:** Có nếu player không mở chi tiết trước khi history UI về sau bị hạn chế; main route có alternate.
- **Mất lúc:** Bản vật lý không có; digital history tồn tại hiện tại. Context/access có thể giảm về sau.
- **Revisit S05/later:** Notebook giữ raw fields nếu đã inspect. Intentional mở live receipt history còn access cho same fields/time với observed_at mới nếu chưa inspect sớm; không auto-link.

### O-S04-04 — Bảng job bình thường, C06

- **Mô tả:** Nhiều đơn doanh nghiệp/y tế thông thường.
- **Observation:** Tân Lộ có business hợp pháp lớn hơn rất nhiều so với E22.
- **Notebook:** Không.
- **Clue ID:** C06.
- **Clue value:** Environmental noise / anti-overgeneralization.
- **Missable:** Có, không hậu quả.
- **Revisit:** Không đổi.

### O-S04-05 — Terminal tiếp nhận

- **Mô tả:** Màn hình chỉ hiện mã đơn, status và lỗi nhóm xử lý; không cho Bắc quyền truy cập hồ sơ nội bộ.
- **Observation:** Mismatch tồn tại ở classification, không phải content.
- **Notebook:** Không riêng; nếu player đã hỏi, Event note có thể thêm “điểm nhận thấy nhóm nội bộ cũ”.
- **Clue value:** Support C04/C02, không clue độc lập.
- **Revisit:** Không.

## PUZZLE

Không có puzzle.

Mismatched scan là authored event, không bắt player giải.

## CINEMATIC

### Arrival Tân Lộ

- **Trigger:** S03 exit.
- **Camera:** 1–2 giây authored look vào quầy điều phối, sau đó control.
- **Audio:** scanner, xe kéo, điện thoại.

### Travel tới Minh Trạch receiving point

- **Trigger:** pickup group charged once24m12:30→12:54; confirm travel card **12:54→13:24,30 phút**. Handover group28m→13:52, job-close18m→14:10; label/media reading0 and original handover time remains13:52.
- **Camera:** 8–12 giây first-person travel montage / transit shots.
- **Blocking:** Không NPC plot.
- **Audio:** traffic, app navigation chime nhẹ.
- **Transition:** Time card 13:24.

### Handover mismatch

Không cut control quá 5–6 giây. Player vẫn có thể nhìn quanh khi nhân viên gọi nội bộ.

## BRANCH VARIANTS

### BV-S04-A — C04 not seen

Receiving-point mismatch vẫn xảy ra. Player chỉ có C02 + lời “nhóm nội bộ cũ” nhưng không có physical observation.

### BV-S04-B — C03 not saved

Chưa có notebook entry khi chưa intentional inspect. Later mở Chi tiết của receipt còn live history nhận cùng C03 raw fields và đặt observed_at mới; không thụ động auto-award. Chỉ actual history-access restriction mới đóng quan sát nếu chưa có retained copy; handover không xóa receipt.

### BV-S04-C — Player nghi Tuấn sớm

Không set TUAN_FALSE_THEORY chỉ vì một câu hỏi. Scene chỉ ghi behavioral observation; false theory được hình thành sau audit/S06–S08 nếu player tiếp tục.

## CLUE HANDLING

### C02

- **Lúc nhận:** S03, reinforced S04.
- **Notebook:** Raw assignment.
- **Missable:** Không.
- **Mất lúc:** Không trước S08.
- **Giá trị:** Mandatory seed.

### C03

- **Lúc nhận:** Beat 6 hoặc intentional later live-history inspect còn access.
- **Notebook:** Same raw receipt/original time, observed_at mới nếu đọc muộn.
- **Missable:** Chỉ khi actual history access đóng trước observation/copy.
- **Mất lúc:** Handover không xóa digital receipt; restriction phải có actor/event.
- **Giá trị:** Transaction/group bridge lead, không tự X current risk authority.

### C04

- **Lúc nhận:** Beat 2 direct inspect hoặc later intentional inspect ảnh authored nhãn rõ.
- **Notebook:** Raw label fact/source; default seal-only photo không cho label.
- **Missable:** Nếu chưa quan sát và không có retained ảnh nhãn rõ.
- **Mất trực tiếp lúc:** 13:52 after handover; ảnh thật có content vẫn còn.
- **Giá trị:** Delayed reclassification seed.

### C06

- **Lúc nhận:** Optional environmental glance.
- **Notebook:** Không.
- **Missable:** Có.
- **Giá trị:** Prevent “all Tân Lộ medical work is crime” reasoning.

## SCENE EXIT

[PHONE — TÂN LỘ WORKER]

**14:01 — Ca TL-2604-117 đã hoàn tất.**  
Đối soát proof-of-handover: **Đang xử lý.**  
Thanh toán dự kiến trong 24 giờ.

Objective: **Rời điểm nhận.**

Bắc cất điện thoại.

Nếu player đã thấy mismatch, inner monologue normalization có thể phát như trên.

Transition tới khu ăn/ngõ trong S05; không suspense sting.

## CONTINUITY CHECK

- E22 hoàn tất đúng 13:52, trong window 12:30–14:10.
- Package đã rời tay Bắc; Bắc không mở và không có magic evidence.
- Tuấn chỉ biết lớp vận hành, không biết core crime/Nam.
- Nhân viên đầu nhận vô tội.
- C02 guaranteed; C03/C04 optional.
- Sau scene, E23 bắt đầu hậu trường nhưng player chưa biết.
- Nam vẫn chưa xuất hiện trong scene; tới E24 sau 16:00 mới biết worker là Bắc.
- Travel Tân Lộ → điểm nhận có đủ 25+ phút objective time.

---

# S05 — ĂN TỐI, ĐỢI TIỀN, VỀ TRỌ

## SCENE HEADER

- **Scene ID:** S05
- **Location:** quán bình dân gần tuyến Minh Trạch→trọ, rồi HUB B dãy trọ; không extra school trip
- **Time:** D0,14:30–18:07; nearby move10m+meal wait10m from14:10, ordinary afternoon group180m→17:30, return35m→18:05, room beat2m→18:07
- **Required state:** E22_COMPLETE = true; package no longer with Bắc; payment pending
- **Characters:** Bắc, Lan, Nam, Linh qua chat; NPC quán/hàng xóm
- **Backstage state by scene end:** E23 → E24 → E25; BARC organization knowledge N0 → N1

## OPENING STAGE DIRECTION

Scene cố tình giảm tension.

Bắc ngồi ở quán bình dân hoặc bàn ăn nhỏ gần tuyến về trọ. Trên bàn là món ăn đơn giản, chai nước, điện thoại úp cạnh tay. Không có ai theo dõi. Không có camera “một người lạ ở xa”.

Âm thanh: quạt treo tường, bát đũa, xe ngoài phố, TV phát chương trình đời thường không cần nội dung rõ.

Ánh sáng chiều. Khi về HUB B, hành lang quen hơn S01; vài đôi dép đã đổi vị trí, quần áo ngoài dây phơi khô hơn, tiếng người về phòng.

NPC state:

- Lan đang sắp đồ/nhắc người thuê chuyện hành lang.
- Nam đã nhận report hậu trường qua chain Khải nhưng chỉ biết Bắc là worker E22, N1. Ông không biết Bắc đã chú ý C03/C04 hay suy nghĩ gì.
- Nam vẫn làm việc đời thường, đã sửa xong ổ kéo của Bắc.
- Linh chỉ nghĩ Bắc đi làm thêm một ca.

## PLAYER FLOW

### Beat 1 — Bữa ăn và payment pending

[PHONE — TÂN LỘ WORKER]

**14:18 — TL-2604-117**  
Trạng thái ca: **Hoàn tất**  
Đối soát: **Đang xử lý**

Nếu player mở chi tiết:

**Proof đã nhận:** Có  
**Dự kiến thanh toán:** Trong 24 giờ

Không gọi đây là anomaly.

[INNER MONOLOGUE, chỉ nếu player kiểm tra payment hai lần]

**BẮC:**  
Hai trăm mấy cũng là tiền. Miễn đừng treo luôn là được.

### Beat 2 — Linh chat, đời thường

[PHONE — CHAT: Linh]

**15:07 — Linh:**  
Ông lấy file bài sáng chưa?

Player response:

[CHOICE A] “Chưa.”  
[CHOICE B] “Lấy rồi, cảm ơn.”

Nếu A:

**15:08 — Bắc:**  
Chưa.

**15:08 — Linh:**  
Tí tôi gửi. Đừng bảo mới ngày đầu đã bỏ học đi ship nhé.

**15:09 — Bắc:**  
Một cuốc thôi.

**15:09 — Linh:**  
Ai cũng có “một cuốc thôi” với “một tập nữa thôi”.

Nếu B:

**15:08 — Bắc:**  
Lấy rồi, cảm ơn.

**15:08 — Linh:**  
Tốt. Tối nhớ xem trang 6, ảnh của tôi méo nhưng chữ vẫn còn.

Không plot info.

### Beat 3 — Optional revisit C03/C04 notes

Player có thể mở notebook. Nếu C03/C04 đã lưu, chỉ hiển thị raw fact; không có “update clue” hoặc arrow.

Không inner monologue mới.

### Beat 4 — Về trọ

Khoảng 17:20–17:40 objective time. Bắc bước vào HUB B.

Lan thấy đôi giày/ba lô Bắc đặt hơi chắn lối khi cậu vào phòng.

**LAN:**  
Bắc, giày để sát vào tường hộ cô.

**BẮC:**  
Vâng. Có một đôi thôi mà cô.

**LAN:**  
Một đôi đặt ngang thì vẫn là một đôi rất có diện tích.

Bắc kéo vào.

Nam ngồi ở góc sửa đồ, ổ kéo của Bắc đặt cạnh cốc trà.

**NAM:**  
Bắc.

Nam nhấc ổ kéo.

**NAM:**  
Của cháu đây. Thay đầu cắm rồi. Dây còn dùng được.

Bắc nhận item.

**BẮC:**  
Bao nhiêu ạ?

**NAM:**  
Không đáng tiền. Lần sau đừng quấn băng dính rồi coi như đã sửa.

**BẮC:**  
Cháu quấn tạm thôi.

**NAM:**  
Ai cũng nói “tạm” cho tới lúc nó thành đồ dùng chính.

Nam nói với nụ cười nhẹ, rồi quay lại chiếc quạt đang sửa.

Không double meaning intentional.

### Beat 5 — Nếu Bắc chủ động nói về việc làm thêm

Đây là branch flavor, Nam không hỏi trước.

Nếu player chọn “Cháu vừa đi làm thêm một ca”:

**BẮC:**  
Cháu vừa chạy một ca làm thêm. Kiếm thêm chút.

**NAM:**  
Ngày đầu lên đã chạy việc rồi à?

**BẮC:**  
Ca ngắn thôi ạ.

**NAM:**  
Ừ. Làm thì làm, nhớ ăn trước. Trẻ mấy cũng không chạy bằng pin được.

Nam không hỏi công ty nào, đi đâu, giao gì.

Nếu player nói rõ “Tân Lộ” bằng một optional dialogue:

**BẮC:**  
Bên Tân Lộ ấy chú. Giao hồ sơ thôi.

Nam phải giữ phản ứng rất nhỏ và hợp biography.

**NAM:**  
Tân Lộ à. Chú biết tên từ hồi còn làm kho. Công ty làm logistics lâu rồi.

Dừng.

**NAM:**  
Ca đầu ổn không?

Nếu player trả lời “Ổn”:

**BẮC:**  
Cũng ổn ạ.

**NAM:**  
Thế được.

Nếu player trả lời “Hơi lằng nhằng”:

**BẮC:**  
Hơi lằng nhằng lúc bàn giao thôi.

**NAM:**  
Việc mới cái gì cũng lằng nhằng. Nếu họ cần đối soát thì cứ để họ đối soát.

Quan trọng: Nam không hỏi “nhãn gì”, “Minh Trạch à”, “mã 117 à”. Ông không được lộ knowledge vượt observable.

[DEV] Việc Bắc tự nói “Tân Lộ” ở N1 không tăng LEAK_PATH và không tạo Exposure. Nam đã biết Bắc là worker qua E24; dialogue chỉ thay flavor. Tuyệt đối không dùng line này như route lock.

### Beat 6 — C28 revisit optional

Nếu C28 đã seen và player giờ biết Tân Lộ, inspect cùng card:

[OBSERVATION TEXT]

“Cùng tên công ty mình vừa nhận ca. Card này trông cũ hơn nhiều.”

[NOTEBOOK] Không tạo clue mới. Có thể append đúng một dòng vào C28:

“Sau ca TL-2604-117, xác nhận đây là cùng tên Tân Lộ Logistics. Chưa rõ card liên quan trực tiếp tới chú Nam tới mức nào.”

Không tăng COMMAND.

Nếu C28 chưa seen, S05 vẫn không bắt camera vào nó. Player có thể inspect nếu tự đi tới bàn; vẫn là C28 từ S01, không phải “clue lớn mới S05”.

### Beat 7 — Bắc về phòng

[PLAYER] Cắm ổ kéo vừa sửa. Đèn sạc ổn định.

Một khoảnh khắc 5–10 giây chỉ có đời sống: mở laptop, đặt file bài học lên màn hình, quạt chạy.

Đây là emotional rest.

## DIALOGUE

### Lan hỏi đã ăn chưa

Nếu player về trọ trước khi ăn:

**LAN:**  
Ăn gì chưa?

**BẮC:**  
Chưa ạ.

**LAN:**  
Thế đi ăn đi rồi hãy cắm mặt vào máy. Cô không nấu hộ đâu.

Nếu đã ăn:

**BẮC:**  
Cháu ăn rồi ạ.

**LAN:**  
Tốt. Thế nhớ giày.

Lan nhất quán: quan tâm nhưng thực tế.

### Hàng xóm nền

**HÀNG XÓM:**  
Anh ơi, Wi‑Fi tầng này mật khẩu có đổi không?

**LAN, từ xa:**  
Không đổi! Sai thì nhìn lại chữ hoa!

Không plot.

### Nam nếu player cảm ơn lần nữa

**BẮC:**  
Cảm ơn chú nhé.

**NAM:**  
Ừ. Dùng được là được.

## INNER MONOLOGUE

Chỉ một line payment nếu player check lặp.

Không dùng inner monologue nghi Nam.

Khi cắm ổ kéo đã sửa, không cần narration.

## PHONE CONTENT

### Tân Lộ payment

**14:18 — TÂN LỘ WORKER**  
Ca TL-2604-117 — Hoàn tất  
Đối soát — Đang xử lý

### Linh chat

Nội dung Beat 2.

### Group class noise

**16:11 — Nhóm lớp:**  
Tài liệu tuần 1 đã tải lên.

**16:24 — Sinh viên nền:**  
Mai có cần mang giáo trình bản giấy không mọi người?

**16:27 — Linh:**  
Trong thông báo không ghi. Tôi đoán là không, nhưng đây là đoán nhé.

Câu cuối reinforce character habit “biết vs đoán” mà không exposition.

### Scene-exit audit notification

Chỉ xuất hiện cuối scene, sau khi player đã có tối thiểu một beat bình thường ở phòng.

**18:07 — TÂN LỘ WORKER**  
**Yêu cầu xác minh ca TL-2604-117**  
Bộ phận điều phối cần đối chiếu lại thông tin bàn giao.  
Trong thời gian đối soát, vui lòng **không tự liên hệ điểm nhận**.  
Bộ phận điều phối sẽ liên hệ qua ứng dụng.

Đây là trigger S06, không phải clue mới của S05.

## INSPECTABLE OBJECTS

### O-S05-01 — Ổ kéo đã sửa

- **Mô tả lần đầu:** Đầu cắm mới, gọn, phần băng dính cũ đã bỏ.
- **Observation:** Nam thực sự sửa đồ, không chỉ “diễn nghề”.
- **Notebook:** Không.
- **Clue value:** C29 characterization only.
- **Item location:** Trả về phòng Bắc từ Beat 4.
- **Revisit:** Dùng bình thường về sau.

### O-S05-02 — C28 card cũ

- **Mô tả:** Giữ đúng O-S01-04, vị trí không tự đổi.
- **Observation sau khi biết Tân Lộ:** cùng tên công ty.
- **Notebook:** Chỉ append raw observation nếu player tự inspect.
- **Clue ID:** C28 existing.
- **Clue value:** Không phải clue mới S05; không tăng proof.
- **Missable:** Có.
- **Revisit:** Như Beat 6.

### O-S05-03 — Laptop/bài học

- **Mô tả:** File bài buổi sáng, tab tìm việc còn mở nếu player chưa đóng.
- **Observation:** Đời sống sinh viên tiếp tục.
- **Notebook:** Không.
- **Clue value:** Noise / pacing.
- **Revisit:** S07 sẽ dùng cùng workstation.

### O-S05-04 — Payment status

- **Mô tả:** “Đang xử lý”.
- **Observation:** Chưa phải bất thường; trong chính listing đã nói thanh toán sau đối soát.
- **Notebook:** Không tạo clue.
- **Clue value:** Motive cho S06/S07, không evidence core.
- **Revisit:** Cuối scene chuyển sang “Yêu cầu xác minh”.

## PUZZLE

Không có puzzle.

Không được biến việc kiểm tra payment hoặc C28 thành required interaction.

## CINEMATIC

### Match cut về trọ

- **Trigger:** Player confirm kết thúc ordinary meal/study afternoon group once180m14:30→17:30, rồi visible travel **17:30→18:05,trọ35 phút**; montage không advance thêm phút từ wall-clock.
- **Camera:** Điện thoại hiển thị “Đang xử lý” → match cut sang cùng điện thoại đặt trên bàn phòng trọ.
- **Duration:** 3–5 giây.
- **Audio:** âm quán crossfade sang tiếng hành lang/quạt.
- **Purpose:** nhấn thời gian đi qua và kéo story về đời thường.
- **Không:** suspense sting.

## BRANCH VARIANTS

### BV-S05-A — Player nói Tân Lộ với Nam

Dialogue Beat 5. Không state danger.

[STATE] Nam already N1 via backstage E24; không tăng chỉ vì player nói tên employer.

### BV-S05-B — Player không nói gì về job

Nam chỉ trả ổ kéo. Đây là default recommended route.

### BV-S05-C — C28 seen before

Cho phép one-line reinspection, không popup “Clue Updated”.

### BV-S05-D — C28 not seen

Không hint. Card vẫn chỉ là prop.

### BV-S05-E — C03/C04 saved

Bắc có thể đọc notebook ở phòng; không có authored deduction. Nội dung chỉ raw facts.

## CLUE HANDLING

### C29

- **Lúc nhận:** Nam sửa/trả ổ kéo và cư xử bình thường.
- **Notebook:** Không.
- **Missable:** Character beat gần như guaranteed.
- **Mất lúc:** Không.
- **Giá trị:** Thematic delayed-value; về sau chứng minh kindness đời thường là thật.

### C28 existing

- **Lúc nhận:** chỉ nếu inspect; không mới nếu đã seen.
- **Notebook:** Raw relation seed only.
- **Missable:** Có.
- **Mất lúc:** Không trong S05.
- **Giá trị:** Relationship/history, không command.

### Không có major clue mới

[DEV] Đây là hard production constraint từ Stage 7. Audit notification cuối scene chỉ mở S06; không được giấu C17/C31/C32 hoặc bất kỳ proof mới nào trong S05.

## SCENE EXIT

Sau khi Bắc đã arrive18:05 và commit một ordinary room beat — mở laptop, cắm sạc, hoặc trả lời Linh — charge S05_ROOM once2m→18:07, display time card và queued audit notification. Reading/inspect trước/sau beat không advance clock, repeated beat/save-load không thêm cost.

[PHONE] Audit notification hiện như trên.

Bắc đọc.

Nếu player đã từng gặp mismatch ở S04:

[INNER MONOLOGUE]

**BẮC:**  
Lại ca đấy.

Nếu player không chú ý mismatch:

**BẮC:**  
Xác minh gì nữa nhỉ?

Không nói “có chuyện rồi”.

Objective đổi:

**Chờ bộ phận điều phối liên hệ.**

Màn hình không fade sang thriller. Player vẫn ở phòng. S06 bắt đầu từ chính trạng thái này ở lượt script kế tiếp.

## CONTINUITY CHECK

- Package vẫn ở điểm nhận; Bắc không thể inspect lại.
- C03 record vẫn trong history; intentional later inspect còn access cho same fields/time. C04 direct item access đã hết, retained label-visible photo/observation còn; default seal-only photo không recover nhãn. Existence, access, observation/copy riêng; replay cùng content cho cùng facts.
- Nam biết Bắc = worker E22 từ E24, nhưng chỉ ở N1.
- Nam không biết Bắc đã thấy nhãn/receipt cụ thể, không biết notebook.
- Lan/Linh không biết plot.
- Hùng đang bị Khải chất vấn ở hậu trường; Nam chọn observe ở E25.
- S05 không thêm major clue.
- Payment pending vẫn hợp listing ban đầu; audit notification là inciting beat của S06.
- HUB B geometry/props nối đúng S01: ổ kéo đã quay về phòng, card C28 không tự di chuyển.
- Objective time ends18:07 via authored room beat, đúng S06 entry; source inspect/UI dwell cannot fire the notification or consume a future window.

---

# STAGE 8 CONTINUATION ANCHOR

Phần hoàn chỉnh hiện tại kết thúc tại **S05**, đúng cuối ACT I.

Lượt Stage 8 kế tiếp phải bắt đầu tại **S06 — JOB BỊ AUDIT**, giữ nguyên schema và không viết lại S01–S05 trừ khi continuity audit ở phần sau buộc phải sửa một fact cụ thể.
