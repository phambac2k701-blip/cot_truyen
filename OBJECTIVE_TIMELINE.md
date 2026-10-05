# OBJECTIVE TIMELINE

> **Status:** STORY DESIGN — STAGE 3 / DESIGN LOCK CANDIDATE  
> **Parent canon:** `MASTER_GAME_BIBLE.md` — blob `c54f045db49e1523edf304165d2a8af09f5a45b2`  
> **Stage 1:** `BACKSTAGE_CRIME_TRUTH.md` — blob `be6d0e99a961945849543db13212c4f23c60a60b`  
> **Stage 2:** `CHARACTER_WEB.md` — blob `ce95ed982f7f45955c347b1e5b9499f9bd984bab`  
> **Repository:** `phambac2k701-blip/cot_truyen`  
> **Setting:** Hà Nội, 2026  
> **Scope:** timeline khách quan tuyệt đối; knowledge flow; evidence lifecycle; baseline không có protagonist; các điểm player có thể làm lệch lịch sử  
> **Không bao gồm:** chapter, scene direction, dialogue, puzzle design, clue placement gameplay chi tiết

---

# 0. NGUYÊN TẮC THỜI GIAN VÀ LOGIC

Tài liệu này không khóa một ngày dương lịch cụ thể vì canon hiện chỉ khóa **Hà Nội, 2026**.

Quy ước:

- **D0** = ngày Bắc chuyển vào dãy trọ và nhận việc ngắn qua Tân Lộ.
- **D−n / D+n** = số ngày trước/sau D0.
- Các giờ và costs tại §0.1–0.2 khóa chronology thực thi chung. Mọi đổi schedule phải cập nhật cùng travel, source receipts và warning/closure tables; không tự xê dịch từng scene.
- Event ghi **chỉ nếu player...** là event có điều kiện, không phải sự thật chắc chắn của mọi run.

Travel budget dùng để audit:

| Cặp khu | Thời gian tối thiểu hợp lý |
|---|---:|
| trong cùng hub | 5–15 phút |
| trọ ↔ trường | 20–30 phút |
| trọ ↔ Tân Lộ | 25–35 phút |
| Tân Lộ ↔ Minh Trạch | 25–40 phút |
| trọ ↔ Minh Trạch | 30–40 phút |
| trường ↔ Tân Lộ | 35 phút, authored route S03 |
| hospital area ↔ police micro-set / quiet point | 5 phút, cùng khu |

Game có thể dùng transition/fast travel giữa hub, nhưng **objective chronology vẫn phải dành đủ thời gian cho việc di chuyển**.

Nguyên tắc bằng chứng:

1. Không có `USB phá cả tổ chức`.
2. Evidence chỉ tồn tại nếu một hành động/hệ thống đã tạo nó.
3. Không xóa evidence tùy tiện nếu nó đã nằm ở hệ thống hợp pháp độc lập.
4. Organization chỉ xóa/thu hồi thứ họ **biết tồn tại và có quyền chạm tới**.
5. Xóa một institutional record có thể tạo audit anomaly; vì vậy Khoa/Hùng thường **thu hẹp, đổi cách trình bày, khóa access** trước khi nghĩ tới xóa.
6. Sau khi evidence được Vũ tiếp nhận/bảo toàn chính thức, Hành Lang không còn quyền đơn giản làm nó biến mất.
7. Mỗi source tách RECORD_EXISTS, SOURCE_ACCESS, SOURCE_WILLINGNESS và COPY_CUSTODY; có original/private copy không tự nghĩa đã authenticate, khóa account không xóa copy. Receipt/authentication ghi custodian và thời điểm riêng.
8. Tri thức Bắc (facts observed + explicit inference), police verification/custody và BARC (report đã nhận) riêng. Report lưu người gửi, exact payload, người nhận, thời điểm nhận; Nam không tự nhận mọi report tới Khải. Cùng report received cho cùng BARC dù private theory khác. Cleanup baseline không tạo awareness về Bắc.

---

## 0.1. SINGLE AUTHORED CLOCK — lịch thực thi chung

OBJECTIVE_TIME là ngày/phút trong fiction, không phải thời gian người chơi ngồi đọc. Clock chỉ tăng khi commit một event group có cost cố định, một chuyến đi thật, hoặc lựa chọn chờ/hẹn khác được báo trước. Reading, inspect, notebook, phone history, idle, hint, retry puzzle và private hypothesis đều 0 phút thêm. Dialogue dùng fixed cost khi group/checkpoint hoàn tất, không dùng độ dài voice/subtitle hoặc tốc độ đọc. Group có warning trước choice được chia checkpoints cố định: S08 CORE_A25m→09:25 rồi warning đọc0, CORE_B10m→09:35; total35m, từng charged flag riêng. Không ghi warning từ tương lai khi clock chưa tới checkpoint.

Mỗi group/travel/wait có event_id, cost, departure/arrival và charged flag. Save lưu nguyên clock, charged flags, warning/report receipts và source custody; resume/revisit không thu cost lần hai. Load một save trước commit khôi phục toàn state trước event, không giữ evidence tương lai hoặc bỏ qua cost. Reinspect không respawn source. Trước commit show thời gian tới/chờ hoặc departure→arrival; 90 phút gameplay chỉ là play budget, không là fail timer. Events hậu trường được xử lý theo clock này khi một committed group đi qua issued/request/received/auth time của chúng, không theo wall clock.

### Lịch Bắc trên main route

| Time card / event group | Cost cố định | Việc thật và receipt |
|---|---:|---|
| D0 S01 07:30→08:35; trọ→trường 08:35→09:00 | 65m +25m | Required ordinary beats rồi explicit departure; không exit vì idle. |
| S02 09:00→11:15; S03 11:15→11:49 | 135m +34m | Class/meal group rồi job conversation; UI/history không thêm phút. |
| Trường→Tân Lộ 11:49→12:24; check-in→12:30 | 35m +6m | Cùng arrival 12:24 đã có; đây là travel thật, không teleport. |
| S04 pickup 12:30→12:54; travel→13:24; handover→13:52; close job→14:10 | 24m +30m +28m +18m | C03 original time13:52; later observed_at riêng. |
| Nearby meal arrival14:30; S05 ordinary afternoon→17:30; về trọ→18:05; ordinary room beat→18:07 | 10m local move +10m chờ món +180m +35m +2m | Meal/study transition authored; audit18:07 sau beat cuối, không do reading. |
| S06 audit18:07→18:22; explicit chờ kết quả→20:00 | 15m +98m | Chờ/hẹn hiển thị trước confirm; S07 contact group20m, extra disclosed company call5m nếu chọn; ngủ/chờ sang08:30 D+1 là explicit transition. |
| D+1 trọ→Tân Lộ08:30→09:00 | 30m | Đúng bound25–35m. |
| S08 core09:00→09:35; optional C18 direct09:35→09:45 | 35m; +10m | Required notice09:25, actual bounded source/contact từ09:30; copy local received09:45 nếu chọn. |
| Explicit hẹn S09 lúc10:00; phone intake10:00→10:15 | 25m wait, hoặc15m sau direct copy; +15m | Sourced C17/group payload receipt10:15. Không physical police trip. |
| New source-address disclosure10:15→10:20; second distinct lead→10:25 nếu cần | +5m mỗi lead mới | Chỉ nếu source address/context chưa có trong payload đầu. Vũ tự collect nguồn đã được nói rõ; không request-checkbox lần hai. |
| Tân Lộ→Minh Trạch10:20→10:50, hoặc10:25→10:55 | 30m | Hai lead mới vẫn tới10:55; nếu không có lead thêm, explicit hẹn departure10:20 dùng5m wait. |
| S10 core10:50/10:55→11:10/11:15; optional Thảo→11:20/11:25 | 20m; +10m | Raw C11/C12 police received11:10; C15 actual receipt trước11:30 nếu chọn. |
| Explicit hẹn S11 lúc11:30; compare→12:00; hospital→Tân Lộ→12:30 | Remaining wait5–20m; +30m +30m | S11 tại quiet point/phone trong hospital area; không chuyến thứ hai tới police. |
| S12 retained verification12:30→13:00 | 30m | C22 original police receipt13:00; C18/C19 từ morning receipt, không fresh pickup. |
| Tân Lộ→hospital area13:00→13:30; micro-set→13:35 | 30m +5m | Micro-set Vũ dùng lại ở hospital area, không thêm hub. |
| S13 compare/callback13:35→14:00; S14 notices14:00→14:20 | 25m +20m | Retained-source verification; private inference đúng/sai không retime reports hoặc police. |
| S15 sourced intake/coordination14:20→15:00 | 40m | E38 actual baseline14:55 nếu required raw sources đã authenticate; scene completion không grant threshold. |
| S16 professional requests/receipts và presentation15:00→16:25 | 85m | Baseline full D actual verified/preserved16:10, không chờ hết presentation để custody. |
| Nếu chọn về trọ sau intake:16:25→17:00; S17 ordinary contact→17:15 | 35m +15m | Đúng hospital↔trọ30–40m. Custody đã có không lùi. Safety/bypass edge thuộc resolver pass sau. |
| Nếu cần quay police:17:15→17:50; S18 consequence từ17:50 | 35m | Không bắt quay lấy proof đã received; final route đọc actual records. |

Đây là lịch không thêm delay; event mới cộng đúng cost vào clock hiện tại, không snap lùi về time card cũ. Hẹn đã qua không thể nhận bằng retroactive timestamp. Police requests đã có chạy song song độc lập: một chuyến đi/chờ của Bắc không retime hoặc xóa actual police receipt.

### Morning police acquisition, không phải queue = proof

| Source | Actual request / contact | Actual received / verification | Local closure |
|---|---|---|---|
| C17 và group bridge | S09 payload10:15; source/archive query10:15 | C17 copy received10:15; original reclassification checked13:00 | Worker-history access11:00; original/archive và police copy còn. |
| C18 nếu Bắc lấy trực tiếp | Đức09:35→09:45; copy/custodian/time ghi rõ | Bắc local receipt09:45; police receipt10:15, origin/fields checked10:35 | Đức withdrawal of timely willingness11:00, không xóa phone copy. |
| C18 police route | Actual shared contact/copy/deadline10:15, hoặc genuinely new disclosure10:20; Vũ contacts10:25 | Actual bounded export/testimony received10:35; origin/fields checked10:45; matched C22 at13:55 | Cùng11:00 willingness; queue hoặc source name alone chưa là receipt. |
| C19 optional finance route | Actual bounded finance lead shared10:15/10:20/10:25; collector contact10:40 sau opening10:30 | Actual finance records received10:50; fields/origin checked11:00; matched C22 at13:55 | Yến quick cooperation/work access12:30; originals không biến mất. |
| C11+C12 hoặc C15 | New group-specific hospital request10:15, không lặp narrow visit query cũ | C11/C12 originals received11:10, knowledge/assistance checked11:20; C15 receipt11:20/11:25 nếu chosen | Review/Thảo timely channel11:30; bản received không mất khi scope co. |
| C22, C24, C25 | Vũ queries archive/risk records từ actual group bridge10:15; C22 follow-up12:30 | C24 hospital packet11:10; C22/C25 logistics packet13:00; X context check13:55, C content match hoàn tất14:55 | Local worker locks không xóa institution records hoặc professional copies. |

Các giờ receipt phía trên là baseline actual share đúng slot, không bảo đảm retroactive cho một run đến muộn. Với actual source disclosure q: C18 contact=max(10:25,q+5m), receipt=contact+10m, fields auth=receipt+10m; C19 contact=max(10:40,q+15m), receipt=contact+10m, fields auth=receipt+10m; hospital originals received=max(11:10,q+55m), check+10m. Chỉ nhận trong timely source window mới ghi receipt; deadline equality/after-close không backdate. Institution originals còn để điều tra sau run, không magic deletion. C22/C25 professional packet baseline13:00, delayed genuinely new group query shifts chưa-completed request response by actual delay; completed receipts không shift. E38 dùng actual receipt/auth completeness, không một scene hoặc queued request tự grant.

Nếu S09 đã chứa đủ source contact/copy/deadline, Vũ bắt đầu collection, không chờ một click xin lại. Nếu Bắc còn giữ source address/context, phải thật sự disclose mới có request. B/C/X không tăng vì queue; receipt và authentication là events khác. Một callback S12/S13 có thể verify copy received sớm, không invent acquisition trước deadline.

### Warning trước last-needed-path loss

| Notice actually received | Actor closure / time | Hành động cứu còn khả thi khi cảnh báo |
|---|---|---|
| S08 required09:25: worker history11:00, Đức chỉ nhận contact tới11:00, finance tới12:30 | Work access11:00 / Đức willingness11:00 / finance12:30, ba state riêng | Copy C17 now; nhận C18 trực tiếp09:35–09:45 hoặc share contact/copy/deadline tại S09 để actual receipt10:35; share bounded Yến lead để10:50 receipt. |
| S09 acknowledgment10:15 và S10 entrance10:50/10:55: review/Thảo11:30 | Hospital scope/access và Thảo timely channel11:30 | Vũ tự request raw review/history từ group payload; C11/C12 receipt11:10. Nếu C12 fact thật thiếu, scoped Thảo10m còn hoàn tất11:20/11:25. Không dùng post-lock notice thay warning. |
| S09 finance acknowledgment trước departure: Yến12:30 | Finance access/cooperation12:30 | Actual new bounded lead cho Vũ; request đủ sớm để contact10:40/receipt10:50. Alternative C18 đã nhận vẫn dùng; một local lock không global-lock case. |
| S13 callback/S14 entrance14:00: command channels baseline17:00; broker confirms availability only, chưa intake annex | E40 global17:00; local manager/record/broker timely channel cùng command deadline | Hand over any missing raw source now; Vũ tự mở selected manager + other-branch record + broker requests sau actual E38. Full pipeline75m, baseline E38 latest15:40 để completion16:55. |
| Nếu actual report gây acceleration: fresh deadline notice tới Bắc và Vũ tại W trước consequence | Global deadline=max(16:30, W+145m), chỉ advance nếu <17:00; canonical W14:00→16:30 | Remote sourced intake và toàn bộ remaining authentication tới actual E38 trong40m + professional D pipeline75m +10m buffer còn khả thi, theo feasibility check dưới đây. Nếu actual remainder không đủ trước candidate deadline hoặc W quá muộn, giữ baseline17:00; không retroactive lock. Latest E38 canonical accelerated15:10→completion16:25. |
| Late broker reminder15:00/actual case contact trước request | Broker willingness/contact closes at known global deadline, private originals vẫn có | Vũ request originals tại E38+15m và receives E38+55m; không Bắc tới gặp Hạnh, không random trust roll. Missing annex remains missing, A không lùi. |

W là actual warning receipt, không thời gian Bắc đọc hết UI. Bound145m gồm remaining notice group tối đa20m + remote missing-source intake/authentication40m tới actual E38 + professional D pipeline75m +10m buffer; không bắt đợi xong một unpriced scene nữa để cứu nguồn.

Advertised40m chỉ áp dụng cho bounded handover còn thực sự khả thi, và gồm ALL remaining steps để đủ actual E38: disclose đúng source/context, actual original/copy receipt, origin/identity/fields checks, exact-content/purpose verification và match/corroboration còn thiếu. Receipt, source name hoặc queue không grant E38; 75m sau E38 chỉ là D collection/authentication, không giấu phần B/C authentication chưa xong. Baseline morning match13:55 và full C content-auth14:55 giữ nguyên; late source không được thừa hưởng những timestamps ấy.

Nếu original acquisition hoặc independent verification còn cần hơn40m, ghi actual remainder R từ lúc saving action có thể bắt đầu tới authentication đủ E38, theo các request/receipt/check thật còn lại; không co steps để vừa40m. Giữ candidate deadline=max(16:30,W+145m), nhưng chỉ accelerate khi có plan thật thỏa W + remaining notice cost (tối đa20m) + R +75m +10m ≤ candidate deadline <17:00. Nếu chưa biết/không đủ remainder, giữ baseline17:00. Saving plan cũng phải còn source willingness/access thật; không restore một source đã đóng. Police work đã chạy vẫn song song, completed receipts/authentication không retime vì Bắc chờ.

Mọi actor event khác muốn đóng last usable path phải thêm warning receipt và saving action còn đủ authored cost trước close; không được tự làm local deadlines sớm hơn bảng vì leak. Leak có thể hạn chế direct C17 scope, nhưng C18/C19/professional reconstruction còn đường thật; nếu muốn đóng đường cuối phải dùng warning gate trên. CLEANUP=LOCKED chỉ tại global E40 command closure, không tại11:00/11:30/12:30. Nếu đã preserve required sources, closure không hạ custody.

### Observable false-apex actions

| Action đã confirm sau notice | Clock cost | Consequence thực |
|---|---:|---|
| Quay lại hẹn Tuấn cùng một việc đã được scope-corrected | +15m =5m local move +10m appointment | Arrival card và deadline notice trước commit. Private suspicion/retry0. Không xóa source police đã giữ. |
| Chờ Hùng rảnh thay vì gửi source còn thiếu cho Vũ | +30m deliberate wait | Show finish time và latest intake15:40 baseline/15:10 accelerated. Saving action là gửi sourced payload ngay; nếu police đã có threshold, case proceeds anyway. |
| Gửi thông tin đã chọn cho company/Minh qua contact mới | +5m | Chỉ exact disclosed payload vào report ledger; report receipt riêng, không toàn notebook. |
| Dời cuộc intake mới sang hẹn sau | +20m deliberate delay | Warning trước confirm nếu vượt local/global last path; queued request và existing custody không bị reset. |

Không có cost vì đứng trong UI, suy sai endpoint, vẫn nghi Tuấn/Hùng/Khải, nghe lại thoại hoặc đọc chậm. Những action này chỉ có consequence nếu actual clock/report/source custody tương ứng thay đổi.

## 0.2. CURRENT D RECORDS — issue trước intake, hai quyết định khác nhau

Các decisions sau do baseline crisis review/breach đang xử lý, hoặc actual received escalation reports, không do private E36 success. Nội dung là scoped pause/approve-again đối với cùng nhóm/case đang review, không phải lời thú nhận toàn mạng. L và H là hai request/authorization khác nhau, không copies của một order.

| Original event | Issued / received / execution trong D+1 | Origin/custodian và giới hạn |
|---|---|---|
| C24 current risk context | Khoa incident request09:10→Khải response09:20 | Hospital origin: crisis Phúc/review group, actual risk role và scope response; không chỉ call/account. Police receives11:10. |
| C25 current risk context | Hùng incident request09:15→Khải response09:25 | Logistics origin: breach/same crisis, actual risk role/scope; police receives13:00, compares13:55. |
| Hạnh bounded source request | Hạnh→Khải13:00: case Phúc, pause case mới/giảm liên hệ/báo lại Phúc đã chia với ai | Broker chỉ giữ phần forward Hạnh thực sự gửi xuống, không biết other-branch bodies hoặc whole network. Chưa police intake annex. |
| L — logistics current decision | Hùng request qua Khải13:10; original Nam reply authorize13:20; Tân Lộ receipt/execution13:25 | Pause next priority medical handovers cùng group/case, only resume with Nam approve-again. Original receiver-side Nam reply trong bounded approval channel Tân Lộ, forward/request/execution đều retained; operational custodian xác nhận records, không tự biết Nam/crime. Hùng firsthand L làm C32H. L original làm C34_AUTH cho Khoa route. |
| H — hospital current decision | Khoa request qua Khải13:35; original Nam reply authorize13:45; hospital receipt/execution13:50 | Pause new handling/intake trong review group/case, keep existing case in scoped review, only resume/contact changes with Nam approve-again. Hospital custodian giữ original receiver-side Nam reply, request/forward/execution. Khoa firsthand H làm C32K. H original làm C33_AUTH cho Hùng route. |
| Source execution of L | Hạnh forward13:30 giữ case request + exact L authorization scope; broker receipt/apply13:32 | Case mới/bàn giao trong scope bị dừng; reduce contact và report disclosure theo bounded directive. L annex match chính C34_AUTH, không được count lại forward làm independent D2. |
| Source execution of H | Hạnh forward14:00 giữ case request + exact H authorization scope; broker receipt/apply14:05 | Same bounded source responsibilities, gắn exact H decision/request khác L. H annex match chính C33_AUTH. Source giữ cả hai portions nếu thực sự đã nhận; không auto grant phần chưa nhận. |

Vũ authenticate authorship Nam từ original receiver-side reply, exact request/reply/scope/forward/execution và endpoint identity đã kiểm bằng professional contact origins. Display name, Khải tự gõ “Nam duyệt”, metadata hoặc Hạnh kể lại đều không thay original. Hạnh/broker không được cấp knowledge toàn branch kia; full scope được Vũ cross-verify từ distinct institutional originals.

| Police event sau actual E38=t0 | Baseline t0=14:55 | Actual receipt/auth và recovery |
|---|---|---|
| Manager own-branch request t0+5m | 15:00 | C32H hoặc C32K direct intake received t0+25m=15:20 nếu willing theo trigger trách nhiệm đã giữ. Vũ tự liên hệ known manager sources; refusal là actual causal event, không quiz/roll. Mất Hùng còn Khoa, không pure record-only D1. |
| OTHER-branch original request t0+10m | 15:05 | Hospital H received t0+40m=15:35 hoặc logistics L received t0+45m=15:40; identity/content/execution checked by t0+60m=15:55. Hùng pairs H, Khoa pairs L, không own-branch duplicate. |
| Known broker private-channel annex request t0+15m | 15:10 | Actual original request/authorization-forward/receipt received t0+55m=15:50; match exact chosen D2 + counterpart origin by t0+75m=16:10. C10_SOURCE_LINK first police receipt này, không E28/future record. |
| Full D custody | 16:10 | Chỉ accepted pair + matching source annex thật được received/authenticate. Presentation có thể tiếp tục tới16:25; custody không chờ scene end. |

Nếu t0 muộn vì required raw sources thật chưa received/authenticate, cộng offsets trên từ actual t0, không backdate. Nếu nguồn đã vào police trước delay của Bắc, Vũ tiếp tục và không chờ một click D-request khác. Baseline latest t0=15:40→16:55; canonical accelerated latest t0=15:10→16:25. Requests queued chưa là records hoặc proof. Không retime L/H creation theo t0 hay private hypotheses.

# 1. OBJECTIVE TIMELINE — HÌNH THÀNH HỆ THỐNG

## E01 — Nam có nền nghề nghiệp hợp pháp

- **Thời điểm:** Khoảng 15–20 năm trước D0.
- **Địa điểm:** Các doanh nghiệp/kênh kho vận, thiết bị và dịch vụ y tế hợp pháp tại Hà Nội.
- **Những người có mặt:** Vũ Đức Nam và các đối tác nghề nghiệp bình thường.
- **Chuyện khách quan xảy ra:** Nam làm việc hợp pháp trong kho vận/chuỗi cung ứng liên quan y tế và tích lũy quan hệ nghề nghiệp. Chưa có Hành Lang.
- **Nguyên nhân:** Lịch sử nghề nghiệp bình thường của Nam.
- **Hậu quả:** Nam hiểu cách logistics, dịch vụ y tế và các trung gian vận hành mà không cần trở thành người nổi bật.
- **Ai biết chuyện này:** Nam và từng người từng làm việc với ông biết phần lịch sử riêng của họ.
- **Ai chỉ biết một phần:** Lan về sau chỉ biết Nam từng làm kho vận/kỹ thuật.
- **Ai hiểu sai:** Chưa có hiểu sai mang ý nghĩa vụ án.
- **Bằng chứng được tạo ra:** Lịch sử việc làm và các quan hệ nghề nghiệp cũ.
- **Bằng chứng tồn tại ở đâu:** Hồ sơ nghề nghiệp cũ và ký ức của người quen.
- **Bằng chứng có thể biến mất lúc nào:** Một phần hồ sơ có thể hết vòng đời sau nhiều năm; đây không phải chứng cứ quyết định của vụ 2026.
- **Event tiếp theo mà nó gây ra:** E02.

## E02 — Giao dịch phi pháp đầu tiên

- **Thời điểm:** Khoảng 11–12 năm trước D0.
- **Địa điểm:** Không khóa địa chỉ cụ thể; ngoài khu trọ.
- **Những người có mặt:** Nam và các đầu mối trung gian đời đầu.
- **Chuyện khách quan xảy ra:** Nam giúp dàn xếp một giao dịch y tế phi pháp đầu tiên và tự coi nó là ngoại lệ.
- **Nguyên nhân:** Nam đã hình thành niềm tin sai rằng nhu cầu sống còn và tiền bạc tạo ra một thị trường có thể được 'sắp xếp' trật tự.
- **Hậu quả:** Ngoại lệ trở thành tiền lệ cho triết lý và mô hình tổ chức sau này.
- **Ai biết chuyện này:** Nam; các bên trực tiếp chỉ biết trường hợp riêng.
- **Ai chỉ biết một phần:** Không ai lúc đó thấy một cấu trúc hoàn chỉnh vì cấu trúc chưa tồn tại.
- **Ai hiểu sai:** Nam hiểu sai rằng có thể tách 'lựa chọn' khỏi hoàn cảnh tuyệt vọng.
- **Bằng chứng được tạo ra:** Dấu vết rời rạc của một giao dịch cũ.
- **Bằng chứng tồn tại ở đâu:** Nhiều phía khác nhau, không tập trung.
- **Bằng chứng có thể biến mất lúc nào:** Phần lớn không còn giá trị trực tiếp vào D0.
- **Event tiếp theo mà nó gây ra:** E03.

## E03 — Hạnh tham gia, nhánh môi giới hình thành

- **Thời điểm:** Khoảng 8–9 năm trước D0.
- **Địa điểm:** Mạng lưới dịch vụ y tế tư nhân và trung gian.
- **Những người có mặt:** Nam, Bùi Thu Hạnh, một số môi giới cấp thấp.
- **Chuyện khách quan xảy ra:** Hạnh bắt đầu điều phối việc tiếp cận những người đang yếu thế về tài chính; nhánh môi giới trở thành hoạt động có thể lặp lại.
- **Nguyên nhân:** Nam muốn nguồn người ổn định; Hạnh giỏi đọc hoàn cảnh và chốt thỏa thuận.
- **Hậu quả:** Các giao dịch rời rạc thành một cell chức năng.
- **Ai biết chuyện này:** Nam và Hạnh biết bản chất phi pháp.
- **Ai chỉ biết một phần:** Môi giới cấp thấp chỉ biết phần việc của mình.
- **Ai hiểu sai:** Nhiều người được tiếp cận tin thỏa thuận gần hợp pháp và quyền rút lại rộng hơn thực tế.
- **Bằng chứng được tạo ra:** Liên hệ, giấy tờ và lịch sử giao dịch phân tán.
- **Bằng chứng tồn tại ở đâu:** Phía môi giới và từng người tham gia.
- **Bằng chứng có thể biến mất lúc nào:** Một số liên lạc có thể bị xóa, nhưng không có một kho chứng cứ trung tâm duy nhất.
- **Event tiếp theo mà nó gây ra:** E04.

## E04 — Tân Lộ trở thành lớp logistics

- **Thời điểm:** Khoảng 6–7 năm trước D0.
- **Địa điểm:** Tân Lộ Logistics.
- **Những người có mặt:** Nam, Trần Quốc Hùng; phần lớn nhân viên Tân Lộ vẫn vô tội.
- **Chuyện khách quan xảy ra:** Nam giúp Hùng qua giai đoạn khó khăn; Tân Lộ dần nhận các hợp đồng y tế hợp pháp và một lượng rất nhỏ đầu việc bí mật.
- **Nguyên nhân:** Hành Lang cần một doanh nghiệp thật có đủ hoạt động bình thường để các ngoại lệ không tự nổi bật.
- **Hậu quả:** Logistics trở thành một cell của mạng lưới.
- **Ai biết chuyện này:** Nam; Hùng về sau hiểu rõ core crime.
- **Ai chỉ biết một phần:** Tuấn và một số tầng vận hành biết có ngoại lệ nhưng không biết mục đích thật.
- **Ai hiểu sai:** Nhiều nhân viên nghĩ đó là hợp đồng ngoài, khách VIP hoặc lách thủ tục.
- **Bằng chứng được tạo ra:** Luồng việc, khách hàng y tế, dòng tiền và ngoại lệ vận hành.
- **Bằng chứng tồn tại ở đâu:** Hệ thống doanh nghiệp Tân Lộ.
- **Bằng chứng có thể biến mất lúc nào:** Dữ liệu cũ có vòng đời khác nhau; dữ liệu gần D0 mới có giá trị chính.
- **Event tiếp theo mà nó gây ra:** E05.

## E05 — Cell Minh Trạch ổn định

- **Thời điểm:** Khoảng 5 năm trước D0.
- **Địa điểm:** Bệnh viện Minh Trạch.
- **Những người có mặt:** Phan Quốc Khoa; sau đó Lâm Thảo và một số mắt xích giới hạn.
- **Chuyện khách quan xảy ra:** Khoa trở thành đầu mối ổn định giúp một số trường hợp phi pháp đi qua lớp hành chính y tế có vẻ hợp lệ.
- **Nguyên nhân:** Mạng lưới cần một điểm kiểm soát y tế ổn định.
- **Hậu quả:** Hành Lang từ mạng giao dịch rời rạc thành hệ thống có khả năng lặp lại.
- **Ai biết chuyện này:** Nam, Khoa; Thảo biết phần việc phi pháp của mình nhưng không biết Nam.
- **Ai chỉ biết một phần:** Nhân sự y tế bình thường chỉ thấy hồ sơ đã qua các bộ phận chịu trách nhiệm.
- **Ai hiểu sai:** Phần lớn bệnh viện tin thủ tục đã được xử lý đúng ở nơi họ không phụ trách.
- **Bằng chứng được tạo ra:** Pattern hành chính nhỏ lặp lại qua nhiều hồ sơ.
- **Bằng chứng tồn tại ở đâu:** Hệ thống hồ sơ và audit trail của Minh Trạch.
- **Bằng chứng có thể biến mất lúc nào:** Không thể xóa toàn bộ an toàn; Khoa chỉ có thể làm chậm, thu hẹp phạm vi hoặc thay cách giải thích.
- **Event tiếp theo mà nó gây ra:** E06.

## E06 — Khải áp dụng compartmentalization

- **Thời điểm:** Khoảng 3–4 năm trước D0.
- **Địa điểm:** Các kênh quản lý lõi.
- **Những người có mặt:** Nam, Lê Duy Khải và các manager.
- **Chuyện khách quan xảy ra:** Khải tổ chức lại hệ thống để môi giới, logistics, bệnh viện và tài chính biết càng ít về nhau càng tốt.
- **Nguyên nhân:** Nam muốn giảm rủi ro một người cấp thấp có thể nhìn thấy toàn mạng.
- **Hậu quả:** Một nguồn đơn lẻ khó phá được mạng; đồng thời Nam phụ thuộc vào báo cáo qua nhiều tầng.
- **Ai biết chuyện này:** Nam, Khải và các manager biết giới hạn chức năng của mình.
- **Ai chỉ biết một phần:** Cấp dưới chỉ biết quy trình riêng.
- **Ai hiểu sai:** Nam và Khải đánh giá thấp nguy cơ nhiều manager cùng che lỗi cá nhân.
- **Bằng chứng được tạo ra:** Dấu vết quan hệ quản trị, contact pattern, các ngoại lệ có cấu trúc nhưng không có 'sơ đồ tổ chức tội phạm'.
- **Bằng chứng tồn tại ở đâu:** Phân tán qua nhiều hệ thống.
- **Bằng chứng có thể biến mất lúc nào:** Từng dấu vết riêng có thể vô nghĩa; chỉ có giá trị khi corroborate.
- **Event tiếp theo mà nó gây ra:** E07.

## E07 — Xung đột tăng trưởng âm ỉ

- **Thời điểm:** Khoảng 1–2 năm trước D0.
- **Địa điểm:** Tân Lộ và các kênh quản lý.
- **Những người có mặt:** Nam, Hùng, Hạnh, Khải.
- **Chuyện khách quan xảy ra:** Nam muốn giữ quy mô nhỏ; Hùng muốn doanh thu/quyền lực lớn hơn; Hạnh muốn hiệu suất nhánh cao hơn.
- **Nguyên nhân:** Mục tiêu cá nhân khác nhau trong một hệ thống phân quyền.
- **Hậu quả:** Ngoại lệ nhỏ tích lũy, đặc biệt dưới Hùng; incentive sai dần rõ hơn.
- **Ai biết chuyện này:** Mỗi manager biết lợi ích riêng của mình.
- **Ai chỉ biết một phần:** Nam biết Hùng có xu hướng tăng trưởng nhưng không biết toàn bộ ngoại lệ.
- **Ai hiểu sai:** Hùng tin thêm một ngoại lệ sẽ không làm hệ thống mất kiểm soát.
- **Bằng chứng được tạo ra:** Sai lệch vận hành và tài chính nhỏ.
- **Bằng chứng tồn tại ở đâu:** Tân Lộ; một phần nằm trong các số liệu Yến nhìn thấy.
- **Bằng chứng có thể biến mất lúc nào:** Hùng có thể sửa cách trình bày nhưng không bảo đảm xóa được lịch sử.
- **Event tiếp theo mà nó gây ra:** E08.


---

# 2. OBJECTIVE TIMELINE — KHỦNG HOẢNG TRƯỚC GAME

## E08 — Phúc chấp nhận thỏa thuận

- **Thời điểm:** Khoảng D−60.
- **Địa điểm:** Qua nhánh môi giới; ngoài bệnh viện.
- **Những người có mặt:** Trần Thanh Phúc, môi giới cấp thấp dưới Hạnh.
- **Chuyện khách quan xảy ra:** Phúc, đang khó khăn tài chính, đồng ý một thỏa thuận liên quan hiến tạng có trả tiền sau khi được làm nhẹ mức bất hợp pháp và rủi ro.
- **Nguyên nhân:** Áp lực tài chính của Phúc và cách nhánh môi giới framing lựa chọn.
- **Hậu quả:** Tiền/lịch/giấy tờ bắt đầu được sắp; case đi vào pipeline của Hạnh.
- **Ai biết chuyện này:** Phúc biết mình đã đồng ý; Hạnh biết đây là case của nhánh.
- **Ai chỉ biết một phần:** Môi giới cấp thấp biết case nhưng không biết cấu trúc lớn.
- **Ai hiểu sai:** Phúc tin quyền rút lại rộng hơn thực tế; Hạnh coi cam kết là gần khóa.
- **Bằng chứng được tạo ra:** Liên lạc với môi giới, giấy tờ và dấu vết tài chính của Phúc.
- **Bằng chứng tồn tại ở đâu:** Thiết bị/giấy tờ của Phúc và phía môi giới.
- **Bằng chứng có thể biến mất lúc nào:** Bản phía môi giới có thể bị xóa sau khi khủng hoảng; bản Phúc giữ không phụ thuộc họ.
- **Event tiếp theo mà nó gây ra:** E09.

## E09 — Phúc nghi ngờ rồi yêu cầu rút

- **Thời điểm:** Từ khoảng D−30; tuyên bố rút khoảng D−21.
- **Địa điểm:** Liên lạc từ xa và các điểm gặp trung gian.
- **Những người có mặt:** Phúc, môi giới cấp thấp; Hạnh nhận báo cáo.
- **Chuyện khách quan xảy ra:** Phúc hỏi sâu, nhận ra thực tế khác điều được nói và yêu cầu rút.
- **Nguyên nhân:** Thông tin và rủi ro không khớp kỳ vọng ban đầu.
- **Hậu quả:** Case có nguy cơ thất bại; Hạnh phải giải thích tiền và tiến độ nếu cắt.
- **Ai biết chuyện này:** Phúc, môi giới trực tiếp, Hạnh.
- **Ai chỉ biết một phần:** Khải chưa biết case đã vượt ngưỡng kiểm soát.
- **Ai hiểu sai:** Hạnh coi việc rút như thất bại giao dịch hơn là quyền cơ bản.
- **Bằng chứng được tạo ra:** Tin nhắn/cuộc gọi thể hiện Phúc muốn rút.
- **Bằng chứng tồn tại ở đâu:** Thiết bị Phúc và phía môi giới.
- **Bằng chứng có thể biến mất lúc nào:** Bản phía môi giới có thể mất; bản Phúc giữ vẫn là nguồn độc lập.
- **Event tiếp theo mà nó gây ra:** E10.

## E10 — Hạnh vượt doctrine và tăng sức ép

- **Thời điểm:** Khoảng D−21 đến D−14.
- **Địa điểm:** Nhánh môi giới.
- **Những người có mặt:** Hạnh, tầng môi giới dưới; Phúc là người nhận sức ép.
- **Chuyện khách quan xảy ra:** Hạnh không cắt lỗ như doctrine của Nam; bà cho người dưới gây sức ép mạnh hơn mức được phép và giấu việc đó khỏi Khải.
- **Nguyên nhân:** Sunk cost, sĩ diện nghề nghiệp và nỗi sợ mất vị trí.
- **Hậu quả:** Phúc quyết định tìm xác minh độc lập và trình báo.
- **Ai biết chuyện này:** Hạnh, người thực hiện và Phúc biết mức sức ép thật.
- **Ai chỉ biết một phần:** Khải chỉ biết case khó, không biết Hạnh đã vượt giới hạn.
- **Ai hiểu sai:** Hạnh báo cáo Phúc như người thay đổi thất thường.
- **Bằng chứng được tạo ra:** Liên lạc gây sức ép, lịch sử tiếp xúc, về sau là lời khai Phúc.
- **Bằng chứng tồn tại ở đâu:** Thiết bị Phúc, phía môi giới, sau này hồ sơ cảnh sát.
- **Bằng chứng có thể biến mất lúc nào:** Dữ liệu phía môi giới có thể bị dọn; lời khai và bản Phúc giữ không tự biến mất.
- **Event tiếp theo mà nó gây ra:** E11 và E12.

## E11 — Phúc kiểm tra tại Minh Trạch

- **Thời điểm:** Khoảng D−14.
- **Địa điểm:** Bệnh viện Minh Trạch.
- **Những người có mặt:** Phúc; nhân viên bình thường; dữ kiện cuối cùng chạm phạm vi Hoàng Huyền.
- **Chuyện khách quan xảy ra:** Phúc cố xác minh những gì mình được nói và tạo ra một anomaly nghiệp vụ khi vài thông tin không khớp hồ sơ/quy trình.
- **Nguyên nhân:** Phúc không còn tin nhánh môi giới.
- **Hậu quả:** Huyền có lý do nghề nghiệp để kiểm tra.
- **Ai biết chuyện này:** Phúc biết có mâu thuẫn; Huyền sau đó biết có anomaly.
- **Ai chỉ biết một phần:** Nhân viên tiếp nhận chỉ biết có một yêu cầu kiểm tra.
- **Ai hiểu sai:** Chưa ai phía hợp pháp kết luận tội phạm.
- **Bằng chứng được tạo ra:** Dấu vết yêu cầu kiểm tra và hồ sơ có điểm không nhất quán.
- **Bằng chứng tồn tại ở đâu:** Hệ thống bệnh viện.
- **Bằng chứng có thể biến mất lúc nào:** Không thể xóa sạch kín đáo; việc sửa/xóa sẽ tạo thêm audit anomaly.
- **Event tiếp theo mà nó gây ra:** E13.

## E12 — Phúc trình báo, Vũ nhận vụ

- **Thời điểm:** Khoảng D−14 đến D−12.
- **Địa điểm:** Cơ quan cảnh sát.
- **Những người có mặt:** Phúc, Đại úy Nguyễn Minh Vũ và nhân sự liên quan.
- **Chuyện khách quan xảy ra:** Phúc trình báo việc tham gia thỏa thuận, muốn rút và bị gây sức ép; anh kể thiếu một số chi tiết về mức tự nguyện ban đầu vì xấu hổ.
- **Nguyên nhân:** Sức ép vượt mức Phúc có thể tự xử lý.
- **Hậu quả:** Một investigation thật tồn tại trước khi Bắc can thiệp. Vũ gửi yêu cầu hẹp kiểm ngày Phúc tới Minh Trạch/yêu cầu kiểm tra; luồng tiếp nhận/compliance thường trả xác nhận cá nhân, timestamp và bộ phận nhận. Response đúng scope, không chứa multi-case review hay nội dung y tế người khác. Phúc chưa biết review-group/Tân Lộ account-family/routing key; Vũ vẫn theo đuổi nhánh môi giới và verification độc lập. C03/C17 về sau cho group bridge cụ thể để mở câu hỏi khác, không phải cảnh sát chờ Bắc mới hỏi.
- **Ai biết chuyện này:** Vũ biết có dấu hiệu môi giới, cưỡng ép và tiền bất thường.
- **Ai chỉ biết một phần:** Vũ biết Minh Trạch xuất hiện trong câu chuyện nhưng chưa có cơ sở coi bệnh viện là tổ chức phạm tội.
- **Ai hiểu sai:** Giả thuyết hợp lý ban đầu của Vũ là một nhóm môi giới nhỏ hơn thực tế.
- **Bằng chứng được tạo ra:** Biên bản, chronology và copies subset liên lạc Phúc đã giao, có receipt/custodian tại E12. Exact core-agreement/withdrawal messages Phúc còn giấu vì xấu hổ về mức đồng ý/tiền ban đầu chưa nằm trong subset này; partial record custody đã giữ không đồng nghĩa A đủ proof. Đầu mối broker counterpart đã được Phúc chỉ tên/kênh, không là NPC mới.
- **Bằng chứng tồn tại ở đâu:** Copies đã intake nằm trong hồ sơ cảnh sát, không phụ thuộc player-seen. Original subset và phần chưa giao ở Phúc; counterpart giữ original thread trên điện thoại mình để phân định việc mình làm với yêu cầu Hạnh. Xác nhận hospital request riêng vào hồ sơ trước E28.
- **Bằng chứng có thể biến mất lúc nào:** Hồ sơ cảnh sát không nằm trong quyền xóa của Hành Lang.
- **Event tiếp theo mà nó gây ra:** E13 và E18.

## E13 — Huyền mở review nhiều hồ sơ

- **Thời điểm:** D−12.
- **Địa điểm:** Minh Trạch.
- **Những người có mặt:** Hoàng Huyền và nhân sự compliance vô tội.
- **Chuyện khách quan xảy ra:** Huyền so một số hồ sơ tương tự và thấy pattern hành chính lặp lại, đủ để mở review nội bộ nghiêm túc.
- **Nguyên nhân:** Anomaly từ case Phúc không giống lỗi đơn lẻ.
- **Hậu quả:** Vấn đề chuyển từ một hồ sơ thành một pattern institution-level.
- **Ai biết chuyện này:** Huyền và những người trong luồng compliance biết review tồn tại.
- **Ai chỉ biết một phần:** Thảo thấy review chạm vùng nhạy cảm nhưng chưa biết phạm vi cuối.
- **Ai hiểu sai:** Huyền vẫn ưu tiên giả thuyết lỗi hệ thống/gian lận hành chính.
- **Bằng chứng được tạo ra:** Danh sách case review, ghi chú thời gian và audit trail mở review.
- **Bằng chứng tồn tại ở đâu:** Compliance system Minh Trạch.
- **Bằng chứng có thể biến mất lúc nào:** Không thể xóa kín đáo; có thể bị giới hạn quyền truy cập hoặc đổi scope.
- **Event tiếp theo mà nó gây ra:** E14.

## E14 — Khoa báo thiếu cho Khải

- **Thời điểm:** D−10.
- **Địa điểm:** Minh Trạch và kênh quản lý.
- **Những người có mặt:** Khoa; Khải nhận báo cáo; Nam nhận bản tổng hợp qua Khải.
- **Chuyện khách quan xảy ra:** Khoa hiểu review đe dọa cell nhưng mô tả phạm vi nhỏ hơn thực tế.
- **Nguyên nhân:** Sợ Nam đóng cell và bỏ Khoa đối mặt hậu quả.
- **Hậu quả:** Nam đánh giá khủng hoảng nghiêm trọng nhưng vẫn trong khả năng kiểm soát.
- **Ai biết chuyện này:** Khoa biết scope thật; Khải và Nam biết phiên bản giảm nhẹ.
- **Ai chỉ biết một phần:** Thảo biết có review nhưng không biết tầng Nam/Khải.
- **Ai hiểu sai:** Nam và Khải đánh giá thấp độ sâu phía bệnh viện.
- **Bằng chứng được tạo ra:** Review trail và các trao đổi quản trị không phản ánh đầy đủ sự thật.
- **Bằng chứng tồn tại ở đâu:** Minh Trạch và dấu vết liên lạc Khoa–Khải.
- **Bằng chứng có thể biến mất lúc nào:** Nội dung một số liên lạc có thể mất; timing/contact pattern và review trail vẫn tồn tại.
- **Event tiếp theo mà nó gây ra:** E15.

## E15 — Nam ra lệnh cleanup có kiểm soát

- **Thời điểm:** Chiều/tối D−10.
- **Địa điểm:** Qua Khải tới các cell.
- **Những người có mặt:** Nam, Khải; Hùng/Khoa/Hạnh nhận quyết định theo kênh tương ứng.
- **Chuyện khách quan xảy ra:** Nam tạm ngừng case mới, yêu cầu đánh giá exposure, giảm liên hệ giữa cell và xác định Phúc đã nói với ai.
- **Nguyên nhân:** Review bệnh viện + rủi ro Phúc.
- **Hậu quả:** Cleanup bắt đầu; nhiều manager đồng thời lo lỗi riêng bị lộ.
- **Ai biết chuyện này:** Nam, Khải và manager biết có khủng hoảng; mỗi người biết nguyên nhân ở mức khác nhau.
- **Ai chỉ biết một phần:** Hùng chỉ biết phải rà hoạt động y tế, không biết chi tiết review.
- **Ai hiểu sai:** Nam tin đã nhận đủ thông tin để quản trị đúng.
- **Bằng chứng được tạo ra:** Thay đổi lịch/ưu tiên, tạm dừng đầu việc, contact pattern quản lý.
- **Bằng chứng tồn tại ở đâu:** Từng hệ thống cell.
- **Bằng chứng có thể biến mất lúc nào:** Thông báo miệng có thể mất; hậu quả vận hành vẫn tạo dấu.
- **Event tiếp theo mà nó gây ra:** E16 và E17.

## E16 — Khoa tiếp tục giấu độ sâu review

- **Thời điểm:** D−8.
- **Địa điểm:** Minh Trạch.
- **Những người có mặt:** Khoa; Huyền tiếp tục review; Thảo quan sát vùng hồ sơ nhạy cảm.
- **Chuyện khách quan xảy ra:** Khoa thấy review chạm nhiều hồ sơ hơn báo cáo nhưng không cập nhật đầy đủ.
- **Nguyên nhân:** Tự bảo vệ vị trí và tránh bị cell cắt bỏ.
- **Hậu quả:** Nam không đóng cell đủ sớm; áp lực cleanup lan sang Tân Lộ.
- **Ai biết chuyện này:** Khoa và Huyền biết phạm vi dữ kiện ở các góc khác nhau.
- **Ai chỉ biết một phần:** Thảo biết review đáng ngại.
- **Ai hiểu sai:** Nam/Khải vẫn dùng thông tin thiếu.
- **Bằng chứng được tạo ra:** Version history của review và chênh lệch scope.
- **Bằng chứng tồn tại ở đâu:** Compliance system.
- **Bằng chứng có thể biến mất lúc nào:** Có thể bị hạn chế quyền truy cập; underlying audit trail vẫn tồn tại.
- **Event tiếp theo mà nó gây ra:** E17.

## E17 — Khải audit Tân Lộ; Đức và Yến bắt đầu hiểu xa hơn

- **Thời điểm:** D−7 đến D−5.
- **Địa điểm:** Tân Lộ.
- **Những người có mặt:** Khải ở tầng giám sát; Hùng, Tuấn, Đức, Yến trong công ty.
- **Chuyện khách quan xảy ra:** Khải yêu cầu rà hoạt động y tế. Hùng nhận ra ngoại lệ riêng sẽ lộ. Khi dữ liệu bị rà và cách trình bày bị sửa, Đức nhận ra các bất thường liên hệ nhau; Yến thấy dòng tiền đáng ngại hơn gian lận doanh nghiệp thường.
- **Nguyên nhân:** Lệnh cleanup E15.
- **Hậu quả:** Hùng tự cứu; Đức export phần log vận hành mình có quyền thấy, giữ cục bộ trong thư mục điện thoại cá nhân, không đồng bộ account Tân Lộ, để tự bảo hiểm; Yến im lặng nhưng tăng nghi. Copy không chứa toàn mạng/Nam hay secret briefing của ai.
- **Ai biết chuyện này:** Hùng biết core crime và lỗi riêng; Đức/Yến chỉ biết vector của họ.
- **Ai chỉ biết một phần:** Tuấn biết có audit và ngoại lệ nhưng không biết organ network.
- **Ai hiểu sai:** Đức có thể nghi Hùng là đỉnh; Tuấn vẫn nghĩ đây chủ yếu là sai phạm doanh nghiệp.
- **Bằng chứng được tạo ra:** Log rà soát/sửa dữ liệu, phần thông tin Đức giữ, đối chiếu tài chính của Yến.
- **Bằng chứng tồn tại ở đâu:** Originals vận hành/tài chính ở Tân Lộ; C18 private export ở điện thoại cá nhân Đức. SOURCE_ACCESS tới originals, SOURCE_WILLINGNESS của Đức và COPY_CUSTODY riêng.
- **Bằng chứng có thể biến mất lúc nào:** Khải chỉ biết access anomaly, chưa biết copy ở đâu/chứa gì. Account/badge revocation không xóa private export. Có thể mất timely cooperation/context; một seizure/deletion thật phải có event discovery và quyền chạm copy được ghi riêng, không default. Bản Vũ đã intake còn; originals công ty không thể xóa sạch mà không tạo gap.
- **Event tiếp theo mà nó gây ra:** E18.

## E18 — Khải phát hiện dấu hiệu leak

- **Thời điểm:** D−3.
- **Địa điểm:** Tân Lộ và kênh risk management.
- **Những người có mặt:** Khải; Hùng được hỏi; Đức nằm trong nhóm nghi ngờ.
- **Chuyện khách quan xảy ra:** Khải thấy một người đã truy cập/giữ thông tin không phù hợp nhiệm vụ và bắt đầu thu hẹp danh sách.
- **Nguyên nhân:** Hành vi tự bảo hiểm của Đức trong bối cảnh audit.
- **Hậu quả:** Nam yêu cầu giảm thêm điểm nối; Hùng càng sợ audit.
- **Ai biết chuyện này:** Khải và Nam biết có leak tiềm năng.
- **Ai chỉ biết một phần:** Hùng biết audit nội bộ đang siết.
- **Ai hiểu sai:** Khải chưa biết động cơ Đức là tự bảo vệ chứ chưa phải một whistleblower có kế hoạch.
- **Bằng chứng được tạo ra:** Access anomaly và danh sách nội bộ người cần kiểm tra.
- **Bằng chứng tồn tại ở đâu:** Hệ thống Tân Lộ/risk notes.
- **Bằng chứng có thể biến mất lúc nào:** Có thể bị dọn sau cleanup, nhưng trước đó đã tạo hành động quản trị.
- **Event tiếp theo mà nó gây ra:** E19.

## E19 — Hùng hạ gói nhạy cảm xuống luồng thường

- **Thời điểm:** D−1, cuối ngày.
- **Địa điểm:** Tân Lộ.
- **Những người có mặt:** Hùng; hệ thống dispatch; Tuấn/nhân viên vận hành chỉ thấy classification mới.
- **Chuyện khách quan xảy ra:** Một gói bàn giao nội bộ nhạy cảm cần di chuyển trước khi một số đầu việc bị đóng. Hùng cố tình hạ nó xuống luồng thường để tránh Khải hỏi vì sao nó chưa được xử lý trước.
- **Nguyên nhân:** Hùng sợ audit phát hiện hàng tháng ngoại lệ do mình tự cho phép.
- **Hậu quả:** Một lao động part-time hợp pháp có thể được phân job vốn không được phép ra pool thường.
- **Ai biết chuyện này:** Hùng biết lý do thật.
- **Ai chỉ biết một phần:** Tuấn thấy job bất thường nhưng không biết core crime.
- **Ai hiểu sai:** Hệ thống vận hành coi classification do cấp trên đặt là hợp lệ.
- **Bằng chứng được tạo ra:** Record reclassification, dispatch metadata; bản thân gói chứa một bridge giữa vài hoạt động nhưng không phải 'magic evidence'.
- **Bằng chứng tồn tại ở đâu:** Tân Lộ và gói vật lý.
- **Bằng chứng có thể biến mất lúc nào:** Gói có thể được thu hồi trong D0; metadata không thể biến mất sạch mà không tạo bất thường mới.
- **Event tiếp theo mà nó gây ra:** E20.


---

# 3. OBJECTIVE TIMELINE — D0

## E20 — Bắc chuyển vào trọ; Nam biết Bắc như hàng xóm

- **Thời điểm:** D0, 07:30–09:00.
- **Địa điểm:** Dãy trọ.
- **Những người có mặt:** Bắc, bà Lan; Nam có mặt trong tương tác đời thường.
- **Chuyện khách quan xảy ra:** Bắc chuyển tới. Nam biết có sinh viên mới, có thể biết tên và hoàn cảnh chung; ông chưa liên hệ Bắc với Tân Lộ.
- **Nguyên nhân:** Bắc mới lên Hà Nội học và thuê trọ.
- **Hậu quả:** Quan hệ Bắc–Nam tồn tại trước mọi knowledge về sự cố.
- **Ai biết chuyện này:** Lan và Nam biết Bắc là người mới ở trọ.
- **Ai chỉ biết một phần:** Không ai ở trọ biết vai trò thật của Nam.
- **Ai hiểu sai:** Bắc/Lan có lý do hợp lý để coi Nam là người hàng xóm lớn tuổi tử tế.
- **Bằng chứng được tạo ra:** Sổ thuê/tin nhắn sinh hoạt và ký ức đời thường; không phải evidence tội phạm.
- **Bằng chứng tồn tại ở đâu:** Khu trọ/thiết bị cá nhân.
- **Bằng chứng có thể biến mất lúc nào:** Không có cửa sổ xóa quan trọng.
- **Event tiếp theo mà nó gây ra:** E21.

## E21 — Bắc nhận kênh việc part-time

- **Thời điểm:** D0, 09:30–11:30.
- **Địa điểm:** Trường/khu lân cận.
- **Những người có mặt:** Bắc, Linh, Minh và sinh viên nền.
- **Chuyện khách quan xảy ra:** Vì thiếu tiền, Bắc quan tâm việc ngắn; Minh biết kênh tuyển part-time Tân Lộ và hướng Bắc tới một job hợp pháp.
- **Nguyên nhân:** Áp lực tiền của Bắc + Tân Lộ thực sự dùng lao động tạm thời.
- **Hậu quả:** Bắc có mặt trong pool đúng lúc job E19 được phân.
- **Ai biết chuyện này:** Minh chỉ biết đây là công ty logistics thật; Bắc không biết network.
- **Ai chỉ biết một phần:** Không ai ở trường biết lý do job tồn tại.
- **Ai hiểu sai:** Không có hiểu sai phi lý; mọi người coi đây là việc làm thêm bình thường.
- **Bằng chứng được tạo ra:** Đăng ký/nhận ca, tin nhắn hoặc record công việc.
- **Bằng chứng tồn tại ở đâu:** Điện thoại Bắc và hệ thống Tân Lộ.
- **Bằng chứng có thể biến mất lúc nào:** Record nhân sự vẫn tồn tại trong game window.
- **Event tiếp theo mà nó gây ra:** E22.

## E22 — Gói được phân cho Bắc và hoàn tất bàn giao

- **Thời điểm:** D0, 12:30–14:10.
- **Địa điểm:** Tân Lộ → một điểm nhận liên quan hoạt động y tế/hành chính; có tối thiểu 25 phút di chuyển.
- **Những người có mặt:** Bắc, nhân viên vận hành/đầu nhận hợp lệ. Tuấn không cần đi cùng.
- **Chuyện khách quan xảy ra:** Hệ thống thường phân job E19 cho Bắc. Cậu thực hiện như lao động part-time; gói đi qua tay cậu nhưng không tự nói ra bản chất tội phạm.
- **Nguyên nhân:** E19 + E21.
- **Hậu quả:** Một người ngoài lõi chạm luồng vốn không được phép chạm người ngoài.
- **Ai biết chuyện này:** Bắc biết mình làm một job có thể có vài chi tiết không khớp nếu để ý; dispatch biết job hoàn tất.
- **Ai chỉ biết một phần:** Tuấn biết job thuộc nhóm y tế/ưu tiên ở mức công việc.
- **Ai hiểu sai:** Người vận hành bình thường coi classification là hợp lệ.
- **Bằng chứng được tạo ra:** Assignment log, timestamps, proof-of-handover, route metadata; quan sát của Bắc về nhãn/đầu mối nếu cậu ghi nhớ.
- **Bằng chứng tồn tại ở đâu:** Tân Lộ, đầu nhận, thiết bị công việc/Bắc.
- **Bằng chứng có thể biến mất lúc nào:** Gói vật lý có thể bị thu hồi trước cuối D0; dispatch metadata không thể xóa sạch mà không tạo gap.
- **Event tiếp theo mà nó gây ra:** E23.

## E23 — Khải phát hiện sai luồng; Hùng bị chất vấn

- **Thời điểm:** D0, 14:30–16:00.
- **Địa điểm:** Tân Lộ/kênh quản trị.
- **Những người có mặt:** Khải, Hùng; Tuấn bị hỏi về vận hành.
- **Chuyện khách quan xảy ra:** Khải đối chiếu cleanup và thấy luồng nhạy cảm đã đi qua pool thường. Hùng giảm nhẹ lý do.
- **Nguyên nhân:** Audit hậu quả E22.
- **Hậu quả:** Khải xác định có exposure ngoài dự kiến và tra lại người thực hiện.
- **Ai biết chuyện này:** Khải biết breach; Hùng biết breach do mình gây.
- **Ai chỉ biết một phần:** Tuấn chỉ biết một job đang bị rà.
- **Ai hiểu sai:** Khải chưa biết Bắc hiểu gì và không mặc định cậu là threat.
- **Bằng chứng được tạo ra:** Internal review về job và câu trả lời không đầy đủ của Hùng.
- **Bằng chứng tồn tại ở đâu:** Risk/internal logs.
- **Bằng chứng có thể biến mất lúc nào:** Có thể bị dọn sau crisis, nhưng không trước khi Nam nhận báo cáo.
- **Event tiếp theo mà nó gây ra:** E24.

## E24 — Nam nhận ra worker chính là Bắc

- **Thời điểm:** D0, 16:00–17:00.
- **Địa điểm:** Nam nhận báo cáo qua Khải; Bắc không có mặt.
- **Những người có mặt:** Nam, Khải.
- **Chuyện khách quan xảy ra:** Thông tin worker được tra lại; Nam nhận ra đó là sinh viên mới ở cùng dãy trọ.
- **Nguyên nhân:** E23.
- **Hậu quả:** Nam chuyển knowledge Bắc từ N0 sang N1: accidental exposure hành chính.
- **Ai biết chuyện này:** Nam, Khải; Hùng biết worker đã được tra.
- **Ai chỉ biết một phần:** Tuấn biết Bắc là worker nhưng không biết Nam.
- **Ai hiểu sai:** Chưa ai có cơ sở kết luận Bắc đang điều tra.
- **Bằng chứng được tạo ra:** Liên kết tên Bắc với assignment E22.
- **Bằng chứng tồn tại ở đâu:** Tân Lộ.
- **Bằng chứng có thể biến mất lúc nào:** Có thể bị hạn chế truy cập sau D0; nguồn gốc assignment vẫn có trace.
- **Event tiếp theo mà nó gây ra:** E25.

## E25 — Nam chọn quan sát thay vì xử lý mạnh

- **Thời điểm:** D0, 17:30–19:00.
- **Địa điểm:** Dãy trọ và kênh Khải–Nam.
- **Những người có mặt:** Nam; Bắc có thể gặp Nam đời thường; Khải ở nơi khác.
- **Chuyện khách quan xảy ra:** Nam quyết định không biến accidental exposure thành một vụ việc lớn. Nếu gặp Bắc, ông vẫn cư xử như hàng xóm bình thường.
- **Nguyên nhân:** Bắc chưa có hành vi chứng minh cậu hiểu giá trị của job; hành động mạnh sẽ tự tạo thêm rủi ro.
- **Hậu quả:** Network theo dõi hậu quả thay vì nhắm trực tiếp Bắc.
- **Ai biết chuyện này:** Nam/Khải biết Bắc là N1.
- **Ai chỉ biết một phần:** Bắc không biết Nam có thông tin này.
- **Ai hiểu sai:** Bắc có thể tiếp tục coi Nam hoàn toàn không liên quan; điều đó vẫn hợp logic.
- **Bằng chứng được tạo ra:** Chỉ có decision/risk note nếu Khải ghi; không phải clue quyết định.
- **Bằng chứng tồn tại ở đâu:** Risk management.
- **Bằng chứng có thể biến mất lúc nào:** Có thể bị dọn sau crisis.
- **Event tiếp theo:** E26/E29 chỉ nếu actual disclosure/contact; E27→E33 và E28→E34 là independent investigation/source lines, không do E25/player curiosity. Nếu không điều tra, baseline E31 vẫn tới.

## E26 — Minh có thể làm lộ mức tò mò của Bắc

- **Thời điểm:** D0, 19:30–21:00, chỉ nếu Bắc hỏi Minh/nhờ Minh kiểm tra.
- **Địa điểm:** Liên lạc từ trường/khu trọ tới Tân Lộ.
- **Những người có mặt:** Minh; Tuấn hoặc đầu mối nhân sự nhận thông tin.
- **Chuyện khách quan xảy ra:** Minh, vì sợ mất việc và muốn dập rắc rối, kể lại rằng Bắc đang hỏi gì; cậu không biết thông tin có thể leo lên tầng Hùng/Khải.
- **Nguyên nhân:** Player intervention + flaw né trách nhiệm của Minh.
- **Hậu quả:** Curiosity của Bắc có thể trở thành observable signal cho organization; Minh sau đó giảm nhẹ việc mình đã nói.
- **Ai biết chuyện này:** Minh và người nhận biết nội dung đã trao đổi.
- **Ai chỉ biết một phần:** Minh không biết network; Tuấn không biết core crime.
- **Ai hiểu sai:** Minh tin đây là vấn đề nhân sự/công ty.
- **Bằng chứng được tạo ra:** Tin nhắn/cuộc gọi bình thường.
- **Bằng chứng tồn tại ở đâu:** Thiết bị/tài khoản liên lạc.
- **Bằng chứng có thể biến mất lúc nào:** Có thể bị người dùng xóa; không phải evidence lõi của vụ organ network.
- **Event tiếp theo mà nó gây ra:** E29 nếu được escalated.

## E27 — Huyền giữ review mở; Khoa cố thu hẹp

- **Thời điểm:** D0, 19:00–20:30.
- **Địa điểm:** Minh Trạch.
- **Những người có mặt:** Huyền, Khoa; Thảo ở phạm vi công việc.
- **Chuyện khách quan xảy ra:** Huyền không chấp nhận một giải thích đơn giản cho toàn pattern. Khoa chỉnh scope theo hướng hẹp hơn nhưng không thể xóa việc review đã từng tồn tại.
- **Nguyên nhân:** Huyền làm đúng quy trình; Khoa tự bảo vệ.
- **Hậu quả:** Một cửa sổ evidence vẫn mở sang D+1.
- **Ai biết chuyện này:** Huyền biết review chưa được giải thích; Khoa biết nguy cơ; Thảo biết vùng hồ sơ nhạy cảm bị soi.
- **Ai chỉ biết một phần:** Nam vẫn chỉ biết bản giảm nhẹ qua Khoa/Khải.
- **Ai hiểu sai:** Huyền chưa gọi đây là conspiracy.
- **Bằng chứng được tạo ra:** Version chênh lệch của review, comments/approval trail, case flags.
- **Bằng chứng tồn tại ở đâu:** Compliance system Minh Trạch.
- **Bằng chứng có thể biến mất lúc nào:** Quyền truy cập có thể bị thu hẹp D+1; audit trail nền vẫn còn.
- **Event tiếp theo mà nó gây ra:** E33 hospital/source window; không E32 logistics.

## E28 — Vũ hoàn tất A độc lập với Bắc

- **Thời điểm:** D0, 20:00–21:30.
- **Địa điểm:** Cơ quan cảnh sát/qua kênh intake nghiệp vụ riêng.
- **Những người có mặt:** Vũ, Phúc; broker counterpart cung cấp original riêng, không cần cùng phòng.
- **Chuyện khách quan xảy ra:** Phúc bổ sung exact original core-agreement/withdrawal messages từng giấu vì xấu hổ. Vũ liên hệ riêng broker counterpart đã được chỉ từ E12, thu original gửi/nhận: promise tiền gắn cung cấp nội tạng/cách gọi hiến tự nguyện; agreement/withdrawal của Phúc; pressure viện tiền đã ứng. Broker giữ thread để không gánh hết quyết định Hạnh, giao bounded case exchange để phân định trách nhiệm, không được hứa miễn trách nhiệm; việc cung cấp qua kênh riêng không tự báo Hạnh.
- **Nguyên nhân:** Investigation E12 vẫn tiến độc lập; Phúc kể rõ hơn, counterpart tự bảo vệ bằng đúng original mình giữ.
- **Hậu quả:** Vũ so exact content từng fact từ hai phía và ghi authentication C10; independent hospital response xác nhận visit/request D−14, endpoint/timestamps xác nhận exchange/order. Hospital/metadata không authenticate money/pressure text thay counterpart originals. CASE.A=2 từ E28 trước S09, không chờ Bắc giao lại chronology.
- **Ai biết chuyện này:** Vũ/police biết và giữ paid-organ agreement → withdrawal → pressure đã authenticate; Phúc/counterpart chỉ biết case/phần mình.
- **Ai chỉ biết một phần:** Vũ chưa có multi-case review group/Tân Lộ bridge, common current risk context X hoặc Nam D. A_PLAYER_SEEN/A_PLAYER_UNDERSTOOD của Bắc chưa tự tăng.
- **Ai hiểu sai:** Nhánh môi giới nhỏ còn là giả thuyết giới hạn; đã có A không tự biết architecture.
- **Bằng chứng được tạo ra:** C08 originals bổ sung, C10 record so exact content từng fact, hospital-request confirmation và receipt/authentication từng source; copy của một lời khai không được đếm là origin độc lập.
- **Bằng chứng tồn tại ở đâu:** Originals ở hai custodians; authenticated copies/chronology ở police ngoài quyền xóa network. C10_SOURCE_LINK là future actual intake S16 sau E38, chưa được tạo/nhận tại E28.
- **Bằng chứng có thể biến mất lúc nào:** Police records không mất trong run và không lùi vì Bắc miss encounter. T07 partial-subset fixture chỉ đặt trước E28, ghi đúng record/fact chưa được nhận.
- **Event tiếp theo:** E34 police comparison khi có new sourced group bridge; không E33 hospital source. E28 custody độc lập với bridge; baseline E31 vẫn tiến.

## E29 — Bắc có thể chuyển N1 → N2

- **Thời điểm:** D0 tối20:20–23:00, chỉ từ authored contacts/disclosures và actual reports; private reading0.
- **Địa điểm:** Tùy hành động; không đòi hỏi Nam/Khải ở cùng Bắc.
- **Những người có mặt:** Bắc và nguồn cậu tiếp cận; Khải chỉ nhận hậu quả/báo cáo.
- **Chuyện khách quan xảy ra:** Bắc làm nhiều hơn phản ứng bình thường của một worker: hỏi sâu, giữ/so dữ kiện hoặc xuất hiện quanh một nguồn thứ hai.
- **Nguyên nhân:** Player intervention.
- **Hậu quả:** Chỉ khi một nguồn thực sự gửi report và Khải nhận được exact hành vi/payload, có cơ sở phân loại PROBING. Giữ/so dữ kiện kín trong notebook không tự nâng BARC; hiểu đúng hay sai riêng không thay report.
- **Ai biết chuyện này:** Bắc biết phần mình đã quan sát/suy; Khải chỉ biết exact reports đã nhận. Nam chỉ nhận phần Khải thực sự báo, với thời điểm nhận riêng.
- **Ai chỉ biết một phần:** Nam chỉ biết điều Khải có thể báo, không biết suy nghĩ Bắc.
- **Ai hiểu sai:** Khải chưa biết Bắc đã hiểu đúng tới đâu.
- **Bằng chứng được tạo ra:** Report ledger người gửi, recipient, received_at và payload Bắc thực sự disclose/hành vi được witness. Không tự sinh report từ notebook; không một dấu riêng đủ kết luận cross-cell.
- **Bằng chứng tồn tại ở đâu:** Nguồn tương ứng.
- **Bằng chứng có thể biến mất lúc nào:** Một số log ngắn hạn; trong game window còn tồn tại.
- **Event tiếp theo mà nó gây ra:** E30.

## E30 — Nam bắt đầu nghi Bắc đang can thiệp

- **Thời điểm:** D0, khoảng 23:00, chỉ nếu E29 xảy ra và để lại dấu.
- **Địa điểm:** Kênh Nam–Khải.
- **Những người có mặt:** Nam, Khải.
- **Chuyện khách quan xảy ra:** Khải báo Bắc đã làm nhiều hơn một nhân viên bình thường. Nam tăng mức chú ý nhưng chưa coi cậu là threat nghiêm trọng nếu mới chạm một nhánh.
- **Nguyên nhân:** Observable consequences của E29.
- **Hậu quả:** Nam chuyển từ N1 sang N2 knowledge; thiện cảm đời thường bắt đầu xung đột với duty bảo vệ system.
- **Ai biết chuyện này:** Nam biết Bắc tò mò có chủ đích.
- **Ai chỉ biết một phần:** Nam chưa biết Bắc có gì trong đầu hoặc chưa chia cho ai.
- **Ai hiểu sai:** Không được phép để Nam 'đọc' notebook hay suy nghĩ của Bắc.
- **Bằng chứng được tạo ra:** Thay đổi lệnh risk-management nếu có.
- **Bằng chứng tồn tại ở đâu:** Phía Khải/manager nhận lệnh.
- **Bằng chứng có thể biến mất lúc nào:** Có thể bị cleanup; hậu quả operational vẫn có thể được suy ra.
- **Event tiếp theo mà nó gây ra:** E31.


---

# 4. OBJECTIVE TIMELINE — D+1 VÀ CÁC ENDING STATE

## E31 — Ba hệ thống tiếp tục tự vận động

- **Thời điểm:** D+1, 08:00–09:30.
- **Địa điểm:** Song song tại Tân Lộ, Minh Trạch và cơ quan cảnh sát.
- **Những người có mặt:** Tân Lộ: Khải/Hùng/Tuấn/Đức/Yến. Minh Trạch: Khoa/Huyền/Thảo. Cảnh sát: Vũ/Phúc.
- **Chuyện khách quan xảy ra:** Tân Lộ tiếp tục cleanup; Huyền tiếp tục giữ vấn đề chưa giải thích; Vũ tiếp tục vụ Phúc. Không tuyến nào cần Bắc để tồn tại.
- **Nguyên nhân:** Khủng hoảng đã bắt đầu trước D0.
- **Hậu quả:** Các cửa sổ evidence vẫn mở nhưng đang hẹp dần.
- **Ai biết chuyện này:** Mỗi nhánh biết phần riêng.
- **Ai chỉ biết một phần:** Ngay cả Nam/Khải vẫn làm việc với báo cáo bị manager lọc.
- **Ai hiểu sai:** Tuấn không biết core crime; Huyền chưa biết Tân Lộ; Vũ chưa có cầu logistics.
- **Bằng chứng được tạo ra:** Thêm audit/cleanup records.
- **Bằng chứng tồn tại ở đâu:** Từng institution.
- **Bằng chứng có thể biến mất lúc nào:** Một số evidence vật lý/quyền truy cập có thể bị thu hồi trong D+1; institutional records tồn tại lâu hơn.
- **Event tiếp theo mà nó gây ra:** E32–E35 hoặc baseline B01.

## E32 — Cửa sổ Đức

- **Thời điểm:** D+1, 09:30–11:00 timely willingness; offer/request S08 sáng, actual receipt09:45 hoặc police10:35 theo §0.1.
- **Địa điểm:** Tân Lộ hoặc điểm gặp hợp lý nếu có contact; không yêu cầu Khải xuất hiện trực tiếp.
- **Những người có mặt:** Đức; Bắc/Vũ chỉ nếu có route tiếp cận.
- **Chuyện khách quan xảy ra:** Đức tự bảo vệ bằng bounded private export từ E17. S08 notice09:25 và contact từ09:30 đặt actual offer trước last willingness11:00. Bắc có thể nhận copy/testimony09:35–09:45, hoặc share contact/copy/deadline ở S09 để Vũ tự collect10:25/receive10:35. Không chờ S12/S13 mới tới nguồn đã đóng.
- **Nguyên nhân:** E17–E18.
- **Hậu quả:** Logistics có thể trở thành nguồn corroboration độc lập; nếu không, Đức bị tước dần quyền truy cập.
- **Ai biết chuyện này:** Đức biết phần logistics và nghi liên hệ y tế.
- **Ai chỉ biết một phần:** Đức không biết Nam/cấu trúc bệnh viện.
- **Ai hiểu sai:** Đức có thể vẫn nghĩ Hùng là đỉnh.
- **Bằng chứng được tạo ra:** Testimony giới hạn và receipt của private copy C18 vốn có; authentication so originals/fields vận hành riêng, không coi một screenshot là proof tự xác thực.
- **Bằng chứng tồn tại ở đâu:** Phía Đức; nếu chuyển hợp pháp thì sang Vũ.
- **Bằng chứng có thể mất timely access lúc nào:** Willingness/contact11:00 sau required notice09:25 và actual saving options §0.1. Work account revocation11:00 là access riêng, không xóa phone export. Received copy giữ receipt/provenance và verify later; không police custody từ queue, không despawn vì badge. Local closure này không CLEANUP=LOCKED.
- **Event tiếp theo mà nó gây ra:** E36.

## E33 — Cửa sổ Huyền/Thảo

- **Thời điểm:** D+1, 09:30–11:30.
- **Địa điểm:** Minh Trạch.
- **Những người có mặt:** Huyền, Thảo; Khoa trong cùng institution nhưng không cần cùng phòng.
- **Chuyện khách quan xảy ra:** Huyền có thể xác nhận pattern review nếu có lý do hợp lệ; Thảo có thể tiếp tục tự bảo vệ hoặc thừa nhận một phần rằng đây không chỉ là lỗi hành chính.
- **Nguyên nhân:** E13/E27 và áp lực đạo đức của Thảo.
- **Hậu quả:** Bệnh viện có thể trở thành nguồn độc lập B; nếu không, Khoa tạm thu hẹp review.
- **Ai biết chuyện này:** Huyền biết pattern; Thảo biết phần phi pháp; Khoa biết cả hai là risk.
- **Ai chỉ biết một phần:** Không nguồn nào ở đây tự chứng minh Nam.
- **Ai hiểu sai:** Huyền vẫn không thể tự suy ra command structure.
- **Bằng chứng được tạo ra:** Review trail + giải thích chuyên môn + nếu Thảo hợp tác, corroboration về khác biệt giữa hồ sơ và hoàn cảnh.
- **Bằng chứng tồn tại ở đâu:** Minh Trạch; nếu được cung cấp hợp pháp thì hồ sơ điều tra.
- **Bằng chứng có thể mất timely access lúc nào:** Hospital/Thảo channel11:30, cảnh báo10:15 và tại entrance10:50/10:55. Actual group query10:15→C11/C12 originals received11:10; Thảo alternative10m còn receipt11:20/11:25. Local scope closure không xóa received originals/history và không global lock.
- **Event tiếp theo mà nó gây ra:** E36.

## E34 — Cửa sổ Phúc/Vũ

- **Thời điểm:** D+1, 10:00–12:00.
- **Địa điểm:** Tuyến cảnh sát.
- **Những người có mặt:** Vũ, Phúc; Bắc chỉ nếu chủ động liên hệ.
- **Chuyện khách quan xảy ra:** Vũ đã có A=2 từ E28. Nếu Bắc mang sourced logistics/group bridge, anh so với A đang giữ và mở targeted review-group verification; không yêu cầu chronology thuộc police được giao lại. Suy đoán không nguồn không mở proof mới.
- **Nguyên nhân:** Hồ sơ Phúc cần một bridge ngoài nhánh môi giới.
- **Hậu quả:** Một chi tiết logistics/bệnh viện có thể chuyển từ coincidence thành corroboration.
- **Ai biết chuyện này:** Vũ chỉ nâng knowledge theo evidence xác minh được.
- **Ai chỉ biết một phần:** Phúc vẫn không biết Tân Lộ/Nam và không được dùng như nguồn cho các facts đó.
- **Ai hiểu sai:** Nếu Bắc quy kết Tuấn/Huyền chỉ vì chức vụ, Vũ không coi đó là fact.
- **Bằng chứng được tạo ra:** Actual S09 sourced payload received10:15 và request ledger. Một source đã đủ contact/copy/deadline khiến Vũ chủ động collection; C18 actual police receipt10:35, C19 actual receipt10:50 nếu bounded finance lead thật shared. New-address action5m chỉ khi thông tin ấy chưa có, không re-delivery checkbox. A từ E28 giữ nguyên.
- **Bằng chứng tồn tại ở đâu:** Hồ sơ điều tra.
- **Bằng chứng có thể biến mất lúc nào:** Sau khi tiếp nhận chính thức, organization không thể xóa.
- **Event tiếp theo mà nó gây ra:** E36/E38.

## E35 — Cửa sổ Yến

- **Thời điểm:** D+1, 10:30–12:30.
- **Địa điểm:** Tân Lộ.
- **Những người có mặt:** Yến; Hùng trong cùng company; Bắc không mặc định gặp Yến.
- **Chuyện khách quan xảy ra:** Actual bounded finance lead trong S09 mở professional request, collector contact10:40 sau opening10:30, finance record received10:50. Yến xác nhận đúng nhóm đối soát để không gánh hết trách nhiệm Hùng; không giải nhánh Phúc/Nam. Queue chưa là receipt; S13 chỉ verify/match copy đã nhận với C22.
- **Nguyên nhân:** E17 và nỗi sợ trách nhiệm.
- **Hậu quả:** Có thể tạo corroboration tài chính, nhưng không giải nguồn người, bệnh viện hay Nam.
- **Ai biết chuyện này:** Yến biết số liệu bất thường.
- **Ai chỉ biết một phần:** Đức/Tuấn không biết mức Yến đã suy ra.
- **Ai hiểu sai:** Yến từng tin im lặng giúp đứng ngoài trách nhiệm.
- **Bằng chứng được tạo ra:** Đối chiếu/records tài chính vốn đã tồn tại; lời xác nhận nếu hợp tác.
- **Bằng chứng tồn tại ở đâu:** Tân Lộ; sau đó hồ sơ điều tra nếu được thu thập.
- **Bằng chứng có thể mất timely access lúc nào:** Yến access/cooperation12:30, notice09:25 và S09 source acknowledgment trước departure. Saving action là disclose bounded source/group/contact để10:50 receipt; C18 đã receipt là alternative C thật. Received finance copy và institution originals không biến mất khi account khóa. Không global lock12:30.
- **Event tiếp theo mà nó gây ra:** E38.

## E36 — N3_UNDERSTANDING của Bắc: nối đúng facts và current risk context

- **Thời điểm:** D+1, khoảng 12:00–14:00, chỉ nếu player có đủ nguồn độc lập.
- **Địa điểm:** Event knowledge; không bắt buộc là một cuộc gặp.
- **Những người có mặt:** Bắc; dữ kiện đến từ các nguồn đã gặp ở thời điểm khác nhau.
- **Chuyện khách quan xảy ra:** Nếu Bắc đã quan sát đủ content A/B/C và thực hiện inference đúng, cậu nhận ra quan hệ nhiều nhánh; C24/C25 phải cung cấp actual Khải endpoint, scope request/response và crisis context để cậu nối current shared risk role, không chỉ same account/giao dịch. Thiếu/sai inference giữ hypothesis, không award N3_UNDERSTANDING/KHẢI_LAYER.
- **Nguyên nhân:** Facts observed từ các nguồn độc lập, cộng successful explicit inference X_PLAYER_CONNECTED về current risk context. C03/C17 transaction/group match là lead, không thay risk context hay current command.
- **Hậu quả:** N3_UNDERSTANDING chỉ phản ánh Bắc. BARC không đổi tại event inference; E37 derive threat từ reports đã nhận, kể cả khi private theory sai. Vũ verify đủ raw risk sources trong custody dù inference Bắc sai; X_VERIFIED riêng.
- **Ai biết chuyện này:** Bắc biết cấu trúc nhiều nhánh ở mức chưa hoàn chỉnh.
- **Ai chỉ biết một phần:** Vũ biết custody/xác minh độc lập từ E12/E28 và các source đã tiếp nhận, kể cả phần Bắc chưa quan sát; private inference của Bắc không tự tới police. Nam/Khải chỉ biết exact reports đã nhận, với receipt riêng.
- **Ai hiểu sai:** Bắc vẫn có thể nghi Hùng/Tuấn là đỉnh vì chưa chứng minh Nam.
- **Bằng chứng được tạo ra:** Không có evidence mới chỉ vì suy luận; evidence gốc vẫn nằm ở các nguồn độc lập.
- **Bằng chứng tồn tại ở đâu:** Notebook của Bắc chỉ là bản tổng hợp; source evidence ở Tân Lộ/Minh Trạch/Phúc/police.
- **Bằng chứng có thể biến mất lúc nào:** Suy luận không thể bị xóa khỏi đầu Bắc; từng source có cửa sổ riêng.
- **Event tiếp theo:** E37 có thể xảy ra từ actual contact/disclosure reports dù inference E36 sai; E38 từ đủ raw source intake/authentication, không phải private certainty.

## E37 — Khải xác nhận Bắc đang can thiệp

- **Thời điểm:** D+1, khoảng 13:00–15:00, nếu received reports từ ít nhất hai nhánh có cùng Bắc và hành vi chạm/nối nguồn; không yêu cầu private N3_UNDERSTANDING đúng.
- **Địa điểm:** Kênh risk management.
- **Những người có mặt:** Khải; các manager thực sự gửi từng mảnh; Nam chỉ tham gia knowledge event nếu actual report được forward tới ông.
- **Chuyện khách quan xảy ra:** Khải so actual reports từ Tân Lộ và ít nhất một nhánh khác: cùng Bắc, exact hành vi/contact và scope/payload được witness. Ledger có sender/recipient/received_at; chỉ appearance tình cờ không đủ. Report chứng minh cross-cell probing cho BARC N3, không chứng minh đọc được inference. Nam chỉ tăng knowledge sau khi nhận nội dung Khải báo; cùng received reports luôn cùng awareness dù private theory khác.
- **Nguyên nhân:** Actual reports về authored contacts/disclosures Bắc đã thực hiện ở các cell, có payload/recipient/received_at; độc lập với thành công hay thất bại của private inference E36.
- **Hậu quả:** Khải tăng awareness từ reports đã nhận. Nam chỉ chuyển sang trực tiếp quan tâm Bắc sau actual forwarding/receipt đủ scope; strategy dựa thông tin evidence đã rời Bắc mà họ thực sự nhận.
- **Ai biết chuyện này:** Khải biết report chứng minh cross-cell probing; Nam chỉ biết exact scope nhận từ Khải, không tự thừa hưởng toàn ledger.
- **Ai chỉ biết một phần:** Họ không biết nguồn nào Bắc chưa chia sẻ.
- **Ai hiểu sai:** Khải có thể đánh giá thiếu các nguồn ngoài organization như Huyền/Vũ.
- **Bằng chứng được tạo ra:** Cross-report nội bộ về Bắc.
- **Bằng chứng tồn tại ở đâu:** Risk management.
- **Bằng chứng có thể biến mất lúc nào:** Có thể bị dọn trong cleanup; không phải evidence cần để kết tội network.
- **Event tiếp theo mà nó gây ra:** E38–E42.

## E38 — Ngưỡng police corroboration

- **Thời điểm:** D+1 baseline actual E38=14:55 nếu B/C required raw sources đã authenticate; late run dùng actual t0, không scene-completion hoặc private-inference grant.
- **Địa điểm:** Cơ quan điều tra và các nguồn xác minh.
- **Những người có mặt:** Vũ; tùy route có Phúc, Huyền, Đức/Yến/Thảo hoặc record chính thức.
- **Chuyện khách quan xảy ra:** Vũ giữ A từ E28; khi đủ sourced B/C corroboration, anh mở điều tra nhiều institution và chủ động bảo toàn các nguồn còn thiếu. X_VERIFIED chỉ khi actual current risk/escalation sources Khải endpoint + request/response scope + crisis context đã intake/authenticate, ngoài relation giao dịch ABC. Nếu raw context đủ, Vũ tự verify dù teen inference sai; nếu context chưa nhận, ABC có thể PRESERVED/X=false mà Vũ vẫn xử lý các case đã rõ.
- **Nguyên nhân:** Evidence có nguồn, không phải kết luận của Bắc.
- **Hậu quả:** Police knowledge tăng nhanh; network mất khả năng xóa sạch các dấu đã được bảo toàn.
- **Ai biết chuyện này:** Vũ và đội điều tra biết giả thuyết mạng lưới đã có cơ sở.
- **Ai chỉ biết một phần:** Có thể vẫn chưa đủ proposition D để chứng minh Nam.
- **Ai hiểu sai:** Sau khi A+B+C đã corroborate, không còn hợp lý để Vũ coi đây chỉ là một môi giới nhỏ.
- **Bằng chứng được tạo ra:** Actual threshold/authentication record và proactive professional requests. §0.2 khóa manager requestt0+5m/receipt+25m, other-branch request+10m/receipt+40m hoặc+45m, source-annex request+15m/receipt+55m, full verification+75m. Không chờ Bắc xin lại khi sourced contacts/context đã trong custody.
- **Bằng chứng tồn tại ở đâu:** Cơ quan điều tra và institutions.
- **Bằng chứng có thể biến mất lúc nào:** Sau khi được bảo toàn chính thức, organization không thể đơn giản xóa.
- **Event tiếp theo mà nó gây ra:** E39–E42.

## E39 — TRUE ROUTE: command structure bị chứng minh đủ sớm

- **Thời điểm:** D+1, khoảng 16:00–20:00; hậu quả pháp lý tiếp tục D+2 trở đi.
- **Địa điểm:** Nhiều điểm; cảnh sát điều phối, không phải Bắc tự 'đột kích'.
- **Những người có mặt:** Vũ và lực lượng phù hợp; các nguồn corroboration; Nam/Khải/Hùng/Khoa/Hạnh bị tác động theo evidence.
- **Chuyện khách quan xảy ra:** Nếu A+B+C/X đã bảo toàn và accepted C32H+C33_AUTH hoặc C32K+C34_AUTH trên hai current decisions L/H khác nhau, cộng matching C10_SOURCE_LINK đã received/authenticate trước global deadline, cảnh sát đủ proof scope phần lõi. Bare relations/contact metadata không đủ; Nam không thể chỉ hy sinh manager.
- **Nguyên nhân:** Bắc tạo bridge đúng lúc + Vũ chuyển bridge đó thành evidence có thể xác minh + organization chưa cleanup xong.
- **Hậu quả:** Mạng chính bị phá ở mức đủ thỏa mãn; Bắc sống; phần lớn sự thật được làm rõ. Một số mắt xích/chi tiết ngoài phạm vi vẫn có thể chưa hoàn toàn khép.
- **Ai biết chuyện này:** Vũ biết đủ cấu trúc để hành động; Bắc hiểu phần lớn nhưng không biết mọi chi tiết nghiệp vụ.
- **Ai chỉ biết một phần:** Public/nhân viên vô tội chỉ biết phần được công bố.
- **Ai hiểu sai:** Không ai cần 'villain confession' để giải vụ.
- **Bằng chứng được tạo ra:** Chuỗi corroboration A+B+C+D, không một file đơn lẻ.
- **Bằng chứng tồn tại ở đâu:** Hồ sơ điều tra, Tân Lộ, Minh Trạch, lời khai các nguồn.
- **Bằng chứng có thể biến mất lúc nào:** Sau preservation, không còn cửa sổ xóa thực tế trong narrative.
- **Event tiếp theo mà nó gây ra:** E43.

## E40 — CLEANUP ROUTE: police có A/B/C nhưng quá muộn với lõi

- **Thời điểm:** D+1 global E40 baseline17:00; accelerated deadline=max(16:30, actual warning W+145m) chỉ nếu sớm hơn17:00. Các local closures11:00/11:30/12:30 không E40.
- **Địa điểm:** Tân Lộ, Minh Trạch và các kênh quản trị.
- **Những người có mặt:** Nam, Khải, các manager; Vũ ở tuyến điều tra.
- **Chuyện khách quan xảy ra:** Baseline crisis đóng timely command channels17:00 dù private Bắc chưa hiểu. Actual received reports có thể làm Khải/Nam advance deadline theo warning rule §0.1; fresh notice phải tới Bắc/Vũ trước close và còn saving action40m intake/authentication đủ E38+75m D collection/authentication. Actual longer remainder phải qua feasibility check §0.1, nếu không giữ baseline17:00; receipt/queue không trigger E38. Không retroactive closure vì leak/private theory. Cảnh sát vẫn giữ/xử lý evidence đã nhận; chỉ phần D còn thiếu bị lỡ finite run window.
- **Nguyên nhân:** Early exposure hoặc chậm chuyển evidence sang Vũ.
- **Hậu quả:** Một số người có tội bị xử lý; network mất phần lớn hoạt động hiện tại nhưng Nam/Khải có thể tránh bị buộc vào toàn cấu trúc. Đây là Bad Ending — Cleanup/Partial.
- **Ai biết chuyện này:** Nam/Khải biết đúng scope actual received reports; Vũ/Bắc nhận deadline warning. Nếu D đã preserve16:10, access lock17:00 hoặc16:30 không hạ proof; thiếu D phải nêu actual receipt/auth chưa hoàn tất.
- **Ai chỉ biết một phần:** Bắc có thể hiểu đúng hơn những gì hồ sơ pháp lý kịp chứng minh.
- **Ai hiểu sai:** Không dùng cảnh sát 'không tin'; vấn đề là preservation/timing.
- **Bằng chứng được tạo ra:** A/B/C đủ mạnh; D còn suy đoán hoặc chain chưa bảo toàn.
- **Bằng chứng tồn tại ở đâu:** Cảnh sát + nguồn cũ.
- **Bằng chứng có thể biến mất lúc nào:** Một số source command/contacts mất giá trị khi quyền truy cập bị khóa và các manager cắt liên hệ.
- **Event tiếp theo mà nó gây ra:** E44.

## E41 — DELAY / MISSED EVIDENCE ROUTE

- **Thời điểm:** D+1 chiều–tối, sau local last-required-path closure có warning; không tự global lock.
- **Địa điểm:** Các institution.
- **Những người có mặt:** Vũ, Bắc và những nguồn còn mở.
- **Chuyện khách quan xảy ra:** Nếu Bắc bỏ lỡ Đức/Huyền hoặc tới sau khi quyền truy cập bị thu hẹp, police chỉ có một hoặc hai hộp sự thật. Vụ Phúc vẫn tiến nhưng không mở được cấu trúc đủ rộng trong game window.
- **Nguyên nhân:** Missable evidence và timing consequence.
- **Hậu quả:** A hoặc A+B được chứng minh; Tân Lộ/boss chưa bị nối chắc. Đây là Bad Ending — Delay/Missed Evidence.
- **Ai biết chuyện này:** Vũ biết phần đã chứng minh; không nhảy qua khoảng trống bằng suy đoán.
- **Ai chỉ biết một phần:** Bắc có thể nghi đúng nhưng không có nguồn đủ mạnh.
- **Ai hiểu sai:** Không biến thiếu evidence thành police incompetence.
- **Bằng chứng được tạo ra:** Những nguồn còn lại.
- **Bằng chứng tồn tại ở đâu:** Cảnh sát/Minh Trạch/Phúc.
- **Bằng chứng có thể biến mất lúc nào:** Các cửa sổ Đức/access review đóng trong D+1; institutional history vẫn có thể được điều tra lâu dài sau ending.
- **Event tiếp theo mà nó gây ra:** E44.

## E42 — WRONG TRUST / EXPOSURE ROUTE

- **Thời điểm:** D0 tối đến D+1 chiều, tùy thời điểm leak.
- **Địa điểm:** Kênh Minh→Tân Lộ và risk management.
- **Những người có mặt:** Minh, Tuấn/Hùng/Khải; Nam chỉ biết khi report đủ mạnh.
- **Chuyện khách quan xảy ra:** Nếu Bắc chia quá nhiều cho Minh hoặc một đầu mối không an toàn trước khi evidence được bảo toàn, organization biết sớm chính xác Bắc đang chạm những nhánh nào. Họ đẩy cleanup nhanh hơn và cô lập các source access. Nếu received reports đã đưa BARC tới N3/N4 và evidence còn chưa đủ được bảo toàn, cậu có thể bị đặt vào tình huống nguy hiểm và mất khả năng tiếp tục điều tra; private theory không tự truyền tới organization.
- **Nguyên nhân:** Player chia thông tin sai người + Minh ưu tiên người có quyền lực hơn khi sợ.
- **Hậu quả:** Có thể dẫn tới Bad Ending — Wrong Trust, Exposure hoặc Cleanup tùy police đã giữ được gì. Minh không phải villain và leak không tự động game-over.
- **Ai biết chuyện này:** Minh chỉ biết lời Bắc nói; Khải suy ra risk từ hậu quả; Nam chỉ nhận mức đã được báo.
- **Ai chỉ biết một phần:** Không ai được tự nhiên biết toàn notebook Bắc.
- **Ai hiểu sai:** Minh tin đang dập rắc rối công việc.
- **Bằng chứng được tạo ra:** Communication trail của leak; các source bị đóng access sau đó.
- **Bằng chứng tồn tại ở đâu:** Tân Lộ/thiết bị liên lạc.
- **Bằng chứng có thể biến mất lúc nào:** Tin nhắn có thể bị xóa nhưng hậu quả cleanup đã xảy ra.
- **Event tiếp theo mà nó gây ra:** E44.

## E43 — Hậu true ending

- **Thời điểm:** D+2 đến D+7; dư âm sau đó.
- **Địa điểm:** Cơ quan điều tra, Tân Lộ, Minh Trạch, khu trọ.
- **Những người có mặt:** Vũ; Bắc; nhân sự vô tội của hai institutions; các nghi can theo evidence.
- **Chuyện khách quan xảy ra:** Cảnh sát tiếp tục xử lý hồ sơ; Tân Lộ và Minh Trạch tách phần hợp pháp khỏi cá nhân bị điều tra. Bắc trở lại đời sống sinh viên nhưng không còn nhìn thế giới như trước.
- **Nguyên nhân:** E39.
- **Hậu quả:** Network chính không thể vận hành như trước. Ending vẫn để một chi tiết rất nhỏ chưa giải thích hoàn toàn, đúng canon dư âm bất an.
- **Ai biết chuyện này:** Knowledge được phân theo vai trò; không public hóa toàn bộ chi tiết.
- **Ai chỉ biết một phần:** Lan/Linh chỉ cần biết mức an toàn, không trở thành người biết toàn conspiracy.
- **Ai hiểu sai:** Không có reveal rằng Nam 'thật ra vô tội vì cấp dưới làm hết'.
- **Bằng chứng được tạo ra:** Hồ sơ đã bảo toàn.
- **Bằng chứng tồn tại ở đâu:** Cơ quan điều tra/institutions.
- **Bằng chứng có thể biến mất lúc nào:** Theo quy trình pháp lý, ngoài scope game.
- **Event tiếp theo mà nó gây ra:** Kết thúc run.

## E44 — Hậu bad/partial ending

- **Thời điểm:** D+2 đến vài tuần.
- **Địa điểm:** Hà Nội; từng institution.
- **Những người có mặt:** Tùy route: Nam/Khải và manager còn lại; Vũ; Phúc; Bắc.
- **Chuyện khách quan xảy ra:** Nếu core chưa bị chứng minh, Hành Lang co nhỏ. Một số người tầng thấp hoặc manager có thể bị xử lý vì tội thật; Nam giảm quy mô, thay người và chờ. Vũ tiếp tục điều tra nhưng game kết thúc trước khi có breakthrough mới.
- **Nguyên nhân:** E40/E41/E42.
- **Hậu quả:** Thế giới tiếp tục vận động; không reset vì player thất bại.
- **Ai biết chuyện này:** Vũ biết phần đã xác minh; Nam biết mức exposure thực tế sau cleanup.
- **Ai chỉ biết một phần:** Bắc có thể hiểu nhiều hơn mức hệ thống pháp lý kịp chứng minh.
- **Ai hiểu sai:** Không dùng coincidence để cho villain thoát; lõi sống vì proposition D chưa được bảo toàn đúng lúc.
- **Bằng chứng được tạo ra:** Những evidence đã vào hồ sơ vẫn còn; phần chưa bảo toàn có thể mất access/context.
- **Bằng chứng tồn tại ở đâu:** Cảnh sát và institutions.
- **Bằng chứng có thể biến mất lúc nào:** Một số nguồn operational mất trong vài ngày; hồ sơ chính thức vẫn còn.
- **Event tiếp theo mà nó gây ra:** Sau vài tuần network có thể hoạt động lại thận trọng hơn nếu chưa bị phá lõi.


---

# 5. EVIDENCE LIFECYCLE

| Evidence | Vì sao tồn tại | Ai kiểm soát ban đầu | Giá trị thật | Khi nào có thể mất/giảm giá trị | Vì sao organization chưa xóa sạch |
|---|---|---|---|---|---|
| Liên lạc Phúc–môi giới | cần để sắp case và vì Phúc giữ bản của mình | hai phía | chứng minh A ở mức nạn nhân/sức ép | phía môi giới có thể xóa; bản Phúc vẫn còn | organization không kiểm soát thiết bị Phúc và trước crisis không có lý do dọn mọi contact |
| Hồ sơ Phúc/C10 | E12 partial intake; E28 exact originals hai phía được so text/authenticate cùng independent visit record | police + originals Phúc/counterpart | A=2 từ E28; tách origin/verification/custody | police custody không mất nếu player chưa xem; annex C10_SOURCE_LINK chỉ tới S16 sau E38 | Hành Lang không kiểm soát police; không bắt Bắc giao lại A |
| Review Huyền | compliance mở review vì anomaly thật | Minh Trạch | chứng minh pattern B khi corroborate | access có thể bị Khoa thu hẹp | xóa thẳng review nhiều hồ sơ sẽ tạo anomaly và chạm nhiều người vô tội |
| Version/scope chênh lệch review | Khoa cố thu hẹp | Minh Trạch | cho thấy có can thiệp quản trị | khó đọc hơn khi access bị khóa | chính hành vi thu hẹp tạo lịch sử thay đổi |
| Dispatch/reclassification E19–E22 | job phải chạy qua hệ thống công ty | Tân Lộ | bridge C giữa việc Bắc chạm và thao tác quản lý | có thể bị hạn chế quyền xem; metadata vẫn có gap nếu sửa mạnh | Tân Lộ là công ty thật; xóa bừa phá hoạt động hợp pháp và tạo audit trail |
| Bản thông tin Đức giữ | private export vận hành từ E17 để tự bảo hiểm | điện thoại cá nhân Đức, không sync account Tân Lộ; police giữ copy nếu intake | corroboration logistics C, chỉ scope trực tiếp | willingness/contact/context có thể đóng; badge loss không xóa private copy; actual seizure cần discovery/quyền/custody event | Khải chưa biết copy gì/ở đâu; bản police không thu hồi được |
| Records tài chính Yến thấy | công ty thật phải hạch toán nhiều khoản | Tân Lộ | corroboration C, không đủ A/B/D | access của Yến có thể khóa | dữ liệu doanh nghiệp không thể xóa toàn bộ mà không làm công ty thật bất thường |
| Communication Minh→Tân Lộ | Minh tự báo vấn đề nhân sự | Minh/Tân Lộ | evidence về betrayal/exposure, không phải core crime | có thể bị xóa | không phải thứ network ưu tiên bảo toàn; hậu quả đã xảy ra |
| Cross-report về Bắc | Khải so báo cáo từ nhiều nhánh | risk management | cho biết network đã nhận diện threat | có thể dọn trong cleanup | không cần cho police conviction; chủ yếu giải thích phản ứng Nam |
| Evidence proposition D | phát sinh từ nhiều dấu command/quan hệ và lời khai/record độc lập | phân tán | nối Nam vào quyền command | nếu chưa bảo toàn, các contact/access có thể bị cắt | Nam cố ý không có một hồ sơ tự xưng boss; D phải được dựng bằng corroboration |

---

# 6. TIMELINE RIÊNG — BẮC

| Mốc | Bắc khách quan làm gì | Bắc biết gì | Rủi ro với organization |
|---|---|---|---|
| Trước D0 | chưa liên quan | không biết network | N0 |
| D0 07:30 | chuyển vào trọ, gặp Nam đời thường | Nam = hàng xóm lớn tuổi | N0 |
| D0 09:30 | tìm việc vì thiếu tiền | Tân Lộ = công ty logistics | N0 |
| D0 12:30–14:10 | làm job E22 | chỉ thấy một số chi tiết có thể không khớp | N1 sau khi audit phát hiện |
| D0 tối, nếu bỏ qua | quay về đời sống bình thường | không nối được gì | N1 → exposure thấp |
| D0 tối, nếu hỏi sâu | bắt đầu kiểm tra Tân Lộ/job | có một anomaly logistics | N2 nếu để lại dấu |
| D+1 sáng | có thể gặp nguồn thứ hai/ba | hypothesis theo facts đã thấy | BARC N2/N3 chỉ theo actual received reports, không theo hiểu riêng |
| D+1 trưa | facts đủ + successful inference current shared risk context | N3_UNDERSTANDING riêng | BARC N3 chỉ khi E37 report đủ; private route có thể giữ prior BARC |
| D+1 chiều | nếu chuyển evidence có nguồn cho Vũ | giúp police corroborate | N4 nếu organization nhận ra |
| True state | evidence rời khỏi tay Bắc và được preserve | hiểu phần lớn truth | organization không thể giải bằng cách chỉ chặn Bắc |
| Bad state | hiểu đúng nhưng giữ evidence rời rạc hoặc leak quá sớm | knowledge > legal proof | cleanup/exposure có thể thắng |

Bắc **không trở thành nguyên nhân của crisis**. Cậu chỉ trở thành nguyên nhân khiến ba hộp sự thật được nối đúng lúc.

---

# 7. TIMELINE RIÊNG — TÂN LỘ LOGISTICS

| Mốc | Trạng thái Tân Lộ | Người biết | Điều quan trọng |
|---|---|---|---|
| T−6/7 năm | công ty thật bắt đầu bị dùng cho số ít việc bí mật | Nam/Hùng | đa số nhân viên vô tội |
| T−1/2 năm | Hùng nới ngoại lệ để tăng trưởng | Hùng; Yến/Đức chỉ thấy dấu | nguồn lỗi tích lũy |
| D−7 | Khải audit nhóm y tế | Khải/Hùng; Tuấn biết audit | Hùng bắt đầu tự cứu |
| D−5 | Đức/Yến nghi xa hơn | Đức/Yến riêng rẽ | chưa ai biết toàn network |
| D−3 | leak anomaly bị phát hiện | Khải/Nam | Đức bị thu hẹp nghi vấn |
| D−1 | Hùng hạ gói xuống luồng thường | Hùng biết lý do; Tuấn không | trực tiếp tạo incident |
| D0 trưa | Bắc nhận job | dispatch/worker | hệ thống thật hoạt động như thiết kế |
| D0 chiều | Khải phát hiện breach | Khải/Hùng | Bắc mới là N1 |
| D+1 | access bị thu hẹp, cleanup tiếp tục | Khải/Hùng | evidence window Đức/Yến đóng dần |
| True | police bảo toàn records trước cleanup hoàn tất | Vũ + nguồn công ty | lớp hợp pháp được tách khỏi manager phạm tội |
| Baseline/Bad | công ty hợp pháp vẫn chạy | nhân viên bình thường | Nam không đóng cả công ty chỉ để che một nhánh nhỏ |

---

# 8. TIMELINE RIÊNG — BỆNH VIỆN MINH TRẠCH

| Mốc | Trạng thái | Người biết | Điều quan trọng |
|---|---|---|---|
| T−5 năm | Khoa tạo cell nhỏ trong institution hợp pháp | Khoa/Nam; Thảo biết phần mình | bệnh viện không thuộc network |
| D−14 | Phúc kiểm tra | Phúc + nhân sự liên quan | anomaly bắt đầu |
| D−12 | Huyền mở review | Huyền/compliance | discovery đến từ người vô tội làm đúng việc |
| D−10 | Khoa báo Khải | Khoa/Khải/Nam | Khoa báo thiếu |
| D−8 | scope thật rộng hơn | Khoa/Huyền; Thảo thấy risk | Nam vẫn thiếu thông tin |
| D0 tối | Huyền giữ review mở | Huyền/Khoa/Thảo | evidence chưa biến mất |
| D+1 sáng | cửa sổ Huyền/Thảo | nguồn độc lập có thể xuất hiện | B cần corroboration, không một file |
| True | police có thể tách cell khỏi institution | Vũ + hospital | không biến cả bệnh viện thành phản diện |
| Baseline/Bad | Khoa thu hẹp review tạm thời | Huyền vẫn nghi | institutional trace không biến mất hoàn toàn |

---

# 9. TIMELINE RIÊNG — CÁC QUẢN LÝ QUAN TRỌNG

## Hạnh

| Mốc | Hành động khách quan | Điều giấu |
|---|---|---|
| D−60 | nhận case Phúc | chưa có crisis |
| D−21 | Phúc rút | nguy cơ case thất bại |
| D−21→D−14 | cho tăng sức ép | giấu Khải việc vượt doctrine |
| D−10 | nhận lệnh cleanup | mô tả Phúc như case khó |
| D+1 | nếu bị đối chiếu với testimony | có thể đẩy trách nhiệm xuống người dưới | mức chỉ đạo thật |

## Khoa

| Mốc | Hành động khách quan | Điều giấu |
|---|---|---|
| D−12 | review chạm phạm vi mình | biết cell bị đe dọa |
| D−10 | báo Khải | giảm nhẹ scope |
| D−8 | biết review sâu hơn | tiếp tục giấu |
| D0/D+1 | thu hẹp access/scope | không thể xóa audit trail sạch |
| True | có thể bị corroborate bởi Huyền + Thảo + records | vai trò quản lý cell |
| Baseline | sống sót qua review hẹp nhưng trở thành liability | Nam về sau có thể thay/cắt |

## Hùng

| Mốc | Hành động khách quan | Điều giấu |
|---|---|---|
| nhiều tháng trước | nới ngoại lệ | giấu Nam/Khải |
| D−7 | bị audit | nhận ra nguy cơ |
| D−1 | hạ gói xuống luồng thường | lý do thật |
| D0 | giảm nhẹ khi Khải chất vấn | tự bảo vệ công ty/quyền lực |
| D+1 | khóa access/cleanup | muốn tách lỗi riêng khỏi core crime |
| True/Bad | có thể phản lại network để tự cứu | không đồng nghĩa trở thành người tốt |

## Khải

| Mốc | Hành động khách quan | Giới hạn knowledge |
|---|---|---|
| D−10 | nhận report Khoa, báo Nam | không biết Khoa báo thiếu |
| D−7 | audit Tân Lộ | không biết Hùng đã nới bao nhiêu |
| D−3 | phát hiện leak | chưa chắc Đức |
| D0 chiều | phát hiện breach Bắc | chưa biết Bắc hiểu gì |
| D0 tối | nếu có dấu, nâng Bắc N2 | không biết suy nghĩ Bắc |
| D+1 | cross-report nâng N3/N4 | vẫn không biết source ngoài network đầy đủ |
| Late | đề xuất cắt rủi ro | Nam cân thêm hậu quả xã hội |

---

# 10. TIMELINE RIÊNG — NGƯỜI PHẢN BỘI: LÊ GIA MINH

| Mốc | Minh biết gì | Minh làm gì | Hậu quả có thể có |
|---|---|---|---|
| Trước D0 | Tân Lộ là nguồn việc part-time | từng nhận/biết kênh | không liên quan network |
| D0 09:30 | Bắc đang cần việc | giới thiệu kênh | vô tình đưa Bắc tới pool |
| D0 tối, nếu Bắc hỏi | Bắc đang nghi job/công ty | báo người phụ trách để 'dập rắc rối' | thông tin có thể leo lên Hùng/Khải |
| Sau leak | biết mình đã nói nhiều hơn Bắc nghĩ | giảm nhẹ/giấu mức chia sẻ | betrayal về lòng tin |
| D+1 | thấy hậu quả lớn hơn dự kiến | có thể hối hận/thừa nhận | không tự xóa hậu quả |
| Không được xảy ra | biết Hành Lang/Nam từ đầu | — | sẽ retcon Stage 2 |

Minh **không phải member network**. Betrayal chỉ có logic vì cậu tưởng mình đang xử lý một vấn đề việc làm với một công ty hợp pháp.

---

# 11. TIMELINE RIÊNG — NẠN NHÂN QUAN TRỌNG: PHÚC

| Mốc | Phúc làm gì | Phúc biết gì | Điều Phúc không biết |
|---|---|---|---|
| D−60 | đồng ý thỏa thuận | người môi giới, tiền, lời hứa | Nam/Tân Lộ/cell |
| D−30 | nghi ngờ | lời nói và thực tế lệch nhau | cấu trúc sau môi giới |
| D−21 | muốn rút | mình có quyền muốn dừng | Hạnh là manager trong network lớn |
| D−21→D−14 | bị gây sức ép | áp lực là thật | command structure |
| D−14 | kiểm tra Minh Trạch | hospital có liên hệ với câu chuyện | Khoa/Thảo cụ thể |
| D−14→D−12 | trình báo | có dấu hiệu phạm pháp | logistics |
| D0 | bổ sung lời khai | lời kể của mình cần chính xác hơn | Tân Lộ/Nam |
| D+1 | có thể corroborate với source khác | phần A trở nên mạnh | vẫn không trở thành exposition machine |

---

# NAM KNOWLEDGE TIMELINE

| Mốc | Nam biết gì về Bắc | Nam nghĩ Bắc là ai | Có để ý Bắc không? | Đánh giá | Phản ứng |
|---|---|---|---|---|---|
| Trước D0 | không biết Bắc | — | không | — | không |
| D0 07:30 | sinh viên mới ở trọ, mới lên Hà Nội | hàng xóm trẻ | mức đời thường | vô hại | cư xử bình thường, có thể giúp thật |
| D0 16:00 | worker của job bị hạ sai luồng chính là Bắc | hàng xóm vô tình chạm exposure | có | N1 / exposure hành chính | yêu cầu quan sát, không làm lớn chuyện |
| D0 tối nếu Bắc không đào | không có hành vi tiếp nối | một sinh viên làm xong việc | giảm chú ý | vô hại/low risk | để yên |
| D0 tối nếu nhận report E29/E30 | Khải đã báo exact probing tới Nam, ghi receiver/time/payload | người tò mò vượt mức worker | tăng theo report | N2 / nguy cơ | theo dõi hậu quả; private read/keep source không tự báo |
| D+1 sau cross-report | Bắc xuất hiện ở từ hai cell trở lên | người đang chủ động nối cấu trúc | cao | N3 / nguy cơ nghiêm trọng | Nam trực tiếp xem report và cân cleanup |
| Khi có observable police-facing consequence được report | Nam nhận thông tin case nhiều nhánh đang được police giữ; A đã safe từ E28 | vector dẫn police tới structure | rất cao | N4 / khủng hoảng tổ chức | protect core theo report; không tự biết nội dung police custody kín |
| True route | D đã được corroborate | Bắc là người ngoài đã làm compartmentalization thất bại | không còn xử lý bằng quan sát | system failure | Nam mất khả năng giải quyết chỉ bằng cắt một nguồn |
| Cleanup route | police chưa đủ D | Bắc hiểu nhiều nhưng proof chain chưa đủ | cao | threat còn kiểm soát được | cắt access/contact, hy sinh nhánh đã lộ |

### Mốc Nam bắt đầu nghi

Nam **không nghi Bắc khi gặp ở trọ**. Mốc nghi hợp lý là sau D0 tối, khi có hành vi vượt phản ứng bình thường của một worker và thông tin đó được report.

### Mốc Nam xác nhận Bắc đang can thiệp

Nam chỉ **xác nhận** sau D+1 khi Khải có cross-report cho thấy cùng một Bắc xuất hiện trong hậu quả của từ hai cell trở lên. Đây là knowledge qua observable behavior, không phải omniscience.

### Vì sao Nam không xử Bắc sớm

- N1 chưa cho biết Bắc hiểu gì.
- Hành động mạnh với sinh viên ở chính khu Nam sống sẽ tạo thêm người hỏi.
- Nam hiểu phản ứng xã hội tốt hơn Khải.
- Doctrine của Nam là không dạy một người rằng thứ họ thấy quan trọng nếu họ chưa hiểu nó.
- Thiện cảm cá nhân với Bắc có thể có thật nhưng **không phải lý do chính**; lý do chính là risk management.

---

# POLICE KNOWLEDGE TIMELINE

| Mốc | Cảnh sát biết gì | Đang điều tra gì | Vì sao chưa thể hành động rộng | Bắc bổ sung gì nếu có |
|---|---|---|---|---|
| D−14→D−12 | Phúc từng đồng ý một thỏa thuận, muốn rút, bị gây sức ép; có tiền và yếu tố y tế | cưỡng ép/môi giới/tài chính quanh Phúc | Phúc chỉ biết tầng dưới; chưa có link logistics; bệnh viện mới là tên trong câu chuyện | chưa có Bắc |
| D−12→D0 | lời khai + narrow hospital query nhận confirmation visit/request cá nhân đúng scope | vụ Phúc tiến độc lập | chưa có multi-case group/account/routing bridge tới Tân Lộ; response không chứa toàn review | chưa có Bắc |
| D0 tối E28 | exact originals Phúc/counterpart so content paid-organ agreement/withdrawal/pressure; hospital xác nhận visit riêng | A=2 đã authenticate/preserve | thiếu group bridge, B/C, common current risk context X và D | không cần Bắc để giữ A |
| D+1 sáng | có thể nhận một bridge logistics hoặc hospital từ Bắc | kiểm chứng source mới | một source đơn không đủ để suy ra network | Bắc giúp đưa **địa chỉ của cầu**, không đưa kết luận thay police |
| D+1 trưa | nếu Huyền/Đức/Thảo/Yến corroborate độc lập | cấu trúc nhiều tổ chức | cần phân biệt institution hợp pháp với cell và xác định command | Bắc giúp nối timing/source |
| D+1 chiều | A+B+C đủ mạnh | network có môi giới + cell hospital + logistics biết việc | vẫn có thể thiếu D để chứng minh Nam | Bắc có thể chỉ ra pattern quan hệ để Vũ xác minh |
| True route | D có ít nhất hai nguồn/dấu command độc lập | phần lõi | threshold đã đạt | Bắc không còn phải tự điều tra |
| Bad/partial | A/B/C thiếu một hoặc D chỉ suy đoán | phần đã chứng minh | timing/evidence, không phải 'cảnh sát không tin' | Vũ tiếp tục sau ending nhưng game không cho breakthrough miễn phí |

## Evidence đủ mạnh

- Lời khai Phúc + contact record: mạnh cho **A**, không đủ B/C/D.
- Review Huyền + source giải thích tại hospital: mạnh cho **B**, không tự chứng minh A/C/D.
- Dispatch/reclassification + Đức/Yến/Tuấn/Hùng evidence: mạnh cho **C**, không tự chứng minh A/B/D.
- Dấu command/quan hệ Nam xuất hiện ở nhiều nguồn độc lập, hoặc một manager + record được corroborate: cần cho **D**.

## Evidence chỉ là suy đoán nếu đứng một mình

- Xe/logo Tân Lộ xuất hiện gần hospital.
- Nam quen Hùng.
- Tuấn né câu hỏi.
- Khoa nói nhiều về quy trình.
- Bắc có notebook tự nối arrows.
- Phúc tin một người môi giới là “trùm”.
- Đức nghi Hùng là đỉnh.
- Một timestamp/contact không có context.

Vũ phải phản ứng **nhanh hơn khi evidence mạnh hơn**. Nếu A+B+C đã đủ và anh vẫn chỉ nói “chưa tin”, Stage 3 coi đó là lỗi.

---

# IF BẮC DOES NOTHING

Đây là timeline baseline nếu Bắc:

- nhận job E22;
- không điều tra;
- không lưu clue có chủ đích;
- không hỏi Minh/Tuấn/Đức/Huyền;
- không báo Vũ;
- chỉ tiếp tục sống như sinh viên bình thường.

## B01 — D0 chiều

Khải phát hiện E22 đi qua pool thường. Hùng bị chất vấn. Worker được tra và Nam nhận ra worker là Bắc.

Nam đánh giá:

**Bắc = accidental exposure, chưa có dấu hiểu biết.**

Không có lý do hợp lý để làm hại Bắc.

## B02 — D0 tối

Bắc không có hành vi tiếp nối.

Không có Minh leak vì Bắc không hỏi.

Khải giảm mức ưu tiên Bắc và tập trung vào leak nội bộ Tân Lộ.

Nam tiếp tục cư xử đời thường nếu gặp Bắc.

## B03 — D+1 sáng

Khải thu hẹp leak tới Đức với độ tin cậy cao hơn.

Đức bị tước dần work access; private export trên điện thoại vẫn tồn tại và không bị account revocation xóa. Anh phải chọn hợp tác với nguồn giới hạn mình giữ, rút willingness/contact trong cửa sổ run để tự bảo vệ, hoặc sau này tự tìm kênh hợp pháp. Mọi lấy/xóa thật cần một event discovery/custody riêng; không mặc định giao private copy cho công ty.

Không có Bắc để giúp Đức nhận ra source ngoài Tân Lộ xác nhận nghi ngờ của mình.

## B04 — D+1 tại Minh Trạch

Khoa thành công biến review thành một cuộc điều tra hành chính hẹp hơn.

Huyền vẫn không hài lòng.

Review history còn tồn tại nhưng không tự biến thành án criminal.

Thảo tiếp tục compartmentalize đạo đức; bà không có trigger từ một source ngoài hospital buộc mình nhìn bức tranh lớn.

## B05 — D+1 tại cảnh sát

Vũ tiếp tục vụ Phúc.

Một số môi giới cấp thấp có thể bị xác định và xử lý vì hành vi thật của họ.

Phúc không bị coi là kẻ nói dối, nhưng lời khai của anh không tạo ra cầu tới Tân Lộ.

## B06 — D+2 đến D+7 tại Tân Lộ

Hùng bị giảm quyền hoặc chuẩn bị thay thế vì phá protocol.

Tân Lộ hợp pháp vẫn chạy để tránh gây chú ý và vì đa số nhân viên vô tội.

Yến tiếp tục lo nhưng có thể chưa hành động.

Tuấn dần nhận ra có cấp trên đã dùng bộ phận mình cho việc không minh bạch, nhưng chưa biết core crime.

## B07 — D+2 đến D+14 tại Hành Lang

Nam/Khải đóng hoặc co một số hoạt động.

Khoa trở thành liability.

Hạnh bị kiểm điểm nội bộ vì case Phúc; mức vượt doctrine của bà có thể chỉ bị lộ một phần.

Network chấp nhận mất một số mắt xích thấp thay vì cứu họ bằng hành động rủi ro.

## B08 — Vài tuần sau

Nếu không có evidence mới độc lập:

- vụ Phúc xử lý được một phần;
- Huyền vẫn mang nghi ngờ;
- Tân Lộ giữ vỏ bọc hợp pháp;
- cell hospital co nhỏ/thay người;
- Nam giảm quy mô;
- Hành Lang cuối cùng hoạt động lại thận trọng hơn.

**Bắc vẫn sống đời sinh viên bình thường và có khả năng được để yên.**

Điều này là normalization quan trọng từ Stage 1:

Bad Ending — Avoidance **không** có nghĩa “chỉ nhận một job là chắc chắn bị hại”. Avoidance chỉ có thể trở thành bad ending nếu Bắc đã đi tới N2/N3/N4 rồi mới cố bỏ mọi thứ, khi organization đã có lý do khách quan coi cậu là một risk chưa được kiểm soát.

---

# PLAYER INTERVENTION POINTS

Chỉ liệt kê event có thể thay đổi bởi hành động player; không thiết kế gameplay chi tiết.

1. **P01 — D0 sau E22:** Bắc có lưu/ghi nhớ được chi tiết bridge của job hay coi nó là chuyện vô nghĩa.
2. **P02 — D0 tối:** Bắc có hỏi Minh về Tân Lộ/job hay không; mức chia sẻ quyết định E26 có xảy ra.
3. **P03 — D0 tối:** Bắc có kiểm tra Tân Lộ/Tuấn ngoài phạm vi một worker bình thường hay không; quyết định N1→N2.
4. **P04 — D+1 sáng:** Bắc có tiếp cận Đức trước khi access bị khóa hay không.
5. **P05 — D+1 sáng:** Bắc có đưa được một dữ kiện có nguồn tới Vũ hay chỉ kể suy đoán.
6. **P06 — D+1 sáng:** Bắc có tạo lý do hợp lệ để pattern Huyền trở thành nguồn độc lập hay không.
7. **P07 — D+1:** Bắc có phân biệt Thảo (complicit insider) với Huyền (compliance vô tội) hay quy kết sai.
8. **P08 — D+1:** Bắc có coi Tuấn là đỉnh vì chức vụ hay tiếp tục tìm source cao hơn.
9. **P09 — D+1:** Bắc có khiến Đức/Yến/Thảo chuyển từ tự bảo vệ sang cung cấp phần sự thật của họ hay không.
10. **P10 — D+1 trưa:** Bắc có nối được A+B+C trước khi các cửa sổ access đóng.
11. **P11 — D+1:** Bắc có giữ toàn bộ evidence cho riêng mình hay đưa các phần đủ nguồn sang Vũ để bảo toàn.
12. **P12 — D+1:** Bắc có làm lộ mức hiểu biết cho Minh/Tân Lộ trước khi police preservation diễn ra.
13. **P13 — Late route:** Bắc có đủ source để chuyển từ “Nam quen người xấu” sang proposition D về quyền command.
14. **P14 — Ending threshold:** timing giữa police preservation và cleanup quyết định True / Cleanup / Delay / Wrong Trust / Exposure.

Không intervention point nào cho phép player:

- teleport;
- hack toàn bộ hệ thống;
- buộc một NPC biết thứ họ không biết;
- dùng một clue đơn lẻ chứng minh toàn mạng;
- đánh thắng organization bằng combat.

---

# 16. AUDIT A — CAUSALITY

Audit được chạy theo hướng **event sau phải truy ngược được tới nguyên nhân trước**.

## A1. Vì sao job nhạy cảm buộc phải di chuyển đúng D−1/D0?

**Rủi ro phát hiện:** nếu chỉ nói “vì plot cần Bắc nhận”, incident sẽ là coincidence.

**Sửa đã áp dụng:** E15 tạo cleanup; một số đầu việc phải đóng/hoàn tất. Hùng có một pending handoff lẽ ra đi luồng đặc biệt, nhưng dùng luồng đó sẽ khiến Khải hỏi vì sao nó chưa được xử lý. Hùng vì che lỗi riêng nên hạ classification.

**Kết quả:** PASS.

## A2. Vì sao Khoa không xóa review của Huyền?

**Rủi ro phát hiện:** nếu Khoa có quyền vận hành cao, người đọc có thể hỏi tại sao không xóa.

**Sửa đã áp dụng:** review nằm trong compliance system, chạm nhiều hồ sơ và người vô tội. Xóa trực tiếp tạo audit anomaly lớn hơn. Khoa chỉ có thể làm chậm, thu hẹp scope, đổi framing và khóa access.

**Kết quả:** PASS.

## A3. Vì sao Khải không xử Đức/Bắc ngay?

**Rủi ro phát hiện:** organization competent nhưng không hành động có thể trông giả.

**Sửa đã áp dụng:** Khải/Nam phân biệt knowledge state. N1 không chứng minh hiểu biết; với Đức, Khải ban đầu chỉ thấy access anomaly, chưa biết anh giữ gì. Hành động mạnh tạo thêm witness/attention. Họ ưu tiên phân loại và cắt access.

**Kết quả:** PASS.

## A4. Vì sao Minh leak có thể tới tầng Khải mà Minh không phải member?

**Rủi ro phát hiện:** nếu tin nhắn bạn học nhảy thẳng tới boss sẽ là teleport information.

**Sửa đã áp dụng:** Minh chỉ báo Tuấn/đầu mối công việc. Tuấn có thể chuyển vấn đề nhân sự lên Hùng vì job đang bị audit; Hùng/Khải đã theo dõi chính incident đó nên thông tin mới có lý do được escalated.

**Kết quả:** PASS.

## A5. Vì sao Vũ không tự nối Minh Trạch với Tân Lộ trước Bắc?

**Rủi ro phát hiện:** cảnh sát có năng lực mà không phá ra có thể trông bị nerf.

**Sửa đã áp dụng:** Vũ đã kiểm chứng narrow visit/request cá nhân và nhận response reception/compliance đúng scope trước E28; không có lý do dừng hỏi hoặc chờ Bắc. Phúc không biết review-group/Tân Lộ account-family/routing key; initial inquiry không chứa multi-case context. C03/C17 về sau cung cấp group bridge để targeted review verification khác. E28 giữ A từ originals hai phía, không đồng nghĩa đã có B/C hoặc common current risk X. Không thêm luật/corrupt gatekeeping.

**Kết quả:** PASS.

## A6. Vì sao True Ending không phụ thuộc một confession?

**Sửa đã áp dụng:** A+B+C+D đều yêu cầu corroboration. D đặc biệt cần ít nhất hai dấu command/quan hệ độc lập.

**Kết quả:** PASS.

### Kết luận Audit A

Không còn event bắt buộc nào chỉ có nguyên nhân “vì game cần thế”. Chuỗi chính vẫn là:

**triết lý Nam → incentive Hạnh → Phúc phản kháng → Huyền phát hiện → Khoa giấu → cleanup → Hùng che lỗi → job hạ luồng → Bắc chạm → Bắc nối → police corroborate hoặc organization cleanup.**

---

# 17. AUDIT B — KNOWLEDGE

## B1. Hùng có biết review bệnh viện chi tiết quá sớm không?

**Lỗi tiềm năng:** Stage 2 cấm.

**Sửa/khóa:** Hùng chỉ biết Khải đang rà nhóm khách hàng y tế; không biết danh sách case/scope Huyền. PASS.

## B2. Khoa có biết chi tiết dispatch Tân Lộ không?

**Lỗi tiềm năng:** sẽ phá compartmentalization.

**Sửa/khóa:** Khoa chỉ biết Tân Lộ là đầu mối cấp cao; E19–E23 không được báo chi tiết cho Khoa trừ khi late crisis cần cross-report, và khi đó chỉ nhận risk summary. PASS.

## B3. Nam có biết suy nghĩ/notebook của Bắc không?

**Lỗi tiềm năng:** omniscient villain.

**Sửa/khóa:** Nam nâng N0→N4 chỉ bằng assignment record, report từ Minh/Tân Lộ, cross-report nhiều cell và police-facing consequences. PASS.

## B4. Phúc có biết Nam/Tân Lộ để exposition không?

**Sửa/khóa:** Không. Phúc giữ knowledge ở source người/sức ép/hospital name. PASS.

## B5. Huyền có biết conspiracy khi mở review không?

**Sửa/khóa:** Không. Huyền chỉ biết pattern administrative. PASS.

## B6. Tuấn có biết core crime không?

**Sửa/khóa:** Không. Anh biết ngoại lệ y tế và có thể nói giảm để bảo vệ công ty; đó là lý do red herring hợp lý. PASS.

## B7. Minh có biết network để cố ý bán Bắc không?

**Sửa/khóa:** Không. Minh chỉ cố làm vấn đề công việc biến mất. PASS.

## B8. Vũ có nhảy knowledge quá nhanh sau khi Bắc nói?

**Sửa/khóa:** Không. Bắc chỉ cung cấp bridge/source. Vũ nâng knowledge sau corroboration độc lập. PASS.

### Kết luận Audit B

Không nhân vật nào được cấp knowledge vượt nguồn họ có. Các giới hạn Stage 1/2 được giữ nguyên.

---

# 18. AUDIT C — TIMING

## C1. D0: Bắc có đủ thời gian trọ → trường → Tân Lộ/job → về trọ không?

- S01 trọ07:30–08:35; travel25m→trường09:00.
- School/meal09:00–11:15; job choice group34m→11:49; travel35m→Tân Lộ12:24/check-in6m→12:30.
- Job12:30–14:10 gồm actual travel30m12:54→13:24 và handover13:52.
- Nearby meal arrival14:30; ordinary afternoon tới17:30; travel hospital area→trọ35m tới18:05, last beat2m→audit18:07.

Fixed departure/arrival cards theo §0.1, không teleport hoặc hidden reading clock. PASS.

## C2. Nam có teleport từ risk meeting về trọ không?

Không cần meeting trực tiếp. E24 là report qua Khải; Nam có thể ở/di chuyển về trọ trước E25. PASS.

## C3. Huyền và Vũ có thể làm việc song song trong D0 tối không?

Có. Họ ở hai institution khác nhau và chưa cần gặp nhau. PASS.

## C4. D+1 có quá nhiều source để Bắc tự đi gặp hết không?

**Lỗi tiềm năng phát hiện:** E32–E35 chồng giờ.

**Sửa đã áp dụng:** shared schedule §0.1 cho S08 morning C18 offer, S09 actual source-led requests, C18 police receipt10:35/C19 receipt10:50, hospital arrival10:50 hoặc10:55 và core+Thảo complete11:20/11:25. Local windows giữ nguyên. S12/S13 verify retained copies. Bắc không physically visit four sources; actual queued/received/authenticated khác nhau.

PASS.

## C5. Organization có đủ thời gian cleanup trước police preservation?

Có một race hợp lý D+1:

- local willingness/access closures11:00/11:30/12:30 sau required warnings, không global lock;
- baseline current decisions L13:20/H13:45 và broker receipts13:32/14:05 không phụ thuộc private N3;
- actual E38 baseline14:55 mở proactive collection; full D16:10;
- global17:00, hoặc actual warned acceleration canonical16:30 vẫn có saving action trước lock.

True/Bad route khác nhau chính ở thứ tự hai event **police preservation** và **cleanup lock**. PASS.

## C6. Evidence có biến mất quá nhanh vô lý không?

Không. Vật/permission dễ mất trước; institutional audit trail và police records tồn tại lâu hơn. PASS.

### Kết luận Audit C

Không có nhân vật bắt buộc xuất hiện ở hai nơi không thể đi kịp. Các cửa sổ song song được ghi rõ là không bắt buộc protagonist tự đi hết.

---

# 19. FINAL CONSISTENCY CHECK

Stage 3 này giữ nguyên các lock quan trọng:

- Bắc 18 tuổi, năm nhất, thiếu tiền.
- Nam gặp Bắc như hàng xóm trước khi biết exposure Tân Lộ.
- Nam không chọn Bắc.
- Phúc là điểm khởi phát crisis.
- Hạnh vượt doctrine.
- Huyền phát hiện bằng công việc hợp pháp.
- Khoa giấu scope review.
- Hùng tạo lỗ hổng cuối vì che lỗi riêng.
- Tân Lộ chủ yếu là công ty thật.
- Minh Trạch chủ yếu là bệnh viện thật.
- Tuấn không biết core crime.
- Minh không phải member network.
- Cảnh sát đã điều tra trước Bắc.
- Vũ không bị viết ngu hoặc tham nhũng.
- Không có single magic evidence.
- Nếu Bắc làm nothing từ đầu, organization có khả năng để cậu yên và vẫn tự xử lý crisis.
- Bắc chỉ làm lịch sử rẽ nhánh khi cậu **nối các nguồn độc lập**.
- True ending yêu cầu corroboration và timing, không yêu cầu combat hay omniscient deduction.

---

# 20. STAGE 4 HANDOFF

Tài liệu tiếp theo có thể dùng Stage 3 để xây **PLAYER-FACING STORY** mà không được thay đổi objective truth.

Khi chia opening/chapter/scene sau này, mỗi scene phải trả lời được:

1. nó nằm trước hay sau event objective nào;
2. NPC trong scene đang ở knowledge state nào;
3. evidence được thấy đã tồn tại bằng event nào;
4. evidence đó còn trong window hay đã bị cleanup;
5. action player có thay đổi P01–P14 hay chỉ là presentation;
6. nếu scene bị bỏ khỏi game, causality khách quan có còn đúng không.

**END — OBJECTIVE TIMELINE / STAGE 3**

### P4 causal terminal ordering

At each authored receipt/closure, process original police receipt/authentication first by `(OBJECTIVE_TIME, event_sequence)`, normalize X_RISK/X_COMMAND from raw sources, then test whether a warning-backed closure removes the **last** feasible path of A/B/C/X/D. Persist one earliest `DECISIVE_LOSS` with slot, before/after source paths, direct/Minh/baseline/ordinary cause and warning. Later harmless attempts cannot overwrite it. E28 A=2 and all later police custody remain monotonic. D-only loss has the same historical attribution even when ABCX are safe. A local source closure with an alternate still open records loss of access only. No earlier deadline is created by this section; OT §0.1 warning/feasibility remains binding.
