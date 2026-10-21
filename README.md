# Longvita

Longvita là dự án ứng dụng di động Android hỗ trợ chuyển đổi kiến thức dinh dưỡng trường thọ từ sách (*La dieta della longevità* — TS. Valter Longo) thành thực đơn hằng tuần, công thức nấu ăn chi tiết và danh sách mua sắm tối ưu có thể áp dụng trực tiếp vào đời sống thực tế.

---

## 1. User Personas

* **Primary Persona (Chân dung chính):** **Minh Anh, 28 tuổi** — Nhân viên văn phòng bận rộn (nhóm tuổi `< 65`), muốn cải thiện chế độ dinh dưỡng, tiết kiệm thời gian lên thực đơn tuần và đi chợ thuận tiện bằng thao tác một tay.
* **Secondary Persona (Chân dung phụ):** **Bác Trần Văn Hoàng, 67 tuổi** — Cán bộ hưu trí (nhóm tuổi `≥ 65`), quan tâm phòng ngừa bệnh mạn tính, duy trì cơ bắp chống teo cơ (sarcopenia), cần giao diện chữ to, dễ đọc, độ tương phản cao và minh bạch nguồn gốc món ăn từ sách.

Chi tiết đầy đủ: [`ux/persona.md`](ux/persona.md).

---

## 2. Core User Flows (3 Luồng chính)

1. **Flow 1 — Lập & Lưu thực đơn 7 ngày:** `S01` Home → `S02` Food Preferences → `S03` Create Meal Plan → `S04` Weekly Meal Plan → `S10` Saved Plans.
2. **Flow 2 — Tổng hợp nguyên liệu & Đi chợ:** `S04` Weekly Meal Plan → `S07` Ingredient Summary (kèm Edit Ingredient Dialog Overlay) → `S08` Shopping List.
3. **Flow 3 — Tra cứu sách & Thay thế món ăn:** `S04` Weekly Meal Plan → `S05` Recipe Details → `S09` Book Knowledge → `S06` Meal Alternatives → `S04` Weekly Meal Plan.

Chi tiết sơ đồ Mermaid và ma trận luồng: [`ux/user-flow.md`](ux/user-flow.md).

---

## 3. Screen Inventory (10 Màn hình độc lập)

Ứng dụng bao gồm đúng 10 màn hình độc lập từ `S01` đến `S10`:
* `S01` — Home Dashboard
* `S02` — Food Preferences
* `S03` — Create Meal Plan
* `S04` — Weekly Meal Plan
* `S05` — Recipe Details
* `S06` — Meal Alternatives
* `S07` — Ingredient Summary
* `S08` — Shopping List
* `S09` — Book Knowledge
* `S10` — Saved Plans

*(Các trạng thái Loading, Empty, Error, Confirmation và Edit Ingredient Dialog Overlay được thiết kế gắn liền với màn hình cha tương ứng, không tính là màn hình độc lập).*

---

## 4. Figma Design & Prototype

* **Public View-Only Link:** [Longvita — UI/UX Design on Figma](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=0-1&t=V1zFv28huRfnPfb8-1)
* *(Đã kiểm tra và mở được ở chế độ Ẩn danh / Incognito window).*

Cấu trúc 6 Pages chuẩn trên Figma:
1. `01 User Flow` — Sơ đồ điều hướng và luồng trải nghiệm người dùng
2. `02 Wireframe` — Khung dây Low-fidelity cho 10 màn hình
3. `03 Final UI` — Thiết kế hoàn chỉnh 10 màn hình chuẩn 360x800 dp cùng các State variants bên cạnh
4. `04 Design System` — Hệ thống Tokens (Variables / Styles: Color, Typography, Spacing, Radius, Elevation)
5. `05 Components` — 9 nhóm Component hoàn chỉnh với Auto Layout và Variants
6. `06 Prototype` — Nối dây tương tác 3 luồng hoàn chỉnh, Dialog Overlay và Loading transition

---

## 5. AI Tools Disclosure (Công khai sử dụng AI)

* **Google Stitch:** Hỗ trợ tạo giao diện ban đầu và thực hiện 3 vòng lặp tinh chỉnh thiết kế (`v0` → `v1` → `v2` → `v3`). Bằng chứng ảnh và mã nguồn lưu tại [`assets/stitch/`](assets/stitch/).
* **AI Critique:** Đánh giá giao diện theo 10 nguyên tắc Nielsen Heuristics, tiêu chuẩn Accessibility (WCAG AA/AAA) và nhu cầu của Persona. Toàn bộ câu lệnh nguyên văn và phân tích được ghi tại [`ai/ai-design-log.md`](ai/ai-design-log.md).
* **Design Decisions:** Toàn bộ đề xuất từ AI đều được nhóm phản biện và phân loại quyết định `Accept`, `Modify` hoặc `Reject` với lý do bảo vệ cụ thể tại [`design/design-decisions.md`](design/design-decisions.md).

---

## 6. Deliverable Map (Bản đồ thư mục dự án)

```text
Longvita/
├── README.md                         # Tổng quan dự án, Persona, Figma link, AI disclosure
├── ux/
│   ├── persona.md                    # Primary & Secondary Persona, Problem statements, Metrics
│   └── user-flow.md                  # Information Architecture, 3 User flows, Flow-to-screen
├── design/
│   ├── DESIGN.md                     # Quy chuẩn Design tokens (Organic / Biomorphic)
│   ├── screen-spec.md                # Đặc tả chi tiết 10 màn hình S01-S10
│   └── design-decisions.md           # Nhật ký quyết định thiết kế Accept/Modify/Reject
├── ai/
│   └── ai-design-log.md              # Prompt gốc, 3 iterations và Nielsen critique
├── assets/
│   ├── stitch/                       # Ảnh màn hình và mã HTML từ Google Stitch (v0-v3)
│   └── figma/                        # Ảnh PNG xuất từ Final UI và Design system
├── handoff/
│   └── flutter-handoff.md            # Tài liệu bàn giao Flutter (Tokens & Components mapping)
└── docs/
    ├── task.md                       # Bảng phân công 4 gói việc & 12 slide thuyết trình
    └── work-sequence.md              # Lộ trình 10 ngày và mốc kiểm tra
```
