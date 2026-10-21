---
version: "1.0-lab2"
name: "Longvita — Organic / Biomorphic Mobile"
platform: "Flutter Mobile — design handoff"
theme: "Light"
description: "Organic / Biomorphic visual system, translated from the Claude Artisan catalog for use in digital products. Flowing curves and asymmetric blobs; Soft natural palettes"
colors:
  primary: "#476429"
  primary-soft: "#6f8f4e"
  background: "#f6f1e7"
  surface: "#ffffff"
  text: "#2f3b2a"
  text-muted: "#5c6b53"
  border-control: "#74796c"
  accent: "#d98b5f"
  on-primary: "#ffffff"
  on-surface: "#2f3b2a"
  on-accent: "#2f3b2a"
typography:
  h1:
    fontFamily: "'Fraunces', Georgia, serif"
    fontSize: "4rem"
    fontWeight: "700"
    lineHeight: "1.05"
  body-md:
    fontFamily: "'Quicksand', 'Nunito', system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: "400"
    lineHeight: "1.6"
  label-caps:
    fontFamily: "'Quicksand', 'Nunito', system-ui, sans-serif"
    fontSize: "0.75rem"
    fontWeight: "600"
    letterSpacing: "0.06em"
rounded:
  xs: "4px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  full: "9999px"
spacing:
  sm: "8px"
  md: "16px"
  lg: "32px"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.md}"
    padding: "16px"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    rounded: "{rounded.md}"
    borderColor: "{colors.border-control}"
    padding: "16px"
  card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: "16px"
  page:
    backgroundColor: "{colors.background}"
    textColor: "{colors.text}"
    padding: "16px"
---

# Longvita Design System — Organic / Biomorphic

Thư viện thiết kế UI/UX trên Figma được chuẩn hóa từ các màn hình nền tảng, bao gồm Foundations (Page 04) và 9 nhóm Components bắt buộc (Page 05) để áp dụng xuyên suốt 10 màn hình Final UI (`S01`–`S10`).

- [Page 04 — Design System](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=53-2)
- [Page 05 — Component Catalog](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=58-153)
- [Mẫu ghép 360/412](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=58-711)

**Đặc trưng nhận diện:**
- Bảng màu organic ấm áp, bố cục biên tập (editorial hierarchy).
- Đường nét tự nhiên, bo góc mềm mại nhưng có kỷ luật hình học để phân cấp tác vụ.
- Thiết kế tối ưu cho trải nghiệm di động một tay, đạt chuẩn tương phản tiếp cận WCAG AA/AAA.

---

## 1. Màu sắc & Độ tương phản (Colors & Accessibility)

- **bg** — `#f6f1e7` (Nền trang / Canvas)
- **surface** — `#ffffff` (Nền thẻ card)
- **surface-strong** — `#eee6d6` (Nền thẻ phụ / Container)
- **border/decorative** — `#dccdb0` (Đường kẻ phân cách trang trí)
- **border/control** — `#74796c` (Đường viền ô nhập text field)
- **text** — `#2f3b2a` (Chữ chính)
- **text-muted** — `#5c6b53` (Chữ phụ)
- **primary/action** — `#476429` (Nút hành động chính)
- **primary/soft** — `#6f8f4e` (Màu xanh nhận diện thương hiệu)
- **accent** — `#d98b5f` (Điểm nhấn cam ấm)
- **clay** — `#e7c9a9` (Màu đất ấm)

**Tỷ lệ tương phản kiểm tra theo chuẩn WCAG:**
- Chữ trắng trên `#476429`: **6.72:1** (vượt chuẩn WCAG AA $\ge 4.5:1$ cho nhãn nút bấm).
- Chữ chính `#2F3B2A` trên nền `#F6F1E7`: **10.48:1** (đạt chuẩn WCAG AAA).
- Chữ phụ `#5C6B53` trên nền `#F6F1E7`: **5.06:1** (đạt chuẩn WCAG AA).
- Viền control `#74796C` trên nền `#F6F1E7`: **3.97:1** (vượt chuẩn $\ge 3:1$ cho UI Controls).

---

## 2. Foundations (Page 04)

Hệ thống biến (Variables) và Styles gồm 64 variables chia làm 3 collections (Primitives, Color, Metrics) lưu tại [`design-system-tokens.json`](design-system-tokens.json).

### Typography Styles:
| Text Style | Font / weight | Size / line height |
|---|---|---|
| Longvita/Brand | Fraunces Bold | 20 / 28 |
| Longvita/Heading/L | Newsreader Bold | 28 / 36 |
| Longvita/Heading/M | Newsreader SemiBold | 24 / 32 |
| Longvita/Title | Newsreader SemiBold | 20 / 28 |
| Longvita/Body | Quicksand Regular | 16 / 26 |
| Longvita/Supporting | Quicksand Medium | 14 / 22 |
| Longvita/Label | Quicksand SemiBold | 14 / 20 |
| Longvita/Label/Strong | Quicksand Bold | 14 / 20 |

### Spacing, Radius & Elevation:
- **Spacing:** 4, 8, 12, 16, 24, 32, 48 dp. Margin trang chuẩn 16dp, padding thẻ 16–24dp.
- **Radius scale:** 4px (xs), 8px (sm), 12px (md), 16px (lg), full (9999px). Controls dùng 8–12px, cards chuẩn 12px, dialogs 16px; full/pill dành riêng cho status chips/tags.
- **Elevation:**
  - **Level 0:** Phẳng (ưu tiên dùng viền `#74796C` và khoảng trắng).
  - **Level 1:** Shadow `0/1 blur 3 alpha 0.08` (cho card hoặc action nổi).
  - **Level 2:** Shadow `0/4 blur 16 alpha 0.12` (cho Dialog và Overlays).
- **Vùng chạm (Hitbox):** Mọi thành phần tương tác giữ tối thiểu $\ge 48\times 48\text{ dp}$. Nút Primary cao thực tế 56dp khi có icon.

---

## 3. Danh mục 9 nhóm Component bắt buộc (Page 05)

Tất cả component được xây dựng hoàn chỉnh bằng Auto Layout và Variants trên Figma Page 05:

| Nhóm bắt buộc | Variants chính | Số lượng |
|---|---|---:|
| **Button** | Primary / Secondary / Destructive × Default / Pressed / Disabled / Loading | 12 |
| **TextField** | Default / Focused / Filled / Error / Disabled | 5 |
| **Card** | Meal / Summary × Default / Pressed | 4 |
| **Navigation** | Home / Plan / Nutrition / Profile selected | 4 |
| **AppBar** | Default / WithActions | 2 |
| **Dialog** | Confirmation / Destructive / Error / Edit / EditError | 5 |
| **Loading** | Spinner / Skeleton | 2 |
| **Empty** | NoPlan / NoIngredients / NoAlternatives | 3 |
| **Error** | Generation / Save / Update | 3 |

**Tổng cộng:** **9 nhóm, 40 variants** chuẩn theo yêu cầu bài Lab. Các thành phần hỗ trợ bao gồm: IconButton, Badge, NavigationItem, DaySelector, CheckboxRow, Snackbar, QuantityStepper.
