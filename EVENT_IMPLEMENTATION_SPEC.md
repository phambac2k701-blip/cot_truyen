# EVENT IMPLEMENTATION SPEC — S01–S18

**Authority:** MASTER_GAME_BIBLE → BACKSTAGE/OBJECTIVE_TIMELINE/CLUE_GRAPH/ENDING_LOGIC → P5 PLAYER_STORY/SCENE_BREAKDOWN → paired FULL_SCRIPT. Scene IDs and signature IDs match script exactly. Godot 4.x target; this is a story-state contract, not a claim of runtime implementation.

## Shared runtime contract

- `GameState`: versioned snapshot of OBJECTIVE_TIME, scene stage, source existence/access/willingness, observed fields, original/observed/received/authenticated times, police custody A/B/C, X profiles, D provenance, report ledger/recipient/receipt, BARC, DECISIVE_LOSS, one-shot keys, prop/NPC stage. `SaveManager` writes all related flags atomically at event boundaries.
- `EventManager.trigger(id)` rejects a repeated one-shot. `InteractionManager` raycast/Area3D calls a reusable door/document/phone/printer/compare wrapper. `AnimationPlayer` or transform/visibility swaps drive props; `AudioStreamPlayer3D` and light controllers react to staged events. `NavigationAgent3D` or fixed markers drive the few NPC routes.
- `source request`, `receipt`, `authentication`, `case preservation`, `player observation`, `private inference`, `organization report receipt` are separate transitions. A/B/C custody never decreases after preservation; E28 starts A=2. C18 on Đức personal phone survives worker account closure. C10_SOURCE_LINK annex exists in its custodian before police intake but cannot be used until actual post-E38 receipt/authentication.
- P3 objective time is authoritative: committed authored actions/travel/waits charge once and display arrival/deadline card before choice. UI/read/retry/private theory0. Source q-relative schedule and warning feasibility are exactly OBJECTIVE_TIMELINE §0.1–0.2; local11:00/11:30/12:30 differs from global17:00. No queued request equals a receipt. Completed police work runs in parallel and never retimes when Bắc waits.
- Source IDs are stable; once flags do not become inferential truth. On load rebuild the door/light/prop variant and NPC marker from snapshot before enabling triggers, restore event sequence/timers, and suppress already played one-shots. Rollback to an earlier save restores the earlier coherent snapshot, including absence of later evidence.
- Graph notation `!` mandatory, `?` optional, `~` missable, `[condition]` conditional, `*` repeatable read, `1` one-shot. The common per-scene nodes `ENTER!1 → MICRO?1 → DISCOVERY?* → SIGNATURE!1 → EXIT!1` can branch and rejoin; a micro or discovery is not itself proof unless its card's action writes the fact. `S17` entire graph is `[return chosen]`, and its bypass connects S16→S18.

## Scene event graphs

- **S01 :** `S01_ENTER!1 → S01_MICRO?1 → S01_DISCOVERY?* → S01_POWER_REPAIR!1 → S01_EXIT!1`; `S01_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Không xem card vẫn tới lớp; thao tác thử ổ có hint không tốn thời gian.`. `S01_DISCOVERY` repeats as a read without time or duplicate clue. `S01_EXIT` requires `Đồ được đặt, điện ổn, player xác nhận rời trọ 08:35.`.
- **S02 :** `S02_ENTER!1 → S02_MICRO?1 → S02_DISCOVERY?* → S02_CLASS_ROUTINE!1 → S02_EXIT!1`; `S02_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Bỏ qua mọi thoại tùy chọn vẫn có link và lý do xem việc.`. `S02_DISCOVERY` repeats as a read without time or duplicate clue. `S02_EXIT` requires `Lớp/bữa trưa kết thúc 11:15; listing có thể mở.`.
- **S03 :** `S03_ENTER!1 → S03_MICRO?1 → S03_DISCOVERY?* → S03_JOB_ACCEPT!1 → S03_EXIT!1`; `S03_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Đã từ chối ban đầu vẫn có một lần nhận lại trong window; không rơi vào bế tắc.`. `S03_DISCOVERY` repeats as a read without time or duplicate clue. `S03_EXIT` requires `Job accepted; đi Tân Lộ theo travel card tới12:24.`.
- **S04 :** `S04_ENTER!1 → S04_MICRO?1 → S04_DISCOVERY?* → S04_SCAN_MISMATCH!1 → S04_EXIT!1`; `S04_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Không inspect nhãn vẫn có biên nhận/history và audit.`. `S04_DISCOVERY` repeats as a read without time or duplicate clue. `S04_EXIT` requires `Proof-of-handover hoàn tất 13:52; đóng ca14:10.`.
- **S05 :** `S05_ENTER!1 → S05_MICRO?1 → S05_DISCOVERY?* → S05_ORDINARY_RETURN!1 → S05_EXIT!1`; `S05_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Bỏ qua chuyện phụ không ảnh hưởng audit.`. `S05_DISCOVERY` repeats as a read without time or duplicate clue. `S05_EXIT` requires `Ordinary room beat xong 18:07, S06 notification.`.
- **S06 :** `S06_ENTER!1 → S06_MICRO?1 → S06_DISCOVERY?* → S06_AUDIT_FORM!1 → S06_EXIT!1`; `S06_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Trả lời tối thiểu vẫn mở S07; không gây LEAK tự động.`. `S06_DISCOVERY` repeats as a read without time or duplicate clue. `S06_EXIT` requires `Đã xem form và chọn explicit wait tới20:00.`.
- **S07 :** `S07_ENTER!1 → S07_MICRO?1 → S07_DISCOVERY?* → S07_COMPARE_AND_CHOOSE!1 → S07_EXIT!1`; `S07_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Không so vẫn có audit cụ thể dẫn tới S08; early stop là lựa chọn rõ.`. `S07_DISCOVERY` repeats as a read without time or duplicate clue. `S07_EXIT` requires `Continue và explicit ngủ/chờ tới D+1 08:30, hoặc G0.`.
- **S08 :** `S08_ENTER!1 → S08_MICRO?1 → S08_DISCOVERY?* → S08_PRINT_COMPARE!1 → S08_EXIT!1`; `S08_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Không nhận C18 vẫn có scoped contact và C19 alternate; local lock không erase copy.`. `S08_DISCOVERY` repeats as a read without time or duplicate clue. `S08_EXIT` requires `Core09:35, optional copy09:45; explicit hẹn S09 10:00.`.
- **S09 :** `S09_ENTER!1 → S09_MICRO?1 → S09_DISCOVERY?* → S09_SCOPED_INTAKE!1 → S09_EXIT!1`; `S09_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Chậm disclosure dùng q-relative receipts, không backdate; police A vẫn an toàn.`. `S09_DISCOVERY` repeats as a read without time or duplicate clue. `S09_EXIT` requires `Cuộc gọi15m hoàn tất, travel hospital30m tới10:50/10:55.`.
- **S10 :** `S10_ENTER!1 → S10_MICRO?1 → S10_DISCOVERY?* → S10_FORM_VERSION!1 → S10_EXIT!1`; `S10_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Không gặp Thảo khi C12 đủ vẫn sống; nếu source cuối mất, warning đã có và G1 sau closure.`. `S10_DISCOVERY` repeats as a read without time or duplicate clue. `S10_EXIT` requires `Core11:10/11:15, optional11:20/11:25; S11 quiet point11:30.`.
- **S11 :** `S11_ENTER!1 → S11_MICRO?1 → S11_DISCOVERY?* → S11_TIME_COMPARE!1 → S11_EXIT!1`; `S11_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Sai xếp vẫn có raw records để xem lại miễn phí; progression không đòi quiz.`. `S11_DISCOVERY` repeats as a read without time or duplicate clue. `S11_EXIT` requires `Compare/wait tới12:00; travel Tân Lộ30m tới12:30.`.
- **S12 :** `S12_ENTER!1 → S12_MICRO?1 → S12_DISCOVERY?* → S12_FALSE_APEX_SWAP!1 → S12_EXIT!1`; `S12_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Nếu đã thấy C20, dùng recap ngắn; nếu chưa, phiên bản full inspect vẫn cho cùng fact.`. `S12_DISCOVERY` repeats as a read without time or duplicate clue. `S12_EXIT` requires `Retained verification tới13:00, travel hospital area13:30/micro-set13:35.`.
- **S13 :** `S13_ENTER!1 → S13_MICRO?1 → S13_DISCOVERY?* → S13_TWO_DESKS!1 → S13_EXIT!1`; `S13_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Sai inference không time/route penalty; raw source vẫn được kiểm.`. `S13_DISCOVERY` repeats as a read without time or duplicate clue. `S13_EXIT` requires `Callback/compare13:35–14:00, S14 notice.`.
- **S14 :** `S14_ENTER!1 → S14_MICRO?1 → S14_DISCOVERY?* → S14_RETURN_CHANGED!1 → S14_EXIT!1`; `S14_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Local locks không chặn professional copies; player vẫn chuyển nguồn đã giữ.`. `S14_DISCOVERY` repeats as a read without time or duplicate clue. `S14_EXIT` requires `20m authored notices/action group tới14:20.`.
- **S15 :** `S15_ENTER!1 → S15_MICRO?1 → S15_DISCOVERY?* → S15_CUSTODY_DESK!1 → S15_EXIT!1`; `S15_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Thử lại provenance không cost; missing source thật đóng thì G1/G2/G5 theo cause.`. `S15_DISCOVERY` repeats as a read without time or duplicate clue. `S15_EXIT` requires `Intake/coordination tới15:00; S16 chỉ theo actual E38 hoặc partial path.`.
- **S16 :** `S16_ENTER!1 → S16_MICRO?1 → S16_DISCOVERY?* → S16_THREE_ORIGINS!1 → S16_EXIT!1`; `S16_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Mất Hùng dùng Khoa+logistics original; mất cả managers không record-only magic D1.`. `S16_DISCOVERY` repeats as a read without time or duplicate clue. `S16_EXIT` requires `Actual D verified nếu đủ; scene presentation tới16:25, no forced extra travel.`.
- **S17 [return chosen]:** `S17_ENTER!1 → S17_MICRO?1 → S17_DISCOVERY?* → S17_ROOM_JAM?1 → S17_EXIT!1`; `S17_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Bỏ về trọ vẫn tới S18; nếu door jam, gõ/gọi hoặc chờ authored release không tốn missing-source window bất ngờ.`. `S17_DISCOVERY` repeats as a read without time or duplicate clue. `S17_EXIT` requires `Door released, optional conversation xong; đi police35m nếu cần, hoặc direct S18.`.
- **S18 :** `S18_ENTER!1 → S18_MICRO?1 → S18_DISCOVERY?* → S18_TWO_TRAYS!1 → S18_EXIT!1`; `S18_MICRO` may be missed without blocking `DISCOVERY`; ignored discovery rejoins signature with `Nếu còn last saving path, không resolve; cho player quay lại nguồn hợp lệ.`. `S18_DISCOVERY` repeats as a read without time or duplicate clue. `S18_EXIT` requires `Cinematic ngắn và ending screen sau confirmed terminal state.`.

### Expanded authored graphs (node suffix: `!1` mandatory one-shot, `?1` optional one-shot, `?*` optional repeatable, `[ ]` conditional)

- **S01:** `S01_ENTER!1 → SOCKET_FAULT!1 → LAN_CALLS_NAM!1 → S01_POWER_REPAIR!1 → SOCKET_RETEST?* → S01_EXIT!1`. `CARD_C28?*` branches from LAN_CALLS_NAM and rejoins EXIT; no command proof.
- **S02:** `S02_ENTER!1 → ROOM_SIGN!1 → SEAT_POWER?1 → S02_CLASS_ROUTINE!1 → LISTING_PHONE!1 → S02_EXIT!1`. `C07_HISTORY?*` rejoins LISTING_PHONE.
- **S03:** `S03_ENTER!1 → BALANCE_VIEW?* → JOB_OFFER!1 → [initial decline] JOB_REOPEN?* → S03_JOB_ACCEPT!1 → S03_EXIT!1`. No accept, no S04 travel; return inside offer window.
- **S04:** `S04_ENTER!1 → POUCH_PICKUP!1 → SCANNER_MISMATCH!1 → S04_SCAN_MISMATCH!1 → SEALED_HANDOVER!1 → RECEIPT_1352!1 → S04_EXIT!1`. `LABEL_C04?1` only if visible, rejoins handover.
- **S05:** `S05_ENTER!1 → MEAL!1 → RETURN_HOME!1 → REPAIRED_PLUG?1 → S05_ORDINARY_RETURN!1 → AUDIT_1807!1 → S05_EXIT!1`. `C28_REVISIT?*` rejoins ordinary beat.
- **S06:** `S06_ENTER!1 → PHONE_VIBRATION!1 → FORM_COMPARE?* → S06_AUDIT_FORM!1 → CONFIRM_WAIT!1 → S06_EXIT!1`. No form answer inferred from merely opening notification.
- **S07:** `S07_ENTER!1 → TWO_JOBS_COMPARE?* → MINH_MESSAGE?1 → S07_COMPARE_AND_CHOOSE!1 → [early stop] G0 | [continue] DAY_TRANSITION!1 → S07_EXIT!1`. `MINH_REPORT_RECEIVED` is an independent authored receipt, not the send click.
- **S08:** `S08_ENTER!1 → NOTICE_0925!1 → PRINT_OLD_VERSION!1 → S08_PRINT_COMPARE!1 → [direct copy] C18_RECEIPT_0945?1 | [contact] C18_CONTACT?1 → S08_EXIT!1`. Finance lead is optional and separate.
- **S09:** `S09_ENTER!1 → CALL_1000!1 → SELECT_SOURCED_FIELDS!1 → S09_SCOPED_INTAKE!1 → POLICE_GROUP_RECEIPT_1015!1 → [new lead] NEW_CONTACT?1 → S09_EXIT!1`. Professional requests/receipts run in parallel after sourced fields.
- **S10:** `S10_ENTER!1 → HUYEN_COUNTER!1 → VERSION_TRAY!1 → S10_FORM_VERSION!1 → [C12 complete] B_VERIFY | [C12 gap] THAO_C15?1 → S10_EXIT!1`. B_VERIFY requires real receipt/authentication; optional Thảo is only available before11:30.
- **S11:** `S11_ENTER!1 → VU_CALLBACK!1 → THREE_TIMES_COMPARE?* → S11_TIME_COMPARE!1 → S11_EXIT!1`; incorrect private ordering returns to compare without cost.
- **S12:** `S12_ENTER!1 → [C20 seen] FAST_RECAP | [unseen] AUTHORITY_LOG?* → S12_FALSE_APEX_SWAP!1 → C22_RECEIPT_1300!1 → S12_EXIT!1`. Repeat Tuấn/Hùng actions are separate priced choices after warning.
- **S13:** `S13_ENTER!1 → TWO_ESCALATIONS!1 → SOURCE_SCOPE_COMPARE?* → S13_TWO_DESKS!1 → [raw complete] POLICE_X_RISK | [raw incomplete] X_PENDING → S13_EXIT!1`; private wrong answer rejoins either branch.
- **S14:** `S14_ENTER!1 → ACCESS_VARIANTS!1 → NOTICE_1400!1 → S14_RETURN_CHANGED!1 → [actual report] WARN_ACCELERATED?1 | [no report] BASELINE → S14_EXIT!1`. Accelerate only if OT feasibility check passes.
- **S15:** `S15_ENTER!1 → EVIDENCE_TRAY!1 → SOURCE_RECEIPTS!1 → S15_CUSTODY_DESK!1 → [E38 true] S16_ENTER | [path open] CONTINUE_SOURCE | [qualified N3 abandon] G3 | [terminal] S18_ENTER`.
- **S16:** `S16_ENTER!1 → MANAGER_REQUEST!1 + OTHER_BRANCH_REQUEST!1 + BROKER_REQUEST!1 → THREE_ORIGINAL_RECEIPTS?1 → S16_THREE_ORIGINS!1 → [verified before lock] C4 | [source missing] D_PARTIAL → S16_EXIT!1`. Requests start only after actual E38, independent receipts/authentication as §critical below.
- **S17:** `[return chosen] S17_ENTER!1 → LEGITIMATE_ERRAND!1 → DOOR_JAM!1 → HANDLE_OR_KNOCK?* → S17_ROOM_JAM?1 → LATCH_RESET_OR_LAN!1 → S17_EXIT!1`; optional notebook pages never release the door. `[bypass] S16_EXIT → S18_ENTER`.
- **S18:** `S18_ENTER!1 → RESTORE_RECEIPTS!1 → VERIFY_X_AND_D!1 → [path open] CONTINUE_SOURCE | [terminal] S18_TWO_TRAYS!1 → ENDING_SNAPSHOT!1 → CREDITS`. Terminal branch uses P4 order; no new clue.

**Conditional edges:** S07 early stop→G0, continue→S08; S08 direct C18 or scoped Vũ contact→S09; S10 C12 or C15→S11; S12 recap or full audit→S13; S13 wrong private inference still→S14; S14 actual leak or baseline closure→S15; S15 actual E38→S16, otherwise keep saving source path until real closure; S16 Hùng/C33 or Khoa/C34 and exact broker annex→optional S17 or S18; S17 door released→S18, bypass S16→S18; S18 open saving path loops to source intake, confirmed terminal goes to ending. No edge depends on C28 or early Nam identification.

## Event cards

### S01_POWER_REPAIR

- **EVENT ID:** `S01_POWER_REPAIR`; **SCENE:** S01; **LOCATION:** HUB B/phòng Bắc; **EVENT CLASS:** SET_PIECE. `S01_MICRO` is MICRO and `S01_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S01_POWER_REPAIR: player giữ góc nhìn và thử điện trước/sau sửa, không cắt sang exposition. Khi S17 recontextualizes Nam, vật cũ vẫn chỉ là quan hệ nghề nghiệp.
- **PRECONDITIONS:** D0_START; room key pending. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** Bắc thử ổ FAULT hoặc Lan gọi Nam; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Hành lang có tiếng quạt, ổ điện chập chờn trong phòng Bắc, góc Nam sửa đồ nằm trong tầm nhìn nhưng không được đóng khung đáng ngờ.
- **PLAYER LURE:** Đèn bàn chớp khi Bắc cắm ổ kéo; tiếng Lan gọi Nam từ hành lang.
- **PLAYER ACTION:** Player đặt vali, thử công tắc/ổ, mở cửa cho Nam; có thể liếc card cũ C28 hoặc đọc hợp đồng thuê.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Lan: cửa phòng→công tơ; Nam: bàn sửa→ổ→bàn sửa; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Lan kiểm công tơ; Nam tiếp tục sửa món khác nếu Bắc chưa ra.
- **EVENT SEQUENCE:** `ENTER` checks C28_SEEN, S01_SOCKET_WORKING; `MICRO` plays Tiếng quạt ngừng rồi chạy; điện thoại báo số dư/tiền trọ.; optional/repeatable `DISCOVERY` reveals Lỗi điện là việc thật; Nam giúp đúng nghề. C27 chỉ background; C28 optional không chứng minh current command.; player commits Bắc thử ổ FAULT hoặc Lan gọi Nam; `SIGNATURE` performs Lan đưa chìa sau khi Bắc nhận phòng; Nam tới vì lời Lan gọi, sửa ổ và về góc đồ.; `EXIT` only after Đồ được đặt, điện ổn, player xác nhận rời trọ 08:35.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Ổ chuyển FAULT→WORKING do Nam xử lý; đồ cũ vẫn ở đó, không tự xuất hiện.
- **AUDIO:** Tiếng quạt ngừng rồi chạy; điện thoại báo số dư/tiền trọ. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** socket, room door, repair table card, phone. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C27 observation; C28 optional relationship only The exact player-facing field is in FULL_SCRIPT S01; no automatic inference from ID.
- **STATE READS:** `C28_SEEN, S01_SOCKET_WORKING` plus source access/willingness and event completion stage.
- **STATE WRITES:** `S01_SOCKET_WORKING; C27_OBSERVED; optional C28_SEEN` only on actual typed action/source event, with `EVENT_DONE:S01_POWER_REPAIR` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Lỗi điện là việc thật; Nam giúp đúng nghề. C27 chỉ background; C28 optional không chứng minh current command. Seen/understood flags separate; optional detail: C28/card Tân Lộ cũ và một cử chỉ tử tế C29.
- **POLICE CUSTODY EFFECT:** none. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** none. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C27 observation; C28 optional relationship only; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** S01 ordinary core65m once; travel25m after exit; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** socket FAULT/WORKING, Nam route stage, key, optional C28; never duplicate repair. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C28/card Tân Lộ cũ và một cử chỉ tử tế C29. never grants its observation; if signature is mandatory, use Không xem card vẫn tới lớp; thao tác thử ổ có hint không tốn thời gian. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Không xem card vẫn tới lớp; thao tác thử ổ có hint không tốn thời gian.
- **RETURN PAYOFF:** Khi S17 recontextualizes Nam, vật cũ vẫn chỉ là quan hệ nghề nghiệp.
- **NEXT EVENTS:** S02_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** DoorInteractable, socket state, Nam route, phone balance, C27/C28 observation flags. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** socket, room door, repair table card, phone; Hợp đồng trọ/phone số dư; card cũ Tân Lộ chỉ nếu inspect; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S02_CLASS_ROUTINE

- **EVENT ID:** `S02_CLASS_ROUTINE`; **SCENE:** S02; **LOCATION:** HUB A/lớp; **EVENT CLASS:** SET_PIECE. `S02_MICRO` is MICRO and `S02_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S02_CLASS_ROUTINE: player tìm đúng phòng và chỗ học trong sinh hoạt đang diễn ra, áp lực tiền hiện qua thao tác điện thoại. S07 so ca bình thường với assignment mới.
- **PRECONDITIONS:** S01_EXIT. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** Player tìm phòng từ bảng lớp; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Bảng phòng học, ghế có ổ hỏng, file bài giảng và bảng thông báo việc làm trong một ngày bình thường.
- **PLAYER LURE:** Linh chỉ chỗ ngồi có ổ điện; thông báo chi phí sáng màn hình, Minh đưa link công việc.
- **PLAYER ACTION:** Player tìm lớp, đổi chỗ, chụp bài hoặc nhận file; tự mở listing khi cần tiền.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Linh: ghế→bảng; Minh: bàn sau→hành lang; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Linh học, Minh đi ngang rồi nhắn link; không nhân vật nào biết crime.
- **EVENT SEQUENCE:** `ENTER` checks C07_SEEN; `MICRO` plays Ổ cạnh ghế tắt; điện thoại rung bởi deadline lớp.; optional/repeatable `DISCOVERY` reveals Linh phân biệt thấy với đoán qua bài tập; Minh từng nhận ca thường C07 nếu hỏi/xem lịch sử được phép.; player commits Player tìm phòng từ bảng lớp; `SIGNATURE` performs Giờ học và bữa trưa tiến theo nhóm hành động đã định, không vì đọc UI lâu.; `EXIT` only after Lớp/bữa trưa kết thúc 11:15; listing có thể mở.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Thông báo chi phí nằm lại trong phone; lớp tan và bảng việc vẫn có.
- **AUDIO:** Ổ cạnh ghế tắt; điện thoại rung bởi deadline lớp. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** room sign, seating, class file, phone listing. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C01 listing; C07 optional ordinary job history The exact player-facing field is in FULL_SCRIPT S02; no automatic inference from ID.
- **STATE READS:** `C07_SEEN` plus source access/willingness and event completion stage.
- **STATE WRITES:** `S02_CLASS_DONE; optional C07_SEEN; C01_LISTING_AVAILABLE` only on actual typed action/source event, with `EVENT_DONE:S02_CLASS_ROUTINE` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Linh phân biệt thấy với đoán qua bài tập; Minh từng nhận ca thường C07 nếu hỏi/xem lịch sử được phép. Seen/understood flags separate; optional detail: C07 lịch sử ca cũ, không là chứng cứ mạng lưới.
- **POLICE CUSTODY EFFECT:** none. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** none. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C01 listing; C07 optional ordinary job history; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** class/meal135m once; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** class beat, listing visibility, optional C07. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C07 lịch sử ca cũ, không là chứng cứ mạng lưới. never grants its observation; if signature is mandatory, use Bỏ qua mọi thoại tùy chọn vẫn có link và lý do xem việc. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Bỏ qua mọi thoại tùy chọn vẫn có link và lý do xem việc.
- **RETURN PAYOFF:** S07 so ca bình thường với assignment mới.
- **NEXT EVENTS:** S03_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Class schedule, interactable seating, phone listing, optional C07. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** room sign, seating, class file, phone listing; Lịch học, bảng việc và tin Linh; không plot record; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S03_JOB_ACCEPT

- **EVENT ID:** `S03_JOB_ACCEPT`; **SCENE:** S03; **LOCATION:** HUB A/khu ăn; **EVENT CLASS:** SET_PIECE. `S03_MICRO` is MICRO and `S03_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S03_JOB_ACCEPT: quyết định được đặt trong ngân sách và lịch học có thể xem, không lời độc thoại lý giải. S07/S08 so lịch sử với routing của ca này.
- **PRECONDITIONS:** S02_CLASS_DONE; job window open. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** Minh gửi TL-2604-117; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Nhiều listing bình thường; ca TL-2604-117 có tiền nhỉnh hơn vì khung giờ và proof-of-handover.
- **PLAYER LURE:** Minh chuyển link đúng lúc Bắc xem số dư; phone rung cạnh hóa đơn bữa ăn.
- **PLAYER ACTION:** Player so giờ học/tiền/đầu việc, chấp nhận ca hoặc do dự; không ai gọi chọn riêng Bắc.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Minh: cạnh bàn ăn→rời đi khi link gửi; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Minh trở lại việc riêng, không theo player điều tra.
- **EVENT SEQUENCE:** `ENTER` checks JOB_ACCEPTED, budget; `MICRO` plays Màn hình số dư; app báo hạn nhận ca.; optional/repeatable `DISCOVERY` reveals C02 là assignment và nhóm khách y tế, chỉ bề mặt công việc.; player commits Minh gửi TL-2604-117; `SIGNATURE` performs Nhận ca phát assignment; xác nhận di chuyển tính authored 34m nhóm và 35m tới Tân Lộ.; `EXIT` only after Job accepted; đi Tân Lộ theo travel card tới12:24.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Assignment vào lịch sử; trạng thái job ACCEPTED một lần.
- **AUDIO:** Màn hình số dư; app báo hạn nhận ca. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** phone listing, budget, schedule. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C02 assignment only The exact player-facing field is in FULL_SCRIPT S03; no automatic inference from ID.
- **STATE READS:** `JOB_ACCEPTED, budget` plus source access/willingness and event completion stage.
- **STATE WRITES:** `JOB_ACCEPTED; C02_OBSERVED; job original snapshot` only on actual typed action/source event, with `EVENT_DONE:S03_JOB_ACCEPT` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** C02 là assignment và nhóm khách y tế, chỉ bề mặt công việc. Seen/understood flags separate; optional detail: C07 đối chiếu ca cũ nếu đã xem.
- **POLICE CUSTODY EFFECT:** none. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** none. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C02 assignment only; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** accept group34m once; travel35m + check-in6m; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** accept confirmation/cost once and original job listing. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C07 đối chiếu ca cũ nếu đã xem. never grants its observation; if signature is mandatory, use Đã từ chối ban đầu vẫn có một lần nhận lại trong window; không rơi vào bế tắc. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Đã từ chối ban đầu vẫn có một lần nhận lại trong window; không rơi vào bế tắc.
- **RETURN PAYOFF:** S07/S08 so lịch sử với routing của ca này.
- **NEXT EVENTS:** S04_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Phone job app, budget card, once-charge accept and travel. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** phone listing, budget, schedule; TL-2604-117, đầu nhận y tế, proof-of-handover, tiền và khung giờ; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S04_SCAN_MISMATCH

- **EVENT ID:** `S04_SCAN_MISMATCH`; **SCENE:** S04; **LOCATION:** Tân Lộ/đầu nhận; **EVENT CLASS:** SET_PIECE. `S04_MICRO` is MICRO and `S04_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S04_SCAN_MISMATCH: player tự đưa gói vào scanner và thấy hai trường không khớp rồi nhân viên sửa bằng thao tác thường. S06 audit và S08 reclassification giải nghĩa mismatch.
- **PRECONDITIONS:** JOB_ACCEPTED. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** Player presents sealed pouch at scan; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Quầy dispatch với nhiều gói thật, máy quét, printer, nhân viên bận; pouch kín đi qua luồng thường.
- **PLAYER LURE:** Scanner báo mismatch nhẹ, nhãn routing có mép dán lại, giấy proof-of-handover ló khỏi khay.
- **PLAYER ACTION:** Player nhận pouch, giữ nguyên niêm, giao và xem lịch sử/biên nhận sau scan; có thể nhìn C04 nếu nhãn thực sự lộ.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Tuấn: dispatch board; receiver: counter; no pursuit; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Tuấn phân ca, đầu nhận xác minh, không ai giải thích conspiracy.
- **EVENT SEQUENCE:** `ENTER` checks C04_LABEL_VISIBLE, C03_OBSERVED; `MICRO` plays Máy quét beep hai nhịp; printer kéo giấy; xe đẩy đi ngang.; optional/repeatable `DISCOVERY` reveals C03 đầu nhận/account family; mismatch không phải bằng chứng crime, C04 chỉ từ vật/ảnh nhìn rõ nhãn.; player commits Player presents sealed pouch at scan; `SIGNATURE` performs Nhân viên xử lý mã hợp lệ theo quy trình; Tuấn đi qua kiểm công việc khác, không chọn Bắc.; `EXIT` only after Proof-of-handover hoàn tất 13:52; đóng ca14:10.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Job DELIVERED, C03 original13:52 lưu lịch sử; later observed_at khi player mở lại, không rewrite source time.
- **AUDIO:** Máy quét beep hai nhịp; printer kéo giấy; xe đẩy đi ngang. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** scanner, pouch, routing label, receipt, phone history. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C03 transaction lead; C04 only visible original label/photo The exact player-facing field is in FULL_SCRIPT S04; no automatic inference from ID.
- **STATE READS:** `C04_LABEL_VISIBLE, C03_OBSERVED` plus source access/willingness and event completion stage.
- **STATE WRITES:** `JOB_DELIVERED; C03 original_at13:52; optional C04_OBSERVED` only on actual typed action/source event, with `EVENT_DONE:S04_SCAN_MISMATCH` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** C03 đầu nhận/account family; mismatch không phải bằng chứng crime, C04 chỉ từ vật/ảnh nhìn rõ nhãn. Seen/understood flags separate; optional detail: Dấu routing C04 và tiếng đầu nhận hỏi mã.
- **POLICE CUSTODY EFFECT:** none. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** E23 report later, not from player seeing mismatch. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C03 transaction lead; C04 only visible original label/photo; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** pickup24m/travel30m/handover28m/close18m once; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** scanner resolved, delivery status, original/observed times; no duplicate C03. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional Dấu routing C04 và tiếng đầu nhận hỏi mã. never grants its observation; if signature is mandatory, use Không inspect nhãn vẫn có biên nhận/history và audit. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Không inspect nhãn vẫn có biên nhận/history và audit.
- **RETURN PAYOFF:** S06 audit và S08 reclassification giải nghĩa mismatch.
- **NEXT EVENTS:** S05_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Scanner, printer, sealed pouch, receipt UI, persistent original/observed timestamps. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** scanner, pouch, routing label, receipt, phone history; Receipt client family/group; no opened pouch document; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S05_ORDINARY_RETURN

- **EVENT ID:** `S05_ORDINARY_RETURN`; **SCENE:** S05; **LOCATION:** quán gần đầu nhận→HUB B; **EVENT CLASS:** SET_PIECE. `S05_MICRO` is MICRO and `S05_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S05_ORDINARY_RETURN: một đoạn thở do player điều khiển, căn phòng cũ thay âm và vị trí vật để tạo cảm giác sống. S17 cùng hành lang đổi nghĩa bằng hiểu biết player, không cần biến Nam thành quái.
- **PRECONDITIONS:** JOB_DELIVERED. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** Player commits meal/study and returns home; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Quán ăn và phòng trọ sinh hoạt bình thường; thanh toán job còn PENDING.
- **PLAYER LURE:** Phone đợi tiền và tin Linh; Nam trả món đồ điện hoặc Lan nhắc chỗ để đồ.
- **PLAYER ACTION:** Player chọn bữa rẻ, xem bài, đi về; có thể nhận món Nam sửa và đặt lại.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Lan: stair/gate; Nam: repair table→returns repaired object; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Nam sửa đồ, Lan làm việc nhà, không chất vấn Tân Lộ.
- **EVENT SEQUENCE:** `ENTER` checks C28_SEEN, S01_SOCKET_WORKING; `MICRO` plays Âm quán ăn thay bằng tiếng ngõ; quạt phòng chạy; phone không báo tiền.; optional/repeatable `DISCOVERY` reveals Nam tử tế trong chuyện nhỏ C29; khoản pending chưa phải dấu tội phạm.; player commits Player commits meal/study and returns home; `SIGNATURE` performs Bữa/việc học cho tới17:30 rồi travel về trọ; audit đến sau ordinary beat18:07.; `EXIT` only after Ordinary room beat xong 18:07, S06 notification.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Vật đã sửa chuyển về phòng Bắc, payment PENDING; không tăng BARC.
- **AUDIO:** Âm quán ăn thay bằng tiếng ngõ; quạt phòng chạy; phone không báo tiền. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** meal menu, phone payment, repaired plug, study file. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C29 character; no major proof The exact player-facing field is in FULL_SCRIPT S05; no automatic inference from ID.
- **STATE READS:** `C28_SEEN, S01_SOCKET_WORKING` plus source access/willingness and event completion stage.
- **STATE WRITES:** `PAYMENT_PENDING; S05_ORDINARY_BEAT_DONE` only on actual typed action/source event, with `EVENT_DONE:S05_ORDINARY_RETURN` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Nam tử tế trong chuyện nhỏ C29; khoản pending chưa phải dấu tội phạm. Seen/understood flags separate; optional detail: Một câu nói đời thường của Nam/Lan.
- **POLICE CUSTODY EFFECT:** none. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** none; speaking employer name to Nam at N1 no new leak. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C29 character; no major proof; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** meal/move20m + ordinary180m + home travel35m + room beat2m once; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** meal/travel/room beat once, returned plug, audit queued. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional Một câu nói đời thường của Nam/Lan. never grants its observation; if signature is mandatory, use Bỏ qua chuyện phụ không ảnh hưởng audit. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Bỏ qua chuyện phụ không ảnh hưởng audit.
- **RETURN PAYOFF:** S17 cùng hành lang đổi nghĩa bằng hiểu biết player, không cần biến Nam thành quái.
- **NEXT EVENTS:** S06_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Ambient zone, repaired prop A/B, payment flag, authored meal/travel. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** meal menu, phone payment, repaired plug, study file; Payment “Đối soát — đang xử lý”; audit notification only at18:07; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S06_AUDIT_FORM

- **EVENT ID:** `S06_AUDIT_FORM`; **SCENE:** S06; **LOCATION:** HUB B/phòng Bắc; **EVENT CLASS:** SET_PIECE. `S06_MICRO` is MICRO and `S06_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S06_AUDIT_FORM: player đối chiếu record thay cho nghe NPC kể toàn bộ lỗi. S07 curiosity bắt đầu từ bất nhất cụ thể.
- **PRECONDITIONS:** S05_ORDINARY_BEAT_DONE at18:07. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** audit notification opens; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Trong phòng, job app bất ngờ yêu cầu đối lại thời gian/đầu nhận, payment giữ chờ.
- **PLAYER LURE:** Phone rung hai lần; form hỏi field mà player vừa thấy scanner xử lý.
- **PLAYER ACTION:** Player mở history, so biên nhận, trả lời chỉ phần trực tiếp thấy; có thể gọi Tuấn theo option có cost.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Tuấn phone only for actual bounded question; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Tuấn đang xử lý audit khác; chỉ phản hồi câu hỏi có trong work ticket.
- **EVENT SEQUENCE:** `ENTER` checks JOB_DELIVERED,C03_OBSERVED; `MICRO` plays Tin payment đổi trạng thái; tiếng khu trọ tiếp tục ngoài cửa.; optional/repeatable `DISCOVERY` reveals Audit hướng tới routing; Tuấn phòng thủ trong giới hạn vận hành, không thú nhận hoặc đọc notebook.; player commits audit notification opens; `SIGNATURE` performs Form xác nhận sau S06 15m; explicit chờ kết quả tới20:00 hiển thị trước commit.; `EXIT` only after Đã xem form và chọn explicit wait tới20:00.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Payment HOLD, audit receipt; phone giữ original job history.
- **AUDIO:** Tin payment đổi trạng thái; tiếng khu trọ tiếp tục ngoài cửa. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** phone audit form, C03 history. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** audit field mismatch; no new proof The exact player-facing field is in FULL_SCRIPT S06; no automatic inference from ID.
- **STATE READS:** `JOB_DELIVERED,C03_OBSERVED` plus source access/willingness and event completion stage.
- **STATE WRITES:** `AUDIT_FORM_REPLIED; PAYMENT_HOLD; AUDIT_WAIT_COMMITTED` only on actual typed action/source event, with `EVENT_DONE:S06_AUDIT_FORM` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Audit hướng tới routing; Tuấn phòng thủ trong giới hạn vận hành, không thú nhận hoặc đọc notebook. Seen/understood flags separate; optional detail: Một field scan bất thường đã quan sát ở S04.
- **POLICE CUSTODY EFFECT:** none. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** none from private form. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** audit field mismatch; no new proof; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** S06 core15m once; explicit wait98m to20:00 once; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** form answer, phone notification and wait charged once. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional Một field scan bất thường đã quan sát ở S04. never grants its observation; if signature is mandatory, use Trả lời tối thiểu vẫn mở S07; không gây LEAK tự động. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Trả lời tối thiểu vẫn mở S07; không gây LEAK tự động.
- **RETURN PAYOFF:** S07 curiosity bắt đầu từ bất nhất cụ thể.
- **NEXT EVENTS:** S07_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Phone diff UI, audit flags, Tuấn response scope, once-charge wait. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** phone audit form, C03 history; “Xác minh ca TL-2604-117: giờ nhận, đầu nhận, mã phân loại; thanh toán chờ đối soát.”; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S07_COMPARE_AND_CHOOSE

- **EVENT ID:** `S07_COMPARE_AND_CHOOSE`; **SCENE:** S07; **LOCATION:** HUB B/phòng Bắc; **EVENT CLASS:** SET_PIECE. `S07_MICRO` is MICRO and `S07_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S07_COMPARE_AND_CHOOSE: thao tác so ca rồi chọn kênh tin trước day transition. S14 nếu có leak, timestamp report khớp cửa đóng, không auto betrayal.
- **PRECONDITIONS:** AUDIT_WAIT_COMMITTED at20:00. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** compare C07/normal job to current assignment, or confirm stop; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Phòng yên, lịch sử ca Minh C07 và TL-2604-117 hiện trong app; hành lang vẫn sống.
- **PLAYER LURE:** Hai dòng assignment có nhãn khác nhau; Minh nhắn hỏi đã nhận tiền chưa.
- **PLAYER ACTION:** Player đặt hai record cạnh nhau; hỏi Minh chung hoặc gửi exact screenshot/theory. Confirm stop nếu muốn G0.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Minh phone; Lan lock gate; Nam uninformed; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Minh trả lời theo thứ được hỏi; Lan khóa cổng, Nam không có magic awareness.
- **EVENT SEQUENCE:** `ENTER` checks C07_SEEN,BARC, disclosed_payloads; `MICRO` plays Tin nhắn rung; đèn hành lang tắt theo giờ.; optional/repeatable `DISCOVERY` reveals Khác biệt ca không chứng minh crime; disclosure ledger chỉ ghi phần Bắc thật sự gửi.; player commits compare C07/normal job to current assignment, or confirm stop; `SIGNATURE` performs Nếu Minh hỏi hộ company, E26 chỉ sau actual message/report receipt; phone gửi không đồng nghĩa Khải/Nam biết ngay.; `EXIT` only after Continue và explicit ngủ/chờ tới D+1 08:30, hoặc G0.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Disclosure payload hoặc NONE, BARC theo report thật; G0 chỉ nếu early stop đủ điều kiện.
- **AUDIO:** Tin nhắn rung; đèn hành lang tắt theo giờ. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** two-record viewer, message composer, exit choice. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C07 comparison ordinary, no case proof The exact player-facing field is in FULL_SCRIPT S07; no automatic inference from ID.
- **STATE READS:** `C07_SEEN,BARC, disclosed_payloads` plus source access/willingness and event completion stage.
- **STATE WRITES:** `optional MINH_DISCLOSURE payload/receipt; EARLY_STOP or D1_CONTINUE` only on actual typed action/source event, with `EVENT_DONE:S07_COMPARE_AND_CHOOSE` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Khác biệt ca không chứng minh crime; disclosure ledger chỉ ghi phần Bắc thật sự gửi. Seen/understood flags separate; optional detail: C07 không bắt buộc, so tối thiểu từ field job app.
- **POLICE CUSTODY EFFECT:** none. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** only after actual Minh→company→Khải received report with exact payload; no auto N3. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C07 comparison ordinary, no case proof; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** compare/UI0; contact group20m, extra company call5m if chosen; explicit sleep to08:30; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** exact message/receipt ledger, G0 choice or D+1 transition once. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C07 không bắt buộc, so tối thiểu từ field job app. never grants its observation; if signature is mandatory, use Không so vẫn có audit cụ thể dẫn tới S08; early stop là lựa chọn rõ. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Không so vẫn có audit cụ thể dẫn tới S08; early stop là lựa chọn rõ.
- **RETURN PAYOFF:** S14 nếu có leak, timestamp report khớp cửa đóng, không auto betrayal.
- **NEXT EVENTS:** S08_ENTER or G0; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Two-record compare UI, disclosure receipt ledger, early resolver, save at day transition. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** two-record viewer, message composer, exit choice; Normal shift vs TL-2604-117 fields; sent text persisted literally; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S08_PRINT_COMPARE

- **EVENT ID:** `S08_PRINT_COMPARE`; **SCENE:** S08; **LOCATION:** Tân Lộ/dispatch; **EVENT CLASS:** SET_PIECE. `S08_MICRO` is MICRO and `S08_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S08_PRINT_COMPARE: player tự đặt bản Internal và Standard song song trong khoảng cửa còn mở. S09 Vũ bắt đầu requests từ actual group/contact, S12 verify retained copies.
- **PRECONDITIONS:** D+1 arrival09:00, payment ticket. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** printer exposes old Internal/Priority version after legitimate query; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Máy printer và terminal dispatch mở cùng job; Đức cầm bản snapshot cá nhân; notice đóng worker access11:00.
- **PLAYER LURE:** Printer trả một bản Internal/Priority cũ trong khi app hiển thị Standard; Đức chú ý Bắc nhìn thấy.
- **PLAYER ACTION:** Player so bản in C17 với assignment, hỏi quyền classification; 09:35 có thể nhận C18 copy từ Đức trong10m hoặc giữ contact/deadline đưa Vũ.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Đức: workstation→offer at09:30; Tuấn dispatch other jobs; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Đức tránh lộ danh tính nhưng giữ private phone copy; Tuấn vận hành không tự reclassify.
- **EVENT SEQUENCE:** `ENTER` checks C17_OBSERVED,C18_LOCAL_RECEIVED, warning09:25; `MICRO` plays Printer feed; badge beep; worker app quyền truy cập đổi màu ở giờ đóng.; optional/repeatable `DISCOVERY` reveals E19 reclassification D−1 bởi tầng trên Tuấn; không suy từ pattern rằng Đức biết organ crime.; player commits printer exposes old Internal/Priority version after legitimate query; `SIGNATURE` performs Warning09:25 trước closure; Đức offer copy thực tế từ09:30, không chờ scene S12.; `EXIT` only after Core09:35, optional copy09:45; explicit hẹn S09 10:00.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** C17 observed, C18 local receipt09:45 nếu chọn; notice và contact tồn tại đến11:00.
- **AUDIO:** Printer feed; badge beep; worker app quyền truy cập đổi màu ở giờ đóng. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** printer output, version compare, Đức phone-copy offer, finance lead card. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C17 reclassification; C18 independent operations if original snapshot copied The exact player-facing field is in FULL_SCRIPT S08; no automatic inference from ID.
- **STATE READS:** `C17_OBSERVED,C18_LOCAL_RECEIVED, warning09:25` plus source access/willingness and event completion stage.
- **STATE WRITES:** `C17_OBSERVED; WARN_WORKER_0925; optional C18_LOCAL_RECEIVED09:45 and contact/deadline` only on actual typed action/source event, with `EVENT_DONE:S08_PRINT_COMPARE` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** E19 reclassification D−1 bởi tầng trên Tuấn; không suy từ pattern rằng Đức biết organ crime. Seen/understood flags separate; optional detail: Bounded finance lead Yến; alternate police route nếu không nhận trực tiếp.
- **POLICE CUSTODY EFFECT:** none until S09 actual share. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** no report merely from reading. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C17 reclassification; C18 independent operations if original snapshot copied; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** core35m once; optional C18 direct10m once; travel30m already charged; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** printer print-once, C17 observed, warning receipt, C18 copy/custodian/time independently. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional Bounded finance lead Yến; alternate police route nếu không nhận trực tiếp. never grants its observation; if signature is mandatory, use Không nhận C18 vẫn có scoped contact và C19 alternate; local lock không erase copy. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Không nhận C18 vẫn có scoped contact và C19 alternate; local lock không erase copy.
- **RETURN PAYOFF:** S09 Vũ bắt đầu requests từ actual group/contact, S12 verify retained copies.
- **NEXT EVENTS:** S09_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Versioned document UI, printer, source availability/warning, C18 custody. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** printer output, version compare, Đức phone-copy offer, finance lead card; Internal/Priority old vs Standard new; worker access11:00 and finance12:30 notice; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S09_SCOPED_INTAKE

- **EVENT ID:** `S09_SCOPED_INTAKE`; **SCENE:** S09; **LOCATION:** Tân Lộ/phone police; **EVENT CLASS:** SET_PIECE. `S09_MICRO` is MICRO and `S09_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S09_SCOPED_INTAKE: player gửi source có timestamp và thấy police receipt tách khỏi queued query. S10 review và S12 C22 matched từ đúng request sáng.
- **PRECONDITIONS:** C17 source available; appointment10:00. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** call connects and player submits exact selected source; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Bắc đứng ở Tân Lộ; trên phone có assignment, receipt và bản in; Vũ ở đầu dây trong micro-set.
- **PLAYER LURE:** Tin hẹn từ Vũ và trường đầu nhận Minh Trạch khiến cuộc gọi có mục tiêu.
- **PLAYER ACTION:** Player chọn gửi original record/contact/group/deadline và phân loại thấy hay suy; optional disclose lead mới có 5m cost.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Vũ police micro-set; only scoped follow-ups; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Vũ làm việc song song, không đợi Bắc đi từng nơi; Nam không nghe private call.
- **EVENT SEQUENCE:** `ENTER` checks C18_LOCAL_RECEIVED, source_contact_disclosed, C17_OBSERVED; `MICRO` plays Phone ring; message acknowledgment; tín hiệu office nền.; optional/repeatable `DISCOVERY` reveals Vũ đã có vụ Phúc A=2 từ E28; anh hỏi raw scope, không kể toàn vụ; request B/C khởi từ actual payload.; player commits call connects and player submits exact selected source; `SIGNATURE` performs C17/group payload receipt10:15; Vũ contact Đức10:25/receipt10:35 nếu đủ contact và tự request hospital review khi group có.; `EXIT` only after Cuộc gọi15m hoàn tất, travel hospital30m tới10:50/10:55.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Police custody mới chỉ cho actual received/authenticated sources; warnings hospital11:30/finance12:30.
- **AUDIO:** Phone ring; message acknowledgment; tín hiệu office nền. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** phone source selector, attachment provenance, receipt status. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C17/group bridge; C18/C19 only after actual originals/auth The exact player-facing field is in FULL_SCRIPT S09; no automatic inference from ID.
- **STATE READS:** `C18_LOCAL_RECEIVED, source_contact_disclosed, C17_OBSERVED` plus source access/willingness and event completion stage.
- **STATE WRITES:** `POLICE_GROUP_RECEIPT10:15; conditional C18 request/contact/receipt/auth; optional C19 lead` only on actual typed action/source event, with `EVENT_DONE:S09_SCOPED_INTAKE` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Vũ đã có vụ Phúc A=2 từ E28; anh hỏi raw scope, không kể toàn vụ; request B/C khởi từ actual payload. Seen/understood flags separate; optional detail: C18/C19 scoped leads có thể gửi trong kênh hợp lệ.
- **POLICE CUSTODY EFFECT:** A=2 already E28; C17 group10:15; C18 contact10:25/receipt10:35/auth10:45 if disclosed; C19 contact10:40/receipt10:50/auth11:00 if bounded lead. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** phone to Vũ secure, no organization report. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C17/group bridge; C18/C19 only after actual originals/auth; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** call15m once, genuinely new lead5m each, then travel30m; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** request, receipt and authentication separately; police A persists. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C18/C19 scoped leads có thể gửi trong kênh hợp lệ. never grants its observation; if signature is mandatory, use Chậm disclosure dùng q-relative receipts, không backdate; police A vẫn an toàn. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Chậm disclosure dùng q-relative receipts, không backdate; police A vẫn an toàn.
- **RETURN PAYOFF:** S10 review và S12 C22 matched từ đúng request sáng.
- **NEXT EVENTS:** S10_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Phone source-selection, receipt ledger, parallel police timers, q-relative schedule. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** phone source selector, attachment provenance, receipt status; Police receipt lists each original custodian, record time and transmitted fields; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S10_FORM_VERSION

- **EVENT ID:** `S10_FORM_VERSION`; **SCENE:** S10; **LOCATION:** Minh Trạch/quầy review; **EVENT CLASS:** SET_PIECE. `S10_MICRO` is MICRO and `S10_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S10_FORM_VERSION: player tự đối chiếu hai version; nhân viên chỉ phản ứng đúng phần đã hỏi. S11 thời điểm review D−12 đặt bên cạnh Phúc/job.
- **PRECONDITIONS:** actual group-specific police request; arrive10:50 or10:55. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** printer/version tray presents old and narrowed review; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Quầy Huyền có khay form hai version; hành lang công khai, không vào phòng hạn chế.
- **PLAYER LURE:** Printer nhả bản scope thu hẹp, version cũ còn ở khay được phép xem khi Vũ đã request đúng nhóm.
- **PLAYER ACTION:** Player so consent và review tại quầy theo quyền cho phép; có thể hỏi Thảo về phần bà trực tiếp xử lý nếu C12 thiếu.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Huyền at legal counter; Thảo available before11:30; Khoa elsewhere; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Huyền tiếp bệnh án hợp pháp; Thảo chỉ có mặt trong window, Khoa ở cell riêng.
- **EVENT SEQUENCE:** `ENTER` checks C11_POLICE_RECEIVED,C12_POLICE_RECEIVED,C15_OPTION, WARN_HOSPITAL; `MICRO` plays Hành lang bớt tiếng khi cửa khép; máy in và bánh xe đẩy.; optional/repeatable `DISCOVERY` reveals C11 discrepancy về money/withdrawal; C12 receipt Khoa biết và vẫn giữ consent, hoặc C15 firsthand cùng case. Huyền không tự biết cả mạng.; player commits printer/version tray presents old and narrowed review; `SIGNATURE` performs Vũ nhận originals11:10, authenticate11:20 nếu actual request; optional Thảo10m tới11:20/11:25.; `EXIT` only after Core11:10/11:15, optional11:20/11:25; S11 quiet point11:30.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Document version/scope hiển thị; police B chỉ tăng sau original fact/authentication; local11:30 không erase receipt.
- **AUDIO:** Hành lang bớt tiếng khi cửa khép; máy in và bánh xe đẩy. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** two-version consent/review UI, request receipt, optional Thảo. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C11 + C12 or C15 with paid/withdrawal knowing assistance The exact player-facing field is in FULL_SCRIPT S10; no automatic inference from ID.
- **STATE READS:** `C11_POLICE_RECEIVED,C12_POLICE_RECEIVED,C15_OPTION, WARN_HOSPITAL` plus source access/willingness and event completion stage.
- **STATE WRITES:** `C11/C12 observed only if viewed; police B=2 only after11:10 receipt/11:20 auth; optional C15 receipt11:20/11:25` only on actual typed action/source event, with `EVENT_DONE:S10_FORM_VERSION` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** C11 discrepancy về money/withdrawal; C12 receipt Khoa biết và vẫn giữ consent, hoặc C15 firsthand cùng case. Huyền không tự biết cả mạng. Seen/understood flags separate; optional detail: C15 alternative; C14 framing chỉ hỗ trợ suspicion.
- **POLICE CUSTODY EFFECT:** C11/C12 original receipt11:10, authenticate11:20 if request; C15 alternative scoped testimony receipt11:20/11:25. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** only observed report to Khải with actual sender/payload/receipt. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C11 + C12 or C15 with paid/withdrawal knowing assistance; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** core20m once; optional Thảo10m once; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** document version, optional testimony, separate source/access/custody. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C15 alternative; C14 framing chỉ hỗ trợ suspicion. never grants its observation; if signature is mandatory, use Không gặp Thảo khi C12 đủ vẫn sống; nếu source cuối mất, warning đã có và G1 sau closure. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Không gặp Thảo khi C12 đủ vẫn sống; nếu source cuối mất, warning đã có và G1 sau closure.
- **RETURN PAYOFF:** S11 thời điểm review D−12 đặt bên cạnh Phúc/job.
- **NEXT EVENTS:** S11_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** DocumentCompare, NPC bounded testimony, receipt/auth, version state. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** two-version consent/review UI, request receipt, optional Thảo; Review D−12, money/withdrawal fields, consent and scope/version history; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S11_TIME_COMPARE

- **EVENT ID:** `S11_TIME_COMPARE`; **SCENE:** S11; **LOCATION:** hospital quiet point/phone; **EVENT CLASS:** SET_PIECE. `S11_MICRO` is MICRO and `S11_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S11_TIME_COMPARE: player tự xếp nguồn theo time, một inference về vị trí Bắc trong cleanup. S12 false apex có thể được bác bằng thứ tự E19/assignment.
- **PRECONDITIONS:** S10 complete, appointment11:30. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** Vũ callback supplies authenticated chronology cards; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Ba timeline cards là raw timestamps: Phúc, Huyền, E19 job; điện thoại của Bắc đặt cạnh police scoped summary.
- **PLAYER LURE:** Tin Vũ chứa một timeline field mới; ngày D−12 nổi khác với D−1 của job.
- **PLAYER ACTION:** Player kéo/đặt đúng thứ tự ba bản gốc; có thể xem exact A content ở mức Vũ cho phép, không giao lại A.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Vũ phone; Phúc only if consent and narrow source; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Vũ tiếp tục professional match, Phúc chỉ biết chuyện mình.
- **EVENT SEQUENCE:** `ENTER` checks A_POLICE_PRESERVED_E28,C11_OBSERVED,C03_OBSERVED; `MICRO` plays Âm bút gạch thời gian; phone hạ âm khi mở document.; optional/repeatable `DISCOVERY` reveals Vụ Phúc/review có trước Bắc; C03 client family đổi nghĩa khi so provenance, không phải nguyên nhân crime.; player commits Vũ callback supplies authenticated chronology cards; `SIGNATURE` performs Vũ nhận ý kiến qua phone; A đã custody E28 không phụ thuộc player drag đúng.; `EXIT` only after Compare/wait tới12:00; travel Tân Lộ30m tới12:30.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Private inference nếu đúng mới ghi; CASE không bị hạ vì xếp sai.
- **AUDIO:** Âm bút gạch thời gian; phone hạ âm khi mở document. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** three timestamp cards, C03 history. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** Phúc withdraw/request, Huyền review D−12, E19 D−1 The exact player-facing field is in FULL_SCRIPT S11; no automatic inference from ID.
- **STATE READS:** `A_POLICE_PRESERVED_E28,C11_OBSERVED,C03_OBSERVED` plus source access/willingness and event completion stage.
- **STATE WRITES:** `optional PRIVATE_PREEXISTING_CASE_INFERRED; no new A custody` only on actual typed action/source event, with `EVENT_DONE:S11_TIME_COMPARE` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Vụ Phúc/review có trước Bắc; C03 client family đổi nghĩa khi so provenance, không phải nguyên nhân crime. Seen/understood flags separate; optional detail: C09 hỗ trợ chronology, không là gate A.
- **POLICE CUSTODY EFFECT:** A=2 immutable; no re-delivery required. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** private comparison0. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** Phúc withdraw/request, Huyền review D−12, E19 D−1; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** compare30m once, travel30m after; retries0; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** card layout/private inference only; custody unchanged. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C09 hỗ trợ chronology, không là gate A. never grants its observation; if signature is mandatory, use Sai xếp vẫn có raw records để xem lại miễn phí; progression không đòi quiz. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Sai xếp vẫn có raw records để xem lại miễn phí; progression không đòi quiz.
- **RETURN PAYOFF:** S12 false apex có thể được bác bằng thứ tự E19/assignment.
- **NEXT EVENTS:** S12_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Timeline UI, source provenance, private inference flag, zero-cost retry. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** three timestamp cards, C03 history; Three provenance/time cards, no unearned crime narration; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S12_FALSE_APEX_SWAP

- **EVENT ID:** `S12_FALSE_APEX_SWAP`; **SCENE:** S12; **LOCATION:** Tân Lộ/dispatch terminal; **EVENT CLASS:** SET_PIECE. `S12_MICRO` is MICRO and `S12_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S12_FALSE_APEX_SWAP: cùng quầy S04, player tự lật audit trail, nghi ngờ đổi từ Tuấn sang Hùng bằng evidence. S16 Hùng D1 chỉ khi firsthand actual statement, không suy từ title.
- **PRECONDITIONS:** retained packets, return12:30. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** player opens authority audit; old Tuấn routine visible nearby; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Cùng dispatch terminal nay hiển thị audit trail; C17, C20, C21 và C22 đã được request/received theo lịch, không source mới từ worker lock.
- **PLAYER LURE:** Tuấn đi qua bảng phân công như hôm qua; timestamp override nằm trước ca anh trực.
- **PLAYER ACTION:** Player mở fast recap hai field C20/C22 thay vì làm lại interrogation; có thể xem C21 routine từ job thường.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Tuấn ordinary route; Hùng offscreen until professional intake; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Tuấn xử lý ca khác, không bất ngờ biết Bắc nghi ai; Hùng không cần monologue.
- **EVENT SEQUENCE:** `ENTER` checks C20_SEEN,C22_POLICE_RECEIVED,C18_AUTH,C19_AUTH; `MICRO` plays Máy quét lặp đúng âm S04; hình ca thường song song ca 117.; optional/repeatable `DISCOVERY` reveals Tuấn không reclassify E19; C22 Hùng đã nhận purpose và approve, nhưng statement Hùng một mình chưa chứng minh Nam.; player commits player opens authority audit; old Tuấn routine visible nearby; `SIGNATURE` performs Police C22 packet receipt13:00; content match không trước14:55 và retained C18/C19 verification13:55.; `EXIT` only after Retained verification tới13:00, travel hospital area13:30/micro-set13:35.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** TUAN_NOT_RECLASSIFIER riêng TUAN_CORE_SCOPE_VERIFIED; Hùng culpable knowledge chỉ từ verified C22.
- **AUDIO:** Máy quét lặp đúng âm S04; hình ca thường song song ca 117. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** audit trail, permission log, ordinary job comparator. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C20 correction; C22 Hùng purpose-known approval + C18/C19 execution The exact player-facing field is in FULL_SCRIPT S12; no automatic inference from ID.
- **STATE READS:** `C20_SEEN,C22_POLICE_RECEIVED,C18_AUTH,C19_AUTH` plus source access/willingness and event completion stage.
- **STATE WRITES:** `TUAN_NOT_RECLASSIFIER; optional TUAN_CORE_SCOPE_VERIFIED; C22 observed; C=2 only after full match14:55` only on actual typed action/source event, with `EVENT_DONE:S12_FALSE_APEX_SWAP` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Tuấn không reclassify E19; C22 Hùng đã nhận purpose và approve, nhưng statement Hùng một mình chưa chứng minh Nam. Seen/understood flags separate; optional detail: C21 hành vi nhất quán; optional conversation không gate.
- **POLICE CUSTODY EFFECT:** C22/C25 packet receipt13:00; operational match13:55; C full fact auth14:55. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** private false apex theory0. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C20 correction; C22 Hùng purpose-known approval + C18/C19 execution; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** retained verification30m once; extra repeat Tuấn visit15m or Hùng wait30m only explicit warning card; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** fast/full viewed and independent Tuấn scope flags, C22 source receipt/auth. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C21 hành vi nhất quán; optional conversation không gate. never grants its observation; if signature is mandatory, use Nếu đã thấy C20, dùng recap ngắn; nếu chưa, phiên bản full inspect vẫn cho cùng fact. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Nếu đã thấy C20, dùng recap ngắn; nếu chưa, phiên bản full inspect vẫn cho cùng fact.
- **RETURN PAYOFF:** S16 Hùng D1 chỉ khi firsthand actual statement, không suy từ title.
- **NEXT EVENTS:** S13_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Fast recap, permission log viewer, versioned audit, no new source pickup. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** audit trail, permission log, ordinary job comparator; Override timestamp before Tuấn, Hùng approval and paid-organ purpose; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S13_TWO_DESKS

- **EVENT ID:** `S13_TWO_DESKS`; **SCENE:** S13; **LOCATION:** hospital-area police micro-set; **EVENT CLASS:** SET_PIECE. `S13_MICRO` is MICRO and `S13_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S13_TWO_DESKS: player nối hai hồ sơ từ hai cơ sở trong không gian chung, phản hồi của Vũ giới hạn vào source đã thấy. S16 X_COMMAND có thể hoàn chỉnh X nếu Khải remit còn thiếu.
- **PRECONDITIONS:** S12 packets and travel13:00→13:35. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** two authenticated risk escalation packets placed for comparison; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Hai request/response packets hospital/logistics với endpoint Khải có thể đặt cạnh nhau; paper custody tags khác private notebook.
- **PLAYER LURE:** Hai thẻ escalation có cùng người nhận nhưng scope khác, điện thoại Vũ báo callback.
- **PLAYER ACTION:** Player so current case, endpoint, role và response; có thể chọn giả thuyết sai về Khải mà vẫn giao raw packets cho Vũ.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Vũ compares at desk; Khải only knows actual risk reports; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Vũ kiểm provenance, Khải chỉ biết report đã nhận; Nam chỉ sau forward thực.
- **EVENT SEQUENCE:** `ENTER` checks C24_RECEIVED,C25_RECEIVED,CASE_B,CASE_C; `MICRO` plays Phone callback; bàn giấy lật, âm phòng nhỏ hơn hành lang.; optional/repeatable `DISCOVERY` reveals X_RISK chỉ khi request/response/auth current Phúc crisis matched; same account/transaction không đủ; N3_UNDERSTANDING private conditional.; player commits two authenticated risk escalation packets placed for comparison; `SIGNATURE` performs Vũ verify C18/C19 match13:55, C content14:55 nếu actual packets complete; X police không đợi player suy đúng.; `EXIT` only after Callback/compare13:35–14:00, S14 notice.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** X_VERIFIED raw source, X_PLAYER_CONNECTED private tách; no auto N3/BARC on completion.
- **AUDIO:** Phone callback; bàn giấy lật, âm phòng nhỏ hơn hành lang. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** two risk packets, provenance tags, notebook inference. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** X_RISK only same Khải endpoint, scoped request/response and Phúc crisis The exact player-facing field is in FULL_SCRIPT S13; no automatic inference from ID.
- **STATE READS:** `C24_RECEIVED,C25_RECEIVED,CASE_B,CASE_C` plus source access/willingness and event completion stage.
- **STATE WRITES:** `conditional X_RISK_VERIFIED; optional X_PLAYER_CONNECTED/N3_UNDERSTANDING` only on actual typed action/source event, with `EVENT_DONE:S13_TWO_DESKS` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** X_RISK chỉ khi request/response/auth current Phúc crisis matched; same account/transaction không đủ; N3_UNDERSTANDING private conditional. Seen/understood flags separate; optional detail: Khải false apex theory; không chặn custody.
- **POLICE CUSTODY EFFECT:** C18/C19 match13:55; C content14:55 if actual complete; X independent of private inference. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** no N3 from scene/private answer. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** X_RISK only same Khải endpoint, scoped request/response and Phúc crisis; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** compare/callback25m once; retry private inference0; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** raw source verification and private inference separately. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional Khải false apex theory; không chặn custody. never grants its observation; if signature is mandatory, use Sai inference không time/route penalty; raw source vẫn được kiểm. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Sai inference không time/route penalty; raw source vẫn được kiểm.
- **RETURN PAYOFF:** S16 X_COMMAND có thể hoàn chỉnh X nếu Khải remit còn thiếu.
- **NEXT EVENTS:** S14_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Dual packet compare, police verifier, private inference, report receipt ledger. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** two risk packets, provenance tags, notebook inference; C24/C25 current incident requests, replies, recipient/source identities; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S14_RETURN_CHANGED

- **EVENT ID:** `S14_RETURN_CHANGED`; **SCENE:** S14; **LOCATION:** multi-hub/phone; **EVENT CLASS:** SET_PIECE. `S14_MICRO` is MICRO and `S14_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S14_RETURN_CHANGED: tái thăm các vật quen cho thấy hệ thống khép cửa bằng state thực, không chase. S18 causal attribution dùng earliest last-path loss, không dùng cảm giác phản bội.
- **PRECONDITIONS:** S13 ends14:00; earlier local closures already happened. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** player revisits phone/door access and receives global notice; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Một worker screen khóa, quầy hospital đổi biển quyền, tin hẹn biến mất theo closure đã xảy ra ở 11:00/11:30/12:30.
- **PLAYER LURE:** Player trở lại cùng điện thoại/hành lang, thấy trạng thái vật khác lần trước; nếu Minh đã hỏi hộ, timestamp report có thể so.
- **PLAYER ACTION:** Player kiểm what actually closed, hỏi Minh phần cậu nói, chuyển ngay retained source còn thiếu cho Vũ hoặc chọn delay có card.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Minh responds only to disclosed text; Khải processes received reports; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Minh giảm nhẹ đúng payload đã gửi; Khải xử lý report thật, Lan/Nam không biết private note.
- **EVENT SEQUENCE:** `ENTER` checks report_received_ledger,C18_PRIVATE_COPY,CASE_C; `MICRO` plays Badge denied; phone vibration; đèn quầy off khi hết ca, không supernatural.; optional/repeatable `DISCOVERY` reveals Cửa access/willingness đóng riêng; copies ở phone Đức/police không biến mất. BARC chỉ từ actual received reports.; player commits player revisits phone/door access and receives global notice; `SIGNATURE` performs Global command notice14:00 trước deadline17:00; acceleration chỉ nếu report, fresh warning và feasible save plan OT §0.1.; `EXIT` only after 20m authored notices/action group tới14:20.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Actual access states và warning receipts; no baseline BARC=N3, no deletion of custody.
- **AUDIO:** Badge denied; phone vibration; đèn quầy off khi hết ca, không supernatural. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** worker screen, hospital sign, phone report timestamps. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C43 actual loss of access, no evidence deletion The exact player-facing field is in FULL_SCRIPT S14; no automatic inference from ID.
- **STATE READS:** `report_received_ledger,C18_PRIVATE_COPY,CASE_C` plus source access/willingness and event completion stage.
- **STATE WRITES:** `WARN_GLOBAL_1400; access variant changes; conditional fresh acceleration warning W` only on actual typed action/source event, with `EVENT_DONE:S14_RETURN_CHANGED` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Cửa access/willingness đóng riêng; copies ở phone Đức/police không biến mất. BARC chỉ từ actual received reports. Seen/understood flags separate; optional detail: C35–C37 conditional leak trace, không tạo proof giả.
- **POLICE CUSTODY EFFECT:** all earlier police receipts persist. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** N3 only if actual two-cell reports received, not baseline scene. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C43 actual loss of access, no evidence deletion; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** notice/action group20m once; optional deliberate waits separately as OT §0.1; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** access variants, report/warning receipts, no rollback of source copies. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C35–C37 conditional leak trace, không tạo proof giả. never grants its observation; if signature is mandatory, use Local locks không chặn professional copies; player vẫn chuyển nguồn đã giữ. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Local locks không chặn professional copies; player vẫn chuyển nguồn đã giữ.
- **RETURN PAYOFF:** S18 causal attribution dùng earliest last-path loss, không dùng cảm giác phản bội.
- **NEXT EVENTS:** S15_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Prop/access variants, notification ledger, warning card, causal report. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** worker screen, hospital sign, phone report timestamps; Local11:00/11:30/12:30 and global17:00 notices; acceleration conditional feasible; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S15_CUSTODY_DESK

- **EVENT ID:** `S15_CUSTODY_DESK`; **SCENE:** S15; **LOCATION:** police micro-set/evidence tray; **EVENT CLASS:** SET_PIECE. `S15_MICRO` is MICRO and `S15_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S15_CUSTODY_DESK: thao tác phân nguồn gốc cụ thể thay cho lời thuyết phục Vũ. S16 professional collection chạy sau actual E38.
- **PRECONDITIONS:** S14 notices,14:20. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** player opens source tray or actual police intake callback; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Bàn nhận evidence có khay source với provenance và pending authentication; không bảng suspects.
- **PLAYER LURE:** Một item giữ riêng trên phone Bắc đối chiếu được với khay police; dấu received chưa phải verified.
- **PLAYER ACTION:** Player chọn gửi bản gốc/custodian/contact và scope, có thể giữ lại, delay20m hoặc abandon khi actual N3 report.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Vũ at tray, checks custodian/fields; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Vũ tự request đủ scope đã biết, không đợi một accusation quiz.
- **EVENT SEQUENCE:** `ENTER` checks CASE_A=2,CASE_B,CASE_C,X_VERIFIED,BARC; `MICRO` plays Scan giấy, phone receipt, tem ngày/giờ; city outside continues.; optional/repeatable `DISCOVERY` reveals A đã Vũ giữ từ E28; B/C/X tăng chỉ sau receipt + independent checks; private N3 understanding không quyết định threshold.; player commits player opens source tray or actual police intake callback; `SIGNATURE` performs E38 actual baseline14:55 khi đủ raw/auth, không auto từ scene completion; custody-first cho command requests S16.; `EXIT` only after Intake/coordination tới15:00; S16 chỉ theo actual E38 hoặc partial path.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Actual custody monotonic, E38 if threshold; ABANDON_AFTER_N3 only on explicit choice + received reports.
- **AUDIO:** Scan giấy, phone receipt, tem ngày/giờ; city outside continues. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** phone originals, evidence tray, source provenance receipt. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C42 custody receipt, not magic clue The exact player-facing field is in FULL_SCRIPT S15; no automatic inference from ID.
- **STATE READS:** `CASE_A=2,CASE_B,CASE_C,X_VERIFIED,BARC` plus source access/willingness and event completion stage.
- **STATE WRITES:** `actual B/C/X source custody; E38_THRESHOLD only when exact required raw sources auth; optional ABANDON_AFTER_N3` only on actual typed action/source event, with `EVENT_DONE:S15_CUSTODY_DESK` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** A đã Vũ giữ từ E28; B/C/X tăng chỉ sau receipt + independent checks; private N3 understanding không quyết định threshold. Seen/understood flags separate; optional detail: Không cần private correct Khải/true boss inference.
- **POLICE CUSTODY EFFECT:** E38 baseline14:55 only if raw sources complete; actual late inputs shift. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** N3 report required for abandonment; custody action alone not leak. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C42 custody receipt, not magic clue; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** coordination/intake40m once; wait20m only explicit delayed appointment; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** atomic receipts and E38, no duplicate source after load. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional Không cần private correct Khải/true boss inference. never grants its observation; if signature is mandatory, use Thử lại provenance không cost; missing source thật đóng thì G1/G2/G5 theo cause. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Thử lại provenance không cost; missing source thật đóng thì G1/G2/G5 theo cause.
- **RETURN PAYOFF:** S16 professional collection chạy sau actual E38.
- **NEXT EVENTS:** S16_ENTER if E38, else partial path/S18 when terminal; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Evidence tray, provenance verifier, E38 timer, abandonment condition. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** phone originals, evidence tray, source provenance receipt; Individual source receipts with status QUEUED/RECEIVED/AUTHENTICATED; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S16_THREE_ORIGINS

- **EVENT ID:** `S16_THREE_ORIGINS`; **SCENE:** S16; **LOCATION:** police source desks/phone; **EVENT CLASS:** SET_PIECE. `S16_MICRO` is MICRO and `S16_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S16_THREE_ORIGINS: player đối chiếu manager firsthand, reply phía branch kia và source execution mà không trộn một forward làm ba chứng cứ. S17 Nam recontextualized, S18 consequence đúng source.
- **PRECONDITIONS:** actual E38=t0. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** Vũ starts manager, other-branch and broker requests on threshold; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Ba station nguồn: manager, original institution reply, broker annex; bản gốc L/H issue trước intake, không future record ở E28.
- **PLAYER LURE:** Một stamp decision trên reply cho branch kia không giống statement manager; broker receipt có cùng directive scope.
- **PLAYER ACTION:** Player xem ba nguồn Vũ được phép hiển thị, so quyết định khác nhau và annex cùng case; không tự đi ép Hạnh/Nam.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Vũ desk; manager on scoped phone; broker source separate; Nam absent; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Vũ intake chuyên nghiệp; manager chỉ branch mình, broker chỉ received directive, Nam không đọc scene completion.
- **EVENT SEQUENCE:** `ENTER` checks E38_TIME,C32H_AVAILABLE,C32K_AVAILABLE,C33_AUTH,C34_AUTH,C10_SOURCE_LINK; `MICRO` plays Điện thoại báo receipt, printer annex nhả trang, bút ký custodial seal.; optional/repeatable `DISCOVERY` reveals C32H+C33_AUTH hoặc C32K+C34_AUTH và C10_SOURCE_LINK exact D2. Original receiver-side Nam reply phải verify; X_COMMAND có thể sinh từ raw facts này.; player commits Vũ starts manager, other-branch and broker requests on threshold; `SIGNATURE` performs Request t0+5/+10/+15; receipts +25/+40 or45/+55; authentication/full match +75 baseline16:10, chỉ khi nguồn hợp tác và window mở.; `EXIT` only after Actual D verified nếu đủ; scene presentation tới16:25, no forced extra travel.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** COMMAND C3/C4 chỉ từ raw verified/preserved; X normalize trước resolver; unavailable route có manager alternate.
- **AUDIO:** Điện thoại báo receipt, printer annex nhả trang, bút ký custodial seal. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** three original packets and compare UI, C31 contact lead. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C32H+C33_AUTH or C32K+C34_AUTH, plus C10_SOURCE_LINK exact D2 The exact player-facing field is in FULL_SCRIPT S16; no automatic inference from ID.
- **STATE READS:** `E38_TIME,C32H_AVAILABLE,C32K_AVAILABLE,C33_AUTH,C34_AUTH,C10_SOURCE_LINK` plus source access/willingness and event completion stage.
- **STATE WRITES:** `D1/D2/source-annex actual receipts/auth; X_COMMAND normalized; COMMAND C3/C4 if timely` only on actual typed action/source event, with `EVENT_DONE:S16_THREE_ORIGINS` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** C32H+C33_AUTH hoặc C32K+C34_AUTH và C10_SOURCE_LINK exact D2. Original receiver-side Nam reply phải verify; X_COMMAND có thể sinh từ raw facts này. Seen/understood flags separate; optional detail: C31 contact chỉ lead, C30 history không gate.
- **POLICE CUSTODY EFFECT:** manager firsthand; original Nam receiver-side reply other branch; broker original request/forward/receipt; exact case/source/decision match. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** no automatic Nam knowledge from intake; only actual report receipt. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C32H+C33_AUTH or C32K+C34_AUTH, plus C10_SOURCE_LINK exact D2; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** professional requests t0+5/+10/+15, receipts+25/+40 or45/+55, full auth+75; presentation to16:25 baseline; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** each request/receipt/auth/result stage and selected manager route, no duplicated manager or future annex. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional C31 contact chỉ lead, C30 history không gate. never grants its observation; if signature is mandatory, use Mất Hùng dùng Khoa+logistics original; mất cả managers không record-only magic D1. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Mất Hùng dùng Khoa+logistics original; mất cả managers không record-only magic D1.
- **RETURN PAYOFF:** S17 Nam recontextualized, S18 consequence đúng source.
- **NEXT EVENTS:** S17_ENTER optional or S18_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Source request scheduler, original reply verifier, broker annex UI, custody variants. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** three original packets and compare UI, C31 contact lead; L13:20/execution13:25 and H13:45/execution13:50 distinct; annex forward/receipt only as matched scope; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S17_ROOM_JAM

- **EVENT ID:** `S17_ROOM_JAM`; **SCENE:** S17; **LOCATION:** HUB B/phòng Nam optional; **EVENT CLASS:** SET_PIECE. `S17_MICRO` is MICRO and `S17_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S17_ROOM_JAM: 1–3 phút khám phá có lối thoát causal, player giữ quyền điều khiển; optional unsafe confrontation riêng. Epilogue vật cũ S01; encounter thay sắc thái theo knowledge, không thêm gate True.
- **PRECONDITIONS:** S16 result or command hypothesis; return choice16:25→17:00. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** legitimate Lan/Nam return errand and player steps inside; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Hành lang S01 và góc sửa đồ vẫn thường; cửa phòng Nam chỉ mở với lý do đời thường được Lan/Nam mời hoặc trả món đồ.
- **PLAYER LURE:** Radio rít nhẹ, một ổ điện lỗi làm chốt cửa kẹt; từ bàn có sổ ghi các mảnh “K. báo lại”, “MT giữ nguyên”, “117”.
- **PLAYER ACTION:** Nếu chọn vào, player thử tay nắm, gõ/gọi, xem đồ hợp lệ; giữ control, có thể rời khi chốt được Lan xử lý từ ngoài. Không bắt đọc sổ.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Lan stairs→door release on knock or latch reset; Nam scheduled return outside player sightline; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Lan đi cầu thang rồi hỗ trợ; Nam về theo lịch, không telepathy; có thể không gặp.
- **EVENT SEQUENCE:** `ENTER` checks COMMAND,C28_SEEN,door_stage,object_disturbed; `MICRO` plays Static radio, bước chân ngoài cửa, đèn buzz; môi trường phản hồi nhẹ nhưng có nguồn vật lý.; optional/repeatable `DISCOVERY` reveals Fragments là context/hypothesis, không Nam-boss proof; command chỉ từ S16 professional sources.; player commits legitimate Lan/Nam return errand and player steps inside; `SIGNATURE` performs Door jam do chốt cũ/điện, Lan nghe tiếng gõ hoặc chốt tự reset sau mechanic beat; không ba clue mở phép. Nam chỉ biết xáo trộn nếu trực tiếp thấy dấu cụ thể.; `EXIT` only after Door released, optional conversation xong; đi police35m nếu cần, hoặc direct S18.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Door JAMMED→RELEASED vì latch reset/Lan; disturbed object flag chỉ nếu player thật sự chuyển vật và Nam nhìn thấy.
- **AUDIO:** Static radio, bước chân ngoài cửa, đèn buzz; môi trường phản hồi nhẹ nhưng có nguồn vật lý. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** door handle/knock, notebook, drawer if legitimate, radio/light. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** notebook fragments only hypothesis, no C4/true gate The exact player-facing field is in FULL_SCRIPT S17; no automatic inference from ID.
- **STATE READS:** `COMMAND,C28_SEEN,door_stage,object_disturbed` plus source access/willingness and event completion stage.
- **STATE WRITES:** `S17_ENTERED; door JAMMED then RELEASED by latch/Lan; optional NOTEBOOK_PAGES_SEEN/disturbance; observed report only if Nam sees` only on actual typed action/source event, with `EVENT_DONE:S17_ROOM_JAM` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Fragments là context/hypothesis, không Nam-boss proof; command chỉ từ S16 professional sources. Seen/understood flags separate; optional detail: Notebook fragments/C28; toàn bộ S17 có thể bỏ qua nếu custody đã an toàn.
- **POLICE CUSTODY EFFECT:** no new proof; S16 custody persists on bypass. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** only exact observable disturbance/confrontation and actual report, not read flag. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** notebook fragments only hypothesis, no C4/true gate; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** return travel35m + ordinary contact15m; no invisible inspect cost; police return35m if chosen; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** event stage, door state, pages, NPC marker, disturbance/actual witness; reload never re-jams after release. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional Notebook fragments/C28; toàn bộ S17 có thể bỏ qua nếu custody đã an toàn. never grants its observation; if signature is mandatory, use Bỏ về trọ vẫn tới S18; nếu door jam, gõ/gọi hoặc chờ authored release không tốn missing-source window bất ngờ. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Bỏ về trọ vẫn tới S18; nếu door jam, gõ/gọi hoặc chờ authored release không tốn missing-source window bất ngờ.
- **RETURN PAYOFF:** Epilogue vật cũ S01; encounter thay sắc thái theo knowledge, không thêm gate True.
- **NEXT EVENTS:** S18_ENTER; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** DoorInteractable JAMMED, light/radio, document pages, Lan NPC route, bypass. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** door handle/knock, notebook, drawer if legitimate, radio/light; “K. báo lại — chưa đóng”; “MT giữ nguyên tới xác nhận”; “117 không nên xuống luồng thường.”; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

### S18_TWO_TRAYS

- **EVENT ID:** `S18_TWO_TRAYS`; **SCENE:** S18; **LOCATION:** police micro-set/consequence; **EVENT CLASS:** SET_PIECE. `S18_MICRO` is MICRO and `S18_DISCOVERY` is DISCOVERY within this staged card, with graph nodes above.
- **PURPOSE:** S18_TWO_TRAYS: cùng bố cục police tray và screen closure, nội dung/sound đổi theo phần thật đã giữ và nguyên nhân mất. Mọi seed vật/âm từ S04/S14 được trả lại qua consequence.
- **PRECONDITIONS:** S16 or S17 return/bypass, actual terminal condition. Scene enter flag once; the source availability and actual clock conditions below still apply.
- **TRIGGER:** confirmed final exit or warned last-path/global closure; Area3D/raycast only when its prop and source are present. Repeat inspect is safe.
- **ENVIRONMENT BEFORE:** Police evidence tray và phone status đặt cạnh nhau, exterior Hà Nội vẫn tiếp tục; không gói clue mới.
- **PLAYER LURE:** Một custody receipt hoặc warned source closure cuối hiện rõ trước khi player xác nhận bước tiếp.
- **PLAYER ACTION:** Player review provenance/source paths, chuyển item còn thiếu nếu window open; xác nhận exit hoặc nhìn timeline consequence.
- **CONTROL MODE:** first-person movement/look maintained; document/phone overlay temporarily takes input only while opened; never force a suspect answer or lock movement for the full event.
- **NPC POSITIONS:** Vũ acts on proof; network actors only on actual knowledge; enable one actor instance at a persisted marker, never spawn a second after reload.
- **NPC ROUTINES:** Vũ hành động trên proof thực; Nam/Khải chỉ phản ứng reports/custody họ có thể biết.
- **EVENT SEQUENCE:** `ENTER` checks CASE_A/B/C,X_RISK,X_COMMAND,COMMAND,DECISIVE_LOSS,ABANDON_AFTER_N3,CLEANUP; `MICRO` plays Printer seal, phone ngừng rung, ambience ngõ trở lại ở epilogue.; optional/repeatable `DISCOVERY` reveals Outcome do CASE/X/COMMAND + earliest DECISIVE_LOSS/abandon, không suspect selection.; player commits confirmed final exit or warned last-path/global closure; `SIGNATURE` performs Resolver P4 xử lý receipts trước closure; G6/G3/G5/G2/G4/G1 exhaustive. A/B/C police held stay held ở mọi cinematic.; `EXIT` only after Cinematic ngắn và ending screen sau confirmed terminal state.. A missed MICRO cannot gate the source.
- **WORLD CHANGES:** Ending ID and locked snapshot persisted once; no magically refreshed records.
- **AUDIO:** Printer seal, phone ngừng rung, ambience ngõ trở lại ở epilogue. Ambience remains tied to location, not private inference.
- **LIGHTING:** use existing practical fixture/phone screen; preserve changed bulb/room state on reload. S17 uses authored fault/repair stage.
- **CAMERA:** eye-level first person; prop/sound cue via position, no mandatory close-up or cinematic information that the player could miss.
- **INTERACTABLES:** custody tray, warning/source-path viewer, confirm exit. Reusable raycast + document/door/phone wrapper, CollisionShape3D only on tangible objects; Area3D for entry/exit.
- **DISCOVERY:** C42/C43 only existing receipts/closures The exact player-facing field is in FULL_SCRIPT S18; no automatic inference from ID.
- **STATE READS:** `CASE_A/B/C,X_RISK,X_COMMAND,COMMAND,DECISIVE_LOSS,ABANDON_AFTER_N3,CLEANUP` plus source access/willingness and event completion stage.
- **STATE WRITES:** `ENDING_ID, TERMINAL_SNAPSHOT once` only on actual typed action/source event, with `EVENT_DONE:S18_TWO_TRAYS` after staged commit; no inference on scene exit.
- **PLAYER KNOWLEDGE EFFECT:** Outcome do CASE/X/COMMAND + earliest DECISIVE_LOSS/abandon, không suspect selection. Seen/understood flags separate; optional detail: Optional old object epilogue không đổi proof.
- **POLICE CUSTODY EFFECT:** all preserved slots monotonic; no reset in G1/G2/G4/G5. Existing A/B/C=2 never decremented by this event.
- **BARC EFFECT:** only historical received reports, no cinematic omniscience. Report ledger stores sender/payload/recipient/received_at.
- **CLUE EFFECT:** C42/C43 only existing receipts/closures; source provenance and original_at retained on repeat.
- **OBJECTIVE TIME COST:** no new source time; consequences after actual timeline, no invented final timer; charge each named group once, preview deadline before extra visit/wait. Reading/retries0.
- **ONE-SHOT / REPEAT:** staged world change and clock commit once; optional document/phone reread repeatable without write; missed micro cannot replay after scene exit.
- **SAVE / LOAD:** atomic terminal snapshot with ending ID, source/custody/time; reload never replays receipt/ending choice. Persist prop variant, staged trigger, NPC marker and source/custody transaction atomically.
- **SKIP BEHAVIOR:** skipping optional Optional old object epilogue không đổi proof. never grants its observation; if signature is mandatory, use Nếu còn last saving path, không resolve; cho player quay lại nguồn hợp lệ. to offer minimum interaction. No skip auto-grants receipt/authentication.
- **FAIL-FORWARD:** Nếu còn last saving path, không resolve; cho player quay lại nguồn hợp lệ.
- **RETURN PAYOFF:** Mọi seed vật/âm từ S04/S14 được trả lại qua consequence.
- **NEXT EVENTS:** credits; use graph conditional edges, no implicit jump over required receipt.
- **DEV IMPLEMENTATION HOOKS:** Total resolver, causal-loss snapshot, custody UI, ending variants, idempotent save/load. EventManager staged ID, GameState predicates, SaveManager snapshot, AudioStreamPlayer3D/AnimationPlayer/visibility swap as appropriate.
- **REQUIRED ASSETS:** custody tray, warning/source-path viewer, confirm exit; Ending screen displays preserved slots and exact missing proposition, not new evidence; sound/light stated above, one reusable NPC variant if named. Detailed IDs in SCENE_ASSET_MANIFEST.md.

## Critical sequences that must be implemented literally

### S08–S10 morning source queue

S08 warning09:25 → Đức offer09:30 → optional direct C18 local receipt09:45. S09 actual group10:15 starts C17 original check, bounded Đức contact10:25/receipt10:35/auth10:45 if exact contact disclosed; optional Yến contact10:40/receipt10:50/auth11:00; hospital C11/C12 group request10:15, receipt11:10, auth11:20. Optional C15 receipt11:20/11:25 before11:30. Late disclosure q uses OT §0.1 formulas and source willingness; zero retroactive timestamps. Receipt/verification status must be visible separately.

### S13–S16 proof normalization

S12 C22/C25 packet receipt13:00, operational match13:55, full C fact/auth14:55 baseline. S13 X_RISK requires two authenticated scoped current Phúc crisis exchanges to same Khải endpoint. Failed private matching writes only a hypothesis. S15 E38 starts at actual complete A/B/C raw corroboration (baseline14:55) and sends the three S16 requests at t0+5/+10/+15; manager t0+25, original branch t0+40/45, annex t0+55, exact full match t0+75. Distinct current L13:20/execution13:25 and H13:45/execution13:50 precede intake. C32H firsthand L + C33_AUTH original H or C32K firsthand H + C34_AUTH original L; broker annex must match **selected D2** by same case/directive and actual execution, not count as independent D2. Receiver-side original Nam reply, author endpoint, request/forward/execution and custody required. Authenticate these raw facts before deriving X_COMMAND; X may be true without Khải remit. C4 only if all D sources preserved before warned global lock.

### S17 room jam and S18 terminal resolver

S17 is optional. Legitimate errand→old latch jams→player handle/knock/call works→room accessible→radio/light practical cues→Lan route or physical latch reset releases door; release does not test notebook clue count. A page observation writes only the page seen. Nam knowledge changes only on witnessed disturbance or actual received report. Save mid-event restores jam stage/actor marker. Bypass after S16 leaves custody untouched.

At S18 apply completed receipt/authentication first; derive X_RISK/X_COMMAND from raw police sources; derive COMMAND; read earliest immutable DECISIVE_LOSS with `(time, sequence, slot, before/after paths, cause, warning receipt, saving action)`. If a saving path exists, stay playable. Terminal order: timely ABC=2+X+C4→G6; explicit qualified N3 abandonment→G3; first irreversible DIRECT→G5 or MINH→G2 (including D-only); ABC=2+X but D late→G4; all others→G1 including ABC=2/X=false and weak two-slot routes. Present actual preserved slots in each ending. A later harmless leak cannot override earlier cause; lock cannot erase custody. Refer to ENDING_LOGIC §4.2 fixtures for negative cases.

## Implementation smoke checks (document contract, not runtime claim)

- Reload S04 after receipt: original13:52 unchanged, no duplicate scanner or clue; inspect later sets observed_at only.
- Reload S08 with Đức copy then worker lock: phone/police copy remains; no second offer or time charge.
- S13 wrong inference with full police raw context: X police true, private understanding false, BARC unchanged.
- S16 X_RISK false but all verified same-case D raw origins and annex: X_COMMAND true then C4 timely. Duplicate forward/mismatched case/unrelated consultant: X_COMMAND false.
- S17 reload during jam: player control/knock available, door/NPC marker coherent, eventual authored release. Bypass reaches S18.
- S18 ABC=2/X=false at lock: G1 and ABC still police held. MINH last D path loss then harmless DIRECT: G2. Timely C4 then disclosure: G6.
