# Flutter Handoff

> Trạng thái: **Draft — prototype recovery pending**. Cấu trúc màn hình, component, token, typography, elevation, 10 PNG Final UI, design accessibility, responsive `max-width` và Shopping List persistence đã được chốt. Semantics/focus/screen-reader là checklist cho giai đoạn triển khai Flutter, không phải bằng chứng thiết kế tĩnh.

## 1. Phạm vi và nguyên tắc triển khai

- Target: Flutter mobile, ưu tiên Android.
- Thiết kế tham chiếu: `360 x 800 dp`, kiểm tra thêm ở `412 dp`.
- Với chiều rộng `>= 600 dp`, căn giữa nội dung trong vùng có `max-width: 600 dp`.
- Không đặt mã màu, font, spacing hoặc radius trực tiếp trong từng màn hình. Dùng theme và token dùng chung.
- Giữ semantics cho nút, checkbox, trường nhập và ảnh.
- Tôn trọng text scaling, contrast và reduced motion khi phù hợp.

## 2. Tokens-to-Flutter mapping

| Token nguồn | Giá trị hiện tại | Flutter đề xuất |
|---|---:|---|
| `colors.primary` | `#6F8F4E` | `ColorScheme.primary` |
| `colors.background` | `#F6F1E7` | `ColorScheme.surface` hoặc app background token |
| `colors.surface` | `#FFFFFF` | `ColorScheme.surfaceContainerLowest` |
| `colors.text` | `#2F3B2A` | `ColorScheme.onSurface` |
| `colors.accent` | `#D98B5F` | `ColorScheme.secondary` |
| `surface-strong` | `#EEE6D6` | Theme extension `surfaceStrong` |
| `border` | `#DCCDB0` | Theme extension `outlineSubtle` |
| `text-muted` | `#5C6B53` | Theme extension `textMuted` |
| `clay` | `#E7C9A9` | Theme extension `clay` |
| `Longvita/Brand` | Fraunces Bold, `20/28` | `TextTheme.titleLarge` hoặc theme extension |
| `Longvita/Heading/L` | Newsreader Bold, `28/36` | `TextTheme.headlineLarge` |
| `Longvita/Heading/M` | Newsreader SemiBold, `24/32` | `TextTheme.headlineMedium` |
| `Longvita/Title` | Newsreader SemiBold, `20/28` | `TextTheme.titleLarge` |
| `Longvita/Body` | Quicksand Regular, `16/26` | `TextTheme.bodyLarge` |
| `Longvita/Supporting` | Quicksand Medium, `14/22` | `TextTheme.bodyMedium` |
| `Longvita/Label` | Quicksand SemiBold, `14/20` | `TextTheme.labelLarge` |
| `Longvita/Label/Strong` | Quicksand Bold, `14/20` | `TextTheme.labelLarge` với weight 700 |
| `spacing.sm` | `8` | `AppSpacing.sm` |
| `spacing.md` | `16` | `AppSpacing.md` |
| `spacing.lg` | `32` | `AppSpacing.lg` |
| `rounded.sm` | `16` | `AppRadius.sm` |
| `rounded.md` | `28` | `AppRadius.md` |
| `rounded.lg` | `48` | `AppRadius.lg` |

Các metric đã xác nhận thêm từ Figma Variables: `space/0,4,8,12,16,24,32,48`; `radius/0,16,28,32,48,pill`; touch target `48`; button height `52`; icon size `24`; navigation height `80`; app bar height `64`; stroke `1` và `2`.

### Lưu ý về token

- Các giá trị chữ phía trên lấy từ `origin/member-2/lab2-demo-finalization`; kiểm tra Thành viên 3 xác nhận không còn non-icon text dưới `14 sp` trên các frame đã audit.
- Màu chữ trắng trên action green `#476429` đạt `6.72:1`; text chính trên nền kem đạt `10.48:1`; text phụ đạt `5.06:1` theo bằng chứng Design System.
- `Longvita/Elevation/0`: phẳng; `Elevation/1`: offset `0/1`, blur `3`, alpha `0.08`; `Elevation/2`: offset `0/4`, blur `16`, alpha `0.12`, màu `#2F3B2A`. Flutter nên ánh xạ bằng `BoxShadow`/theme extension thay vì đặt lẻ trên từng widget.
- Token nguồn `size/button/height = 52`, trong khi instance có icon và padding thực tế cao `56`; implementation nên giữ min-height `56` cho CTA và không giảm touch target dưới `48`.

## 3. Components-to-Widgets mapping

| Component thiết kế | Flutter đề xuất | Trạng thái bắt buộc |
|---|---|---|
| Button | `FilledButton`, `OutlinedButton` hoặc wrapper dùng chung | Default, Pressed, Disabled, Loading |
| Text field | `TextFormField` | Default, Focused, Filled, Error, Disabled |
| Card | `Card`/`InkWell` với theme chung | Default, Pressed |
| Bottom navigation | `NavigationBar` | Mỗi destination có trạng thái Selected |
| App bar | `AppBar` | Default, With actions |
| Dialog | `AlertDialog` hoặc custom `Dialog` | Confirmation, Destructive/Error |
| Loading state | `CircularProgressIndicator` hoặc Skeleton | Screen-level loading có semantics label |
| Empty state | Custom `EmptyStateView` | Icon/ảnh, thông điệp, một CTA |
| Error state | Custom `ErrorStateView` | Thông điệp, nguyên nhân dễ hiểu, Retry |
| Snackbar Undo | `SnackBar` + `SnackBarAction` | Undo sau khi xóa nguyên liệu |

Tên class ở trên là đề xuất kỹ thuật, không phải tên component Figma cuối cùng.

## 4. Screen handoff

### S01 — Home

- **Layout:** Safe area; header/hero; primary CTA; nhóm shortcut; navigation chính ở cuối nếu Final UI sử dụng.
- **Components:** App bar/brand header, Button, Card, Navigation.
- **States:** Default; optional first-use empty state.
- **User interactions:** Tạo kế hoạch; mở kế hoạch đã lưu; mở danh sách mua sắm; mở kiến thức sách.
- **Navigation:** `S02/S03`, `S08`, `S09`, `S10` theo lựa chọn.
- **UI constraints:** CTA chính phải nổi bật và reachable bằng một tay; không để shortcut có vùng chạm dưới `48 dp`.

### S02 — Food Preferences

- **Layout:** Form cuộn được, nhóm field theo nội dung, CTA tiếp tục ở cuối hoặc sticky theo Figma.
- **Components:** Text field, segmented/radio selection, Button, inline error.
- **States:** Default, Focused, Filled, Error, Disabled.
- **User interactions:** Chọn nhóm tuổi, nhập cân nặng, chọn số bữa và khung giờ; lưu/tiếp tục.
- **Navigation:** Tiếp tục → `S03`; khi đi từ `S06`, lưu rồi quay lại flow thay thế.
- **UI constraints:** Dùng `Form` và validator; lỗi có text; keyboard không che field/CTA; giữ dữ liệu khi Back hợp lý.

### S03 — Create Meal Plan

- **Layout:** Tóm tắt thiết lập, quy tắc chính, CTA tạo kế hoạch.
- **Components:** Card, Button, Loading state, Error state.
- **States:** Default, Loading, Generation Error, No suitable result.
- **User interactions:** Generate, Retry, Edit Preferences, Back.
- **Navigation:** Thành công → `S04`; chỉnh sở thích → `S02`.
- **UI constraints:** Chặn gửi trùng khi loading; loading có semantics; lỗi không làm mất cấu hình.

### S04 — Weekly Meal Plan

- **Layout:** Header; selector/ngày; danh sách meal card; nhóm hành động lưu và xem nguyên liệu.
- **Components:** App bar, Card, source badge, Button, Snackbar/Error state.
- **States:** Result, transitional Loading, Save Success, Save Error.
- **User interactions:** Mở món, lưu kế hoạch, xem nguyên liệu, chuyển ngày.
- **Navigation:** Meal → `S05`; ingredients → `S07`; saved plans → `S10`; Back theo route nguồn.
- **UI constraints:** Danh sách dài dùng lazy list; nhãn nguồn có icon + text; lỗi lưu giữ nguyên state hiện tại.

### S05 — Recipe Details

- **Layout:** Nội dung cuộn: hero/ảnh, metadata, nguyên liệu, các bước và action thay món.
- **Components:** App bar, Image, source badge, list/step row, Button.
- **States:** Default; unavailable image/reference fallback.
- **User interactions:** Mở kiến thức sách, thay món, Back.
- **Navigation:** Reference → `S09`; replace → `S06`; Back → `S04`.
- **UI constraints:** Ảnh có semantic label; steps theo thứ tự; hỗ trợ text scaling mà không cắt nội dung.

### S06 — Meal Alternatives

- **Layout:** Món hiện tại ở đầu; danh sách alternatives; CTA xác nhận.
- **Components:** Card/selectable row, Button, Empty state, Error state, optional Dialog.
- **States:** Default, Selected, Empty/No alternative, Update Error, Confirming.
- **User interactions:** Chọn, xác nhận, Retry, Cancel, sửa sở thích.
- **Navigation:** Thành công → `S04`; cancel → `S05`; revise preferences → `S02`.
- **UI constraints:** Chỉ cập nhật plan sau khi thành công; lỗi giữ món gốc; selection không chỉ biểu thị bằng màu.

### S07 — Ingredient Summary

- **Layout:** Danh sách section theo nhóm; tổng số lượng; CTA tạo Shopping List.
- **Components:** Grouped list, editable row, Dialog, Text field, Snackbar, Button.
- **States:** Default, Empty, Editing, Validation Error, Creation Error.
- **User interactions:** Sửa số lượng, xóa, Undo, tạo danh sách mua sắm.
- **Navigation:** Create list → `S08`; Back → `S04`.
- **UI constraints:** Dialog mở dạng overlay; input số dương; không đóng dialog khi validation thất bại; gộp đơn vị chỉ khi tương thích.

### S08 — Shopping List

- **Layout:** Danh sách phân section; progress/tóm tắt nếu có; navigation chính.
- **Components:** Checkbox/ListTile, section header, Empty state, Navigation.
- **States:** Default, Partially completed, Completed, Empty.
- **User interactions:** Check/uncheck nguyên liệu, cuộn danh sách, Back.
- **Navigation:** Back → `S07` hoặc route nguồn; top-level navigation theo Final UI.
- **UI constraints:** Checkbox/tile hit target `>= 48 dp`; hỗ trợ dùng một tay; trạng thái có semantics `checked`; lưu check/uncheck riêng theo từng Shopping List và khôi phục khi mở lại. Danh sách mới khởi tạo với toàn bộ item chưa check.

### S09 — Book Knowledge

- **Layout:** Header; danh sách chủ đề hoặc nội dung chi tiết cuộn được; citation/reference block.
- **Components:** App bar, Card/ListTile, source/reference label.
- **States:** Default, Detail-in-screen, No result/Unavailable reference.
- **User interactions:** Chọn chủ đề, mở nội dung, Back về route nguồn.
- **Navigation:** Khi mở từ `S05`, Back → `S05`; khi mở từ Home, Back → `S01`.
- **UI constraints:** Phân biệt rõ nội dung sách và diễn giải ứng dụng; nội dung dài hỗ trợ text scaling.

### S10 — Saved Plans

- **Layout:** Header; danh sách plan card; CTA tạo kế hoạch mới.
- **Components:** App bar, Card/ListTile, Empty state, Error state, Button.
- **States:** Default, Empty, Load Error.
- **User interactions:** Mở kế hoạch; tạo mới; Retry khi tải lỗi.
- **Navigation:** Mở plan → `S04`; tạo mới → `S03` hoặc `S02`; Back → `S01`.
- **UI constraints:** Mỗi card có tên và khoảng ngày dễ phân biệt; Empty state có một CTA rõ ràng.

## 5. Navigation contract

```text
S01 -> S02/S03, S08, S09, S10
S02 -> S03 (hoặc quay lại S06 khi sửa filter trong Flow 3)
S03 -> S04
S04 -> S05, S07, S10
S05 -> S06, S09
S06 -> S02, S04, S05
S07 -> S04, S08
S08 -> S07 hoặc route nguồn
S09 -> S01 hoặc S05 tùy route nguồn
S10 -> S01, S02/S03, S04
```

Flutter nên truyền `originRoute` hoặc dùng route stack chuẩn để Back từ `S04`, `S08` và `S09` trở về đúng nguồn thay vì hard-code một destination.

## 6. Trạng thái dữ liệu đề xuất

- `idle`: chưa bắt đầu tác vụ.
- `loading`: đang tải/tạo/cập nhật; chặn submit trùng.
- `success`: dữ liệu hợp lệ để render.
- `empty`: tác vụ thành công nhưng không có dữ liệu.
- `validationError`: lỗi đầu vào người dùng có thể sửa tại chỗ.
- `operationError`: lỗi tạo/lưu/cập nhật; giữ dữ liệu trước đó và cung cấp Retry.

Không hiển thị Loading bằng modal chặn toàn ứng dụng nếu chỉ một vùng nội dung đang cập nhật.

## 7. Accessibility checklist

- [x] Design QA không phát hiện hit target được audit nhỏ hơn `48 x 48 dp`.
- [x] Design QA không phát hiện non-icon text dưới `14 sp`; không còn text overflow trên 29 frame được audit.
- [x] Các cặp màu chính đã có số liệu contrast đạt ngưỡng tương ứng.
- [ ] Mọi icon-only button có semantic label/tooltip phù hợp.
- [ ] Ảnh món ăn có mô tả thay thế.
- [ ] Error có nội dung/hướng khắc phục trong thiết kế; khả năng đọc bởi screen reader phải kiểm tra khi triển khai Flutter.
- [ ] Focus order theo thứ tự đọc tự nhiên.
- [ ] Selected, checked, loading và disabled có semantics tương ứng.
- [x] Trạng thái có icon hoặc text bổ sung và không dùng màu làm tín hiệu duy nhất.

## 8. Responsive behavior

- `< 600 dp`: một cột, padding ngang theo token, danh sách cuộn dọc.
- `>= 600 dp`: căn giữa nội dung trong vùng `max-width: 600 dp`; có thể chuyển nhóm card sang hai cột nếu không phá thứ tự đọc.
- Form và Recipe Details ưu tiên một cột để dễ đọc.
- Dialog phải vừa viewport và cuộn nội dung khi chiều cao bị giới hạn.
- Giá trị breakpoint/max-width cuối cùng phải lấy từ Figma hoặc quyết định đã được nhóm phê duyệt.

## 9. Assets và dependency cần bàn giao thêm

- Font Fraunces và Quicksand/Nunito kèm license hoặc nguồn package đã thống nhất.
- Icon set chính thức và quy tắc stroke/fill.
- Hình món ăn, Empty/Error illustrations và semantic description.
- Export PNG từ `assets/figma/` phục vụ đối chiếu màn hình.
- Link Figma public/view-only.

## 10. Definition of Done

- [x] Đã xác nhận cấu trúc và kích thước chính của `S01–S10` trong file local từ Figma Page 03.
- [x] Đã xác nhận tên component và variant chính trong file local từ Figma Page 05.
- [ ] Ba flow chạy đúng trên Figma Page 06 và khớp navigation contract.
- [x] Dialog S07 là Overlay; Loading S03 chuyển sang Result S04 sau 1 giây.
- [x] Token màu, metric, typography và elevation đã được đối chiếu với bằng chứng Design System của Thành viên 2.
- [x] Design accessibility đã được đối chiếu bằng worklog/QA Thành viên 3; semantics, focus order và screen-reader behavior được giữ làm yêu cầu cho giai đoạn triển khai Flutter.
- [x] Responsive `>= 600 dp` dùng vùng nội dung có `max-width: 600 dp`.
- [x] Shopping List lưu trạng thái checkbox theo từng danh sách và khôi phục khi mở lại.
- [x] Link Figma và 10 PNG Final UI `S01–S10` đã được thêm vào repo; quyền xem ẩn danh vẫn được theo dõi riêng trong README.
