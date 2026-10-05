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

Không tăng BARC vì private inference, giữ copy kín, scene completion hoặc baseline closure. Report ledger ghi sender, exact disclosed/witnessed payload, recipient và received_at; Minh không biết phần Bắc chưa chia, Nam không nhận report tới Khải cho đến khi actual forward. Cùng received reports cho cùng BARC dù private theory khác. N3_UNDERSTANDING/KHẢI_LAYER/X_PLAYER_CONNECTED riêng; raw sources đầy đủ cho Vũ verify X độc lập.

---

## 1.2. CASE — trạng thái evidence theo proposition

Không cần giữ hàng chục boolean clue ở ending layer.

Mỗi slot A, B, C có ba trạng thái:

- **0 — MISSING:** chưa có source đủ.
- **1 — ASSEMBLED:** đã có đủ nội dung và nguồn để proposition có cơ sở, nhưng chưa được Vũ bảo toàn đầy đủ; người giữ có thể là player hoặc investigation đã có.
- **2 — PRESERVED:** source cốt lõi đã được Vũ/police tiếp nhận hoặc được giữ trong một chain hợp lý ngoài quyền xóa của network.

Các slot:

- **A:** thỏa thuận môi giới trả tiền để cung cấp nội tạng, trình bày như hiến tự nguyện; Phúc muốn rút rồi bị ép tiếp tục, được xác thực ngoài lời Phúc.
- **B:** cell hospital biết phần tiền và withdrawal nhưng vẫn hỗ trợ hồ sơ có vẻ consent hợp lệ.
- **C:** Hùng đã nhận mục đích trả tiền cho người hiến, vẫn approve xử lý/hạ luồng cùng nhóm hồ sơ, được corroborate độc lập.

CASE đo đủ proof/custody của investigation, không đo Bắc đã xem bao nhiêu. E12 chỉ có phần trình báo/liên lạc; E28 bổ sung exact core-agreement/withdrawal messages Phúc còn giấu, so exact content từng fact với original broker counterpart thread giữ trước intake; hospital request xác nhận visit, metadata xác nhận exchange/order, hai phần sau không authenticate money/pressure text. Từ E28, baseline CASE.A=2 trước S09. A_PLAYER_SEEN/A_PLAYER_UNDERSTOOD là scene flags riêng; Bắc không phải giao lại chronology của Vũ. Không hạ A vì player xem muộn hoặc miss C09. Fixture thiếu A chỉ hợp lệ khi ghi rõ exact fact/source nào thực sự chưa được nhận/xác thực, không reset custody đã có.

Không tạo score 0–100.

---

## 1.3. X_VERIFIED — bridge giữa các cell

Boolean:

- FALSE: common current risk/escalation context chưa được verify, dù quan hệ cùng giao dịch có thể đã rõ từ A/B/C.
- TRUE: Vũ đã verify common current risk/escalation relation từ các raw sources/context có provenance đã tiếp nhận.

X không tự bật chỉ vì player sở hữu nhiều clue.

X có hai profile tương đương về **common current coordination**, đều cần raw source có provenance đã vào custody:

- `X_RISK`: C24+C25/C26 xác thực cùng Khải endpoint, request/response scope và current Phúc crisis context từ hospital và logistics.
- `X_COMMAND`: D1 firsthand manager về một quyết định hiện tại, D2 original receiver-side Nam authorization cho quyết định **khác** tại branch kia kèm execution, cộng C10_SOURCE_LINK original broker request/forward/receipt match đúng D2 directive, tất cả trong cùng case. Profile này chứng minh coordinated current authority trên ba cell dù thiếu riêng Khải remit ở logistics.

Authenticate raw sources trước, normalize X từ hai profile, rồi derive COMMAND và ending. Không dùng X làm gate để tiếp nhận chính D1/D2/annex đủ mạnh sinh ra X: điều đó tạo vòng. Không cấp X từ enum COMMAND, clue ID, lawful consultant/authority không gắn current crisis, same transaction/account/keyword, display name hoặc private theory. Một order forward hai lần vẫn chỉ có một origin. ABC=2/X=false là state hợp lệ khi cả hai profile chưa đủ; police vẫn xử lý A/B/C đã giữ. Vũ verify raw sources đầy đủ độc lập với Bắc hiểu sai; `X_PLAYER_CONNECTED` riêng.
---

## 1.4. COMMAND — mức chứng minh Nam

Một enum duy nhất thay cho nhiều cờ nhỏ:

- **C0 — NONE:** Nam chỉ là hàng xóm.
- **C1 — HYPOTHESIS:** C27/C28/C30 khiến Nam đáng nghi nhưng chỉ chứng minh background/relationship.
- **C2 — CURRENT LINK:** có current-crisis relation tới Nam, nhưng chưa đủ command.
- **C3 — CORROBORATED COMMAND:** D1 manager firsthand + D2 authenticated decision ở branch khác, hai quyết định/origins độc lập; source-branch link đã verify để đủ phạm vi cả ba nhánh.
- **C4 — PRESERVED COMMAND:** các nguồn D1+D2 và source-branch verification context đã được Vũ/police bảo toàn trước cleanup lock.

True ending yêu cầu C4.

C27, C28, C30 không bao giờ tự nâng COMMAND quá C1.

---

## 1.5. LEAK_PATH — Bắc làm lộ route bằng cách nào

Một enum:

- **NONE**
- **MINH:** leak đi qua Minh vì Bắc chia quá nhiều trước preservation.
- **DIRECT:** Bắc tự confront Nam/Khải, đi cuộc hẹn không an toàn, hoặc để organization biết chính xác evidence đang nằm ở đâu.

LEAK_PATH là disclosure ledger có thể chứa cả MINH và DIRECT với timestamp, exact payload, recipient và receipt. Không có DIRECT-priority cho nguyên nhân kết thúc. `DECISIVE_LOSS` là record immutable của lần đầu một event đóng **đường cuối còn khả thi** cho một required slot trước preservation: `{at, sequence, slot: A|B|C|X|D, before_paths, after_paths, cause: MINH|DIRECT|BASELINE|ORDINARY_EXPIRY, warning_receipt, feasible_save_action}`. Tie dùng authored sequence; chỉ set khi after_paths rỗng và không có source police đã preserve có thể đáp ứng slot. Một event đóng hai slots cùng lúc dùng một cause/event. DIRECT/MINH attempt về sau vô hại không overwrite record. D-only loss được ghi như A/B/C loss; local closure không xóa custody đã có.

LEAK_PATH không tự động quyết định ending. Nó chỉ có ý nghĩa nếu leak **thực sự làm source đóng hoặc làm chain evidence gãy**.

---

## 1.6. CLEANUP — trạng thái race

- **BASELINE:** crisis cleanup theo objective timeline, local willingness/access11:00/11:30/12:30 riêng.
- **ACCELERATED:** actual report làm actor advance a future deadline; requires fresh received warning and feasible saving action. Minh/direct route alone không tự grant lock.
- **LOCKED:** global E40 command closure at17:00, hoặc deadline=max(16:30,W+145m) nếu sớm hơn17:00 sau actual warningW. Local source closures không enum LOCKED. Evidence đã police received/authenticate không bị hạ khi lock.

Single OBJECTIVE_TIME và once-charged event ledger tại OT §0.1 áp dụng toàn resolver: UI/reading/retries/private hypotheses0, fixed committed events/travel/waits only; save-load không duplicate cost hoặc giữ future receipt. Deadline/arrival cards là notice, không ticking failure meter. Canonical W14:00→16:30 vẫn để40m missing-source intake gồm ALL remaining authentication đủ actual E38+75m D pipeline+10m buffer; longer actual remainder phải qua OT §0.1 feasibility check hoặc giữ baseline17:00. Receipt/queue không grant E38; W muộn không được retroactively advance lock. Private understanding không tạo acceleration.

---

## 1.7. ABANDON_AFTER_N3

Boolean duy nhất cho Avoidance route.

Chỉ có giá trị nếu:

- BARC≥N3: organization thực sự có received reports coi Bắc là unresolved cross-cell threat. N3_UNDERSTANDING riêng, không dùng private understanding làm report hoặc thay ngưỡng awareness;
- CASE chưa được bảo toàn đủ;
- player chủ động cắt liên lạc và cố quay lại đời thường.

Bỏ cuộc ở N1 không dùng state này; đó là Neutral Ending hợp logic.

---

# 2. STATE KHÔNG CẦN Ở ENDING LAYER

Các biến sau vẫn có thể tồn tại ở scene scripting, nhưng không phải root state của ending:

- JOB_E22_SEEN;
- C03_SAVED/OBSERVED_AT từ intentional live-history inspect sớm hoặc muộn;
- C04_SEEN từ actual direct observation/label-visible media; default seal-only media không có label fact;
- source existence/access/willingness/copy custodian/receipt/authentication riêng;
- TUAN_FALSE_THEORY;
- TUAN_NOT_RECLASSIFIER;
- TUAN_CORE_SCOPE_VERIFIED;
- từng interaction nhỏ;
- từng optional lore clue;
- từng lần Bắc nói dối phòng vệ.

Chúng chỉ thay đổi cách player đi tới CASE/X/COMMAND/LEAK/CLEANUP. TUAN_NOT_RECLASSIFIER chỉ sửa attribution của E22. TUAN_CORE_SCOPE_VERIFIED là đánh giá từ assignment/permissions và lời Tuấn giới hạn đã được Vũ kiểm trong hồ sơ này; không có nghĩa chứng minh anh chưa từng biết bất cứ bí mật nào. Private suspicion không tự đổi CASE hoặc tạo penalty.

Không tạo một state chỉ vì một scene cần nhớ rằng player đã bấm một câu thoại.

---

# 3. TRANSITION RULES CỐT LÕI

## 3.1. Early game

E22 hoàn tất:

- BARC N0 → N1 chỉ khi E23 audit xác định worker và report tới Khải; knowledge Nam tăng sau actual E24 forwarding/receipt. E22 completion một mình không phải received report.
- E22 không tự tăng CASE; partial records đã police giữ từ E12 vẫn giữ. E28 độc lập hoàn tất A=2, không một clue Bắc xem tạo/reset institutional custody.

Player hoàn toàn có thể dừng ở đây.

Nếu Bắc không đào sâu, không leak, không chạm cell thứ hai:

- organization kiểm tra;
- thấy exposure thấp;
- route G0 có thể kết thúc.

---

## 3.2. Curiosity

Khi hành vi Bắc hỏi hoặc contact một nhánh được witness/disclose và exact report đã tới Khải:

- BARC có thể N1 → N2 theo payload đã nhận. Giữ source kín hoặc private inspect/inference không tự nâng awareness.

Không được nhảy thẳng N3 chỉ vì player tìm được một clue.

BARC N3 chỉ xảy ra khi Khải/organization đã nhận reports đủ từ ít nhất hai cell về cùng Bắc và hành vi chạm/nối nguồn, có payload/recipient/time. Không cần Bắc privately hiểu đúng. Nam tăng knowledge chỉ sau actual report tới ông. N3_UNDERSTANDING riêng: facts observed đủ và explicit inference đúng current shared risk role/context; sai/thiếu thì giữ hypothesis. Baseline S14 giữ prior BARC nếu chưa có new reports.

---

## 3.3. Preservation

C42 không phải “một clue thần kỳ”.

C42 là consequence của việc player đưa source đúng cho Vũ.

Khi Vũ tiếp nhận đủ source:

- B/C hoặc nguồn còn thiếu tương ứng chuyển từ ASSEMBLED → PRESERVED; A đã PRESERVED từ E28 vẫn giữ nguyên.
- C42 ghi custody đang có cùng provenance của các source bổ sung, không bắt Bắc giao lại A.
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

CLEANUP chuyển LOCKED chỉ tại global E40 command deadline17:00 hoặc actual warned acceleration=max(16:30,W+145m)<17:00. Local Đức11:00/hospital11:30/Yến12:30 closures thay source access/willingness riêng, không tự enum LOCKED.

Warnings/save actions theo OT §0.1/CG §10, và actual late requests/receipts/auth offsets theo OT §0.2. A source request chưa nhận không được dùng như proof; deadlines evaluated bằng authored clock, không wall clock.

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

## 4.2. Late resolver — total terminal function

Chỉ resolve khi player xác nhận kết thúc/bỏ cuộc, hoặc warned last path/global deadline thật sự đóng. Nếu còn saving path, gameplay tiếp tục. Trước resolver: áp mọi receipt/authentication hoàn tất theo authored `OBJECTIVE_TIME` và sequence (custody receipt trước closure sau đó); derive `X_RISK`/`X_COMMAND` từ raw police sources; derive C3/C4; đọc `DECISIVE_LOSS`. CASE custody chỉ đi 0→1→2 và không lùi.

1. A/B/C đều 2, X=true, C4 preserved **trước** lock → **G6**; leak/lock sau đó không revoke.
2. Abandon explicit sau actual N3 report khi police chưa tự hoàn tất đường thiếu → **G3**. Full G6 custody thắng G3.
3. `DECISIVE_LOSS.cause=DIRECT` → **G5**; cause `MINH` → **G2**, kể cả mất riêng D khi ABCX an toàn. Earliest irreversible last-path loss thắng later harmless attempt của loại kia.
4. Mọi terminal còn lại với A/B/C=2 và X=true nhưng D/C4 thiếu hoặc muộn → **G4**. D-only baseline/ordinary expiry thuộc đây.
5. Mọi terminal còn lại → **G1**, gồm ABC=2/X=false; A+B, A+C, B+C weak/partial, một hoặc không slot preserved, và X-only expiry không có decisive leak. Cinematic hiển thị đúng police custody hiện có, không nói các case được bảo toàn đã biến mất.

Đây là partition đầy đủ cho late terminal states. Trước closure, hai slot hoặc ABC/X=false là **ongoing**, không auto G1; source alternative có thể nâng 1→2, X hoặc D. `CLEANUP=LOCKED` không xóa records; C3 đã corroborate không lùi khi nguồn ở custody, C4 chỉ tới sau đủ source D được preserve đúng hạn. G0 chỉ ở early exit S07.

### Resolver fixtures (terminal unless marked ongoing)

| State / event order | Expected | Custody and cause |
|---|---|---|
| ABC=2, X=false, no D, lock | G1 | A/B/C retained; missing sourced coordination stated, never G4 or G6. |
| ABC=2, X=true, C4 before lock, later DIRECT/MINH | G6 | Full custody immutable. |
| ABC=2, X=true, D-only ordinary expiry | G4 | A/B/C/X safe; Nam authority unproven in time. |
| ABC=2, X=true, D-only DIRECT last-path loss | G5 | Loss record D/DIRECT; preserved slots stay safe. |
| ABC=2, X=true, D-only MINH last-path loss | G2 | Loss record D/MINH. |
| MINH closes last B at t1, DIRECT attempt at t2 | G2 | First irreversible loss t1; later exposure harmless to classification. |
| DIRECT closes last D at t1, MINH attempt at t2 | G5 | First irreversible loss t1. |
| MINH report at t1, alternate C18/C19 open, eventual ordinary expiry | G1 or G4 by ABCX | MINH never decisive; retained police slots unchanged. |
| A+B=2, C=1, X=false, final path closes | G1 | Police keeps A/B, C assembled only. |
| A+C=2, B=0; B+C=2, A=0 in isolated fixture | G1 | Police keeps respective two; baseline real run starts A=2 after E28. |
| A+B=2, C source alternate open | ongoing | Do not finish just because route weak now. |
| ABC=2, X_RISK absent, full same-case D originals+manager+source annex | G6 if C4 timely | X_COMMAND computed from raw sources before resolver. |
| ABC=2, same transaction/account/keyword or C03 only, no risk/command profile | G1 at lock | No X. |
| ABC=2, lawful consultant authorized unrelated case, mismatched case/group, or only forwarded display-name Nam | G1 at lock | No X_COMMAND and no accepted D2. |
| ABC=2, one D decision duplicated across two custodians, or annex missing original scope match | G4 if X_RISK true; else G1 | No C4; forwarded copy is not independent D1/D2. |
| N3 report received, explicit abandon before police can finish, partial ABC | G3 | No private N3 shortcut. |

For any fixture with `A=0` after baseline E28, supply an explicit alternate-world missing exact receipt/authentication; never simulate that state by erasing E28 custody. Validate each event against OT warning and feasible action before a last path closes.
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

Tại terminal, không đạt đồng thời A/B/C=2 và X=true, và không có decisive MINH/DIRECT loss hoặc qualified G3. Có thể A/B/C đã được giữ đủ nhưng cả hai sourced X profiles vẫn thiếu. Với missing A/B/C, nguyên nhân có thể là:

- player miss source chính;
- route thay thế cuối cùng cũng đóng;
- player tới sau access window;
- hoặc đã confirm một observable extra visit/wait sau notice, với fixed cost làm actual clock qua deadline của source chưa received. Private false theory/reading0 không đóng source.

Không cần leak.

## Lựa chọn/clue dẫn tới

Ví dụ:

- miss C11 và cả C12/C15 route hospital;
- miss C17/equivalent reconstruction và không còn Đức/Yến + C22 đủ để dựng lại C;
- đến Đức sau E32 window;
- tiếp tục một hành động truy Tuấn sau scope correction/cảnh báo, khiến bỏ lỡ nguồn C22/corroborator còn thiếu; còn nghi trong đầu không gây closure;
- pre-E28 subset fixture thiếu exact core-agreement/withdrawal originals/authentication phải nêu record/fact chưa nhận; E28 hoàn tất độc lập. Đây không phải D+1 route mất A vì Bắc chưa xem/chuyển chronology; baseline A=2 không lùi.

## Điểm thực sự khóa route

Không khóa ở **clue đầu tiên bị miss**.

Chỉ khóa khi **đường thay thế cuối cùng cho một required fact cũng đóng**.

Đây là rule bắt buộc để tránh softlock vô hình.

## Cảnh báo mềm

- C43: access bắt đầu đổi.
- Người từng trả lời nay cần quyền khác.
- Đức báo willingness11:00, private copy vẫn còn; S08 saving action trước close, không badge=deletion.
- Huyền báo11:30 ở S09/S10 trước loss; group request/receipt hoặc Thảo10m vẫn feasible, không chỉ explanation sau khóa.
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

- `DECISIVE_LOSS.cause=MINH`, là earliest irreversible last-required-path loss; có thể thiếu riêng D trong khi ABCX đã giữ.
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
- Lấy được C31 contact lead nhưng không có manager D1 và authenticated D2.
- Có C32H nhưng thiếu C33_AUTH, hoặc có C32K nhưng thiếu C34_AUTH trước lock.
- Có hai-branch command pair nhưng chưa verify/preserve C10_SOURCE_LINK để gắn nhánh môi giới với cùng actual Nam-authorized directive.
- Mất Hùng C32H và không dùng recovery Khoa C32K + authenticated logistics record; pure C33+C34 không thay manager D1.
- Investigate Nam trực tiếp quá lâu thay vì chuyển D sang Vũ.

## Điểm thực sự khóa route

Khi command-source window đóng và CLEANUP = LOCKED trong khi A+B+C đã nằm an toàn với Vũ nhưng COMMAND chưa đạt C4.

## Cảnh báo mềm

- Nhiều branch đồng thời đổi trạng thái.
- Vũ chuyển từ hỏi “có chuyện gì” sang hỏi “ai có quyền ra quyết định”.
- C27/C30 được framing rõ là history/relationship, không phải command proof.
- C31 là lead; C32H/C32K là manager direct intake; C33_AUTH/C34_AUTH cùng C10_SOURCE_LINK là record/context có provenance cần preserve trong window hiện tại.

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
- Tuấn: C20 sửa attribution E22; nếu Vũ đã verify assignment, permissions và lời giới hạn, không còn cơ sở xếp anh vào core trong hồ sơ này. C20/C22 đơn lẻ không chứng minh một universal negative về knowledge.
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

- `DECISIVE_LOSS.cause=DIRECT`, là earliest irreversible last-required-path loss; có thể thiếu riêng D trong khi ABCX đã giữ.
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

### SLOT A — paid-organ agreement, withdrawal and pressure

Canonical route: **C08 + C10**.

C08 phải có nội dung thỏa thuận trả tiền gắn trực tiếp với việc cung cấp nội tạng dưới mô tả hiến tự nguyện, yêu cầu rút của Phúc, rồi sức ép tiếp tục viện tiền đã ứng. C10 so exact message content với original thread môi giới trực tiếp phía counterpart giữ trước police intake: broker promise tiền đổi cung cấp nội tạng/cách gọi hiến tự nguyện; Phúc agreement/withdrawal; broker pressure viện tiền đã ứng. Vũ thu từ đầu mối Phúc đã chỉ trong E12/C08 và so original phía Phúc tại E28 cho từng fact. Chronology hoặc bản sao lời Phúc lần hai không tạo authentication origin mới. Hospital timestamp chỉ xác nhận visit; counterpart metadata chỉ exchange/order; hai phần này không authenticate money/withdrawal/pressure text.

Origin C08 là những người thực sự viết từng message; Phúc giữ original. Vũ giữ phần E12 và nhận phần từng bị giấu ở E28, so bản gốc/counterpart rồi ghi provenance từng fact. Baseline A=PRESERVED từ E28 trước S09, dù Bắc xem muộn. C09 tăng fairness nhưng không bắt buộc. Equivalent phải giữ cùng nội dung crime và authentication độc lập, không chỉ withdrawal-before-pressure.

---

### SLOT B — knowing hospital assistance

Bắt buộc **C11 + C12 hoặc C15** có cùng fact:

- C11: review của Huyền đối chiếu yêu cầu kiểm tra của Phúc có tiền/withdrawal với hồ sơ vẫn mang nghĩa consent tự nguyện/không có trao đổi tiền.
- C12: receipt/approval history có trước intake cho thấy Khoa đã nhận và xác nhận thấy hai fact đó; version sau vẫn giữ vẻ consent hợp lệ và thu hẹp review.
- C15: Thảo xác nhận phần case mình trực tiếp xử lý có tiền bên ngoài và muốn rút nhưng hồ sơ bà tham gia vẫn giữ nghĩa tự nguyện; Vũ so đúng case/field với C11.

No-Thảo route C12 phải chứng minh knowledge **và** assistance, không chỉ Khoa đổi scope. Thảo không biết Nam/logistics/toàn mạng. C14 framing/C16 timing chỉ hỗ trợ, không thay fact knowledge. Hospital giữ original review/history, Vũ nhận và so với A đã authenticate. Player không cần cả C12 lẫn C15.

---

### SLOT C — informed logistics leadership involvement

Canonical route **C17 + C22 + C18 hoặc C19**:

- C17 chứng minh luồng bị đổi, chưa tự nói organ crime.
- C22 đặt approve/hạ luồng ở Hùng và có phần mục đích trả tiền cho người hiến mà ông đã nhận **trước** quyết định.
- C18 operational snapshot của Đức hoặc C19 đối soát finance của Yến độc lập match cùng nhóm bàn giao/đầu nhận/đợt thanh toán; Vũ so với A/B và C22 có provenance.

Đức chỉ biết record vận hành; Yến chỉ biết dòng tiền. Họ không thay knowledge payload C22 bằng pattern, không biết toàn mạng. Nếu miss C17 trực tiếp, police reconstruction chỉ thay đúng reclassification fact bằng source thật đã verify; C20 hoặc Đức đoán ai được secret briefing không thay C22.

C18/C19 có execution/settlement origin độc lập xác nhận handling thực tế cùng nhóm công việc; C17/C22 riêng ghi đổi luồng và approve, chưa thay fact đã thực hiện. Equivalent chỉ hợp lệ với cùng fact/origin/authentication theo BACKSTAGE §0.1, không thêm một copy approval.

---

### SLOT X — sourced cross-cell relation

Bắt buộc **X_VERIFIED=TRUE**. Canonical **C24+C25→C26** phải match Khải endpoint, current risk role, scope request/response và crisis context; không link chỉ vì same case/group hoặc cùng thời điểm. C03 là transaction bridge lead; equivalent phải reconstruct cùng current risk relation từ nguồn có provenance. Vũ verify từ đầy đủ raw sources/context đã tiếp nhận dù player inference sai; notebook không tự cấp understanding cho Bắc. X không đòi Nam authorize hoặc proof Khải là apex; đó là câu hỏi command tiếp theo của D.

**Source-branch verification cho full D:** C10_SOURCE_LINK là annex late S16 của case Phúc, không phải record hiện tại đã nằm ở E28. Lead là chính đầu mối môi giới trực tiếp phía counterpart Phúc đã chỉ trong E12/C08; Vũ đã thu original exchange A của đầu mối này ở E28. Custodian của annex là đầu mối đó, giữ original thread nhận từ Hạnh và reply mình gửi, không phải Phúc giữ liên lạc Hạnh–Khải. Sau E38 xảy ra thực tế trong run, tại S16 trong window 15:00–17:00 và trước E40 closure/cleanup lock, Vũ quay lại direct case intake để thu/giữ thread mới.

Acquisition dùng kênh riêng và động cơ tự phân định trách nhiệm của broker counterpart tại BACKSTAGE §0.1. Actual original intake phải xảy ra khi timely cooperation/contact còn mở; refusal/contact loss cần causal event và pre-loss warning, không random roll hoặc tự grant annex. Refusal late không xóa A đã preserve.

Payload annex phải cho đúng ba fact: (1) request Hạnh chuyển tới Khải nêu case Phúc và crisis đang xử lý, nằm trong phần forward chain broker thực sự đã nhận; (2) reply/forward Hạnh truyền quyết định Nam-authorized về ngừng case mới, giảm liên hệ và báo lại Phúc đã nói với ai, có case/scope khớp exact directive D2; (3) receipt của broker ghi đã nhận và áp dụng các giới hạn này trong nhánh nguồn. Vũ so original nội dung request/forward/receipt, endpoints gửi–nhận và scope case với original request/authorization/forward context C33_AUTH hoặc C34_AUTH đã authenticate tới Nam. Display name, lời Hạnh nói Nam duyệt, metadata hoặc broker tự kể lại đều chưa đủ. Nếu thiếu nguồn gốc forward chain hoặc không match đúng directive được Nam authorize, annex vẫn là lead, không full scope.

Annex chứng minh nhánh môi giới nhận/thực hiện cùng actual current directive D2; không cấp cho broker/Hạnh knowledge toàn mạng. Bản forward cùng order không được count thêm một independent D2. D1 vẫn phải là manager firsthand về một quyết định hiện tại khác; D2 là quyết định khác ở branch khác. Thiếu C10_SOURCE_LINK verified/preserved, pair chỉ support hai-branch hospital/logistics authority, chưa đủ BACKSTAGE §53.D **cả ba nhánh**, chưa nâng COMMAND=C3/C4. Police có thể verify/preserve annex dù Bắc chưa được xem toàn bộ, rồi chỉ chia kết luận/fields được phép; player không phải tự lấy thread từ Hạnh.

---

### SLOT D1 — firsthand current manager command

Chỉ **C32H hoặc C32K**:

- C32H: Hùng trực tiếp xin/nhận quyết định hiện tại từ Nam về pause/tiếp tục logistics, trong branch của ông.
- C32K: Khoa trực tiếp nhận quyết định hiện tại từ Nam về cell hospital, trong branch của ông.

Vũ intake manager trực tiếp tại S16, không Bắc ép confession. C17/C22 + record thu hẹp quyền Hùng đã nhận, hoặc C12 receipt/approval + record thu hẹp cell Khoa đã nhận, làm nguy cơ bị hy sinh cụ thể; họ tự chọn bảo vệ mình bằng đúng scope biết, không được miễn culpability. Thảo không thay Khoa vì không biết Nam. C27/C28/C30 lịch sử, C31 contact và record pattern không thay D1.

---

### SLOT D2 — authenticated other-branch decision and execution

Một kiến trúc, hai acquisition routes:

| D1 | D2 bắt buộc | Fact và origin độc lập |
|---|---|---|
| C32H logistics | C33_AUTH hospital | Original Nam authorization/approval chain qua Khải, có nội dung, quyền pause/tiếp tục/approve lại, nhận và thực hiện tại hospital; record có trước lời Hùng, hospital custody |
| C32K hospital | C34_AUTH logistics | Original Nam authorization/approval chain qua Khải với nội dung/scope và receipt/execution Tân Lộ; record có trước lời Khoa, logistics custody |

**Authentication D2 cụ thể:** Khải trình yêu cầu trong kênh approve đã có; institution custodian giữ bản trao đổi gốc nhận reply authorize từ chính endpoint của Nam, rồi Khải chuyển scope triển khai và institution ghi receipt/execution. Vũ thu trực tiếp original receiver-side reply đó trong hồ sơ hospital/logistics, so exact nội dung quyết định với request/forward/execution và kiểm endpoint tác giả qua nguồn quan hệ/đầu mối nghề nghiệp đã verify. Không chấp nhận chỉ một screenshot/forward do Khải tự gõ mang tên Nam, không suy tác giả từ display name hoặc timestamps. Receipt/execution xác nhận lệnh đã áp vào branch; original reply có tác giả/source xác thực mới xác nhận Nam authorize. Operational custodian chỉ xác nhận record mình giữ, không tự suy Nam là boss hoặc biết crime. Đây là record ở branch khác về quyết định khác với firsthand decision D1, không copy order D1 rồi đếm thêm nguồn.

Vũ thu bản gốc qua institution intake và đối chiếu endpoint identity bằng contact/relationship records đã có, kiểm lời authorize Nam, forward Khải và execution. C31 chỉ hỗ trợ lead/identity; tên display Nam, cuộc gọi tới số Nam hoặc Khải nói Nam duyệt chưa đủ. C34 generic simultaneous closures chỉ hỗ trợ timing; chỉ subset C34_AUTH có payload/authentication trên được dùng làm D2.

D1 phải là manager firsthand về một quyết định hiện tại; D2 là record **một quyết định hiện tại khác ở branch khác**, origin có trước intake. Hai copies cùng một forwarded Nam order không được count hai nguồn dù khác custodian. C10_SOURCE_LINK đối chiếu việc thực hiện ở nhánh môi giới với đúng directive D2, không được count lại chính forward đó làm một independent command proof.

Accepted full D: **(C32H + C33_AUTH) hoặc (C32K + C34_AUTH)**, với source-branch context C10_SOURCE_LINK đã verify/preserve. Authenticate bộ raw D trước khi normalize X; chính bộ này có thể lập X_COMMAND, không đòi X_RISK có trước. Mất Hùng còn Khoa + authenticated TL record; không có pure C33+C34 recovery, không có C31+C32 route, không có manager đứng một mình. Mất cả hai manager routes thì D1 chưa đủ.

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

C17/C20 hoặc nguồn equivalent sửa fact người đổi luồng và scope Tuấn; C22 mới đặt leadership/purpose ở Hùng. Chỉ action truy sai tiếp sau correction/cảnh báo có thể tốn source window; private belief không phải ending predicate. Đánh giá Tuấn không là core participant trong hồ sơ này phải qua Vũ verify assignment/permissions và lời giới hạn, không Đức biết secret briefing.

### I2 — ngoài giao dịch chung, có một tầng current risk/escalation chung

Hành động đặt relation đúng có thể mở yêu cầu source có scope cụ thể; giao đầy đủ raw sources/context để Vũ verify độc lập cũng hợp lệ. Không bắt Vũ bỏ qua dữ kiện đã giữ vì Bắc suy luận sai. X_PLAYER_CONNECTED/N3_UNDERSTANDING chỉ phản ánh Bắc đã hiểu, không thay X_VERIFIED hoặc là accusation quiz.

### I3 — relationship không phải command

Player phải hiểu:

- C27/C28/C30 = Nam có lịch sử phù hợp;
- C31 = current contact/identity lead, chưa nói authority;
- C32H/C32K + authenticated other-branch D2 = current authority trên hospital/logistics;
- C10_SOURCE_LINK verified với cùng D2 directive mới hoàn tất phạm vi cả ba nhánh.

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
- **Phúc:** tin exact paid-organ agreement, withdrawal và pressure messages đã authenticate; không count chronology kể lại thành nguồn độc lập hoặc tin suy đoán vượt knowledge.
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

OT §0.1–0.2 là shared fixed schedule; không co giãn một scene riêng hoặc convert reading speed thành objective time.

- A authenticated/preserved E28 D020:00–21:30.
- S08 morning09:00–09:35, required notice09:25, optional C18 local receipt09:45. S09 sourced payload10:15: once actually told contact/copy/deadline, Vũ collect C18 received10:35; actual bounded finance lead→C19 received10:50. Queue chưa receipt, later S12/S13 only verify retained sources.
- Hospital arrival10:50/10:55, core20m+Thảo10m finishes11:20/11:25 before local11:30; C11/C12 actual police receipt11:10. All local clocks11:00/11:30/12:30 differ from global lock.
- C22/C25 packet actual receipt13:00, raw current-risk X verify13:55, C required content authentication baseline14:55 triggers actual E38=t0 independently of private N3 success or scene end. Police advances from sources already held, no second request checkbox.
- Current decisions L: Nam issue13:20/logistics execution13:25; H: Nam issue13:45/hospital execution13:50. Hạnh request13:00 is actually forwarded with L13:30/broker receipt13:32 and H14:00/receipt14:05. These are two distinct original decisions, not retimed by private theory or later police intake. Original receiver-side Nam authorization and identity verification, not display name or villain exposition, establish authorship.
- After actual t0: manager request+5/receipt+25; OTHER-branch request+10, H receipt+40 or L+45, pair auth+60; broker private annex request+15/receipt+55/final exact-D2 match+75. Baseline t014:55 gives actual manager15:20, other-branch15:35/15:40, annex15:50 and full D16:10, before presentation finishes16:25. Never retroactive E28 annex.
- Baseline global17:00 allows latest t015:40→16:55. Canonical actual warned acceleration16:30 allows latest t015:10→16:25. Any delay matters only to required sources genuinely still unreceived; police custody/proactive processing already started cannot be retimed by Bắc waiting or traveling.

Warnings/save actions are the OT §0.1 and CG §10 table, mandatory BEFORE loss of the last path. A post-lock S14 explanation is not its earlier warning. Broker availability-only notice14:00 is not annex receipt; actual annex intake remains after E38. Required sourced intake40m/professional pipeline75m are shown before a deliberate wait that would overrun the deadline. Reading/hints/retries do not consume those windows.

---

## 11.5. Bằng chứng nào phải còn tồn tại

True route cần giữ được:

- exact paid-organ agreement/withdrawal/pressure A + authentication ngoài Phúc đã giữ từ E28;
- Huyền review + knowledge/assistance C12 hoặc C15;
- reclassification + C22 purpose đã nhận trước approve + matched C18 hoặc C19;
- sourced cross-cell connector và current source-branch execution context C10_SOURCE_LINK;
- C32H/C32K firsthand current manager;
- C33_AUTH/C34_AUTH đúng other-branch pair có independent origin;
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

- A: paid-organ agreement, withdrawal và pressure content được authenticate ngoài Phúc;
- B: hospital biết tiền/withdrawal nhưng tiếp tục hỗ trợ vẻ consent hợp lệ;
- C: Hùng đã nhận mục đích trả tiền cho người hiến vẫn approve/hạ luồng, được operational/finance match độc lập;
- X: sourced current shared risk/escalation role/context, ngoài relation cùng giao dịch ABC và không chỉ timing;
- D: firsthand manager + authenticated decision khác tại institution khác, cùng source-branch execution link đủ phạm vi cả ba nhánh;
- source provenance đủ để biết đâu là fact, đâu là theory.

Đây là điểm qualitatively khác.

Police không hành động vì Bắc “đoán đúng boss”.

Police hành động vì nhiều nguồn độc lập bắt đầu xác nhận cùng architecture.

---

## 11.7. Vì sao Nam không thể đơn giản xóa hết dấu

Vì true route phá đúng cơ chế bảo vệ của Nam: compartmentalization.

Khi C42 đã xảy ra:

- Vũ giữ original Phúc và original broker counterpart thread so exact A content tại E28; chronology ghi kiểm chứng, không origin crime độc lập thứ hai;
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

- C20 chỉ sửa attribution E22; sau Vũ verify assignment/permissions và lời giới hạn, không có cơ sở xếp anh vào core trong hồ sơ này; không universal negative về mọi knowledge;
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
            └─ accepted D1 + other-branch D2 và source-branch link verified
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
| True | nghi đúng Nam | A+B+C preserved + sourced X + accepted D pair và C10_SOURCE_LINK verified/preserved trước cleanup lock |

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

- A cần crime content C08 + C10 authentication origin ngoài Phúc; E28 custody không phụ thuộc player xem lại.
- B cần C11 + C12/C15 chứng minh knowledge và assistance, không chỉ scope/timing.
- C cần reclassification + C22 known paid-donor purpose + independent matched C18/C19.
- D cần C32H+C33_AUTH hoặc C32K+C34_AUTH, distinct current decisions/origins, cùng verified source-branch context cho đủ cả ba nhánh.
- X cần actual relation và endpoint/context được verify; C03 alone là lead.
- C42 là event preservation, không phải pixel clue.

C28 không bắt buộc.

C31 không là D1/D2 dù đi cạnh manager.

C32H/C32K không đứng một mình; generic C34 và pure C33+C34 không thay required pair. Hai copies cùng order không independent.

PASS.

---

## 16.5. Có thể đạt True Ending bằng brute-force lựa chọn mà không hiểu mystery không?

**Không nên.**

Production phải giữ ba cơ chế:

### Một — source windows chồng nhau

Retry/hint/reinspect/replay đã charged có cost0. Một cuộc hẹn/visit/contact mới thật có fixed cost hiển thị trước commit; không charge vì thử private interpretation.

Không cần biến game thành timer gắt; chỉ cần event progression có hậu quả.

### Hai — evidence không phải collectible score

Sở hữu C27/C30 không tự biến Nam thành boss.

Sở hữu nhiều record không tự bật X_VERIFIED.

Full D chỉ mở khi player đưa sourced relation để Vũ intake manager firsthand, authenticate quyết định khác ở branch khác và verify source-branch context của cùng directive; không mở từ contact/closures pattern.

### Ba — observable action có cost/report consequence, private interpretation0

Tuấn extra appointment+15m (5m local move+10m talk); chờ Hùng thay vì gửi required source+30m; new company/Minh disclosure+5m; deliberately dời intake+20m. Each cost/finish time and last-path warning precedes confirm. Actual reports chứa exact payload/recipient/receipt; police đã giữ sources vẫn proceed. Private suspicion, wrong endpoint và slow reading0.

Không có accusation quiz để brute-force tất cả tên.

Tuy nhiên game cũng không được giả tạo bằng cách bắt Vũ cố tình không suy luận từ evidence ông đã thật sự có.

Nếu police đã được player cung cấp đủ source có provenance, police phải xử lý chúng có năng lực.

PASS với điều kiện implementation giữ event windows và provenance logic.

---

# 17. TRUE ENDING BLIND-RUN TEST

Một tester không biết hierarchy trước khi chơi phải có khả năng:

1. thấy E22 mismatch mà không kết luận crime;
2. nhận C17 rồi hiểu reclassification;
3. dùng C20 để sửa attribution E22; chỉ Vũ verify assignment/permissions và lời Tuấn giới hạn mới cho đánh giá core scope trong hồ sơ;
4. xem đủ nội dung A từ Phúc/Vũ đã authenticate/giữ ở E28, không phải giao lại A;
5. lấy B từ Huyền + C12/C15 có fact knowledge/assistance tương đương;
6. lấy C từ C17 + C22 purpose trước approve + C18 hoặc C19 matched độc lập;
7. thấy C24+C25 có actual endpoint/context và đưa relation cho Vũ verify, không C03 alone;
8. không leak source quan trọng qua Minh;
9. đưa B/C và sourced X còn thiếu sang Vũ trước access closure, ghi custody A đang có;
10. coi C27/C30 là history, C31 là contact lead, chưa phải authority;
11. mở direct police intake C32H hoặc C32K bằng cooperation trigger thuộc scope manager;
12. authenticate other-branch C33_AUTH hoặc C34_AUTH đúng pair, distinct decision/origin; verify C10_SOURCE_LINK cùng D2 directive cho đủ cả ba nhánh;
13. preserve accepted D pair và source-branch context trước cleanup lock.

Nếu tester phải biết trước “C31 quan trọng vì guide nói vậy”, implementation chưa đạt.

Nếu tester có thể tìm ra chỉ bằng việc đọc source, thời gian và knowledge boundaries, design đạt.

---

# 18. ENDING DIFFERENTIATION MATRIX

| Ending | Player hiểu mystery | Police giữ A/B/C | Nam proven | Failure core |
|---|---|---:|---:|---|
| Một ca làm thêm | rất ít | không | không | player không bước vào |
| Quá muộn | một phần/khá nhiều | có thể đủ ABC nhưng thiếu X | không/không đủ | missing proof/coordination, ordinary expiry |
| Sai người | khá nhiều | thiếu do leak | không/không đủ | trust channel |
| Quay lưng quá muộn | nhiều | chưa đủ | có thể nghi | withdrawal after N3 |
| Dọn sạch | có thể nhiều | có, X verified | chưa preserve đủ | D command proof too late; D-only ordinary loss |
| Bị nhìn thấy | nhiều/có thể rất nhiều | thiếu do direct exposure | có thể nghi đúng | operational exposure |
| Những mảnh khớp lại | gần toàn bộ core | có | có, preserved | corroboration thắng cleanup |

---

# 19. PRODUCTION RULES CHO STAGE 7+

1. Không thêm ending mới trừ khi nó có causal state khác thực sự.
2. Không cho một dialogue option đơn lẻ khóa true ngay nếu hậu quả chưa xảy ra.
3. Mỗi permanent last-needed-path loss có actual warning receipt BEFORE và saving action còn đủ fixed cost; gồm accelerated leak/global lock và late broker annex. Post-loss explanation không thay warning.
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
    actual source receipt/authentication → professional E38 → distinct current D intake/authentication → global cleanup lock; private N3 track riêng, local closures không global lock.
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
→ accepted manager + authenticated other-branch decision khác, cùng verified source-branch execution context mới đủ D cả ba nhánh  
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
