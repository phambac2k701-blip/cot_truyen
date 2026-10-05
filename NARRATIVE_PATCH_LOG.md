# NARRATIVE PATCH LOG

> **Baseline:** ff47d5989886b680c1d32c170a469cc2d70edc59  
> **Roadmap:** FINAL_NARRATIVE_AUDIT.md, audit snapshot f17628f53e78805e739382ab8d811cea1a07edfe  
> **Scope authorized:** P0→P6 source patch, completion S06–S18, T01–T25 and final re-audit.  
> **Historical audit:** giữ nguyên FINAL_NARRATIVE_AUDIT.md; kết quả mới ở FINAL_NARRATIVE_REAUDIT.md.

## Implementation plan

**Goal:** khép proof/state/timing/ending, hoàn tất production script mà không đổi canon hoặc rewrite Act I.

**Authority:** MASTER_GAME_BIBLE → objective truth BACKSTAGE → canonical design → presentation/script. Audit là roadmap, không tự ghi đè fact đã khóa. Hai DOCX giữ nguyên như nguồn brainstorm.

**Execution:** các lượt đọc/review độc lập; mutation canonical theo phase tuần tự, root kiểm diff và commit. Workspace là checkout riêng `cot_truyen_work`, branch `narrative/final-patch`. Không reset/revert WIP; commit/push fast-forward theo phạm vi được yêu cầu.

**Global constraints:** Bắc 18 tuổi/năm nhất; school nền; Nam không toàn tri/confession; kindness thật; Minh outsider; Tuấn không core villain; Vũ có năng lực; không magic file/raid/combat; notebook fact/source/time; no-C28 và không đoán boss sớm vẫn có True route.

| Phase | Deliverable / interface cho phase sau | Files | Verification | Status |
|---|---|---|---|---|
| P0–P1 | Mapping canon→truth→proof→source→scene→ending; A/B/C/X/D1/D2 payload/provenance và accepted alternatives cùng nghĩa | BACKSTAGE, CLUE_GRAPH, ENDING_LOGIC | Full diff + independent canon/proof review; hai MEDIUM của review đã sửa; X được làm rõ ngoài transaction relation | COMPLETE — GitHub 82333dc |
| P2 | Tách observed/inferred/police-custody/BARC/source-existence/access/willingness/copy | CHARACTER_WEB, OBJECTIVE_TIMELINE, CLUE_GRAPH, ENDING_LOGIC; matching scene hooks và FS Act I lifecycle | Full diff; same report/different thought; E28 A preserved; retained copy không mất do account lock | COMPLETE — GitHub 79c5f9a |
| P3 | Một authored clock, morning source requests/intakes, pre-loss warning và action costs | OBJECTIVE_TIMELINE, CLUE_GRAPH, PLAYER_STORY, SCENE_BREAKDOWN; FS clock | Lịch khả thi trong travel bounds; last loss có warning và action cứu trước | IN PROGRESS |
| P4 | Total terminal resolver; decisive loss history; partial transitions | ENDING_LOGIC, CLUE_GRAPH, OBJECTIVE_TIMELINE, PLAYER_STORY, SCENE_BREAKDOWN | ABC=P/X=false; mixed leaks; D-only; weak routes; monotonic custody | COMPLETE — commit recorded below |
| P5 | Playable event-driven S01–S18; conditional S13/S14, fast recap S12, custody-first/bypass S17 | PLAYER_STORY, SCENE_BREAKDOWN | 18 scene contracts, entry/action/state/exit, no compulsory unsafe encounter | COMPLETE — commit recorded below |
| P6 | Full tagged production script S06–S18 plus event spec | FULL_SCRIPT, EVENT_IMPLEMENTATION_SPEC | 18 event graphs/cards, save/load, state/source checks | COMPLETE — commit recorded below |
| Validation | T01–T25 có inputs/actions/transitions/results + 17-layer adversarial re-audit | FINAL_NARRATIVE_REAUDIT, validation fixtures nếu cần | Không claim runtime/human playtest khi mới kiểm tài liệu/reference model | PENDING |

## Pre-flight dependency review

| Producer → consumer | Shared contract | Resolution |
|---|---|---|
| P1 → P2/P3/P4 | Proof payload và source origin | Khóa P1 trước, downstream không đổi nghĩa proof để cứu một scene |
| P2 → P3/P4/P5 | Police custody và actor knowledge | Custody khởi từ event thật; player visibility không phải institutional memory |
| P3 → P4/P5/P6 | Window/request/receipt và authored time | Late callback chỉ dùng source đã lấy sáng; closure có cause/warning |
| P4 → P5/P6 | Accepted endings và weak-route exits | Full script dùng cùng predicate, không bịa fallback riêng |
| P5 → P6 | Scene entry/action/state/exit | Script thêm thoại/action thật trong flow đã patch, không redesign |
| P6 → validation | Actual 18-scene script | Đọc/attack lại độc lập; test fixture không thay thế đọc thoại |

## Canonical rulings

- **D architecture:** D1 manager-firsthand C32H (Hùng/logistics) hoặc C32K (Khoa/hospital); D2 là một quyết định hiện tại khác ở **nhánh khác**, origin độc lập: C33_AUTH hospital cho Hùng; C34_AUTH logistics cho Khoa. Original receiver-side reply từ endpoint Nam phải được xác thực, không chỉ Khải tự forward mang tên Nam. C10_SOURCE_LINK late S16 từ case môi giới hiện hữu xác minh nhánh nguồn thực hiện đúng directive D2, để đủ canon cả ba nhánh; đây là context, không count cùng order lần thứ ba. Bare C31 contact/time và generic C34 closures chỉ là lead. Cost nếu sai: đồng bộ accepted routes, không đổi identity/canon Nam.
- **Police A:** E12 là subset; E28 tối D0 nhận exact records Phúc bỏ sót và so nội dung với original thread phía broker counterpart, từng fact tiền/nội tạng, withdrawal, pressure. Metadata chỉ xác nhận exchange/order; hospital request chỉ xác nhận visit. CASE.A=2 từ E28 trước S09; player hiểu/đã xem riêng. Annex command hiện tại C10_SOURCE_LINK chỉ được nhận sau E38 trong S16, không phải future record đã giữ ở E28. Cost nếu sai: điều chỉnh exact custody subset, không reset hồ sơ Vũ.
- **Loss attribution:** earliest irreversible last-required-path loss, có timestamp và sequence. DIRECT/MINH attempts không thắng cause đã quyết định trước. D-only DIRECT→G5, MINH→G2, baseline/ordinary expiry với ABCX preserved→G4. Cost nếu sai: đổi taxonomy/predicate/matrix/cinematic cùng nhau.
- **X:** verified shared current risk/escalation role/context ở Khải, vượt quan hệ cùng giao dịch mà ABC đã có thể chứng minh. C24/C25 cần endpoint + scope request/response + crisis context; C03/same group chỉ là transaction bridge lead. Vũ derive từ đủ raw sources đã giữ dù private inference sai. ABC=P/X=false có thể thật khi common risk context chưa được nhận/xác thực; cảnh sát vẫn hành động trên các case đã giữ. X không tự đòi Nam authorize hoặc Khải là apex; D giữ câu hỏi command.
- **Clock:** reading/notebook/ordinary inspect không time cost; dialogue/travel/deliberate delay có authored objective cost khi commit action. Cost nếu sai: đổi action costs/window schedule, không hidden punishment.
- **Validation scope:** re-audit tài liệu và mô phỏng state/source routes; runtime/performance/empirical tỷ lệ blind win chỉ có thể đo khi có build/tester thật. Không trình bày simulation thành playtest đã diễn ra.

## Full-read evidence before source mutation

Current main được xác nhận là baseline trên; Git tree có 12 files. Toàn văn MASTER, BACKSTAGE, CHARACTER_WEB, OBJECTIVE_TIMELINE, CLUE_GRAPH, PLAYER_STORY, ENDING_LOGIC, SCENE_BREAKDOWN, FULL_SCRIPT và historical audit đã được đọc theo bounded chunks; những lượt có truncation được đọc lại phần thiếu. Hai DOCX được extract toàn Word XML text, đối chiếu original bytes và đọc đầy đủ (idea: 7 paragraphs; bổ sung: 2 paragraphs/4 text nodes). Bản snapshot trước audit trùng source blobs trên main; clone giữ original history.

## Baseline witnesses cần đóng

- H03: graph/scene cho C33+C34 thay mất C32, ending gate còn yêu cầu manager D1.
- H09/T15: ABC=2, X=false, lock, no leak/abandon không match predicate cũ.
- M05/T16: MINH gây last-path loss rồi DIRECT attempt vô hại có thể ghi đè LEAK_PATH.
- H06/H07/T03–T05: S13 auto private understanding; S14 baseline closure auto N3 cho Nam.
- H04/T11: source offer mới trưa sau window sáng; callback chưa tách retained copy.

## Phase records

Chỉ đánh COMPLETE sau khi diff/consistency của phase đã được kiểm và commit tồn tại. Finding closure và test outcomes sẽ được ghi ở đây theo phase; final report chứa từng T01–T25 và residual risks cụ thể.

### P0–P1 — proof contract đã kiểm

- Commit source local `fe721763b97221b0b114d44260c864a98be88d3e`; GitHub [82333dc](https://github.com/phambac2k701-blip/cot_truyen/commit/82333dc267882ab93de6e2d68c6c9b00609f8e1b). Hai commits có cùng tree `45d47114b339e2528c3057376879cf3a86b1ed58`; mỗi blob được đối chiếu SHA trước khi cập nhật main, ref/tree được kiểm lại sau publish.
- H02: A có paid-organ content/withdrawal/pressure; B có notice + knowing assistance; C có known purpose + approve + independently real execution/settlement. No-Thảo và Yến-only routes giữ cùng proposition.
- H03: accepted D pairs duy nhất C32H+C33_AUTH hoặc C32K+C34_AUTH. C31/generic closure không proof; mất cả managers không pure-record recovery.
- H08: correction Tuấn chỉ not-reclassifier; verified case scope riêng. Đức không biết ai được secret briefing.
- M01: exact counterpart message content xác thực A; metadata/visit không tự xác thực text. E28 tối D0 đã giữ A, không player redelivery.
- M02: D có original Nam receiver-side reply, distinct current decisions/origins, identity/source/branch scope, manager cooperation và late broker source-link với actual intake/channel/self-protection. Full D đủ cả ba nhánh; source link không count lại một order làm D2 thứ ba.
- Review độc lập đọc toàn diff và toàn MASTER; bắt E28 summary sai ngày và broker cooperation thiếu trigger. Cả hai đã sửa bằng patch nhỏ. Root đọc toàn diff và các fix; check diff giữ intentional Markdown hard breaks.
- X được phân biệt khỏi transaction association: thiếu authenticated common current risk context vẫn có ABC preserved hợp lệ, Vũ vẫn xử lý các case đã có. Đủ raw risk sources thì professional verification không phụ thuộc teen trả lời puzzle đúng.
- Đây là đóng contract của P0–P1, chưa claim toàn repo đã đóng H02/H03/H08/M02: P2–P5 còn đồng bộ event/knowledge/lifecycle/scene, P6 còn trình bày thực tế và validation còn chạy T01–T25.

### P2 — knowledge, custody và lifecycle đã đồng bộ

- Commit local `53c7cab551743d6241874d596e928e94d8fc2189`; GitHub [79c5f9a](https://github.com/phambac2k701-blip/cot_truyen/commit/79c5f9a4f1815478614b04012a556bb861f26d22). Đối chiếu từng blob và toàn tree `15f2f102837c2e9807d7153a72cea3ff5aba2435`; main cập nhật fast-forward, kiểm lại ref/tree thành công.
- H05: E12 giữ đúng subset; E28 nhận/xác thực exact content từ hai original custodians, CASE.A=2 trước S09. S09/S11/S15 chỉ mở observation và intake nguồn mới, không đòi giao lại hoặc reset hồ sơ cảnh sát.
- H06/H07: S13 không award understanding/Khải certainty vì scene completion; đủ retained raw risk context thì Vũ vẫn verify X khi private inference sai. E37 và Nam chỉ biết reports có payload/recipient/receipt thật. S14 baseline giữ prior BARC; S15 không bị chặn bởi private N3.
- H08: permission correction chỉ TUAN_NOT_RECLASSIFIER; professional TUAN_CORE_SCOPE_VERIFIED là kết luận trong case, không blanket innocence hoặc quiz.
- M04: C18 ở điện thoại cá nhân Đức từ E17, không sync work account. Account lock không xóa private copy; willingness/contact, existence và custody riêng. Mọi seizure/deletion thật cần event discovery/quyền chạm/custody.
- M07: intentional later C03 history cho same fields/original 13:52 time với observed_at mới. Default proof photo chỉ seal; authored ảnh nhãn rõ mới có C04, cùng content luôn cho cùng fact trên replay.
- M12/L02: Vũ đã hỏi hẹp về lần Phúc tới hospital trước D0, nhận response cá nhân đúng scope; thiếu group/routing bridge cụ thể chứ không ngừng điều tra. Dấu leak là thông tin dư tại Tuấn/company khớp phần Bắc chỉ chia Minh.
- Root đã đọc diff và các delta cuối; reviewer độc lập bắt các gate private-N3 còn sót ở S15 cùng wording Vũ S13. Đã thay các gate đó bằng actual source/custody/report conditions. Không động MASTER, BACKSTAGE đã khóa, hai DOCX hoặc historical audit; cả năm nguồn được đối chiếu byte-for-byte.
- Reserved: actual morning requests/receipts, authored clock/warnings/local-vs-global lock thuộc P3; decisive-loss resolver/partial edges P4; scene presentation P5; dialogue/state production P6. Chưa claim final test PASS.

### Handoff ruling P4 — không giữ điều kiện vòng D/X

- Witness mới: A/B/C đã preserve; thiếu riêng role Khải ở logistics nên X cũ=false; Hùng firsthand current L + hospital current H original + broker annex match H có thể chứng minh Nam hiện tại điều phối cả ba nhánh trong cùng crime case. EL §1.4 chấp nhận COMMAND pair, nhưng §11.1 còn đòi “X đã sourced” trước khi chấp nhận chính payload đủ mạnh để chứng minh quan hệ. Đây là một gate vòng, không phải thiếu evidence.
- **Ruling:** X có một nghĩa: authenticated current common coordination của các cell gắn cùng crime/case, vượt mere transaction association. C24/C25 shared-risk Khải là profile sớm; stronger late all-three Nam coordination là profile tương đương khi actual manager/other-branch authorization/execution/broker facts cùng scope đã xác thực. Không auto-X từ COMMAND enum, clue ID, lawful authority, cùng từ khóa hoặc private hypothesis.
- Missing riêng Khải remit vẫn có thể để KHẢI_LAYER=false; không thêm core proof gate ngoài proposition cần chứng minh. Accepted D được kiểm độc lập, sau đó professional raw-source X normalization trước resolver. Nếu chỉ ABC và không có stronger relation facts thì X vẫn false và partial phải rõ.
- Cost nếu ruling sai: rework đúng predicate/context của X và các consumers; không đổi identity Nam, crime truth hoặc thêm twist. P4 phải đồng bộ BS/CG/EL/CW/OT/PS/SB và có negative fixtures unlinked lawful authority/mismatched case/group. Ruling này là handoff, chưa ghi implementation COMPLETE.

### P3 — clock, morning acquisition và warnings đã kiểm

- Sáu source files được patch thật: OT/CG/EL clock/PS/SB và minimal Act I clock. Writer freeze, root đọc toàn delta và reviewer độc lập đọc diff cùng các context cần thiết. Phase commit/publication được ghi sau khi tạo và đối chiếu tree.
- H04: actual C18 offer/copy/contact từ S08; local receipt09:45 hoặc professional receipt10:35. C19 bounded lead từ S09, actual contact10:40/receipt10:50. Late new queries dùng actual offsets; S12/S13 chỉ verify retained sources, không backdate pickup sau cửa sáng.
- M03/M08/M09: single authored clock; reading/inspect/notebook/hint/retry/private hypotheses0. Dialogue/travel/deliberate wait có fixed cost, card trước confirm, charge once và save state đầy đủ. Sai interpretation riêng không tăng BARC, không tốn window.
- Required warning checkpoints:09:25 trước worker/Đức11:00; hospital notices trước11:30; finance notice trước12:30. Các local closures tách global17:00. Acceleration chỉ khi actual report và fresh warning W để còn saving action; canonical W14:00→16:30.
- Narrow review fix: advertised40m gồm toàn remaining authentication đủ actual E38, không queue=proof. Nếu remainder R dài hơn/không biết, candidate max(16:30,W+145m) chỉ được advance khi notice+R+75m D+10m buffer thực sự vừa và nguồn còn mở; nếu không, baseline17:00. Không nén professional checks để vừa deadline.
- Current original decisions L13:20/execution13:25 và H13:45/execution13:50 đã tồn tại trước E38, khác request/origin. Late broker police annex receipt15:50, full exact-D2 matching16:10 trên baseline t0=14:55; không future record ở E28. Source existence, receipt và authentication riêng.
- L01 pointers đã đồng bộ. Review LOW meal location S05 và S16 exact baseline group đã sửa. Fresh diff-check không lỗi; source schedules giữ nguyên sau narrow fixes. MASTER, crime truth, CW, historical audit và raw DOCX không bị P3 mutation. Đây là scoped source verification; full runtime, blind win rate và T01–T25 final chưa được claim.

### P4 — terminal resolver closure

- X_RISK and X_COMMAND are two raw-source profiles for the same current coordination proposition. Authenticate distinct same-case D1/D2, original receiver-side Nam decision, execution, and matching original broker annex before normalizing X_COMMAND. Khải-specific remit may remain false. Same transaction/account/keyword, lawful unrelated authority, duplicate forward and private theory do not grant X.
- Total terminal order: timely full custody G6; qualified N3 abandonment G3; immutable earliest irreversible last-path DIRECT G5 / MINH G2; ABCX safe but D late G4; all remaining terminal partials including ABC safe/X false G1. While alternatives remain, the run remains ongoing.
- DECISIVE_LOSS persists event time/sequence, required slot, source paths before/after, cause, warning receipt and feasible saving action; later harmless attempts cannot change it. CASE custody stays monotonic. Resolver fixtures in ENDING_LOGIC cover partial A+B/A+C/B+C, D-only, mixed leaks, circular X and negative matching.
- P0–P3 canon/clock/provenance remain authority; no re-audit or runtime claims here.

### P5 — playable presentation

- S01–S18 player-facing flows now center on world lure → player action → observed proof → authored NPC/world response. Every SCENE_BREAKDOWN scene has entry, environment, curiosity, action, discovery, automatic/micro/signature events, NPC routine, state, missed detail, return, fail-forward, exit and hooks. 18 primary set-pieces, with secondary beats possible inside S04/S08/S10/S16/S17; no jumpscare quota.
- S08 raw source morning copy and S09 scoped request preserve P3 offsets. S12 recap avoids repeated Tuấn interrogation. S13 private inference is separate from competent Vũ verification; S14 only actual reports raise BARC. S15 custody precedes optional S17, whose room jam has a physical cause and release; direct S18 bypass remains.
- P4 X normalization and earliest decisive loss persist; no scene completion grants police proof, boss identity or NPC knowledge. This is production design, not runtime playtest.

### Block 3 — paired game script and event spec

- S01–S05 retain detailed Act I script with a current P5 tagged overlay; S06–S18 now have full 13-section tagged game-script coverage, dialogue/source/UI, branch, timing and continuity rather than outline anchors.
- EVENT_IMPLEMENTATION_SPEC shares exactly 18 signature IDs with the script and supplies 18 explicit scene graphs plus fully fielded event cards for preconditions, trigger, world/NPC state, actions, custody/knowledge/report/time, save/load, skip/fail-forward, hooks and required assets. Micro and discovery stages are named within each card/graph.
- Critical source scheduling, X_COMMAND normalization, optional S17 jam/bypass and total S18 resolver have separate literal contracts. Source requests are not receipts, and cinematic/scene completion grants no clue. No Godot runtime code/playtest claimed.
