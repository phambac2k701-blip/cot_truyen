# FINAL NARRATIVE AUDIT

Repo: **phambac2k701-blip/cot_truyen**  
Snapshot được kiểm định: **f17628f53e78805e739382ab8d811cea1a07edfe**  
Ngày chốt audit: **04/10/2026**  
Vai trò: lead narrative editor, mystery architect, continuity auditor, adversarial reviewer.

## Kết luận kiểm định

**HOLD — chưa đủ điều kiện khóa narrative để đưa vào production cuối.**

Xương sống nhân quả của vụ án đứng được: khủng hoảng có trước Bắc; Hùng hạ luồng công việc vì tự bảo vệ; Bắc đi vào bằng một ca làm thêm bình thường; các nguồn độc lập và cảnh sát mới có thể biến sự tò mò thành một vụ án. Không tìm thấy căn cứ để kết luận twist Nam hoàn toàn từ trên trời rơi xuống, mọi true route bất khả thi, hoặc cảnh sát phải ngu mới giữ được truyện.

Các lỗi mạnh nhất nằm ở **nghĩa của proof, cửa sổ lấy nguồn, custody, knowledge flags và tính đầy đủ của ending resolver**. Cùng một tập bằng chứng hoặc cùng một hành động hiện có thể nhận kết quả khác nhau tùy implementer đọc file nào.

Một giới hạn đặc biệt quan trọng: `FULL_SCRIPT.md` tự ghi **IN PROGRESS**, mới hoàn chỉnh **S01–S05 / Act I**. S06–S18 có blueprint, nhưng chưa có full dialogue/action script. Vì vậy đây là audit toàn bộ tài liệu hiện có, không phải chứng nhận một full script 18 scene hay một bản game đã chơi được. [FULL_SCRIPT.md:1–5](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1-L5) [FULL_SCRIPT.md:1971–1977](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1971-L1977) [SCENE_BREAKDOWN.md:1996–2007](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1996-L2007)

| Mức | Số lỗi | Ý nghĩa trong báo cáo |
|---|---:|---|
| CRITICAL | **0** | Chưa xác nhận lỗi buộc mọi route phá canon hoặc làm core mystery không thể đúng. Không nâng thiếu đặc tả thành plot hole đã xảy ra. |
| HIGH | **9** | Mâu thuẫn hoặc thiếu khóa ở proof, knowledge, ending, hoặc chặn kiểm định sản xuất. |
| MEDIUM | **12** | Fairness, provenance, transition, motivation hoặc handoff cần sửa trước implementation. |
| LOW | **3** | Sai tham chiếu, phrasing hoặc chức năng chi tiết cuối. |
| Tổng | **24** | Mỗi ID là một vấn đề riêng; các lớp audit có thể cùng trỏ về một ID. |

**Phân biệt độ chắc chắn:** “mâu thuẫn văn bản” có hai quy tắc không khớp; “thiếu khóa đặc tả” có một counterexample mà tài liệu chưa ngăn; “chặn kiểm định” là phần chưa được viết để có thể kiểm tra. Báo cáo không gọi các khoảng hở này là bug runtime đã tái hiện.

## Phạm vi đọc và thứ tự thẩm quyền

Đã đọc toàn văn cả **11 file** trong Git tree của snapshot, gồm 9 Markdown và nội dung hai `.docx`; không dùng summary thay việc đọc. Các lượt đọc chuyên biệt được đối chiếu lại với nguồn khi tổng hợp finding. Snapshot Markdown và hai DOCX được kiểm tra bằng Git blob SHA; trích dẫn bên dưới ghim vào commit nguồn để việc thêm báo cáo không làm lệch line number.

| File | Phạm vi đã đọc | Vai trò khi phân xử |
|---|---|---|
| [MASTER_GAME_BIBLE.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/MASTER_GAME_BIBLE.md) | 1–1877 | Canon và giới hạn thiết kế |
| [BACKSTAGE_CRIME_TRUTH.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/BACKSTAGE_CRIME_TRUTH.md) | 1–2432 | Sự thật khách quan, tổ chức, động cơ và culpability |
| [CHARACTER_WEB.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md) | 1–1128 | Knowledge limits và quan hệ |
| [OBJECTIVE_TIMELINE.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md) | 1–1307 | Event E01–E44, baseline, thời gian, nguồn và custody |
| [CLUE_GRAPH.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md) | 1–1234 | Clue catalog, reveal, dependence và fairness |
| [PLAYER_STORY.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md) | 1–1967 | Trình tự trải nghiệm và các nhánh |
| [ENDING_LOGIC.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md) | 1–1635 | Predicate, priority, proof và outcome |
| [SCENE_BREAKDOWN.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md) | 1–2414 | Handoff S01–S18, budget và cơ chế |
| [FULL_SCRIPT.md](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md) | 1–1977 | Thoại/action thực tế, hiện chỉ S01–S05 |
| [idea.docx](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/idea.docx) | Toàn bộ nội dung văn bản | Ý tưởng gốc; không ghi đè canon đã khóa |
| [bổ sung.docx](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/b%E1%BB%95%20sung.docx) | Toàn bộ nội dung văn bản | Bổ sung ban đầu; không ghi đè quyết định đã chốt |

Các ý brainstorm về tuổi/năm học, bản đồ khổng lồ, nhiều giấc mơ hoặc hình thức truy đuổi không được dùng để buộc tài liệu sau quay về phương án cũ. Canon hiện là Bắc 18 tuổi, sinh viên năm nhất; trường là nền đời sống; hub có giới hạn; suy luận khó nhưng thao tác đơn giản. Không thấy code, build hoặc test runtime trong tree nguồn để xác nhận các predicate đã được implement.

## Bản đồ 17 lớp audit

| Lớp | Kết quả có bằng chứng | Finding / giới hạn |
|---|---|---|
| 1. Canon | Act I giữ tuổi, đời thường, kindness thật của Nam, trường không dính conspiracy, không superhacker. Drift nằm ở proof/knowledge ở blueprint sau. | H01, H02, H06–H08 |
| 2. Causality | E01–E44 có causal spine; coincidence mở cửa, không tự giải án. Thiếu trigger cụ thể cho một số nguồn late. | H04, M02, M12; bảng event bên dưới |
| 3. Timeline | Không xác nhận teleport người/vật ở Act I. C18 được mời lấy muộn hơn cửa sổ canon; cơ chế đồng hồ chưa đồng nhất. | H04, M04, M08, L01 |
| 4. Knowledge | Bắc, Nam và police phải có state riêng. S13/S14 đang cấp tri thức quá rộng; Đức biết quá mức khi giải oan Tuấn. | H05–H08; matrices bên dưới |
| 5. Villain competence | N1 không đáng để Nam gây bạo lực; managers che báo cáo có incentive riêng. Lỗi là thông tin không có nguồn, không phải thiếu hung ác. | H07, M02, M04 |
| 6. Police competence | Vũ có case trước Bắc và được phép xác minh song song. Chưa khóa rõ custody A và rào cản truy vấn hẹp trước D0. | H05, M01, M12 |
| 7. Fairness | Có seed trước mọi nhóm reveal; payload core proof và recovery D chưa tương đương; warning có thể đến sau loss. | H02–H04, M02–M03, M07 |
| 8. Red herring | Tuấn, Hùng, Huyền, Minh, Phúc bị nghi từ hành động thật. Giải oan Tuấn đang kết luận rộng hơn dữ kiện. | H08, L02 |
| 9. True ending | Có abstract route khả thi; chưa chứng minh blind first-run. Không cần C28 hay đoán Nam sớm. | H02–H05, M02–M03, M08; simulation bên dưới |
| 10. Bad ending | Không có quy tắc “nhắn Minh là thua”. Có một terminal state thiếu outcome và mixed-leak attribution chưa kín. | H09, M05–M06, M09 |
| 11. Motivation | Minh giữ việc là động cơ hợp canon; Nam kindness thật. Forced return S17 và động cơ manager mở D cần cụ thể. | M02, M11 |
| 12. Dialogue | Chỉ S01–S05 có thoại đầy đủ để xét. Giọng Lan/Nam/Tuấn/Bắc có khác nhau; chưa đủ căn cứ nói mọi người cùng giọng. | H01; phần dialogue |
| 13. Pacing | Opening 24 phút có breather; S08/S12 lặp một phần correction; middle dày và climax chưa có actual timing. | M10, H01; budget bên dưới |
| 14. Gameplay–narrative | Puzzle chronology/permission/custody hợp truyện. Notebook Act I không giải hộ; flags và thời gian có thể phản lại điều đó. | H06, M06–M09, M11 |
| 15. Replay | C27–C29, E24 và cách Nam giữ bình thường đổi nghĩa được sau reveal. Không có bắt buộc “đoán boss” ở opening. | M07, L03; phần replay |
| 16. Scope | 93 phút trên giấy, 4 vùng chính + police micro-set, 15 named NPC ngoài Bắc. Chi phí lớn ở branch QA. | H01, M06, M08, M10; chưa có timed build |
| 17. Plot-hole attack | 45 câu hỏi, mỗi câu có verdict và bằng chứng; không dùng nhãn self-audit PASS làm bằng chứng thay event. | Bảng attack phía dưới |

## HIGH — phải xử lý trước khi khóa thiết kế cuối

### H01 — HIGH — FULL_SCRIPT chưa phải full script của game

**Loại:** chặn kiểm định sản xuất. **File/scene:** FULL_SCRIPT, S06–S18.

**Bằng chứng:** header ghi IN PROGRESS; continuation anchor chỉ xác nhận Act I S01–S05. Scene breakdown có 18 scene và full flow đến S18. [FULL_SCRIPT.md:1–5](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1-L5) [FULL_SCRIPT.md:1971–1977](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1971-L1977) [SCENE_BREAKDOWN.md:1996–2032](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1996-L2032)

**Lỗi và hậu quả:** chưa thể kiểm tra thoại late, lượng exposition thực, phản ứng khi player suy sai, transition partial, source request, thứ tự reveal cuối hay quyền player trong cinematic climax. Tự coi outline là full dialogue sẽ bỏ sót chính phần mystery khó nhất. Đây không phải bằng chứng truyện về sau chắc chắn sai, nhưng là lý do không thể ký “final validation passed”.

**Sửa ít phá hệ thống nhất:** sửa các quy tắc liên file dưới đây trước, sau đó hoàn tất S06–S18 theo outline/canon đã có. Không rewrite S01–S05 hàng loạt. Với Act I chỉ patch những dòng lifecycle/time thực sự bị finding chỉ ra. Điều kiện đóng H01: mọi nhánh có script/action/state tương ứng và có thể được đọc từ đầu đến ending mà không phải người đọc tự sáng tác phần thiếu.

### H02 — HIGH — Nghĩa A/B/C bị thu hẹp khi chuyển thành proof gates

**Loại:** thiếu khóa core mystery proof. **File/scene:** BACKSTAGE, CLUE_GRAPH, ENDING_LOGIC; S09–S13.

**Bằng chứng:** proposition A là môi giới hiến tạng bất hợp pháp + sức ép khi rút; B là cell biết và hỗ trợ hợp thức hóa các trường hợp; C là lãnh đạo biết và chủ ý hỗ trợ mạng. Nhưng gate hiện chấp nhận A=C08+C10 chronology, B=C11+(C12 hoặc C15), C=C17+(C18 hoặc C19)+C22. Các payload mô tả chronology, pattern hành chính, scope change, reclassification, finance anomaly và override chưa khóa rõ **fact phân biệt tội lõi với một vụ gian lận hành chính/tiền/điều phối khác**. [CLUE_GRAPH.md:44–49](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L44-L49) [BACKSTAGE_CRIME_TRUTH.md:1742–1752](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/BACKSTAGE_CRIME_TRUTH.md#L1742-L1752) [CLUE_GRAPH.md:93–121](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L93-L121) [ENDING_LOGIC.md:62–72](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L62-L72) [ENDING_LOGIC.md:910–948](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L910-L948)

**Tại sao là lỗi:** sự thật tác giả biết ở backstage không tự trở thành thông tin player biết. “Có can thiệp” không tự bằng “biết thỏa thuận phi pháp này và cố hỗ trợ nó”. X chung và Khải xử lý risk có thể nối các scandal nhưng chưa thay nội dung tội lõi. Đặc biệt no-Thảo route C11+C12 cần chứng minh cùng ý nghĩa với route có insider acknowledgment.

**Hậu quả:** thông minh nhất là giữ giả thuyết khác, trong khi resolver có thể coi player đã chứng minh organ network; reveal có nguy cơ được narrator/police cấp thêm sự thật sau cùng. Đây là thiếu payload được quy định, không kết luận không một lời khai tương lai nào có thể cung cấp fact đó; cũng không phải yêu cầu chứng minh theo một chuẩn pháp luật ngoài game.

**Sửa nhỏ:** khóa một bảng “proposition → fact cần chứng minh → clue chứa fact → alternative cùng nghĩa”. Bổ sung fact không kỹ thuật vào **clue hiện hữu**: thỏa thuận bất hợp pháp nào Phúc trực tiếp biết; hoàn cảnh/rút lui nào người có quyền hospital đã biết nhưng hồ sơ vẫn giữ vẻ hợp lệ; Hùng biết mục đích nào khi approve/override. Không thêm hồ sơ chứa toàn bộ âm mưu. Pattern/timestamp tiếp tục làm corroboration, không làm thay nội dung.

### H03 — HIGH — Route mất C32 được hứa cứu bằng C33+C34 nhưng vẫn thiếu D1

**Loại:** mâu thuẫn văn bản. **File/scene:** CLUE_GRAPH, PLAYER_STORY, ENDING_LOGIC, S16.

**Bằng chứng:** graph ghi C31+C32 **OR** C33+C34 → D; bảng missable và scene nói mất C32 thì C33/C34 là alternate. Ngược lại, định nghĩa D1 vẫn cần C32 hoặc equivalent manager biết command; C33/C34 nằm ở D2; “alternative clean route” lại là **C32+C33/C34**. [CLUE_GRAPH.md:788–794](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L788-L794) [CLUE_GRAPH.md:628–643](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L628-L643) [CLUE_GRAPH.md:842–843](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L842-L843) [PLAYER_STORY.md:1197–1200](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L1197-L1200) [PLAYER_STORY.md:1227–1231](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L1227-L1231) [SCENE_BREAKDOWN.md:1728–1730](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1728-L1730) [ENDING_LOGIC.md:972–1001](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L972-L1001)

**Tại sao/hậu quả:** cùng một run mất manager nhưng giữ hai records được blueprint coi là đủ, còn ending spec coi là thiếu D1. Đây là contradiction quyết định True/Cleanup, không cần build mới chứng minh.

**Sửa nhỏ:** chọn đúng một nghĩa và đồng bộ các file. Nếu giữ manager D1, alternate phải **chỉ tên nguồn manager tương đương và cửa sổ của họ**; C33/C34 chỉ thay D2. Nếu giữ pure-record recovery, chỉ rõ record hiện hữu nào xác thực được quyền approve của Nam để mang D1, và record độc lập nào mang D2. Không chữa bằng lowering D thành “trùng giờ là boss”, confession hoặc file thần kỳ.

### H04 — HIGH — C18 được mời lấy mới sau cửa sổ Đức; C19 cũng sát/sau deadline

**Loại:** mâu thuẫn timeline/handoff. **File/scene:** E32/E35, S08/S12/S13.

**Bằng chứng:** Đức E32 mở 09:30–11:00, khoảng trưa có thể mất access; C19/Yến mở 10:30–12:30. S12 diễn ~12:00–13:00 vẫn cho C18 “nếu window còn”; S13 12:30–14:00 tiếp tục offer C18/C19. S08 có optional gặp Đức nhưng PLAYER_STORY chỉ cho glimpse, chưa biến thành source exposition. [OBJECTIVE_TIMELINE.md:561–575](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L561-L575) [OBJECTIVE_TIMELINE.md:609–623](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L609-L623) [CLUE_GRAPH.md:833–835](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L833-L835) [PLAYER_STORY.md:600–605](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L600-L605) [SCENE_BREAKDOWN.md:1256–1296](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1256-L1296) [SCENE_BREAKDOWN.md:1356–1396](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1356-L1396)

**Tại sao/hậu quả:** player làm nhanh theo spine có thể chỉ được giới thiệu nguồn corroboration khi nguồn đã đóng. “Nếu window còn” chưa giải thích route nào khiến nó còn. Cùng scene có thể xử lý theo đồng hồ khách quan hoặc gate scene và cho outcome khác nhau.

**Phản biện đã kiểm:** S08 optional encounter và việc Vũ thu nguồn song song cho phép một route tồn tại; **không đủ căn cứ nói mọi True route bất khả thi hoặc Bắc phải teleport**. [SCENE_BREAKDOWN.md:901–904](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L901-L904) [OBJECTIVE_TIMELINE.md:1240–1246](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L1240-L1246)

**Sửa nhỏ:** đặt trigger lấy C18/request nguồn vào S08/E32; hoặc cho S09 nhận yêu cầu Vũ thu C19 đúng cửa sổ, với acknowledgement/timestamp. S12/S13 xác minh **bản đã lấy sáng**, không offer pickup mới sau hạn. Nếu giữ pickup muộn, phải có intervention cụ thể giữ copy/hợp tác mở; không nới deadline vô cớ trên toàn hệ thống.

### H05 — HIGH — Custody A của cảnh sát bị lẫn với việc Bắc đã nhìn/đưa clue

**Loại:** thiếu khóa institution/player state. **File/scene:** E12/E28, CASE.A, S09/S11/S15, G1/G3.

**Bằng chứng:** trước Bắc, E12 đã tạo biên bản, chronology và copies một phần liên lạc; E28 D0 tối bổ sung chronology và nói không mất. Police knowledge có withdrawal/pressure trước khi Bắc tới. Nhưng ví dụ G1 nói có C08 mà không đưa chronology sang Vũ kịp để preserve A; CASE description dựa một phần vào player có gì. [OBJECTIVE_TIMELINE.md:231–245](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L231-L245) [OBJECTIVE_TIMELINE.md:492–505](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L492-L505) [OBJECTIVE_TIMELINE.md:955–959](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L955-L959) [ENDING_LOGIC.md:62–72](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L62-L72) [ENDING_LOGIC.md:424–428](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L424-L428) [CLUE_GRAPH.md:828–829](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L828-L829)

**Tại sao/hậu quả:** Vũ không thể đánh mất chronology trong hồ sơ của chính mình chỉ vì một sinh viên chưa gặp Phúc hoặc chưa “giao lại”. Nó có thể biến cảnh sát có năng lực thành người chờ một nhiệm vụ UI, và làm lựa chọn custody ở S15 giả nếu proof vốn đã nằm ngoài quyền network.

**Phản biện đã kiểm:** E12 chỉ nói **một phần** messages, nên không mặc định A hoàn chỉnh trong mọi run. Vấn đề là tài liệu chưa chỉ rõ **fact/record còn thiếu**, không phải police buộc đã phá được toàn bộ A.

**Sửa nhỏ:** initialize institutional custody từ E12/E28; tách A_PLAYER_SEEN/UNDERSTOOD. Nếu C08 quan trọng đã bị Phúc giữ lại, nêu rõ record nào, tại sao E28 chưa nhận, disclosure mới bổ sung gì. Loại ví dụ buộc Bắc giao Vũ chronology đã thuộc Vũ. Preserved evidence không lùi trạng thái do thiếu presentation cho player.

### H06 — HIGH — S13 cấp hiểu biết Bắc/Khải dù inference chưa thành công

**Loại:** mâu thuẫn knowledge transition. **File/scene:** E36, PLAYER_STORY, S13.

**Bằng chứng:** PLAYER_STORY chỉ đặt N3_UNDERSTANDING khi A+B+C+bridge đủ; E36 đòi corroboration, không tạo evidence chỉ vì suy luận. S13 cho quyền nối C24/C25 và X_VERIFIED có điều kiện, nhưng state changes lại đặt N3_UNDERSTANDING=true và KHẢI_LAYER=true vô điều kiện. [PLAYER_STORY.md:1006–1010](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L1006-L1010) [OBJECTIVE_TIMELINE.md:625–638](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L625-L638) [SCENE_BREAKDOWN.md:1366–1387](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1366-L1387) [SCENE_BREAKDOWN.md:1420–1432](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1420-L1432) [MASTER_GAME_BIBLE.md:165–179](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/MASTER_GAME_BIBLE.md#L165-L179)

**Tại sao/hậu quả:** đã xem records không bằng đã nối đúng. Player suy sai hoặc thiếu nửa bridge vẫn có thể được scene sau cho nói/biết điều chưa đạt; notebook không cần popup cũng có thể bị hệ thống “nghĩ hộ” qua flags.

**Sửa nhỏ:** derive hai flags từ source đủ và hành động inference cụ thể. Partial/sai inference giữ hypothesis và fail-forward; không cấp certainty. KHẢI_LAYER cần đúng endpoint relation được biết/verify. Không đổi truth Khải và không chặn mọi progression chỉ vì chưa nối xong.

### H07 — HIGH — S14 nâng BARC N3 từ baseline closure; định nghĩa N3 còn đọc suy nghĩ

**Loại:** mâu thuẫn knowledge của phản diện. **File/scene:** BARC, E37, S14.

**Bằng chứng:** BARC là organization biết gì, cấm tăng vì suy luận trong đầu; E37 cần observable cross-report. S14 được vào bằng N3 **hoặc cleanup objective đạt threshold**, nhưng hậu trường mặc định Nam đọc report Bắc ở N3 và state đặt BARC N3. Định nghĩa N3 ở ENDING_LOGIC còn yêu cầu player thật sự hiểu, khiến hai người để lại cùng report nhưng nghĩ khác có thể tạo belief khác ở Nam. [ENDING_LOGIC.md:42–54](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L42-L54) [ENDING_LOGIC.md:200–203](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L200-L203) [OBJECTIVE_TIMELINE.md:641–655](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L641-L655) [SCENE_BREAKDOWN.md:1470–1471](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1470-L1471) [SCENE_BREAKDOWN.md:1514–1523](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1514-L1523) [PLAYER_STORY.md:1083–1085](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L1083-L1085)

**Tại sao/hậu quả:** baseline review/access closure cũng xảy ra nếu Bắc không nối network. Nó không chứng minh Nam đã nhận diện cậu nối hai cell. Nâng sai có thể arm late avoidance, tăng phản ứng nguy hiểm hoặc vô tình làm Nam omniscient; điều này phá canon competence thay vì tăng nó.

**Sửa nhỏ:** BARC chỉ derive từ reports/hành vi Nam nhận được; N3_UNDERSTANDING là biến Bắc riêng. Baseline S14 giữ BARC trước đó, Nam phản ứng theo information thực. Cùng adversary-visible reports phải cho cùng BARC bất kể notebook riêng của player đúng hay sai.

### H08 — HIGH — Đức biết quá mức; không có quyền reclassify bị dùng để chứng minh Tuấn không biết crime

**Loại:** knowledge breach và overclaim của red-herring correction. **File/scene:** C18/C20–C22, R5, S08/S12.

**Bằng chứng:** Đức chỉ nghi mạnh việc không sạch/liên hệ y tế, không biết core network/Nam/hospital. Nhưng graph cho Đức biết Tuấn không nằm trong nhóm “được giải thích core crime”; blueprint đặt TUAN_CORE_EXONERATED sau permission/override chain. [CHARACTER_WEB.md:267–277](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L267-L277) [CHARACTER_WEB.md:541–551](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L541-L551) [BACKSTAGE_CRIME_TRUTH.md:1288–1300](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/BACKSTAGE_CRIME_TRUTH.md#L1288-L1300) [CLUE_GRAPH.md:496–502](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L496-L502) [SCENE_BREAKDOWN.md:930–934](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L930-L934) [SCENE_BREAKDOWN.md:1281–1285](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1281-L1285) [SCENE_BREAKDOWN.md:1322–1325](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1322-L1325)

**Tại sao/hậu quả:** người không biết crime không tự biết mọi secret briefing về crime. Tuấn không phải account hạ luồng chứng minh cậu không gây E19, chưa chứng minh không biết/tiếp tay. Một player thận trọng có lý do giữ nghi ngờ, nhưng hệ thống có thể phạt họ vì chưa chấp nhận kết luận mạnh hơn evidence.

**Phản biện:** C21 và hành vi không hiểu câu hỏi giúp giảm nghi đúng hướng; canon Tuấn vô tội vẫn được giữ. Không cần đổi Tuấn thành guilty để chữa lỗi epistemic.

**Sửa nhỏ:** Đức xác nhận điều trực tiếp thấy: thời điểm Tuấn nhận job, giới hạn dữ liệu, bị loại khỏi một cuộc họp cụ thể, câu hỏi Tuấn thực sự chưa được trả lời. Tách NOT_RECLASSIFIER/giảm nghi khỏi formal core exoneration; nguồn Vũ xác minh sau hoàn tất giới hạn knowledge. Giữ trách nhiệm nghề nghiệp của Tuấn về bỏ qua bất thường.

### H09 — HIGH — Late resolver bỏ lọt state A/B/C đã giữ nhưng X chưa verify

**Loại:** thiếu khóa terminal-state coverage. **File/scene:** CASE/X, S13/S15/S18, G1/G4/G6.

**Counterexample:** A=B=C=PRESERVED, X=false, CLEANUP=LOCKED, không causal leak, không abandon. PLAYER_STORY cho miss một nửa C24/C25 mà main story vẫn tiến; S15 preserve từng bundle và chỉ verify X nếu bridge đủ. G6/G4 cần X=true; G1 cần ít nhất một A/B/C không thể preserve; G2/G3/G5 cần hành vi khác. Không predicate nào bao state này. [PLAYER_STORY.md:992–996](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L992-L996) [ENDING_LOGIC.md:78–87](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L78-L87) [SCENE_BREAKDOWN.md:1611–1623](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1611-L1623) [ENDING_LOGIC.md:278–296](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L278-L296)

**Hậu quả:** implementation phải tự bịa fallback hoặc có thể kẹt resolver. Ba vụ riêng đã được giữ mà relation chưa chứng minh là một kết quả điều tra hợp lý, không phải enum ngẫu nhiên.

**Phản biện:** S13 ghi C24/C25 mandatory có thể nhằm bảo đảm invariant. Tuy nhiên xem record không tự bằng đưa/verify relation; PLAYER_STORY còn cho miss. Đây là HIGH đặc tả, chưa có bằng chứng runtime softlock. [SCENE_BREAKDOWN.md:1382–1398](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1382-L1398)

**Sửa nhỏ:** mở G1/partial hợp lệ cho mất route cuối của relation/provenance bắt buộc, giữ thành quả ba case riêng; hoặc ghi invariant all-ABC-preserved ⇒ source-driven X verification và chứng minh nó thực sự xảy ra. Không auto-link notebook hay cho Vũ biết relation chưa nhận nguồn.

## MEDIUM — sửa trước khi script/implementation làm cứng các khoảng hở

### M01 — MEDIUM — C10 có custody độc lập nhưng chưa khóa xác minh fact độc lập

**File/scene:** C08/C10, E12/E28, SLOT A. **Loại:** provenance gap.

**Bằng chứng:** gate gọi C10 independent police chronology và đòi source ghi/verify ngoài Phúc; chronology hiện được tạo từ lời Phúc và copies liên lạc Phúc đưa. [CLUE_GRAPH.md:595–602](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L595-L602) [ENDING_LOGIC.md:910–920](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L910-L920) [OBJECTIVE_TIMELINE.md:236–243](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L236-L243) [OBJECTIVE_TIMELINE.md:496–505](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L496-L505)

**Lỗi/hậu quả:** hai nơi giữ lời kể của cùng người không tự là hai xác nhận factual độc lập. Nếu chỉ đếm clue ID, A có thể đếm cùng origin hai lần.

**Sửa nhỏ:** C10 khóa một bước kiểm chứng record hiện có: metadata/timestamp với counterpart, dấu kiểm tra tại bệnh viện, hoặc payment/appointment record có origin rõ. Không đòi một nhân chứng mới chỉ để “tin” nạn nhân; authentication có thể đủ. Tách origin, verification và custodian để Vũ không phải giả có thêm evidence.

### M02 — MEDIUM — D1/D2 thiếu scope, identity, lead và trigger hợp tác cụ thể

**File/scene:** C31–C34, manager sources, E39, S16. **Loại:** handoff gap khác H03.

**Bằng chứng:** D1 đòi current authority trên nhiều branch; manager chỉ được nói chain branch mình. C31 hiện chỉ nói contact Khải→Nam; C33 so policy change với “decision window của Nam” nhưng chưa chỉ nguồn biết window đó. S16 gọi selected manager/authored records thay vì khóa một route cụ thể. Hùng/Khoa có knowledge limits; Hùng có sợ bị bỏ làm vật tế, nhưng chưa chốt trigger để ông cung cấp C32 lúc này. [ENDING_LOGIC.md:972–1001](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L972-L1001) [CLUE_GRAPH.md:149–152](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L149-L152) [CHARACTER_WEB.md:344–358](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L344-L358) [CHARACTER_WEB.md:375–376](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L375-L376) [SCENE_BREAKDOWN.md:1651–1689](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1651-L1689)

**Lỗi/hậu quả:** contact identity + lời manager về logistics chưa tự chứng minh command nhiều branch. Player có thể biết cần “một manager” nhưng chưa được lead đến người đủ quyền; reviewer khác có thể nâng manager thành biết toàn mạng hoặc dùng timing tự xác nhận chính timing.

**Sửa nhỏ:** cho mỗi accepted D route một hàng: lead trước đó, owner, custodian, xác thực Nam endpoint, branch scope, nội dung approve/decision, corroborator độc lập, cửa sổ và intake. Cho Hùng/Khoa hợp tác do **một hành động/record hiện hữu** khiến nguy cơ bị hy sinh thành cụ thể. Không mở rộng lời khai vượt kiến thức. Hai records cùng copy một cleanup order không tự là hai origin độc lập.

### M03 — MEDIUM — Contract đòi cảnh báo trước mất route cuối; beat bắt buộc có thể đến sau

**File/scene:** E32/E33/E35, C43, S08/S10/S14. **Loại:** fairness handoff.

**Bằng chứng:** mọi permanent last-route loss phải có soft warning trước. C43 bắt buộc ở S14 13:30–15:00, sau các window 11:00/11:30/12:30; câu source sắp mất access lại optional. Đức biết chuyện ở backstage không bằng player được cảnh báo. [ENDING_LOGIC.md:1431–1435](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1431-L1435) [ENDING_LOGIC.md:1572–1575](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1572-L1575) [SCENE_BREAKDOWN.md:153–164](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L153-L164) [SCENE_BREAKDOWN.md:925–928](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L925-L928) [SCENE_BREAKDOWN.md:1463–1494](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1463-L1494)

**Lỗi/hậu quả:** một explanation sau loss không làm lựa chọn trước đó fair, nhất là accelerated leak. General clue “review từng bị thu hẹp” chưa bảo đảm player nhận ra **nguồn cuối mình có thể cứu**.

**Sửa nhỏ:** conditional required warning ở S08/S10 hoặc request với Vũ trước last usable route. Cho biết sự kiện thực — lịch tiếp nhận, thu hồi quyền, ca kết thúc — không meter hay countdown gamey. Warn lại khi leak làm deadline đổi đủ để lựa chọn trước không còn bảo đảm.

### M04 — MEDIUM — Khóa access công việc chưa giải thích mất bản snapshot Đức đã giữ

**File/scene:** E17/E32/B03, C18. **Loại:** item/custody gap.

**Bằng chứng:** Đức đã giữ phần snapshot; Khải ban đầu chưa biết anh giữ gì/ở đâu. E32 mô tả khóa quyền công việc; missable table cho C18 mất/khó lấy khoảng trưa khi access bị kiểm soát. Canon chỉ thu hồi thứ organization biết và có quyền chạm. [OBJECTIVE_TIMELINE.md:37–44](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L37-L44) [OBJECTIVE_TIMELINE.md:322–324](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L322-L324) [OBJECTIVE_TIMELINE.md:561–575](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L561-L575) [OBJECTIVE_TIMELINE.md:780–781](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L780-L781) [OBJECTIVE_TIMELINE.md:1021–1029](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L1021-L1029) [CLUE_GRAPH.md:833–834](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L833-L834)

**Lỗi/hậu quả:** thu hồi account gốc không tự xóa copy riêng. Dùng một closure flag despawn mọi C18 sẽ cho Khải năng lực ngoài quyền đã có. Chưa có bằng chứng tài liệu buộc mọi run phải xóa copy, nên đây là gap, không magic deletion đã diễn.

**Sửa nhỏ:** khóa nơi lưu: workstation/tủ công ty, hoặc copy cá nhân còn nhưng Đức rút hợp tác. Nếu thực sự bị lấy, có discovery/custody event. Bản đã giao Vũ vẫn tồn tại. Distinguish SOURCE_ACCESS, SOURCE_WILLINGNESS và COPY_CUSTODY.

### M05 — MEDIUM — DIRECT-priority có thể ghi đè leak quyết định; D-only loss chưa đồng nhất taxonomy

**File/scene:** LEAK_PATH, G2/G5/G4, S14/S17. **Loại:** causal attribution gap.

**Bằng chứng:** khi có cả hai leak, DIRECT ưu tiên, nhưng mỗi bad ending đòi leak tương ứng là nguyên nhân thực làm route cuối gãy. G5 description cho command chain gãy, trong khi summary matrix thiên về A/B/C thiếu và G4 bao command mất. [ENDING_LOGIC.md:111–117](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L111-L117) [ENDING_LOGIC.md:286–295](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L286-L295) [ENDING_LOGIC.md:872–875](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L872-L875) [ENDING_LOGIC.md:1562–1565](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1562-L1565) [SCENE_BREAKDOWN.md:1523–1526](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1523-L1526) [SCENE_BREAKDOWN.md:1813–1825](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1813-L1825)

**Counterexample/hậu quả:** Minh leak làm mất source B cuối; later direct attempt không làm mất thêm source nào. Nếu enum đổi DIRECT chỉ vì attempt, G5 không đủ causal condition, G2 không còn enum, G1 dễ blame delay sai. Nếu hai leak mất hai nguồn khác nhau, cũng chưa có policy chọn primary cause. Guard scene hiện có giúp tránh, nhưng enum contract chưa khóa guard.

**Sửa nhỏ:** LEAK_PATH là kết quả derive từ **decisive source/chain loss**, có cause/timestamp; attempt flags riêng. Định nghĩa policy khi nhiều losses và khi chỉ D mất sau ABC+X đã giữ: G5 nếu direct gây loss quyết định, hoặc G4 nếu taxonomy chủ ý gom D-loss; đồng bộ mô tả/matrix. Không mặc định một lời nói hớ sau custody đã an toàn làm mất ending.

### M06 — MEDIUM — Partial route được hứa nhưng thiếu cạnh đi qua/bỏ qua stronger scenes

**File/scene:** minimum route, S11–S18 entry gates. **Loại:** transition handoff gap.

**Bằng chứng:** minimum main route chỉ cần A và B **hoặc** C để tới partial. Các entry lại đòi logistics+hosp ở S11/S12, đủ ABC fragments ở S13, N3+response ở S15, proof mạnh/late layer ở S16/S17. EL có early partial resolver, nhưng scene edges chưa nói rõ branch thiếu bundle đi đâu. [CLUE_GRAPH.md:1129–1137](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L1129-L1137) [ENDING_LOGIC.md:1341–1345](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1341-L1345) [SCENE_BREAKDOWN.md:1171–1172](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1171-L1172) [SCENE_BREAKDOWN.md:1265–1266](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1265-L1266) [SCENE_BREAKDOWN.md:1366–1367](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1366-L1367) [SCENE_BREAKDOWN.md:1567–1568](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1567-L1568) [SCENE_BREAKDOWN.md:1660–1661](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1660-L1661) [SCENE_BREAKDOWN.md:1763–1764](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1763-L1764)

**Lỗi/hậu quả:** implementer có thể phải cấp evidence miễn phí để qua gate hoặc làm player không đủ clue mắc kẹt. Chưa phải runtime softlock; outline đang thiếu phép nối từ promise tới resolver.

**Sửa nhỏ:** viết weak-route transition table: entry, scene bỏ qua, time advances, sources/custody giữ lại, outcome đủ điều kiện. Không ép partial player gặp command scene như đã hiểu Nam. Đưa early G1/late partial vào scene transitions có thật.

### M07 — MEDIUM — C03 còn trong history nhưng early-save flag có thể chặn quan sát hợp lệ về sau

**File/scene:** C03/C04, S04–S11. **Loại:** fairness/lifecycle drift.

**Bằng chứng:** receipt đã hiện Minh Trạch/account/recipient; mở Chi tiết mới đặt C03_SAVED; app vẫn giữ history. Cuối script lại nói C03/C04 chỉ tồn tại nếu lưu/quan sát đúng lúc; payoff scene dùng early flag. C04 không inspect trước bàn giao có thể mất đúng, nhưng Tuấn bắt chụp seal và chưa khóa photo có/không thấy label. [FULL_SCRIPT.md:1180–1185](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1180-L1185) [FULL_SCRIPT.md:1218–1223](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1218-L1223) [FULL_SCRIPT.md:1295–1307](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1295-L1307) [FULL_SCRIPT.md:1392–1404](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1392-L1404) [FULL_SCRIPT.md:1456–1458](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1456-L1458) [FULL_SCRIPT.md:1958–1961](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1958-L1961) [PLAYER_STORY.md:519–522](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L519-L522) [SCENE_BREAKDOWN.md:1194–1203](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1194-L1203)

**Lỗi/hậu quả:** player quay lại đọc cùng record còn hợp lệ có thể bị tính như chưa từng có fact. Khó biến thành bấm đúng thời điểm thay vì suy luận. C03 không mandatory True; alternate không xóa bất công ở route này.

**Sửa nhỏ:** intentional later inspection đặt observed/equivalent bridge với timestamp mới khi history còn thật. “Không tự bật” chỉ cấm award thụ động, không cấm đọc lại hợp lệ. Khóa photo framing: label legible thì ảnh hỗ trợ C04; nếu ảnh chỉ seal, mô tả nó như vậy. C04 mất khi item đã giao vẫn hợp lý nếu không có ảnh đọc được.

### M08 — MEDIUM — Authored clock và real-time trigger chưa có một contract thống nhất

**File/scene:** MASTER time, SB travel/time, FS S01/S02/S05. **Loại:** time handoff gap.

**Bằng chứng:** blueprint dùng scene progression + choices/traversal, tránh trừng phạt từng phút đọc. Script có clock 08:35 **hoặc** đủ beats; meal exit **hoặc** phone sau 11:10; một hành động đời thường rồi nhảy 18:07. Chưa có conversion/pause/cost cho notebook, inspect, hint, phone và dialogue. [SCENE_BREAKDOWN.md:95–101](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L95-L101) [SCENE_BREAKDOWN.md:2154–2158](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L2154-L2158) [MASTER_GAME_BIBLE.md:1285–1307](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/MASTER_GAME_BIBLE.md#L1285-L1307) [FULL_SCRIPT.md:449–457](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L449-L457) [FULL_SCRIPT.md:846–856](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L846-L856) [FULL_SCRIPT.md:1931–1934](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1931-L1934)

**Lỗi/hậu quả:** cùng một slow reader có thể mất source ở implementation này, còn implementation khác thì không. Không kết luận game hiện đã phạt đọc; chưa có runtime.

**Sửa nhỏ:** khóa objective clock advance theo authored events/choices, nói rõ loại UI nào pause và action nào tốn thời gian narrative. Mỗi fast travel có cost trong bounds canon. Đọc kỹ phải giúp mystery, không âm thầm ăn last-source window; nếu chờ có chủ ý là action, telegraph cost trước.

### M09 — MEDIUM — “Dừng suy luận / theo boss giả quá lâu” chưa có hành động đo được

**File/scene:** S08/S12/S13, false-apex penalties. **Loại:** agency/knowledge gap.

**Bằng chứng:** fixation Tuấn tốn time; HUNG_FALSE_APEX có thể arm khi player dừng reasoning; theo Khải quá lâu hẹp D window. MASTER cho hypothesis riêng và hành động biểu lộ belief; time model cần decisions, không đọc tâm trí. [SCENE_BREAKDOWN.md:939–941](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L939-L941) [SCENE_BREAKDOWN.md:1325–1327](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1325-L1327) [SCENE_BREAKDOWN.md:1431–1432](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1431-L1432) [CLUE_GRAPH.md:515–520](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L515-L520) [MASTER_GAME_BIBLE.md:1183–1189](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/MASTER_GAME_BIBLE.md#L1183-L1189) [FULL_SCRIPT.md:24–32](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L24-L32)

**Lỗi/hậu quả:** không có choice/event thì không thể biết player tin Hùng hay chỉ đang cân nhắc. Phạt vì họ đọc lại, chưa click inference hoặc nghĩ sai thầm sẽ random punishment về trải nghiệm.

**Sửa nhỏ:** gắn cost vào observable choice: quay hỏi Tuấn lần nữa thay vì gặp Đức, trì hoãn intake sau cảnh báo, hoặc chọn channel không an toàn. Chốt event/time consumed và clue báo tradeoff. Private wrong hypothesis tự nó không đóng nguồn.

### M10 — MEDIUM — S08/S12 lặp correction Tuấn mà chưa có fast path

**File/scene:** S08/S12. **Loại:** pacing.

**Bằng chứng:** S08 có C20 mandatory, C22 seed và correction/exoneration; S12 lại required C20/correction rồi complete C22, trong budget 5 phút. [SCENE_BREAKDOWN.md:895–910](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L895-L910) [SCENE_BREAKDOWN.md:930–934](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L930-L934) [SCENE_BREAKDOWN.md:1268–1285](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1268-L1285) [SCENE_BREAKDOWN.md:1322–1325](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1322-L1325)

**Lỗi/hậu quả:** người đã hiểu authority chain phải nhận lại cùng chức năng ở đoạn middle vốn dày. Việc thêm Đức/C22 khiến S12 không phải scene thừa hoàn toàn; xóa nó sẽ mất leadership transition.

**Sửa nhỏ:** nếu C20 đã hiểu, S12 recap một beat ngắn và chuyển sang bằng chứng mới về Hùng/leadership. Nếu chưa, dùng bản correction đủ. Kết hợp với H08 để lần đầu chỉ giảm nghi, lần sau xác minh phần knowledge còn thiếu; không lặp cùng một “Tuấn vô tội”.

### M11 — MEDIUM — Bắt trở về trọ ở S17 trước khi D an toàn thiếu nhu cầu đủ mạnh

**File/scene:** S16→S17, Nam encounter, preservation race. **Loại:** motivation/agency gap.

**Bằng chứng:** cleanup gần; transition bắt về trọ; nhu cầu có thể chỉ lấy đồ thường/thay áo, trong lúc D lý tưởng vẫn đang verify. Vũ có tuyến an toàn, canon không buộc confrontation để kết thúc. [SCENE_BREAKDOWN.md:1712–1739](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1712-L1739) [SCENE_BREAKDOWN.md:1763–1777](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1763-L1777) [ENDING_LOGIC.md:1055–1065](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1055-L1065) [ENDING_LOGIC.md:1578–1580](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1578-L1580)

**Lỗi/hậu quả:** smart player sẽ muốn hoàn tất source handover từ police route trước. Location payoff không đủ lý do để sinh viên đang nghi hàng xóm là command core tự quay về trước custody. Chưa có script chứng minh Vũ thực sự ép cậu vào nguy hiểm; đây là transition cần khóa.

**Sửa nhỏ:** cho handover D trước encounter hoặc bypass visit nếu player lựa chọn an toàn; scene Nam có thể diễn sau custody với nghĩa cảm xúc nguyên vẹn. Nếu thật sự phải về trước, dùng nhu cầu cụ thể hiện hữu và cách bảo vệ phù hợp, không làm Bắc/Vũ bỏ phương án hiển nhiên chỉ để có climax.

### M12 — MEDIUM — Police không biết review là trạng thái; rào cản truy vấn hẹp 12 ngày chưa được giải thích

**File/scene:** E11–E13, police baseline, A5, S10. **Loại:** causality handoff cần bổ sung, không cáo buộc cảnh sát ngu.

**Bằng chứng:** Phúc kiểm tra Minh Trạch và trình báo khoảng D−14/D−12; Huyền review từ D−12. Tài liệu giải thích Vũ chưa nối vì review internal và chưa có Tân Lộ; S10 mới mở review route bằng relevant question. [OBJECTIVE_TIMELINE.md:215–260](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L215-L260) [OBJECTIVE_TIMELINE.md:955–960](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L955-L960) [OBJECTIVE_TIMELINE.md:1153–1159](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L1153-L1159) [PLAYER_STORY.md:709–719](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L709-L719)

**Tại sao/hậu quả:** không có lý do raid cả bệnh viện là đúng. Nhưng thông tin “chưa có review trong file” chưa trả lời vì sao một case-specific verification hợp lý trước D0 chưa chạm dấu kiểm tra của Phúc/Huyền. Smart player có thể hỏi tại sao Bắc có bridge từ một job còn police không lấy được một liên hệ hẹp từ case đã biết.

**Sửa nhỏ:** nêu một past narrow request có kết quả giới hạn qua luồng Khoa, thiếu định danh do Phúc chưa cung cấp, hoặc scope/routing thật của inquiry. E22 cung cấp đúng identifier/fact phá rào cản ấy. Không thêm tham nhũng, cấm hỏi vô lý hay tuyên bố luật ngoài canon. Đây là yêu cầu giải thích causal barrier, không khẳng định một thủ tục ngoài game bắt buộc phải diễn.

## LOW — polish và độ chính xác khi handoff

### L01 — LOW — Hai next-event ID trỏ sai cửa sổ nguồn

**File/scene:** OBJECTIVE_TIMELINE E27/E28. **Bằng chứng:** E27 hospital/review trỏ E32 (Đức logistics) thay vì E33 (Huyền/Thảo); E28 Phúc/Vũ trỏ E33 thay vì E34 (Phúc/Vũ). [OBJECTIVE_TIMELINE.md:476–506](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L476-L506) [OBJECTIVE_TIMELINE.md:561–607](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L561-L607)

**Hậu quả:** wiring event hoặc QA dùng trường này có thể mở nhầm nguồn dù người đọc prose vẫn hiểu. **Sửa nhỏ:** E27→E33; E28→E34, hoặc ghi một causal edge khác có chủ ý và lý do. Không đổi chronology chính.

### L02 — LOW — Minh biết câu hỏi Bắc đã chia không phải dấu bất thường

**File/scene:** CHARACTER_WEB Minh; C35/C36. **Bằng chứng:** profile cho reason to suspect vì Minh biết câu hỏi Bắc sớm hơn lẽ ra; Bắc đã hỏi/chia chính với Minh. Graph dùng phép so đúng: Tuấn biết chi tiết vượt phần Bắc nói trực tiếp với công ty. [CHARACTER_WEB.md:228–231](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L228-L231) [CLUE_GRAPH.md:137–138](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L137-L138)

**Hậu quả:** writer có thể dựng dấu plant giả hoặc thêm nghe lén để chữa wording. **Sửa nhỏ:** đổi chủ thể sang Tuấn/đầu mối công ty biết phần chỉ chia Minh; giữ Minh outsider và motive giữ việc.

### L03 — LOW — Tem cuối chỉ xác nhận tiểu sử dài hơn, chức năng “chưa kết thúc” hơi yếu

**File/scene:** true epilogue, MASTER và ENDING_LOGIC. **Bằng chứng:** MASTER cần một chi tiết tinh tế gợi câu chuyện có thể chưa kết thúc; ending đóng “ý nghĩa duy nhất” thành nghề nghiệp Nam dài hơn hồ sơ 2026. C27/C30 đã cho background quá khứ. [MASTER_GAME_BIBLE.md:1483–1500](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/MASTER_GAME_BIBLE.md#L1483-L1500) [ENDING_LOGIC.md:1299–1328](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1299-L1328) [CLUE_GRAPH.md:145–149](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L145-L149)

**Tại sao/hậu quả:** tem có thể hoàn thành chức năng visual rất tinh tế, nhưng nếu chỉ lặp thông tin “ông từng làm ngành này”, recontextualization sau True yếu. Đây là editorial risk, không bằng chứng phải thêm boss hoặc phải hủy victory.

**Sửa nhỏ:** trong chính motif/record cũ đang có, chọn một chi tiết còn chưa được giải thích, đủ để nghĩ lại về lịch sử vụ án; tránh đóng mọi cách hiểu thành một câu tiểu sử. Không xác nhận villain mới, Nam thoát, sequel, hoặc conspiracy lớn hơn.

## Causality audit — thử tháo từng event khỏi chuỗi

“Đứng” ở bảng này nghĩa là có nguyên nhân và giới hạn hậu quả trong tài liệu, không phải mọi payload/scene đã production-ready. Một event có thể không cần cho mọi route mà vẫn hợp lý: branch conditional không được coi là coincidence bắt buộc.

| Event | Nguyên nhân → hậu quả | Nếu tháo event / điểm adversarial |
|---|---|---|
| E01 | Nghề hợp pháp của Nam tạo contacts, kinh nghiệm và vỏ đời thường. | Bỏ thì quan hệ y tế/logistics về sau mất nền; không tự chứng minh phạm tội hiện tại. |
| E02 | Nam dùng nền nghề nghiệp cho giao dịch phi pháp đầu tiên. | Bỏ thì không có lõi crime để scale; phải giữ ranh giới quyết định của Nam, không đổ hết cho đàn em. |
| E03 | Hạnh tham gia, tạo nhánh nguồn người/môi giới. | Bỏ thì case Phúc và coercion mất actor có motive. |
| E04 | Tân Lộ cung cấp lớp logistics trong doanh nghiệp thật. | Bỏ thì E19/E22 không có đường vận hành; majority hợp pháp là constraint, không miễn culpability của lãnh đạo. |
| E05 | Một cell Minh Trạch ổn định hỗ trợ giấy tờ. | Bỏ thì Phúc check không chạm pattern; H02 cần khóa nội dung knowingly hỗ trợ. |
| E06 | Khải compartmentalize và quản lý risk. | Bỏ thì manager knowledge limits và việc ba case chưa nối mất cơ sở. |
| E07 | Scale làm incentive, lỗi và áp lực giữa managers tăng. | Bỏ thì Hạnh/Khoa/Hùng cùng tự cứu khó thuyết phục; không cần họ hành động như hivemind. |
| E08 | Phúc chấp nhận thỏa thuận vì nhu cầu riêng. | Bỏ thì withdrawal và omission ban đầu không có nền; không phải nạn nhân hoàn hảo. |
| E09 | Nghi ngờ khiến Phúc muốn rút. | Bỏ thì E10 không còn là coercion sau withdrawal. |
| E10 | Hạnh chịu sunk cost/deadline/status nên vượt doctrine. | Bỏ thì crisis không mở theo đường hiện có; Nam vẫn chịu trách nhiệm thiết kế incentives, không được rửa sạch vai trò. |
| E11 | Phúc tự kiểm tra Minh Trạch do mất tin môi giới. | Bỏ thì Huyền chưa có anomaly khởi review; police và hospital vẫn là hai đường riêng. |
| E12 | Sức ép khiến Phúc trình báo. | Bỏ thì Vũ xuất hiện sau chỉ vì Bắc sẽ tiện tác giả; hiện case có trước player. H05/M01 cần custody rõ. |
| E13 | Huyền thấy pattern vượt một case và mở review. | Bỏ thì Khoa không có review để thu hẹp, B yếu; không phải review tự sinh để đưa clue. |
| E14 | Khoa giảm nhẹ report vì tự bảo vệ. | Bỏ thì Nam/Khải có đúng picture sớm hơn, cleanup/pressure phải thay; đây là giới hạn thông tin có motive. |
| E15 | Nam nhận report risk và chọn controlled cleanup. | Bỏ thì baseline các cell không có định hướng chung; cleanup không chờ Bắc bắt đầu chơi. |
| E16 | Khoa tiếp tục che độ sâu review. | Bỏ thì risk manager có thể điều chỉnh trước; failure của Nam là report bị lọc, không thiếu trí thông minh. |
| E17 | Cleanup/risk kiểm tra Tân Lộ; Đức giữ phần dữ liệu, Yến thấy anomaly. | Bỏ thì insider corroborators chưa có lý do hình thành. M04 phải khóa copy owner/location. |
| E18 | Khải thấy dấu leak/access bất thường. | Bỏ thì áp lực khiến Hùng tự cứu bằng E19 yếu; Khải chưa biết mọi copy nên chưa được thu hồi tất cả. |
| E19 | Hùng hạ gói xuống ordinary pool để che sai phạm của mình trong audit. | Bỏ thì assignment Bắc nhận không còn anomaly cùng nghĩa. Không phải Nam chủ động tuyển một sinh viên. |
| E20 | Bắc chuyển trọ và Nam gặp cậu trong đời sống thật. | Bỏ thì emotional reveal/replay mất nền; nhưng case tội phạm vẫn đang chạy. |
| E21 | Thiếu tiền và Minh giới thiệu kênh part-time thật. | Bỏ thì Bắc chưa có entry vào ordinary worker pool. Minh không cần biết crime. |
| E22 | Ordinary dispatch phân job đã hạ luồng; Bắc hoàn tất sealed handover. | Bỏ thì Bắc không có bridge cá nhân, nhưng baseline investigation vẫn tồn tại. Chance mở cửa, không giải án. |
| E23 | Breach sai luồng lộ trong kiểm tra, Hùng bị chất vấn. | Bỏ thì Khải không có worker-incident report để E24 đến đúng Nam. |
| E24 | Khải report identity; Nam mới nối worker với hàng xóm. | Bỏ thì Nam chỉ biết Bắc đời thường. S01 không được retroactively diễn như đã tuyển/đặt bẫy. |
| E25 | N1 chỉ chứng minh đã giao, chưa hiểu/giữ/chia; Nam quan sát. | Bỏ/thay bằng bạo lực sẽ tự tăng attention vì thông tin chưa xác nhận. Competent restraint có cơ sở. |
| E26 | Conditional: Bắc chia hỏi sâu; Minh báo channel công việc vì sợ/giữ việc. | Không chia thì không leak. Đường Minh→Tuấn→Hùng→Khải cần giữ, không nhảy thẳng boss. |
| E27 | Huyền không nhận lời giải thích đủ; Khoa cố thu hẹp. | Bỏ thì morning B window khó tồn tại. L01 sai ID không làm prose causal spine sai. |
| E28 | Vũ tiếp tục làm rõ Phúc độc lập với Bắc. | Bỏ thì police bị chờ player. Hiện chronology đã trong file nên H05 không thể reset nó. |
| E29 | Bắc có thể chủ động probe, tạo hành vi có thể bị report. | Chỉ nghĩ trong đầu thì chưa có adversary signal. M09 phải khóa observable choice. |
| E30 | Nam nhận thêm report mức can thiệp, có thể lên N2. | Bỏ reports mà vẫn tăng awareness là knowledge breach; không default N3. |
| E31 | Company audit, hospital review và police case cùng tiếp tục. | Bỏ thì thế giới đứng chờ player; baseline hiện chống convenience này. |
| E32 | Đức bị nghi leak, muốn tự bảo vệ, còn quyền/source. | Bỏ thì C18 không tự đến từ NPC clue dispenser; H04/M04 khóa timing/custody. |
| E33 | Review còn mở, Huyền/Thảo có thể cung cấp đúng phạm vi. | Bỏ thì không có B window. No-Thảo alternative phải cùng nghĩa proof, H02. |
| E34 | Bắc cung cấp sourced bridge; Vũ so với case Phúc. | Bỏ bridge thì police không tự có Tân Lộ; đã giữ chronology không bằng đã có relation. |
| E35 | Yến thấy finance anomalies trong quyền mình và có route hợp lệ. | Không dùng thì C18 vẫn có thể corroborate C; không bắt Bắc gặp Yến riêng. |
| E36 | Đủ independent facts cho Bắc nối nhiều cell. | Bỏ fact/inference thì không được cấp certainty chỉ vì tới S13, H06. |
| E37 | Cross-report cho Khải thấy cùng Bắc can thiệp hai nhánh. | Bỏ observable reports thì Nam chưa biết N3; baseline closure không thay chúng, H07. |
| E38 | Sourced corroboration đủ để police preserve và tăng phản ứng. | Bỏ corroboration thì không được raid bằng hypothesis; có đủ thì không được trì hoãn chỉ để kéo climax. |
| E39 | D current-command corroborated và preserve đủ sớm. | Bỏ D/timing thì Nam có thể bị nghi nhưng chưa mất lõi theo True. H03/M02 khóa đường chứng minh. |
| E40 | ABC được giữ nhưng command route đến muộn. | Bỏ race/loss thật thì không được cho Cleanup chỉ vì tác giả muốn bad. |
| E41 | Route cuối cho required proof/nguồn mất vì delay/miss. | Không final loss thì chưa được resolve G1. H09/M06 phải bao relation/partial đúng. |
| E42 | Unsafe trust/direct disclosure gây loss thực trước custody. | Không loss causal thì leak chưa là ending. M05 tránh nhãn theo attempt thay nguyên nhân. |
| E43 | True dẫn tới consequences và đời sống sau vụ án. | Không xóa thành quả để tạo sequel. L03 chỉ là chức năng subtle detail. |
| E44 | Bad/partial vẫn có institutional traces và police tiếp tục. | Không được hiểu partial Nam thoát trong run là mọi hồ sơ vĩnh viễn biến mất. |

Nguồn toàn chuỗi: [OBJECTIVE_TIMELINE.md:50–160](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L50-L160) [OBJECTIVE_TIMELINE.md:167–357](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L167-L357) [OBJECTIVE_TIMELINE.md:364–538](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L364-L538) [OBJECTIVE_TIMELINE.md:545–767](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L545-L767). Baseline B01–B08 tiếp tục audit, thu hẹp review, điều tra và co network khi Bắc không làm gì; không có yêu cầu player kích hoạt thế giới. [OBJECTIVE_TIMELINE.md:988–1084](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L988-L1084)

**Coincidence còn lại nhưng chấp nhận được:** Bắc ở gần Nam và nhận đúng job bị hạ luồng. Đây là coincidence tạo premise. Điều tra tiếp theo phụ thuộc vào quan sát, hành động, truy nguồn và intake; coincidence không tạo proof thắng. Thêm lý do “Nam đã chọn Bắc từ đầu” sẽ phá chính điểm mạnh này.

## Timeline, di chuyển, NPC schedule và item lifecycle

### Cửa sổ song song không phải bốn cuộc hẹn bắt Bắc tự đi

| Mốc/nguồn | Objective time | Người/quyền tại nguồn | Audit |
|---|---|---|---|
| E20/S01→S02 | Exit khoảng 08:35; lớp 09:15 | Bắc rời trọ; travel trọ–trường 20–30 phút | Đến ~08:55–09:05 khả thi; header scene rộng không buộc ở lại tới 09:00. [FULL_SCRIPT.md:449–483](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L449-L483) [OBJECTIVE_TIMELINE.md:25–35](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L25-L35) |
| E22 | Bắc giữ 12:30–13:52 | Nhận sealed pouch → giao điểm nhận | Custody rõ; sau 13:52 không được inspect item trên tay. [FULL_SCRIPT.md:1370–1376](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1370-L1376) |
| E24 | D0 16:00–17:00 | Khải report Nam từ xa | Không cần Nam cùng phòng Hùng hoặc teleport về trọ. [OBJECTIVE_TIMELINE.md:428–442](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L428-L442) |
| S05 repair return | D0 17:20–17:40 | Nam trả ổ kéo đã nhận sửa S01 | Không phát hiện teleport item. [FULL_SCRIPT.md:479–483](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L479-L483) [FULL_SCRIPT.md:1620–1645](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1620-L1645) |
| E27 / E28 | 19:00–20:30 / 20:00–21:30 | Huyền/Khoa ở hospital; Vũ/Phúc qua tuyến police | Song song ở hai institution; không đòi cùng NPC ở hai nơi. [OBJECTIVE_TIMELINE.md:476–506](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L476-L506) |
| E32/C18 | D+1 09:30–11:00 | Đức, snapshot/source trong giới hạn quyền | Late offers S12/S13 cần sửa H04; loss copy cần M04. |
| E33/C11–C15 | D+1 09:30–11:30 | Huyền/Thảo; Khoa có thể giới hạn scope | Player hoặc police hợp lệ tiếp cận; không xóa nền audit. |
| E34/A bridge | D+1 10:00–12:00 | Vũ/Phúc, sourced comparison | Thuần phone/intake nếu route cho phép; không reset E12/E28. |
| E35/C19 | D+1 10:30–12:30 | Yến, finance rights của cô | Police có thể thu song song; phải có request/intake trước close. |
| E36/E37 | Trưa D+1 | Bắc suy được / Khải nhận cross-report | Hai event khác điều kiện, không một flag thay cả hai. |
| E38–E42 | Chiều/late D+1 | Police giữ case, network siết routes | Giữ relative order source window→corroboration→preservation→D→lock; không elapsed-time tùy người viết. |

Nguồn cửa sổ: [OBJECTIVE_TIMELINE.md:561–655](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L561-L655). Bounds travel: cùng hub 5–15 phút; trọ–trường 20–30; trọ–Tân Lộ 25–35; Tân Lộ–Minh Trạch 25–40; trọ–Minh Trạch 30–40. Không tự thêm khoảng cách police micro-set ngoài tài liệu. [OBJECTIVE_TIMELINE.md:25–35](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L25-L35)

### Nguồn còn tồn tại, nguồn còn tiếp cận và bản đã bảo toàn là ba điều khác nhau

| Evidence/item | Owner/custodian thực | Điều có thể mất | Điều không được mất theo closure chung |
|---|---|---|---|
| Pouch E22/C04 | Tân Lộ → Bắc → điểm nhận | Khả năng nhìn nhãn trực tiếp sau bàn giao | Quan sát/ảnh hợp lệ đã lưu; photo framing phải khóa M07 |
| C02/C03 | Worker app và history | Account/context khi actor thật hạn chế | Fact có thể đọc lại khi history còn; flag early không xóa dữ liệu |
| C08/C10 | Phúc giữ original; Vũ giữ phần đã tiếp nhận | Phúc rút hợp tác / phần chưa giao | Police record đã có từ E12/E28 |
| C11/C12 | Minh Trạch compliance/audit systems | Quyền truy cập hoặc scope review | Lịch sử nền; bản police đã nhận |
| C17/C22 | Tân Lộ operational/approval systems | Worker access, live context | Snapshot/intake sourced đã giữ |
| C18 | Đức giữ phần thông tin; nơi lưu chưa khóa | Copy/hợp tác nếu có event đủ quyền | Không auto-xóa vì badge/account khóa |
| C19 | Finance system/Yến; police nếu verify | Access vector của Yến | Toàn bộ hạch toán hợp pháp hoặc copy đã intake |
| C31–C34 | Contact/manager/institution phân tán | Một source chưa gửi, context hoặc willingness | Corroboration đã bảo toàn; không có single total-delete switch |

Canon đã có các giới hạn deletion này; patch cần thực thi chúng, không thêm cơ chế phòng vệ mới. [OBJECTIVE_TIMELINE.md:37–44](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L37-L44) [CLUE_GRAPH.md:822–847](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L822-L847) [ENDING_LOGIC.md:294–305](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L294-L305)

## Knowledge audit — từng nhân vật và bốn người trọng tâm

### Trần tri thức của toàn cast

| Nhân vật | Nguồn hợp lệ / mức biết | Điều không được tự biết |
|---|---|---|
| **Bắc** | Job, raw observation, app, lời nguồn trong phạm vi, records được chia hợp lệ; tăng bằng inference có facts | Core crime từ opening, briefing ngoài màn hình, proof Nam từ background; không tự thành chuyên gia nghiệp vụ |
| **Vũ Đức Nam** | Kiến trúc network, decision của mình, report Khải/managers; hàng xóm trước E24 | Notebook/suy nghĩ Bắc, exact copy/source chưa bị lộ; không tự nhận report mọi cell nói thật |
| **Trần Thị Lan** | Đời sống nhà trọ và tiểu sử nghề nghiệp Nam bà từng thấy/nghe | Crime, command chain, kế hoạch police; không tự thành điều tra viên |
| **Đại úy Nguyễn Minh Vũ** | Case Phúc có trước Bắc; verification/intake từ sources khi mở route | Tân Lộ/Nam trước bridge; facts chỉ Bắc suy riêng hoặc nói không có nguồn |
| **Nguyễn Ngọc Linh** | Đời lớp học, điều Bắc trực tiếp chia, hậu quả đời sống có thể thấy | Cấu trúc network; không dùng bạn học để tự cấp police/manager knowledge |
| **Lê Gia Minh** | Part-time thật, câu hỏi/thông tin Bắc chia; liên hệ nhân sự với Tuấn | Nam/organ network/chain escalation thật; không leak fact Bắc chưa cho |
| **Đỗ Minh Tuấn** | Dispatch, checklist, assignment sau classification, phản hồi audit trong phần việc | Core crime/Nam; không cố tình tuyển Bắc cho network |
| **Nguyễn Hoàng Đức** | Logs vận hành/phần snapshot; thấy việc không sạch, nghi liên hệ y tế | Full network, Nam, hospital scope và ai được secret core briefing |
| **Trần Thanh Phúc** | Thỏa thuận/withdrawal/pressure/check/report của mình | Tân Lộ/Nam, architecture nhiều cell; suy đoán phải được ghi là suy đoán |
| **Lê Duy Khải** | Gần toàn risk picture và giao điểm reports | Exact unseen copies, mọi private inference; không toàn tri |
| **Trần Quốc Hùng** | Crime/logistics branch, decision/quan hệ Nam trực tiếp biết; có incentive giấu sai phạm | Chi tiết nhánh hospital/môi giới ngoài phạm vi; không global witness tùy nhu cầu D |
| **Phan Quốc Khoa** | Hospital cell, phần crime và command trực tiếp biết | Logistics branch đầy đủ, mọi dữ kiện Hùng che |
| **BS. Lâm Thảo** | Phần hồ sơ/hoàn cảnh phi pháp mình tham gia | Nam/full command; admission B không tự hoàn tất D |
| **BS. Hoàng Huyền** | Review/pattern/audit trail trong compliance | Tự biết organ network hoặc Nam chỉ vì pattern |
| **Bùi Thu Hạnh** | Broker branch, các bên liên quan trong phạm vi; Nam qua quan hệ/chain giới hạn | Full operational picture của hospital/logistics hoặc điều Bắc chưa chia |
| **Mai Yến** | Finance anomalies/records trong quyền mình | Nam chắc chắn, full organ scheme; finance không tự thay content tội lõi |

Nguồn toàn cast: [CHARACTER_WEB.md:87–485](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L87-L485); knowledge matrix và information barriers: [CHARACTER_WEB.md:504–553](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L504-L553); backstage limits: [BACKSTAGE_CRIME_TRUTH.md:1288–1300](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/BACKSTAGE_CRIME_TRUTH.md#L1288-L1300). Những giới hạn này cũng áp dụng ở ending montage: biết tác giả không bằng ai cũng biết sau một cuộc gọi.

### Trạng thái theo thời điểm: Bắc / Nam / cảnh sát / Minh

| Mốc | Bắc | Nam | Vũ / police | Minh |
|---|---|---|---|---|
| Trước D0 | Chưa liên quan | Biết architecture, nhận report bị lọc | Phúc + pressure/tiền + tên hospital; có hồ sơ thật | Kênh job hợp pháp |
| D0 sáng | Nam hàng xóm; Minh chỉ job | Bắc là hàng xóm N0 | Case tiếp tục, chưa TL | Giới thiệu job thật |
| E22 12:30–13:52 | Sealed handover; fields/label nếu xem | Chưa nối Bắc với worker trước E24 | Chưa tự có receipt Bắc | Biết job nếu được kể |
| E24 16:00–17:00 | Chưa biết Nam đã nhận identity | Worker=Bắc, N1; chưa biết cậu hiểu gì | Chưa bridge mới nếu Bắc chưa liên hệ | Chưa biết boss chain |
| D0 tối conditional | Có thể probe; private hypothesis | N2 chỉ từ observed reports | E28 làm case Phúc rõ hơn | Chỉ leak phần Bắc chia; có thể giấu mức đã báo |
| D+1 sáng | Có thể mở C17/hospital/police; không sở hữu mọi source | Reports theo branch; baseline closure vẫn chạy | Nhận sourced bridge, có thể thu song song | Vẫn outsider |
| E36/E37 trưa | N3 hiểu nếu facts/inference đủ | N3 awareness nếu cross-report đủ | Chỉ tăng theo facts tiếp nhận/verify | Không tự được biết Nam/core crime |
| E38 afternoon | Cần custody thay chỉ giữ notebook | N4 khi có signal về case nguy hiểm thực | ABC có thể đủ để chủ động; D vẫn riêng | Leak có hậu quả hoặc vô hại tùy custody |
| E39–E42 late | Nam hypothesis khác Nam proved | Không biết exact missing/preserved route nếu chưa có report | D1/D2/time cho hành động lõi; partial vẫn giữ case cũ | Có thể hối hận; không thành exposition manager |
| E43/E44 | Sống/biết theo run; vẫn sinh viên | True mất khả năng giữ lõi; partial co/rút | Tiếp tục điều tra; không reset hồ sơ | Không retcon thành member |

Nguồn: [OBJECTIVE_TIMELINE.md:364–767](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L364-L767) [OBJECTIVE_TIMELINE.md:893–902](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L893-L902) [OBJECTIVE_TIMELINE.md:923–984](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L923-L984). **Điểm cần khóa:** H05–H08. Không thấy lý do canon để nâng Bắc thành professional investigator: cậu có thể so records mình thấy, còn việc xác minh nghiệp vụ, bảo vệ và xử lý thuộc Vũ.

## Mystery fairness và red herring — từng reveal

| Reveal | Clue có trước kết luận / việc player phải suy | Audit |
|---|---|---|
| **R1: job bị hạ luồng** | C02–C04 seed → C17 actual log → C20/C22 authority | Fair về cấu trúc; C03/C04 recovery cần M07. Không cần biết pouch chứa gì. |
| **R2: withdrawal trước pressure, case có trước Bắc** | C08/C09/C10/C11A; so chronology, tách omission và nói dối | Timestamp độc lập về thời điểm case tốt. Payload organ/coercion và independence cần H02/M01/H05. |
| **R3: hospital pattern + management intervention** | C11 review, C12 scope history hoặc C15 insider; C13 refusal có lý do | Có hai route; no-Thảo route cần cùng nghĩa knowingly hỗ trợ, H02. |
| **R4: Tân Lộ leadership chủ ý tham gia** | C17 + C18/C19 + C22; không equate dispatch với leadership | Timing route H04; override chưa tự chứng minh core knowledge, H02. |
| **R5: Tuấn vô tội core, có lỗi nghề nghiệp** | Suspicion C05/C35; correction C20/C21/C22 và behavior | Dữ kiện nghi là thật. Permission correction fair; core exoneration overclaim H08. |
| **R6: Minh leak, không phải plant** | C07 việc thật → C35 contact → C36 excess detail → C37 actual early closure | Motivation mundane đủ; không phải twist cần ngoại truyện. Attribution M05, wording L02. |
| **R7: ABC cùng network** | C03 early bridge, C24/C25 shared non-public risk endpoint, C26 inference | Không chỉ cùng chữ “y tế”. Cùng consultant chưa tự crime; phải khóa endpoint/context thật. H06/H09 quan trọng. |
| **R8: managers có tội nhưng không phải apex** | C22/C12/A sources và khác biệt knowledge; Khải ở giao điểm | Có motive che riêng. Cần actual dialogue không cho Hùng/Khoa biết toàn bộ rồi mới rút lời. M02/H01. |
| **R9: Nam current command** | C27–C29 life seeds, C30 historical relation, C31–C34 current independent authority | Foreshadow tồn tại và không tự đủ proof. H03/M02 cần recovery/provenance, không thêm early villain tells. |
| **R10: biết ≠ bảo toàn** | C42 custody, C43 closures, Vũ phản ứng theo nguồn | Ý tưởng gameplay hợp story; warning phải trước last loss, custody đã có không reset. H05/M03. |

Nguồn catalog/reveals: [CLUE_GRAPH.md:79–160](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L79-L160) [CLUE_GRAPH.md:168–297](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L168-L297). **Không xác nhận có twist bị giấu chỉ để giật mình ở Act I**; dữ kiện late chưa cần có sẵn trong opening, nhưng phải được player tiếp cận trước kết luận mà chúng chứng minh. H01 khiến thứ tự lời thoại late chưa thể chứng nhận.

| Red herring | Sự thật làm nó đáng nghi | Cách correction phải giữ fair |
|---|---|---|
| RH1 Tuấn cố tình chọn Bắc | Dispatch authority, nói procedural, thật sự bỏ qua abnormal job | C20 loại originator; knowledge innocence không được suy vượt, H08 |
| RH2 Hùng là ultimate boss | Hùng thật guilty, override và che audit | Knowledge/authority giới hạn + current command có source; không chữa bằng Hùng ngu |
| RH3 Huyền che hospital | Từ chối đưa dữ liệu khi Bắc chưa đủ quyền | C11 bà mở review; tiêu chuẩn access nhất quán cả trước/sau, không lời nói dối author |
| RH4 Minh là plant | Leak và giảm nhẹ phần đã kể | Việc làm thật, fear/job motive, chain tới Tuấn; không secretly member |
| RH5 Phúc dựng chuyện | Đồng ý/tiền ban đầu, omission vì xấu hổ | C09 và chronology; omission không làm withdrawal/pressure vô hiệu |
| RH6 cả hospital/Tân Lộ đều crime | Nhiều records cùng tổ chức và manager liên quan | Noise/vận hành hợp pháp, các NPC vô tội, scope của cell nhỏ |

Nguồn: [CLUE_GRAPH.md:389–479](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L389-L479). Red herrings hiện dựa trên facts thật; vấn đề lớn là **độ mạnh của correction**, không có căn cứ nói tác giả đang nói dối player toàn bộ.

## True ending audit — mô phỏng smart player chơi lần đầu

Đây là walkthrough suy luận **từ tài liệu**, không phải kết quả playtest. Mục blind-run trong ENDING_LOGIC là yêu cầu test tương lai, không có logs/tester results đi kèm. Không dùng tỷ lệ ~10% như một metric đã đo. [ENDING_LOGIC.md:1532–1552](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1532-L1552)

| Bước | Hành động hợp lý khi chưa biết Nam | Clue/decision phải tự tiếp cận | Rủi ro hiện tại |
|---|---|---|---|
| 1. D0 opening | Nhận đời sinh viên, lấy việc vì tiền; Nam là người giúp | Có thể bỏ C28; chưa lý do kết luận crime từ C27 | Không lỗi: early boss guess không required |
| 2. E22 | Làm đúng ca; ghi mismatch/receipt vì trách nhiệm cá nhân | C02; chủ động inspect C03/C04 nếu quan tâm | M07: later history không được chặn bởi click sớm |
| 3. S06/S07 | Audit hỏi factual vì tiền/uy tín; chọn tiếp tìm hiểu | Không mặc định employer channel là channel giữ bí mật; chia có phạm vi | No-automatic-fail đúng; M09 cần observable probes/cost |
| 4. S08/S09 | So log/permission; mang sourced anomaly cho Vũ | C17/C20; trigger Đức hoặc police collection trước window đóng | H04/M03: source lead/warning chưa guaranteed đúng lúc |
| 5. S10/S11 | So review với chronology Phúc | B alternative; A exact record và nguồn verify | H02/H05/M01: fact được chứng minh/custody chưa một nghĩa |
| 6. S12/S13 | Không dừng ở manager; so hai endpoints/timestamps | C22, C24/C25, tự nối X; police verify từ nguồn | H06: không được auto-understand; H09 nếu X thiếu |
| 7. S15/S16 | Đưa nguồn ra khỏi tay mình; phân biệt old relation và current authority | ABC+X preserved; D1 và D2 độc lập | H03/M02: alternative D và provenance chưa kín |
| 8. S17/S18 | Ưu tiên custody trước disclosure; phản ứng bình tĩnh khi gặp Nam | D preserved trước lock; không cần confession/confrontation | M11 và clock cần khóa; safe handover không được mất ngược |

**Một lịch ngắn tồn tại:** trọ→Tân Lộ từ ~08:30; S08 ~09:00–09:35, liên hệ Đức lúc 09:30; S09 qua phone ~09:35–10:05; travel Tân Lộ→Minh Trạch 25–40 phút, tới ~10:30–10:45 trước 11:30. S11 ở điểm công cộng gần hospital; quay Tân Lộ ~12:20; S12 dùng **copy sáng**. Vũ thu nguồn khác song song. Đây là witness khả thi, không phải timeline canon mới hay chứng minh người chơi không guide sẽ chọn nó. [OBJECTIVE_TIMELINE.md:25–35](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L25-L35) [OBJECTIVE_TIMELINE.md:561–623](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L561-L623) [OBJECTIVE_TIMELINE.md:1240–1246](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L1240-L1246)

Ngay cả S09 xong 10:40, travel có thể đưa Bắc tới hospital 11:05–11:20. Tài liệu không chốt một minimum objective duration cho S10 khiến toàn bộ route chắc chắn hỏng. Gameplay budget 6 phút cũng không tự bằng 6 phút in-universe. Vì vậy không đánh lỗi teleport chỉ vì hai header overlap.

**Trả lời câu hỏi first-run:** một player cực tinh ý **có thể có đủ hành động hợp lý để đạt True trên abstract design**. Tuy nhiên hiện chưa bảo đảm discoverability và equivalent proof: source lead/timing H04, warning M03, proof payload H02, D recovery H03/M02 và clock M08. Không cần thêm clue “Nam đáng ngờ” vào opening; cần làm thông tin đã có đủ dùng đúng lúc.

**Có quá dễ không?** Chưa đủ bằng chứng để kết luận. Nếu mandatory scene tự tặng tất cả corroborators, set N3/X và objective/hints viết kết luận, True sẽ thành đi đúng checklist. H06 là dấu drift cụ thể theo hướng đó. Ngược lại, internal PRIMARY OBJECTIVE trong blueprint không tự là UI text; Act I actual UI dùng mục tiêu đời thường, chưa spoiler boss. Không buộc tăng độ khó bằng thao tác, pixel, source mất vô báo hoặc giấu proof cần thiết.

## Bad ending audit — outcome phải giữ đúng nguyên nhân player

| Ending | Hành động / thiếu sót dẫn đến | Safeguard đã có | Cần khóa |
|---|---|---|---|
| **G0 — Một ca làm thêm** | Chủ động không đào sâu lúc còn ≤N1, không leak/chạm cell thứ hai | Neutral, không xử tử ngẫu nhiên chỉ vì nhận job | Giữ BARC thật; không baseline closure tự arm G3 |
| **G1 — Quá muộn** | Delay/miss làm route required cuối không thể preserve | Phải actual final loss, không thiếu một optional là thua | H09 relation-loss; M03 warning; M06 transition; M08–M09 time/action |
| **G2 — Sai người** | Thông tin chia Minh đi đúng chain, làm source cần thiết mất route cuối trước custody | Nhắn Minh đơn lẻ không auto-fail; có alternate/đã preserve thì route sống | M05 decisive cause; clue hậu quả phải có timing fair |
| **G3 — Quay lưng quá muộn** | Cắt route sau N3 khi police chưa đủ tự giữ case | Early avoidance là G0; late withdrawal sau full safe custody không phải G3 | H05/H07 để N3/custody không giả; không random retaliation |
| **G4 — Dọn sạch** | ABC+X đã giữ, D current command chưa đủ/preserve trước lock | Thành quả partial thật; boss thoát lõi trong cửa run, case tiếp tục | H03/M02 proof alternative; M05 D-only attribution |
| **G5 — Bị nhìn thấy** | Direct disclosure cho network biết source/chain để gây loss trước custody | Confront sau toàn proof đã giữ không xóa True; Nam không đọc notebook | M05 cause policy; M11 không bắt risky encounter |
| **G6 — Những mảnh khớp lại** | ABC+X+D source đủ, D custody thắng cleanup | Không cần mọi optional, confession, combat hoặc early boss guess | Đồng bộ proof/state/window trên tất cả tài liệu |

Nguồn predicates và precedence: [ENDING_LOGIC.md:255–305](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L255-L305); summaries: [ENDING_LOGIC.md:1556–1566](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1556-L1566); production safeguards: [ENDING_LOGIC.md:1570–1595](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1570-L1595). **Điểm đang đứng:** custody là thành quả không bị trừng phạt ngược, leak cần loss thật, neutral được phân biệt với abandonment muộn. Giữ những điểm này khi patch.

## Dialogue, character, pacing, gameplay, replay và scope

### Thoại và hành vi đã có thực tế

S01–S05 không chứa villain confession hoặc exposition organ network từ người không biết. Nam nói và giúp trong phạm vi hàng xóm; Lan thiên về việc nhà/tiền/sinh hoạt; Tuấn dùng checklist/job fields; Bắc hỏi vì trách nhiệm ca và tiền hơn là phát biểu như cảnh sát. Linh/Minh có cùng nhịp đùa ngắn ở trường, nhưng còn khác vị trí/mục tiêu; chưa đủ căn cứ gắn lỗi “everyone sounds the same”. [FULL_SCRIPT.md:174–437](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L174-L437) [FULL_SCRIPT.md:521–680](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L521-L680) [FULL_SCRIPT.md:1170–1230](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1170-L1230) [FULL_SCRIPT.md:1580–1736](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1580-L1736)

C27 nghề cũ Nam là seed có chức năng; nếu diễn bằng nhấn camera/nhạc hoặc để Lan kể một đoạn tiểu sử dài không có trigger, nó sẽ quá lộ. Actual script hiện tránh boss marker, nên không cần cắt seed này. Lời procedural của Tuấn có nghĩa ở replay: ông nói điều đúng trong knowledge layer mình, không giả confession. Nam kindness thật ngăn caricature tốt hơn thêm một speech triết lý ác.

**Phần chưa thể xét:** natural speech và sự khác giọng của Phúc/Huyền/Thảo/Hùng/Khải/Vũ ở các scene late; repetition của custody explanation; exposition dump ở S11/S13/S16; độ dài climax. Đây là H01, không gán cho outline các lời thoại chưa viết. Khi viết tiếp, câu nói thể hiện source biết bao nhiêu và muốn gì phải đi trước câu giải nghĩa mystery; Bắc hỏi ngắn và kiểm facts, Vũ làm phần professional verification.

### Pacing và coverage S01–S18

| Scene | Budget Stage 7 | Chức năng | Audit |
|---|---:|---|---|
| S01 | 5m | Chuyển trọ, Nam/Lan, tiền/sửa đồ | Opening đời thường thật; C28 optional |
| S02 | 5m | Lớp, Linh/Minh, job context | Trường không thành conspiracy hub |
| S03 | 4m | Chọn nhận ca vì nhu cầu | Decline là hesitation reconverge, đừng quảng bá như ending branch |
| S04 | 6m | Sealed delivery/mismatch/receipt | M07 lifecycle; không organ imagery clue quá lộ |
| S05 | 4m | Ăn/uống/chat/về trọ | Breather thật, Nam đã N1 ngoài màn hình |
| S06 | 4m | Job audit, self-protection | Trigger curiosity hợp motive |
| S07 | 5m | Share/continue/stop, day transition | G0; dream optional remix, không tạo facts |
| S08 | 6m | Reclassification/permission | Early Đức lead cần H04, correction chỉ đúng mức H08 |
| S09 | 5m | Police intake | Police vào đủ sớm; H05 custody |
| S10 | 6m | Hospital review và alternative B | H02/M03 payload/warning |
| S11 | 5m | Chronology Phúc | Reasoning nên do player; M06 weak-route edge |
| S12 | 5m | Hùng leadership / Tuấn correction | M10 fast path; C18 không pickup muộn |
| S13 | 6m | Cross-cell endpoints | H06/H09; montage chỉ verify nguồn, không giải hộ |
| S14 | 5m | Closures và conditional leak | H07; không dùng warning muộn để chữa loss sáng |
| S15 | 4m | Custody decision | Preserve từng phần thật, không xóa police files |
| S16 | 7m | Historical relation vs current command | H03/M02; không final code/magic record |
| S17 | 5m | Nam đời thường đổi nghĩa, response choice | M11 safe path; không boss speech |
| S18 | 6m | Resolver/consequence/epilogue | H09/M05 terminal coverage; không raid kéo dài |

Nguồn budget: [SCENE_BREAKDOWN.md:2015–2040](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L2015-L2040). **Tổng 93 phút**, gồm opening 24; Act II 15; S09–S13 27; S14–S17 21; S18 6. Stage 5 budget cũ 99 đã được Stage 7 giảm; không đánh lỗi cộng sai. Strong/True dự kiến 98–105, dream nằm S07 và epilogue nằm S18. Đây là estimate, chưa measured runtime.

Opening đạt nền đời thường khoảng 20 phút yêu cầu. Middle có nguy cơ clue-heavy vì năm scene liên tiếp phải so nguồn/timestamps, nhưng puzzle verbs khác nhau và actual dialogue chưa đủ để kết luận đã clue dump. M10 là duplication cụ thể cần xử lý. S16–S18 có 18 phút trên giấy, chưa đủ căn cứ nói climax chắc rushed; phải đo full script/read/interact thay vì thêm spectacle trước.

### Gameplay và quyền player

S08 permissions, S10 versions, S11 chronology, S13 endpoint relation, S15 custody, S16 relation-vs-command đều phát sinh từ việc Bắc cần kiểm điều có thật. Chúng không cần puzzle code/khóa vô cớ. Notebook Act I ghi raw fact/source/time, chưa suy luận boss hộ. Source-state UI được phép cho biết đã bàn giao; không nên biến thành A/B/C/D progress bar. [CLUE_GRAPH.md:64–72](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L64-L72) [CLUE_GRAPH.md:851–907](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L851-L907) [SCENE_BREAKDOWN.md:2167–2184](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L2167-L2184)

Cinematic target 8–10 phút là contract, không số đã đo. Transition/micro-dream/verification/consequence có lý do; montage xác minh off-screen của Vũ tiết kiệm traversal. Nếu montage tự quyết inference player chưa làm hoặc S17 buộc unsafe action, agency bị lấy đi — H06/M11. [SCENE_BREAKDOWN.md:2188–2225](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L2188-L2225)

Missable fair khi player được thấy source/window, có lựa chọn cứu, và mất do actor/event hợp quyền. Không fair khi app còn record nhưng cờ nói đã mất, warning sau closure, hoặc thời gian đọc bị âm thầm quy thành delay. Đây là M03/M07–M09, không cần thêm mọi optional vào mandatory để chữa.

### Replay khi đã biết Nam là boss

| Scene/fact cũ | Nghĩa lần đầu | Nghĩa sau reveal |
|---|---|---|
| Nam sửa điện/giúp nhà trọ | Một ông hàng xóm tử tế, có nghề | Kindness và systemic harm cùng tồn tại; không phải mọi việc ông làm là recruitment |
| C27 nghề kho vận/y tế | Tiểu sử hợp tuổi | Nền contacts/expertise của hai cell; vẫn không tự chứng minh command |
| C28 vật cũ Tân Lộ | Đồ nghề/kỷ niệm bình thường | Quan hệ Hùng/Tân Lộ thật có trước; không mandatory trophy |
| S05 Nam bình thường sau E24 | Hàng xóm vẫn sinh hoạt như cũ | Đã biết worker identity nhưng chỉ N1, quyết định quan sát hợp competence |
| Receipt/routing label | Việc giao cần đối soát | Dấu E19 management reclassification, không Tuấn tuyển Bắc |
| Minh part-time và hỏi employer | Bạn học giúp việc rồi xử lý sợ hãi | Đường trust leak mundane; không retcon plant |
| Tuấn procedural | Khô khan/có thể giấu điều gì | Thật sự bị giới hạn information, vẫn có lỗi nghề nghiệp |
| C11A/C23 timestamp trước E22 | Chi tiết record | Crisis/network không được sinh ra quanh protagonist |

Nguồn: [CLUE_GRAPH.md:310–381](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L310-L381) [CLUE_GRAPH.md:527–582](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L527-L582) [OBJECTIVE_TIMELINE.md:428–458](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L428-L458). Replay đã có đổi nghĩa; không chữa twist bằng nhạc ominous, Nam nhìn camera, dấu hiệu quá bí hiểm hoặc biến kindness thành diễn hoàn toàn. L03 chỉ cần nâng chức năng motif cuối, không thêm twist mới.

### Scope khoảng 90 phút

| Thành phần | Scope thực trong tài liệu | Kết luận |
|---|---|---|
| Location | 4 vùng player chính: trường, trọ, Tân Lộ, Minh Trạch; thêm police micro-set/transition cards | Không có yêu cầu full city/full hospital/full crime base |
| NPC | 15 tên ngoài Bắc; nhiều vai qua phone, records, police verification hoặc consequence | Chưa chứng minh cần cắt cast hàng loạt; tránh mỗi người thêm subplot |
| Mechanics | 9 hệ: dialogue/phone, notebook, inspect, scene state, source window, custody, access, travel/time, ending resolver | Nhiều hệ state chia dữ liệu; cost chính là consistency/QA |
| Puzzle | 6 reasoning patterns ở core scenes | Không thao tác khó; không combat/stealth/driving sandbox |
| Clues | Catalog C01–C44 có các ID phụ A, noise và alternatives | Không được đếm như mọi run phải inspect toàn catalog; limit payload per scene khi viết full |
| Branches | G0–G6, substitutes B/C/D, leak types, private/observable understanding, preservation states | Tổ hợp QA lớn hơn scene count; H09/M05/M06 chứng minh cần matrix |
| Runtime | 93 focused, 98–105 strong/True dự kiến | Trong định hướng ~90; không có measured evidence để bảo đảm |

Nguồn scope: [SCENE_BREAKDOWN.md:2068–2113](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L2068-L2113) [SCENE_BREAKDOWN.md:2305–2329](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L2305-L2329). Ưu tiên reuse set/source interaction, conditional recap và police parallel collection. Không thêm NPC/location/mechanic để vá một proof predicate vốn có thể sửa bằng payload/custody hiện hữu.

## PLOT-HOLE ATTACK — 45 câu hỏi khó

**Đứng:** tài liệu có nguyên nhân/nguồn đủ chống câu hỏi ở mức canon. **Hở:** có contradiction/counterexample rõ cần patch. **Một phần:** nguyên tắc đúng nhưng source, route hoặc hành động chưa khóa; không tự cho PASS. Các câu trả lời là đánh giá evidence hiện có, không bổ sung sự thật mới vào truyện.

| # | Câu hỏi nhằm phá truyện | Verdict và bằng chứng |
|---:|---|---|
| 1 | Tại sao boss lại ở đúng dãy trọ của protagonist? Ông đã bố trí Bắc tới à? | **Đứng ở mức premise.** Nam có đời sống/cư trú thật, E20 gặp Bắc trước E24 worker identity. Coincidence địa điểm không tự tạo proof. Thêm tuyển dụng bí mật sẽ trái chuỗi hiện có. [CHARACTER_WEB.md:112–135](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L112-L135) [OBJECTIVE_TIMELINE.md:364–378](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L364-L378) [OBJECTIVE_TIMELINE.md:428–442](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L428-L442) |
| 2 | Một job nhạy cảm tại sao được giao cho sinh viên mới 18 tuổi? | **Đứng.** E19 hạ vào ordinary pool rồi E21/E22 dispatch bình thường; không ai chọn riêng Bắc vì phẩm chất điều tra. [OBJECTIVE_TIMELINE.md:343–410](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L343-L410) |
| 3 | Hùng thông minh sao tự đưa gói ra luồng kém kiểm soát? | **Đứng có giới hạn.** Ông tối ưu tránh dấu audit/lỗi của mình, xung đột với risk toàn mạng; không phải không biết rủi ro tồn tại. Phải giữ motive tự cứu khi script hóa. [OBJECTIVE_TIMELINE.md:343–357](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L343-L357) [CHARACTER_WEB.md:344–358](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L344-L358) |
| 4 | Tại sao mọi scandal vừa nổ đúng hôm Bắc nhập học/chuyển trọ? | **Đứng.** Phúc, review, audit đã chạy nhiều ngày trước E22; Bắc chạm late crisis, không sinh ra nó. [OBJECTIVE_TIMELINE.md:167–357](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L167-L357) [CLUE_GRAPH.md:95–109](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L95-L109) |
| 5 | Hạnh đã biết doctrine, sao vẫn dùng pressure tạo witness? | **Đứng.** Sunk cost, deadline và vị thế khiến lợi ích cá nhân lệch doctrine; E07/E10 có causal lead. Không cần biến bà không hiểu risk. [OBJECTIVE_TIMELINE.md:146–213](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L146-L213) |
| 6 | Nếu Hạnh vượt chỉ thị, Nam có thể nói không liên quan coercion và thoát trách nhiệm narrative không? | **Đứng trong backstage, proof cần H02.** Nam thiết kế hệ/incentive, không phải người vô can bị đàn em dựng crime mới. Player phải nhận facts chứng minh phần đó thay author declaration. [BACKSTAGE_CRIME_TRUTH.md:1742–1752](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/BACKSTAGE_CRIME_TRUTH.md#L1742-L1752) [OBJECTIVE_TIMELINE.md:82–96](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L82-L96) [OBJECTIVE_TIMELINE.md:199–213](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L199-L213) |
| 7 | Nam/Khải competent thì sao để Khoa và Hùng giấu report liên tục? | **Đứng.** Compartmentalization + fear bị hy sinh/che revenue/career làm reports bị lọc; hệ quản trị không xóa incentive conflict. Họ phát hiện/audit dần, không ngồi chờ. [OBJECTIVE_TIMELINE.md:130–160](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L130-L160) [OBJECTIVE_TIMELINE.md:263–357](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L263-L357) |
| 8 | Tại sao Nam không khử Bắc ngay khi biết cậu đã giao gói? | **Đứng.** N1 chưa chứng minh hiểu/giữ/chia; bạo lực tạo attention với một hàng xóm trẻ trong đời sống thật. E25 chọn classify/observe. Không cần Nam mềm lòng để được tha. [OBJECTIVE_TIMELINE.md:444–458](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L444-L458) [OBJECTIVE_TIMELINE.md:943–949](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L943-L949) |
| 9 | Khải có thể tịch thu mọi bản Đức giữ ngay từ đầu để triệt nguồn không? | **Một phần.** Khải chưa biết giữ gì/ở đâu; chỉ được chạm source có quyền. Điều này chặn total seizure, nhưng C18 location/loss mechanism còn M04. [OBJECTIVE_TIMELINE.md:37–44](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L37-L44) [OBJECTIVE_TIMELINE.md:780–781](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L780-L781) [CLUE_GRAPH.md:833–834](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L833-L834) |
| 10 | Nam ra lệnh cleanup sao không xóa toàn bộ bệnh viện/công ty và hồ sơ police? | **Đứng.** Phần lớn tổ chức hợp pháp, audit trail và police custody ngoài quyền network; cleanup là access/context/people trong cửa run. Không có quyền admin thần kỳ. [OBJECTIVE_TIMELINE.md:215–260](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L215-L260) [OBJECTIVE_TIMELINE.md:593–607](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L593-L607) [ENDING_LOGIC.md:1581–1583](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1581-L1583) |
| 11 | Kindness của Nam có phải một trò diễn để lừa player, nên replay mọi cảnh đều thành nói dối? | **Đứng.** C29 và canon giữ kindness thật, không cố lôi Bắc vào network. Người tử tế với hàng xóm vẫn có thể gây systemic harm. [CLUE_GRAPH.md:145–148](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L145-L148) [CLUE_GRAPH.md:358–364](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L358-L364) |
| 12 | Bắc suy luận kín, không leak, sao baseline closure S14 làm Nam biết cậu đã nối cell? | **Hở — H07.** S14 OR entry rồi auto BARC N3 không có cross-report bắt buộc. [ENDING_LOGIC.md:42–54](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L42-L54) [OBJECTIVE_TIMELINE.md:641–655](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L641-L655) [SCENE_BREAKDOWN.md:1470–1523](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1470-L1523) |
| 13 | Hai player để lại report y hệt nhưng một người đoán sai trong đầu: Nam có phản ứng khác được không? | **Hở — H07.** BARC không đọc thought; định nghĩa N3 còn yêu cầu private understanding thật. Phải derive solely từ report Nam nhận. [ENDING_LOGIC.md:200–203](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L200-L203) [ENDING_LOGIC.md:42–54](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L42-L54) |
| 14 | C08 và C10 có thực sự hai nguồn hay chỉ lời Phúc được chép hai lần? | **Một phần — M01.** Independent custody/date rõ; bước factual authentication ngoài Phúc chưa khóa. [OBJECTIVE_TIMELINE.md:236–243](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L236-L243) [OBJECTIVE_TIMELINE.md:496–505](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L496-L505) [ENDING_LOGIC.md:910–920](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L910-L920) |
| 15 | Vũ có chronology E12/E28 rồi, sao Bắc phải mang chronology cho Vũ để giữ A? | **Hở — H05.** Chỉ có thể hợp lý nếu record thiết yếu mới chưa được giao, nhưng record đó chưa được chỉ rõ. [OBJECTIVE_TIMELINE.md:231–245](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L231-L245) [OBJECTIVE_TIMELINE.md:492–505](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L492-L505) [ENDING_LOGIC.md:424–428](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L424-L428) |
| 16 | Cảnh sát nghe tên Minh Trạch từ Phúc sao chưa raid cả hospital? | **Đứng.** Tên trong lời kể chưa chứng minh toàn institution; Vũ có case hẹp, không có TL/command bridge. Raid tổng lực vì tên sẽ kém competence hơn xác minh. [CHARACTER_WEB.md:162–185](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L162-L185) [OBJECTIVE_TIMELINE.md:955–984](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L955-L984) |
| 17 | Không raid là đúng, nhưng trong gần hai tuần sao narrow check case Phúc chưa chạm Huyền/review? | **Một phần — M12.** Review internal là trạng thái thiếu thông tin, chưa khóa causal barrier của request. E22 cần phá đúng identifier/scope barrier, không làm police ngừng làm việc. [OBJECTIVE_TIMELINE.md:215–260](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L215-L260) [OBJECTIVE_TIMELINE.md:1153–1159](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L1153-L1159) |
| 18 | Sau khi Vũ có corroborated ABC, sao còn chờ Bắc tự điều tra thay vì hành động? | **Đứng như contract; chưa certify implementation.** E38 phải nâng phản ứng/preservation, rule cấm Vũ chậm giả. D command vẫn riêng. Full script late cần thể hiện professional action, H01. [OBJECTIVE_TIMELINE.md:657–671](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L657-L671) [ENDING_LOGIC.md:1576–1580](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1576-L1580) |
| 19 | Phúc đã nhận tiền/đồng ý rồi, sao player phải tin coercion? Tác giả giấu chi tiết này để tạo twist à? | **Đứng về fairness.** C09 ghi initial participation/omission; chronology phải tách đồng ý, rút, pressure. Không yêu cầu nạn nhân hoàn hảo. Nội dung core proof vẫn H02. [CLUE_GRAPH.md:95–98](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L95-L98) [CLUE_GRAPH.md:452–467](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L452-L467) |
| 20 | C11+C12 sao chứng minh hospital biết thỏa thuận phi pháp, thay vì scope review bị đổi vì lý do hành chính? | **Hở về payload — H02.** Alternative no-Thảo được chấp nhận nhưng fact phân biệt knowledge/assistance chưa khóa. [CLUE_GRAPH.md:104–109](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L104-L109) [ENDING_LOGIC.md:926–936](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L926-L936) |
| 21 | Hùng override routing và Yến thấy finance anomaly sao chứng minh biết organ network? | **Hở về payload — H02.** Nó đủ chỉ leadership misconduct, chưa tự specify purpose được biết khi approve. C19 còn nói không tự cho biết organ network. [CLUE_GRAPH.md:116–121](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L116-L121) [ENDING_LOGIC.md:940–948](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L940-L948) |
| 22 | Hai company contact cùng một risk consultant có thể là quan hệ hợp pháp chung không? | **Một phần.** C26 yêu cầu endpoint không phải vendor công khai chung, nên design nhận ra alternate này. Actual records/nguồn xác nhận đặc tính ấy còn phải được cụ thể hóa, không chỉ nhãn “network”. [CLUE_GRAPH.md:128–130](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L128-L130) [ENDING_LOGIC.md:954–968](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L954-L968) |
| 23 | Tuấn không phải account hạ classification; sao đó chứng minh ông không biết mục đích? | **Hở — H08.** Permission loại originator không loại knowledgeable accomplice. Giảm nghi khác core exoneration. [CLUE_GRAPH.md:119–121](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L119-L121) [SCENE_BREAKDOWN.md:1281–1285](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1281-L1285) |
| 24 | Đức chưa biết core crime thì làm sao biết ai được cấp trên briefing về core crime? | **Hở — H08.** Canon knowledge cap xung đột với C18 exoneration claim; không cứu bằng cho Đức biết toàn mạng. [CHARACTER_WEB.md:267–277](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L267-L277) [CLUE_GRAPH.md:496–502](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L496-L502) |
| 25 | Minh outsider thì thông tin sao lên được tới Khải/Nam mà không teleport? | **Đứng.** Minh→Tuấn/đầu mối công việc→Hùng audit→Khải; incident đã bị audit nên có trigger escalation. [OBJECTIVE_TIMELINE.md:460–474](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L460-L474) [OBJECTIVE_TIMELINE.md:1145–1151](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L1145-L1151) |
| 26 | Minh biết chính câu hỏi Bắc hỏi mình thì có gì bất thường? | **Hở phrasing — L02.** Excess detail phải ở Tuấn/company so với phần Bắc trực tiếp chia cho họ. [CHARACTER_WEB.md:228–231](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L228-L231) [CLUE_GRAPH.md:137–138](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L137-L138) |
| 27 | Bắc không chia cho Minh gì, game có được cho Minh leak chính xác proof của Bắc để tạo bad ending không? | **Đứng: không được.** E26 conditional theo thông tin được chia; production rule cấm leak khi không được cho info. Không có leak default toàn run. [OBJECTIVE_TIMELINE.md:460–474](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L460-L474) [ENDING_LOGIC.md:1574–1576](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1574-L1576) |
| 28 | Player handover toàn proof rồi nói hớ với Nam, có bị tước True để phạt lựa chọn không? | **Đứng: không.** Resolver True priority và custody monotonic; confrontation sau preservation không xóa True. [ENDING_LOGIC.md:278–305](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L278-L305) |
| 29 | C32 rút hợp tác, player giữ C33+C34: True hay Cleanup? | **Hở — H03.** Hai file trả lời khác nhau về D1, đây là contradiction trực tiếp. [CLUE_GRAPH.md:788–794](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L788-L794) [SCENE_BREAKDOWN.md:1728–1730](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1728-L1730) [ENDING_LOGIC.md:972–1001](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L972-L1001) |
| 30 | Hùng chỉ biết branch mình, sao một statement của ông chứng minh Nam command trên nhiều branch? | **Một phần — M02.** C32 đúng scope mình; D2 phải có authority-linked branch corroboration, mere contact không tự đủ global scope. [CHARACTER_WEB.md:350–351](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CHARACTER_WEB.md#L350-L351) [CLUE_GRAPH.md:149–152](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L149-L152) [ENDING_LOGIC.md:972–1001](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L972-L1001) |
| 31 | Metadata contact tới một số/account: player/police biết nó thuộc Nam bằng nguồn nào? | **Một phần — M02.** Catalog gắn Nam nhưng accepted route chưa khóa authentication/custodian; phải specify, không cho Bắc hack identity. [CLUE_GRAPH.md:149–150](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L149-L150) [SCENE_BREAKDOWN.md:1651–1689](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1651-L1689) |
| 32 | C33 trùng “decision window Nam”: ai biết window đó nếu chỉ có timestamps của cleanup? | **Một phần — M02.** Phải có nguồn command window độc lập, tránh lấy timing đang cần chứng minh làm chính chứng minh của nó. [CLUE_GRAPH.md:151–152](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L151-L152) [ENDING_LOGIC.md:988–1001](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L988-L1001) |
| 33 | Đức/hospital/Phúc/Yến mở cùng sáng; Bắc có phải đi bốn nơi trong vài giờ không? | **Đứng: không.** Police parallel verification được phép, phone/meeting micro-set; travel bounds có witness khả thi. Request/intake cụ thể cần H04. [OBJECTIVE_TIMELINE.md:25–35](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L25-L35) [OBJECTIVE_TIMELINE.md:1240–1246](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L1240-L1246) |
| 34 | Đi tới Đức theo S12 lúc 12:20, làm sao lấy source chỉ mở 09:30–11:00? | **Hở — H04.** Phải lấy/có request sáng rồi verify trưa, hoặc có intervention giữ route; late offer không tự kéo clock. [OBJECTIVE_TIMELINE.md:561–575](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L561-L575) [SCENE_BREAKDOWN.md:1256–1296](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1256-L1296) |
| 35 | Đức mất badge/account, bản snapshot anh đã giữ biến mất bằng cơ chế gì? | **Một phần — M04.** Nơi lưu và quyền thu hồi chưa khóa. Nếu copy riêng thì access closure không tự xóa. [OBJECTIVE_TIMELINE.md:322–324](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L322-L324) [OBJECTIVE_TIMELINE.md:561–575](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L561-L575) [CLUE_GRAPH.md:833–834](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L833-L834) |
| 36 | C43 báo lúc 14:00, sao player biết phải cứu nguồn hết từ 11:00? | **Hở về guarantee — M03.** General warning không đủ bảo đảm last-route choice; required pre-loss beat còn thiếu. [ENDING_LOGIC.md:1572–1575](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L1572-L1575) [SCENE_BREAKDOWN.md:1463–1494](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1463-L1494) |
| 37 | Receipt còn trong history; tại sao đọc nó sau audit không được cùng fact như mở Chi tiết sớm? | **Một phần — M07.** Không auto-award là đúng; intentional reinspection tương đương chưa khóa. Optional không làm bất công biến mất. [FULL_SCRIPT.md:1295–1307](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1295-L1307) [FULL_SCRIPT.md:1456–1458](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L1456-L1458) |
| 38 | Player nối sai C24/C25, sao S13 vẫn đặt hiểu network và Khải layer? | **Hở — H06.** Fact ownership/inference success không có cùng condition với auto flags. [PLAYER_STORY.md:1006–1010](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L1006-L1010) [SCENE_BREAKDOWN.md:1420–1432](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1420-L1432) |
| 39 | ABC đều preserved nhưng X=false, không leak/abandon, lock xảy ra: ending nào? | **Hở — H09.** Không predicate hiện tại bao state; không được giả sử unreachable khi PLAYER_STORY cho miss nửa bridge. [PLAYER_STORY.md:992–996](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/PLAYER_STORY.md#L992-L996) [ENDING_LOGIC.md:278–296](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L278-L296) |
| 40 | Minh đã gây loss quyết định rồi player direct attempt vô hại: ai chịu nguyên nhân bad ending? | **Một phần — M05.** Causal guards đúng nhưng DIRECT-priority enum có thể ghi đè cause; cần giữ decisive loss thay last attempt. [ENDING_LOGIC.md:111–117](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L111-L117) [ENDING_LOGIC.md:286–295](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/ENDING_LOGIC.md#L286-L295) |
| 41 | Player tin sai Hùng trong đầu hoặc đang đọc lại notebook: hệ thống biết “fixation” bằng cách nào để phạt time? | **Một phần — M09.** Chưa có observable choice/cost rõ cho wording “dừng reasoning”; phải gắn event, không thought. [SCENE_BREAKDOWN.md:1325–1327](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1325-L1327) [MASTER_GAME_BIBLE.md:1183–1189](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/MASTER_GAME_BIBLE.md#L1183-L1189) |
| 42 | Một người đọc chậm nhưng không trì hoãn action có bị đóng source hơn người lướt nhanh? | **Một phần — M08.** Coarse scene clock là ý định đúng, actual triggers/pause/conversion chưa thống nhất; chưa có build để kết luận punishment thực. [SCENE_BREAKDOWN.md:95–101](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L95-L101) [FULL_SCRIPT.md:449–457](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L449-L457) [FULL_SCRIPT.md:846–856](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/FULL_SCRIPT.md#L846-L856) |
| 43 | Đang có police safe route, sao Bắc phải về trọ lấy áo/đồ thường trước khi gửi D? | **Một phần — M11.** Emotional payoff không tự thành survival need; cho custody trước/bypass hoặc nhu cầu cụ thể được bảo vệ. [SCENE_BREAKDOWN.md:1738–1739](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1738-L1739) [SCENE_BREAKDOWN.md:1763–1777](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L1763-L1777) |
| 44 | Dream/ký ức thiếu có thể giấu một fact objective player cần để True không? | **Đứng: không.** Dream S07 chỉ remix anxiety/facts đã thấy, có thể cut không đổi state; không một clue mới hay gian lận reality. [SCENE_BREAKDOWN.md:2188–2204](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/SCENE_BREAKDOWN.md#L2188-L2204) |
| 45 | Biết Nam là boss rồi replay opening có thật đổi nghĩa, hay toàn clue chỉ được bịa ở S16? | **Đứng về seed.** C27/C28/C29, old relation và E24/N1 recontextualize. Current proof cần đến sau là hợp lý; không require boss guess sớm. [CLUE_GRAPH.md:310–364](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L310-L364) [CLUE_GRAPH.md:527–582](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/CLUE_GRAPH.md#L527-L582) [OBJECTIVE_TIMELINE.md:428–458](https://github.com/phambac2k701-blip/cot_truyen/blob/f17628f53e78805e739382ab8d811cea1a07edfe/OBJECTIVE_TIMELINE.md#L428-L458) |

## REQUIRED PATCH PLAN

Thứ tự dưới đây nhằm chốt **fact và state trước**, rồi mới đổi scene/thoại theo chúng. Không sửa một cảnh để cứu một predicate chưa thống nhất. Đây là kế hoạch cho lượt patch tiếp theo; audit này không áp patch story.

| Thứ tự | Việc phải chốt/sửa | Finding | File chính | Điều kiện nghiệm thu |
|---|---|---|---|---|
| **P0 — Khóa source of truth cho patch** | Ghim snapshot, lập mapping canon→objective truth→proof predicate→scene presentation; xác nhận source prose có thẩm quyền và route D được chọn. | Tất cả, đặc biệt H02/H03 | MASTER, BACKSTAGE, CLUE_GRAPH, ENDING_LOGIC | Một fact/predicate chỉ có một nghĩa; không để Stage 7 tự phủ định Stage 4 mà không cập nhật upstream. |
| **P1 — Chốt payload và provenance** | Tạo bảng A/B/C/X/D1/D2 fact, origin, custodian, verification, scope. Khóa core-crime knowledge trong alternatives; D recovery chứng minh cùng authority; giảm early Tuấn claim đúng mức. | H02, H03, H08, M01, M02 | BACKSTAGE, CHARACTER_WEB, CLUE_GRAPH, ENDING_LOGIC | No-Thảo, no-Đức, lost-C32 routes nếu được cho phép phải cùng proposition; không duplicate một origin thành hai proof. |
| **P2 — Tách knowledge/custody/lifecycle** | Player understood khác BARC; organization chỉ nhận observable report. Khởi tạo police case từ E12/E28. Khóa snapshot/receipt/photo existence, access và observation. | H05–H07, M04, M07, L02 | CHARACTER_WEB, OBJECTIVE_TIMELINE, CLUE_GRAPH, ENDING_LOGIC | Cùng visible report→cùng BARC; police không mất own record vì player miss; read lại source còn thật được fact tương đương. |
| **P3 — Chốt clock, acquisition và warning** | Lấy/request C18/C19 trước hạn, late callback dùng retained copy. Khóa authored-time costs, UI reading rule, travel bounds, pre-last-loss warning; sửa next-event IDs. | H04, M03, M08, M09, L01 | OBJECTIVE_TIMELINE, CLUE_GRAPH, PLAYER_STORY, SCENE_BREAKDOWN; FS các dòng clock/lifecycle bị ảnh hưởng | Có ít nhất một schedule không guide-compatible theo lead tự nhiên; mọi irreversible loss có lựa chọn cứu sau warning; không implicit mind/reading penalty. |
| **P4 — Làm kín resolver và branch transitions** | Bao relation-loss/partial state; derive causal ending từ decisive loss, giữ leak attempts riêng; chốt D-only loss taxonomy và precedence; nối weak route tới resolver. | H09, M05, M06 | ENDING_LOGIC, PLAYER_STORY, SCENE_BREAKDOWN | Mọi reachable terminal state có đúng một outcome hoặc explicit ongoing transition; achieved custody không lùi; blame match hành động gây loss. |
| **P5 — Sửa scene tối thiểu theo spec đã khóa** | S08 source lead và limited correction; S12 fast recap + new leadership evidence; S13/S14 conditional flags; S15 real custody; S16 accepted D route; S17 custody-first/bypass; motif cuối giữ subtle function. | M10, M11, L03; presentation của H02–H09 | PLAYER_STORY, SCENE_BREAKDOWN | Không thêm twist/NPC/location/mechanic; scene không nói player biết nhiều hơn run cho phép; mỗi scene đổi chức năng rõ. |
| **P6 — Hoàn tất full script và blind validation** | Viết S06–S18 trong canon theo spec mới; kiểm dialogue/voice, payload per scene, actual duration, cinematic agency; chạy case matrix dưới đây và blind first-run. | H01; xác nhận mọi finding | FULL_SCRIPT và playable fixture khi có | Full read-through không còn gap phải người đọc tự bịa; blind tester tìm lead/source/time từ game, không từ clue IDs/guide. |

### Các quyết định cần chốt để tránh domino

1. **A/B/C có nghĩa gì?** Giữ proposition objective của canon, không thu nhỏ thành giấy tờ lạ. Đổi payload clue thay vì rewrite core crime.
2. **Mất C32 còn được True bằng route nào?** Chọn manager-equivalent hoặc authenticated record authority thật trong nguồn hiện có; đồng bộ D1/D2 và missable table một lần. Không vừa hứa pure records vừa bắt manager ở resolver.
3. **Cái gì Vũ đã giữ trước Bắc?** Chốt record subset E12/E28 rồi derive CASE.A; không dùng player-visible cutscene làm institutional memory.
4. **Bắc hiểu và Nam biết Bắc đang hiểu là hai điều gì?** Private inference có evidence condition; BARC có report condition. Đồng hồ/bad ending không được dùng biến này thay biến kia.
5. **Source đóng thế nào?** Mỗi nguồn có owner/location, access/willingness, copy custody và last-route event. Thu hồi quyền khác xóa record; notebook screenshot khác source authentication.
6. **Một loss được blame cho ai?** Giữ causal source-loss history đủ nhỏ để xác định decisive failure. DIRECT là cause đã xảy ra, không lá cờ thắng mọi leak trước chỉ vì attempt mới hơn.

### Ma trận kiểm chứng bắt buộc sau patch

Các case này kiểm hành vi theo yêu cầu truyện; không phải test lặp lại từng dòng implementation. Có thể chạy dưới dạng narrative/state fixture trước khi build đầy đủ.

| Case | Thiết lập/hành động | Kết quả cần thấy |
|---|---|---|
| T01 | Không probe/leak, dừng ở S07 ≤N1 | G0; baseline world tiếp tục nhưng không tự biến thành G3 hoặc random death |
| T02 | Không share thông tin với Minh | Không có C35 leak payload tự sinh; Minh không biết private source |
| T03 | Cùng reports gửi Nam, private hypothesis của hai runs khác nhau | BARC/response Nam giống nhau; player-understanding khác nhau được phép |
| T04 | Private route, S14 vào do baseline cleanup | BARC không tự lên N3; Nam không có report chưa tồn tại |
| T05 | S13 có fragments nhưng nối sai/thiếu C24 hoặc C25 | Không auto N3/KHẢI certainty; partial route vẫn có transition hợp lệ |
| T06 | Vũ đã có một record từ E12/E28; Bắc miss scene xem record | Custody record ấy không mất; chỉ player knowledge thiếu |
| T07 | C08 direct record mới thật sự chưa giao | A chưa hoàn chỉnh vì đúng missing fact, không vì “chưa click Vũ”; clue nói disclosure mới bổ sung gì |
| T08 | Inspect history C03 muộn khi app chưa bị hạn chế | Nhận same raw fields/equivalent fact với late timestamp; không cần guide click sớm |
| T09 | Seal photo có label legible / photo chỉ seal | C04 recovery đúng nội dung ảnh; không hai run ảnh giống nhau cho fact khác nhau |
| T10 | Đức mất account nhưng copy riêng vẫn giữ; không có discovery | Copy không despawn; cooperation/access xử lý theo event thật |
| T11 | Lấy/request C18/C19 sáng, verify ở S12/S13 sau window | Custody/availability bản đã lấy vẫn hợp lệ; callback không giả pickup mới |
| T12 | Route cuối sắp đóng hoặc leak làm nó đóng sớm | Có warning khi còn một action cứu hợp lý; warning sau loss chỉ giải thích, không tính fairness đã đủ |
| T13 | No-Thảo B route; Yến-only C corroboration | Accepted bundle vẫn chứng minh cùng purposeful/knowledge fact, không chỉ patterns |
| T14 | Lost-C32 route được design hứa cứu | D1/D2 thực sự đủ theo cùng predicate giữa graph, scene và resolver; nếu không đủ, scene không hứa True-capable |
| T15 | A=B=C preserved, X=false, lock; no leak/abandon | Explicit partial/relationship-loss outcome; không undefined state hoặc free X |
| T16 | Minh gây final loss, later harmless direct attempt | Outcome attribution theo decisive loss Minh; attempt không overwrite cause |
| T17 | ABC+X preserved, direct disclosure làm mất D cuối | Outcome theo policy D-only đã chốt; matrix và cinematic cùng blame, custody ABC còn |
| T18 | Toàn ABC+X+D preserved đúng hạn, sau đó confront Nam | G6 giữ nguyên; speech không xóa nguồn police |
| T19 | Police đã đủ tự giữ case, Bắc cắt contact sau custody | Không G3 vì withdrawal muộn vô hại với case đã giữ |
| T20 | Partial chỉ có A+B hoặc A+C, thiếu late command lead | Đến resolver theo weak edges, không bị buộc giả đã biết Nam/Khải |
| T21 | Slow reader inspect/notebook lâu, không chọn delay action | Không mất source vì clock conversion ngầm; wait có chủ ý nếu tốn time phải được thông báo |
| T22 | Player đã sửa nghi Tuấn ở S08 | S12 fast recap rồi new fact; không lặp nguyên correction 5 phút |
| T23 | Player chọn police custody trước, không cần về trọ lúc đang race | Có safe transition; emotional Nam payoff không lấy mất proof/agency |
| T24 | Không inspect C28, không đoán Nam sớm, chọn đúng sources và preserve | True vẫn có thể đạt bằng late current command; không mandatory collectible bí mật |
| T25 | Biết boss từ replay, chọn thông minh từ đầu | Scene cũ consistent, Nam không biết điều ông chưa nhận report; early guess không tự award D |

### Blind first-run acceptance

Cho tester mới không xem bible/clue IDs/guide. Log điều họ **quan sát, suy, chọn và bỏ lỡ**, cùng objective clock và custody events. Kiểm tra họ có tự tìm được source lead trước cửa sổ, biết lý do ưu tiên intake, phân biệt history với command, và giải thích ending bằng hành động của mình.

Nếu tester chọn hợp lý từ dữ kiện game nhưng chỉ thất bại vì một flag/predicate chưa hề được biểu đạt, đó là fairness failure. Nếu tester được notebook/objective/cinematic giải hộ và chỉ thu đủ checklist, đó là inference difficulty failure. Chưa đặt tỷ lệ thắng tuyệt đối từ một mẫu quá nhỏ; định hướng ~10% phải được hiệu chỉnh sau khi actual script/gameplay tồn tại.

Điều kiện ký lại final audit: HIGH đã đóng hoặc có bằng chứng counterexample bị invariant hợp lệ ngăn; mọi remaining issue được ghi nhận cụ thể; full script và route matrix cùng snapshot; thời lượng, thoại và blind discoverability đã được kiểm trực tiếp. Không ký chỉ vì các self-audit trong tài liệu có chữ PASS.

**Phạm vi thay đổi của bước hiện tại:** chỉ tạo báo cáo `FINAL_NARRATIVE_AUDIT.md`. Các phương án sửa ở trên là hướng dẫn cho patch có kiểm soát ở lượt sau; không áp dụng thay đổi lên các file story nguồn trong lần audit này.
