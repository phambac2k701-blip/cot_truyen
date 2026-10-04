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
| C08 | A, C, H, J | Contact/tin nhắn do Phúc giữ cho thấy anh yêu cầu dừng/rút trước khi bị gây sức ép | D0 tối hoặc D+1 qua Vũ/Phúc | Một tranh chấp có tiền | Core proof rằng withdrawal có trước pressure | Auto khi nguồn hợp lệ |
| C09 | B, H, J | Dấu vết Phúc đã từng đồng ý/nhận một phần tiền hoặc bước vào quy trình | Cùng route Phúc | Làm lời kể Phúc kém “sạch” hơn | Giải thích omission/xấu hổ; tăng fairness, tránh viết nạn nhân hoàn hảo | Auto |
| C10 | A, C, H, J | Police chronology tách: đồng ý → muốn rút → áp lực → kiểm tra bệnh viện → trình báo | D+1 qua Vũ | Timeline vụ Phúc | Chứng minh A bằng nguồn độc lập đã được police ghi trước Bắc | Auto |
| C11A | B, D, J | Timestamp Phúc trình báo nằm trước E22 nhiều ngày | D+1 | Chi tiết thời gian | Recontextualize toàn opening: conspiracy/crisis có trước Bắc | Auto |

## 2.3. Proposition B — Minh Trạch

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C11 | A, C, H, J | Huyền mở review nhiều hồ sơ có pattern hành chính lặp lại; timestamp D−12 | D+1 sáng, E33 | Có vấn đề compliance | Nguồn độc lập mạnh cho B; đồng thời chứng minh crisis có trước Bắc | Auto nếu được tiếp cận hợp lệ |
| C12 | B, C, H, J | Version/scope history cho thấy review từng rộng hơn rồi bị thu hẹp sau khi đi qua vùng quản lý Khoa | D+1 | Có can thiệp quản trị | Corroborate rằng vấn đề không chỉ là lỗi ngẫu nhiên | Nếu inspect/được chia |
| C13 | E, G | Huyền từ chối cung cấp một số dữ liệu khi Bắc chưa có quyền/lý do hợp lệ | D+1 | Có thể trông như che giấu | Về sau player thấy tiêu chuẩn của Huyền nhất quán và chính bà mở review | Có dưới dạng interaction note |
| C14 | B, G | Thảo dùng cách framing thay đổi khi câu hỏi chuyển từ giấy tờ sang hoàn cảnh người tham gia | D+1 | Bà có thể chỉ là bác sĩ phòng thủ | Cho thấy knowledge lớn hơn người chỉ xử lý hồ sơ | Nếu interaction |
| C15 | C, G | Nếu trust/pressure đúng, Thảo xác nhận một số hồ sơ không phản ánh đầy đủ hoàn cảnh/thỏa thuận bên ngoài | D+1, cửa sổ E33 | Insider admission giới hạn | Nguồn thứ hai cho B, không chứng minh A/C/D | Auto khi thu được |
| C16 | B, H, J | Timing Khoa can thiệp scope xảy ra sau review Huyền và trước/đúng lúc báo lên Khải | D+1 | Administrative intervention | Dẫn từ hospital anomaly tới management risk layer | Nếu nguồn hợp lệ |
| C16A | F | Nhiều lỗi hồ sơ nhỏ khác ở bệnh viện không liên quan network | D+1 | Background realism | Ngăn player coi mọi anomaly là clue | Không |

## 2.4. Proposition C — Tân Lộ leadership

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C17 | A, C, H, J | Reclassification log cho thấy job E22 từng ở luồng hạn chế rồi được chuyển xuống pool thường D−1 | D+1 sáng | Chứng minh job không “tự nhiên” là thường | Core C bridge; đúng objective E19 | Auto nếu mở được source |
| C18 | C, H, J | Phần log/snapshot Đức giữ cho thấy các ngoại lệ y tế lặp lại và một số thay đổi diễn ra khi audit bắt đầu | D+1 E32 | Insider self-insurance | Corroboration rằng đây là pattern leadership-level, không phải lỗi dispatch đơn | Auto khi nhận |
| C19 | B, C, H | Pattern tài chính Yến thấy: một nhóm khách hàng y tế có luồng giá trị/đối soát bất thường so với dịch vụ tương ứng | D+1 E35 hoặc police verify | Có gian lận tài chính | Corroborate C nhưng không nói organ network là gì | Auto nếu được verify |
| C20 | B, E, H, J | Permission/approval chain cho thấy Tuấn duyệt vận hành sau classification; anh không phải account đã hạ mức job | D+1 | Giảm nghi Tuấn | Exoneration logic của innocent suspect | Auto |
| C21 | B, G, H | Một record đời thường cho thấy Tuấn từng phản đối job thiếu chứng từ/đòi checklist ở vụ không liên quan | D0/D+1 | Chi tiết nghề nghiệp | Sau C20, củng cố rằng procedural defensiveness của anh là thật | Optional |
| C22 | A, C, H, J | Override/reclassification truy lên quyền quản lý của Hùng hoặc quyết định do Hùng xác nhận | D+1 | Hùng có trách nhiệm trực tiếp | Chứng minh leadership complicity của Tân Lộ; không chứng minh Hùng là apex | Auto |
| C23 | B, H, J | Audit request từ Khải tới Tân Lộ bắt đầu D−7, trước job E22 | D+1 | Công ty đang bị rà trước Bắc | Cắt giả thuyết “Bắc làm mọi thứ bắt đầu” và dẫn tới risk layer | Optional/auto nếu source |

## 2.5. Cross-cell connector / Khải

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C24 | C, H, J | Sau khi Huyền mở review, Khoa có contact quản trị tới Khải; nội dung đầy đủ không cần lộ | D+1 | Hospital manager báo ai đó bên ngoài | Một nửa của connector Khải | Auto nếu police/hospital source |
| C25 | C, H, J | Sau breach E22, Hùng/Tân Lộ cũng escalates tới cùng Khải | D+1 | Logistics có cùng risk contact | Nửa còn lại; cùng C24 chứng minh Khải nối nhiều cell | Auto |
| C26 | C, D, H, J | C24 + C25 có cùng endpoint và đúng các mốc crisis; endpoint không phải vendor công khai chung | D+1 trưa | Một người quản trị risk chung | Cho player inference “đây không phải hai scandal riêng” | Notebook giữ hai entry, không tự nối |
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
| C31 | C, D, H, J | Trong crisis hiện tại, contact metadata cho thấy Khải báo/trao đổi với Nam ngay sau các mốc cross-cell quan trọng, đặc biệt sau E37 | Late D+1 | Nam đang được risk manager cập nhật | Một nguồn độc lập mạnh cho D; cần corroboration | Auto nếu police/source |
| C32 | C, G/H | Hùng hoặc một manager-level source xác nhận quyết định pause/cleanup toàn nhánh phải được Nam approve/định hướng; statement chỉ về quyền command mình trực tiếp biết | Late D+1 | Nam không chỉ là bạn cũ | Core command source D; không đủ đứng một mình | Auto khi police receives |
| C33 | C, H, J | Một route thay thế: record từ phía hospital/manager cho thấy sau báo cáo qua Khải, instruction thay đổi scope/hoạt động trùng với decision window của Nam | Late D+1 | Policy change đồng bộ | Independent corroboration cho D nếu C32 yếu/không có | Auto |
| C34 | C, D, H, J | Pattern nhiều branch cùng đổi trạng thái sau cùng một crisis chain: hospital thu hẹp, Tân Lộ khóa access, môi giới pause; timing hội tụ về Khải→Nam | Late D+1 | Có central command | Corroboration hệ thống; không dùng một mình để buộc tội Nam | Notebook giữ timestamps |

## 2.8. Timing / preservation

| ID | Loại | Dữ kiện | Xuất hiện | Ý nghĩa tức thời | Giá trị về sau | Notebook |
|---|---|---|---|---|---|---|
| C42 | A, C, H, J | Vũ/police tạo record tiếp nhận và bảo toàn nguồn A/B/C trước cleanup | D+1 chiều | “Đã giao cảnh sát” | Khóa các source khỏi quyền xóa của network; true-ending timing gate | Auto |
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

## R2 — Vụ Phúc là một sự kiện thật, có trước Bắc và chứa coercion sau withdrawal

1. **Player cần hiểu:** Phúc không tạo chuyện sau khi Bắc xuất hiện; crisis đã chạy từ trước và pressure xảy ra sau khi Phúc muốn rút.
2. **Clue:** C08, C09, C10, C11A.
3. **Xuất hiện:** dấu đầu tiên D0 tối hoặc D+1; police chronology D+1.
4. **Hiểu:** có thể player ban đầu chỉ thấy “tranh chấp tiền”; thứ tự thời gian mới tạo nghĩa pháp lý/narrative.
5. **Sai hợp lý:** Phúc đổi ý sau một giao dịch xấu; đang đổ lỗi để thoát trách nhiệm; người môi giới trực tiếp là toàn bộ vụ án.
6. **Xác nhận:** police record E12/E28 và contact record Phúc giữ độc lập.
7. **Nếu miss:** A yếu; Vũ vẫn điều tra nhưng player không đủ bridge sang network trong game window.
8. **Notebook:** ghi tách “Phúc trực tiếp biết” và “Phúc suy đoán”.
9. **Mandatory:** Có, ít nhất phần core withdrawal→pressure.
10. **True ending:** Có. A phải được preserve trước khi dùng nó nối B/C.

## R3 — Minh Trạch không có một lỗi đơn; có pattern và có người quản lý đang thu hẹp nó

1. **Player cần hiểu:** Huyền phát hiện pattern thật; Khoa can thiệp scope; bệnh viện không phải toàn bộ đồng phạm.
2. **Clue:** C11, C12, C13, C14, C15, C16.
3. **Xuất hiện:** D+1 hospital window.
4. **Hiểu:** C13 có thể làm Huyền đáng ngờ trước; C11/C12/C15 tách người mở review khỏi người thu hẹp.
5. **Sai hợp lý:** Huyền là người che hồ sơ; lỗi hành chính lớn nhưng không criminal; cả bệnh viện cùng dính.
6. **Xác nhận:** version history C12 + Thảo C15 là hai nguồn khác chức năng.
7. **Nếu miss:** B không đủ; route có thể kết thúc ở A hoặc A+C với nghi ngờ chưa chứng minh hospital cell.
8. **Notebook:** lưu review timestamp, scope changes, lời nguồn; không gắn “complicit”.
9. **Mandatory:** Bản thân pattern cần cho main escalation; Thảo/version history có thể optional theo route.
10. **True ending:** Có. B cần Huyền + ít nhất một corroborator (C12 hoặc C15).

## R4 — Tân Lộ leadership có chủ ý tham gia; đây không chỉ là vendor bị lợi dụng

1. **Player cần hiểu:** ít nhất Hùng biết có hoạt động phi pháp và dùng quyền của mình để hỗ trợ/che giấu; đa số nhân viên vẫn vô tội.
2. **Clue:** C17, C18, C19, C22, C23.
3. **Xuất hiện:** anomaly từ D0; chứng minh D+1.
4. **Hiểu:** reclassification có thể ban đầu chỉ là corporate misconduct; corroboration Đức/Yến nâng nó thành pattern.
5. **Sai hợp lý:** một nhân viên dispatch làm sai; Tuấn là người cầm đầu; Tân Lộ chỉ là công ty gian lận nhưng không liên quan hospital.
6. **Xác nhận:** C18 hoặc C19 độc lập với C22.
7. **Nếu miss:** C không đủ; police không có bridge logistics mạnh.
8. **Notebook:** log raw records và nguồn Đức/Yến; không ghi “Tân Lộ là front”.
9. **Mandatory:** C ở mức tối thiểu cần cho late main story; không phải mọi corroborator đều mandatory.
10. **True ending:** Có. C cần ít nhất một record leadership + một nguồn độc lập.

## R5 — Tuấn là innocent suspect: đáng ngờ vì thật sự che sai phạm nghề nghiệp, nhưng không biết organ network

1. **Player cần hiểu:** “có quyền truy cập và nói tránh” không đồng nghĩa “biết mục đích thật”.
2. **Clue:** suspicion từ C05 + vị trí điều phối + C35; correction từ C20, C21, C22 và giới hạn knowledge do Đức xác nhận.
3. **Xuất hiện:** D0 ngay sau incident; giải oan D+1 trước final command reveal.
4. **Hiểu:** player có đủ lý do nghi thật; game không bảo player “đừng nghi”.
5. **Sai hợp lý:** Tuấn cố tình chọn Bắc/giao gói; Tuấn là liaison hospital.
6. **Xác nhận:** timestamp authority C20 cho thấy classification bị đổi trước phần approval của Tuấn; C22 đưa quyền lên Hùng.
7. **Nếu miss exoneration:** player có thể đưa giả thuyết sai cho Vũ, mất thời gian và một source window; không game-over ngay.
8. **Notebook:** ghi các hành động và permission, không có nhãn suspect.
9. **Mandatory:** Không bắt buộc để finish bad route; cần hiểu đúng nếu muốn route tốt.
10. **True ending:** Gián tiếp có. Quy kết sai Tuấn có thể làm miss C/D timing.

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

1. **Player cần hiểu:** Phúc, Minh Trạch và Tân Lộ không phải ba scandal song song.
2. **Clue:** A: C08/C10. B: C11/C15. C: C17/C18. Bridge: C03 và C26.
3. **Xuất hiện:** seed từ D0, đủ dữ kiện khoảng D+1 trưa.
4. **Hiểu:** không clue nào tự nói “network”; player phải nối source độc lập.
5. **Sai hợp lý:** Phúc gặp môi giới nhỏ; hospital có compliance issue riêng; Tân Lộ có corporate fraud riêng.
6. **Xác nhận:** same crisis connector Khải C24–C26 và các chronology độc lập.
7. **Nếu miss:** N3 không đạt; police vẫn xử lý từng hộp nhưng không mở rộng đủ trong game window.
8. **Notebook:** lưu ba timeline riêng, không auto draw arrow.
9. **Mandatory:** Đây là core inference của main mystery.
10. **True ending:** Có. A+B+C phải được police-preserved, không chỉ nằm trong notebook.

## R8 — Hùng/Khoa/Hạnh đều có tội và đều che lỗi riêng, nhưng không ai trong họ giải thích toàn bộ mạng

1. **Player cần hiểu:** structure không phải “một manager xấu”; các manager có động cơ khác nhau và information limits thật.
2. **Clue:** Hùng C22/C23; Khoa C12/C16/C24; Hạnh từ C08/C10 và source môi giới; Đức C38-like belief rằng Hùng là đỉnh; C26 cho thấy layer Khải ở trên cross-cell.
3. **Xuất hiện:** D+1.
4. **Hiểu:** mỗi source có thể làm player dừng sớm ở một “boss giả”.
5. **Sai hợp lý:** Hùng là mastermind vì CEO; Khoa là mastermind vì hospital; Hạnh là mastermind vì source người.
6. **Xác nhận:** knowledge mismatch — mỗi người thiếu một phần mà một mastermind phải biết; Khải xuất hiện ở giao điểm.
7. **Nếu miss:** player có thể đạt partial ending bắt/đẩy được một manager nhưng lõi sống.
8. **Notebook:** ghi mỗi người theo facts, không có hierarchy auto-generated.
9. **Mandatory:** Hiểu có layer cao hơn cần cho late route.
10. **True ending:** Có, vì D chỉ mở khi player không dừng ở Hùng/Khoa/Hạnh.

## R9 — Nam là command core, nhưng dấu sớm của ông đều có giải thích vô tội hợp lý

1. **Player cần hiểu:** Nam là người có quyền command trên cross-cell risk response; sự tử tế và đời sống hàng xóm của ông là thật, không phải giả 100%.
2. **Clue:** foreshadow C27/C28/C29; relation C30; current command C31/C32/C33/C34.
3. **Xuất hiện:** foreshadow ngay D0 opening; proof late D+1.
4. **Hiểu:** C27/C28 trước A+B+C chỉ là quá khứ nghề nghiệp; sau B/C mới đổi nghĩa. Chỉ C31+manager/record corroboration mới đủ D.
5. **Sai hợp lý:** Nam chỉ là người quen cũ của Hùng; ông vô tình có background cùng ngành; Hùng mới là boss.
6. **Xác nhận:** ít nhất hai dấu độc lập về **quyền command hiện tại**, không chỉ quan hệ cũ.
7. **Nếu miss:** A+B+C vẫn có thể phá phần lớn operation nhưng Nam/Khải có cơ hội thoát lõi → Cleanup/Partial.
8. **Notebook:** ghi “Nam từng làm logistics/thiết bị y tế”, “Nam có quan hệ cũ với Tân Lộ”, “Khải contact Nam at X time”; không ghi “boss”.
9. **Mandatory:** Nam reveal tồn tại ở final route, nhưng mức proof quyết định ending.
10. **True ending:** Bắt buộc. D cần hai nguồn/dấu command độc lập hoặc manager statement + independent record.

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

**Cách giải:** C20 cho thấy reclassification xảy ra ở quyền cao hơn; C22 truy lên Hùng; Đức xác nhận Tuấn chỉ thấy lớp vận hành.

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

**Cách giải:** C24–C26 chứng minh một risk layer cross-cell ở Khải; C31–C34 cho thấy command tiếp tục lên Nam.

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

**Cách giải:** C08 + C10 cho thấy withdrawal có trước pressure; police đã ghi nhận từ trước Bắc.

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

## 6.2. Clue giải oan

- C20: permission chain/timestamp cho thấy classification đã bị thay ở tầng cao hơn trước khi Tuấn xử lý assignment.
- C21: hành vi procedural tương tự xuất hiện ở một việc không liên quan plot.
- C22: quyền override truy về Hùng.
- C18: Đức biết Tuấn không nằm trong nhóm được giải thích core crime.
- Knowledge check: Tuấn không thể trả lời nhất quán những câu chỉ người core biết; đây không phải “diễn kém” mà là giới hạn thật.

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
- Player có thể mất 20–40 phút narrative time tương đương một source window vì theo đuổi giả thuyết sai.
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
- C31: crisis-time Khải→Nam contact.
- C32/C33: manager/record cho thấy decision authority.
- C34: synchronized branch changes sau command window.

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

### SLOT A1 — Withdrawal before pressure

Bắt buộc có:

- C08 hoặc equivalent direct record của Phúc;
- và C10/police corroboration.

Mục tiêu: chứng minh A bằng source người + source đã được ghi nhận độc lập.

### SLOT B1 — Hospital pattern

Bắt buộc:

- C11 Huyền review pattern;
- cộng **một trong** C12 hoặc C15.

Mục tiêu: một nguồn compliance + một nguồn cho thấy pattern không đơn giản là lỗi hành chính.

### SLOT C1 — Intentional logistics leadership involvement

Bắt buộc:

- C17 reclassification;
- cộng **một trong** C18, C19 hoặc một source tương đương từ Tuấn/Hùng đã được Vũ xác minh;
- C22 hoặc equivalent phải đặt quyết định ở tầng leadership, không ở worker.

### SLOT X — Cross-cell inference

Bắt buộc player hiểu và đưa được bridge để Vũ kiểm chứng:

- A+B+C không độc lập.
- C03/C26 là các bridge tốt, nhưng không phải duy nhất nếu Vũ có thể xác minh cùng relation bằng nguồn khác.

### SLOT D1 — Current command

Bắt buộc có một nguồn hiện tại cho thấy Nam có quyền decision trên nhiều cell:

- C32 manager-level statement/record; **hoặc**
- một source manager tương đương thuộc branch khác, nếu được corroborate.

### SLOT D2 — Independent corroboration of command

Bắt buộc thêm ít nhất một nguồn độc lập:

- C31 crisis-time Khải→Nam contact; hoặc
- C33/C34 institutional timing/record đủ mạnh; hoặc
- một record khác được police xác minh cho thấy decision chain kết thúc ở Nam.

**C27/C28/C30 chỉ hỗ trợ interpretation, không bao giờ đủ thay D1/D2.**

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

Fact F3 — Phúc muốn rút rồi mới bị gây sức ép  
├── C08 — withdrawal/contact record  
├── C09 — dấu đồng ý/tiền trước đó  
└── C10 — police chronology độc lập  
      ↓  
Inference I2 — đây không chỉ là “một giao dịch đổi ý”  
      ↓  
Proposition A — có môi giới phi pháp + pressure khi withdrawal

## 9.3. Proposition B

Fact F4 — Huyền phát hiện pattern nhiều hồ sơ  
├── C11 — review pattern + timestamp  
├── C12 — version/scope history  
└── C13 — procedural boundary của Huyền  
      ↓  
Inference I3 — Huyền đang điều tra anomaly, không phải người tạo nó

Fact F5 — Khoa/Thảo biết phần nhạy cảm hơn  
├── C14 — Thảo framing shift  
├── C15 — insider acknowledgment  
└── C16 — Khoa intervention timing  
      ↓  
Inference I4 — có cell/management knowledge bên trong hospital  
      ↓  
Proposition B

## 9.4. Proposition C

Fact F6 — Tân Lộ leadership biết và chủ ý tạo ngoại lệ  
├── C17 — reclassification  
├── C18 — Đức retained log  
├── C19 — Yến financial pattern  
└── C22 — Hùng override  
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
Correction I6 — Tuấn biết ngoại lệ nhưng không biết purpose; culpability của anh là làm ngơ, không phải organ-network command

## 9.6. Three-box network

Proposition A  
+ Proposition B  
+ Proposition C  
+ C03/C26 bridge  
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
C31/C32/C33/C34 needed for next layer

## 9.8. Nam / proposition D

C27 — Nam public logistics/medical background  
+ C28/C30 — old Tân Lộ relation  
      ↓  
Inference I9 — Nam có vị trí lịch sử hợp lý để nối hai thế giới  
      ↓  
**Không đủ D**

C31 — current crisis contact Khải→Nam  
+ C32 — manager-level command source  
OR C33 + C34 — independent current command pattern  
      ↓  
Inference I10 — Nam có decision authority trên cross-cell response  
      ↓  
Proposition D

## 9.9. Ending gate

A + B + C preserved by Vũ  
      ↓  
Police threshold E38  
      ↓  
D1 + D2 corroborated trước cleanup lock  
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
| C08 Phúc withdrawal record | D0 tối/D+1 | Không “mất” ở police nếu đã nộp; có thể miss encounter/source | player không mở đúng source | A vẫn có thể tới từ Vũ nhưng yếu hơn/đến muộn | True/Delay |
| C11 Huyền review | D+1 09:30–11:30 | access thu hẹp trưa/chiều | Khoa thu hẹp quyền/scope | B khó đạt trong game window | True/Delay |
| C12 review version history | D+1 sáng | khó lấy sau scope lock | quyền truy cập bị siết | phải dựa C15 làm corroborator B | True nếu C15 cũng miss |
| C15 Thảo acknowledgment | D+1 sáng | Thảo tự đóng lại/hospital lock | self-protection + Khoa control | B vẫn possible qua C12 | True nếu C12 miss |
| C17 reclassification | D+1 sáng | access vận hành khóa dần | cleanup Tân Lộ | mất core C record; cần Đức/Yến + police reconstruction | True/Delay |
| C18 Đức retained snapshot | D+1 09:30–11:00 | khoảng trưa khi Đức mất access/bị kiểm soát | Khải thu hẹp leak | C yếu và mất source giải oan Tuấn/Hùng layer | True/Delay |
| C19 Yến finance | D+1 10:30–12:30 | khi Hùng khóa access | cleanup/self-protection | mất alternative corroborator C | True nếu Đức miss |
| C20 Tuấn authority chain | D+1 | records khó tiếp cận sau cleanup | Tân Lộ khóa quyền | player dễ giữ false theory Tuấn, tốn timing | Delay/Cleanup |
| C22 Hùng override | D+1 | khó hơn sau cleanup; police có thể vẫn reconstruct nếu đã có C17 | access + manager self-protection | C leadership khó chứng minh | True/Cleanup |
| C24 Khoa→Khải | D+1 | contact/context khó hơn sau crisis | communication cleanup | mất half connector Khải | True/Partial |
| C25 Hùng→Khải | D+1 | tương tự | risk logs/contact context bị dọn | mất half connector | True/Partial |
| C26 cross-cell connector | D+1 trưa | không phải vật; phụ thuộc có C24+C25 | nếu một half miss thì inference yếu | A+B+C vẫn possible nhưng layer trên khó mở nhanh | True/Cleanup |
| C28 old Tân Lộ item | D0 opening | có thể vẫn ở phòng Nam nhưng access không còn an toàn late game | không nên quay lại vô hạn khi threat tăng | chỉ mất foreshadow, không khóa ending | none trực tiếp |
| C31 Khải→Nam crisis metadata | late D+1 | sau cleanup contact context/correlation khó preserve | các manager cắt liên hệ | D mất một independent source | True/Cleanup |
| C32 manager command source | late D+1 | source có thể rút/luật sư hóa/tự bảo vệ hoặc access đóng | risk tăng | cần route D thay thế C33+C34 | True |
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

- Có direct record + police chronology.
- C09 cố ý làm source không hoàn hảo nhưng không phủ định core fact.
- Không dùng “nạn nhân nói gì cũng đúng”; Vũ tách fact/suy đoán.

**PASS.**

## R3 — Hospital cell

**Vấn đề phát hiện:** nếu C15 Thảo nói quá nhiều, bà biến thành exposition machine.

**Sửa áp dụng:** C15 chỉ xác nhận discrepancy giữa hồ sơ và hoàn cảnh mà bà trực tiếp biết; không biết Nam/Tân Lộ/source people toàn bộ.

**PASS sau sửa.**

## R4 — Tân Lộ leadership

**Vấn đề:** C22 Hùng override + C17 có thể khiến C quá dễ nếu nó đồng thời nói rõ mục đích organ network.

**Sửa:** records chỉ chứng minh intentional hidden handling/leadership override. Ý nghĩa organ network chỉ xuất hiện khi A/B corroborate.

**PASS.**

## R5 — Tuấn innocent suspect

- Suspicion dựa trên quyền truy cập, defensive behavior và omission thật.
- Exoneration dựa permission/timing, không phải một NPC nói “Tuấn vô tội”.
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
4. D chỉ mở bằng **current command evidence** C31 + C32/C33/C34.
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
- D có current contact + manager/record corroboration.

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
- C31 không đứng một mình.
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
- B: C11+C12 hoặc C15.
- C: C17+C18/C19+C22.
- Cross-cell: C03/C26.
- D: C31 + C32 hoặc C33/C34.
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
2. C08+C10.
3. C11 + C12/C15.
4. C17 + C18/C19.
5. C20 để tránh Tuấn trap.
6. C24+C25/C26.
7. Đưa A+B+C sang Vũ sớm.

Mục tiêu: mở late command investigation.

## True route

Strong route  
+ tránh/giới hạn C35 leak trước preservation  
+ C31 current Khải→Nam relation  
+ C32 hoặc C33/C34 independent command source  
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
→ biết một người tên Phúc đã bị gây sức ép trước khi Bắc xuất hiện  
→ thấy hospital có pattern riêng  
→ thấy logistics có leadership override riêng  
→ nhận ra hai institution có cùng risk connector  
→ loại dần các suspect hợp lý nhưng sai tầng  
→ hiểu nhiều manager đang tự che lỗi chứ không có một “villain file”  
→ nhìn lại các chi tiết đời thường của Nam với nghĩa mới  
→ chứng minh command hiện tại bằng hai nguồn độc lập  
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
