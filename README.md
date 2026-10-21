# Longvita

Longvita là dự án ứng dụng di động Android hỗ trợ chuyển đổi kiến thức dinh dưỡng trường thọ từ sách (*La dieta della longevità* — TS. Valter Longo) thành thực đơn hằng tuần, công thức nấu ăn chi tiết và danh sách mua sắm có thể áp dụng trực tiếp.

## 1. User Personas

- **Primary Persona:** **Minh Anh, 28 tuổi** — nhân viên văn phòng bận rộn, muốn cải thiện dinh dưỡng, tiết kiệm thời gian lên thực đơn tuần và đi chợ thuận tiện bằng thao tác một tay.
- **Secondary Persona:** **Bác Trần Văn Hoàng, 67 tuổi** — cán bộ hưu trí quan tâm phòng ngừa bệnh mạn tính và duy trì cơ bắp, cần giao diện chữ lớn, dễ đọc, tương phản cao và minh bạch nguồn món ăn.

Chi tiết: [`ux/persona.md`](ux/persona.md).

## 2. Core User Flows

1. **Flow 1 — Lập và lưu thực đơn:** `S01 → S02 → S03 → S04 → S10`.
2. **Flow 2 — Tổng hợp nguyên liệu và đi chợ:** `S04 → S07 → S08`.
3. **Flow 3 — Tra cứu sách và thay món:** `S04 → S05 → S09/S06 → S04`.

Chi tiết: [`ux/user-flow.md`](ux/user-flow.md).

## 3. Screen Inventory

Ứng dụng có đúng 10 màn hình độc lập:

- `S01` Home Dashboard
- `S02` Food Preferences
- `S03` Create Meal Plan
- `S04` Weekly Meal Plan
- `S05` Recipe Details
- `S06` Meal Alternatives
- `S07` Ingredient Summary
- `S08` Shopping List
- `S09` Book Knowledge
- `S10` Saved Plans

Loading, Empty, Error, Confirmation và Edit Ingredient Dialog là state/overlay của màn hình cha, không tính là màn hình độc lập.

## 4. Figma Design & Prototype

**Public view-only link:** [Longvita — UI/UX Design](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=0-1)

Nhóm ghi nhận link đã mở được ở chế độ ẩn danh. Khi nghiệm thu cuối, cần mở lại bằng cửa sổ ẩn danh trên thiết bị không đăng nhập để tránh rủi ro thay đổi quyền chia sẻ.

Figma có sáu page:

1. `01 User Flow`
2. `02 Wireframe`
3. `03 Final UI`
4. `04 Design System`
5. `05 Components`
6. `06 Prototype`

### Offline `.fig` verification — 2026-10-21

File `Longvita - UI_UX Design.fig` export lúc `2026-10-21T11:01:46.418Z` (18:01 giờ Việt Nam), SHA-256 `130F97610C9BCEA0391D619E925F3F005C019E85EFE88B67B2AF46C84643AFE8`, đã được giải mã và đối chiếu ở mức cấu trúc:

- Có đủ 6 page, 10 Final UI master `S01–S10` ở `360 x 800` và 10 bản Responsive QA ở `412 x 915`.
- Có 9 required state frame cho `S03`, `S04`, `S06`, `S07`; 64 Variables và 81 component symbols.
- Có 3 prototype starting point; `S07` mở Edit Ingredient Dialog bằng Overlay; `S03 Loading` tự chuyển sang `S04` sau `1000 ms`.
- Chưa đạt tiêu chí không có dead end: `S03 Generation Error` chỉ ghi nhận Cancel về Home; `S04 Save Error`, `S07 Empty Ingredients`, `S07 Undo Snackbar`, `S06 Update Error` và Edit/Validation Overlay còn thiếu recovery interaction trong file export.

## 5. AI Tools Disclosure

- **Google Stitch:** tạo giao diện ban đầu và ba vòng lặp tinh chỉnh; bằng chứng lưu trong [`assets/stitch/`](assets/stitch/).
- **AI critique:** đánh giá Nielsen Heuristics, Accessibility và sự phù hợp Persona; prompt và phân tích lưu tại [`ai/ai-design-log.md`](ai/ai-design-log.md).
- **Design decisions:** quyết định `Accept`, `Modify`, `Reject` và lý do lưu tại [`design/design-decisions.md`](design/design-decisions.md).

AI hỗ trợ quá trình thiết kế nhưng không thay thế quyết định của nhóm.

## 6. Deliverable Map

```text
Longvita/
├── README.md
├── ux/
│   ├── persona.md
│   └── user-flow.md
├── design/
│   ├── DESIGN.md
│   ├── screen-spec.md
│   └── design-decisions.md
├── ai/
│   └── ai-design-log.md
├── assets/
│   ├── stitch/
│   └── figma/
├── handoff/
│   └── flutter-handoff.md
└── docs/
    ├── task.md
    ├── work-sequence.md
    └── task-4-worklog.md
```

## 7. Review Checklist

- [x] Public Figma link đã được thêm; cần kiểm tra lại quyền ẩn danh ngay trước khi nộp.
- [x] Figma có đủ 6 page và 10 màn hình `S01–S10`.
- [ ] Ba Prototype Flow không có dead end; Back và recovery path hoạt động đúng.
- [x] `S07` có Edit Ingredient Dialog dạng Overlay.
- [x] `S03 Loading` chuyển sang `S04 Result` sau `1000 ms`.
- [x] `assets/figma/` có đủ 10 PNG Final UI hợp lệ, kích thước `360 x 800`.
- [x] `ai-design-log.md` có prompt gốc, ba iterations và ít nhất năm critique findings.
- [x] `design-decisions.md` ghi các quyết định `Accept`/`Modify`/`Reject`.
- [x] Cấu trúc `screen-spec.md` và `flutter-handoff.md` đã được đối chiếu với Final UI, component và token.
- [ ] Accessibility và prototype cần được chạy kiểm thử trực tiếp trên thiết kế cuối.

## 8. Current Documentation Status

- Persona, User Flow, AI log, Design Decisions, Final UI PNG, Screen Specification và Flutter Handoff đã có trong nhánh `Task_4`.
- Screen Specification và Flutter Handoff vẫn ở trạng thái Draft có kiểm soát do prototype recovery và accessibility chưa được xác nhận hoàn tất.
- Không đổi tài liệu sang `Final` trước khi các mục chưa đánh dấu ở checklist được xử lý và kiểm tra lại.
