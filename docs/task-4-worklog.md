# Task 4 Worklog — Technical Writer & Flutter Handoff

**Branch:** `Task_4`

**Ngày cập nhật:** 2026-10-21

**Trạng thái:** Draft — chỉ còn các blocker thiết kế cuối

## 1. Mục tiêu

Hoàn thiện các phần thuộc trách nhiệm Thành viên 4 có thể thực hiện từ tài liệu hiện có, đồng thời không tự suy đoán những thông số chỉ có thể xác nhận sau khi Final UI, Components và Prototype trên Figma hoàn tất.

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
- File local `Longvita - UI_UX Design.fig`, export lúc `2026-10-21T11:01:46.418Z` (18:01 giờ Việt Nam), SHA-256 `130F97610C9BCEA0391D619E925F3F005C019E85EFE88B67B2AF46C84643AFE8`.

### Kết quả đối chiếu file `.fig` ngày 2026-10-21

- Giải mã thành công `2.699` node từ canvas Figma local.
- Xác nhận đủ 6 page, đủ `S01–S10` trên Final UI và kích thước màn hình chính `360 x 800`.
- Xác nhận 64 Variables thuộc ba nhóm `Longvita / Primitives`, `Longvita / Color`, `Longvita / Metrics`.
- Xác nhận component catalog có Button, TextField, Card, Navigation, AppBar, Dialog, Loading, Empty, Error và các component hỗ trợ.
- Xác nhận ba prototype starting point, Overlay Edit Ingredient tại `S07`, và chuyển tự động `S03 Loading` → `S04` sau 1 giây.
- Ngày 22/10/2026 đã kiểm tra trực tiếp Figma Page 06 và sửa prototype recovery: loại bỏ trigger `MOUSE_DOWN` xung đột với `ON_CLICK`, nối Retry/Edit Preferences/Keep Reviewing/Keep Original/Return/Undo, hoàn thiện Save/Cancel/Validation cho Edit Ingredient Overlay và thêm hotspot cho bottom navigation. Acceptance audit cuối đạt `22/22` core recovery behaviors và `16/16` CTA/navigation behaviors.
- Đưa 10 PNG Final UI từ nhánh `origin/member3-ui` vào `assets/figma/`; xác nhận `10/10` là PNG hợp lệ, kích thước `360 x 800`, không có file rỗng và có SHA-256 riêng biệt.
- Đồng bộ `origin/main` vào `Task_4`; giữ nội dung Persona phụ, AI log ba iterations, chín critique findings, Design Decisions và User Flow đã sửa đúng `S10`/`S08`.
- Dùng bằng chứng Thành viên 2 để chốt typography, elevation, 9 component groups/40 variants và Light theme trong Flutter Handoff.
- Dùng bằng chứng Thành viên 3 để xác nhận Final UI `360`, Responsive QA `412`, contrast, text `>=14 sp`, touch target `>=48 dp`, non-color cues, visual layout audit và 10 PNG cuối.

## 4. Giả định và giới hạn

- Nội dung ban đầu được viết theo User Flow và rubric; cấu trúc chính đã được đối chiếu với file `.fig` export ngày 2026-10-21 và prototype đã được chạy/audit trực tiếp trên Figma ngày 22/10/2026.
- Tên Flutter widget là đề xuất triển khai, không phải quyết định bắt buộc.
- Nhóm đã chốt responsive content max-width `600 dp` cho màn hình rộng và Shopping List checkbox persistence theo từng Shopping List.
- Chỉ đánh dấu các mục accessibility có bằng chứng trong worklog/verification; semantics và screen-reader behavior vẫn là yêu cầu downstream khi triển khai Flutter.
- Các mục chưa thể xác nhận được ghi `TBD`, checklist hoặc trạng thái Draft.

## 5. Việc còn chờ nhóm thiết kế

- Public Figma link đã được `origin/main` ghi nhận mở thành công bằng cửa sổ ẩn danh; nên kiểm tra lại ngay trước khi nộp như một bước vận hành, không còn xem đây là blocker tài liệu.
- Prototype recovery, CTA/navigation Flow 1/2, Overlay Edit/Validation, Undo, Shopping List persistence và responsive max-width `600 dp` đã được chốt ngày 22/10/2026.
- Semantics, focus order, screen-reader labels và mô tả ảnh được giữ trong handoff làm yêu cầu downstream khi triển khai Flutter, không dùng làm blocker cho việc hoàn thiện tài liệu thiết kế.

## 6. Hướng dẫn review

1. Đọc `design/screen-spec.md` và so từng màn hình với Figma Page 03.
2. Đọc `handoff/flutter-handoff.md` và đối chiếu component với Figma Page 05.
3. Chạy ba flow trên Figma Page 06 và kiểm tra navigation contract.
4. Ghi comment cho mọi giá trị khác với thiết kế thực tế; không xóa các cảnh báo `TBD` trước khi có bằng chứng.
5. Sau khi thống nhất, cập nhật các checklist và đổi trạng thái từ `Draft for review` sang `Final`.

## 7. Ngoài phạm vi commit này

- Không chỉnh sửa Figma.
- Không tạo hoặc thay đổi Final UI assets.
- Không sửa các lỗi nội dung đang có trong `ux/user-flow.md` để tránh trộn trách nhiệm Thành viên 1 vào cùng commit.
- Không mở Pull Request; branch được chuẩn bị để nhóm kiểm tra trước.
