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
| P2 | Tách observed/inferred/police-custody/BARC/source-existence/access/willingness/copy | CHARACTER_WEB, OBJECTIVE_TIMELINE, CLUE_GRAPH, ENDING_LOGIC; matching scene hooks và FS Act I lifecycle | Full diff; same report/different thought; E28 A preserved; retained copy không mất do account lock | VERIFIED — phase commit |
| P3 | Một authored clock, morning source requests/intakes, pre-loss warning và action costs | OBJECTIVE_TIMELINE, CLUE_GRAPH, PLAYER_STORY, SCENE_BREAKDOWN; FS clock | Lịch khả thi trong travel bounds; last loss có warning và action cứu trước | PENDING |
| P4 | Total terminal resolver; decisive loss history; partial transitions | ENDING_LOGIC, PLAYER_STORY, SCENE_BREAKDOWN | ABC=P/X=false; mixed leaks; D-only; weak routes; monotonic custody | PENDING |
| P5 | Presentation theo contract P0–P4; conditional S13/S14, fast recap S12, custody-first/bypass S17 | PLAYER_STORY, SCENE_BREAKDOWN | Scene entry/action/state/exit nhất quán; no compulsory unsafe encounter | PENDING |
| P6 | Full production dialogue/action/state S06–S18 cùng 13-section schema | FULL_SCRIPT | S01–S18 mỗi scene đủ schema, branch actions/state có nguyên nhân, no late outlines | PENDING |
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

- H05: E12 giữ đúng subset; E28 nhận/xác thực exact content từ hai original custodians, CASE.A=2 trước S09. S09/S11/S15 chỉ mở observation và intake nguồn mới, không đòi giao lại hoặc reset hồ sơ cảnh sát.
- H06/H07: S13 không award understanding/Khải certainty vì scene completion; đủ retained raw risk context thì Vũ vẫn verify X khi private inference sai. E37 và Nam chỉ biết reports có payload/recipient/receipt thật. S14 baseline giữ prior BARC; S15 không bị chặn bởi private N3.
- H08: permission correction chỉ TUAN_NOT_RECLASSIFIER; professional TUAN_CORE_SCOPE_VERIFIED là kết luận trong case, không blanket innocence hoặc quiz.
- M04: C18 ở điện thoại cá nhân Đức từ E17, không sync work account. Account lock không xóa private copy; willingness/contact, existence và custody riêng. Mọi seizure/deletion thật cần event discovery/quyền chạm/custody.
- M07: intentional later C03 history cho same fields/original 13:52 time với observed_at mới. Default proof photo chỉ seal; authored ảnh nhãn rõ mới có C04, cùng content luôn cho cùng fact trên replay.
- M12/L02: Vũ đã hỏi hẹp về lần Phúc tới hospital trước D0, nhận response cá nhân đúng scope; thiếu group/routing bridge cụ thể chứ không ngừng điều tra. Dấu leak là thông tin dư tại Tuấn/company khớp phần Bắc chỉ chia Minh.
- Root đã đọc diff và các delta cuối; reviewer độc lập bắt các gate private-N3 còn sót ở S15 cùng wording Vũ S13. Đã thay các gate đó bằng actual source/custody/report conditions. Không động MASTER, BACKSTAGE đã khóa, hai DOCX hoặc historical audit; cả năm nguồn được đối chiếu byte-for-byte.
- Reserved: actual morning requests/receipts, authored clock/warnings/local-vs-global lock thuộc P3; decisive-loss resolver/partial edges P4; scene presentation P5; dialogue/state production P6. Chưa claim final test PASS.
