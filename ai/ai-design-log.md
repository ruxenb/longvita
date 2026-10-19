# AI Design Log — Longvita Project

Tài liệu ghi chép toàn bộ quá trình sử dụng AI trong thiết kế UI/UX theo nguyên tắc **"AI tạo ra, bạn quyết định"** (Chuẩn PRM393 Lab 2).

---

## 1. UI Ban đầu từ Google Stitch (Initial AI Generation — v0)

### 1.1. Câu Prompt khởi tạo nguyên văn (Initial Prompt)

```text
Design a 3-screen mobile user flow for 'Longvita' (Android, 360x800 dp) targeting Minh Anh, a 28-year-old busy professional following the Longevity Diet. 
Visual Style based on DESIGN.md: Organic/Biomorphic, primary green (#6F8F4E), warm cream background (#F6F1E7), text (#2F3B2A), rounded corners (16-28px), minimum 48x48 dp touch targets.
The flow consists of 3 connected screens:
1. Screen S01 (Home): Clean dashboard with daily wellness greeting, quick overview of today's meals, and a prominent primary button "Create Weekly Plan".
2. Screen S03 (Create Meal Plan): Form to select 7-day cycle, input weight to calculate protein (0.8g/kg), meal frequency (2 or 3 meals/day), and low-mercury fish quota toggle (max 2-3 times/week).
3. Screen S04 (Weekly Meal Plan): Suggested 7-day plan card list with plant-based dishes, omega-3 reminder every 3 days, clear visual hierarchy, and a primary "Save Plan" action at the bottom.
```

### 1.2. Minh chứng kết quả ban đầu (v0)
- **Ảnh chụp kết quả nguyên bản:** `assets/stitch/v0/v0_initial.png` (hoặc `assets/stitch/stitch_v1_initial.png`).
- **Đánh giá ban đầu:** Stitch đã tạo ra bản xem trước hệ thống Design Tokens và 3 màn hình liên hoàn thuộc Flow 1 (`S01`, `S03`, `S04`), bao phủ phong cách Organic/Biomorphic với bảng màu xanh lá và nền kem ấm.

---

## 2. Bản phản biện giao diện bằng AI (AI UX & Accessibility Critique)

Sử dụng AI phản biện chi tiết giao diện do Stitch tạo ra theo **10 nguyên tắc Nielsen Heuristics**, **tiêu chuẩn WCAG 2.1 AA** và **nhu cầu của Persona Minh Anh (28 tuổi, nhân viên văn phòng bận rộn)**.

### Tổng hợp 9 phát hiện UX & Accessibility trọng yếu:

#### Phát hiện 1 (Finding 1 — S01 Home): Bảng điều khiển cạnh tranh với tác vụ chính
- **Mức độ:** Cao (P1) | **Tiêu chí:** Nielsen H8 (Aesthetic & Minimalist), Nielsen H6 (Recognition over recall).
- **Vấn đề quan sát:** Màn hình Home xếp chồng quá nhiều thẻ (cửa sổ nhịn ăn, chỉ số trường thọ, tuổi chuyển hóa, thực đơn trong ngày, nút ghi nhận bữa ăn), làm phân tán sự chú ý khỏi tác vụ tạo thực đơn tuần.

#### Phát hiện 2 (Finding 2 — S01 Home): Cỡ chữ nhãn phụ quá nhỏ, khó đọc
- **Mức độ:** Cao (P1) | **Tiêu chí:** WCAG 2.1 AA 1.4.4 (Resize Text), WCAG 1.4.3 (Contrast Minimum).
- **Vấn đề quan sát:** Nhãn thời gian, chi tiết dinh dưỡng và mô tả phụ rất nhỏ so với tiêu đề chính, khó đọc khi dùng điện thoại trong lúc di chuyển. Khuyến nghị nâng lên $\ge 14\text{sp}$.

#### Phát hiện 3 (Finding 3 — S01 Home): Trạng thái phụ thuộc quá nhiều vào màu sắc
- **Mức độ:** Cao (P1) | **Tiêu chí:** WCAG 2.1 AA 1.4.1 (Use of Color), Nielsen H4 (Consistency).
- **Vấn đề quan sát:** Các viên thuốc trạng thái như "Plant-Rich", "Logged", "Optimal" chỉ dùng màu để phân biệt, nguy cơ không nhận biết được với người mù màu.

#### Phát hiện 4 (Finding 4 — S03 Create Meal Plan): Quá nhiều khái niệm dinh dưỡng dồn vào 1 màn hình
- **Mức độ:** Cao (P1) | **Tiêu chí:** Nielsen H8 (Tối giản), Nielsen H7 (Linh hoạt & Hiệu quả).
- **Vấn đề quan sát:** Màn hình dồn chu kỳ 7 ngày, tính đạm, số bữa, khung giờ nhịn ăn, định mức cá thành danh sách dài, gây quá tải nhận thức, cản trở mục tiêu tạo thực đơn dưới 3 phút.

#### Phát hiện 5 (Finding 5 — S03 Create Meal Plan): Mục tiêu năng lượng/đạm cần phân định rõ
- **Mức độ:** Trung bình (P2) | **Tiêu chí:** Nielsen H2 (Match system and real world), Nielsen H6.
- **Vấn đề quan sát:** Hiển thị mục tiêu "44.0 g protein/ngày" và công thức "0.8 g/kg" cạnh ô cân nặng nhưng không phân biệt rõ ô nào là nhập liệu, ô nào là kết quả tính toán tự động.

#### Phát hiện 6 (Finding 6 — S04 Weekly Meal Plan): Mật độ thông tin thực đơn 7 ngày quá dày
- **Mức độ:** Cao (P1) | **Tiêu chí:** Nielsen H8 (Tối giản), Nielsen H4 (Nhất quán).
- **Vấn đề quan sát:** Màn hình kết hợp thanh chọn ngày, thẻ món ăn từng bữa, các nhãn dinh dưỡng chi tiết khiến màn hình dài và rối mắt trên viewport 360x800 dp.

#### Phát hiện 7 (Finding 7 — S04 Weekly Meal Plan): Thiếu lối dẫn rõ ràng sang Đi chợ
- **Mức độ:** Cao (P1) | **Tiêu chí:** Nielsen H1 (Visibility of system status), Nielsen H7 (Hiệu quả tác vụ).
- **Vấn đề quan sát:** Màn hình chỉ nhấn mạnh nút "Save Plan", nhưng thiếu lối dẫn trực tiếp sang danh sách nguyên liệu tổng hợp và danh sách đi chợ.

#### Phát hiện 8 (Finding 8 — S04 Weekly Meal Plan): Nhãn dinh dưỡng thiếu nhất quán
- **Mức độ:** Trung bình (P2) | **Tiêu chí:** Nielsen H4 (Nhất quán), WCAG 1.4.1 (Màu sắc).
- **Vấn đề quan sát:** Có quá nhiều kiểu nhãn (badge) khác nhau trên cùng thẻ món ăn khiến người dùng bối rối.

#### Phát hiện 9 (Finding 9 — Toàn bộ màn hình): Kích thước vùng chạm cần kiểm tra thực tế
- **Mức độ:** Cao (P1) | **Tiêu chí:** WCAG 2.5.5 (Target Size) & Android Accessibility (48 × 48 dp).
- **Vấn đề quan sát:** Các nút bấm nhỏ, checkbox, icon điều hướng có nguy cơ nhỏ hơn 48x48 dp.

---

## 3. Nhật ký 3 vòng lặp tinh chỉnh có ý nghĩa (3 Meaningful Iterations)

Dựa trên kết quả phản biện AI, nhóm thực hiện 3 vòng lặp tinh chỉnh trực tiếp trên giao diện:

---

### Vòng lặp 1 (Iteration 01 — Mã I01): Tối ưu Accessibility (v0 $\to$ v1)
- **Vấn đề nhắm tới:** Sửa **Finding #2** (Cỡ chữ nhỏ) + **Finding #9** (Vùng chạm nhỏ).
- **Mục tiêu:** Nâng cỡ chữ body/metadata lên $\ge 14\text{sp}$, đảm bảo độ tương phản chữ $\ge 4.5:1$, mở rộng vùng chạm hitbox $\ge 48\times 48\text{ dp}$. Giữ nguyên cấu trúc layout và màu sắc.
- **Câu Prompt nguyên văn trên Stitch:**
  ```text
  Refine the existing S01 Home, S03 Create Meal Plan, and S04 Weekly Meal Plan with accessibility fixes only. Keep the current visual style, layout structure, color palette (#6F8F4E primary, #F6F1E7 background), and all content unchanged.

  1. Increase all supporting/body text (meal times, nutrition details, status labels, badges, captions) to at least 14sp. Primary headings can stay as-is. Nothing should require squinting to read on a 360×800 dp Android phone.

  2. Ensure every text on cards meets WCAG 2.1 AA contrast (≥4.5:1 for normal text). Replace any light gray secondary text with a darker neutral (#2F3B2A or darker) so it passes the check.

  3. Expand all interactive touch targets (meal checkboxes, day selectors, small icons, +/- steppers, card actions) so the tappable area is at least 48×48 dp. Visible icon can stay smaller — just enlarge the hitbox.

  4. Do NOT change: layout order, number of sections, badge wording, or any feature. Only fix size and contrast.

  Output the updated S01, S03, and S04 screens.
  ```
- **Minh chứng Before / After:**
  - *Before:* `assets/stitch/v0/v0_initial.png`
  - *After:* `assets/stitch/v1/v1_S01_home.png`, `v1_S03_create_plan.png`, `v1_S04_weekly.png`
- **Tự kiểm tra (Self-check):** Chữ phụ đọc rõ ràng ở khoảng cách một cánh tay, không bị tràn viền, độ tương phản đạt chuẩn WCAG.

---

### Vòng lặp 2 (Iteration 02 — Mã I02): Tái cấu trúc & Giảm tải màn `S03` (v1 $\to$ v2)
- **Vấn đề nhắm tới:** Sửa **Finding #4** (Quá nhiều khái niệm dinh dưỡng) + **Finding #5** (Mục tiêu đạm không rõ). Chỉ thay đổi `S03`.
- **Mục tiêu:** Chia `S03` thành 3 nhóm rõ ràng (Cơ bản, Tùy chọn nâng cao, Xác nhận), phân biệt rõ ô nhập cân nặng với kết quả tính đạm tự động `0.8g/kg`.
- **Câu Prompt nguyên văn trên Stitch:**
  ```text
  Restructure S03 Create Meal Plan to reduce cognitive load. Keep the visual style (colors, typography, spacing) identical to version 1. Only S03 changes — S01 and S04 stay the same.

  Organize S03 into 3 clear horizontal groups with section headers:

  GROUP 1 — "Essential preferences" (top, always visible):
  - 7-day rhythm selector
  - Meal frequency (2 Meals / 3 Meals / 2 Meals + 1 Snack)
  - Dietary pattern (Plant-Rich / Mediterranean / etc.)
  Provide sensible defaults pre-selected.

  GROUP 2 — "Optional nutrition settings" (middle, secondary visual weight):
  - Weight input field labeled "Your weight (kg)" with a clear editable-input style
  - Read-only calculated result labeled "Calculated protein target: 44 g/day (0.8 g/kg)" with a small ⓘ info icon — distinguish visually from editable fields
  - Show "Optional" tag on this entire group header

  GROUP 3 — "Review & Generate" (bottom, sticky):
  - Short summary line: "7 days · 3 meals · Mediterranean"
  - Single primary button: "Generate Weekly Plan" using #6F8F4E

  Do NOT remove any nutritional controls. Do NOT change S01 or S04. Only restructure S03.
  ```
- **Minh chứng Before / After:**
  - *Before:* `assets/stitch/v1/v1_S03_create_plan.png`
  - *After:* `assets/stitch/v2/v2_S03_create_plan.png`
- **Tự kiểm tra (Self-check):** Màn hình chia 3 phần rành mạch, ô nhập cân nặng phân biệt rõ với kết quả đạm, nút Generate nằm ở đáy nổi bật.

---

### Vòng lặp 3 (Iteration 03 — Mã I03): Lối chuyển tiếp Đi chợ & Chuẩn hóa Badge trên `S04` (v2 $\to$ v3)
- **Vấn đề nhắm tới:** Sửa **Finding #7** (Thiếu lối dẫn đi chợ) + **Finding #8** (Nhãn dinh dưỡng thiếu nhất quán).
- **Mục tiêu:** Thêm nút "Shopping List · 24 items" ngay dưới nút Save trên `S04`; chuẩn hóa huy hiệu món ăn gồm Icon + Text ("From Book" vs "App Suggestion").
- **Câu Prompt nguyên văn trên Stitch:**
  ```text
  Update S04 Weekly Meal Plan to fix the shopping-list path and standardize all status badges. Keep the visual style identical to version 2. Only touch S04 and the badge style on S01.

  1. Add a persistent secondary button directly below the save action at the bottom of S04:
     Label: "🛒 Shopping List · 24 items"
     Style: high contrast, same size as primary button, but secondary visual weight (outline or lighter fill of #6F8F4E)
     This button is always visible — not buried in a menu.

  2. Standardize every badge on meal cards across S04 (and S01 if badges appear there). Use exactly ONE pill style with icon + text — never color alone:
     - "📖 From Book" for recipes from the source book
     - "✨ App Suggestion" for AI-generated recipes
     - "✓ Logged" for completed meals
     - "○ Pending" for not-yet-logged meals
     Keep the same shape, size, corner radius, font for all badges. Color can differentiate, but icon + text must always be present.

  3. Every meal card must have at most ONE dietary label (e.g., "Plant-Rich") plus the status badge. Do not stack 3+ labels on a card.

  4. Do NOT change S03. Do not change layout structure of S04 beyond adding the shopping button.

  Output updated S04 (and S01 if badge style changed).
  ```
- **Minh chứng Before / After:**
  - *Before:* `assets/stitch/v2/v2_S04_weekly.png` (hoển thị thực đơn đơn lẻ, nhãn rối)
  - *After:* `assets/stitch/v3/v3_S04_weekly.png` (có nút Shopping List và nhãn chuẩn hóa)
- **Tự kiểm tra (Self-check):** Nút Shopping List nổi bật, nhãn món ăn có icon và chữ rõ ràng, không bị quá tải thông tin.
