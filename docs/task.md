# Bảng Phân Công Nhiệm Vụ & Kế Hoạch Bảo Vệ — Dự Án Longvita

Tài liệu này bao phủ toàn bộ khối lượng công việc của bài **Lab 2 môn PRM393** (từ lúc phân tích Persona, User Flow, Design System cho đến khi hoàn thiện GitHub, Figma và bảo vệ trước Hội đồng chấm thi). Toàn bộ nội dung đã được **đối chiếu và chuẩn hóa 100% theo Guideline chính thức của bộ môn** tại [prm393-material.web.app/lab2-presentation](https://prm393-material.web.app/lab2-presentation) và **lịch sử commit Git thực tế**.

---

## 1. Phân công theo 4 Gói công việc chuyên trách (Work Packages)

Dự án được phân bổ đồng đều cho 4 thành viên theo 4 vai trò chuẩn, tương ứng với cơ cấu điểm số trong Rubric chấm Lab 2 (Tổng 100 điểm: 45đ Quy trình + 55đ Sản phẩm):

| Gói công việc / Thành viên | Nhánh Git & Tài khoản | Đầu mục công việc cụ thể | File GitHub & Figma phụ trách | Điểm Rubric |
| :--- | :--- | :--- | :--- | :---: |
| **Thành viên 1: Thái An**<br>*(UX & AI Prompt Lead)* | • **Branch:** `main`<br>• **Git:** `duongvuthaian@gmail.com`<br>• Quản trị chung Repo | • Xây dựng Persona chính (Minh Anh 28t) và Persona phụ (Bác Hoàng 67t).<br>• Xác lập Information Architecture (IA) và 3 User Flows cốt lõi.<br>• Vẽ sơ đồ 3 User Flows trên **Figma Page 01: User Flow**.<br>• Viết prompt nguyên văn trên **Google Stitch**, lưu ảnh ban đầu v0 vào `assets/stitch/v0/`.<br>• Thực hiện **3 vòng lặp tinh chỉnh (Iterations I01–I03)** trên Stitch, lưu ảnh Before/After.<br>• Thực hiện **AI Critique** theo 10 Nielsen Heuristics, WCAG 2.1 AA (9 phát hiện).<br>• Lập nhật ký AI Design Log và bảng quyết định thiết kế (D01–D07). | • `ux/persona.md`<br>• `ux/user-flow.md`<br>• `ai/ai-design-log.md`<br>• `design/design-decisions.md`<br>• `assets/stitch/`<br>• **Figma Page 01: User Flow** | **40 điểm**<br>(UX & Flows: 15đ;<br>AI Generation: 10đ;<br>AI Critique & Iterations: 15đ) |
| **Thành viên 2: CharlieMinh**<br>*(Design System & Component Architect)* | • **Branch:** `member-2/lab2-demo-finalization`<br>• **Git:** `CharlieMinh` | • Quản lý quy chuẩn nền tảng trong `design/DESIGN.md`.<br>• Thiết lập hệ thống **Design Tokens** bằng **Figma Variables & Styles** trên **Figma Page 04: Design System** (64 Variables: Primitives, Color, Metrics; không hard-code).<br>• Xây dựng đầy đủ **9 nhóm Component bắt buộc** bằng Auto Layout và Variants trên **Figma Page 05: Components**: `Button`, `TextField`, `Card`, `Navigation`, `AppBar`, `Dialog`, `Loading`, `Empty`, `Error`.<br>• Viết tài liệu hướng dẫn demo Design System `docs/member-2-design-system-guide.md`. | • `design/DESIGN.md`<br>• `docs/member-2-design-system-guide.md`<br>• **Figma Page 04: Design System**<br>• **Figma Page 05: Components** | **15 điểm**<br>(Design System & Components: 15đ) |
| **Thành viên 3: Hoàng DV (YAHsaveme)**<br>*(UI Designer & Prototyper)* | • **Branch:** `member3-ui`, `member3-prototype-fixes`<br>• **Git:** `hoangdvse183095@fpt.edu.vn` | • Vẽ khung dây Low-fidelity cho 10 màn hình trên **Figma Page 02: Wireframe**.<br>• Thiết kế hoàn chỉnh 10 màn hình `360x800 dp` trên **Figma Page 03: Final UI**.<br>• Thiết kế 9 State Variants (Loading, Empty, Error, Dialog) đặt cạnh màn gốc.<br>• Nhân bản và kiểm tra Responsive QA trên 10 màn hình ở kích thước `412x915 dp`.<br>• Tinh chỉnh thẩm mỹ (D08): chuyển radius về `4/8/12/16/full`, chỉnh action `#476429` & border `#74796C` đạt chuẩn WCAG AA contrast.<br>• Xuất 10 file PNG màn hình vào `assets/figma/`.<br>• Nối dây **Interactive Prototype** cho cả 3 Flows trên **Figma Page 06**: Flow starting points, Back navigation không có dead ends, Dialog Overlay trên `S07`, hiệu ứng chuyển Loading sang Result (`S03`→`S04`), các đường phục hồi (Recovery paths). | • `docs/member-3-ui-worklog.md`<br>• `assets/figma/` (10 PNG)<br>• `design/design-decisions.md` (Checklist kỹ thuật)<br>• **Figma Page 02: Wireframe**<br>• **Figma Page 03: Final UI**<br>• **Figma Page 06: Prototype** | **30 điểm**<br>(Final UI/UX: 20đ;<br>Interactive Prototype: 10đ) |
| **Thành viên 4: Thắng VLQ**<br>*(Technical Writer & Flutter Handoff Lead)* | • **Branch:** `Task_4`<br>• **Git:** `thangvlqse184739@fpt.edu.vn` | • Viết tài liệu đặc tả chi tiết 10 màn hình `design/screen-spec.md` (mục đích, nội dung, tương tác, navigation, state variants, constraints).<br>• Viết tài liệu bàn giao lập trình `handoff/flutter-handoff.md` đủ 6 mục cho mỗi màn hình, gồm cả hành vi tablet $\ge 600\text{dp}$.<br>• Xây dựng 2 bảng ánh xạ kỹ thuật: Tokens-to-Flutter (`ColorScheme`, `TextTheme`...) và Components-to-Widgets (`FilledButton`, `Card`...).<br>• Hoàn thiện `README.md` (tổng quan dự án, public Figma link, AI disclosure, deliverable map, review checklist).<br>• Viết nhật ký công việc tích hợp `docs/task-4-worklog.md`. | • `design/screen-spec.md`<br>• `handoff/flutter-handoff.md`<br>• `README.md`<br>• `docs/task-4-worklog.md` | **15 điểm**<br>(Flutter Handoff: 10đ;<br>Documentation: 5đ) |

---

## 2. Phân chia chi tiết 10 Màn hình (`S01`–`S10`) theo 3 Cụm luồng

| Cụm luồng | Loại nội dung | Chi tiết màn hình & Nghiệp vụ từ sách Valter Longo |
| :--- | :--- | :--- |
| **Cụm 1 (Flow 1 — Lập & Lưu thực đơn 7 ngày)** | **Màn hình:** | `S01` — Home Dashboard; `S02` — Food Preferences; `S03` — Create Meal Plan; `S04` — Weekly Meal Plan; `S10` — Saved Plans. |
|  | **Nghiệp vụ sách:** | Chọn nhóm tuổi (`<65` hoặc `≥65`), nhập cân nặng để tự động tính đạm (`0.8g/kg` cho người trẻ, tăng đạm thực vật chống teo cơ cho người già), chọn 2 hoặc 3 bữa/ngày, đếm số bữa cá trong tuần (tối đa `2–3 bữa/tuần`), khung nhịn ăn 12h, nhắc uống Multivitamin & Omega-3 mỗi 3 ngày. |
|  | **State Variants:** | Loading State chuyển tiếp sang `S04` Result; Generation Error trên `S03` và Save Error trên `S04` có nút Retry & Back. |
| **Cụm 2 (Flow 2 — Tổng hợp nguyên liệu & Đi chợ)** | **Màn hình:** | `S07` — Ingredient Summary; `S08` — Shopping List. |
|  | **Nghiệp vụ sách:** | Gom nhóm nguyên liệu khoa học: Rau củ, Các loại đậu, Hạt (`30g/ngày`: óc chó, hạnh nhân, hạt phỉ), Dầu ô liu nguyên chất (~3 muỗng canh/ngày), Cá ít thủy ngân. Checkbox vùng chạm $\ge 48\times 48\text{ dp}$ để Minh Anh thao tác một tay trong siêu thị. |
|  | **Dialog & State:** | **Edit Ingredient Dialog** mở dạng **Overlay** trên `S07` kèm Validation Error (không cho nhập số âm); Empty State khi chưa có nguyên liệu; Snackbar Undo khi xóa nhầm. |
| **Cụm 3 (Flow 3 — Tra cứu sách & Thay thế món ăn)** | **Màn hình:** | `S05` — Recipe Details; `S06` — Meal Alternatives; `S09` — Book Knowledge. |
|  | **Nghiệp vụ sách:** | Hiển thị định lượng chi tiết, đánh dấu bữa ăn $\ge 30\text{g protein}$. Phân biệt minh bạch bằng Icon + Chữ giữa **"📖 Từ sách: Phụ lục A"** và **"✨ App gợi ý"**. Đổi món tương đương theo sách (pasta nguyên cám $\leftrightarrow$ gạo hoang, lúa mạch, farro, quinoa). |
|  | **State Variants:** | Empty/No-Alternative State trên `S06` dẫn về `S02` để nới lỏng bộ lọc; Update Error State trên `S06` giữ nguyên món gốc và cho Retry. |

---

## 3. Kế hoạch Thuyết trình & Demo chuẩn theo Guideline (10' Trình bày + 5' Demo + 5' Q&A)

Căn cứ theo hướng dẫn chính thức [Lab 2 · Slide & Demo](https://prm393-material.web.app/lab2-presentation), buổi đánh giá gồm **10 phút thuyết trình (chuẩn 12 slides) + 5 phút Live Demo + 5 phút Q&A**. Cả 4 thành viên cùng tham gia, mỗi người chịu trách nhiệm đúng phần việc mình đã thực hiện:

### A. Cấu trúc chuẩn 12 Slides và Phân vai thuyết trình (10 phút)

| # | Tiêu đề chuẩn (Guideline) | Người trình bày & Thời lượng | Nội dung bắt buộc phải trình bày | Minh chứng bắt buộc phải chiếu |
| :---: | :--- | :--- | :--- | :--- |
| **01** | **Project Overview** | **Thành viên 1: Thái An**<br>*(45 giây)* | Tên sản phẩm (Longvita), đối tượng mục tiêu, danh sách 4 thành viên và vai trò, bài toán thực tế chuyển hóa sách *La dieta della longevità*. | Link GitHub repository + Figma public link |
| **02** | **Problem & Persona** | **Thành viên 1: Thái An**<br>*(45 giây)* | Bối cảnh người dùng bận rộn, mục tiêu ăn lành mạnh, pain points khi tự tính đạm/lên thực đơn; Problem statement và chỉ số thành công đo được (80% lên thực đơn < 3 phút). Giới thiệu cả Persona chính Minh Anh (28t) và phụ Bác Hoàng (67t). | `ux/persona.md` |
| **03** | **Information Architecture** | **Thành viên 1: Thái An**<br>*(45 giây)* | Sơ đồ Sitemap / cấu trúc điều hướng toàn diện; đủ 10 màn hình độc lập (`S01`–`S10`), phân biệt rõ màn hình cấp cao (Home, Saved Plans, Shopping List, Book Knowledge) và màn hình cấp con. | `ux/user-flow.md`; Figma Page 01 |
| **04** | **Three User Flows** | **Thành viên 1: Thái An**<br>*(50 giây)* | 3 sơ đồ luồng hoàn chỉnh start $\to$ goal $\to$ end; phân tích Happy path và Alternate paths; chỉ rõ ít nhất 1 nhánh lỗi và đường phục hồi; bảng ánh xạ Flow $\to$ Screen bao phủ 10 màn hình. | Figma Page 01; `ux/user-flow.md` |
| **05** | **AI UI Generation** | **Thành viên 2: CharlieMinh**<br>*(45 giây)* | Câu prompt tiếng Anh nguyên văn khởi tạo trên Google Stitch (chứa Persona, Task, Android 360x800dp, Constraints dinh dưỡng, Style từ DESIGN.md); chiếu ảnh kết quả giao diện Stitch ban đầu v0. | `design/DESIGN.md`; `ai/ai-design-log.md`; screenshots v0 |
| **06** | **AI Iterations & Critique** | **Thành viên 2: CharlieMinh**<br>*(55 giây)* | Tối thiểu 5 phát hiện UX & Accessibility (nhóm có 9 phát hiện gắn với từng màn hình theo Nielsen Heuristics và WCAG); 3 vòng lặp tinh chỉnh có mục tiêu khác nhau (I01: Cỡ chữ & Vùng chạm; I02: Tái cấu trúc S03; I03: Nút Đi chợ S04); đối chiếu ảnh Before/After. | `ai/ai-design-log.md`; ảnh v0 $\to$ v1 $\to$ v2 $\to$ v3 |
| **07** | **Design Decisions** | **Thành viên 2: CharlieMinh**<br>*(45 giây)* | Trình bày 3–5 ví dụ tiêu biểu về quyết định Chấp nhận (Accept — D01 gộp đi chợ, D03 nút đi chợ S04, D05 chuẩn a11y), Sửa đổi (Modify — D04 giữ quy chuẩn đạm 0.8g/kg thay vì xóa, D08 đổi radius về 4/8/12/16px) hoặc Từ chối (Reject — D07 từ chối tra giá siêu thị); giải trình căn cứ theo Persona và ràng buộc. | `design/design-decisions.md`; Figma |
| **08** | **Wireframe → Final UI** | **Thành viên 3: Hoàng DV**<br>*(55 giây)* | Đối chiếu khung dây Low-fidelity (Page 02) sang Final UI hoàn chỉnh (Page 03); phân cấp thị giác (visual hierarchy), tính nhất quán; bố trí các trạng thái Empty, Loading, Error và Dialog đặt ngay cạnh màn hình gốc. | Figma Page 02 & Page 03 (10 màn hình) |
| **09** | **Design System** | **Thành viên 3: Hoàng DV**<br>*(50 giây)* | Hệ thống Design Tokens: Color, Typography, Spacing, Radius, Elevation; minh chứng 64 Figma Variables / Styles; minh chứng 9 nhóm Component chuẩn Auto Layout có State Variants và các instances trên màn hình. | Figma Page 04 & Page 05 |
| **10** | **Accessibility / Responsive** | **Thành viên 3: Hoàng DV**<br>*(50 giây)* | Bằng chứng kiểm tra Accessibility: Độ tương phản chữ thường `#2F3B2A` đạt 10.48:1 (vượt WCAG AA $\ge 4.5:1$), vùng chạm hitbox $\ge 48\times 48\text{ dp}$, cỡ chữ nội dung $\ge 14\text{sp}$, không phụ thuộc vào màu sắc (dùng Icon + Label); đối chiếu bố cục responsive an toàn ở cả `360x800 dp` và `412x915 dp` (không overflow). | `design/design-decisions.md` (Checklist); Figma Page 03 QA copies |
| **11** | **Live Prototype** | **Thành viên 4: Thắng VLQ**<br>*(45 giây)* | Tổng quan kiến trúc Prototype trên Figma Page 06: cấu trúc 3 luồng chạy từ Flow starting point tới đích; xử lý nút Back thông suốt (cam kết không có ngõ cụt); trình diễn điểm nổi bật: Dialog Overlay trên S07 và hiệu ứng Loading $\to$ Result (S03 $\to$ S04); các nhánh lỗi và đường phục hồi. | Figma Page 06 |
| **12** | **Flutter Handoff / Summary** | **Thành viên 4: Thắng VLQ**<br>*(55 giây)* | Tài liệu bàn giao lập trình Flutter: đủ 6 mục đặc tả cho mỗi màn hình; 2 bảng ánh xạ Tokens-to-Flutter (`ColorScheme`, `TextTheme`) và Components-to-Widgets (`FilledButton`, `Card`...); hành vi co giãn trên tablet $\ge 600\text{dp}$; tổng kết kết quả đạt được, giới hạn hiện tại (quy hoạch FMD 5 ngày vào Phase 2 do an toàn y tế), link nộp bài. | `handoff/flutter-handoff.md`; `README.md`; GitHub repo |

---

### B. Kịch bản phối hợp Live Demonstration (7 bước bắt buộc trong 5 phút)

Đúng theo Mục 3 của Guideline, trong 5 phút Live Demo, **Thành viên 3 (Hoàng DV)** giữ vai trò **Driver** (thao tác trực tiếp trên Figma / Prototype), các thành viên lần lượt đóng vai trò **Narrator** thuyết minh:

```
[00:00 - 00:30] Bước 1: Chiếu lướt 6 Pages Figma theo đúng thứ tự (Narrator: Thành viên 2)
- Driver mở file Figma, click lần lượt qua đúng 6 Pages: 
  01 User Flow -> 02 Wireframe -> 03 Final UI -> 04 Design System -> 05 Components -> 06 Prototype.
- Lời thoại: "File Figma của nhóm được tổ chức chuẩn hóa gồm đúng 6 Pages theo quy định, liên kết chặt chẽ từ phân tích luồng đến nguyên mẫu tương tác."

[00:30 - 01:00] Bước 2: Zoom vào Page 03 Final UI (Narrator: Thành viên 3)
- Driver zoom vào Page 03, rê chuột chỉ rõ 10 màn hình độc lập S01-S10.
- Lời thoại: "Trên Final UI, nhóm có đúng 10 màn hình độc lập từ S01 đến S10. Các Dialog Overlay và trạng thái Loading/Empty/Error được đặt ngay bên cạnh màn hình cha tương ứng, không tính là màn hình riêng để đảm bảo đúng quy chuẩn đề bài (C6)."

[01:00 - 02:30] Bước 3: Chạy trực tiếp cả 3 Flows trên Prototype (Narrator: Thành viên 1 & 3)
- Driver bấm Present chạy Page 06:
  + Flow 1: Start từ S01 -> qua S02 cấu hình tuổi/cân nặng -> S03 bấm Generate -> Loading xoay -> sang S04 -> bấm Save sang S10. Bấm thử nhánh lỗi tạo thực đơn -> bấm "Retry" để phục hồi. Bấm nút Back quay về trang trước an toàn.
  + Flow 2: Từ S04 -> bấm nút Shopping List -> sang S07 xem nguyên liệu gộp -> sang S08 tích chọn checkbox đi chợ bằng một tay.
  + Flow 3: Từ S04 mở S05 -> tra cứu sách S09 -> quay lại S05 chọn Replace -> sang S06 chọn món thay thế -> xác nhận cập nhật lại S04.
- Lời thoại: "Cả 3 luồng đều có Flow starting point, nút Back thông suốt và nhánh phục hồi lỗi hoàn chỉnh, cam kết không có điểm cụt (no dead ends)."

[02:30 - 03:00] Bước 4: Demo Dialog Overlay S07 & Chuyển cảnh Loading S03->S04 (Narrator: Thành viên 3)
- Driver mở S07, click nút sửa nguyên liệu -> Edit Ingredient Dialog mở đè lên dạng Overlay làm mờ nền phía sau.
- Driver quay về S03, bấm Generate -> màn hình Loading hiển thị hiệu ứng xoay rồi tự động chuyển sang màn hình kết quả S04 sau 1 giây (1000ms).
- Lời thoại: "Thầy/Cô có thể thấy Edit Dialog mở dạng Overlay đè lên S07 và hiệu ứng chuyển tiếp tự động từ Loading sang S04 Result sau 1000ms."

[03:00 - 03:45] Bước 5: Bóc tách Tokens & Components trên Page 04, 05 (Narrator: Thành viên 2)
- Driver chuyển sang Page 04, mở panel Variables (chiếu 64 tokens: Primitives, Colors, Metrics).
- Driver chuyển sang Page 05, click vào Button Component, bật tắt các biến thể Variants (Default, Pressed, Loading, Disabled) và chỉ rõ Auto Layout đang bật.
- Lời thoại: "Toàn bộ hệ thống dùng 64 Figma Variables, 9 nhóm component đều dùng Auto Layout và Variants, tuyệt đối không hard-code mã màu hay khoảng cách."

[03:45 - 04:15] Bước 6: Truy vết AI Design Log trên GitHub (Narrator: Thành viên 1)
- Driver mở trình duyệt vào file `ai/ai-design-log.md` trên repo GitHub.
- Chỉ vào Prompt nguyên văn v0 -> ảnh Stitch v0 -> phát hiện Finding #2 (font nhỏ) & Finding #9 (hitbox nhỏ) -> Prompt vòng lặp I01 -> ảnh After v1 trên Figma.
- Lời thoại: "Nhóm tuân thủ nguyên tắc 'AI tạo ra, con người quyết định', có đầy đủ chứng cứ truy vết từ câu prompt, phản biện UX cho đến ảnh Before/After."

[04:15 - 05:00] Bước 7: Mở Spec & Flutter Handoff trên GitHub (Narrator: Thành viên 4)
- Driver mở `design/screen-spec.md` (chỉ 6 mục đặc tả của S01) -> mở tiếp `handoff/flutter-handoff.md` (chỉ 2 bảng ánh xạ Tokens sang ColorScheme và Components sang Flutter Widgets).
- Lời thoại: "Tài liệu bàn giao sẵn sàng cho đội ngũ lập trình Flutter với 6 trường chi tiết cho 10 màn hình và 2 bảng ánh xạ kỹ thuật toàn diện."
```

---

### C. Chiến lược trả lời 7 Câu hỏi Giảng viên có thể sử dụng (Mục 6 Guideline)

Theo đúng danh mục 7 câu hỏi chính thức được bộ môn công bố tại Mục 6 của Guideline, nhóm đã chuẩn bị sẵn câu trả lời sắc bén:

1. **Câu 1: "Persona có nhu cầu gì khiến bạn chọn cấu trúc điều hướng này?"**
   * **Người trả lời:** **Thành viên 1 (Thái An)**.
   * **Nội dung trả lời:** *"Minh Anh là nhân viên văn phòng 28 tuổi, rất bận rộn và thường vào app với mục tiêu nhanh gọn: xem thực đơn hôm nay ăn gì hoặc đi chợ mua gì. Do đó, nhóm chọn cấu trúc điều hướng phân cấp (Hierarchical Navigation) kết hợp Bottom Bar đưa 4 điểm đến chính (Home, Saved Plans, Shopping List, Book Knowledge) lên cấp cao nhất. Việc cấu hình sở thích dinh dưỡng (S02) được đưa vào dạng lồng (Nested) để người dùng chỉ cần thiết lập 1 lần, những lần sau mở app là có thể tạo thực đơn ngay trong vòng dưới 3 phút."*

2. **Câu 2: "Flow nào dễ thất bại nhất? Khi xảy ra lỗi, người dùng phục hồi ra sao?"**
   * **Người trả lời:** **Thành viên 1 & Thành viên 3 (Hoàng DV)**.
   * **Nội dung trả lời:** *"Flow 1 (Lập & Lưu thực đơn) là luồng dễ thất bại nhất vì phụ thuộc vào việc tính toán dinh dưỡng (tính đạm 0.8g/kg, lọc cá 2-3 bữa/tuần) và lưu trữ dữ liệu. Khi xảy ra lỗi: (1) Nếu lỗi tạo thực đơn (Generation Error trên S03), app không đóng mà hiển thị thông báo lỗi thân thiện kèm nút Retry và nút 'Edit Preferences' để người dùng quay về S02 nới lỏng tiêu chí; (2) Nếu lỗi lưu thực đơn (Save Error trên S04), app vẫn giữ nguyên toàn bộ thực đơn trên màn hình và cung cấp nút Thử lại, tuyệt đối không làm mất dữ liệu đã sinh ra của người dùng."*

3. **Câu 3: "Một đề xuất AI nào đã bị từ chối? Vì sao?"**
   * **Người trả lời:** **Thành viên 2 (CharlieMinh)**.
   * **Nội dung trả lời:** *"Đề xuất D07 từ AI gợi ý: 'Tích hợp tính năng tra cứu giá cả siêu thị và chỉ đường trong quầy hàng tự động'. Nhóm đã kiên quyết TỪ CHỐI (REJECT) vì tính năng này thuộc phạm vi ứng dụng thương mại điện tử / bán lẻ, làm loãng mục tiêu cốt lõi của Longvita là 'chuyển hóa kiến thức sách trường thọ thành thực đơn khoa học', đồng thời vượt quá phạm vi và thời gian 2 tuần của bài Lab 2."*

4. **Câu 4: "Ba vòng lặp đã giải quyết ba vấn đề UX khác nhau như thế nào?"**
   * **Người trả lời:** **Thành viên 2 (CharlieMinh)**.
   * **Nội dung trả lời:** *"Ba vòng lặp nhắm vào 3 mục tiêu hoàn toàn khác nhau: (1) Vòng lặp I01 tập trung vào Accessibility: sửa lỗi font chữ nhỏ (<14sp) và mở rộng vùng chạm hitbox nút/checkbox $\ge 48\text{dp}$; (2) Vòng lặp I02 tập trung vào Giảm tải nhận thức trên S03: chia form dài thành 3 nhóm trực quan (Sở thích thiết yếu $\to$ Tùy chọn nâng cao với ô tính đạm read-only $\to$ Nút Generate cố định); (3) Vòng lặp I03 tập trung vào Hiệu quả tác vụ và Nhất quán trên S04: thêm nút chuyển tiếp nhanh sang Đi chợ và chuẩn hóa huy hiệu món ăn (chỉ dùng icon + chữ: From Book, App Suggestion)."*

5. **Câu 5: "Nếu đổi primary color hoặc spacing token, những màn hình nào tự cập nhật?"**
   * **Người trả lời:** **Thành viên 2 (CharlieMinh)**.
   * **Nội dung trả lời:** *"Toàn bộ 10 màn hình Final UI và 10 bản Responsive QA sẽ tự động cập nhật ngay lập tức. Vì trên Figma Page 04 nhóm đã thiết lập 64 Figma Variables cho Color (`primary`, `primary-action`, `surface`...) và Spacing (`spacing/4`, `8`, `16`...), sau đó gắn các Variables này trực tiếp vào 9 nhóm Component trên Page 05. Các màn hình trên Page 03 đều là instance của component và liên kết trực tiếp với token, tuyệt đối không có mã màu hard-code."*

6. **Câu 6: "Làm thế nào chứng minh màn hình rộng 412 dp không vỡ layout?"**
   * **Người trả lời:** **Thành viên 3 (Hoàng DV)**.
   * **Nội dung trả lời:** *"Nhóm đã tạo riêng một khu vực 'Responsive QA — 412dp' trên Page 03, nhân bản đủ 10 màn hình ở kích thước container `412x915 dp` và mở rộng khung nội dung lên 380dp bằng Auto Layout co giãn (Fill container), tuyệt đối không dùng thao tác co kéo tỷ lệ (scale tool). Kết quả kiểm tra biên tự động: toàn bộ thanh App bar, Bottom bar và thẻ card dàn đều theo chiều ngang, thanh chọn ngày hiển thị trọn vẹn 7 ngày, cỡ chữ và hitbox $\ge 48\text{dp}$ được giữ nguyên, không có bất kỳ hiện tượng tràn viền (overflow) nào."*

7. **Câu 7: "Một lập trình viên Flutter chưa biết dự án sẽ dựa vào đâu để dựng màn hình và states?"**
   * **Người trả lời:** **Thành viên 4 (Thắng VLQ)**.
   * **Nội dung trả lời:** *"Lập trình viên chỉ cần mở file `handoff/flutter-handoff.md`: (1) Khởi tạo `ThemeData` từ bảng ánh xạ Tokens-to-Flutter (`ColorScheme`, `TextTheme`); (2) Dựng 9 Widget dùng chung từ bảng ánh xạ Components-to-Widgets; (3) Khi code bất kỳ màn hình nào trong S01–S10, dev chỉ cần đọc đúng 6 mục đặc tả chuẩn: Layout, Components, States (Default, Loading, Empty, Error), User interactions, Navigation và UI constraints (kèm hành vi co giãn tablet $\ge 600\text{dp}$) mà không cần tự suy đoán bất kỳ thông số nào."*

---

## 4. Bảng Đối Chiếu Lịch Sử Commit Git Thực Tế (Academic Integrity)

Để minh chứng tính trung thực học thuật và quá trình làm việc liên tục rải đều qua các giai đoạn (không nộp bài dồn vào phút cuối), dưới đây là bảng đối chiếu **26 commits thực tế từ git repository**:

| Mốc thời gian | Hash Git | Tác giả & Branch | Thông điệp Commit (Commit Message) | Nội dung công việc thực tế được ghi nhận |
| :---: | :---: | :--- | :--- | :--- |
| **Mốc 1: Khởi tạo & Phân tích UX Brief**<br>*(12/10 – 16/10)* | `97f5b79` | Thái An (`main`) | `Initated` | Khởi tạo cấu trúc dự án Longvita. |
|  | `e2d6a08` | Thái An (`main`) | `docs(ux): update persona and user flows` | Xác lập chân dung Persona Minh Anh, mục tiêu, rào cản và 3 user flows sơ bộ. |
|  | `f45a5dc` | Thái An (`main`) | `docs(design): add organic biomorphic design system tokens` | Thiết lập bộ Design Tokens khởi đầu theo phong cách Organic Biomorphic. |
|  | `9482e81` | Thái An (`main`) | `docs: sync user flows with screen inventory, add task sequence and stitch assets` | Đồng bộ 10 màn hình `S01`–`S10`, quy trình thực hiện dự án và nạp ảnh Stitch ban đầu. |
| **Mốc 2: AI Generation, Critique & Spec Draft**<br>*(18/10 – 19/10)* | `f641603` | Thắng VLQ (`Task_4`) | `docs: add Task 4 screen specs and Flutter handoff` | Khởi tạo khung tài liệu Screen Specifications và Flutter Handoff. |
|  | `57d1584` | Thái An (`main`) | `docs(design): document 3 AI design iterations, design decisions, and stitch assets` | Ghi chép 3 vòng lặp AI (I01–I03), 9 phát hiện phản biện UX/Accessibility và bảng Design Decisions (D01–D07). |
| **Mốc 3: Design System, Final UI & Prototype**<br>*(21/10)* | `d6dfb95` | CharlieMinh (`member-2/lab2-demo-finalization`) | `docs(design): finalize Member2 foundations and component demo` | Hoàn thiện hệ thống Tokens (64 Variables trên Page 04) và 9 nhóm Components (Page 05). |
|  | `59ed263` | Hoàng DV (`member3-ui`) | `docs: add member 3 UI design spec` | Đặc tả chi tiết triển khai UI cho Thành viên 3. |
|  | `d730cca` | Hoàng DV (`member3-ui`) | `docs: add member 3 UI implementation plan` | Kế hoạch vẽ Wireframe, Final UI và nối Prototype. |
|  | `1508010` | Hoàng DV (`member3-ui`) | `chore: ignore local worktrees` | Cấu hình git bỏ qua thư mục tạm. |
|  | `609c430` | Hoàng DV (`member3-ui`) | `design: normalize Longvita mobile tokens` | Chuẩn hóa bán kính bo góc `4/8/12/16/full`, chỉnh mã màu Action `#476429` (Quyết định D08). |
|  | `566ea73` | Hoàng DV (`member3-ui`) | `docs: record member 3 UI QA evidence` | Kiểm tra giới hạn biên bố cục ở `360x800 dp` và `412x915 dp` (Pass 10/10 màn hình). |
|  | `7d4773f` | Hoàng DV (`member3-ui`) | `design: complete member 3 final UI and prototype evidence` | Xuất 10 PNG Final UI, hoàn tất checklist tương phản, vùng chạm và nối dây Prototype. |
|  | `40dd92a` | Hoàng DV (`member3-ui`) | `fix: resolve final member 3 UI review findings` | Sửa các lỗi khoảng cách và căn lề theo kết quả review. |
|  | `1a64b10` | Hoàng DV (`member3-ui`) | `fix: polish member 3 mobile layouts` | Tinh chỉnh độ cân bằng thị giác trên các thẻ món ăn. |
|  | `ac0489c` | Hoàng DV (`member3-ui`) | `fix: refine member 3 layout balance` | Chuẩn hóa lề trang 16dp và thanh điều hướng đáy. |
|  | `ab8ae49` | Hoàng DV (`member3-ui`) | `chore: clean member 3 handoff diff` | Dọn dẹp nhánh chuẩn bị merge. |
|  | `838aa31` | Thái An (`main`) | `docs(ux): add secondary persona and update project README overview` | Bổ sung Persona phụ Bác Hoàng (67 tuổi) vào `persona.md` và cập nhật README. |
|  | `d7e06fb` | Thái An (`main`) | `Merge branch 'member-2/lab2-demo-finalization' into main` | Hợp nhất gói Design System & Components của Thành viên 2 vào nhánh chính. |
| **Mốc 4: Handoff Integration & Verification**<br>*(21/10)* | `f1343ac` | Thắng VLQ (`Task_4`) | `docs: validate final UI handoff evidence` | Đối chiếu bằng chứng Final UI thực tế vào tài liệu handoff. |
|  | `fdf0264` | Thắng VLQ (`Task_4`) | `Merge remote-tracking branch 'origin/main' into Task_4` | Đồng bộ dữ liệu mới nhất từ main vào nhánh Task 4. |
|  | `bfb55e8` | Thắng VLQ (`Task_4`) | `docs: record Task 4 integration evidence` | Ghi nhận bằng chứng tích hợp giữa Figma và mã nguồn. |
|  | `08c2928` | Thắng VLQ (`Task_4`) | `docs: apply verified design evidence to Task 4` | Cập nhật 6 mục đặc tả cho 10 màn hình dựa trên 2.699 nodes đã phân tích từ file `.fig`. |
|  | `ad65e3d` | Thái An (`main`) | `Merge branch 'origin/member3-ui' into main (resolve DESIGN.md)` | Hợp nhất gói UI & Prototype của Thành viên 3 vào nhánh chính. |
|  | `1d38bae` | Thái An (`main`) | `Merge remote-tracking branch 'origin/Task_4'` | Hợp nhất gói Handoff & Spec của Thành viên 4 vào nhánh chính. |
| **Mốc 5: Prototype Recovery & Nghiệm thu**<br>*(22/10)* | `8b2b6b9` | Hoàng DV (`member3-prototype-fixes`) | `docs: record prototype recovery decisions` | Cập nhật quyết định nối recovery path cho Prototype (loại bỏ toàn bộ dead ends). |

---

## 5. Checklist Kỹ Thuật Tự Kiểm Tra (Mục 4 Guideline)

| Tiêu chuẩn kỹ thuật kiểm tra | Trạng thái đạt được trên Longvita | Bằng chứng kiểm tra |
| :--- | :---: | :--- |
| **Tối thiểu 8 màn hình cuối; 3 flows có nhánh lỗi/phục hồi** | **ĐẠT (10/8 màn)** | Đủ 10 màn hình `S01`–`S10`; cả 3 flows đều có starting points, nút Back và nhánh lỗi có đường phục hồi. |
| **AI log giữ prompt nguyên văn, $\ge 3$ vòng lặp Before/After, $\ge 5$ critique findings** | **ĐẠT** | `ai/ai-design-log.md` lưu prompt gốc, 9 phát hiện UX critique, 3 vòng lặp tinh chỉnh Before/After đầy đủ ảnh. |
| **Design System có Tokens & đủ 9 nhóm Component chuẩn** | **ĐẠT (9/9 nhóm)** | 64 Figma Variables trên Page 04; 9 nhóm Components có Auto Layout, State Variants trên Page 05. |
| **Accessibility: Contrast $\ge 4.5:1$, Hitbox $\ge 48\text{dp}$, Text $\ge 14\text{sp}$, test 360/412dp** | **ĐẠT** | Tương phản chữ 10.48:1, hitbox 48–64dp, font $\ge 14\text{sp}$, 10 bản responsive 412dp không bị vỡ layout. |
| **Flutter handoff đủ 6 mục/màn hình và 2 bảng mapping** | **ĐẠT** | `handoff/flutter-handoff.md` mô tả 6 trường cho 10 màn hình; 2 bảng ánh xạ Tokens và Components chi tiết. |
| **Figma public link truy cập được; README ghi đủ artefacts** | **ĐẠT** | Link Figma mở chế độ xem công khai (đã test Incognito); README đầy đủ deliverable map; không yêu cầu code Flutter. |
