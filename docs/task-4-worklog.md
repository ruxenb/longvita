# Task 4 Worklog — Technical Writer & Flutter Handoff

**Branch:** `Task_4`

**Ngày cập nhật:** 2026-10-24

**Trạng thái:** Hoàn thành — đáp ứng đầy đủ phạm vi Task 4 của dự án hiện tại

## 1. Mục tiêu

Hoàn thiện đầy đủ các phần thuộc trách nhiệm Thành viên 4 trong phạm vi dự án hiện tại, đồng thời ghi nhận riêng các đề xuất nâng cấp để nhóm xem xét ở dự án tiếp theo.

## 2. Công việc đã thực hiện

### `design/screen-spec.md`

- Viết đặc tả cho đủ 10 màn hình `S01–S10`.
- Mỗi màn hình có mục đích, nội dung, tương tác, điều hướng và trạng thái liên quan.
- Ghi lại các ràng buộc chung về kích thước, contrast, text size, hit target và trạng thái lỗi.
- Thêm checklist các điểm cần đối chiếu với Figma trước khi chốt.

### `handoff/flutter-handoff.md`

- Bổ sung nguyên tắc triển khai Flutter và responsive behavior.
- Tạo bảng ánh xạ Design Tokens → Flutter.
- Tạo bảng ánh xạ Components → Flutter Widgets.
- Viết đủ 6 mục handoff cho từng màn hình:
  - Layout
  - Components
  - States
  - User interactions
  - Navigation
  - UI constraints
- Bổ sung navigation contract, mô hình trạng thái dữ liệu, accessibility checklist, danh sách asset còn thiếu và Definition of Done.

### `README.md`

- Mở rộng phần giới thiệu dự án và Primary Persona.
- Tóm tắt 3 Core User Flows và Screen Inventory.
- Thêm public Figma link vào README.
- Thêm AI Tools Disclosure.
- Cập nhật Deliverable Map, Review Checklist và trạng thái tài liệu hiện tại.

## 3. Nguồn được sử dụng

- `docs/task.md`
- `docs/work-sequence.md`
- `ux/persona.md`
- `ux/user-flow.md`
- `design/DESIGN.md`
- `ai/ai-design-log.md` và `design/design-decisions.md` từ `origin/main` commit `838aa31`.
- `design/design-system-tokens.json`, `design/design-system-verification.json`, `docs/member-2-design-system-guide.md` và ảnh Design System từ `origin/member-2/lab2-demo-finalization` commit `d6dfb95`.
- `docs/member-3-ui-worklog.md` và 10 PNG Final UI từ `origin/member3-ui` commit `ab8ae49`.
- File local `Longvita - UI_UX Design.fig` mới nhất, export lúc `2026-10-21T21:54:03.731Z` (04:54 ngày 22/10/2026, giờ Việt Nam), SHA-256 `066794C221D028425032A777A0FBD55C034AFA24E3D0C29E3441E2964FA042AD`.

### Kết quả đối chiếu file `.fig` ngày 2026-10-22

- Giải mã thành công `2.699` node từ canvas Figma local.
- Xác nhận đủ 6 page, đủ `S01–S10` trên Final UI và kích thước màn hình chính `360 x 800`.
- Xác nhận 64 Variables thuộc ba nhóm `Longvita / Primitives`, `Longvita / Color`, `Longvita / Metrics`.
- Xác nhận component catalog có Button, TextField, Card, Navigation, AppBar, Dialog, Loading, Empty, Error và các component hỗ trợ.
- Xác nhận ba prototype starting point, Overlay Edit Ingredient tại `S07`, và chuyển tự động `S03 Loading` → `S04` sau 1 giây.
- Ghi nhận các recovery path mở rộng chưa có trong file export: `Flow1 / S03 Generation Error` chỉ có Cancel về Home; `Flow1 / S04 Save Error`, `Flow2 / S07 Empty Ingredients`, `Flow2 / S07 Undo Snackbar`, `Flow3 / S06 Update Error` chưa có recovery navigation; Overlay Edit/Validation chưa ghi nhận Save/Cancel/sửa lỗi. Nhóm đã thống nhất đây là định hướng nâng cấp cho dự án tiếp theo, không thuộc tiêu chí còn thiếu của dự án hiện tại.
- Đưa 10 PNG Final UI từ nhánh `origin/member3-ui` vào `assets/figma/`; xác nhận `10/10` là PNG hợp lệ, kích thước `360 x 800`, không có file rỗng và có SHA-256 riêng biệt.
- Đồng bộ `origin/main` vào `Task_4`; giữ nội dung Persona phụ, AI log ba iterations, chín critique findings, Design Decisions và User Flow đã sửa đúng `S10`/`S08`.
- Dùng bằng chứng Thành viên 2 để chốt typography, elevation, 9 component groups/40 variants và Light theme trong Flutter Handoff.
- Dùng bằng chứng Thành viên 3 để xác nhận Final UI `360`, Responsive QA `412`, contrast, text `>=14 sp`, touch target `>=48 dp`, non-color cues, visual layout audit và 10 PNG cuối.

## 4. Giả định và giới hạn

- Nội dung được viết theo User Flow và rubric; cấu trúc chính đã được đối chiếu với file `.fig` mới nhất và đáp ứng phạm vi bàn giao hiện tại.
- Tên Flutter widget là đề xuất triển khai, không phải quyết định bắt buộc.
- Nhóm đã chốt vùng nội dung `max-width: 600 dp` cho màn hình `>= 600 dp` và lưu checkbox riêng theo từng Shopping List, kể cả khi đóng rồi mở lại.
- Chỉ các kết quả accessibility có bằng chứng trong worklog/verification mới được mô tả là đã kiểm tra; semantics runtime không được suy ra từ ảnh tĩnh và được chuyển sang định hướng dự án tiếp theo.
- Task 4 được đánh dấu hoàn thành theo phạm vi dự án hiện tại; các ý tưởng mở rộng không được dùng làm blocker cho việc nghiệm thu.

## 5. Định hướng dành cho dự án tiếp theo

Các nội dung dưới đây không thuộc phần còn thiếu của dự án hiện tại. Nhóm lưu lại làm roadmap nếu tiếp tục phát triển sản phẩm:

- Mở rộng và kiểm thử toàn bộ recovery navigation cho các trạng thái lỗi, empty và Undo.
- Bổ sung đầy đủ interaction Save, Cancel và sửa lỗi cho Overlay Edit/Validation.
- Khi triển khai Flutter, kiểm thử semantics, focus order, screen-reader labels, mô tả ảnh và TalkBack trên thiết bị thật.
- Thực hiện thêm usability test cho các nhánh lỗi và accessibility test tự động.
- Kiểm tra lại quyền truy cập public Figma ngay trước mỗi lần bàn giao sau này như một bước vận hành định kỳ.

## 6. Kết luận nghiệm thu Task 4

1. `design/screen-spec.md` đã mô tả đủ `S01–S10` và được đối chiếu với Final UI.
2. `handoff/flutter-handoff.md` đã có đủ sáu mục cho từng màn hình, hai bảng mapping toàn cục và các ràng buộc triển khai.
3. README, public Figma link, AI disclosure, deliverable map và 10 PNG Final UI đã được bàn giao.
4. Các bằng chứng về Design System, responsive và design accessibility đã được tổng hợp vào tài liệu.
5. Thành viên 4 không còn đầu việc bắt buộc chưa hoàn thành trong dự án hiện tại.

## 7. Ngoài phạm vi commit này

- Không chỉnh sửa Figma.
- Không tạo hoặc thay đổi Final UI assets.
- Không sửa các lỗi nội dung đang có trong `ux/user-flow.md` để tránh trộn trách nhiệm Thành viên 1 vào cùng commit.
- Không mở Pull Request; branch được chuẩn bị để nhóm kiểm tra trước.
