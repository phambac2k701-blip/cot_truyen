# CLUE ARCHITECTURE / CLUE GRAPH

> **Status:** STORY DESIGN — STAGE 4 / DESIGN LOCK CANDIDATE  
> **Parent canon:** MASTER_GAME_BIBLE.md — blob c54f045db49e1523edf304165d2a8af09f5a45b2  
> **Stage 1:** BACKSTAGE_CRIME_TRUTH.md — blob be6d0e99a961945849543db13212c4f23c60a60b  
> **Stage 2:** CHARACTER_WEB.md — blob ce95ed982f7f45955c347b1e5b9499f9bd984bab  
> **Stage 3:** OBJECTIVE_TIMELINE.md — blob ac7736c732fe36e5774d31a6630d39811eeb3ee8  
> **Repository:** phambac2k701-blip/cot_truyen  
> **Date:** 2026-10-04  
> **Scope:** player-facing clue architecture, reveal dependencies, delayed-value clues, red herrings, innocent-suspect logic, boss foreshadowing, true-ending evidence requirements, missable consequences, fairness audit  
> **Không bao gồm:** dialogue hoàn chỉnh, chapter hoàn chỉnh, cinematic direction chi tiết, puzzle implementation, retcon canon

---

# 0. DESIGN CONTRACT

Tài liệu này không thay đổi objective truth.

Mọi clue ở đây chỉ làm một trong ba việc:

1. cho player nhìn thấy một phần sự thật vốn đã tồn tại ở Stage 1–3;
2. cho player nhìn thấy dấu vết được tạo ra bởi hành động objective đã khóa;
3. cho player hiểu lại một dữ kiện cũ sau khi một dữ kiện mới xuất hiện.

Không clue nào được phép tạo ra một sự thật mới chỉ vì mystery cần nó.

Đặc biệt giữ các lock:

- Phúc muốn rút là điểm khởi phát khủng hoảng.
- Hạnh vượt doctrine.
- Huyền phát hiện bằng công việc hợp pháp.
- Khoa giấu độ sâu review.
- Hùng hạ gói nhạy cảm xuống luồng thường vì che sai phạm riêng.
- Bắc được kéo vào một cách ngẫu nhiên hợp lý, không ai chọn cậu.
- Tuấn không biết core crime.
- Minh không phải member network.
- Tân Lộ và Minh Trạch chủ yếu là tổ chức hợp pháp với đa số người vô tội.
- Nam gặp Bắc như hàng xóm trước khi biết Bắc chạm Tân Lộ.
- Nam không biết suy nghĩ/notebook của Bắc.
- Vũ phản ứng theo chất lượng evidence, không bị viết ngu để kéo dài game.
- Không có single magic evidence.
- True ending phải chứng minh A+B+C+D bằng corroboration và timing.

Bốn proposition khách quan từ Stage 1 tiếp tục là xương sống:

- **A — Source/Coercion:** tồn tại hệ thống môi giới người tham gia hiến tạng bất hợp pháp và gây sức ép khi họ muốn rút.
- **B — Hospital Cell:** một cell nhỏ trong Minh Trạch biết và hỗ trợ biến một số trường hợp thành hồ sơ có vẻ hợp lệ.
- **C — Logistics Complicity:** một số lãnh đạo Tân Lộ biết và chủ ý hỗ trợ mạng lưới; Tân Lộ không chỉ là nhà vận chuyển tình cờ.
- **D — Command:** Nam là người thiết kế/điều phối có quyền quyết định trên nhiều nhánh, không chỉ là người quen xa của vài manager.

Contract proof/provenance tại BACKSTAGE_CRIME_TRUTH §0.1 giữ cùng nghĩa A/B/C/X/D với §53. Nguồn chép lại cùng lời kể không thành factual corroboration thứ hai; contact/timing không thay current authority. Các gates dưới đây chỉ mở khi payload và verification đã đủ, không chỉ vì sở hữu clue ID.

---

# 1. TAXONOMY

Một clue có thể mang nhiều loại cùng lúc.

- **A. Mandatory Progression Clue:** đủ rõ để trục story không kẹt; không đồng nghĩa tự giải mystery.
- **B. Optional Understanding Clue:** không bắt buộc để đi tiếp nhưng giúp hiểu đúng người, động cơ hoặc mức độ culpability.
- **C. True Ending Clue:** thuộc một slot evidence cần cho true ending hoặc là nguồn thay thế hợp lệ cho slot đó.
- **D. Delayed-Value Clue:** thấy sớm, lúc đầu bình thường, về sau đổi nghĩa.
- **E. Red Herring:** dữ kiện thật có thể hỗ trợ một giả thuyết sai hợp lý.
- **F. Environmental Noise:** chi tiết thật nhưng không có chức năng chứng minh plot; bảo vệ cảm giác đời sống.
- **G. Character Behavioral Clue:** hành vi, phản ứng, giới hạn knowledge hoặc thói quen.
- **H. Digital Clue:** log, tin nhắn, metadata, version history, contact record, hồ sơ số.
- **I. Physical Evidence:** vật, giấy, nhãn, biên nhận hoặc bằng chứng vật lý.
- **J. Timing/Alibi Clue:** giá trị nằm ở thứ tự/thời điểm hơn là nội dung đơn lẻ.

Nguyên tắc notebook:

- Notebook được phép ghi **fact thô + nguồn + thời gian + địa điểm**.
- Notebook không được tự viết các kết luận như “Tuấn vô tội”, “Hùng là boss”, “Nam đứng sau tất cả”.
- Với delayed-value clue, notebook có thể giữ entry cũ để player tự quay lại đọc, nhưng không tự bật popup “clue này giờ quan trọng”.
- Evidence do police đã preserve có thể đổi trạng thái thành “đã bàn giao”, nhưng game không tự nói nó chứng minh proposition nào.

---

# 2. CLUE CATALOG

## 2.1. Opening / E22 bridge

| ID | Loại | Dữ kiện player có thể thấy | Xuất hiện lần đầu | Ý nghĩa lúc đầu | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C01 | F, H | Tin tuyển việc part-time Tân Lộ, ca ngắn, điều khoản bình thường; Minh từng dùng kênh này | D0 sáng, E21 | Công việc sinh viên hợp pháp | Chứng minh Tân Lộ thật sự có lao động part-time; Bắc không ngu khi nhận việc | Auto |
| C02 | A, D, H, J | Assignment E22 hiện như job thường nhưng có một trường “nhóm khách hàng y tế/ưu tiên” và thời điểm tạo bất thường sát D−1 | D0 trưa, E22 | Một nhãn vận hành khó hiểu | Sau C17, player nhận ra job đã bị hạ classification | Auto, fact thô |
| C03 | A, D, I, J | Proof-of-handover/biên nhận ở đầu nhận dùng cùng client/account family mà player về sau gặp trong review Minh Trạch | D0 trưa, E22 | Biên nhận bình thường | Bridge sớm giữa logistics và hospital; không tự chứng minh tội phạm | Nếu inspect |
| C04 | B, D, I | Bao/gói có dấu đã được dán lại nhãn vận hành hoặc thay lớp routing ngoài; không có nội dung “bí mật” lộ ra | D0 trưa | Có thể chỉ là xử lý kho | Sau C17 cho thấy classification thực sự đã đổi | Nếu inspect |
| C05 | E, G | Tuấn phản ứng khó chịu khi Bắc hỏi vì job đang bị audit; nhấn mạnh quy trình và trách nhiệm nhân viên | D0 chiều/tối nếu hỏi | Tuấn trông như người che việc | Sau C20/C22, hành vi được hiểu là tự bảo vệ nghề nghiệp, không phải biết organ network | Có nếu interaction |
| C06 | F | Nhiều job Tân Lộ khác tới phòng khám/doanh nghiệp y tế hoàn toàn bình thường | D0 và D+1 | Background | Ngăn suy luận “xe Tân Lộ ở bệnh viện = tội phạm” | Không |
| C07 | B, E, H | Lịch sử việc làm/trao đổi cũ cho thấy Minh thực sự từng nhận ca Tân Lộ như sinh viên bình thường | D0 sáng/tối | Minh có vẻ có “connection” | Về sau giải thích Minh không phải plant/member; betrayal vẫn là thật | Nếu xem chat |

## 2.2. Proposition A — Phúc / coercion

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C08 | A, C, H, J | Original Phúc–môi giới gồm hứa trả tiền gắn với cung cấp nội tạng, yêu cầu rút, rồi phản hồi ép tiếp tục viện tiền đã ứng; từng message có người viết/thời điểm rõ | Nội dung được police bổ sung E28; player xem D+1 qua Vũ/Phúc | Thỏa thuận bị gọi là hiến tự nguyện nhưng có tiền và withdrawal thật | Core content A, cần authentication C10; player xem muộn không thay custody | Auto khi được xem hợp lệ |
| C09 | B, H, J | Dấu vết Phúc đã từng đồng ý/nhận một phần tiền hoặc bước vào quy trình | Cùng route Phúc | Làm lời kể Phúc kém “sạch” hơn | Giải thích omission/xấu hổ; tăng fairness, tránh viết nạn nhân hoàn hảo | Auto |
| C10 | A, C, H, J | Police chronology ghi E28 so exact C08 content với original message thread broker counterpart giữ trước intake: paid-organ agreement/withdrawal/pressure; hospital visit record kiểm riêng D−14 | Police giữ A authentication từ E28; player xem D+1 | Exact content được đối chiếu ở custodian ngoài Phúc | Counterpart original content xác nhận text từng fact; metadata chỉ exchange/order, hospital chỉ visit. Không count chronology/copy lời Phúc là crime origin mới | Auto |
| C10_SOURCE_LINK | C, H, J | Late annex cùng case/custodian: original Hạnh→Khải request forward scoped Phúc, reply directive xuống broker và broker receipt áp dụng; Vũ match nội dung/endpoint/scope với exact authenticated Nam directive D2 | S16 15:00–17:00 sau E38 thực tế, trước E40 closure/lock; chưa có future record ở E28 | Nhánh nguồn thực sự nhận/thực hiện cùng directive hiện tại | Required verification context cho full D cả ba nhánh, không independent D2 thứ ba; Phúc không giữ hidden Hạnh–Khải messages | Police verify; notebook chỉ fields được phép |
| C11A | B, D, J | Timestamp Phúc trình báo nằm trước E22 nhiều ngày | D+1 | Chi tiết thời gian | Recontextualize toàn opening: conspiracy/crisis có trước Bắc | Auto |

## 2.3. Proposition B — Minh Trạch

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C11 | A, C, H, J | Review Huyền mở D−12 giữ yêu cầu kiểm tra nêu tiền/withdrawal của Phúc, đối chiếu hồ sơ vẫn ghi consent tự nguyện/không trao đổi tiền và các case có discrepancy lặp | D+1 sáng, E33 | Compliance discrepancy có nguồn và fields cụ thể | Compliance origin cho B; cần C12 hoặc C15 chứng minh actor biết và vẫn hỗ trợ vẻ hợp lệ. Huyền chưa biết toàn network | Auto nếu được tiếp cận hợp lệ |
| C12 | B, C, H, J | Receipt/approval trail Khoa đã nhận phần review ghi tiền và withdrawal; version sau vẫn giữ consent misleading và thu hẹp scope | D+1 E33 | Có cả notice được nhận và hành động giữ hồ sơ | No-Thảo B corroborator về knowledge + assistance, cùng nghĩa C15; bare scope timestamp chưa đủ | Nếu inspect/được chia và Vũ verify |
| C13 | E, G | Huyền từ chối cung cấp một số dữ liệu khi Bắc chưa có quyền/lý do hợp lệ | D+1 | Có thể trông như che giấu | Về sau player thấy tiêu chuẩn của Huyền nhất quán và chính bà mở review | Có dưới dạng interaction note |
| C14 | B, G | Thảo dùng cách framing thay đổi khi câu hỏi chuyển từ giấy tờ sang hoàn cảnh người tham gia | D+1 | Bà có thể chỉ là bác sĩ phòng thủ | Cho thấy knowledge lớn hơn người chỉ xử lý hồ sơ | Nếu interaction |
| C15 | C, G | Thảo xác nhận case mình trực tiếp xử lý: biết tiền bên ngoài/ý định rút nhưng phần hồ sơ mình tham gia vẫn giữ nghĩa consent tự nguyện | D+1 E33 | Admission giới hạn về knowledge + assistance | Cùng proposition với C12, so được với C11; không cấp cho bà Nam/logistics/toàn nguồn người | Auto khi Vũ intake |
| C16 | B, H, J | Timing Khoa can thiệp scope xảy ra sau review Huyền và trước/đúng lúc báo lên Khải | D+1 | Administrative intervention | Dẫn từ hospital anomaly tới management risk layer | Nếu nguồn hợp lệ |
| C16A | F | Nhiều lỗi hồ sơ nhỏ khác ở bệnh viện không liên quan network | D+1 | Background realism | Ngăn player coi mọi anomaly là clue | Không |

## 2.4. Proposition C — Tân Lộ leadership

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C17 | A, C, H, J | Reclassification log cho thấy job E22 từng ở luồng hạn chế rồi được chuyển xuống pool thường D−1 | D+1 sáng | Chứng minh job không “tự nhiên” là thường | Core C bridge; đúng objective E19 | Auto nếu mở được source |
| C18 | C, H, J | Snapshot Đức giữ nhận diện cùng nhóm bàn giao/đầu nhận của C22, ngoại lệ lặp và thay đổi lúc audit; chỉ fields/interactions vận hành anh trực tiếp thấy | D+1 E32 | Insider tự bảo hiểm | Corroboration vận hành độc lập với approval C22; không cho Đức biết purpose đầy đủ hoặc ai được secret core briefing | Auto khi nhận |
| C19 | B, C, H | Đối soát Yến nhận diện cùng nhóm bàn giao/đợt thanh toán của C22, giá trị khác dịch vụ tương ứng và pattern lặp | D+1 E35 hoặc police verify | Finance anomaly có match cụ thể | Yến-only corroboration C hợp lệ cùng C17+C22 có knowledge; finance không tự nói crime hoặc Nam | Auto nếu được verify |
| C20 | B, E, H, J | Authority chain đặt thay classification trước phần việc Tuấn; records cho fields anh nhận và câu hỏi mục đích chưa được cấp trên giải đáp | D+1 | Tuấn không phải người reclassify | S08 chỉ TUAN_NOT_RECLASSIFIER; Vũ xác minh scope từ nguồn giao việc/records ở S12 mới có TUAN_CORE_SCOPE_VERIFIED, không suy innocence chỉ từ thiếu quyền | Auto |
| C21 | B, G, H | Một record đời thường cho thấy Tuấn từng phản đối job thiếu chứng từ/đòi checklist ở vụ không liên quan | D0/D+1 | Chi tiết nghề nghiệp | Sau C20, củng cố rằng procedural defensiveness của anh là thật | Optional |
| C22 | A, C, H, J | Approval trail Hùng đã nhận thông tin nhóm hồ sơ liên quan tiền trả cho người hiến trước approve; vẫn xử lý và tự hạ luồng cùng đầu việc E22 | Seed authority S08; purpose/record được verify S12 | Trách nhiệm ở leadership, biết purpose khi quyết định | C knowledge + assistance khi match A/B và C18 hoặc C19; không chứng minh Hùng là apex | Auto khi source hợp lệ |
| C23 | B, H, J | Audit request từ Khải tới Tân Lộ bắt đầu D−7, trước job E22 | D+1 | Công ty đang bị rà trước Bắc | Cắt giả thuyết “Bắc làm mọi thứ bắt đầu” và dẫn tới risk layer | Optional/auto nếu source |

## 2.5. Cross-cell connector / Khải

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C24 | C, H, J | Sau review Huyền, Khoa gửi incident request tới Khải về crisis Phúc; source xác nhận scope nhận incident/định hướng pause trong quyền Khải được giao, không cần lộ toàn body | D+1 | Hospital manager có một đầu mối xử lý risk | Half connector có endpoint + role/context, không chỉ call timestamp | Auto nếu được xem qua police/hospital source |
| C25 | C, H, J | Sau breach E22, Hùng/Tân Lộ gửi incident/escalation cùng crisis tới Khải; source xác nhận role/context phản hồi đối với logistics | D+1 | Logistics có risk contact cần đối chiếu | Half connector độc lập; cùng C24 verify current shared risk role, chưa nói Nam authorize | Auto nếu source được xem |
| C26 | C, D, H, J | C24+C25 match đúng endpoint Khải, scope request/response và crisis context; khác cùng vendor/khách hàng hợp pháp | D+1 trưa | Một tầng quản trị risk chung trên hai institution | Inference về current shared risk structure, ngoài relation cùng giao dịch đã có thể rõ ở ABC | Notebook giữ hai entry, không tự nối |
| C26A | B, G | Khải nói/ứng xử chính xác trong phạm vi hẹp nhưng tránh mọi câu về phạm vi quyền của mình | Late D+1 | Có vẻ như consultant lạnh lùng | Character clue: dangerous vì biết giao điểm, không vì biểu diễn villain | Optional |

## 2.6. Betrayal / exposure

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C35 | B, E, H, J | Minh liên hệ Tuấn/đầu mối công việc ngay sau khi Bắc hỏi sâu | D0 tối hoặc D+1 | Có thể là xử lý công việc | Sau source closures, đây là leak path hợp lý | Auto nếu phát hiện |
| C36 | B, E, G | Minh giảm nhẹ lượng thông tin mình đã nói, nhưng chi tiết Tuấn biết vượt phần Bắc trực tiếp nói với công ty | D0 tối/D+1 | Minh trông như liar/member | Về sau C07 cho thấy động cơ là sợ và giữ việc, không phải network membership | Interaction note |
| C37 | B, J | Một source/access bị siết sớm hơn bình thường sau leak | D+1 | Có thể là coincidence cleanup | Nếu timing bám sát C35, chứng minh betrayal có hậu quả dù Minh không biết network | Auto timeline |

## 2.7. Boss / proposition D

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C27 | B, D, G | Lan/đời sống khu trọ cho biết Nam từng làm kho vận và thiết bị/dịch vụ liên quan y tế | D0 opening | Tiểu sử một ông lớn tuổi | Sau A+B+C, hai lĩnh vực trùng đúng các nhánh chính; vẫn chưa phải proof | Auto People note |
| C28 | B, D, I | Một vật cũ hợp lý ở góc sửa đồ của Nam gợi quan hệ nghề nghiệp cũ với Tân Lộ: biên nhận cũ/card/đồ quảng cáo từ thời công ty mới phát triển | D0 opening nếu inspect | Đồ cũ từ nghề trước | Sau khi biết Hùng/Tân Lộ, chứng minh Nam thật sự từng có quan hệ; không chứng minh command | Nếu inspect |
| C29 | D, G | Nam thực sự giúp Bắc/nhà trọ ở việc đời thường và không cố lôi Bắc vào network | D0 opening | Tử tế bình thường | Sau reveal, player hiểu kindness không phải fake; làm boss phức tạp và scene đầu đổi nghĩa | Không đánh dấu “clue” |
| C30 | B, C, D, H/I | Record kinh doanh cũ hợp pháp xác nhận Nam từng giúp Hùng tiếp cận khách hàng/vốn/quan hệ khi Tân Lộ khó khăn | Late D+1 qua source công khai/manager/police | Old business relation | Tăng weight cho C27/C28 nhưng vẫn chưa chứng minh 2026 command | Auto |
| C31 | B, D, H, J | Current-crisis Khải–Nam contact metadata; Vũ kiểm endpoint identity qua source gốc/lịch sử đầu mối nghề nghiệp, không chỉ display name | Late D+1 | Nam được risk manager cập nhật | Lead/auth context cho command investigation; contact metadata không phải D1 hoặc D2, kể cả khi trùng giờ closure | Auto nếu police/source |
| C32 | C, G/H | Family manager firsthand current command: chỉ hai routes C32H/C32K bên dưới, không một manager kể toàn mạng | Late D+1 15:00–17:00 | Authority trong branch source trực tiếp biết | D1; mất Hùng phải thay bằng Khoa, không bằng pure C33+C34 | Auto khi Vũ intake |
| C32H | C, G/H | Hùng mô tả quyết định logistics trong crisis D+1 mà ông trực tiếp phải xin và nhận Nam approve; lead C22/C25, trigger records trách nhiệm/thu hẹp quyền ông đã nhận | Late D+1 sau intake đủ nguồn | Nam có quyền thật trên logistics | D1 Hùng route; cần C33_AUTH hospital độc lập | Auto khi police receives |
| C32K | C, G/H | Khoa mô tả quyết định hiện tại về cell hospital mình trực tiếp nhận từ Nam; lead C11/C12/C24, trigger receipt/approval và quyết định thu hẹp cell ông đã nhận | Cùng window, recovery khi Hùng rút | Nam có quyền thật trên hospital | D1 recovery; cần C34_AUTH logistics độc lập. Thảo không thay Khoa | Auto khi police receives |
| C33 | C, H, J | Original hospital record lời Nam authorize qua Khải: nội dung pause/tiếp tục, scope quyền, điều kiện xin approve lại; receipt/execution hospital. C33_AUTH chỉ khi Vũ xác thực original, identity và chain | Late D+1, intake độc lập với Hùng | Một quyết định hiện tại có người authorize và hành động thực | D2 cho C32H; record origin/custody hospital khác trải nghiệm D1 logistics. Timing không có nội dung/authentication chưa đủ | Auto khi nguồn/authentication được thấy |
| C34 | B, D, H, J | Generic pattern hospital/logistics/môi giới cùng thu hẹp là lead. Subset C34_AUTH riêng: original logistics lời Nam approve qua Khải, scope pause/tiếp tục và operational execution được Vũ authenticate | Late D+1, intake Tân Lộ độc lập với Khoa | Pattern hỗ trợ timing; AUTH subset có current authority | Chỉ C34_AUTH làm D2 cho C32K. Generic simultaneous closures không chứng minh Nam; không count hai copies cùng order là hai origins | Notebook giữ raw records/timestamps |

## 2.8. Timing / preservation

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C42 | A, C, H, J | Vũ/police ghi A custody đã có từ E28 và intake/preservation B/C/X/D còn thiếu trước cleanup | D+1 chiều | “Nguồn đã được giữ trong hồ sơ” | Không buộc Bắc giao lại A; giữ source khỏi quyền xóa của network, true timing gate | Auto |
| C43 | A, J | Access Đức/Yến/review bị đóng hoặc thu hẹp theo các mốc Stage 3 | D+1 trưa–chiều | Một cửa đã đóng | Chứng minh missable consequence và tạo race với cleanup | Auto event |
| C44 | F, J | Một số việc đời thường vẫn tiếp tục đúng giờ trong lúc crisis diễn ra | Cả D0/D+1 | Background | Nhắc player thế giới không chờ mình; không phải timer UI | Không |

---

# 3. MAJOR REVEALS

Các reveal dưới đây là những lần player phải thay đổi mô hình mental của câu chuyện. Mỗi reveal đều có dữ kiện trước reveal và không phụ thuộc một clue duy nhất.

## R1 — Job E22 không phải một job thường “tự nhiên” bị kỳ lạ

1. **Player cần hiểu:** job Bắc nhận là một đầu việc vốn ở luồng hạn chế nhưng đã bị người có quyền hạ xuống luồng thường; Bắc không được “chọn”.
2. **Clue dẫn tới:** C02, C03, C04 → C17 → C22.
3. **Xuất hiện lần đầu:** D0 trưa ở chính job E22; xác nhận vào D+1.
4. **Hiểu ngay hay về sau:** C02–C04 chỉ tạo cảm giác lạ; C17 mới đổi nghĩa chúng.
5. **Interpretation sai hợp lý:** Tuấn/dispatch vô tình giao sai; lỗi phần mềm; một job VIP bị nhập sai.
6. **Clue bổ sung xác nhận:** C20 loại Tuấn khỏi authority hạ classification; C22 truy quyết định lên Hùng.
7. **Nếu bỏ lỡ:** story vẫn có thể đi qua route Phúc/hospital, nhưng C yếu; true ending cần route phục hồi C17 hoặc source Đức/Yến.
8. **Notebook:** ghi assignment, receipt và timestamps, không ghi “bị hạ luồng”.
9. **Mandatory main story:** Có ở mức “job có anomaly”; chi tiết người hạ classification không bắt buộc để một bad/partial route tiến.
10. **True ending:** Có. C phải được chứng minh bằng reclassification + corroboration leadership.

## R2 — Paid-organ agreement thật; withdrawal trước pressure và case có trước Bắc

1. **Player cần hiểu:** thỏa thuận có tiền gắn trực tiếp với cung cấp nội tạng được gọi là hiến tự nguyện; sau khi Phúc yêu cầu rút, môi giới ép tiếp tục. Không chỉ một tranh chấp tiền bất kỳ.
2. **Clue:** nội dung C08 + authentication/chronology C10; C09/C11A cho omission và crisis trước Bắc.
3. **Xuất hiện:** police nhận bản còn thiếu và authenticate E28; player xem phần được phép ở S09/S11 D+1.
4. **Hiểu:** phải đọc nội dung và thứ tự, không chỉ so timestamp; C10 ghi record nào kiểm chứng fact nào.
5. **Sai hợp lý:** Phúc hối hận, kể thiếu mức đồng ý/tiền ban đầu; tầng môi giới trực tiếp là toàn vụ.
6. **Xác nhận:** Vũ so exact C08 content với original broker counterpart thread ở E28: lời hứa tiền/cung cấp nội tạng, agreement/withdrawal và pressure text từng fact. Metadata xác nhận exchange/order; hospital xác nhận visit. Chỉ hai phần sau không authenticate text; lời Phúc được police chép lại không tạo origin độc lập.
7. **Nếu bỏ lỡ encounter:** A_PLAYER_SEEN thiếu, nhưng CASE.A đã police-preserved từ E28 không lùi; bridge X vẫn cần nguồn mới.
8. **Notebook:** tách nội dung trực tiếp, kết quả authenticate và Phúc suy đoán; không tự ghi network.
9. **Mandatory:** player cần gặp core nội dung/withdrawal→pressure nếu route dùng A, không cần gặp Phúc trực tiếp.
10. **True ending:** A phải có đủ content + authentication trong custody; không yêu cầu Bắc giao lại chronology thuộc Vũ.

## R3 — Một hospital cell biết facts bị che trong consent và vẫn hỗ trợ vẻ hợp lệ

1. **Player cần hiểu:** C11 ghi discrepancy cụ thể về tiền/withdrawal; C12 hoặc C15 cho actor đã biết và vẫn giữ consent misleading. Không kết luận toàn bệnh viện guilty.
2. **Clue:** C11 + C12 hoặc C15; C13/C14/C16 là behavior/timing hỗ trợ.
3. **Xuất hiện:** D+1 E33/S10 hospital window.
4. **Hiểu:** Huyền mở review, không tạo anomaly. Receipt Khoa được thông báo trước hành động hoặc lời Thảo firsthand mới thêm knowledge/assistance.
5. **Sai hợp lý:** scope đổi vì administrative error; Huyền che; cả institution cùng dính.
6. **Xác nhận:** C11 compliance origin + C12 management receipt/version trail hoặc C15 firsthand riêng; so A đã authenticate để xác nhận cùng fact/case. Hai copies cùng review không count hai origins.
7. **Nếu miss:** B chưa đủ nếu chỉ có pattern hoặc timestamp; route A/A+C vẫn có thể fail-forward.
8. **Notebook:** giữ fields, notice được nhận, version và source statement; không tự gắn culpability.
9. **Mandatory:** pattern trên hospital route; một knowledge/assistance corroborator cần nếu muốn chứng minh B.
10. **True ending:** C11+C12 và C11+C15 phải cùng nghĩa. No-Thảo route thiếu receipt/knowledge payload không được coi đủ.

## R4 — Hùng biết paid-organ purpose khi approve hỗ trợ logistics

1. **Player cần hiểu:** không chỉ có override; Hùng đã nhận thông tin tiền trả cho người hiến của nhóm hồ sơ này, vẫn approve xử lý/hạ luồng. Phần lớn nhân viên vô tội.
2. **Clue:** C17 + C22 knowledge/approval + C18 hoặc C19 match cùng đầu việc; C23 cho audit có trước Bắc.
3. **Xuất hiện:** D0 anomaly; S08 reclassification; S12 purpose/leadership source được verify.
4. **Hiểu:** C17 đơn lẻ vẫn có thể là corporate misconduct. C22 thêm purpose được biết; independent operational/finance origin xác nhận handling thật, so A/B xác nhận crime liên quan.
5. **Sai hợp lý:** dispatch accident; Tuấn culpable; company fraud riêng không chạm hospital/Phúc.
6. **Xác nhận:** C18 snapshot vận hành hoặc C19 đối soát vốn có, độc lập với C22 approval trail; không cần Đức/Yến biết toàn crime.
7. **Nếu miss:** thiếu knowledge ở C22 thì C chưa đủ dù có nhiều anomalies; police reconstruction phải khôi phục cùng fact từ nguồn rõ.
8. **Notebook:** giữ raw approval, thông tin đã nhận, source và match; không tự viết Tân Lộ là front.
9. **Mandatory:** bridge tối thiểu cho story, đủ payload nếu branch claim C proved.
10. **True ending:** C17+C22 có knowledge+assistance và một corroborator độc lập. Yến-only route có cùng nghĩa; Tuấn không thay nguồn knowledge ông chưa có.

## R5 — Tuấn: correction người tạo E19 riêng với scope core knowledge

1. **Player cần hiểu:** C20 loại Tuấn khỏi người reclassify; thiếu quyền không tự chứng minh không biết crime. Truth Tuấn không biết core vẫn giữ nguyên.
2. **Clue:** suspicion C05/C35; C20/C22 sửa origin; C21 và records fields/câu hỏi Tuấn nhận giúp Vũ verify scope. Đức chỉ xác nhận interactions vận hành mình thấy.
3. **Xuất hiện:** D0 nghi thật; S08 có TUAN_NOT_RECLASSIFIER; S12 có thể hoàn tất TUAN_CORE_SCOPE_VERIFIED qua intake có nguồn.
4. **Hiểu:** player được giữ nghi ngờ hợp lý khi chưa có knowledge evidence; không phải chấp nhận lời Đức về secret briefing mà Đức không biết.
5. **Sai hợp lý:** Tuấn cố ý chọn Bắc; Tuấn biết purpose vì dispatch role.
6. **Xác nhận:** Vũ so assignment/source giao việc, fields được chuyển và câu hỏi nghiệp vụ chưa được giải đáp, cùng lời Tuấn giới hạn. C20 permission đơn lẻ chỉ có limited correction.
7. **Nếu miss:** có thể chọn tiếp probe Tuấn và tốn authored action time sau warning; private suspicion không tự đóng nguồn hoặc game-over.
8. **Notebook:** facts về origin/scope, không badge innocence hoặc secret hierarchy.
9. **Mandatory:** main story không kẹt vì chưa giải hết Tuấn; strong route dùng leadership facts, không đòi player tin một kết luận quá evidence.
10. **True ending:** không có flag chấp nhận Tuấn vô tội làm hidden quiz; chỉ hành động delay/leak thật có thể làm miss C/D timing.

## R6 — Minh phản bội lòng tin nhưng không phải network member

1. **Player cần hiểu:** Minh làm lộ câu hỏi/hành vi của Bắc vì sợ mất việc và tin Tân Lộ là một công ty bình thường đang xử lý vấn đề.
2. **Clue:** C07, C35, C36, C37.
3. **Xuất hiện:** C07 rất sớm; leak D0 tối; hậu quả D+1.
4. **Hiểu:** C07 ban đầu chỉ là background; sau C35 nó trở thành bằng chứng cho động cơ mundane.
5. **Sai hợp lý:** Minh là plant được cài vào lớp; Minh được network trả tiền để theo dõi Bắc.
6. **Xác nhận:** lịch sử part-time thật, nội dung/timing leak, giới hạn knowledge của Tuấn.
7. **Nếu miss:** player có thể tiếp tục chia sai người, tăng tốc cleanup.
8. **Notebook:** chỉ ghi liên hệ/timing nếu player biết được; không tự gắn “betrayal”.
9. **Mandatory:** Không; một run có thể không kích hoạt betrayal nếu Bắc không hỏi Minh sâu.
10. **True ending:** Không bắt buộc phải “bắt quả tang Minh”, nhưng tránh leak sớm là điều kiện timing quan trọng.

## R7 — A+B+C là ba mặt của cùng một network

1. **Player cần hiểu:** ngoài relation cùng giao dịch A/B/C, hospital và logistics cùng escalates crisis Phúc qua một tầng risk hiện tại; việc từng box có tội chưa tự chứng minh tầng quản trị chung.
2. **Clue:** A: C08 content + C10 authentication. B: C11 + knowledge/assistance C12 hoặc C15. C: C17+C22 có purpose + C18/C19. Bridge: C24+C25/C26; C03 chỉ lead tới relation phải được source-verified.
3. **Xuất hiện:** seed từ D0, đủ dữ kiện khoảng D+1 trưa.
4. **Hiểu:** không clue nào tự nói “network”; player phải nối source độc lập.
5. **Sai hợp lý:** Phúc gặp môi giới nhỏ; hospital có compliance issue riêng; Tân Lộ có corporate fraud riêng.
6. **Xác nhận:** sourced C24/C25 có endpoint, risk role, scope request/response và crisis context để Vũ verify; không chỉ same group/case hoặc cùng consultant. C03 là transaction bridge lead; equivalent X phải reconstruct cùng current risk relation, không chỉ match đầu nhận.
7. **Nếu miss:** N3 không đạt; police vẫn xử lý từng hộp nhưng không mở rộng đủ trong game window.
8. **Notebook:** lưu ba timeline riêng, không auto draw arrow.
9. **Mandatory:** Đây là core inference của main mystery.
10. **True ending:** Có. A+B+C phải được police-preserved, không chỉ nằm trong notebook.

## R8 — Hùng/Khoa/Hạnh đều có tội và đều che lỗi riêng, nhưng không ai trong họ giải thích toàn bộ mạng

1. **Player cần hiểu:** structure không phải “một manager xấu”; các manager có động cơ khác nhau và information limits thật.
2. **Clue:** Hùng C22/C23; Khoa C12/C16/C24; Hạnh từ C08/C10 và source môi giới; Đức chỉ có belief từ scope C18 rằng Hùng là đỉnh; C26 cho thấy layer Khải ở trên cross-cell.
3. **Xuất hiện:** D+1.
4. **Hiểu:** mỗi source có thể làm player dừng sớm ở một “boss giả”.
5. **Sai hợp lý:** Hùng là mastermind vì CEO; Khoa là mastermind vì hospital; Hạnh là mastermind vì source người.
6. **Xác nhận:** knowledge mismatch — mỗi người thiếu một phần mà một mastermind phải biết; Khải xuất hiện ở giao điểm.
7. **Nếu miss:** player có thể đạt partial ending bắt/đẩy được một manager nhưng lõi sống.
8. **Notebook:** ghi mỗi người theo facts, không có hierarchy auto-generated.
9. **Mandatory:** Hiểu có layer cao hơn cần cho late route.
10. **True ending:** Có, vì D chỉ mở khi player không dừng ở Hùng/Khoa/Hạnh.

## R9 — Nam có current command được manager và other-branch record chứng minh

1. **Player cần hiểu:** manager biết authority branch mình; record authenticated ở branch khác cho cross-cell command. Kindness/đời sống Nam vẫn thật.
2. **Clue:** seed C27/C28/C29; history C30; C31 lead/auth context; D1 C32H/C32K; D2 C33_AUTH/C34_AUTH theo route; late C10_SOURCE_LINK trong source case cho scope cả ba nhánh.
3. **Xuất hiện:** seed D0; current proof D+1 15:00–17:00 ở S16.
4. **Hiểu:** background/old relation chỉ hypothesis; contact metadata chỉ current link. D cần đúng accepted pair, không trùng giờ suy Nam approve.
5. **Sai hợp lý:** old business acquaintance; Hùng hoặc Khải apex; Khải gửi chỉ đạo mà tự gắn tên Nam.
6. **Xác nhận:** Vũ kiểm original authorize, endpoint identity, Khải forwarding và other-branch execution từ institutional custodian; so C10_SOURCE_LINK source broker receipt với cùng actual D2 directive. D1 firsthand manager và D2 là quyết định khác ở branch khác/origin khác, không copy một order hai lần.
7. **Nếu miss:** mất C32H có thể recovery C32K+C34_AUTH; mất cả manager routes thì thiếu D1, dù giữ C33 và generic C34. ABC safe vẫn partial.
8. **Notebook:** giữ source statement, nội dung approve, identity verification và timestamps; không tự viết Boss.
9. **Mandatory:** late route có lead; lượng proof quyết định ending. Vũ trực tiếp intake manager theo trigger tự bảo vệ, Bắc không ép confession.
10. **True ending:** D=(C32H+C33_AUTH) hoặc (C32K+C34_AUTH), cùng C10_SOURCE_LINK verified/preserved trước lock để đủ cả ba nhánh. Pair thiếu source link chỉ nói hospital/logistics authority; C31 hoặc C33+generic C34 không thay accepted pair.

## R10 — Biết sự thật không bằng bảo toàn được sự thật

1. **Player cần hiểu:** notebook của Bắc không đủ; evidence phải rời khỏi tay một sinh viên và được Vũ/police preserve trước cleanup.
2. **Clue:** C42, C43, evidence lifecycle, phản ứng Vũ tăng theo source quality.
3. **Xuất hiện:** được foreshadow từ việc access thay đổi D+1; rõ ở police route.
4. **Hiểu:** ban đầu “đã chụp/đã nhớ” có vẻ đủ; về sau player thấy source có thể mất context/quyền truy cập.
5. **Sai hợp lý:** gom đủ clue trong notebook là tự động true ending; Vũ cần được thuyết phục bằng một theory dài.
6. **Xác nhận:** Vũ tiếp nhận source cụ thể, preservation xảy ra, cleanup sau đó không xóa được chúng.
7. **Nếu miss:** có thể player hiểu đúng toàn bộ nhưng nhận Cleanup/Exposure vì chain chưa được preserve.
8. **Notebook:** có trạng thái nguồn: observed / source still open / handed to police; không có progress bar A/B/C/D.
9. **Mandatory:** Có cho late progression.
10. **True ending:** Bắt buộc về timing.

---

# 4. DELAYED-VALUE CLUES — SIGNATURE SYSTEM

Delayed-value không phải easter egg. Đây là nhịp nhận thức chính của game.

Quy tắc:

**thấy A sớm → A có nghĩa đời thường → biết B → player tự nhớ A → A đổi nghĩa, nhưng vẫn không tự trở thành proof hoàn chỉnh.**

Không dùng popup “CLUE UPDATED: THIS WAS IMPORTANT”.

## DV1 — Nghề cũ của Nam

- **A sớm:** C27 — Nam từng làm kho vận và thiết bị/dịch vụ y tế.
- **Lúc đó:** hợp với một người 61 tuổi biết sửa đồ và có lịch sử nghề nghiệp.
- **B về sau:** player xác nhận Tân Lộ + Minh Trạch là hai cell của cùng network.
- **Nghĩa mới:** background của Nam nằm đúng giao điểm hai lĩnh vực.
- **Giới hạn fairness:** không được count là D proof. Hàng nghìn người có thể có background tương tự.
- **Replay value:** cực rõ, nhưng run đầu vẫn chưa đủ để đoán boss chắc chắn.

## DV2 — Vật cũ Tân Lộ ở chỗ Nam

- **A:** C28 — một vật/biên nhận/card cũ từ quan hệ nghề nghiệp.
- **Lúc đó:** junk nghề cũ.
- **B:** Hùng được xác nhận là manager culpable; C30 xác nhận quan hệ Nam–Hùng có lịch sử.
- **Nghĩa mới:** Nam không chỉ “biết tên công ty”.
- **Giới hạn:** vẫn chỉ là relationship, không command.

## DV3 — Client/account family trên biên nhận E22

- **A:** C03 — phần của handover receipt.
- **Lúc đó:** mã/nhóm khách hàng vô nghĩa.
- **B:** Huyền cho thấy cùng family xuất hiện trong phạm vi review hoặc Vũ xác minh đầu nhận thuộc cùng institutional chain.
- **Nghĩa mới:** job E22 là bridge thật giữa logistics và hospital.
- **Giới hạn:** không được dùng một mã bí mật thần kỳ; match phải là tên đơn vị/account/routing family hợp pháp có thể tồn tại trong cả hai hệ thống.

## DV4 — Timestamp Phúc trước Bắc

- **A:** C11A/C10 — police report và withdrawal đều trước D0.
- **Lúc đó:** timeline một người lạ.
- **B:** player bắt đầu nghi mình bị “chọn” hoặc sự cố xảy ra vì mình.
- **Nghĩa mới:** Bắc chỉ bước vào một crisis có sẵn.
- **Giá trị:** sửa mental model, không phải bằng chứng tội phạm mới.

## DV5 — Timestamp review Huyền

- **A:** C11 — review mở D−12.
- **Lúc đó:** chi tiết compliance.
- **B:** C17 cho thấy Hùng hạ job D−1 vì cleanup.
- **Nghĩa mới:** hospital pressure precedes logistics mistake; player có thể tự dựng causal chain Khoa/Khải → audit → Hùng → E22.

## DV6 — “Procedural Tuấn”

- **A:** C05/C21 — Tuấn khó chịu, nói/đòi đúng quy trình.
- **Lúc đó:** trông như cover-up behavior.
- **B:** C20 cho thấy authority của anh không đủ để hạ classification.
- **Nghĩa mới:** cùng hành vi từng làm anh đáng ngờ giờ trở thành bằng chứng character consistency.
- **Giá trị:** delayed exoneration, không phải “game nói player nghi sai”.

## DV7 — Sự tử tế thật của Nam

- **A:** C29 — Nam giúp việc nhỏ không liên quan plot.
- **Lúc đó:** characterization.
- **B:** D được chứng minh.
- **Nghĩa mới:** villain reveal không xóa scene đầu; nó làm scene đó khó chịu hơn vì Nam có thể tử tế cá nhân và vẫn xây hệ thống tàn nhẫn.
- **Giá trị:** thematic delayed-value; không count proof.

## DV8 — Cleanup nhìn như hành chính

- **A:** quyền truy cập bị thu hẹp, schedule thay đổi, review scope chỉnh.
- **Lúc đó:** corporate/hospital bureaucracy.
- **B:** C24–C26 cho thấy các thay đổi được kích hoạt bởi cùng risk layer.
- **Nghĩa mới:** những động tác “nhàm chán” chính là cách network tự bảo vệ, phù hợp triết lý Nam không thích ồn ào.

### Minimum signature requirement

Một run main path phải cho player gặp **ít nhất ba delayed-value seed trước khi biết chúng quan trọng**:

- C27 gần như guaranteed trong opening đời thường.
- C02 guaranteed qua job UI/assignment.
- C11A hoặc C11 guaranteed khi tuyến Phúc/hospital mở.

Các seed C28, C03, C21 là optional để thưởng người quan sát kỹ.

---

# 5. RED HERRING DESIGN

Red herring chỉ hợp lệ nếu mọi dữ kiện nền đều đúng.

## RH1 — Tuấn là người cố ý đưa gói cho Bắc

**Dữ kiện thật hỗ trợ:**

- Tuấn quản lý điều phối.
- Job đi qua bộ phận của anh.
- Anh biết nhóm đơn y tế ưu tiên.
- Anh né câu hỏi vì audit và trách nhiệm nghề nghiệp.
- Minh có thể báo hành vi Bắc cho phía Tuấn/Tân Lộ.

**Kết luận sai hợp lý:** Tuấn chọn Bắc hoặc cố tình tạo giao nhầm.

**Cách giải:** C20/C22 loại Tuấn khỏi người tạo E19. Đức chỉ xác nhận fields/interactions vận hành mình thấy; Vũ verify scope từ nguồn giao việc, records và lời Tuấn giới hạn. Correction không chứng minh universal negative rằng Tuấn chưa từng biết bất kỳ bí mật nào.

**Không vô dụng:** Tuấn vẫn là witness cho quy trình, assignment, người nào có quyền override và cách ngoại lệ được đẩy xuống bộ phận.

## RH2 — Hùng là ultimate boss

**Dữ kiện thật:**

- Founder/leader Tân Lộ.
- Biết core crime.
- Trực tiếp hạ luồng E19.
- Có quyền trên Tuấn/Đức/Yến.
- Có quan hệ cũ với Nam.
- Có động cơ che sai phạm.

**Kết luận sai:** Hùng đứng đầu cả network.

**Cách giải:** C24–C26 mở risk layer Khải; C31 dẫn tới identity/contact cần kiểm. C32H+C33_AUTH hoặc C32K+C34_AUTH có independent current authority, cộng verified C10_SOURCE_LINK thực hiện cùng directive, mới đưa full command cả ba nhánh lên Nam.

**Không vô dụng:** Hùng thật sự culpable và là nguồn C/D quan trọng; bắt Hùng ở partial route vẫn là hậu quả hợp lý.

## RH3 — Huyền là người che bệnh viện

**Dữ kiện thật:**

- Huyền giữ review.
- Từ chối chia một số dữ liệu.
- Review sau đó bị thu hẹp.
- Bà thuộc hệ thống compliance.

**Kết luận sai:** Huyền mở review để kiểm soát/xóa dấu.

**Cách giải:** creation timestamp + version history cho thấy Huyền mở rộng pattern trước khi Khoa can thiệp; tiêu chuẩn chia sẻ của bà nhất quán.

**Không vô dụng:** sự thận trọng của Huyền dạy player phân biệt “giữ dữ liệu đúng quy trình” với “che giấu”.

## RH4 — Minh là plant của Tân Lộ

**Dữ kiện thật:**

- Minh biết kênh tuyển.
- Chính Minh hướng Bắc tới Tân Lộ.
- Minh về sau leak câu hỏi Bắc.
- Minh nói giảm việc mình đã làm.

**Kết luận sai:** Minh được cài để chọn/giám sát Bắc.

**Cách giải:** C07 chứng minh lịch sử làm thêm bình thường; leak xảy ra sau khi Bắc chủ động hỏi; Tuấn/Hùng không biết Bắc trước assignment.

**Không vô dụng:** betrayal vẫn có hậu quả thật và là route lesson về trust.

## RH5 — Phúc là người dựng chuyện vì hối hận

**Dữ kiện thật:**

- Phúc ban đầu tự nguyện ở một mức nào đó.
- Anh kể thiếu một số chi tiết.
- Có tiền/cam kết.
- Một số chi tiết phụ không nhất quán vì xấu hổ/sợ.

**Kết luận sai:** pressure chỉ là cách Phúc thoát thỏa thuận.

**Cách giải:** C08 có nội dung paid-organ agreement, withdrawal rồi pressure; C10 authenticate đúng records/thứ tự, giữ từ E28. Initial consent/tiền C09 không phủ định việc rút sau đó.

**Không vô dụng:** buộc player phân biệt direct knowledge của Phúc với suy đoán của anh về hierarchy.

**Boundary:** không dùng framing nhục mạ nạn nhân hoặc twist “Phúc thật ra lừa đảo”.

## RH6 — “Cả bệnh viện” hoặc “mọi xe Tân Lộ” đều thuộc network

**Dữ kiện thật:** hospital và Tân Lộ đều có cell/manager liên quan.

**Kết luận sai:** institution = criminal organization.

**Cách giải:** C06/C16A + hành vi Tuấn/Huyền + hàng loạt hoạt động bình thường.

**Không vô dụng:** red herring này bảo vệ theme rằng tổ chức sống được nhờ bám vào các institution thật, không phải vì mọi người đều đồng phạm.

---

# 6. INNOCENT SUSPECT — TUẤN

Tuấn là innocent suspect chính vì chuỗi nghi ngờ của ông phải **được tạo bởi dữ kiện thật**, không phải camera/nhạc ép player nghi.

## 6.1. Chuỗi khiến Tuấn trông đáng ngờ

1. Bắc nhận job qua hệ thống do bộ phận Tuấn điều phối.
2. C02/C03 cho thấy job hơi lệch chuẩn nhưng vẫn chạy.
3. Khi Bắc hỏi, C05 cho thấy Tuấn phòng thủ và muốn chuyện được xử lý trong nội bộ.
4. Minh có quan hệ việc làm với phía Tuấn và có thể leak sang đó.
5. Tuấn thừa nhận có nhóm đơn y tế ưu tiên nhưng không giải thích rõ nguồn gốc.
6. Sau E23, job bị audit và Tuấn có lý do khóa/giảm access của worker.

Không bước nào là giả.

## 6.2. Correction có hai mức, theo đúng evidence

- C20/C22: classification đổi ở quyền Hùng trước assignment Tuấn; chỉ đặt TUAN_NOT_RECLASSIFIER.
- C21: procedural consistency giảm nghi, không tự chứng minh core innocence.
- C18: Đức chỉ kể lúc Tuấn nhận job, fields anh thấy và câu hỏi/câu trả lời vận hành mình trực tiếp chứng kiến; Đức không biết ai được secret briefing.
- Vũ intake nguồn giao việc, records fields/trao đổi và lời Tuấn trong cùng phạm vi. TUAN_CORE_SCOPE_VERIFIED nghĩa hồ sơ đang có đặt Tuấn ở lớp vận hành, không có basis quy ông vào purpose/command đã chứng minh ở Hùng; không là khẳng định universal negative về mọi điều Tuấn từng biết.
- Author truth Tuấn không biết crime vẫn giữ. Player được tiếp tục cân nhắc riêng; chỉ probe/delay/leak thật có cost, không cần bấm chấp nhận Tuấn vô tội để True.

## 6.3. Sau khi giải oan, Tuấn vẫn có trách nhiệm gì?

Tuấn không được biến thành “thiên thần”.

Anh:

- biết có ngoại lệ.
- từng làm ngơ vì nghĩ chỉ là sai phạm doanh nghiệp.
- bảo vệ công ty trước khi bảo vệ một worker mới.
- có thể nói giảm sự không minh bạch.

Vì vậy red herring tạo thêm chiều sâu chứ không bị reset thành vô dụng.

## 6.4. Hậu quả nếu player tin sai tới cuối

- Vũ không coi chức vụ của Tuấn là proof.
- Chỉ lựa chọn observable quay probe Tuấn/trì hoãn intake sau warning mới có authored time cost; private hypothesis hoặc đọc lại C20 không tự tốn source window.
- Đức/Huyền/Yến có thể bị khóa access trong lúc đó.
- Có thể rơi vào Delay/Missed Evidence hoặc Cleanup.
- Không có “Wrong Answer Game Over” ngay khi player nghi Tuấn.

---

# 7. BOSS FORESHADOWING — NAM

Mục tiêu: replay thấy rõ, first run không thể kết luận boss chỉ từ opening.

## 7.1. Foreshadow tier 1 — hoàn toàn đời thường

- C27: quá khứ kho vận + thiết bị/dịch vụ y tế.
- C29: kỹ năng sửa đồ thật, đời sống nhỏ, cư xử ổn định.
- Lan biết Nam lâu năm và không có lý do nghi.
- Nam không phô tiền/quyền lực.

**Chức năng:** tạo một biography hoàn chỉnh mà sau này có thể nối vào network, nhưng không “villain code”.

## 7.2. Foreshadow tier 2 — optional observation

- C28: đồ cũ/liên hệ nghề nghiệp với Tân Lộ.
- Một vài chi tiết nghề cũ cho thấy Nam hiểu cách doanh nghiệp/logistics vận hành hơn một người sửa đồ thuần túy.
- Không dùng logo treo ngay giữa phòng, ảnh Nam đứng giữa Hùng/Khoa, hay tài liệu nhạy cảm ở nhà trọ.

**Chức năng:** thưởng player quan sát, không count proof.

## 7.3. Foreshadow tier 3 — late relational evidence

- C30: old business relation Nam–Hùng được xác nhận độc lập.
- C31: crisis-time contact và identity lead, chưa phải authority.
- C32H/C32K: firsthand decision trong branch manager, khác decision/origin của D2.
- C33_AUTH hospital hoặc C34_AUTH logistics: Nam authorize thật và other-branch execution được verify.
- Generic C34 synchronized closures chỉ hỗ trợ timing, không D2.

**Chức năng:** chuyển “ông chú có background trùng hợp” thành proposition D.

## 7.4. Những thứ cấm để tránh villain cliché

Không dùng:

- nhạc đổi tone riêng mỗi khi Nam xuất hiện;
- ánh sáng/camera linger kiểu boss;
- Nam nói triết lý quá sớm;
- Nam biết chính xác Bắc đã thấy gì khi chưa có report;
- đồ vật có chữ “Hành Lang”;
- ảnh nhóm tất cả manager;
- một email “Boss Nam”;
- Nam vô cớ hỏi đúng chi tiết gói E22;
- Lan nói câu kiểu “ông ấy bí ẩn lắm”.

## 7.5. Replay payoff

Sau reveal, player có thể nhìn lại và thấy:

- Nam có background đúng hai thế giới logistics/y tế.
- Quan hệ Tân Lộ cũ đã ở đó.
- Ông sống ở nơi hoàn toàn bình thường vì đó thật sự là đời sống bình thường của ông.
- Ông không chọn Bắc; scene đầu không phải trap.
- Sự tử tế của Nam không phủ định trách nhiệm vì system do ông thiết kế.

Đó là “fair but invisible”, không phải “villain was obviously creepy”.

---

# 8. TRUE ENDING REQUIREMENT

True ending khó vì player phải hiểu **cấu trúc + nguồn + timing**.

Không được khóa true ending vào một pixel, một vật cực nhỏ hoặc một lựa chọn thoại duy nhất.

## 8.1. Requirement theo evidence slots

Player không cần đúng một bộ clue cố định. Họ cần lấp đủ các slot dưới đây bằng nguồn hợp lệ.

### SLOT A1 — Paid-organ agreement, withdrawal rồi pressure

- C08 phải có nội dung tiền đổi việc cung cấp nội tạng, cách gọi hiến tự nguyện, yêu cầu rút và phản hồi ép tiếp tục.
- C10 phải so exact message content với original broker counterpart thread ở E28 cho từng fact paid-organ agreement/withdrawal/pressure. Metadata chỉ exchange/order; hospital request chỉ visit. Không dùng hai phần này authenticate text, không count police chép lời Phúc là factual source mới.
- E28 hoàn tất intake/authentication trong baseline: CASE.A=2 trước player S09. A_PLAYER_SEEN/UNDERSTOOD riêng; miss encounter không mất police custody.

### SLOT B1 — Hospital knowing assistance

- C11 compliance discrepancy về tiền/withdrawal so consent.
- C12 có receipt Khoa nhận facts rồi vẫn giữ consent misleading/thu hẹp review, **hoặc** C15 Thảo firsthand biết facts và tham gia giữ hồ sơ có vẻ hợp lệ.
- No-Thảo và Thảo routes cùng nghĩa B. Pattern + bare scope change chưa đủ; Vũ match với A authenticated, không nâng Huyền thành người biết whole conspiracy.

### SLOT C1 — Logistics leadership biết purpose khi hỗ trợ

- C17 reclassification fact, hoặc reconstruction cùng fact có provenance.
- C22 approval trail có purpose trả tiền cho người hiến đã được Hùng nhận trước approve/hạ luồng, match cùng đầu việc với A/B.
- C18 operational snapshot **hoặc** C19 finance record độc lập xác nhận cùng nhóm handling/đợt thanh toán. Tuấn chỉ corroborate fields phần mình, không thay C22 knowledge.

Execution/settlement origin này xác nhận công việc thực tế; C17/C22 riêng chỉ ghi đổi luồng và approve. Equivalent phải giữ cùng fact/origin/authentication theo BACKSTAGE §0.1, không thêm một copy approval để lấp slot.

### SLOT X — Source-verified cross-cell relation

X chứng minh hospital và logistics cùng escalates crisis Phúc tới một đầu mối có vai trò quản trị rủi ro hiện tại, vượt quan hệ cùng giao dịch mà A/B/C đã có thể chứng minh. C24+C25/C26 phải có đúng Khải endpoint, scope request/response và crisis context; cùng consultant hợp pháp hoặc same group/account không đủ. C03 là transaction bridge lead; equivalent X phải reconstruct cùng risk-authority relation bằng nguồn có provenance. Vũ verify đầy đủ raw sources/context đã tiếp nhận kể cả khi private inference của Bắc sai; X_PLAYER_CONNECTED/N3_UNDERSTANDING vẫn riêng. ABC được preserve nhưng thiếu raw risk context là một state thật, không cần Vũ bỏ qua liên hệ giao dịch đã rõ.

**Source-branch verification cho full D:** C10_SOURCE_LINK là annex late S16 của case Phúc, không phải record hiện tại đã nằm ở E28. Lead là chính đầu mối môi giới trực tiếp phía counterpart Phúc đã chỉ trong E12/C08; Vũ đã thu original exchange A của đầu mối này ở E28. Custodian của annex là đầu mối đó, giữ original thread nhận từ Hạnh và reply mình gửi, không phải Phúc giữ liên lạc Hạnh–Khải. Sau E38 xảy ra thực tế trong run, tại S16 trong window 15:00–17:00 và trước E40 closure/cleanup lock, Vũ quay lại direct case intake để thu/giữ thread mới.

Acquisition dùng kênh riêng và động cơ tự phân định trách nhiệm của broker counterpart đã khóa tại BACKSTAGE §0.1. Timely contact còn mở có actual original intake; refusal/contact loss phải có causal event và pre-loss warning, không random roll hoặc tự grant annex. C10/A đã preserve không bị refusal late xóa ngược.

Payload annex phải cho đúng ba fact: (1) request Hạnh chuyển tới Khải nêu case Phúc và crisis đang xử lý, nằm trong phần forward chain broker thực sự đã nhận; (2) reply/forward Hạnh truyền quyết định Nam-authorized về ngừng case mới, giảm liên hệ và báo lại Phúc đã nói với ai, có case/scope khớp exact directive D2; (3) receipt của broker ghi đã nhận và áp dụng các giới hạn này trong nhánh nguồn. Vũ so original nội dung request/forward/receipt, endpoints gửi–nhận và scope case với original request/authorization/forward context C33_AUTH hoặc C34_AUTH đã authenticate tới Nam. Display name, lời Hạnh nói Nam duyệt, metadata hoặc broker tự kể lại đều chưa đủ. Nếu thiếu nguồn gốc forward chain hoặc không match đúng directive được Nam authorize, annex vẫn là lead, không full scope.

Annex chứng minh nhánh môi giới nhận/thực hiện cùng actual current directive D2; không cấp cho broker/Hạnh knowledge toàn mạng. Bản forward cùng order không được count thêm một independent D2. D1 vẫn phải là manager firsthand về một quyết định hiện tại khác; D2 là quyết định khác ở branch khác. Thiếu C10_SOURCE_LINK verified/preserved, pair chỉ support hai-branch hospital/logistics authority, chưa đủ BACKSTAGE §53.D **cả ba nhánh**, chưa nâng COMMAND=C3/C4. Police có thể verify/preserve annex dù Bắc chưa được xem toàn bộ, rồi chỉ chia kết luận/fields được phép; player không phải tự lấy thread từ Hạnh.

### SLOT D1 — Firsthand current manager authority

Chỉ hai sources trong family C32:

- C32H: Hùng trực tiếp nhận/quyết định phải đợi Nam approve trong logistics crisis D+1.
- C32K: Khoa trực tiếp nhận current authority Nam trong cell hospital, recovery nếu Hùng rút.

Manager nói branch mình; không một người tự chứng minh command cả mạng. Lead, trigger cooperation, window D+1 15:00–17:00 và direct police intake theo BACKSTAGE §0.1. Thảo không biết Nam nên không thay C32K.

### SLOT D2 — Authenticated current authority từ branch khác

- Khi D1=C32H, chỉ C33_AUTH hospital có original Nam authorize, identity/source/forward chain và execution được Vũ kiểm chứng.
- Khi D1=C32K, chỉ C34_AUTH logistics có original approval, scope và operational execution được Vũ kiểm chứng.

Accepted full D: **C32H+C33_AUTH** hoặc **C32K+C34_AUTH**, cùng **C10_SOURCE_LINK** verified/preserved với đúng actual D2 directive để scope cả ba nhánh. D1 và D2 phải nói hai quyết định current khác ở hai branches, có origin độc lập; manager đọc lại chính forwarded order D2 và một copy order đó không thành hai nguồn. Mất Hùng còn Khoa + actual logistics record; C33+generic C34 không cứu khi cả manager routes mất. C31 metadata là lead/auth context, không D2. C27/C28/C30 chỉ history, không D1/D2. Không đòi player inspect C30; Vũ có thể kiểm identity từ provenance đầu mối nghề nghiệp đã có.

**Authentication D2 cụ thể:** Khải trình yêu cầu trong kênh approve đã có; institution custodian giữ bản trao đổi gốc nhận reply authorize từ chính endpoint của Nam, rồi Khải chuyển scope triển khai và institution ghi receipt/execution. Vũ thu trực tiếp original receiver-side reply đó trong hồ sơ hospital/logistics, so exact nội dung quyết định với request/forward/execution và kiểm endpoint tác giả qua nguồn quan hệ/đầu mối nghề nghiệp đã verify. Không chấp nhận chỉ một screenshot/forward do Khải tự gõ mang tên Nam, không suy tác giả từ display name hoặc timestamps. Receipt/execution xác nhận lệnh đã áp vào branch; original reply có tác giả/source xác thực mới xác nhận Nam authorize. Operational custodian chỉ xác nhận record mình giữ, không tự suy Nam là boss hoặc biết crime. Đây là record ở branch khác về quyết định khác với firsthand decision D1, không copy order D1 rồi đếm thêm nguồn.

### SLOT T — Preservation timing

Trước cleanup lock:

- A+B+C phải có phần cốt lõi đã được Vũ tiếp nhận/preserve.
- D phải được corroborate trước khi các contact/access command trở nên quá khó bảo toàn trong game window.
- Player không được giữ toàn bộ evidence chỉ trong notebook/điện thoại.

## 8.2. Vì sao đây khó nhưng fair

- Clue quan trọng xuất hiện ở **nguồn có lý do tồn tại**, không trong ngăn bí mật vô lý.
- Mỗi proposition có tối thiểu hai đường corroboration.
- Early seed chủ yếu là automatically encountered hoặc nằm trong interaction lớn, không phải vật thể một pixel.
- Người chơi phải phân biệt **fact vs interpretation**.
- Người chơi phải hiểu **ai biết gì**.
- Người chơi phải nhận ra **cửa sổ đang đóng** từ hành vi/institution, không từ đồng hồ “True Ending 05:00”.
- Player có thể đạt true ending run đầu vì toàn bộ dữ kiện tồn tại trước threshold.
- Tỷ lệ đạt thấp đến từ việc chọn đúng nguồn, nhớ seed, tránh leak và chuyển evidence đúng lúc.

## 8.3. Những thứ không phải requirement

Không yêu cầu:

- tìm C28.
- nghi Nam từ phút đầu.
- lấy hết mọi clue optional.
- gặp trực tiếp Yến nếu police có nguồn C khác.
- thuyết phục mọi NPC.
- hack hệ thống.
- mở một file bí mật duy nhất.
- bắt player nhớ một code dài.
- combat/stealth khó.

---

# 9. CLUE DEPENDENCY GRAPH

## 9.1. Inciting bridge

Fact F1 — Hùng hạ gói nhạy cảm xuống luồng thường ở D−1  
├── C02 — assignment thường + client group y tế  
├── C03 — handover receipt đầu nhận  
├── C04 — dấu thay routing ngoài  
└── C17 — reclassification log  
      ↓  
Inference I1 — E22 không vốn là job thường  
      ↓  
C20 loại Tuấn khỏi quyền hạ classification  
      ↓  
C22 đặt quyết định ở Hùng  
      ↓  
Fact F2 — Bắc là accidental exposure do lỗi tự cứu của Hùng, không phải target

## 9.2. Proposition A

Fact F3 — paid-organ agreement; Phúc muốn rút rồi mới bị ép tiếp tục  
├── C08 — nội dung thỏa thuận tiền/nội tạng + withdrawal/pressure  
├── C09 — dấu đồng ý/tiền trước đó  
└── C10 — authenticate exact content bằng original counterpart thread; metadata chỉ exchange/order, hospital chỉ visit  
      ↓  
Inference I2 — đây không chỉ là “một giao dịch đổi ý”  
      ↓  
Proposition A — nội dung crime + withdrawal/pressure authenticated, police custody từ E28

## 9.3. Proposition B

Fact F4 — Huyền ghi discrepancy tiền/withdrawal so consent và pattern nhiều hồ sơ  
├── C11 — review pattern + timestamp  
├── C12 — notice Khoa nhận facts + consent vẫn misleading + version/scope history  
└── C13 — procedural boundary của Huyền  
      ↓  
Inference I3 — Huyền đang điều tra anomaly, không phải người tạo nó

Fact F5 — Khoa/Thảo biết phần nhạy cảm hơn  
├── C14 — Thảo framing shift  
├── C15 — Thảo firsthand knowledge + assistance cùng nghĩa C12  
└── C16 — Khoa intervention timing  
      ↓  
Inference I4 — C12 hoặc C15 có knowledge + assistance trong cell; C14/C16 riêng chỉ hỗ trợ suspicion/timing  
      ↓  
Proposition B — chỉ C11 + C12/C15 cùng fact đủ; framing và scope timing không thay notice/assistance

## 9.4. Proposition C

Fact F6 — Hùng đã biết paid-organ purpose khi approve/hạ luồng cùng nhóm handling  
├── C17 — reclassification  
├── C18 — Đức retained log  
├── C19 — Yến financial pattern  
└── C22 — Hùng nhận purpose + approve/override, không chỉ quyền account  
      ↓  
Inference I5 — không phải worker/dispatch accident  
      ↓  
Proposition C

## 9.5. Innocent suspect correction

C05 — Tuấn phòng thủ  
+ quyền điều phối công khai  
+ C35 — Minh báo về phía công ty  
      ↓  
False inference FI1 — Tuấn chọn Bắc / biết core crime

C20 — authority chain  
+ C21 — procedural consistency  
+ C22 — Hùng override  
      ↓  
Correction I6 — Tuấn không tạo E19; Vũ verify fields/nguồn giao việc/lời giới hạn để đặt anh ở scope vận hành trong case này. Không permission → universal negative; truth không biết core vẫn giữ

## 9.6. Three-box network

Proposition A  
+ Proposition B  
+ Proposition C  
+ sourced C26 hoặc reconstruction cùng current risk role/context (C03 chỉ lead), không same group là đủ  
      ↓  
Inference I7 — ba scandal là các cell của cùng một structure  
      ↓  
N3 understanding  
      ↓  
Vũ có thể mở điều tra cấu trúc nếu sources được preserve

## 9.7. Khải layer

C24 — Khoa→Khải after hospital review  
+ C25 — Hùng/Tân Lộ→Khải after logistics breach  
      ↓  
C26 — same cross-cell risk endpoint  
      ↓  
Inference I8 — Khải quản trị rủi ro trên nhiều branch  
      ↓  
False stopping point FI2 — Khải/Hùng có thể là apex  
      ↓  
C31 lead; accepted C32H+C33_AUTH hoặc C32K+C34_AUTH + verified C10_SOURCE_LINK needed for full three-branch layer

## 9.8. Nam / proposition D

C27/C28/C30 cho biography/old relation: chỉ hypothesis, không D. C31 current contact cho lead và context xác thực identity: vẫn chưa phải authority.

| D route | D1 firsthand current manager | D2 authenticated current other-branch record | Inference |
|---|---|---|---|
| Hùng | C32H logistics decision trực tiếp biết | C33_AUTH hospital original Nam authorize + execution | Nam có current cross-cell authority |
| Khoa recovery | C32K hospital decision trực tiếp biết | C34_AUTH logistics approval/execution | Cùng proposition và chuẩn independence |

D1 và D2 phải có current decisions/origins độc lập, không hai copies cùng forwarded order. C33+generic C34 hoặc C31+manager statement thiếu other-branch authenticated record không đủ. Vũ phải verify/preserve C10_SOURCE_LINK match cùng D2 directive để pair đủ cả ba nhánh; thiếu source link chỉ support hospital/logistics authority. Accepted pair và source context trước cleanup lock mới có COMMAND C4.

## 9.9. Ending gate

A + B + C preserved by Vũ  
      ↓  
Police threshold E38  
      ↓  
Accepted D1 + other-branch D2 và C10_SOURCE_LINK verified/preserved trước cleanup lock  
      ↓  
True route E39

A+B+C đủ nhưng D chưa preserve  
      ↓  
Cleanup/Partial E40

A/B/C thiếu source vì window đóng  
      ↓  
Delay/Missed Evidence E41

Knowledge leak trước preservation  
      ↓  
Source closures / faster cleanup  
      ↓  
Wrong Trust / Exposure / Cleanup E42

---

# 10. MISSABLE CONSEQUENCE TABLE

| Clue | Xuất hiện | Biến mất/khó lấy | Lý do | Hậu quả nếu miss | Ending bị ảnh hưởng |
|---|---|---|---|---|---|
| C03 handover receipt | D0 E22 | Sau bàn giao / cuối D0 bản vật lý không còn với Bắc | job hoàn tất, chứng từ đi theo hệ thống | mất một early bridge; vẫn recover qua C17/C11 nhưng tốn timing | True/Delay |
| C04 routing layer | D0 E22 | Khi gói được thu hồi | Bắc không sở hữu gói | mất delayed-value; không khóa main story | chủ yếu True understanding |
| C08/C10 A content/authentication | Police hoàn tất E28; player D+1 | player có thể miss encounter, không mất bản Vũ đã giữ | knowledge và custody riêng | A_PLAYER_SEEN thiếu; CASE.A=2 không lùi, bridge X vẫn cần | knowledge/route discovery, không A deletion |
| C11 Huyền review | D+1 09:30–11:30 | access thu hẹp trưa/chiều | Khoa thu hẹp quyền/scope | B khó đạt trong game window | True/Delay |
| C12 review version history | D+1 sáng | khó lấy sau scope lock | quyền truy cập bị siết | phải dựa C15 làm corroborator B | True nếu C15 cũng miss |
| C15 Thảo acknowledgment | D+1 sáng | Thảo tự đóng lại/hospital lock | self-protection + Khoa control | B vẫn possible qua C12 | True nếu C12 miss |
| C17 reclassification | D+1 sáng | access vận hành khóa dần | cleanup Tân Lộ | mất core C record; cần Đức/Yến + police reconstruction | True/Delay |
| C18 Đức retained snapshot | D+1 09:30–11:00 | khoảng trưa khi Đức mất access/bị kiểm soát | Khải thu hẹp leak | C yếu và mất operational scope corroboration; không mất một lời Đức chứng minh secret core briefing | True/Delay |
| C19 Yến finance | D+1 10:30–12:30 | khi Hùng khóa access | cleanup/self-protection | mất alternative corroborator C | True nếu Đức miss |
| C20 Tuấn authority chain | D+1 | records khó tiếp cận sau cleanup | Tân Lộ khóa quyền | player dễ giữ false theory Tuấn, tốn timing | Delay/Cleanup |
| C22 Hùng override | D+1 | khó hơn sau cleanup; police có thể vẫn reconstruct nếu đã có C17 | access + manager self-protection | C leadership khó chứng minh | True/Cleanup |
| C24 Khoa→Khải | D+1 | contact/context khó hơn sau crisis | communication cleanup | mất half connector Khải | True/Partial |
| C25 Hùng→Khải | D+1 | tương tự | risk logs/contact context bị dọn | mất half connector | True/Partial |
| C26 cross-cell connector | D+1 trưa | không phải vật; phụ thuộc có C24+C25 | nếu một half miss thì inference yếu | A+B+C vẫn possible nhưng layer trên khó mở nhanh | True/Cleanup |
| C28 old Tân Lộ item | D0 opening | có thể vẫn ở phòng Nam nhưng access không còn an toàn late game | không nên quay lại vô hạn khi threat tăng | chỉ mất foreshadow, không khóa ending | none trực tiếp |
| C31 Khải→Nam crisis metadata | late D+1 | sau cleanup contact context/correlation khó preserve | các manager cắt liên hệ | mất lead/auth context; metadata chưa bao giờ tự là D2 | True/Cleanup |
| C32H/C32K manager D1 | D+1 15:00–17:00 | willingness/contact có thể đóng nếu chưa intake | actor tự bảo vệ trước lock | mất Hùng: recovery Khoa+C34_AUTH; cả hai manager mất: thiếu D1 dù C33/C34 còn | True/Cleanup |
| C33_AUTH hospital D2 | Cùng command window | quyền/context bản chưa preserve có thể siết | hospital closure có owner/quyền thật | Hùng route thiếu D2; còn Khoa route chỉ nếu C32K+C34_AUTH đủ | True/Cleanup |
| C34_AUTH logistics D2 | Cùng command window | chưa thu original trước operational closure | Tân Lộ thu quyền/context | Khoa recovery thiếu D2; generic synchronized closure không thay | True/Cleanup |
| C10_SOURCE_LINK full-D source context | Late S16 sau actual E38, trước E40 lock | source broker contact/forward context đóng trước police intake | manager co nhánh/cắt liên hệ; record đã preserve không mất | D pair chỉ còn two-branch authority, chưa full scope §53.D | True/Cleanup |
| C35 Minh leak | D0 tối/D+1 | message có thể bị xóa | người dùng tự xóa | player khó biết vì sao source đóng; có thể lặp sai trust | Wrong Trust/Exposure |
| C42 police preservation | D+1 chiều | threshold time-based | cleanup đi trước | player có thể biết đúng nhưng proof chain không được giữ | True vs Cleanup |
| C43 access closure | D+1 | event xảy ra một lần | time tiến | không phải clue cần nhặt; là consequence signal | tất cả late endings |

**Fairness rule cho missable evidence:** clue biến mất vì một actor/hệ thống có lý do làm nó mất access, không vì game arbitrarily despawn. Institutional traces không “xóa sạch”; cái mất chủ yếu là **quyền truy cập, context hoặc thời gian để biến trace thành evidence trong run hiện tại**.

---

# 11. NOTEBOOK ARCHITECTURE

Notebook phải hỗ trợ memory nhưng không suy luận thay.

## 11.1. People

Ví dụ entry cho Nam chỉ được phép lưu facts đã biết:

- Vũ Đức Nam, khoảng 61.
- Sống/thường xuyên ở dãy trọ.
- Từng làm kho vận/thiết bị hoặc dịch vụ liên quan y tế.
- Biết Hùng/Tân Lộ nếu player đã xác minh.
- Khải liên hệ Nam ở mốc X nếu source đã được thấy.

Không được tự thêm:

- “Boss.”
- “Có thể điều khiển bệnh viện.”
- “Đứng sau vụ Phúc.”

## 11.2. Events

Các event nên có timestamp rõ:

- E22 assignment.
- Phúc withdrawal/pressure chronology.
- Huyền review creation.
- E19 reclassification.
- E23 breach audit.
- Source access closures.
- Police preservation.

Player có thể tự nhận ra “review có trước job” bằng cách so dates.

## 11.3. Evidence

Mỗi evidence entry có:

- source;
- timestamp;
- institution;
- trạng thái: observed / copy exists / source still accessible / handed to police.

Không có:

- evidence score;
- percentage truth;
- màu xanh/đỏ cho suspect;
- auto-link graph.

## 11.4. Media

Ảnh/receipt/log screenshot có thể được lưu nếu player thực sự có quyền/khả năng nhìn thấy lúc đó.

Không cho điện thoại tự chụp mọi thứ.

---

# 12. ENVIRONMENTAL NOISE

Mystery sẽ bị lộ nếu mọi thứ có inspect prompt đều hữu ích.

Các lớp noise cần tồn tại có chủ đích:

- job Tân Lộ hoàn toàn bình thường;
- bệnh viện có lỗi giấy tờ thật nhưng không liên quan Hành Lang;
- sinh viên khác từng nhận việc part-time không gặp gì lạ;
- xe/nhãn y tế xuất hiện hợp pháp;
- Lan kể chuyện khu trọ không liên quan;
- đồ sửa điện của Nam không mang ý nghĩa plot;
- thông báo trường, deadline, tiền phòng, ăn uống;
- complaint vận hành ở Tân Lộ không liên quan E22.

**Rule:** noise không được thiết kế như punishment. Nó phải nhanh, có đời sống và không đòi player đọc hàng trang để biết “đây là rác”.

---

# 13. FAIRNESS AUDIT — PASS 1

## R1 — E22 misclassification

- **Đủ dữ kiện trước reveal?** Có: C02/C03/C04 trước C17.
- **Clue chỉ tác giả hiểu?** Không; reclassification là record vận hành bình thường.
- **Quá lộ?** Không; client group y tế tự nó vô hại.
- **Trùng chức năng?** C03/C04 cùng seed nhưng một cái bridge, một cái physical anomaly; không bắt buộc cả hai.
- **False clue có nói dối?** Không.
- **Run đầu suy được?** Có.

**PASS.**

## R2 — Phúc coercion

- Có C08 core-agreement/withdrawal/pressure content và C10 authentication có origin ngoài lời kể; không chỉ thêm custodian cho cùng claim.
- C09 cố ý làm source không hoàn hảo nhưng không phủ định core fact.
- Không dùng “nạn nhân nói gì cũng đúng”; Vũ tách fact/suy đoán.

**PASS.**

## R3 — Hospital cell

**Vấn đề phát hiện:** nếu C15 Thảo nói quá nhiều, bà biến thành exposition machine.

**Sửa áp dụng:** C15 chỉ xác nhận knowledge về tiền/withdrawal và phần consent mình tham gia; C12 phải chứa receipt Khoa nhận cùng facts + assistance trail nếu no-Thảo. Huyền giữ discrepancy, không tự biết conspiracy; Thảo không biết Nam/Tân Lộ/source people toàn bộ.

**PASS sau sửa.**

## R4 — Tân Lộ leadership

**Vấn đề:** override không có purpose có thể chỉ là corporate misconduct.

**Sửa:** C17 giữ nguyên operational fact không nói crime; C22 thêm thông tin paid-donor purpose Hùng đã nhận trước approve, giới hạn trong đúng nhóm handling. C18/C19 independently corroborate cùng đầu việc; A/B authenticated tạo context crime. Không file nào chứa toàn mạng hoặc tự complete mọi proposition.

**PASS.**

## R5 — Tuấn innocent suspect

- Suspicion dựa trên quyền truy cập, defensive behavior và omission thật.
- Permission/timing chỉ sửa origin E19; Vũ verify scope qua source giao việc/records/lời giới hạn. Đức không biết ai được core briefing; assessment case này không là universal negative và không hidden innocence quiz.
- Tuấn vẫn có vùng xám trách nhiệm.

**PASS.**

## R6 — Minh betrayal

**Vấn đề:** nếu leak luôn xảy ra, game ép betrayal dù player không chia gì.

**Sửa:** C35 chỉ tồn tại nếu player trigger E26 bằng việc hỏi/chia đủ thông tin. Nếu không, Minh vẫn là bạn học bình thường.

**PASS.**

## R7 — A+B+C network

**Vấn đề:** C26 same endpoint Khải có thể thành “magic connector”.

**Sửa:** C26 chỉ chứng minh một người quản trị risk nối hai institution; để nói cùng organ network vẫn cần A/B/C facts độc lập. Khải không có file tổng hợp toàn mạng.

**PASS.**

## R8 — Manager layer

- Hùng/Khoa/Hạnh mỗi người có motive/knowledge khác nhau.
- Không ai tự exposition người khác.
- Dừng ở Hùng vẫn tạo một partial ending hợp lý.

**PASS.**

## R9 — Nam boss

**Vấn đề lớn nhất:** C27+C28 nếu quá prominent sẽ khiến player đoán Nam chỉ vì game vừa giới thiệu ông rồi cho thấy logistics+y tế.

**Sửa áp dụng:**

1. C27 được trình bày như biography tự nhiên giữa nhiều chi tiết đời thường.
2. C28 là optional và không được đặt camera/lighting đặc biệt.
3. C27/C28/C30 không count D proof.
4. Full D chỉ mở bằng accepted independent current pairs **C32H+C33_AUTH** hoặc **C32K+C34_AUTH**, cùng C10_SOURCE_LINK verified/preserved ở late S16 cho source branch; C31 metadata/generic C34 là leads.
5. Nam không có villain behavior ở opening.

**PASS sau sửa.**

## R10 — Preservation

**Vấn đề:** true ending có thể thành “đưa hết item cho Vũ” checklist.

**Sửa:**

- Vũ chỉ cần source đủ mạnh theo slots, không cần mọi clue.
- Player phải chọn đúng thời điểm và hiểu source nào đáng chuyển.
- Police có thể tự verify phần còn lại khi được cung cấp đúng bridge.
- Notebook không hiện completeness bar.

**PASS.**

---

# 14. FAIRNESS AUDIT — CLUE LOAD / REDUNDANCY

## 14.1. Có quá nhiều clue cùng chức năng không?

Các cụm được giữ có chủ đích:

- A có Phúc direct + police.
- B có Huyền + version history/Thảo.
- C có reclassification + Đức/Yến + Hùng.
- D có firsthand current manager + authenticated current other-branch record; current contact chỉ lead.

Mỗi proposition có redundancy vì mystery công bằng cần nhiều source, nhưng **mỗi source có chức năng khác nhau**:

- direct witness;
- institutional record;
- insider context;
- timing/command.

Không có ba clue chỉ nói cùng một câu bằng ba skin khác nhau.

## 14.2. Có clue nào tác giả mới hiểu?

Cấm sử dụng một code vô nghĩa mà không có in-world explanation.

Nếu receipt/account family được dùng làm match, game phải cho player thấy cùng tên/nhóm/account ở hai nguồn theo cách con người đọc được.

## 14.3. Có clue nào quá lộ?

- C27/C28 không proof.
- C31 metadata không mang D1/D2, kể cả khi đi cùng generic closure timestamps.
- C32 không đứng một mình.
- C17 không nói “organ”.
- C11 không nói “crime”.

Không clue sớm nào chứa tên Nam bên cạnh từ khóa tội phạm.

## 14.4. False clue có cheat không?

Không.

- Tuấn thực sự phòng thủ.
- Hùng thực sự culpable.
- Huyền thực sự giữ dữ liệu.
- Minh thực sự leak nếu trigger.
- Phúc thực sự từng đồng ý một phần.

Sai nằm ở **interpretation của player**, không ở fact game cung cấp.

---

# 15. FAIRNESS AUDIT — TRUE ENDING RUN 1

## 15.1. Có thể suy ra thật sự ngay run đầu không?

**Có.**

Trước threshold E39, một player cực kỳ tinh ý có thể có:

- A: C08+C10.
- B: C11+(C12 hoặc C15) có đủ knowledge + assistance payload.
- C: C17+C22 có purpose đã biết+(C18 hoặc C19) match độc lập.
- Cross-cell: C26 hoặc equivalent reconstruction cùng current risk role/context; C03/same group chỉ là lead.
- D: C32H+C33_AUTH hoặc C32K+C34_AUTH, đúng distinct current decisions/identity/origin; C10_SOURCE_LINK verified/preserved match same actual D2 directive để scope cả ba nhánh.
- Timing: C42 trước cleanup.

Không clue nào đòi knowledge từ replay.

## 15.2. Vì sao đa số player vẫn không đạt?

Không phải vì thiếu một pixel.

Họ có thể:

- tin Tuấn quá lâu.
- dừng ở Hùng như boss.
- coi Huyền là người che.
- bỏ qua thứ tự thời gian.
- không nhận ra C27/C30 chỉ là relationship, rồi accuse Nam quá sớm.
- chia giả thuyết cho Minh trước preservation.
- giữ evidence cho riêng Bắc thay vì đưa source đủ mạnh cho Vũ.
- đến Đức/Huyền sau khi access đóng.
- có A+B+C nhưng không đủ D.

Đây là failure do reasoning/trust/timing.

## 15.3. Anti-save-scum design note

Save system vẫn phải tôn trọng canon.

Không nên làm một lựa chọn sai lập tức bật “Bad choice” khiến player reload 15 giây.

Hậu quả nên nở muộn:

- access đóng;
- source đổi thái độ;
- cleanup đi trước;
- Vũ chỉ preserve được một phần;
- Nam/Khải có thêm knowledge.

---

# 16. FINAL CLUE ROUTES

## Minimum main-story route

1. E22 anomaly: C02 hoặc C03.
2. Một source A: Phúc/Vũ.
3. Một source B hoặc C đủ để nhận ra chuyện lớn hơn job.
4. Vũ xác minh bridge.
5. Player tiến tới partial ending ngay cả khi thiếu D.

Mục tiêu: game không kẹt vì một clue miss.

## Strong investigation route

1. C02/C03.
2. C08 content + C10 authentication đã trong police custody; player tiếp cận đúng phần.
3. C11 + C12/C15 đủ knowledge/assistance.
4. C17+C22 có purpose + C18/C19 match độc lập.
5. C20 để tránh Tuấn trap.
6. C24+C25/C26.
7. Vũ ghi A custody đã có E28, tiếp nhận B/C và sourced X còn thiếu sớm; không Bắc giao lại A.

Mục tiêu: mở late command investigation.

## True route

Strong route  
+ tránh/giới hạn C35 leak trước preservation  
+ C31 lead/auth context nếu được thấy  
+ accepted pair C32H+C33_AUTH hoặc C32K+C34_AUTH độc lập current decisions, cùng verified/preserved C10_SOURCE_LINK đủ three-branch scope  
+ C42 preservation đúng timing  
= E39.

Không yêu cầu C28.

Không yêu cầu tìm mọi clue optional.

Không yêu cầu player “chọn Nam” trong một màn accusation quiz.

---

# 17. PRODUCTION RULES CHO STAGE 5+

Khi chia scene/chapter sau này:

1. Mỗi scene clue phải trỏ về một ID trong file này hoặc tạo ID mới mà không retcon objective truth.
2. Nếu một clue mới chứng minh proposition A/B/C/D, phải ghi rõ source độc lập của nó.
3. Không thêm clue chỉ để giải thích một plot hole của scene.
4. Không cho NPC truyền knowledge vượt Character Web.
5. Không để Nam biết clue Bắc thu được nếu chưa có observable consequence.
6. Không biến UI highlight thành đáp án.
7. Red herring phải có resolution trên cùng fact set.
8. Delayed-value seed phải tồn tại trước payoff đủ lâu để player có cảm giác “mình đã thấy cái này”.
9. Nếu một critical clue bị missable vĩnh viễn, phải có:
   - telegraph tự nhiên;
   - ít nhất một route alternate cho main story;
   - hậu quả logic;
   - không phải vật một pixel.
10. True ending phải được test bằng một playthrough blind giả lập: tester không được biết hierarchy và vẫn phải có thể giải từ evidence.
11. Replay test phải cho cảm giác Nam “đã ở trước mắt” nhưng không được tạo cảm giác game gian lận vì camera/nhạc giấu quá lộ.
12. Police reaction test: khi Vũ có A+B+C, anh phải chủ động; khi D đủ, police phải chuyển sang hành động phần lõi.
13. Institution test: không scene nào được làm toàn Tân Lộ/Minh Trạch trông như cult/băng đảng.
14. Tuấn test: player có thể nghi anh, nhưng một player cẩn thận phải giải oan được trước final route.
15. Minh test: betrayal chỉ xảy ra nếu player tạo thông tin để leak; Minh không được “biết bí mật” vô cớ.
16. Evidence lifecycle test: mỗi vật/log phải trả lời được ai tạo, ai sở hữu, ai có thể mất access và vì sao.

---

# 18. FINAL CONSISTENCY CHECK

Stage 4 này không thay đổi canon Stage 1–3.

Nó chỉ biến objective truth thành player-facing inference chain:

**Bắc thấy một job bình thường có chi tiết lệch  
→ nhận ra job từng thuộc luồng khác  
→ đọc paid-organ agreement, withdrawal/pressure của Phúc được authenticate trước Bắc xem  
→ thấy hospital đã biết tiền/withdrawal mà vẫn hỗ trợ vẻ consent hợp lệ  
→ thấy Hùng đã biết paid-donor purpose mà vẫn approve/hạ luồng  
→ nhận ra hai institution có cùng risk connector  
→ loại dần các suspect hợp lý nhưng sai tầng  
→ hiểu nhiều manager đang tự che lỗi chứ không có một “villain file”  
→ nhìn lại các chi tiết đời thường của Nam với nghĩa mới  
→ intake manager firsthand và authenticated decision khác ở branch khác, verify source-branch execution cùng directive để đủ command cả ba nhánh  
→ đưa evidence ra khỏi tay Bắc trước khi cleanup khóa các cửa  
→ True Ending.**

Difficulty nằm ở:

- quan sát;
- nhớ;
- timing;
- trust;
- phân biệt source với theory;
- phân biệt “quen nhau” với “có quyền command”;
- không dừng ở suspect đầu tiên hợp lý.

Không nằm ở:

- pixel hunt;
- code vô nghĩa;
- camera giấu;
- police incompetence;
- villain confession;
- một USB;
- combat.

**END — CLUE ARCHITECTURE / CLUE GRAPH / STAGE 4**
