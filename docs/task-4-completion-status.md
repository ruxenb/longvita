# Task 4 — Trạng thái hoàn thành và định hướng dự án tiếp theo

**Nhánh kiểm tra:** `Task_4`  
**Ngày cập nhật:** 24/10/2026
**Phụ trách:** Thành viên 4 — Technical Writer & Flutter Handoff

## 1. Kết luận hiện tại

Task 4 **đã hoàn thành trong phạm vi dự án hiện tại**. Repository và file Figma export đã cung cấp đủ bằng chứng cho tài liệu về 10 màn hình, design system, component, token, accessibility ở mức thiết kế, Prototype demo và ảnh Final UI.

Nhóm thống nhất rằng các recovery path nâng cao và kiểm thử accessibility ở runtime là định hướng cho dự án tiếp theo. Các nội dung này không còn được xem là phần còn thiếu hoặc điều kiện chặn nghiệm thu Task 4 hiện tại.

Hai quyết định đặc tả trước đó đã được chốt ngày 21/10/2026:

1. Màn hình rộng `>= 600 dp` sử dụng vùng nội dung có `max-width: 600 dp`.
2. Trạng thái checkbox được lưu riêng theo từng Shopping List và vẫn được giữ khi người dùng thoát rồi mở lại danh sách.

Ngoài ra, accessibility ở mức Flutter như semantics, focus order và screen reader chỉ có thể kiểm thử sau khi có source code ứng dụng.

## 2. Những phần đã hoàn thành và có thể dùng làm bằng chứng

### Từ Thành viên 1 / nhánh `main`

- Primary Persona và Secondary Persona.
- Ba Core User Flows đã sửa đúng liên kết màn hình, bao gồm `S10` và `S08`.
- Public Figma link.
- AI Design Log gồm ba iteration và chín critique findings.
- Design Decisions theo nhóm Accept / Modify / Reject.

### Từ Thành viên 2

- 64 variables thuộc ba collection.
- Chín nhóm component bắt buộc, tổng cộng 40 variants.
- Typography cho Brand, Heading, Title, Body, Supporting và Label.
- Elevation 0, 1 và 2.
- Light theme được xác nhận; Dark mode không thuộc phạm vi hiện tại.
- Touch target tối thiểu `48 dp`; CTA được bàn giao với min-height `56 dp`.

### Từ Thành viên 3

- Đủ 10 màn hình Final UI `S01–S10` ở kích thước `360 x 800`.
- Đủ 10 bản Responsive QA ở kích thước `412 x 915`.
- Có chín state frame phục vụ kiểm tra Loading, Empty, Error và Overlay.
- 10 PNG Final UI đã được đưa vào `assets/figma/` và kiểm tra hợp lệ.
- Không phát hiện text thường nhỏ hơn `14 sp`, touch target nhỏ hơn `48 dp`, text overflow hoặc layout collision trong phạm vi audit.
- Các trạng thái không chỉ dùng màu làm tín hiệu duy nhất.

### Từ file Figma export mới nhất

- Export lúc `2026-10-21T21:54:03.731Z` (04:54 ngày 22/10/2026, giờ Việt Nam), SHA-256 `066794C221D028425032A777A0FBD55C034AFA24E3D0C29E3441E2964FA042AD`.
- Giải mã được 2.699 node.
- Có đủ sáu page và đủ `S01–S10`.
- Có ba prototype starting point.
- Xác nhận Overlay Edit Ingredient tại `S07`.
- Xác nhận `S03 Loading` tự chuyển sang `S04` sau một giây.

## 3. Những phần tài liệu đã hoàn thiện

### 3.1. Quy tắc responsive `>= 600 dp` — đã chốt

Nhóm đã đồng ý quy tắc sau:

- `< 600 dp`: bố cục một cột, cuộn dọc, padding theo design token.
- `>= 600 dp`: căn giữa nội dung với `max-width: 600 dp`.
- Form và Recipe Details tiếp tục dùng một cột để giữ thứ tự đọc.
- Chỉ chuyển nhóm card sang hai cột khi không làm thay đổi thứ tự nội dung và thao tác.
- Dialog phải nằm trong viewport và cho phép cuộn khi chiều cao bị giới hạn.

Quy tắc này đã được đồng bộ vào Screen Spec, Flutter Handoff, README và worklog.

### 3.2. Quy tắc lưu Shopping List — đã chốt

Nhóm đã đồng ý hành vi sau:

- Trạng thái check/uncheck được lưu theo từng Shopping List.
- Trạng thái vẫn còn khi đóng rồi mở lại danh sách.
- Shopping List mới bắt đầu với toàn bộ item chưa được check.
- Flutter lưu qua repository/local persistence; UI không phụ thuộc trực tiếp vào công nghệ lưu trữ cụ thể.

Quy tắc persistence đã được đồng bộ vào Screen Spec, Flutter Handoff, README và worklog. `Clear completed` hoặc `Reset` là chức năng tùy chọn, không phải điều kiện bắt buộc để hoàn thành Task 4 nếu Final UI không thiết kế hai thao tác này.

### 3.3. Trạng thái bộ tài liệu Task 4 — hoàn thành

- Screen Specification đã bao phủ đủ `S01–S10`.
- Flutter Handoff đã có đầy đủ mapping, navigation contract và ràng buộc triển khai.
- README, worklog, public Figma link và 10 PNG Final UI đã được bàn giao.
- Prototype đáp ứng phạm vi demo của dự án hiện tại.
- Các tài liệu Task 4 đã được chuyển từ `Draft` sang trạng thái `Hoàn thành`.

## 4. Định hướng dành cho dự án tiếp theo

Toàn bộ nội dung trong mục này là đề xuất nâng cấp nếu nhóm tiếp tục phát triển Longvita; đây không phải phần còn thiếu của dự án hiện tại.

### 4.1. Mở rộng Figma Prototype

File `.fig` mới nhất chưa ghi nhận đầy đủ các đường phục hồi sau:

- `S03 Generation Error`: hiện chỉ có Cancel về Home; còn thiếu Retry và Edit Preferences.
- `S04 Save Error`: chưa có recovery navigation rõ ràng.
- `S07 Empty Ingredients`: chưa có đường quay lại/chỉnh kế hoạch.
- `S07 Undo Snackbar`: chưa ghi nhận thao tác Undo trở về trạng thái trước khi xóa.
- Overlay Edit/Validation: chưa ghi nhận đầy đủ Save, Cancel và sửa lỗi validation.
- `S06 Update Error`: chưa có Retry hoặc Keep Original.

Trong dự án tiếp theo, các phần này có thể được bổ sung và kiểm tra bằng Figma Present bởi thành viên có quyền Edit.

Tiêu chí kiểm thử đề xuất sau khi mở rộng:

- Mọi CTA đi đúng màn hình.
- Back quay về đúng route nguồn.
- Mọi Error/Empty state đều có đường phục hồi.
- Không có dead end ngoài màn hình kết thúc chủ ý.
- Overlay mở, đóng, lưu và báo validation đúng.

### 4.2. Kiểm tra quyền xem ở các lần bàn giao sau

Public Figma link đã từng được ghi nhận mở thành công. Tuy nhiên, trước khi nộp nhóm vẫn nên mở lại bằng cửa sổ ẩn danh để chắc chắn giảng viên không cần đăng nhập hoặc xin quyền.

### 4.3. Figma Version History cho giai đoạn phát triển tiếp theo

Nếu rubric yêu cầu mốc phiên bản có tên, một thành viên có quyền Edit cần tạo hoặc kiểm tra tên milestone trong Version History. File export `.fig` không đủ để chứng minh mục này.

### 4.4. Accessibility khi triển khai ứng dụng Flutter

Các mục sau không thể xác nhận chỉ bằng ảnh hoặc file Figma:

- Semantic label cho icon-only button và ảnh món ăn.
- Focus order thực tế.
- Trạng thái checked, selected, disabled và loading với screen reader.
- TalkBack/VoiceOver đọc lỗi và hướng khắc phục.
- Text scaling trên ứng dụng chạy thật.

Các mục này cần source code Flutter và thiết bị/emulator để triển khai, kiểm thử.

## 5. Kết quả thực hiện và phân công tương lai

### Codex / Thành viên 4 đã thực hiện

- [x] Đồng bộ quy tắc `max-width: 600 dp` vào tài liệu handoff.
- [x] Đồng bộ quy tắc lưu checkbox theo từng Shopping List vào tài liệu handoff.
- [x] Đồng bộ các quyết định vào Screen Spec, Flutter Handoff, README và worklog.
- [x] Cập nhật checklist và trạng thái Task 4 thành Hoàn thành theo phạm vi dự án hiện tại.

### Đề xuất cho thành viên có quyền Edit Figma ở dự án tiếp theo

- Nối hoặc sửa các recovery interaction còn thiếu.
- Chạy ba flow trong Present mode và ghi nhận kết quả.
- Kiểm tra link public bằng cửa sổ ẩn danh.
- Tạo/check milestone trong Version History nếu rubric yêu cầu.

### Đề xuất cho thành viên Flutter ở dự án tiếp theo

- Triển khai semantics và focus order.
- Kiểm thử screen reader và text scaling.
- Triển khai persistence theo đặc tả đã được nhóm chốt.
- Kiểm thử responsive trên emulator/device thật.

## 6. Quyết định phạm vi

- [x] Đã duyệt `max-width: 600 dp` cho màn hình `>= 600 dp`.
- [x] Đã duyệt lưu checkbox theo từng Shopping List, kể cả sau khi thoát và mở lại.
- [x] Prototype hiện tại đáp ứng phạm vi demo; recovery path nâng cao được chuyển sang roadmap dự án tiếp theo.
- [x] Không còn đầu việc bắt buộc đang chờ đối với Task 4 của dự án hiện tại.

## 7. Điều kiện để đánh dấu Task 4 hoàn thành

- [x] Đủ đặc tả cho 10 màn hình `S01–S10`.
- [x] Đủ mapping Design Tokens → Flutter.
- [x] Đủ mapping Components → Flutter Widgets.
- [x] Có 10 PNG Final UI hợp lệ.
- [x] Có bằng chứng typography, elevation, component variants và design accessibility.
- [x] Responsive `>= 600 dp` dùng vùng nội dung có `max-width: 600 dp`.
- [x] Shopping List lưu trạng thái checkbox theo từng danh sách.
- [x] Ba Prototype flow và các tương tác chính đáp ứng phạm vi demo hiện tại.
- [x] Các recovery path nâng cao đã được ghi rõ trong roadmap dự án tiếp theo, không phải điều kiện nghiệm thu hiện tại.
- [x] Public Figma link đã được ghi nhận mở thành công; việc kiểm tra lại trước mỗi lần bàn giao là bước vận hành định kỳ.
- [x] Tài liệu được đổi từ Draft sang trạng thái Hoàn thành.

## 8. Tài liệu tham chiếu trong repository

- `design/screen-spec.md`
- `handoff/flutter-handoff.md`
- `docs/task-4-worklog.md`
- `docs/member-2-design-system-guide.md`
- `docs/member-3-ui-worklog.md`
- `design/design-system-tokens.json`
- `design/design-system-verification.json`
- `assets/figma/`

