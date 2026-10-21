# Task 4 — Trạng thái hoàn thiện và phân công phần còn lại

**Nhánh kiểm tra:** `Task_4`  
**Ngày cập nhật:** 21/10/2026  
**Phụ trách:** Thành viên 4 — Technical Writer & Flutter Handoff

## 1. Kết luận hiện tại

Phần lớn Task 4 đã có đủ bằng chứng từ repository và file Figma export để hoàn thiện tài liệu bàn giao. Các tài liệu về 10 màn hình, design system, component, token, accessibility ở mức thiết kế và ảnh Final UI đã được xác nhận.

Task 4 **chưa thể chuyển hoàn toàn sang trạng thái Final** vì còn ba quyết định/kiểm tra thiết kế chính:

1. Chạy và sửa các recovery path còn thiếu trong Figma Prototype.
2. Chốt quy tắc responsive cho màn hình rộng `>= 600 dp`.
3. Chốt quy tắc lưu trạng thái checkbox của Shopping List.

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

- Giải mã được 2.699 node.
- Có đủ sáu page và đủ `S01–S10`.
- Có ba prototype starting point.
- Xác nhận Overlay Edit Ingredient tại `S07`.
- Xác nhận `S03 Loading` tự chuyển sang `S04` sau một giây.

## 3. Những phần Codex có thể thực hiện

### 3.1. Chốt tài liệu responsive `>= 600 dp`

Codex có thể cập nhật toàn bộ Screen Spec và Flutter Handoff sau khi nhóm đồng ý quy tắc sau:

- `< 600 dp`: bố cục một cột, cuộn dọc, padding theo design token.
- `>= 600 dp`: căn giữa nội dung với `max-width: 600 dp`.
- Form và Recipe Details tiếp tục dùng một cột để giữ thứ tự đọc.
- Chỉ chuyển nhóm card sang hai cột khi không làm thay đổi thứ tự nội dung và thao tác.
- Dialog phải nằm trong viewport và cho phép cuộn khi chiều cao bị giới hạn.

Phần này Codex có thể tự sửa tài liệu, checklist và mapping Flutter; nhóm chỉ cần xác nhận quyết định thiết kế.

### 3.2. Chốt quy tắc lưu Shopping List

Codex có thể cập nhật đặc tả theo phương án đề xuất:

- Trạng thái check/uncheck được lưu theo từng Shopping List.
- Trạng thái vẫn còn khi đóng rồi mở lại danh sách.
- Shopping List mới bắt đầu với toàn bộ item chưa được check.
- Có thao tác `Clear completed` hoặc `Reset` nếu thiết kế cho phép.
- Flutter lưu qua repository/local persistence; UI không phụ thuộc trực tiếp vào công nghệ lưu trữ cụ thể.

Phần này Codex có thể hoàn thiện trong tài liệu ngay sau khi nhóm xác nhận hành vi mong muốn.

### 3.3. Hoàn thiện bộ tài liệu Task 4

Sau khi hai quyết định trên và Prototype được xác nhận, Codex có thể:

- Xóa các nhãn `TBD` không còn cần thiết.
- Cập nhật `design/screen-spec.md`.
- Cập nhật `handoff/flutter-handoff.md`.
- Cập nhật `docs/task-4-worklog.md` và README checklist.
- Đổi trạng thái tài liệu từ Draft sang Final.
- Commit và push lên nhánh `Task_4` để nhóm review.

## 4. Những phần cần thao tác thủ công hoặc cần quyền chỉnh sửa Figma

### 4.1. Kiểm tra và sửa Figma Prototype

File `.fig` mới nhất chưa ghi nhận đầy đủ các đường phục hồi sau:

- `S03 Generation Error`: hiện chỉ có Cancel về Home; còn thiếu Retry và Edit Preferences.
- `S04 Save Error`: chưa có recovery navigation rõ ràng.
- `S07 Empty Ingredients`: chưa có đường quay lại/chỉnh kế hoạch.
- `S07 Undo Snackbar`: chưa ghi nhận thao tác Undo trở về trạng thái trước khi xóa.
- Overlay Edit/Validation: chưa ghi nhận đầy đủ Save, Cancel và sửa lỗi validation.
- `S06 Update Error`: chưa có Retry hoặc Keep Original.

Các phần này phải được kiểm tra bằng Figma Present. Nếu link/file mở được với quyền Edit, Codex có thể thử nối interaction bằng điều khiển Figma Desktop. Nếu tự động hóa không ổn định, thành viên có quyền Edit cần nối thủ công.

Sau khi sửa, cần chạy đủ ba flow và xác nhận:

- Mọi CTA đi đúng màn hình.
- Back quay về đúng route nguồn.
- Mọi Error/Empty state đều có đường phục hồi.
- Không có dead end ngoài màn hình kết thúc chủ ý.
- Overlay mở, đóng, lưu và báo validation đúng.

### 4.2. Kiểm tra quyền xem trước khi nộp

Public Figma link đã từng được ghi nhận mở thành công. Tuy nhiên, trước khi nộp nhóm vẫn nên mở lại bằng cửa sổ ẩn danh để chắc chắn giảng viên không cần đăng nhập hoặc xin quyền.

### 4.3. Figma Version History

Nếu rubric yêu cầu mốc phiên bản có tên, một thành viên có quyền Edit cần tạo hoặc kiểm tra tên milestone trong Version History. File export `.fig` không đủ để chứng minh mục này.

### 4.4. Accessibility ở mức ứng dụng Flutter

Các mục sau không thể xác nhận chỉ bằng ảnh hoặc file Figma:

- Semantic label cho icon-only button và ảnh món ăn.
- Focus order thực tế.
- Trạng thái checked, selected, disabled và loading với screen reader.
- TalkBack/VoiceOver đọc lỗi và hướng khắc phục.
- Text scaling trên ứng dụng chạy thật.

Các mục này cần source code Flutter và thiết bị/emulator để triển khai, kiểm thử.

## 5. Phân công đề xuất

### Codex / Thành viên 4 có thể làm ngay

- Hoàn thiện đặc tả responsive sau khi nhóm duyệt giá trị `max-width`.
- Hoàn thiện đặc tả Shopping List persistence sau khi nhóm duyệt hành vi.
- Đồng bộ các quyết định vào Screen Spec, Flutter Handoff, README và worklog.
- Cập nhật checklist và trạng thái Final khi đã có bằng chứng Prototype.
- Commit/push tài liệu lên nhánh `Task_4`.

### Thành viên có quyền Edit Figma cần thực hiện

- Nối hoặc sửa các recovery interaction còn thiếu.
- Chạy ba flow trong Present mode và ghi nhận kết quả.
- Kiểm tra link public bằng cửa sổ ẩn danh.
- Tạo/check milestone trong Version History nếu rubric yêu cầu.

### Thành viên Flutter cần thực hiện sau này

- Triển khai semantics và focus order.
- Kiểm thử screen reader và text scaling.
- Triển khai persistence theo đặc tả đã được nhóm chốt.
- Kiểm thử responsive trên emulator/device thật.

## 6. Quyết định nhóm cần xác nhận

Nhóm chỉ cần trả lời ba điểm sau để Task 4 có thể tiếp tục:

1. Có duyệt `max-width: 600 dp` cho màn hình `>= 600 dp` hay chọn giá trị khác?
2. Shopping List có lưu checkbox sau khi thoát/mở lại không, và có cần `Clear completed`/`Reset` không?
3. Ai có quyền Edit Figma để sửa và chạy lại các recovery path trong Prototype?

## 7. Điều kiện để đánh dấu Task 4 hoàn thành

- [x] Đủ đặc tả cho 10 màn hình `S01–S10`.
- [x] Đủ mapping Design Tokens → Flutter.
- [x] Đủ mapping Components → Flutter Widgets.
- [x] Có 10 PNG Final UI hợp lệ.
- [x] Có bằng chứng typography, elevation, component variants và design accessibility.
- [ ] Responsive `>= 600 dp` được nhóm phê duyệt và ghi thành thông số cuối.
- [ ] Shopping List persistence được nhóm phê duyệt.
- [ ] Ba Prototype flow được chạy thành công và không còn dead end ngoài ý muốn.
- [ ] Các recovery path còn thiếu đã được nối và kiểm tra.
- [ ] Public Figma link được kiểm tra lại trước khi nộp.
- [ ] Tài liệu được đổi từ Draft sang Final sau khi các mục trên hoàn tất.

## 8. Tài liệu tham chiếu trong repository

- `design/screen-spec.md`
- `handoff/flutter-handoff.md`
- `docs/task-4-worklog.md`
- `docs/member-2-design-system-guide.md`
- `docs/member-3-ui-worklog.md`
- `design/design-system-tokens.json`
- `design/design-system-verification.json`
- `assets/figma/`

