# ENDING LOGIC

> **Status:** STORY DESIGN — STAGE 6 / DESIGN LOCK CANDIDATE  
> **Parent canon:** MASTER_GAME_BIBLE.md  
> **Inputs read:** BACKSTAGE_CRIME_TRUTH.md, CHARACTER_WEB.md, OBJECTIVE_TIMELINE.md, CLUE_GRAPH.md, PLAYER_STORY.md  
> **Repository:** phambac2k701-blip/cot_truyen  
> **Created:** 2026-10-04  
> **Scope:** hidden branching state, route-lock rules, ending conditions, true-ending proof chain, branch map, softlock audit  
> **Không bao gồm:** dialogue line-by-line, cinematic shot list, level scripting chi tiết

---

# 0. DESIGN CONTRACT

Ending của game không phải phần thưởng cho việc chọn một nút “đúng”.

Ending phải là hậu quả của bốn thứ:

1. player thực sự đã nối được bao nhiêu phần của mystery;
2. source nào còn tồn tại và đã được bảo toàn;
3. player đã để ai biết mình đang làm gì;
4. player hành động trước hay sau khi cleanup khóa các cửa.

Không có ending nào chỉ tồn tại để tăng số lượng.

Các ending phải khác nhau về **causal failure**, không chỉ khác cutscene.

Một lựa chọn sai không tự động bật Bad Ending. Hậu quả phải có thời gian nở ra.

Nếu player miss một clue nhưng vẫn còn một source hợp lý khác chứng minh cùng fact, route chưa bị khóa.

Nếu player đã đưa evidence hợp lệ cho Vũ, tổ chức không được phép “xóa ngược” evidence đó chỉ để ép bad ending.

---

# 1. HIDDEN STATE TỐI GIẢN

Không hiển thị meter cho player.

Stage 5 liệt kê nhiều biến scripting. Stage 6 gom chúng thành sáu nhóm state thực sự cần cho ending resolver.

## 1.1. BARC — organization awareness về Bắc

Giữ nguyên logic objective truth:

- **N0 — NORMAL:** Bắc chỉ là sinh viên mới.
- **N1 — ACCIDENTAL EXPOSURE:** Bắc vô tình chạm E22.
- **N2 — PROBING:** Bắc chủ động hỏi vượt phạm vi job.
- **N3 — CROSS-CELL THREAT:** hành vi observable cho thấy Bắc đang nối nhiều cell.
- **N4 — CASE THREAT:** organization có cơ sở tin Bắc có thể đưa chuỗi evidence dùng được cho cảnh sát.

BARC đo **organization biết gì về Bắc**, không đo player biết gì.

Không tăng BARC chỉ vì player suy luận trong đầu.

---

## 1.2. CASE — trạng thái evidence theo proposition

Không cần giữ hàng chục boolean clue ở ending layer.

Mỗi slot A, B, C có ba trạng thái:

- **0 — MISSING:** chưa có source đủ.
- **1 — ASSEMBLED:** player có đủ source để proposition có cơ sở, nhưng chưa được Vũ bảo toàn đầy đủ.
- **2 — PRESERVED:** source cốt lõi đã được Vũ/police tiếp nhận hoặc được giữ trong một chain hợp lý ngoài quyền xóa của network.

Các slot:

- **A:** Phúc rút trước rồi mới bị gây sức ép.
- **B:** Minh Trạch có pattern và có internal knowledge/intervention.
- **C:** Tân Lộ leadership chủ ý tham gia, không phải lỗi worker/dispatch.

Không tạo score 0–100.

---

## 1.3. X_VERIFIED — bridge giữa các cell

Boolean:

- FALSE: A/B/C vẫn có thể bị đọc như các scandal riêng.
- TRUE: player đã đưa được bridge hợp lệ để Vũ xác minh rằng các box không độc lập.

X không tự bật chỉ vì player sở hữu nhiều clue.

Nó bật khi relation được **đưa vào một hành động điều tra có thể kiểm chứng**: ví dụ C24+C25/C26, hoặc bridge tương đương được Vũ xác minh.

---

## 1.4. COMMAND — mức chứng minh Nam

Một enum duy nhất thay cho nhiều cờ nhỏ:

- **C0 — NONE:** Nam chỉ là hàng xóm.
- **C1 — HYPOTHESIS:** C27/C28/C30 khiến Nam đáng nghi nhưng chỉ chứng minh background/relationship.
- **C2 — CURRENT LINK:** có current-crisis relation tới Nam, nhưng chưa đủ command.
- **C3 — CORROBORATED COMMAND:** D1+D2 đủ từ các nguồn độc lập.
- **C4 — PRESERVED COMMAND:** D1+D2 đã được Vũ/police bảo toàn trước cleanup lock.

True ending yêu cầu C4.

C27, C28, C30 không bao giờ tự nâng COMMAND quá C1.

---

## 1.5. LEAK_PATH — Bắc làm lộ route bằng cách nào

Một enum:

- **NONE**
- **MINH:** leak đi qua Minh vì Bắc chia quá nhiều trước preservation.
- **DIRECT:** Bắc tự confront Nam/Khải, đi cuộc hẹn không an toàn, hoặc để organization biết chính xác evidence đang nằm ở đâu.

Nếu cả hai xảy ra, DIRECT có ưu tiên khi xác định nguyên nhân thất bại.

LEAK_PATH không tự động quyết định ending. Nó chỉ có ý nghĩa nếu leak **thực sự làm source đóng hoặc làm chain evidence gãy**.

---

## 1.6. CLEANUP — trạng thái race

Một enum:

- **BASELINE:** cleanup objective vẫn diễn ra theo Stage 3.
- **ACCELERATED:** organization đã có thêm lý do đẩy nhanh source isolation.
- **LOCKED:** các cửa command/source quan trọng của run hiện tại đã đóng; police vẫn có thể điều tra lâu dài, nhưng game window không còn đủ để xây phần còn thiếu.

CLEANUP_ACCELERATED có thể đến từ:

- Minh leak;
- direct exposure;
- BARC N3/N4;
- hoặc objective cleanup vốn đã tăng theo timeline.

Không có visible countdown.

---

## 1.7. ABANDON_AFTER_N3

Boolean duy nhất cho Avoidance route.

Chỉ có giá trị nếu:

- Bắc đã tới N3;
- CASE chưa được bảo toàn đủ;
- player chủ động cắt liên lạc và cố quay lại đời thường.

Bỏ cuộc ở N1 không dùng state này; đó là Neutral Ending hợp logic.

---

# 2. STATE KHÔNG CẦN Ở ENDING LAYER

Các biến sau vẫn có thể tồn tại ở scene scripting, nhưng không phải root state của ending:

- JOB_E22_SEEN;
- C03_SAVED;
- C04_SEEN;
- TUAN_FALSE_THEORY;
- TUAN_CORE_EXONERATED;
- từng interaction nhỏ;
- từng optional lore clue;
- từng lần Bắc nói dối phòng vệ.

Chúng chỉ thay đổi cách player đi tới CASE/X/COMMAND/LEAK/CLEANUP.

Không tạo một state chỉ vì một scene cần nhớ rằng player đã bấm một câu thoại.

---

# 3. TRANSITION RULES CỐT LÕI

## 3.1. Early game

E22 hoàn tất:

- BARC: N0 → N1.
- CASE chưa tự tăng.

Player hoàn toàn có thể dừng ở đây.

Nếu Bắc không đào sâu, không leak, không chạm cell thứ hai:

- organization kiểm tra;
- thấy exposure thấp;
- route G0 có thể kết thúc.

---

## 3.2. Curiosity

Khi Bắc chủ động hỏi, giữ source hoặc xuất hiện quanh một nhánh thứ hai:

- BARC có thể N1 → N2.

Không được nhảy thẳng N3 chỉ vì player tìm được một clue.

N3 chỉ xảy ra khi:

- player thực sự có cross-cell understanding;
- và hành vi đó để lại consequence observable ở nhiều nhánh.

---

## 3.3. Preservation

C42 không phải “một clue thần kỳ”.

C42 là consequence của việc player đưa source đúng cho Vũ.

Khi Vũ tiếp nhận đủ source:

- A/B/C tương ứng chuyển từ ASSEMBLED → PRESERVED.
- organization không thể đơn giản thu hồi phần đã sang hồ sơ điều tra.
- mất access về sau vẫn có thể ảnh hưởng COMMAND, nhưng không xóa ngược A/B/C.

---

## 3.4. Leak

MINH leak:

- không game-over;
- có thể tăng BARC;
- có thể đưa CLEANUP → ACCELERATED;
- chỉ mở Wrong Trust ending nếu chính leak đó đóng đường evidence cần thiết trước preservation.

DIRECT exposure:

- có thể tăng BARC nhanh hơn;
- thường đưa CLEANUP → ACCELERATED;
- chỉ mở Exposure ending nếu Bắc còn giữ source quan trọng chủ yếu một mình và hậu quả làm chain gãy.

---

## 3.5. Cleanup lock

CLEANUP chuyển LOCKED khi:

- các cửa command/source quan trọng của run hiện tại đã đóng;
- hoặc objective timeline đã đi qua mốc mà D không còn có thể được corroborate/preserve trong run.

Lock không có nghĩa “mọi database bị xóa”.

Nó nghĩa:

- access bị thu hồi;
- context bị mất;
- source rút lại;
- contact chain bị cắt;
- hoặc police không còn đủ thời gian để biến dấu vết còn lại thành proof trong game window.

---

# 4. ENDING RESOLVER — THỨ TỰ ƯU TIÊN

Ending resolver dùng causal state, không dùng một số điểm.

## 4.1. Early resolver

Nếu player chủ động kết thúc curiosity ở S07 khi:

- BARC ≤ N1;
- chưa chạm N2;
- không leak;
- chưa mang anomaly sang cell thứ hai;

→ **G0 — MỘT CA LÀM THÊM.**

Đây là short neutral ending.

---

## 4.2. Late resolver

Sau N2/N3, resolver theo thứ tự:

1. Nếu A/B/C đều PRESERVED + X_VERIFIED + COMMAND C4 trước CLEANUP LOCKED  
   → **G6 TRUE — NHỮNG MẢNH KHỚP LẠI.**

2. Nếu ABANDON_AFTER_N3 = TRUE và police chưa đủ preservation để tự giữ case  
   → **G3 AVOIDANCE — QUAY LƯNG QUÁ MUỘN.**

3. Nếu LEAK_PATH = DIRECT và direct exposure là nguyên nhân làm source/chain gãy trước preservation  
   → **G5 EXPOSURE — BỊ NHÌN THẤY.**

4. Nếu LEAK_PATH = MINH và leak qua Minh là nguyên nhân làm một slot cần thiết mất route cuối trước preservation  
   → **G2 WRONG TRUST — SAI NGƯỜI.**

5. Nếu A/B/C đều PRESERVED + X_VERIFIED nhưng COMMAND chưa đạt C4 khi CLEANUP = LOCKED  
   → **G4 CLEANUP — DỌN SẠCH.**

6. Nếu một hoặc nhiều A/B/C không thể đạt PRESERVED vì cửa source cuối cùng đã đóng, và thất bại không chủ yếu do Wrong Trust/Exposure  
   → **G1 DELAY — QUÁ MUỘN.**

Điểm quan trọng:

- Một Minh leak sau khi A/B/C đã được preserve không tự ép G2.
- Một confrontation sau khi toàn bộ A/B/C+D đã được preserve không xóa True Ending.
- Một player biết Nam là boss nhưng không chứng minh command vẫn không đạt True.
- Một player không biết Nam từ đầu vẫn có thể đạt True nếu late evidence được nối đúng.

---

# 5. G0 — NEUTRAL ENDING: MỘT CA LÀM THÊM

## Premise

Bắc gặp một việc hơi lạ, nhưng quyết định nó không đủ để biến thành vấn đề của mình.

Đây là ending chứng minh game tôn trọng objective truth: chỉ chạm E22 không khiến Bắc tự động thành mục tiêu.

## Điều kiện cần

- BARC ở N1.
- Không bước sang N2.
- Không tạo Minh leak.
- Không cross-check sang cell thứ hai.
- Không giữ một source mà organization có lý do xem là threat.

## Lựa chọn/clue dẫn tới

- C02/C03/C04 có thể đã thấy.
- Player không follow-up sau audit.
- Không hỏi Minh sâu về company.
- Không truy hospital/Phúc/Tân Lộ beyond job resolution.

## Điểm thực sự khóa route

Cuối S07, khi player chấp nhận đóng vấn đề như một ca làm thêm và time progression đi qua cửa điều tra đầu tiên.

Không khóa ngay ở lần đầu player nói “kệ”.

## Cảnh báo mềm

Không có cảnh báo “bạn sắp bỏ mystery”.

Chỉ có:

- một vài chi tiết chưa giải thích;
- audit vẫn còn;
- cảm giác Bắc có thể hỏi tiếp nếu muốn.

Neutral phải là lựa chọn hợp lý, không phải punishment trap.

## Tình trạng Bắc

- An toàn.
- Tiếp tục đời sống sinh viên.
- Có thể vẫn thấy job đó hơi khó hiểu nhưng không còn bị cuốn vào.

## Tình trạng Nam

- Nhận report về accidental worker rồi hạ mức quan tâm.
- Không có lý do làm gì Bắc.

## Tình trạng tổ chức

- Co nhỏ qua crisis hiện tại.
- Mất một vài mắt xích/chi phí.
- Có khả năng sống sót và hoạt động lại thận trọng hơn.

## Tình trạng cảnh sát

- Vũ tiếp tục vụ Phúc.
- Có thể xử lý nhánh thấp nhưng chưa có bridge ba box.

## NPC quan trọng

- Minh vẫn là bạn học bình thường.
- Tuấn tiếp tục công việc.
- Huyền vẫn giữ nghi ngờ compliance.
- Đức/Yến tự xử lý nỗi sợ theo baseline objective timeline.

## Sự thật player hiểu

- Job E22 có vài thứ lệch.

## Sự thật player chưa hiểu

- A/B/C/D gần như toàn bộ.
- Không biết Nam là command core.

## Cảm xúc kết thúc

Bình thường, hơi ngứa ngáy.

Không bi kịch.

## Ending screen

Một buổi học/đường về trọ bình thường. Điện thoại hiện thông báo công việc đã đóng hoặc tiền đã về. Một notification cũ liên quan audit trôi xuống dưới các tin sinh viên khác.

**MỘT CA LÀM THÊM**  
“Có những chuyện chỉ trở thành câu chuyện của mình nếu mình quyết định nhìn lại.”

---

# 6. G1 — DELAY / MISSED EVIDENCE BAD ENDING: QUÁ MUỘN

## Premise

Bắc hiểu rằng có chuyện nghiêm trọng, nhưng hiểu đến đó sau khi cửa source cần thiết đã đóng.

Đây là failure của **timing + evidence**, không phải police incompetence.

## Điều kiện cần

Ít nhất một trong A/B/C không thể đạt PRESERVED vì:

- player miss source chính;
- route thay thế cuối cùng cũng đóng;
- player tới sau access window;
- hoặc đã dành quá nhiều thời gian cho false theory khiến source không còn usable trong run.

Không cần leak.

## Lựa chọn/clue dẫn tới

Ví dụ:

- miss C11 và cả C12/C15 route hospital;
- miss C17/equivalent reconstruction và không còn Đức/Yến + C22 đủ để dựng lại C;
- đến Đức sau E32 window;
- giữ false theory Tuấn quá lâu và bỏ qua authority chain C20/C22;
- có C08 nhưng không đưa chronology sang Vũ kịp để A được preserve.

## Điểm thực sự khóa route

Không khóa ở **clue đầu tiên bị miss**.

Chỉ khóa khi **đường thay thế cuối cùng cho một required fact cũng đóng**.

Đây là rule bắt buộc để tránh softlock vô hình.

## Cảnh báo mềm

- C43: access bắt đầu đổi.
- Người từng trả lời nay cần quyền khác.
- Đức nói rõ mình sắp bị khóa.
- Huyền báo scope review bị thu hẹp.
- Vũ nhấn mạnh rằng source có giá trị hơn theory.

Không có timer UI.

## Tình trạng Bắc

- Sống.
- Có thể hiểu một phần lớn mystery.
- Không đủ chain để biến hiểu biết thành outcome trong game window.

## Tình trạng Nam

- Không cần đối đầu Bắc trực tiếp.
- Tiếp tục chiến lược co nhỏ và chờ.

## Tình trạng tổ chức

- Có thể mất nhánh môi giới hoặc một scandal hẹp.
- Phần lõi sống sót.

## Tình trạng cảnh sát

- Vũ có A, A+B hoặc một case hẹp khác.
- Điều tra vẫn có thể tiếp tục sau ending, nhưng không có breakthrough miễn phí.

## NPC quan trọng

- Phúc có thể được tin ở phần cốt lõi.
- Huyền/Đức/Yến có thể vẫn tồn tại như source tương lai nhưng cửa của run đã qua.
- Tuấn không nhất thiết được giải oan hoàn toàn nếu player dừng sai theory.

## Sự thật player hiểu

Tùy route:

- có coercion;
- hoặc hospital pattern;
- hoặc logistics leadership issue.

## Sự thật player chưa hiểu

- cấu trúc đủ rộng;
- hoặc command Nam;
- hoặc cách ba box xác nhận lẫn nhau.

## Cảm xúc kết thúc

Tiếc vì player nhìn đúng nhưng chậm một nhịp.

## Ending screen

Một record trong notebook vẫn còn đúng, nhưng bên cạnh source liên quan chỉ còn trạng thái “không còn truy cập / không thể xác minh lúc này”. Vũ không phủ nhận Bắc; anh chỉ nói phần còn lại chưa đủ để hành động trong cửa hiện tại.

**QUÁ MUỘN**  
“Biết một điều từng tồn tại không giống với việc còn có thể chứng minh nó.”

---

# 7. G2 — WRONG TRUST / BETRAYAL BAD ENDING: SAI NGƯỜI

## Premise

Bắc chia đúng mối lo cho sai kênh.

Minh không phải member. Chính vì Minh là người bình thường, hành động “báo cho người phụ trách để dập rắc rối” mới nguy hiểm.

## Điều kiện cần

- LEAK_PATH = MINH.
- Leak xảy ra trước preservation đủ.
- Leak chứa đủ chi tiết để Tân Lộ/risk layer biết Bắc đang chạm nhánh nào.
- Sau leak, ít nhất một required source route đóng sớm.
- Việc source đóng phải có quan hệ timing rõ với leak.
- Không có alternate source đủ để phục hồi trước cleanup lock.

Nếu Minh leak nhưng route vẫn được preserve, ending này không được ép xảy ra.

## Lựa chọn/clue dẫn tới

- Bắc kể cho Minh mình đang nghi ai.
- Gửi ảnh/log cụ thể để “hỏi hộ”.
- Nói rõ sẽ gặp Đức/Huyền hoặc đã có record nào.
- Tin Minh như secure channel vì cậu từng giúp kiếm việc.
- C35/C36/C37 dần cho thấy leak path.

## Điểm thực sự khóa route

Không phải lúc Bắc nhắn Minh.

Route chỉ khóa khi:

1. Minh chuyển thông tin;
2. source bị siết vì thông tin đó;
3. route thay thế cuối cùng biến mất trước C42.

## Cảnh báo mềm

- Minh có pattern né xung đột và ưu tiên người có quyền.
- C36: lời Minh về “tao chỉ hỏi thôi” không khớp mức công ty biết.
- Access closure xảy ra sát sau tin nhắn.
- Vũ từng khuyên không chia theory/source cho người không cần biết.

## Tình trạng Bắc

- Sống.
- Mất quyền chủ động.
- Hiểu rằng betrayal không nhất thiết đến từ ác ý.

## Tình trạng Nam

- Không cần biết mọi clue.
- Chỉ nhận đủ report để đánh giá risk tăng và cho cleanup đi trước.

## Tình trạng tổ chức

- Co lại nhanh hơn baseline.
- Một số source bị cô lập.
- Lõi còn khả năng sống sót.

## Tình trạng cảnh sát

- Có một phần case.
- Không đủ source đúng lúc để mở phần lõi.

## NPC quan trọng

- Minh nhận ra hậu quả muộn.
- Minh không được reveal là plant.
- Tuấn có thể là người Minh liên hệ đầu tiên nhưng không phải mastermind.
- Đức/Huyền có thể bị mất access mà không “biến mất bí ẩn”.

## Sự thật player hiểu

- Minh đã làm lộ mình.
- Organization không cần có spy ở khắp nơi; chỉ cần người bình thường chuyền thông tin theo incentive bình thường.

## Sự thật player chưa hiểu

Có thể vẫn thiếu:

- command Nam;
- hoặc một proposition bị leak làm mất route.

## Cảm xúc kết thúc

Đau vì sai trust, không phải vì bị “twist phản bạn” rẻ tiền.

## Ending screen

Một đoạn chat cũ với Minh còn mở. Tin “tao chỉ hỏi bên đó xem sao thôi” có timestamp ngay trước chuỗi access closure. Không có nhạc phản bội lớn.

**SAI NGƯỜI**  
“Thông tin không cần đến tay kẻ xấu nếu nó chỉ cần đi qua đúng một người đang sợ.”

---

# 8. G3 — AVOIDANCE BAD ENDING: QUAY LƯNG QUÁ MUỘN

## Premise

Bỏ qua từ N1 có thể an toàn.

Bỏ sau N3 là một việc hoàn toàn khác.

Player đã tạo dấu ở nhiều cell rồi mới cố giả vờ mọi thứ chưa từng xảy ra.

## Điều kiện cần

- BARC đã đạt N3.
- ABANDON_AFTER_N3 = TRUE.
- A/B/C chưa được preserve đủ để police tự tiếp tục route an toàn.
- Bắc vẫn là unresolved risk trong mắt organization.
- Player cắt liên lạc với Vũ/source thay vì chuyển evidence ra khỏi tay mình.

Nếu A/B/C+D đã được bảo toàn đủ, player rút lui cá nhân không tạo bad ending này.

## Lựa chọn/clue dẫn tới

- Sau S15, chọn quay lại lịch học và không trả lời Vũ.
- Không giao source đang giữ.
- Không follow-up source đã hẹn dù biết cửa đang đóng.
- Cố “xóa mình khỏi chuyện” sau khi đã để nhiều nhánh nhận ra mình.

## Điểm thực sự khóa route

Khi player xác nhận bỏ toàn bộ contact và time progression làm các source window cuối đóng trong khi police chưa đạt threshold.

Không khóa ngay khi player nói “tôi muốn dừng”.

## Cảnh báo mềm

- Vũ nói rõ evidence đang nằm ở đâu quan trọng hơn việc Bắc có tiếp tục tự điều tra hay không.
- Access closures cho thấy organization đã nhận ra pattern.
- Bắc đã thấy cùng tên mình xuất hiện trong hậu quả nhiều nhánh.

## Tình trạng Bắc

- Sống.
- Trở lại đời thường về bề mặt.
- Nhưng mất quyền tự quyết trong câu chuyện: contact biến mất, access bị khóa, Nam/Khải đã đưa cậu vào risk model.
- Bắc phải sống với việc mình biết có chuyện nhưng đã bỏ cửa để chứng minh nó.

## Tình trạng Nam

- Coi Bắc là unresolved risk nhưng ưu tiên containment hơn bạo lực.
- Có thể rời một số điểm tiếp xúc, giảm branch và chờ.

## Tình trạng tổ chức

- Sống sót sau crisis.
- Co nhỏ đáng kể.
- Học được từ failure lần này.

## Tình trạng cảnh sát

- Vũ tiếp tục phần case đã có.
- Không nhận được bridge đúng lúc từ Bắc.

## NPC quan trọng

- Phúc vẫn có vụ của mình.
- Huyền vẫn có review history.
- Minh/Linh/Lan không được kéo vào biết toàn sự thật.
- Đức/Thảo/Yến tự chịu hậu quả riêng của việc im lặng/hợp tác.

## Sự thật player hiểu

- Có network nhiều cell.
- Organization đã nhận ra Bắc đang nhìn vào nó.

## Sự thật player chưa hiểu

Có thể:

- chưa chứng minh Nam;
- chưa biết nhánh nào còn sống;
- không biết phần nào của case Vũ có thể tiếp tục về sau.

## Cảm xúc kết thúc

Không phải “hèn nên bị phạt”.

Là cảm giác bất an vì đã đi đủ sâu để không thể thật sự quay về trạng thái trước đó.

## Ending screen

Bắc ngồi lại trong lớp. Một thông báo lịch học hiện lên bình thường. Sau đó một contact từng trả lời nhanh nay chỉ còn trạng thái không khả dụng. Không có jumpscare.

**QUAY LƯNG QUÁ MUỘN**  
“Có lúc rời khỏi một câu chuyện không làm câu chuyện rời khỏi mình.”

---

# 9. G4 — CLEANUP BAD/PARTIAL ENDING: DỌN SẠCH

## Premise

Player giải đúng phần lớn mystery.

Cảnh sát cũng tin và hành động.

Nhưng command proof đến chậm một bước.

Đây là ending quan trọng nhất để chứng minh “hiểu đúng” không bằng “chứng minh đúng lúc”.

## Điều kiện cần

- A = PRESERVED.
- B = PRESERVED.
- C = PRESERVED.
- X_VERIFIED = TRUE.
- Vũ đã đạt E38.
- COMMAND chưa đạt C4 khi CLEANUP chuyển LOCKED.

Có thể COMMAND đang ở C1, C2 hoặc C3 nhưng chưa được preserve đủ.

## Lựa chọn/clue dẫn tới

- Dừng ở Hùng như apex.
- Dừng ở Khải như apex.
- Coi C27/C30 là đủ để accuse Nam.
- Lấy được C31 nhưng không có corroboration độc lập.
- Có C32 nhưng không kịp bảo toàn source thứ hai.
- Investigate Nam trực tiếp quá lâu thay vì chuyển D sang Vũ.

## Điểm thực sự khóa route

Khi command-source window đóng và CLEANUP = LOCKED trong khi A+B+C đã nằm an toàn với Vũ nhưng COMMAND chưa đạt C4.

## Cảnh báo mềm

- Nhiều branch đồng thời đổi trạng thái.
- Vũ chuyển từ hỏi “có chuyện gì” sang hỏi “ai có quyền ra quyết định”.
- C27/C30 được framing rõ là history/relationship, không phải command proof.
- C31/C32/C33/C34 xuất hiện dưới áp lực thời gian tự nhiên.

## Tình trạng Bắc

- Sống.
- Hiểu gần như toàn bộ picture.
- Có cảm giác cay nhất vì biết ai đứng sau nhưng không đủ chain để khóa command trong game window.

## Tình trạng Nam

- Không được “minh oan”.
- Vẫn là người chịu trách nhiệm khách quan.
- Có cơ hội tách khỏi phần đã lộ về mặt proof hiện tại.

## Tình trạng tổ chức

- Operation hiện tại bị thiệt hại nặng.
- Một số cell bị phá.
- Khả năng hoạt động như cũ giảm mạnh.
- Phần command còn cơ hội tái cấu trúc/co lại nếu điều tra sau ending không đi xa hơn.

## Tình trạng cảnh sát

- Đây không phải thất bại hoàn toàn.
- Vũ đã chứng minh network nhiều cell.
- Hùng/Khoa/Hạnh hoặc các mắt xích tương ứng có thể bị xử lý theo evidence.
- Thiếu D khiến việc nối toàn bộ architecture tới Nam/Khải chưa đủ mạnh trong game window.

## NPC quan trọng

- Phúc: lời khai có giá trị.
- Huyền: review trở thành phần của case.
- Tuấn: nếu C20/C22 đã có, được loại khỏi core-network hypothesis.
- Minh: hậu quả tùy player có leak hay không nhưng không quyết định ending.
- Thảo/Đức/Yến: có thể trở thành source trong case mà không ai thành exposition machine.

## Sự thật player hiểu

- A+B+C.
- Khải là cross-cell risk layer.
- Nam rất có thể là command core.

## Sự thật player chưa chứng minh

- D ở chuẩn đủ để phần lõi không thể hy sinh manager rồi tách ra.

## Cảm xúc kết thúc

Thắng một trận, thua đúng tầng quan trọng nhất.

## Ending screen

Một loạt trạng thái institutional đã đổi: nhánh bị đóng, hồ sơ được giữ, người liên quan bị tách khỏi vị trí. Sau đó camera/scene trở về khu trọ — chỗ Nam từng ngồi đã trống, không có lời nhắn giải thích.

**DỌN SẠCH**  
“Phá được hệ thống không có nghĩa đã giữ được người đã thiết kế nó.”

---

# 10. G5 — EXPOSURE BAD ENDING: BỊ NHÌN THẤY

## Premise

Không phải organization “đoán được” Bắc biết gì.

Bắc tự làm cho họ biết.

Đây là failure của operational judgment sau N3/N4.

## Điều kiện cần

- LEAK_PATH = DIRECT.
- Bắc đã ở N3 hoặc gần N4.
- Player confront Nam/Khải hoặc đi một interaction không an toàn trước khi source độc nhất được preserve.
- Direct exposure cho organization biết đủ cụ thể về source/evidence.
- Hậu quả làm chain gãy hoặc cô lập Bắc khỏi source.
- Police chưa có đủ preservation để route tự sống tiếp.

Nếu source đã an toàn với Vũ, direct exposure chỉ tăng risk/cleanup; nó không magically xóa case và không bắt buộc ending này.

## Lựa chọn/clue dẫn tới

- Confront Nam chỉ bằng C27/C30 hoặc C31 chưa corroborate.
- Nói với Nam mình biết C32/source manager.
- Tự đi gặp một đầu mối risky thay vì gửi source cho Vũ.
- Giữ evidence duy nhất trên điện thoại/notebook rồi để đối phương biết điều đó.
- Cố ép confession.

## Điểm thực sự khóa route

Khi direct exposure tạo một observable response khiến source cuối hoặc chain-of-custody cuối bị mất trước C42.

Không khóa ở câu thoại đối đầu đầu tiên nếu player vẫn còn route recovery hợp lý.

## Cảnh báo mềm

- Vũ đã nhấn mạnh source cần rời khỏi tay Bắc.
- Stage 5 cho thấy organization thích source isolation.
- Nam không phản ứng kiểu villain; chính sự bình thường của scene là warning rằng player đang nói quá nhiều trong một không gian không an toàn.
- C43 cho thấy các cửa đang đóng.

## Tình trạng Bắc

- Sống, nhưng bị loại khỏi khả năng tiếp tục điều tra hiệu quả.
- Có thể được Vũ yêu cầu rời khỏi tuyến tiếp xúc vì đã trở thành known risk.
- Không dùng cảnh bạo lực phô trương làm payoff mặc định.

## Tình trạng Nam

- Biết đủ về threat để chuyển ưu tiên sang protect core.
- Không cần confession.
- Không cần “bắt Bắc” nếu evidence chưa ra ngoài; chỉ cần làm các source không còn accessible.

## Tình trạng tổ chức

- Cleanup đi trước.
- Một phần có thể mất, lõi có cơ hội sống.

## Tình trạng cảnh sát

- Có thể biết Bắc nói thật.
- Nhưng phần chứng cứ có giá trị đã bị mất context/access trước khi tiếp nhận.

## NPC quan trọng

- Source manager có thể rút.
- Đức/Yến/Huyền có thể bị khóa access.
- Minh không cần liên quan.
- Tuấn không bị biến thành enforcer.

## Sự thật player hiểu

Có thể rất nhiều, kể cả Nam là hypothesis đúng.

## Sự thật player chưa chuyển thành proof

- chain command đủ chuẩn;
- hoặc một slot A/B/C còn nằm chủ yếu trong tay Bắc.

## Cảm xúc kết thúc

Cảm giác player đã tự biến knowledge thành signal cho đối phương.

## Ending screen

Bắc mở một source từng có thể dùng. Nội dung không nhất thiết bị “xóa sạch”; thay vào đó quyền truy cập/context không còn, và Vũ chỉ có bản kể lại không đủ thay thế source gốc.

**BỊ NHÌN THẤY**  
“Điều nguy hiểm không phải là biết. Là để người khác biết chính xác mình đang biết bằng cách nào.”

---

# 11. G6 — TRUE ENDING: NHỮNG MẢNH KHỚP LẠI

## Premise

Player không cần tìm hết game.

Player cần:

- hiểu đúng cấu trúc;
- phân biệt fact với interpretation;
- tin đúng người ở đúng phạm vi;
- giữ source;
- và đưa proof ra khỏi tay Bắc trước khi cleanup thắng race.

True Ending khó nhưng hoàn toàn đạt được ở run đầu.

---

## 11.1. Evidence requirement chính thức

### SLOT A — withdrawal before pressure

Canonical route:

- **C08** — record Phúc yêu cầu rút;
- **C10** — police chronology độc lập.

Equivalent chỉ hợp lệ nếu vẫn có:

- một source trực tiếp từ phía Phúc;
- một source độc lập đã được ghi nhận/xác minh ngoài Phúc.

C09 tăng fairness nhưng không bắt buộc.

---

### SLOT B — hospital pattern

Bắt buộc:

- **C11** — Huyền review pattern;
- cộng **C12 hoặc C15**.

C12 = institutional history.  
C15 = insider acknowledgment.

Player không cần cả hai.

---

### SLOT C — intentional logistics leadership involvement

Canonical route:

- **C17** — reclassification fact;
- cộng **C18 hoặc C19** hay source tương đương đã được Vũ verify;
- **C22** — leadership override đặt quyết định ở Hùng-level, không ở Tuấn/worker.

Nếu C17 trực tiếp bị miss, một police reconstruction chỉ được thay nó khi reconstruction chứng minh **cùng fact** bằng source có provenance rõ; không được cho Vũ “đoán hộ”.

---

### SLOT X — cross-cell relation

Bắt buộc X_VERIFIED = TRUE.

Canonical strongest route:

- **C24 + C25 → C26.**

C03 có thể là early bridge rất tốt nhưng không tự chứng minh network.

Điều player phải tự hiểu:

- hospital issue và Tân Lộ issue không chỉ cùng có chữ “y tế”;
- hai nhánh có cùng risk endpoint/timing;
- vụ Phúc là nhánh người bị tác động chứ không phải một scandal riêng.

Vũ có thể verify relation, nhưng game không auto-link notebook thay player.

---

### SLOT D1 — current command authority

Cần một source hiện tại cho thấy Nam có quyền quyết định trên nhiều branch.

Canonical route:

- **C32** — manager-level source xác nhận pause/cleanup toàn nhánh cần Nam approve/định hướng.

Một source manager tương đương chỉ hợp lệ nếu họ trực tiếp biết decision chain của branch mình.

C27/C28/C30 không thay được D1.

---

### SLOT D2 — independent corroboration

Cần một nguồn độc lập với D1:

- **C31** — current crisis Khải → Nam contact metadata;
- hoặc route **C33/C34** đủ mạnh để police xác minh command pattern cross-cell.

Canonical clean route:

- C31 + C32.

Alternative clean route:

- C32 + C33/C34.

Không cho một manager statement đứng một mình quyết định boss.

---

### SLOT T — preservation timing

Trước CLEANUP LOCKED:

- A = PRESERVED;
- B = PRESERVED;
- C = PRESERVED;
- X_VERIFIED = TRUE;
- COMMAND = C4.

Đây là requirement true cuối cùng.

---

## 11.2. Những inference player phải tự có

True Ending không yêu cầu accusation quiz, nhưng player phải thể hiện các inference qua hành động:

### I1 — E22 là reclassification, không phải “Tuấn chọn Bắc”

Player phải dùng C17/C20/C22 hoặc equivalent để thoát false theory.

### I2 — ba box là cùng structure

Player phải nhận ra relation đủ để đưa đúng sources cho Vũ kiểm chứng, không chỉ thu thập chúng như collectibles.

### I3 — relationship không phải command

Player phải hiểu:

- C27/C28/C30 = Nam có lịch sử phù hợp;
- C31/C32/C33/C34 = Nam có quyền hiện tại.

Confront Nam ở C1/C2 là premature.

### I4 — evidence custody quan trọng hơn sở hữu

Player phải hiểu rằng giữ mọi thứ trên Bắc không làm case mạnh hơn.

C42 là payoff của inference này.

---

## 11.3. Ai phải được tin

Không có “trust the good NPC” như quiz đạo đức.

Player phải tin **đúng phạm vi knowledge**.

### Phải tin đủ để route sống

- **Vũ:** phải tin đủ để chuyển source có provenance cho police.
- **Huyền:** tin rằng review của bà là compliance source thật, dù bà không biết conspiracy.
- **Phúc:** tin phần chronology/coercion đã được corroborate, không tin suy đoán vượt knowledge.
- **Đức/Yến/Thảo:** chỉ tin phần họ trực tiếp biết nếu route dùng họ.

### Không được dùng như secure channel

- **Minh:** bạn thật, nhưng không phải kênh an toàn cho investigation.
- **Nam:** kindness thật không làm ông đáng tin về network.
- **Khải:** có thể nói fact hẹp đúng nhưng framing luôn bảo vệ system.
- **Hùng/Khoa/Hạnh:** có knowledge thật nhưng incentive tự cứu rất mạnh.

### Không được nghi sai tới mức dừng mystery

- **Tuấn:** có lỗi nghề nghiệp thật nhưng không phải core network.
- **Huyền:** giữ review không đồng nghĩa che review.

---

## 11.4. Timing phải đúng

Canonical timing:

- D+1 sáng: mở các source A/B/C khi window còn sống.
- Khoảng 12:00–14:00: player có thể đạt cross-cell understanding N3.
- Khoảng 14:00–16:00: Vũ đạt E38 nếu có đủ independent sources; A/B/C bắt đầu được preserve.
- Khoảng 15:00–18:00: command investigation mở.
- Trước khoảng late D+1 cleanup lock: D1+D2 phải được corroborate và preserve.

Không biến các giờ trên thành countdown tuyệt đối ở UI.

Chúng là objective pacing windows, có thể co giãn nhẹ theo scene implementation.

---

## 11.5. Bằng chứng nào phải còn tồn tại

True route cần giữ được:

- source chronology A;
- Huyền review trail + một corroborator B;
- reclassification/leadership trail C;
- cross-cell connector;
- current command source;
- independent command corroborator;
- police intake/preservation record.

Không yêu cầu:

- C28;
- toàn bộ optional clues;
- mọi screenshot Bắc từng chụp;
- một “master file”;
- mọi source còn quyền truy cập sau ending.

---

## 11.6. Vì sao cảnh sát lúc này có thể hành động

Trước E38, Vũ có các hộp rời.

Ở true route, anh có:

- A: human/coercion chronology;
- B: institutional hospital pattern + corroboration;
- C: leadership logistics involvement + corroboration;
- X: verified relation giữa các boxes;
- D: command chain tới Nam bằng ít nhất hai nguồn;
- source provenance đủ để biết đâu là fact, đâu là theory.

Đây là điểm qualitatively khác.

Police không hành động vì Bắc “đoán đúng boss”.

Police hành động vì nhiều nguồn độc lập bắt đầu xác nhận cùng architecture.

---

## 11.7. Vì sao Nam không thể đơn giản xóa hết dấu

Vì true route phá đúng cơ chế bảo vệ của Nam: compartmentalization.

Khi C42 đã xảy ra:

- Phúc/Vũ có chronology độc lập;
- Huyền/institution giữ review history;
- Tân Lộ có operation/finance/authority traces;
- command relation đã được preserve ngoài quyền của network;
- nhiều source nằm ở nhiều nơi khác nhau.

Nam có thể:

- cắt access;
- dừng operation;
- ra lệnh pause;
- hy sinh manager;
- thu hẹp network.

Nhưng ông không còn một nơi duy nhất để “xóa hết”.

Cố xóa đồng loạt sau preservation còn có nguy cơ tạo thêm dấu hành vi.

True Ending vì vậy thắng bằng **distributed corroboration**, không bằng việc Bắc giữ một USB.

---

## 11.8. Vì sao Bắc sống sót

Ba lý do cùng tồn tại:

1. **Evidence đã rời khỏi tay Bắc.** Làm hại Bắc không còn loại bỏ case.
2. **Nam ghét tạo vụ việc lớn.** Một sự cố công khai với sinh viên 18 tuổi sau khi police đã có case chỉ tăng attention.
3. **Vũ đã chuyển sang active preservation/coordination.** Bắc không còn tự đi một mình để lấy mọi source.

True route không đòi Bắc thắng Nam bằng sức mạnh.

Bắc sống vì player hiểu lúc nào phải ngừng làm người duy nhất giữ sự thật.

---

## 11.9. Tổ chức bị phá tới mức nào

Đủ thỏa mãn nhưng không giả vờ mọi lịch sử được giải quyết trong một tối.

### Bị phá

- operation hiện tại của Hành Lang không thể vận hành như trước;
- các cell chính mất compartmentalization;
- phần logistics/hospital/môi giới bị nối trong case;
- command architecture của Nam không thể chỉ đẩy tội xuống một manager;
- Khải/Nam bị kéo vào phần lõi của điều tra theo evidence;
- Hùng/Khoa/Hạnh chịu hậu quả theo phần culpability đã chứng minh.

### Không cần đóng tuyệt đối

- không cần giải mọi case lịch sử;
- không cần tìm mọi người từng giao dịch với network;
- không cần biến toàn Tân Lộ/Minh Trạch thành tổ chức tội phạm;
- không cần cho public biết toàn bộ bí mật;
- không cần giải thích mọi năm trong quá khứ của Nam.

---

## 11.10. Tình trạng nhân vật

### Bắc

- sống;
- trở lại đời sống sinh viên;
- không biến thành cảnh sát/thám tử chuyên nghiệp;
- hiểu việc “biết” tạo trách nhiệm nhưng cũng hiểu giới hạn của mình.

### Nam

- không được minh oan bằng lỗi cấp dưới;
- mất khả năng vận hành architecture như trước;
- bị nối vào command layer bằng current evidence, không phải chỉ history.

### Vũ

- chủ động xử lý phần lõi;
- chứng minh police competence;
- không trở thành người giải mystery hộ player.

### Phúc

- chronology của anh được đặt vào context đúng;
- không phải exposition machine.

### Huyền

- review được xác nhận là nguồn độc lập có giá trị;
- không trở thành “người duy nhất cứu bệnh viện”.

### Tuấn

- được loại khỏi core-network hypothesis nếu player đã theo C20/C22;
- vẫn chịu trách nhiệm cho việc làm ngơ với ngoại lệ nghề nghiệp.

### Minh

- nếu từng leak, hậu quả vẫn tồn tại nhưng không biến cậu thành villain.
- nếu không leak, cậu vẫn chỉ là bạn học bình thường.

### Thảo / Đức / Yến

- chịu hậu quả theo mức complicity/omission riêng;
- không ai tự nhiên được tha chỉ vì cuối cùng hợp tác.

### Lan / Linh

- chỉ biết phần cần thiết để Bắc an toàn;
- không bị kéo thành người biết toàn conspiracy.

---

## 11.11. Sự thật player hiểu

- Phúc là trigger của crisis có trước Bắc.
- Minh Trạch có cell/management involvement giới hạn.
- Tân Lộ leadership cố ý tham gia.
- Khải nối các branch về risk.
- Hùng/Khoa/Hạnh có tội nhưng không phải apex.
- Tuấn không phải core villain.
- Nam là command core.
- triết lý của Nam tạo incentive dẫn tới crisis.
- Bắc không phải “chosen one”; cậu chỉ là người đầu tiên nối đúng các box trong đúng cửa thời gian.

## 11.12. Sự thật vẫn chưa hiểu hết

- mọi case cũ của network;
- mọi quan hệ nghề nghiệp lịch sử của Nam;
- mọi người từng biết một phần;
- toàn bộ hậu quả pháp lý dài hạn.

Đây là khoảng chưa biết hợp lý, không phải plot hole.

## 11.13. Cảm xúc kết thúc

Giải tỏa mạnh nhưng không triumphant kiểu action movie.

Cảm giác:

- mình đã thật sự tự hiểu;
- mình đã giữ đúng thứ cần giữ;
- một phần cuộc sống bình thường trở lại;
- nhưng thế giới bình thường đó giờ có chiều sâu đáng ngờ hơn trước.

## 11.14. Ending screen

Bắc trở về phòng trọ sau một chuỗi ngày mất nhịp. Laptop mở bài học dang dở. Điện thoại có tin nhắn đời thường từ Linh/nhóm lớp. Ngoài hành lang, âm thanh sinh hoạt quay lại.

Không có bài diễn văn chiến thắng.

**NHỮNG MẢNH KHỚP LẠI**  
“Sự thật không nằm trong một mảnh. Nó tồn tại khi những mảnh độc lập không còn có thể phủ nhận nhau.”

---

# 12. LAST SUBTLE DETAIL — SAU TRUE ENDING

Chi tiết hậu true phải giữ đúng Stage 5 nhưng làm rõ cách trình bày.

Trong epilogue, bà Lan gom lại một hộp đồ sửa điện cũ Nam để lại.

Nếu player nhìn đủ lâu vào mặt dưới một món đồ bình thường trong hộp — ví dụ hộp nguồn/đồng hồ đo cũ — có một **tem bảo hành kỹ thuật bạc màu**.

Trên tem là:

- tên một đơn vị thiết bị/dịch vụ y tế cũ;
- một năm nằm trước giai đoạn Tân Lộ hiện tại;
- tên đơn vị này **không xuất hiện trong hồ sơ 2026 mà player vừa phá**.

Không:

- zoom camera;
- âm thanh sting;
- subtitle;
- notebook update;
- Vũ gọi điện nói “còn một tổ chức khác”;
- chữ to be continued.

Lan chỉ đặt món đồ vào thùng.

Ý nghĩa duy nhất:

**phần lịch sử nghề nghiệp của Nam dài hơn phần vụ án mà game vừa chứng minh.**

Nó không phủ định True Ending.

Nó không nói Nam thoát.

Nó không xác nhận một villain mới.

Một player không chú ý có thể hoàn toàn không thấy.

---

# 13. BRANCH MAP

S07 — Bắc có tiếp tục đào sâu không?  
├─ Không; vẫn N1, không leak, không chạm cell 2  
│  └─ G0 — MỘT CA LÀM THÊM  
└─ Có  
   ↓  
S08–S13 — xây A/B/C và bridge  
   ├─ Miss một source  
   │  ├─ còn alternate → tiếp tục  
   │  └─ alternate cuối đóng trước preservation  
   │     └─ G1 — QUÁ MUỘN  
   │  
   └─ đạt cross-cell understanding  
      ↓  
      BARC tiến tới N3 nếu hành vi để lại dấu  
      │
      ├─ Player bỏ toàn bộ contact khi police chưa preserve đủ
      │  └─ G3 — QUAY LƯNG QUÁ MUỘN
      │
      ├─ Player chia source/theory quá sâu cho Minh
      │  ├─ leak không làm mất route → tiếp tục, CLEANUP có thể nhanh hơn
      │  └─ leak làm route cuối của A/B/C đóng
      │     └─ G2 — SAI NGƯỜI
      │
      ├─ Player tự confront/để lộ source trực tiếp trước preservation
      │  ├─ chain vẫn recover được → tiếp tục nhưng CLEANUP nhanh hơn
      │  └─ direct exposure làm chain cuối gãy
      │     └─ G5 — BỊ NHÌN THẤY
      │
      └─ Player đưa sources cho Vũ
         ↓
         E38 threshold
         ├─ A/B/C chưa đều PRESERVED
         │  └─ G1 — QUÁ MUỘN
         │
         └─ A+B+C PRESERVED + X_VERIFIED
            ↓
            S16–S17 — command investigation
            ├─ chỉ có C27/C28/C30
            │  └─ COMMAND C1 — hypothesis, chưa đủ
            ├─ có current link nhưng thiếu corroboration
            │  └─ COMMAND C2/C3 — vẫn chưa đủ
            └─ D1 + D2 được corroborate
               ↓
               race với CLEANUP
               ├─ CLEANUP LOCKED trước COMMAND C4
               │  └─ G4 — DỌN SẠCH
               └─ COMMAND C4 trước cleanup lock
                  └─ G6 — NHỮNG MẢNH KHỚP LẠI

---

# 14. ROUTE-LOCK TABLE

| Route | Không khóa ở | Thực sự khóa khi |
|---|---|---|
| Neutral | thấy anomaly | player chủ động kết thúc S07 ở N1 và time progression đóng curiosity route |
| Delay | miss clue đầu tiên | alternate cuối cho required fact đóng |
| Wrong Trust | nhắn Minh | leak qua Minh gây source closure không còn alternate trước preservation |
| Avoidance | Bắc nói muốn dừng | player bỏ contact sau N3 + police chưa đủ preservation + source windows đóng |
| Cleanup | player chưa có D ngay | A+B+C đã safe nhưng D không đạt C4 trước cleanup lock |
| Exposure | confront một câu | direct leak làm unique source/chain thực sự gãy trước preservation |
| True | nghi đúng Nam | A+B+C preserved + X verified + D1+D2 preserved trước cleanup lock |

---

# 15. SOFT WARNING LANGUAGE — NGUYÊN TẮC

Game không được nói:

- “Lựa chọn này sẽ khóa True Ending.”
- “Minh sẽ phản bội.”
- “Bạn còn 5 phút.”
- “Hãy đưa C31 cho Vũ.”
- “Đây là clue bắt buộc.”

Warning phải đến từ thế giới:

- quyền truy cập thay đổi;
- source nói họ sắp mất access;
- Vũ hỏi provenance;
- Minh có thói quen báo người có quyền;
- Khải/Hùng/Khoa bắt đầu thu hẹp phạm vi;
- nhiều branch đổi trạng thái cùng lúc;
- Nam biết những điều chỉ có thể biết từ report observable.

---

# 16. SOFTLOCK AUDIT

## 16.1. Player có thể vô tình khóa mọi route quá sớm không?

**Không, sau chỉnh.**

Rules:

1. Miss một clue không khóa route nếu alternate còn sống.
2. Main story luôn có fail-forward tới ít nhất một partial/bad ending.
3. Neutral chỉ xảy ra khi player chủ động không bước sang N2.
4. True route chỉ khóa khi một required fact mất **tất cả** path hợp lệ hoặc cleanup lock đi qua.
5. Game phải telegraph source-window closure trước khi alternate cuối biến mất.

---

## 16.2. Có ending nào chỉ khác cinematic nhưng cùng logic không?

Đã tách:

- **Delay:** không có đủ source vì timing/miss.
- **Wrong Trust:** source mất vì player chia sai qua Minh.
- **Exposure:** source/chain gãy vì player tự lộ trực tiếp.
- **Cleanup:** police đã có A+B+C nhưng command proof đến muộn.
- **Avoidance:** player chủ động rời route sau khi đã thành N3 threat.
- **Neutral:** player chưa từng thành threat nghiêm trọng.
- **True:** preservation thắng cleanup.

Các ending có thể cùng thấy organization sống sót một phần, nhưng **nguyên nhân và knowledge state khác nhau**.

PASS.

---

## 16.3. Có state vô dụng không?

Các state scene-level như C03_SAVED, TUAN_FALSE_THEORY không dùng trực tiếp ở resolver.

Stage 6 chỉ cần:

- BARC;
- CASE A/B/C;
- X_VERIFIED;
- COMMAND;
- LEAK_PATH;
- CLEANUP;
- ABANDON_AFTER_N3.

TRUE_ROUTE_AVAILABLE là derived condition, không lưu riêng.

PASS.

---

## 16.4. Có một clue duy nhất quyết định quá nhiều thứ không?

Không.

- A cần hai nguồn.
- B cần C11 + C12/C15.
- C cần reclassification fact + corroborator + leadership.
- D cần current command + independent corroboration.
- X cần relation được verify.
- C42 là event preservation, không phải pixel clue.

C28 không bắt buộc.

C31 không đứng một mình.

C32 không đứng một mình.

PASS.

---

## 16.5. Có thể đạt True Ending bằng brute-force lựa chọn mà không hiểu mystery không?

**Không nên.**

Production phải giữ ba cơ chế:

### Một — source windows chồng nhau

Player không thể vô hạn “nói với mọi người, thử mọi option” mà không trả giá timing.

Không cần biến game thành timer gắt; chỉ cần event progression có hậu quả.

### Hai — evidence không phải collectible score

Sở hữu C27/C30 không tự biến Nam thành boss.

Sở hữu nhiều record không tự bật X_VERIFIED.

D chỉ mở khi player đi từ relationship → current command → corroboration.

### Ba — sai interpretation tốn thời gian/thay đổi consequence

Nếu player dừng ở Tuấn/Hùng, hoặc chia theory cho Minh, world reacts.

Không có accusation quiz để brute-force tất cả tên.

Tuy nhiên game cũng không được giả tạo bằng cách bắt Vũ cố tình không suy luận từ evidence ông đã thật sự có.

Nếu police đã được player cung cấp đủ source có provenance, police phải xử lý chúng có năng lực.

PASS với điều kiện implementation giữ event windows và provenance logic.

---

# 17. TRUE ENDING BLIND-RUN TEST

Một tester không biết hierarchy trước khi chơi phải có khả năng:

1. thấy E22 mismatch mà không kết luận crime;
2. nhận C17 rồi hiểu reclassification;
3. dùng C20/C22 để rời false theory Tuấn;
4. lấy A từ Phúc/Vũ;
5. lấy B từ Huyền + C12/C15;
6. lấy C từ C17 + corroborator + C22;
7. thấy C24+C25 cùng endpoint và đưa relation cho Vũ verify;
8. không leak source quan trọng qua Minh;
9. đưa A/B/C sang Vũ trước khi access closure hoàn tất;
10. coi C27/C30 là history chứ chưa phải proof;
11. lấy current command evidence;
12. corroborate Nam bằng hai nguồn;
13. chuyển D cho Vũ trước cleanup lock.

Nếu tester phải biết trước “C31 quan trọng vì guide nói vậy”, implementation chưa đạt.

Nếu tester có thể tìm ra chỉ bằng việc đọc source, thời gian và knowledge boundaries, design đạt.

---

# 18. ENDING DIFFERENTIATION MATRIX

| Ending | Player hiểu mystery | Police giữ A/B/C | Nam proven | Failure core |
|---|---|---:|---:|---|
| Một ca làm thêm | rất ít | không | không | player không bước vào |
| Quá muộn | một phần/khá nhiều | thiếu | không/không đủ | timing/missed source |
| Sai người | khá nhiều | thiếu do leak | không/không đủ | trust channel |
| Quay lưng quá muộn | nhiều | chưa đủ | có thể nghi | withdrawal after N3 |
| Dọn sạch | rất nhiều | có | chưa preserve đủ | command proof too late |
| Bị nhìn thấy | nhiều/có thể rất nhiều | thiếu do direct exposure | có thể nghi đúng | operational exposure |
| Những mảnh khớp lại | gần toàn bộ core | có | có, preserved | corroboration thắng cleanup |

---

# 19. PRODUCTION RULES CHO STAGE 7+

1. Không thêm ending mới trừ khi nó có causal state khác thực sự.
2. Không cho một dialogue option đơn lẻ khóa true ngay nếu hậu quả chưa xảy ra.
3. Mỗi permanent route loss phải có ít nhất một soft warning trước đó.
4. Mỗi required fact phải có provenance rõ.
5. Không dùng death của NPC làm token để tăng stakes nếu objective truth không cần.
6. Không cho Nam biết notebook/inference riêng của Bắc nếu chưa có observable report.
7. Không để Minh leak dù player chưa cho Minh thông tin.
8. Không để Vũ chậm giả tạo sau khi A+B+C đã được corroborate.
9. Không cho confrontation với Nam là requirement true.
10. Không cho player “chọn Nam” từ list suspects để thắng.
11. Không biến C28 thành mandatory collectible.
12. Không biến cleanup thành “xóa sạch database”.
13. Không để Bad Ending — Exposure và Wrong Trust cùng resolve cho một nguyên nhân; dùng causal attribution.
14. Không cho Avoidance trigger trước N3.
15. Không cho True Ending yêu cầu tất cả optional clues.
16. Nếu scene implementation thay timing, phải giữ relative order:
    source windows → N3 → preservation threshold → command proof → cleanup lock.
17. Nếu thêm alternate clue cho A/B/C/D, nó phải chứng minh cùng proposition với independence tương đương; không được là shortcut exposition.
18. Ending screen phải ngắn, có nhãn và mô tả, nhưng cinematic trước đó mới là nơi thể hiện consequence.

---

# 20. FINAL LOGIC SUMMARY

Toàn bộ Stage 6 có thể rút thành:

**Bắc thấy anomaly  
→ có thể bỏ từ sớm và an toàn  
→ nếu đào sâu, phải xây A/B/C bằng source độc lập  
→ phải tự nhận ra các box liên quan và đưa bridge cho Vũ verify  
→ organization chỉ tăng threat state khi hành vi Bắc để lại dấu  
→ sai trust có thể làm cleanup nhanh hơn nhưng không auto-game-over  
→ sau N3, giữ evidence một mình là nguy hiểm  
→ A/B/C được preserve thì police route trở nên thật  
→ late game chuyển câu hỏi từ “ai đáng ngờ?” sang “ai có quyền command?”  
→ history của Nam không đủ  
→ current command + independent corroboration mới đủ D  
→ nếu D được preserve trước cleanup lock, True Ending  
→ nếu command đến muộn, Cleanup  
→ nếu source chết vì miss, Delay  
→ nếu source chết vì Minh leak, Wrong Trust  
→ nếu source chết vì player tự lộ, Exposure  
→ nếu player bỏ sau N3 khi case chưa an toàn, Avoidance.**

Difficulty của ending system vì vậy nằm ở:

- reasoning;
- provenance;
- trust;
- timing;
- preservation;
- hiểu knowledge boundary của NPC.

Không nằm ở:

- hidden score vô lý;
- một clue pixel;
- chọn đúng tên boss;
- savescum một câu thoại;
- combat;
- police ngu;
- villain confession.

**END — BRANCH & ENDING LOGIC / STAGE 6**
