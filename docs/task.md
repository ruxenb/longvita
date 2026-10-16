Bảng phân công dưới đây bao phủ toàn bộ khối lượng công việc còn lại của bài **Lab 2 môn PRM323** (từ lúc đã có `persona.md`, `user-flow.md`, `DESIGN.md` cho đến khi hoàn thiện GitHub, Figma và bảo vệ trước giảng viên). Mặc định bài Lab là bài tập cá nhân trừ khi giảng viên cho phép làm nhóm, nhưng dù bạn làm theo nhóm (2–4 thành viên) hay làm cá nhân chia theo từng giai đoạn, cấu trúc chia gói công việc này sẽ giúp kiểm soát chặt chẽ lịch sử commit trên GitHub và lịch sử phiên bản trên Figma.

---

## 1. Phân công theo 4 Gói công việc chuyên trách (Work Packages)

Nếu nhóm có **4 thành viên**, mỗi người nhận 1 gói; nếu nhóm có **2–3 thành viên**, có thể gộp Gói 1 với Gói 4; nếu làm **cá nhân**, bạn thực hiện lần lượt từ Gói 1 đến Gói 4 theo từng ngày để tạo lịch sử commit tự nhiên.

| Gói công việc / Vai trò | Đầu mục công việc cụ thể | File GitHub & Figma phụ trách | Điểm số trong Rubric |
| --- | --- | --- | --- |
| **Thành viên 1: UX & AI Prompt Lead** (Phụ trách Analyze, Generate, Critique) | • Hoàn thiện và chuẩn hóa `persona.md`, `user-flow.md`. | `ux/persona.md`, `ux/user-flow.md` | **40 điểm tổng** (UX & Flows: 15đ; AI Generation: 10đ; AI Iterations & Critique: 15đ) |
|  | • Vẽ sơ đồ 3 User Flows trên **Figma Page 01** và nối link tới từng màn hình tương ứng. | **Figma Page 01: User Flow** |  |
|  | • Chạy prompt đầu tiên trên **Google Stitch**, chụp màn hình lưu vào `assets/stitch/`. | `assets/stitch/` |  |
|  | • Thực hiện **ít nhất 3 lần chỉnh sửa (Iterations)** trên Stitch nhắm vào 3 lỗi UX cụ thể, chụp ảnh Before/After. | `assets/stitch/`, `ai/ai-design-log.md` |  |
|  | • Dùng AI đánh giá giao diện (**AI Critique**) theo 10 nguyên tắc Nielsen Heuristics + Accessibility + Persona (ít nhất 5 phát hiện gắn với màn hình cụ thể). | `ai/ai-design-log.md` |  |
|  | • Ghi chép đầy đủ toàn bộ câu lệnh nguyên văn và lý do **Accept / Modify / Reject**. | `ai/ai-design-log.md`, `design/design-decisions.md` |  |
| **Thành viên 2: Design System & Component Architect** (Phụ trách nền tảng Figma) | • Quản lý quy chuẩn trong `design/DESIGN.md`. | `design/DESIGN.md` | **15 điểm tổng** (Design System & Components: 15đ) |
|  | • Thiết lập Design Tokens bằng **Figma Variables hoặc Styles**: Color, Typography, Spacing, Corner radius, Elevation trên **Figma Page 04**; không dùng mã màu/cỡ chữ hard-code. | **Figma Page 04: Design System** |  |
|  | • Xây dựng 9 loại Component bắt buộc bằng Auto Layout và Variants trên **Figma Page 05**, gắn với Tokens: `Button` (Default, Pressed, Disabled, Loading); `Text field` (Default, Focused, Filled, Error, Disabled); `Card` (Default, Pressed). | **Figma Page 05: Components** |  |
|  | • Tiếp tục xây dựng `Navigation` (Bottom bar với từng tab Selected), `App bar` (Default, With actions) và `Dialog` (Confirmation, Destructive/Error variant). |  |  |
|  | • Hoàn thiện `Loading state` (Skeleton hoặc Spinner cấp màn hình), `Empty state` (Icon/hình minh họa, thông điệp, 1 nút hành động) và `Error state` (Thông điệp, nguyên nhân dễ hiểu, nút Retry). |  |  |
| **Thành viên 3: UI Designer & Prototyper** (Phụ trách Refine & Prototype) | • Vẽ khung dây Low-fidelity cho toàn bộ 10 màn hình (`S01`–`S10`) trên **Figma Page 02**. | **Figma Page 02: Wireframe** | **30 điểm tổng** (Final UI/UX: 20đ; Interactive Prototype: 10đ) |
|  | • Thiết kế hoàn chỉnh 10 màn hình (`S01`–`S10`) ở kích thước `360x800 dp` trên **Figma Page 03**, đặt các biến thể trạng thái (Loading, Empty, Error, Dialog) ngay cạnh màn hình gốc. | **Figma Page 03: Final UI** |  |
|  | • Kiểm tra bố cục ở `360 dp` và `412 dp`; bảo đảm độ tương phản chữ thường `>= 4.5:1`, chữ lớn/control `>= 3:1`, vùng chạm `>= 48x48 dp`, cỡ chữ thân bài `>= 14 sp`. | **Figma Page 03: Final UI** |  |
|  | • Xuất toàn bộ màn hình hoàn chỉnh ra ảnh PNG lưu vào `assets/figma/`. | `assets/figma/` |  |
|  | • Nối dây tương tác cho cả 3 User Flows trên **Figma Page 06**; gắn Flow starting point, bảo đảm nút Back hoạt động đúng, có ít nhất 1 Dialog mở dạng Overlay và 1 chuyển cảnh từ Loading sang Result. | **Figma Page 06: Prototype** |  |
| **Thành viên 4: Technical Writer & Flutter Handoff Lead** (Phụ trách Handoff & Documentation) | • Viết đặc tả mục đích, nội dung hiển thị và luồng của từng màn hình (`S01`–`S10`) trong `design/screen-spec.md`. | `design/screen-spec.md` | **15 điểm tổng** (Flutter Handoff: 10đ; Documentation & AI Log: 5đ) |
|  | • Viết `handoff/flutter-handoff.md`, mô tả đủ 6 mục cho mỗi màn hình: Layout, Components, States, User interactions, Navigation, UI constraints; gồm cả hành vi trên màn hình rộng `>= 600 dp`. | `handoff/flutter-handoff.md` |  |
|  | • Lập 2 bảng ánh xạ toàn cục trong `flutter-handoff.md`: Tokens-to-Flutter (`ColorScheme`, `TextTheme`...) và Components-to-Widgets (ví dụ `Button` → `FilledButton`). | `handoff/flutter-handoff.md` |  |
|  | • Hoàn thiện `README.md` (chứa đề tài, 1 dòng Persona, link Figma đã mở quyền xem công khai, danh sách công cụ AI và sơ đồ dẫn tới các file). | `README.md` |  |

---

## 2. Phân chia chi tiết 10 Màn hình (`S01`–`S10`) khi vẽ Wireframe, Final UI & viết Handoff

Để tránh chồng chéo khi vẽ trên **Figma Page 02, Page 03** và khi viết đặc tả **Flutter Handoff**, chia 10 màn hình theo 3 cụm luồng (User Flows) như sau.

| Cụm luồng | Loại nội dung | Chi tiết |
| --- | --- | --- |
| **Cụm 1 (Flow 1 — Lập & Lưu thực đơn 7 ngày)** | Màn hình | `S01` — Home; `S02` — Food Preferences; `S03` — Create Meal Plan; `S04` — Weekly Meal Plan; `S10` — Saved Plans. |
|  | Nghiệp vụ sách | Chọn nhóm tuổi (`<65` hoặc `>=65`), nhập cân nặng để tự tính đạm (`0.8g/kg`), chọn 2 hoặc 3 bữa/ngày, đếm số bữa cá trong tuần (tối đa `2–3 bữa/tuần`), nhắc uống Multivitamin & Omega-3 mỗi 3 ngày. |
|  | Loading State | Trên `S03`/`S04`; nối dây hiệu ứng chuyển từ Loading sang `S04` Result. |
|  | Error States | Generation Error trên `S03` và Save Error trên `S04`; có nút Retry & Back. |
| **Cụm 2 (Flow 2 — Tổng hợp nguyên liệu & Đi chợ)** | Màn hình | `S07` — Ingredient Summary; `S08` — Shopping List. |
|  | Nghiệp vụ sách | Gom nhóm nguyên liệu theo Rau củ, Các loại đậu, Hạt (óc chó, hạnh nhân, hạt phỉ khoảng `30g/ngày`) và Dầu ô liu (khoảng 3 muỗng canh/ngày), Cá ít thủy ngân. Checkbox có kích thước `>= 48x48 dp` để Minh Anh bấm bằng một tay khi đi siêu thị. |
|  | Dialog & Validation | Edit Ingredient Dialog Overlay mở đè lên `S07`, kèm Validation Error khi nhập số lượng âm hoặc không hợp lệ. |
|  | Empty State & Undo | Empty State trên `S07` khi chưa có nguyên liệu nào và Snackbar Undo khi xóa nhầm nguyên liệu. |
| **Cụm 3 (Flow 3 — Tra cứu sách & Thay thế món ăn)** | Màn hình | `S05` — Recipe Details; `S06` — Meal Alternatives; `S09` — Book Knowledge. |
|  | Nghiệp vụ sách | Hiển thị định lượng nguyên liệu (nhân thêm 20% nếu là nam giới), đánh dấu bữa ăn chính chứa `>= 30g protein`. Phân biệt bằng Icon + Chữ giữa **"📖 Từ sách: Phụ lục A"** và **"✨ App gợi ý"**. Cho phép thay thế nguyên liệu tinh bột tương đương (pasta nguyên cám ↔ gạo hoang, lúa mạch, farro, gnocchi). |
|  | Empty / No-Alternative State | Trên `S06`, có nút dẫn về `S02` để nới lỏng bộ lọc. |
|  | Update Error State | Trên `S06`; giữ nguyên món gốc và cho phép Retry. |

---

## 3. Phân công Thuyết trình (12 Slides - 10 phút) & Live Demo (5 phút)

Theo tài liệu hướng dẫn chấm bảo vệ (`PRM323_Lab2_Presentation_Assessment_Guidelines_EN.pdf`), buổi đánh giá gồm **10 phút thuyết trình (10–12 slides) + 5 phút Live Demo + 5 phút Q&A**. Nếu làm nhóm, trách nhiệm nói cần được phân bổ rõ ràng như sau:

### A. Phân công trình bày 12 Slides (10 phút)

| Người trình bày | Slide | Tiêu đề Slide | Nội dung cốt lõi & Bằng chứng cần chiếu | Thời lượng |
| --- | --- | --- | --- | --- |
| **Người 1** (UX & AI Lead) | **Slide 01** | Project Overview | Tên app, đối tượng mục tiêu, bài toán thực tế từ sách *La dieta della longevità*, link GitHub & Figma. | 45 giây |
|  | **Slide 02** | Problem and Persona | Bối cảnh Minh Anh (28 tuổi), mục tiêu, rào cản, câu Problem Statement, tiêu chí đo lường (80% hoàn thành dưới 3 phút) từ `ux/persona.md`. | 45 giây |
|  | **Slide 03** | Information Architecture | Sơ đồ điều hướng và danh sách 10 màn hình độc lập (`S01`–`S10`) từ `ux/user-flow.md` & Figma Page 01. | 45 giây |
|  | **Slide 04** | Three User Flows | 3 luồng hoàn chỉnh từ đầu đến cuối, các nhánh rẽ thay thế, nhánh báo lỗi/phục hồi và bảng ánh xạ Flow-to-Screen. | 1 phút |
| **Người 2** (AI Critique & Design Decisions) | **Slide 05** | AI UI Generation | Câu prompt gốc nguyên văn (chứa Persona, Task, Platform, Constraints, Style từ `DESIGN.md`) và ảnh kết quả đầu tiên từ Google Stitch. | 45 giây |
|  | **Slide 06** | AI Iterations and UX Critique | 3 lần chỉnh sửa giải quyết 3 vấn đề cụ thể (ảnh Before/After) và 5+ phát hiện UX gắn với từng màn hình từ `ai/ai-design-log.md`. | 1 phút |
|  | **Slide 07** | Design Decisions | 3–5 ví dụ tiêu biểu về việc Chấp nhận (Accept), Sửa đổi (Modify) hoặc Từ chối (Reject) gợi ý của AI kèm lý do bảo vệ từ `design-decisions.md`. | 1 phút |
| **Người 3** (Design System & UI Lead) | **Slide 08** | Wireframes and Final UI | So sánh khung dây Low-fidelity (`Page 02`) với Final UI (`Page 03`), phân cấp thị giác, tính nhất quán và các trạng thái Empty/Loading/Error. | 1 phút |
|  | **Slide 09** | Design System and Components | Hệ thống Tokens (Color, Typography, Spacing, Radius, Elevation) bằng Variables/Styles (`Page 04`) và 9 nhóm Component có Variants (`Page 05`). | 1 phút |
|  | **Slide 10** | Accessibility and Responsiveness | Bằng chứng kiểm tra độ tương phản (`>= 4.5:1`), vùng chạm (`>= 48x48 dp`), cỡ chữ (`>= 14 sp`) và kiểm tra bố cục ở `360 dp` & `412 dp`. | 45 giây |
| **Người 4** (Prototype & Flutter Handoff Lead) | **Slide 11** | Interactive Prototype | Tổng quan 3 luồng chạy trên `Figma Page 06`, hành vi nút Back, Dialog Overlay (`S07`) và hiệu ứng chuyển Loading sang Result (`S03`→`S04`). | 45 giây |
|  | **Slide 12** | Flutter Handoff and Summary | 6 trường đặc tả cho mỗi màn hình, 2 bảng ánh xạ Token-to-Flutter & Component-to-Widget từ `flutter-handoff.md`, cùng các giới hạn hiện tại. | 45 giây |

### B. Kịch bản phối hợp Live Demonstration (7 bước bắt buộc trong 5 phút)

Trong 5 phút Live Demo, 1 người điều khiển chuột (Driver) và 1 người thuyết minh (Narrator) thực hiện đúng 7 bước theo thứ tự quy định của giảng viên:

1. **Bước 1 (30s):** Mở file Figma, chiếu lướt qua đủ 6 Pages theo đúng thứ tự: `01 User Flow`, `02 Wireframe`, `03 Final UI`, `04 Design System`, `05 Components`, `06 Prototype`.
2. **Bước 2 (30s):** Zoom vào `03 Final UI`, chỉ rõ 10 màn hình độc lập (`S01`–`S10`), giải thích các Dialog và State variants nằm cạnh màn hình chính không tính vào số lượng màn hình.
3. **Bước 3 (1p30s):** Bấm chạy trực tiếp cả 3 Prototype Flows từ điểm bắt đầu (Flow starting point) đến kết thúc; bấm vào nhánh lỗi (ví dụ nhập sai số lượng hoặc lỗi tạo thực đơn) để demo đường phục hồi (Recovery path), bấm nút Back và chứng minh không có đường cụt (No dead ends).
4. **Bước 4 (30s):** Chỉ rõ **Edit Ingredient Dialog** mở dưới dạng **Overlay** trên màn `S07` và hiệu ứng chuyển từ **Loading sang Result** khi bấm tạo thực đơn từ `S03` sang `S04`.
5. **Bước 5 (45s):** Mở `05 Components` và `03 Final UI`, click vào 1 Component để giảng viên thấy cấu trúc **Auto Layout**, các **Variants**, và bảng **Figma Variables/Styles** đang được gắn trực tiếp (không có mã màu hard-code).
6. **Bước 6 (30s):** Mở file `ai/ai-design-log.md` trên GitHub, truy vết 1 ví dụ cụ thể từ câu Prompt → kết quả Google Stitch → nhận xét Critique → quyết định chỉnh sửa → hình ảnh đã thay đổi tương ứng trên Figma.
7. **Bước 7 (45s):** Mở GitHub repository, chiếu cấu trúc thư mục chuẩn, mở `design/screen-spec.md` và `handoff/flutter-handoff.md` để chỉ rõ 6 mục đặc tả màn hình cùng 2 bảng ánh xạ sang Flutter.

---

## 4. Lịch trình Commit GitHub & Lưu Figma History (Đảm bảo Academic Integrity)

Mục 10 của đề bài Lab 2 quy định rõ: bài nộp sẽ bị nghi vấn nếu chỉ upload lên GitHub 1 lần vào phút cuối hoặc file Figma hoàn thành chỉ trong 1 lần lưu. Bạn cần tuân thủ lịch trình đẩy bài (Commit) rải đều theo từng mốc sau:

### Mốc 1 (Hôm nay — Giai đoạn Analyze & Brief)

- **GitHub:**
  - Commit 1: `Add primary persona in ux/persona.md`
  - Commit 2: `Add IA and 3 user flows in ux/user-flow.md`
  - Commit 3: `Add mobile design tokens and rules in design/DESIGN.md`
- **Figma:** Tạo file, lập sẵn 6 Pages đúng tên, đưa sơ đồ luồng vào `01 User Flow` và bấm **Save to Version History** lần 1.

### Mốc 2 (Ngày tiếp theo — Giai đoạn Generate & Critique)

- **GitHub:**
  - Commit 4: `Add initial Google Stitch prompt and screenshots in assets/stitch/`
  - Commit 5: `Record 3 AI iterations and Nielsen heuristic critique in ai/ai-design-log.md`
  - Commit 6: `Document top design decisions in design/design-decisions.md`

### Mốc 3 (Giai đoạn Wireframe & Design System trên Figma)

- **Figma:** Hoàn thành `04 Design System` (Variables/Styles) + `05 Components` (9 components) + `02 Wireframe` → bấm **Save to Version History** lần 2.
- **GitHub:** Commit 7: `Add screen specifications for S01-S10 in design/screen-spec.md`

### Mốc 4 (Giai đoạn Final UI & Prototype)

- **Figma:** Hoàn thành 10 màn hình trên `03 Final UI` (kiểm tra ở `360 dp` và `412 dp`) + nối dây `06 Prototype` → bấm **Save to Version History** lần 3.
- **GitHub:**
  - Commit 8: `Export final UI PNG screens to assets/figma/`
  - Commit 9: `Complete accessibility checklist in design/design-decisions.md`

### Mốc 5 (Giai đoạn Handoff & Kiểm tra cuối)

- **GitHub:**
  - Commit 10: `Add complete Flutter handoff spec and mapping tables in handoff/flutter-handoff.md`
  - Commit 11: `Update README.md with public Figma link, AI tools disclosure, and deliverable map`

**Kiểm tra bắt buộc:** Mở đường link Figma trong cửa sổ ẩn danh (Private/Incognito window) để chắc chắn giảng viên truy cập được. Nếu link bị khóa quyền truy cập, toàn bộ 55 điểm phần Figma có thể bị tính 0 điểm theo nội dung bạn cung cấp.
