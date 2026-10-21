# Longvita

Longvita là dự án ứng dụng Android hỗ trợ người trưởng thành bận rộn chuyển kiến thức dinh dưỡng từ sách thành thực đơn 7 ngày, công thức và danh sách mua sắm có thể áp dụng trong đời sống.

## Primary Persona

**Minh Anh, 28 tuổi** — nhân viên văn phòng muốn lên kế hoạch ăn uống lành mạnh nhanh hơn, xem lại thực đơn trên điện thoại và thao tác danh sách mua sắm thuận tiện bằng một tay.

Chi tiết: [`ux/persona.md`](ux/persona.md).

## Core User Flows

1. Tạo và lưu thực đơn 7 ngày.
2. Tổng hợp nguyên liệu và tạo danh sách mua sắm.
3. Tra cứu kiến thức từ sách và thay thế món ăn.

Chi tiết: [`ux/user-flow.md`](ux/user-flow.md).

## Screen Inventory

Ứng dụng có 10 màn hình độc lập từ `S01` Home đến `S10` Saved Plans. Loading, Empty, Error, Confirmation và Edit Ingredient Dialog là trạng thái/overlay của màn hình cha, không tính là màn hình độc lập.

## Figma

**Public view-only link:** [Longvita — UI/UX Design](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=1-6&p=f)

Link đã mở tới đúng file mà không xuất hiện yêu cầu đăng nhập vào ngày 2026-10-21. Canvas Figma chưa tải hoàn tất trong lần kiểm tra tự động, vì vậy checklist về 6 page, 10 màn hình và prototype vẫn cần được kiểm tra thủ công trong cửa sổ ẩn danh.

Figma cần có đủ sáu page:

1. `01 User Flow`
2. `02 Wireframe`
3. `03 Final UI`
4. `04 Design System`
5. `05 Components`
6. `06 Prototype`

### Offline `.fig` verification — 2026-10-21

File local `Longvita - UI_UX Design.fig` export lúc `2026-10-21T11:01:46.418Z` (18:01 giờ Việt Nam), SHA-256 `130F97610C9BCEA0391D619E925F3F005C019E85EFE88B67B2AF46C84643AFE8`, đã được giải mã và đối chiếu ở mức cấu trúc:

- Có đủ 6 page nêu trên; ngoài ra có một canvas nội bộ chứa Variables và Text/Effect styles.
- `03 Final UI` có đủ `S01–S10`, mỗi màn hình chính ở kích thước `360 x 800`.
- Có các required states cho `S03`, `S04`, `S06`, `S07` và một frame Responsive QA ở `412 dp`.
- `05 Components` có Button, TextField, Card, Navigation, AppBar, Dialog, Loading, Empty, Error và các component hỗ trợ.
- `06 Prototype` có đủ 3 flow starting point; `S07` mở Edit Ingredient Dialog bằng Overlay và `S03 Loading` tự chuyển sang `S04` sau 1 giây.
- Chưa đạt tiêu chí “không có dead end”: `Flow1 / S03 Generation Error` chỉ ghi nhận Cancel về Home; `Flow1 / S04 Save Error`, `Flow2 / S07 Empty Ingredients`, `Flow2 / S07 Undo Snackbar` và `Flow3 / S06 Update Error` chưa có recovery navigation. Overlay Edit/Validation cũng chưa ghi nhận interaction Save/Cancel/sửa lỗi trong file local.

## AI Tools Disclosure

- **Google Stitch:** tạo phương án giao diện ban đầu và các vòng lặp thiết kế; bằng chứng lưu trong `assets/stitch/`.
- **AI critique:** hỗ trợ đánh giá Nielsen Heuristics, Accessibility và sự phù hợp với Persona; prompt, kết quả và quyết định phải được ghi trong [`ai/ai-design-log.md`](ai/ai-design-log.md).

Mọi đề xuất AI phải được nhóm đánh giá và ghi quyết định `Accept`, `Modify` hoặc `Reject`; AI không thay thế quyết định thiết kế của nhóm.

## Deliverable Map

```text
Longvita/
├── README.md                         # Tổng quan và bản đồ bài nộp
├── ux/
│   ├── persona.md                    # Persona, pain points và success metric
│   └── user-flow.md                  # IA, 3 user flows và navigation
├── design/
│   ├── DESIGN.md                     # Design tokens và quy chuẩn hình ảnh
│   ├── screen-spec.md                # Đặc tả S01-S10
│   └── design-decisions.md           # Nhật ký Accept/Modify/Reject
├── ai/
│   └── ai-design-log.md              # Prompt, iterations và AI critique
├── assets/
│   ├── stitch/                       # Ảnh Google Stitch và Before/After
│   └── figma/                        # PNG Final UI được export
├── handoff/
│   └── flutter-handoff.md            # Bàn giao token, component và màn hình
└── docs/
    ├── task.md                        # Phân công và yêu cầu
    ├── work-sequence.md               # Trình tự thực hiện
    └── task-4-worklog.md              # Ghi chú công việc thành viên 4
```

## Review Checklist

- [ ] Link Figma mở được trong cửa sổ ẩn danh.
- [x] Figma có đủ 6 page và 10 màn hình `S01–S10`.
- [ ] Ba Prototype Flow không có dead end; Back hoạt động đúng.
- [x] S07 có Edit Ingredient Dialog dạng Overlay.
- [x] S03 Loading chuyển sang S04 Result.
- [x] `assets/figma/` có đủ 10 PNG Final UI hợp lệ, kích thước `360 x 800`.
- [ ] `ai-design-log.md` có prompt gốc, ít nhất 3 iterations và ít nhất 5 critique findings.
- [ ] `design-decisions.md` ghi các quyết định Accept/Modify/Reject.
- [ ] `screen-spec.md` và `flutter-handoff.md` đã đối chiếu Final UI.

## Current Documentation Status

- Persona, User Flow và Design System draft: đã có.
- Stitch initial screenshot: đã có.
- Screen Specification và Flutter Handoff: draft, chờ đối chiếu Final UI/Figma.
- Figma public link: đã thêm; quyền xem toàn bộ canvas vẫn cần kiểm tra thủ công trong cửa sổ ẩn danh.
- Final UI PNG: đã thêm đủ `S01–S10` và kiểm tra kích thước/chữ ký ảnh.
- AI iteration log và final design decisions: chờ đồng bộ phiên bản mới nhất từ `main` trước khi đánh dấu hoàn tất trên nhánh này.
