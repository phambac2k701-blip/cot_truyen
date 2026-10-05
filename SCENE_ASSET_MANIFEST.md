# SCENE ASSET MANIFEST — S01–S18

> Derived from the committed P5 scene contracts, FULL_SCRIPT and EVENT_IMPLEMENTATION_SPEC. Event IDs below are exact. No asset has been downloaded or licensed by this document. Source/license verification is recorded later in ASSET_SOURCES.md.

## Global acquisition queue

**P0 — FIND FIRST:** modular boarding-house rooms/door and correct-pivot handle; logistics counter/printer/scanner/monitor; phone; sealed pouch; hero paper/tray; generic NPC body; core SFX FX01–FX07, FX10–FX15, FX19, FX23; AN01–AN08, AN10–AN11. Create in-house fictional form/phone textures PR13/PR15/PR18/PR21/PR22/PR24 before source hunt gets broad.

**P1 — FIND AFTER PROTOTYPE:** campus/meal/hospital/police modular sets; Đức/Huyền/Vũ/Thảo variants; background workers, trolley; radio/notebook; ambience AU03–AU07; remaining motion and SFX.

**P2 — POLISH:** old C28 card art, extra clothing and environmental decals, secondary clutter, optional full Hùng/Khoa on-screen models, richer VO. Asset sources and commercial terms remain unverified until each is entered in ASSET_SOURCES.md.

## Visual model versus gameplay component

| Visual items | One reusable gameplay component | State owner |
|---|---|---|
| PR01/PR02 door models | `DoorInteractable.tscn` + latch child | S01/S17 event state |
| PR07/PR13/PR15/PR18/PR20/PR21/PR22/PR24/PR25 paper/screen artwork | `DocumentInteractable.tscn`, `VersionCompare.tscn`, `ThreeOriginsViewer.tscn` | clue/source provenance + pages seen |
| PR03/PR04/PR05 utility variants | socket/light/fan controllers | authored prop state |
| PR08/PR16 phone shells | `PhoneInteractable.tscn` with different owned content | phone source/receipt ledger |
| PR11/PR12/PR14/PR19/PR23 machines/trays | scanner, printer, screen, access, evidence components | EventManager + custody/source state |
| CH02–CH12 visual clothing/head variants | `NPC_Base.tscn` plus route markers | report/witness stage, not private thought |

## Asset item register

Codes: source `NEED_TO_FIND` needs URL/author/commercial license/attribution check; `CREATE_IN_HOUSE` is a future original deliverable, not an existing asset. License requirement for every sourced item is **commercial use and attribution verification before import**; for in-house originals the owner sets project rights. `P0` prototype, `P1` vertical slice, `P2` polish. `YES/NO` in Collision refers to a physical hit/collision target; 2D document UI has a 3D host where noted.

| Asset ID | Name | Type | Used in / exact event IDs | Priority | Interactive? | Reusable? | Collision? | Animations required | Audio required | State variants | Godot wrapper | Source status | License requirement | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| AR01 | Dãy trọ: phòng Bắc/Nam, hành lang, cầu thang | 3D ARCHITECTURE | S01, S05, S06, S07, S17, S18 / S01_POWER_REPAIR S05_ORDINARY_RETURN S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S17_ROOM_JAM S18_TWO_TRAYS | P0 | NO | YES | YES | — | AU01 AU02 | ordinary/evening; S17 return | `BoardingHouseHub.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Modular rooms; doorways and stairs support first-person routes. |
| AR02 | Giảng đường và khu bảng tin | 3D ARCHITECTURE | S02 / S02_CLASS_ROUTINE | P1 | NO | YES | YES | — | AU03 | class/in-between | `CampusRoom.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Simple classroom and public corridor. |
| AR03 | Khu ăn/sinh hoạt sinh viên | 3D ARCHITECTURE | S03, S05 / S03_JOB_ACCEPT S05_ORDINARY_RETURN | P1 | NO | YES | YES | — | AU04 | lunch/afternoon | `MealArea.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Can reuse furniture and background clutter. |
| AR04 | Tân Lộ dispatch/quầy kho | 3D ARCHITECTURE | S04, S08, S09, S12 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S09_SCOPED_INTAKE S12_FALSE_APEX_SWAP | P0 | NO | YES | YES | — | AU05 | normal/audit/access-denied | `LogisticsHub.tscn` | NEED_TO_FIND | verify commercial permission + attribution | One modular location revisited; no full warehouse required. |
| AR05 | Điểm nhận hành chính | 3D ARCHITECTURE | S04 / S04_SCAN_MISMATCH | P1 | NO | YES | YES | — | AU06 | check-in/scanned | `ReceiverCounter.tscn` | NEED_TO_FIND | verify commercial permission + attribution | No operating room, only public/admin counter. |
| AR06 | Minh Trạch quầy review/hành lang | 3D ARCHITECTURE | S10, S11, S13, S14 / S10_FORM_VERSION S11_TIME_COMPARE S13_TWO_DESKS S14_RETURN_CHANGED | P1 | NO | YES | YES | — | AU06 | scope-open/scope-narrowed | `HospitalReviewHub.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Legitimate public access, paired version tray. |
| AR07 | Police micro-set/bàn Vũ | 3D ARCHITECTURE | S09, S11, S13, S15, S16, S18 / S09_SCOPED_INTAKE S11_TIME_COMPARE S13_TWO_DESKS S15_CUSTODY_DESK S16_THREE_ORIGINS S18_TWO_TRAYS | P1 | NO | YES | YES | — | AU07 | intake/command/consequence | `PoliceMicroSet.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Reuse same desk for phone and physical compare. |
| PR01 | Cửa phòng/gate modular | 3D INTERACTIVE PROP | S01, S05, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S17_ROOM_JAM | P0 | YES | YES | YES | AN05 | FX01 FX02 FX03 FX04 FX05 | open/closed/locked/jammed/released | `DoorInteractable.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Pivot and handle alignment; S17 release via Lan/latch, never clue count. |
| PR02 | Chốt cửa/handle hero | 3D INTERACTIVE PROP | S17 / S17_ROOM_JAM | P0 | YES | YES | YES | AN05 | FX03 FX04 FX05 | normal/jammed/reset | `LatchInteractable.tscn` | CREATE_IN_HOUSE | owner-set original rights | Separate collision/hit target; persists jam stage. |
| PR03 | Ổ điện/ổ kéo sửa được | 3D INTERACTIVE PROP | S01, S02, S05, S17 / S01_POWER_REPAIR S02_CLASS_ROUTINE S05_ORDINARY_RETURN S17_ROOM_JAM | P0 | YES | YES | YES | AN08 | FX06 FX07 | fault/working/repaired | `SocketInteractable.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Real fault/motion cause; classroom variant shares wrapper. |
| PR04 | Đèn bàn/huỳnh quang | 3D INTERACTIVE PROP | S01, S05, S14, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S14_RETURN_CHANGED S17_ROOM_JAM | P0 | YES | YES | YES | — | FX06 FX07 | normal/flicker/off | `LightController.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Use fixture state, no supernatural deduction response. |
| PR05 | Quạt bàn/quạt trần | 3D PROP | S01, S05, S06, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S06_AUDIT_FORM S17_ROOM_JAM | P1 | NO | YES | YES | AN09 | FX08 | stopped/rotating | `FanProp.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Spatial room-tone accent. |
| PR06 | Bàn/ghế/tủ trọ + laptop | 3D PROP | S01, S05, S06, S07, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S17_ROOM_JAM | P0 | YES | YES | YES | AN03 | FX09 | study/repair/room-return | `RoomFurniture.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Modular variants and seat collision. |
| PR07 | Card Tân Lộ cũ C28 | UI / DOCUMENT | S01, S05, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S17_ROOM_JAM | P2 | YES | YES | NO | — | FX10 | unseen/seen/revisited | `DocumentInteractable.tscn` | CREATE_IN_HOUSE | owner-set original rights | Optional old relationship, never current command. |
| PR08 | Điện thoại Bắc hero | 3D INTERACTIVE PROP | S01, S02, S03, S04, S05, S06, S07, S08, S09, S11, S13, S14, S15, S16, S17, S18 / S01_POWER_REPAIR S02_CLASS_ROUTINE S03_JOB_ACCEPT S04_SCAN_MISMATCH S05_ORDINARY_RETURN S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S08_PRINT_COMPARE S09_SCOPED_INTAKE S11_TIME_COMPARE S13_TWO_DESKS S14_RETURN_CHANGED S15_CUSTODY_DESK S16_THREE_ORIGINS S17_ROOM_JAM S18_TWO_TRAYS | P0 | YES | YES | YES | AN06 | FX11 FX12 | idle/notification/app/call | `PhoneInteractable.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Shared physical shell; screen content separate UI. |
| PR09 | Biển phòng học và ghế có ổ | 3D PROP | S02 / S02_CLASS_ROUTINE | P1 | YES | YES | YES | — | AU03 | seat/plug-state | `CampusInteractables.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Room sign must be readable in first-person. |
| PR10 | Pouch TL-2604-117 niêm kín | 3D INTERACTIVE PROP | S04 / S04_SCAN_MISMATCH | P0 | YES | NO | YES | AN10 | FX13 | sealed/in-transit/handed-over | `SealedPouch.tscn` | CREATE_IN_HOUSE | owner-set original rights | Never open into magic evidence. |
| PR11 | Máy quét barcode | 3D INTERACTIVE PROP | S04, S08, S12 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S12_FALSE_APEX_SWAP | P0 | YES | YES | YES | AN08 | FX14 | normal/mismatch/resolved | `ScannerInteractable.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Two scan tones and scope-correct mismatch UI. |
| PR12 | Máy in/quầy giấy | 3D INTERACTIVE PROP | S04, S08, S10, S12, S16, S18 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S10_FORM_VERSION S12_FALSE_APEX_SWAP S16_THREE_ORIGINS S18_TWO_TRAYS | P0 | YES | YES | YES | AN11 | FX15 FX16 | idle/feeding/page-present | `PrinterInteractable.tscn` | NEED_TO_FIND | verify commercial permission + attribution | C17 old version emerges from actual printer; no auto proof. |
| PR13 | Giấy biên nhận/proof-of-handover | UI / DOCUMENT | S04, S06, S09, S11 / S04_SCAN_MISMATCH S06_AUDIT_FORM S09_SCOPED_INTAKE S11_TIME_COMPARE | P0 | YES | YES | NO | AN03 | FX10 | original13:52/reinspected | `DocumentInteractable.tscn` | CREATE_IN_HOUSE | owner-set original rights | Same content/original time on later history inspect. |
| PR14 | Terminal dispatch và monitor | 3D INTERACTIVE PROP | S04, S08, S12, S14 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S12_FALSE_APEX_SWAP S14_RETURN_CHANGED | P0 | YES | YES | YES | AN07 | FX17 | Standard/Internal/override/denied | `ScreenInteractable.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Model separate from screen textures/state. |
| PR15 | Bản in C17 và operations C18 | UI / DOCUMENT | S08, S09, S12 / S08_PRINT_COMPARE S09_SCOPED_INTAKE S12_FALSE_APEX_SWAP | P0 | YES | YES | NO | AN03 | FX10 | old/new; local/police custody | `VersionCompare.tscn` | CREATE_IN_HOUSE | owner-set original rights | C18 custodian Đức phone or police export, not retroactive. |
| PR16 | Điện thoại riêng Đức | 3D INTERACTIVE PROP | S08 / S08_PRINT_COMPARE | P1 | YES | YES | YES | AN06 | FX11 | copy-held/offered | `PhoneInteractable.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Private copy survives worker-account lock. |
| PR17 | Bảng finance/lead Yến | UI / DOCUMENT | S08, S09, S12 / S08_PRINT_COMPARE S09_SCOPED_INTAKE S12_FALSE_APEX_SWAP | P1 | YES | YES | NO | — | FX10 | lead/request/received/auth | `DocumentInteractable.tscn` | CREATE_IN_HOUSE | owner-set original rights | No instant financial full-proof from lead alone. |
| PR18 | Form consent/review hai version | UI / DOCUMENT | S10, S11, S13 / S10_FORM_VERSION S11_TIME_COMPARE S13_TWO_DESKS | P0 | YES | YES | NO | AN03 | FX10 | old/narrow; received/auth | `VersionCompare.tscn` | CREATE_IN_HOUSE | owner-set original rights | Exact money/withdrawal/knowledge fields, not generic dates. |
| PR19 | Khay/biển quyền review bệnh viện | 3D INTERACTIVE PROP | S10, S14 / S10_FORM_VERSION S14_RETURN_CHANGED | P1 | YES | YES | YES | AN11 | FX16 FX18 | scope-open/narrowed/access-denied | `AccessStateProp.tscn` | NEED_TO_FIND | verify commercial permission + attribution | World changes after earlier actual closure. |
| PR20 | Ba thẻ mốc thời gian | UI / DOCUMENT | S11 / S11_TIME_COMPARE | P1 | YES | YES | NO | — | FX10 | unordered/ordered/retry | `TimelineCompare.tscn` | CREATE_IN_HOUSE | owner-set original rights | Provenance date vs observed_at; wrong retry0. |
| PR21 | Authority log C20/C22 | UI / DOCUMENT | S12 / S12_FALSE_APEX_SWAP | P0 | YES | YES | NO | — | FX10 | fast-recap/full; receipt/auth | `AuditTrailViewer.tscn` | CREATE_IN_HOUSE | owner-set original rights | Hùng received purpose before approval; separate Tuấn permission. |
| PR22 | Hai packet escalation C24/C25 | UI / DOCUMENT | S13 / S13_TWO_DESKS | P0 | YES | YES | NO | — | FX10 | raw/pending/verified | `TwoPacketCompare.tscn` | CREATE_IN_HOUSE | owner-set original rights | Endpoint, case scope, request/response; no X by account match. |
| PR23 | Khay custody Vũ/tem nhận | 3D INTERACTIVE PROP | S09, S13, S15, S16, S18 / S09_SCOPED_INTAKE S13_TWO_DESKS S15_CUSTODY_DESK S16_THREE_ORIGINS S18_TWO_TRAYS | P0 | YES | YES | YES | AN03 | FX19 FX10 | empty/queued/received/auth | `EvidenceTray.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Police A already held from E28. |
| PR24 | Ba packet D1/D2/annex | UI / DOCUMENT | S16, S18 / S16_THREE_ORIGINS S18_TWO_TRAYS | P0 | YES | YES | NO | AN03 | FX10 FX15 | requested/received/auth/mismatch | `ThreeOriginsViewer.tscn` | CREATE_IN_HOUSE | owner-set original rights | Original Nam receiver-side reply, distinct L/H decisions, exact broker annex. |
| PR25 | Sổ Nam fragments | 3D INTERACTIVE PROP | S17 / S17_ROOM_JAM | P1 | YES | NO | YES | AN03 | FX10 | closed/open/pages seen | `NotebookInteractable.tscn` | CREATE_IN_HOUSE | owner-set original rights | Page flags only; no clue-count door unlock. |
| PR26 | Ngăn kéo, radio | 3D INTERACTIVE PROP | S17 / S17_ROOM_JAM | P1 | YES | YES | YES | AN12 | FX20 FX21 | closed/open; off/static | `DrawerRadioSet.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Only legit accessible objects; no new command proof. |
| PR27 | Xe đẩy, thùng, kệ logistics | 3D PROP | S04, S08, S12 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S12_FALSE_APEX_SWAP | P1 | NO | YES | YES | AN13 | FX22 | A/B position | `LogisticsClutter.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Routine movement can change background without evidence. |
| PR28 | Biển/quầy bệnh viện, trolley | 3D PROP | S04, S10, S11, S14 / S04_SCAN_MISMATCH S10_FORM_VERSION S11_TIME_COMPARE S14_RETURN_CHANGED | P1 | NO | YES | YES | AN13 | FX22 | normal/scope changed | `HospitalClutter.tscn` | NEED_TO_FIND | verify commercial permission + attribution | No complex medical equipment or operating room. |
| PR29 | Đồng hồ, notice board | 3D PROP | S02, S08, S10, S14, S15 / S02_CLASS_ROUTINE S08_PRINT_COMPARE S10_FORM_VERSION S14_RETURN_CHANGED S15_CUSTODY_DESK | P1 | YES | YES | YES | — | FX10 | current notice/access status | `NoticeInteractable.tscn` | CREATE_IN_HOUSE | owner-set original rights | Warnings have actual receipt; wall clock is diegetic. |
| PR30 | Bữa ăn/biên lai tiền sinh viên | 3D PROP | S03, S05 / S03_JOB_ACCEPT S05_ORDINARY_RETURN | P1 | YES | YES | YES | AN03 | FX09 | ordered/paid | `MealProp.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Budget decision, not crime clue. |
| CH01 | Bắc first-person hands/body shadow | CHARACTER | S01, S02, S03, S04, S05, S06, S07, S08, S09, S10, S11, S12, S13, S14, S15, S16, S17, S18 / S01_POWER_REPAIR S02_CLASS_ROUTINE S03_JOB_ACCEPT S04_SCAN_MISMATCH S05_ORDINARY_RETURN S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S08_PRINT_COMPARE S09_SCOPED_INTAKE S10_FORM_VERSION S11_TIME_COMPARE S12_FALSE_APEX_SWAP S13_TWO_DESKS S14_RETURN_CHANGED S15_CUSTODY_DESK S16_THREE_ORIGINS S17_ROOM_JAM S18_TWO_TRAYS | P0 | NO | YES | YES | AN03 AN06 AN08 AN10 | FX23 | hands empty/phone/paper | `PlayerHands.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Never require full cutscene rig for proof. |
| CH02 | Lan | CHARACTER | S01, S05, S07, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S07_COMPARE_AND_CHOOSE S17_ROOM_JAM | P0 | YES | YES | YES | AN01 AN02 AN05 | FX23 | ordinary/stair helper | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Door release cause in S17. |
| CH03 | Nam | CHARACTER | S01, S05, S17, S18 / S01_POWER_REPAIR S05_ORDINARY_RETURN S17_ROOM_JAM S18_TWO_TRAYS | P0 | YES | YES | YES | AN01 AN02 AN08 | FX23 | ordinary/optional late return | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | No omniscient reactions or villain-only outfit. |
| CH04 | Linh | CHARACTER | S02, S05 / S02_CLASS_ROUTINE S05_ORDINARY_RETURN | P1 | YES | YES | YES | AN01 AN02 AN03 | FX23 | class/message | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Student variant. |
| CH05 | Minh | CHARACTER | S02, S03, S07, S14 / S02_CLASS_ROUTINE S03_JOB_ACCEPT S07_COMPARE_AND_CHOOSE S14_RETURN_CHANGED | P1 | YES | YES | YES | AN01 AN02 AN06 | FX23 | class/call/report | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Outsider; exact forwarded payload matters. |
| CH06 | Tuấn | CHARACTER | S04, S06, S08, S12 / S04_SCAN_MISMATCH S06_AUDIT_FORM S08_PRINT_COMPARE S12_FALSE_APEX_SWAP | P1 | YES | YES | YES | AN01 AN02 AN07 | FX23 | routine/phone | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Dispatch uniform variant; not core villain. |
| CH07 | Đức | CHARACTER | S08 / S08_PRINT_COMPARE | P1 | YES | YES | YES | AN01 AN02 AN06 AN03 | FX23 | work/offer | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Can reuse generic body with distinct face/clothes. |
| CH08 | Huyền | CHARACTER | S10 / S10_FORM_VERSION | P1 | YES | YES | YES | AN01 AN03 AN07 | FX23 | counter/review | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Competent procedural reaction. |
| CH09 | Thảo | CHARACTER | S10 / S10_FORM_VERSION | P1 | YES | YES | YES | AN01 AN02 AN03 | FX23 | optional testimony | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | No secret whole-network briefing. |
| CH10 | Vũ | CHARACTER | S09, S11, S13, S15, S16, S18 / S09_SCOPED_INTAKE S11_TIME_COMPARE S13_TWO_DESKS S15_CUSTODY_DESK S16_THREE_ORIGINS S18_TWO_TRAYS | P1 | YES | YES | YES | AN01 AN03 AN06 | FX23 | phone/desk | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Can be voice plus desk portrait early, full model P1. |
| CH11 | Hùng/Khoa scoped source | CHARACTER | S16 / S16_THREE_ORIGINS | P2 | YES | YES | YES | AN01 AN06 | FX23 | phone/brief intake | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Voice/phone portrait placeholder accepted; two people must stay distinct. |
| CH12 | Background worker/student/receiver | NPC VARIANT | S02, S03, S04, S05, S10, S12 / S02_CLASS_ROUTINE S03_JOB_ACCEPT S04_SCAN_MISMATCH S05_ORDINARY_RETURN S10_FORM_VERSION S12_FALSE_APEX_SWAP | P1 | NO | YES | YES | AN01 AN02 AN13 | FX23 | school/warehouse/hospital | `NPC_Base.tscn` | NEED_TO_FIND | verify commercial permission + attribution | Small wardrobe variants; no crowd AI required. |
| PR31 | Vali/chìa khóa thuê trọ | 3D INTERACTIVE PROP | S01, S05 / S01_POWER_REPAIR S05_ORDINARY_RETURN | P1 | YES | YES | YES | AN03 | FX24 | carried/placed; key handed-over | `CarryProp.tscn` | NEED_TO_FIND | verify commercial permission + attribution | S01 entry and Lan handing a physical key; no hidden clue. |
| PR32 | Phone/job/source status screens | UI / DOCUMENT | S01, S02, S03, S04, S05, S06, S07, S08, S09, S11, S13, S14, S15, S16, S17, S18 / S01_POWER_REPAIR S02_CLASS_ROUTINE S03_JOB_ACCEPT S04_SCAN_MISMATCH S05_ORDINARY_RETURN S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S08_PRINT_COMPARE S09_SCOPED_INTAKE S11_TIME_COMPARE S13_TWO_DESKS S14_RETURN_CHANGED S15_CUSTODY_DESK S16_THREE_ORIGINS S17_ROOM_JAM S18_TWO_TRAYS | P0 | YES | YES | NO | — | FX11 FX12 | original/observed/queued/received/authenticated; access denied | `PhoneUI.tscn` | CREATE_IN_HOUSE | owner-set original rights | Content separate from PR08/PR16 phone 3D shells; actual receipts only. |
| PR33 | Ending screen and causal custody layout | UI / DOCUMENT | S18 / S18_TWO_TRAYS | P1 | YES | YES | NO | — | FX19 | G0–G6; preserved/missing; decisive cause | `EndingScreen.tscn` | CREATE_IN_HOUSE | owner-set original rights | Displays existing slots; no new evidence or omniscient confession. |
| MT01 | Trọ plaster/tile/wood/metal/damp | MATERIAL / DECAL | S01, S05, S06, S07, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S17_ROOM_JAM | P1 | NO | YES | NO | — | — | dry/damp/worn | `MaterialLibrary` | CREATE_IN_HOUSE | owner-set original rights | 1K default, 2K hero close-up only. |
| MT02 | Kho concrete/cardboard/plastic/labels | MATERIAL / DECAL | S04, S08, S12 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S12_FALSE_APEX_SWAP | P1 | NO | YES | NO | — | — | ordinary/worn | `MaterialLibrary` | CREATE_IN_HOUSE | owner-set original rights | Readability of labels matters more than clutter. |
| MT03 | Hospital clean tile/fluorescent/signs | MATERIAL / DECAL | S10, S11, S13, S14 / S10_FORM_VERSION S11_TIME_COMPARE S13_TWO_DESKS S14_RETURN_CHANGED | P1 | NO | YES | NO | — | — | normal/scope changed | `MaterialLibrary` | CREATE_IN_HOUSE | owner-set original rights | Practical lighting states, no horror tint by truth. |
| MT04 | Campus/meal/office shared surfaces | MATERIAL / DECAL | S02, S03, S05, S09, S15, S16, S18 / S02_CLASS_ROUTINE S03_JOB_ACCEPT S05_ORDINARY_RETURN S09_SCOPED_INTAKE S15_CUSTODY_DESK S16_THREE_ORIGINS S18_TWO_TRAYS | P2 | NO | YES | NO | — | — | day/evening | `MaterialLibrary` | CREATE_IN_HOUSE | owner-set original rights | Reuse base PBR set. |

## Scene-by-scene acquisition and implementation

Each S## uses the one signature event shown in the heading; staged MICRO and DISCOVERY nodes in EVENT_IMPLEMENTATION_SPEC use the same scene bundle. Props here are visual instances; the last fields point to reusable components.

### S01 — `S01_POWER_REPAIR`

- **3D ARCHITECTURE:** AR01.
- **3D PROPS / INTERACTIVE PROPS:** PR03 PR04 PR05 PR06 PR07 PR08 PR01 PR31 PR32.
- **CHARACTERS:** CH01 CH02 CH03.
- **NPC VARIANTS:** CH12.
- **MATERIALS:** MT01.
- **DECALS:** MT01.
- **UI / DOCUMENTS:** PR07 PR08.
- **AMBIENCE:** AU01 AU02.
- **EVENT SFX:** FX01 FX06 FX07 FX08 FX11 FX23 FX24.
- **VOICE / DIALOGUE REQUIREMENTS:** Lan, Nam, Bắc short contextual; subtitles first.
- **ANIMATIONS:** AN01 AN02 AN05 AN08.
- **LIGHTING / VFX:** fault→working desk light; normal alley.
- **COLLISION / TRIGGERS:** room door/socket raycast, room entry Area3D.
- **REUSABLE SYSTEM:** DoorInteractable SocketInteractable PhoneInteractable LightController.
- **SPECIAL IMPLEMENTATION NEEDS:** Card C28 optional, socket repair source of power restoration..

### S02 — `S02_CLASS_ROUTINE`

- **3D ARCHITECTURE:** AR02.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR09 PR29.
- **CHARACTERS:** CH01 CH04 CH05.
- **NPC VARIANTS:** CH12 student.
- **MATERIALS:** MT04.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR08 PR09.
- **AMBIENCE:** AU03.
- **EVENT SFX:** FX06 FX09 FX11 FX23.
- **VOICE / DIALOGUE REQUIREMENTS:** Linh/Minh class barks; phone texts.
- **ANIMATIONS:** AN01 AN02 AN04.
- **LIGHTING / VFX:** ordinary classroom daylight.
- **COLLISION / TRIGGERS:** class entry, seat/socket collision.
- **REUSABLE SYSTEM:** PhoneInteractable NoticeInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** C07 history optional, no crime reveal..

### S03 — `S03_JOB_ACCEPT`

- **3D ARCHITECTURE:** AR03.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR30.
- **CHARACTERS:** CH01 CH05.
- **NPC VARIANTS:** CH12 student.
- **MATERIALS:** MT04.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR08 PR30.
- **AMBIENCE:** AU04.
- **EVENT SFX:** FX09 FX11.
- **VOICE / DIALOGUE REQUIREMENTS:** Minh offer, Bắc acceptance; subtitle.
- **ANIMATIONS:** AN01 AN03 AN06.
- **LIGHTING / VFX:** meal/daylight.
- **COLLISION / TRIGGERS:** table/phone raycast; acceptance confirmation.
- **REUSABLE SYSTEM:** PhoneInteractable MealProp.
- **SPECIAL IMPLEMENTATION NEEDS:** Once-charge accept/travel; decline can reopen in window..

### S04 — `S04_SCAN_MISMATCH`

- **3D ARCHITECTURE:** AR04 AR05.
- **3D PROPS / INTERACTIVE PROPS:** PR10 PR11 PR12 PR13 PR14 PR27 PR28.
- **CHARACTERS:** CH01 CH06.
- **NPC VARIANTS:** CH12 worker/receiver.
- **MATERIALS:** MT02 MT03.
- **DECALS:** labels worn but readable.
- **UI / DOCUMENTS:** PR13 PR14.
- **AMBIENCE:** AU05 AU06.
- **EVENT SFX:** FX10 FX13 FX14 FX15 FX16 FX22 FX23.
- **VOICE / DIALOGUE REQUIREMENTS:** receiver short mismatch; Tuấn routine bark.
- **ANIMATIONS:** AN02 AN07 AN10 AN11 AN13.
- **LIGHTING / VFX:** practical dispatch/receiver.
- **COLLISION / TRIGGERS:** scanner Area3D, pouch sealed collision, receiver trigger.
- **REUSABLE SYSTEM:** ScannerInteractable PrinterInteractable DocumentInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** Original receipt13:52; C04 only label-visible observation..

### S05 — `S05_ORDINARY_RETURN`

- **3D ARCHITECTURE:** AR01 AR03.
- **3D PROPS / INTERACTIVE PROPS:** PR03 PR05 PR06 PR07 PR08 PR30 PR31 PR32.
- **CHARACTERS:** CH01 CH02 CH03 CH04.
- **NPC VARIANTS:** CH12 neighbor.
- **MATERIALS:** MT01 MT04.
- **DECALS:** ordinary wear.
- **UI / DOCUMENTS:** PR07 PR08.
- **AMBIENCE:** AU01 AU02 AU04.
- **EVENT SFX:** FX08 FX09 FX11 FX23.
- **VOICE / DIALOGUE REQUIREMENTS:** Lan/Nam everyday lines; Linh text.
- **ANIMATIONS:** AN01 AN02 AN03 AN08.
- **LIGHTING / VFX:** meal→evening home.
- **COLLISION / TRIGGERS:** meal and repaired plug raycast.
- **REUSABLE SYSTEM:** PhoneInteractable SocketInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** No new major clue; audit after ordinary room beat..

### S06 — `S06_AUDIT_FORM`

- **3D ARCHITECTURE:** AR01.
- **3D PROPS / INTERACTIVE PROPS:** PR06 PR08 PR13.
- **CHARACTERS:** CH01 CH06 voice-only.
- **NPC VARIANTS:** none.
- **MATERIALS:** MT01.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR08 PR13.
- **AMBIENCE:** AU02.
- **EVENT SFX:** FX11 FX12.
- **VOICE / DIALOGUE REQUIREMENTS:** Tuấn call and conditional Bắc reply.
- **ANIMATIONS:** AN06.
- **LIGHTING / VFX:** room evening practical lamp.
- **COLLISION / TRIGGERS:** phone notification trigger.
- **REUSABLE SYSTEM:** PhoneInteractable DocumentInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** Payment HOLD, form compare, wait98m once..

### S07 — `S07_COMPARE_AND_CHOOSE`

- **3D ARCHITECTURE:** AR01.
- **3D PROPS / INTERACTIVE PROPS:** PR06 PR08 PR13.
- **CHARACTERS:** CH01 CH05 voice/text.
- **NPC VARIANTS:** none.
- **MATERIALS:** MT01.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR08 PR13.
- **AMBIENCE:** AU02.
- **EVENT SFX:** FX11 FX12.
- **VOICE / DIALOGUE REQUIREMENTS:** Minh exact send/reply variants.
- **ANIMATIONS:** AN06.
- **LIGHTING / VFX:** room night/hallway lamp.
- **COLLISION / TRIGGERS:** phone compare/send raycast.
- **REUSABLE SYSTEM:** PhoneInteractable TwoPacketCompare.
- **SPECIAL IMPLEMENTATION NEEDS:** G0 early stop or D+1; disclosure payload exact..

### S08 — `S08_PRINT_COMPARE`

- **3D ARCHITECTURE:** AR04.
- **3D PROPS / INTERACTIVE PROPS:** PR11 PR12 PR14 PR15 PR16 PR17 PR27 PR29.
- **CHARACTERS:** CH01 CH06 CH07.
- **NPC VARIANTS:** CH12 warehouse worker.
- **MATERIALS:** MT02.
- **DECALS:** routing sticker variants.
- **UI / DOCUMENTS:** PR15 PR17 PR29.
- **AMBIENCE:** AU05.
- **EVENT SFX:** FX10 FX11 FX14 FX15 FX16 FX17 FX23.
- **VOICE / DIALOGUE REQUIREMENTS:** Đức bounded offer, Bắc question.
- **ANIMATIONS:** AN01 AN02 AN03 AN06 AN11.
- **LIGHTING / VFX:** warehouse practical morning.
- **COLLISION / TRIGGERS:** printer page/compare, Đức offer Area3D.
- **REUSABLE SYSTEM:** PrinterInteractable VersionCompare PhoneInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** Warning09:25; C18 direct09:45 or scoped police route..

### S09 — `S09_SCOPED_INTAKE`

- **3D ARCHITECTURE:** AR04 AR07.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR13 PR17 PR23.
- **CHARACTERS:** CH01 CH10 phone.
- **NPC VARIANTS:** none.
- **MATERIALS:** MT02 MT04.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR13 PR17 PR23.
- **AMBIENCE:** AU05 AU07.
- **EVENT SFX:** FX11 FX12 FX19.
- **VOICE / DIALOGUE REQUIREMENTS:** Vũ sourced questions, Bắc scoped reply.
- **ANIMATIONS:** AN06.
- **LIGHTING / VFX:** office/phone normal.
- **COLLISION / TRIGGERS:** phone source selector and receipt trigger.
- **REUSABLE SYSTEM:** PhoneInteractable EvidenceTray.
- **SPECIAL IMPLEMENTATION NEEDS:** C17 group10:15; q-relative C18/C19; A already preserved..

### S10 — `S10_FORM_VERSION`

- **3D ARCHITECTURE:** AR06.
- **3D PROPS / INTERACTIVE PROPS:** PR12 PR18 PR19 PR28 PR29.
- **CHARACTERS:** CH01 CH08 CH09.
- **NPC VARIANTS:** CH12 hospital.
- **MATERIALS:** MT03.
- **DECALS:** clean signage/scope variant.
- **UI / DOCUMENTS:** PR18 PR19.
- **AMBIENCE:** AU06.
- **EVENT SFX:** FX10 FX15 FX16 FX22.
- **VOICE / DIALOGUE REQUIREMENTS:** Huyền limited; optional Thảo firsthand.
- **ANIMATIONS:** AN01 AN03 AN07 AN11.
- **LIGHTING / VFX:** fluorescent review counter.
- **COLLISION / TRIGGERS:** version tray raycast; Thảo area before11:30.
- **REUSABLE SYSTEM:** VersionCompare AccessStateProp.
- **SPECIAL IMPLEMENTATION NEEDS:** C12 or C15 same B proposition; no illegal access..

### S11 — `S11_TIME_COMPARE`

- **3D ARCHITECTURE:** AR06 AR07.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR13 PR20.
- **CHARACTERS:** CH01 CH10 phone.
- **NPC VARIANTS:** none.
- **MATERIALS:** MT03 MT04.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR20 PR13.
- **AMBIENCE:** AU06 AU07.
- **EVENT SFX:** FX10 FX11.
- **VOICE / DIALOGUE REQUIREMENTS:** Vũ timestamp prompt, Bắc conditional observation.
- **ANIMATIONS:** AN03 AN06.
- **LIGHTING / VFX:** neutral quiet point.
- **COLLISION / TRIGGERS:** timeline cards UI interact.
- **REUSABLE SYSTEM:** TimelineCompare DocumentInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** Source time distinct observed_at; wrong retry0..

### S12 — `S12_FALSE_APEX_SWAP`

- **3D ARCHITECTURE:** AR04.
- **3D PROPS / INTERACTIVE PROPS:** PR11 PR14 PR15 PR21 PR27.
- **CHARACTERS:** CH01 CH06.
- **NPC VARIANTS:** CH12 worker.
- **MATERIALS:** MT02.
- **DECALS:** ordinary scuffs.
- **UI / DOCUMENTS:** PR21 PR15.
- **AMBIENCE:** AU05.
- **EVENT SFX:** FX10 FX14 FX17 FX23.
- **VOICE / DIALOGUE REQUIREMENTS:** Tuấn routine, Vũ recap voice.
- **ANIMATIONS:** AN01 AN02 AN07.
- **LIGHTING / VFX:** normal dispatch.
- **COLLISION / TRIGGERS:** terminal permission audit raycast.
- **REUSABLE SYSTEM:** AuditTrailViewer ScreenInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** C20 fast recap vs full; C22 auth later14:55..

### S13 — `S13_TWO_DESKS`

- **3D ARCHITECTURE:** AR07.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR22 PR23.
- **CHARACTERS:** CH01 CH10.
- **NPC VARIANTS:** none.
- **MATERIALS:** MT04.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR22 PR23.
- **AMBIENCE:** AU07.
- **EVENT SFX:** FX10 FX11 FX19.
- **VOICE / DIALOGUE REQUIREMENTS:** Vũ scoped inference reaction.
- **ANIMATIONS:** AN01 AN03 AN06.
- **LIGHTING / VFX:** practical desk light.
- **COLLISION / TRIGGERS:** two original packet compare.
- **REUSABLE SYSTEM:** TwoPacketCompare EvidenceTray.
- **SPECIAL IMPLEMENTATION NEEDS:** Private X wrong may coexist police X true..

### S14 — `S14_RETURN_CHANGED`

- **3D ARCHITECTURE:** AR04 AR06 AR07.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR14 PR19 PR29.
- **CHARACTERS:** CH01 CH05 voice/text.
- **NPC VARIANTS:** CH12 routine.
- **MATERIALS:** MT02 MT03.
- **DECALS:** scope/access signage change.
- **UI / DOCUMENTS:** PR08 PR19 PR29.
- **AMBIENCE:** AU05 AU06 AU07.
- **EVENT SFX:** FX11 FX12 FX18.
- **VOICE / DIALOGUE REQUIREMENTS:** Minh payload-limited reply.
- **ANIMATIONS:** AN02 AN06 AN14.
- **LIGHTING / VFX:** ordinary closure; no horror transformation.
- **COLLISION / TRIGGERS:** access terminal/notice interaction.
- **REUSABLE SYSTEM:** AccessStateProp NoticeInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** Local closure visuals, no evidence deletion; warning14:00..

### S15 — `S15_CUSTODY_DESK`

- **3D ARCHITECTURE:** AR07.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR23 PR29.
- **CHARACTERS:** CH01 CH10.
- **NPC VARIANTS:** none.
- **MATERIALS:** MT04.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR23 PR08.
- **AMBIENCE:** AU07.
- **EVENT SFX:** FX10 FX11 FX19.
- **VOICE / DIALOGUE REQUIREMENTS:** Vũ provenance dialogue.
- **ANIMATIONS:** AN01 AN03 AN06.
- **LIGHTING / VFX:** desk task light.
- **COLLISION / TRIGGERS:** tray/phone source commit.
- **REUSABLE SYSTEM:** EvidenceTray PhoneInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** E38 actual after raw authentication; no scene-completion grant..

### S16 — `S16_THREE_ORIGINS`

- **3D ARCHITECTURE:** AR07.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR12 PR23 PR24.
- **CHARACTERS:** CH01 CH10 CH11 voice/portrait.
- **NPC VARIANTS:** none.
- **MATERIALS:** MT04.
- **DECALS:** none.
- **UI / DOCUMENTS:** PR24 PR23.
- **AMBIENCE:** AU07.
- **EVENT SFX:** FX10 FX11 FX15 FX19.
- **VOICE / DIALOGUE REQUIREMENTS:** Vũ manager/broker scoped calls; distinct voices.
- **ANIMATIONS:** AN01 AN03 AN06 AN11.
- **LIGHTING / VFX:** desk/printer normal.
- **COLLISION / TRIGGERS:** three packet compare, source receipt triggers.
- **REUSABLE SYSTEM:** ThreeOriginsViewer EvidenceTray PrinterInteractable.
- **SPECIAL IMPLEMENTATION NEEDS:** Distinct L/H and broker scope match; X_COMMAND from raw before C4..

### S17 — `S17_ROOM_JAM`

- **3D ARCHITECTURE:** AR01.
- **3D PROPS / INTERACTIVE PROPS:** PR01 PR02 PR03 PR04 PR05 PR06 PR07 PR25 PR26.
- **CHARACTERS:** CH01 CH02 CH03.
- **NPC VARIANTS:** none.
- **MATERIALS:** MT01.
- **DECALS:** damp old paint, not supernatural.
- **UI / DOCUMENTS:** PR25 PR07 PR08.
- **AMBIENCE:** AU01 AU02.
- **EVENT SFX:** FX01 FX02 FX03 FX04 FX05 FX06 FX07 FX20 FX21 FX23.
- **VOICE / DIALOGUE REQUIREMENTS:** Lan outside-door helper; Nam only if witnessed.
- **ANIMATIONS:** AN01 AN02 AN03 AN05 AN08 AN12 AN14.
- **LIGHTING / VFX:** normal/flicker/off; authored electrical fault.
- **COLLISION / TRIGGERS:** door/latch/knock/notebook page Area3D.
- **REUSABLE SYSTEM:** DoorInteractable LatchInteractable NotebookInteractable LightController.
- **SPECIAL IMPLEMENTATION NEEDS:** Optional bypass; physical release, no three-clue lock; save stage..

### S18 — `S18_TWO_TRAYS`

- **3D ARCHITECTURE:** AR07 AR01.
- **3D PROPS / INTERACTIVE PROPS:** PR08 PR23 PR24 PR32 PR33.
- **CHARACTERS:** CH01 CH10 CH03 conditional.
- **NPC VARIANTS:** CH12 optional epilogue.
- **MATERIALS:** MT01 MT04.
- **DECALS:** prior location wear unchanged.
- **UI / DOCUMENTS:** PR23 PR24 PR08 PR32 PR33.
- **AMBIENCE:** AU07 AU01.
- **EVENT SFX:** FX10 FX11 FX15 FX19.
- **VOICE / DIALOGUE REQUIREMENTS:** Vũ outcome by custody; no omniscient villain monologue.
- **ANIMATIONS:** AN01 AN03 AN06.
- **LIGHTING / VFX:** normal office→city ambience.
- **COLLISION / TRIGGERS:** custody tray/confirm terminal trigger.
- **REUSABLE SYSTEM:** EvidenceTray ThreeOriginsViewer.
- **SPECIAL IMPLEMENTATION NEEDS:** P4 resolver; shown slots stay held in partial endings..

## Audio manifest — exact reusable sound families

All sound sources remain unverified. `YES` means one library family should be reused with gain/distance/variant tuning; do not assume the same recording must be literally repeated. Voice/dialogue is listed per scene above; subtitle-first P0, record VO only after line lock. The scene-specific paper/door timing is an authored event cue, not a new sound asset.

| Audio ID | Family | Type | Used in / event IDs | Priority | Reusable? | Source status | License requirement | State or spatial requirement |
|---|---|---|---|---|---|---|---|---|
| AU01 | Hanoi alley motorbikes/voices/horn | AMBIENCE | S01, S05, S07, S17, S18 / S01_POWER_REPAIR S05_ORDINARY_RETURN S07_COMPARE_AND_CHOOSE S17_ROOM_JAM S18_TWO_TRAYS | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| AU02 | Boarding house fan/neighbors/stairs | AMBIENCE | S01, S05, S06, S07, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| AU03 | University class/room tone | AMBIENCE | S02 / S02_CLASS_ROUTINE | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| AU04 | Student meal street/utensils | AMBIENCE | S03, S05 / S03_JOB_ACCEPT S05_ORDINARY_RETURN | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| AU05 | Logistics office/warehouse hum | AMBIENCE | S04, S08, S09, S12 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S09_SCOPED_INTAKE S12_FALSE_APEX_SWAP | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| AU06 | Hospital corridor HVAC/PA | AMBIENCE | S04, S10, S11, S13, S14 / S04_SCAN_MISMATCH S10_FORM_VERSION S11_TIME_COMPARE S13_TWO_DESKS S14_RETURN_CHANGED | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| AU07 | Police office low room tone | AMBIENCE | S09, S11, S13, S15, S16, S18 / S09_SCOPED_INTAKE S11_TIME_COMPARE S13_TWO_DESKS S15_CUSTODY_DESK S16_THREE_ORIGINS S18_TWO_TRAYS | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX01 | Door soft close | SFX | S01, S05, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX02 | Door slam | SFX | S17 / S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX03 | Latch click/reset | SFX | S17 / S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX04 | Locked/jammed handle rattle | SFX | S17 / S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX05 | Knock/door call | SFX | S17 / S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX06 | Fluorescent buzz/flicker | SFX | S01, S02, S14, S17 / S01_POWER_REPAIR S02_CLASS_ROUTINE S14_RETURN_CHANGED S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX07 | Switch/power return | SFX | S01, S05, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX08 | Fan motor hum | SFX | S01, S05, S06, S17 / S01_POWER_REPAIR S05_ORDINARY_RETURN S06_AUDIT_FORM S17_ROOM_JAM | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX09 | Chair scrape/dishes/meal handling | SFX | S02, S03, S05 / S02_CLASS_ROUTINE S03_JOB_ACCEPT S05_ORDINARY_RETURN | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX10 | Paper pickup/page turn/document UI | SFX | S04, S08, S09, S10, S11, S12, S13, S15, S16, S17, S18 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S09_SCOPED_INTAKE S10_FORM_VERSION S11_TIME_COMPARE S12_FALSE_APEX_SWAP S13_TWO_DESKS S15_CUSTODY_DESK S16_THREE_ORIGINS S17_ROOM_JAM S18_TWO_TRAYS | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX11 | Phone vibration | SFX | S01, S02, S03, S05, S06, S07, S09, S13, S14, S15, S16 / S01_POWER_REPAIR S02_CLASS_ROUTINE S03_JOB_ACCEPT S05_ORDINARY_RETURN S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S09_SCOPED_INTAKE S13_TWO_DESKS S14_RETURN_CHANGED S15_CUSTODY_DESK S16_THREE_ORIGINS | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX12 | Phone notification/call connect | SFX | S06, S07, S09, S14, S15, S16 / S06_AUDIT_FORM S07_COMPARE_AND_CHOOSE S09_SCOPED_INTAKE S14_RETURN_CHANGED S15_CUSTODY_DESK S16_THREE_ORIGINS | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX13 | Pouch/cardboard handling | SFX | S04 / S04_SCAN_MISMATCH | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX14 | Scanner normal/mismatch beep pair | SFX | S04, S08, S12 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S12_FALSE_APEX_SWAP | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX15 | Printer feed/receipt output | SFX | S04, S08, S10, S16, S18 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S10_FORM_VERSION S16_THREE_ORIGINS S18_TWO_TRAYS | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX16 | Paper drop/tray slide | SFX | S04, S08, S10, S16 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S10_FORM_VERSION S16_THREE_ORIGINS | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX17 | Keyboard/terminal key | SFX | S04, S08, S12, S14 / S04_SCAN_MISMATCH S08_PRINT_COMPARE S12_FALSE_APEX_SWAP S14_RETURN_CHANGED | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX18 | Badge/access denied | SFX | S14 / S14_RETURN_CHANGED | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX19 | Evidence stamp/seal | SFX | S09, S15, S16, S18 / S09_SCOPED_INTAKE S15_CUSTODY_DESK S16_THREE_ORIGINS S18_TWO_TRAYS | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX20 | Drawer slide | SFX | S17 / S17_ROOM_JAM | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX21 | Radio static/room-tone dip | SFX | S17 / S17_ROOM_JAM | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX22 | Trolley wheels/concrete footsteps | SFX | S04, S10, S12, S14 / S04_SCAN_MISMATCH S10_FORM_VERSION S12_FALSE_APEX_SWAP S14_RETURN_CHANGED | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX23 | Footsteps corridor/stairs/concrete | SFX | S01, S02, S04, S05, S08, S10, S12, S17 / S01_POWER_REPAIR S02_CLASS_ROUTINE S04_SCAN_MISMATCH S05_ORDINARY_RETURN S08_PRINT_COMPARE S10_FORM_VERSION S12_FALSE_APEX_SWAP S17_ROOM_JAM | P0 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | 3D localized if event; area bed if ambience; save one-shot stage |
| FX24 | Key jingle/key in lock | SFX | S01, S05 / S01_POWER_REPAIR S05_ORDINARY_RETURN | P1 | YES | NEED_TO_FIND | verify commercial use, attribution, recording rights | Localized to Lan/door; one-shot handover |

### Voice and dialogue acquisition

| Voice family | Exact scene needs | Prototype | Production |
|---|---|---|---|
| VO_BAC | S03, S06–S18 conditional short reactions | subtitles + text barks | record only observed-field branches; no private-proof narration |
| VO_LAN_NAM | S01/S05 ordinary lines; S17 outside-door help/conditional witnessed reaction | subtitle or temp lines | different restrained ordinary vs tense delivery |
| VO_LINH_MINH_TUAN | S02/S03/S07/S12/S14 messages and bounded calls | subtitles/phone text | record exact disclosure variants, no extra exposition |
| VO_DUC_HUYEN_THAO | S08/S10 source-window and bounded testimony | subtitles | case-specific lines; no conspiracy knowledge |
| VO_VU_MANAGER_BROKER | S09/S11/S13/S15/S16/S18 police coordination and scoped source intake | text/phone with distinct labels | record Hùng/Khoa/broker as separate voices if audio pursued |

## Animation manifest

All animations are requirements, not existing imports. Generic retargeting accepted on compatible rigs; prototype placeholders may be simple pose/transform/hand camera motion. No choreography is allowed to be the sole evidence source.

| Animation ID | Family | NPC / events requiring it | Generic reuse? | Retarget acceptable? | Placeholder enough for prototype? | Source status | License requirement |
|---|---|---|---|---|---|---|---|
| AN01 | Idle standing/sitting | all visible NPC | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN02 | Walk/turn/look back | Lan Nam Minh Tuấn Đức background; S01 S02 S04 S08 S12 S14 S17 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN03 | Take/place/read paper | Bắc hands Huyền Thảo Vũ; S04 S08 S10 S11 S15 S16 S17 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN04 | Sit/stand | class and police S02 S13 S15 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN05 | Open/close door/knock | Lan Nam Bắc; S01 S17 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN06 | Use phone | Bắc Minh Đức Vũ; S03 S07 S08 S09 S14 S16 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN07 | Type/use workstation | Tuấn Huyền; S04 S08 S10 S12 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN08 | Inspect/repair socket | Nam Bắc; S01 S05 S17 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN09 | Fan blades simple loop | S01 S05 S06 S17 | YES | N/A | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN10 | Carry/hand sealed pouch | Bắc receiver; S04 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN11 | Printer feed/tray movement | S04 S08 S10 S16 S18 | YES | N/A | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN12 | Drawer/radio interaction | S17 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN13 | Trolley push/background route | S04 S10 S12 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |
| AN14 | Short restrained reaction/point | Tuấn Đức Huyền Minh Nam; S06 S08 S10 S14 S17 | YES | YES | YES | NEED_TO_FIND | verify commercial use/retarget permission; in-house placeholder needs owner-set rights |

## Coverage and acquisition constraints

- Model/texture and gameplay component are separately named. One Godot wrapper can use multiple models, material variants and document textures. Import source files unmodified, wrap them in `.tscn`, check pivot/scale/collision before scene placement.
- No URLs, license grants, author names or “already have” claims are invented. Record verified downloads, licenses and attribution in ASSET_SOURCES.md.
- S04 sealed pouch cannot contain discoverable crime proof. S08/S10/S12/S13/S16 document artwork must use canon exact field and source timing from CLUE_GRAPH and OBJECTIVE_TIMELINE; a pretty generic paper cannot substitute.
- S17 requires a practical latch, hand/knock interaction, Lan route or mechanical reset, plus persisted door/light/NPC stages. S18 needs evidence tray variants that preserve actual held records even in G1/G2/G4/G5.
- P0 prototype can use blockout architecture and text documents; prioritize source/custody/readability over detailed geometry. No asset acquisition begins in this block.
