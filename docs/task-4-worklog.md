# Task 4 Worklog — Technical Writer & Flutter Handoff

**Branch:** `Task_4`

**Ngày cập nhật:** 2026-10-18

**Trạng thái:** Draft for team review

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
- Thêm vị trí dành cho public Figma link.
- Thêm AI Tools Disclosure.
- Cập nhật Deliverable Map, Review Checklist và trạng thái tài liệu hiện tại.

## 3. Nguồn được sử dụng

- `docs/task.md`
- `docs/work-sequence.md`
- `ux/persona.md`
- `ux/user-flow.md`
- `design/DESIGN.md`

## 4. Giả định và giới hạn

- Nội dung được viết theo User Flow và yêu cầu rubric hiện có, chưa phải xác nhận trực quan từ Final UI.
- Tên Flutter widget là đề xuất triển khai, không phải quyết định bắt buộc.
- Không tự đặt giá trị spacing, typography, elevation hoặc max-width còn thiếu.
- Không tuyên bố Figma, prototype hoặc accessibility đã được kiểm thử khi chưa có bằng chứng.
- Các mục chưa thể xác nhận được ghi `TBD`, checklist hoặc trạng thái Draft.

## 5. Việc còn chờ nhóm thiết kế

- Public view-only Figma link đã kiểm tra bằng cửa sổ ẩn danh.
- Final UI `S01–S10` và các trạng thái liên quan.
- Component names, variants và token values thực tế trên Figma.
- Icon, font, illustration và ảnh món ăn chính thức.
- Export PNG vào `assets/figma/`.
- Prototype cho 3 flows, Dialog Overlay S07 và transition S03 → S04.
- Quyết định cuối về Dark mode, Shopping List persistence và responsive max-width.

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
