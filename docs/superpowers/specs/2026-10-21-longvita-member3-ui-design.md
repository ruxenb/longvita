# Longvita — Member 3 UI Designer & Prototyper Design Spec

**Ngày:** 21/10/2026  
**Phạm vi:** Thành viên 3 — UI Designer & Prototyper  
**Dự án:** PRM393 / Longvita  
**Figma:** `73GTcipwH825N7l501or8D`

## 1. Mục tiêu

Hoàn thiện toàn bộ phần việc Thành viên 3 theo rubric: Wireframe S01–S10, Final UI S01–S10, trạng thái Loading/Empty/Error/Dialog, responsive 360dp/412dp, accessibility, ba prototype flows và PNG exports. Thiết kế phải giữ DNA tốt từ Stitch nhưng loại bỏ cảm giác AI-generated do bo góc quá mức, mật độ card cao và pill sử dụng tràn lan.

Kết quả cuối phải đủ rõ để trình bày trực tiếp trước giảng viên, đủ nhất quán để Thành viên 4 handoff sang Flutter, và đủ chặt chẽ để các màn hình không tạo dead-end trong prototype.

## 2. Hiện trạng đã xác minh

- `02 Wireframe`: đang trống.
- `03 Final UI`: đang trống.
- `06 Prototype`: đang trống.
- `04 Design System`: đã có foundations, màu, typography, spacing, radius, elevation và responsive QA mẫu.
- `05 Components`: đã có bộ component đầy đủ gồm Button, TextField, Card, Navigation, AppBar, Dialog, Loading, Empty, Error, Badge, DaySelector, CheckboxRow, Snackbar, QuantityStepper và icon set.
- Stitch assets v0–v3 đã nằm trong `assets/stitch/`; v2/v3 là nguồn remix chính.
- User flow chính thức sử dụng 10 màn hình S01–S10 và ba flow trong `ux/user-flow.md`.

## 3. Hướng thiết kế được duyệt

Sử dụng phương án **Stitch remix → Figma-native**.

Không sao chép nguyên trạng Stitch. Giữ lại bảng màu, cảm giác organic, typography định hướng wellness và các pattern tốt; tái cấu trúc bằng Figma Auto Layout, components và tokens để tạo một sản phẩm mobile thực tế hơn.

Phong cách đích: **Organic Editorial / Mediterranean Modern**.

Đặc tính:
- Ấm, tự nhiên, chuyên nghiệp, không mang cảm giác template AI.
- Nội dung và hierarchy quan trọng hơn trang trí.
- Hình ảnh món ăn có vai trò hỗ trợ, không chiếm lấn CTA.
- Ít shadow; ưu tiên border, spacing và typography để phân tầng.
- Không dùng emoji trong UI hoặc tài liệu Member 3.

## 4. Quy tắc hình học và anti-AI-look

Hệ radius mới cho Final UI:
- `radius/4`: indicator nhỏ hoặc chi tiết phụ.
- `radius/8`: input, control nhỏ, compact container.
- `radius/12`: card chuẩn, button, list item.
- `radius/16`: card đặc biệt hoặc modal nội dung lớn.
- `radius/full`: chỉ dùng cho chip/status/segmented control thật sự cần dạng pill.

Không sử dụng 28px, 32px hoặc 44px làm radius mặc định cho card. Không dùng pill cho mọi button. Không bọc từng cụm thông tin vào card nếu grouping bằng spacing/divider là đủ.

Elevation:
- Level 0 là mặc định.
- Level 1 chỉ dùng cho card cần tách khỏi background.
- Level 2 chỉ dùng dialog/overlay hoặc phần nổi thực sự.

## 5. Hệ màu và accessibility

Giữ các màu nền tảng hiện có khi đạt chuẩn:
- Canvas: `#F6F1E7`
- Surface: `#FFFFFF`
- Text primary: `#2F3B2A`
- Text secondary: `#5C6B53`
- Error: `#BA1A1A`

Primary action phải sử dụng cặp màu đạt contrast cho text/control. Không dùng white text trên `#6F8F4E` cho body-size label nếu không đạt 4.5:1. Primary có thể chuyển sang green đậm đã có trong Figma (`#476429`) hoặc dùng text tối phù hợp nếu giữ nền nhạt.

Functional border không dùng `#DCCDB0` làm tín hiệu duy nhất. Dùng border/control đủ tương phản, hiện đang có `#74796C` trong Page 04.

Tiêu chuẩn bắt buộc:
- Normal text contrast >= 4.5:1.
- Large text / graphical control contrast >= 3:1.
- Touch target >= 48x48dp.
- Body text >= 14sp; nội dung chính ưu tiên 16sp.
- Không biểu đạt trạng thái chỉ bằng màu; luôn có icon hoặc text label đi kèm.

## 6. Screen-by-screen design contract

### S01 — Home
Mục tiêu: đưa tác vụ tạo kế hoạch tuần lên trước, giảm dashboard clutter. Giữ greeting, một summary hữu ích và CTA chính. Secondary modules phải có priority thấp hơn CTA.

### S02 — Food Preferences
Mục tiêu: form ngắn, scan nhanh. Nhóm Age, Weight, Meals/day và eating window theo section rõ ràng. Editable field và calculated value phải phân biệt thị giác.

### S03 — Create Meal Plan
Mục tiêu: xác nhận cấu hình trước khi generate. Dùng ba vùng: Essential preferences, Optional nutrition settings, Review & Generate. Có Loading và Generation Error state.

### S04 — Weekly Meal Plan
Mục tiêu: xem kế hoạch 7 ngày nhưng không tạo một feed quá dài khó hiểu. Có day selector, meal cards, Save Plan và đường dẫn rõ sang Ingredient Summary/Shopping flow. Có Save Error state.

### S05 — Recipe Details
Mục tiêu: đọc nhanh trong lúc nấu. Thứ tự ưu tiên: ảnh/tên món → source provenance → serving/protein → ingredients → steps → Replace Meal. Steps đánh số rõ, không phụ thuộc decorative cards.

### S06 — Meal Alternatives
Mục tiêu: so sánh lựa chọn thay thế nhanh. Mỗi alternative nêu lý do phù hợp, source badge và action chọn. Có No Alternatives và Update Error state; lỗi không được làm mất món gốc.

### S07 — Ingredient Summary
Mục tiêu: tổng hợp nguyên liệu theo category, chỉnh quantity nhanh. Có Edit Ingredient Dialog dạng Overlay, Validation Error, Empty State và Undo snackbar.

### S08 — Shopping List
Mục tiêu: sử dụng một tay khi đi siêu thị. Checkbox rows tối thiểu 48dp, category grouping rõ, trạng thái purchased có text/icon ngoài màu sắc.

### S09 — Book Knowledge
Mục tiêu: giải thích nguyên tắc từ sách mà không biến màn hình thành bài viết dài. Sử dụng section headings, source/citation block và các principle cards/rows tiết chế.

### S10 — Saved Plans
Mục tiêu: xem và mở lại kế hoạch đã lưu. List/card density vừa phải, metadata thiết yếu, Empty State rõ và CTA quay về tạo plan.

## 7. Wireframe contract — Page 02

Tạo đủ 10 frame `360x800` với tên:
`S01 Home`, `S02 Food Preferences`, `S03 Create Meal Plan`, `S04 Weekly Meal Plan`, `S05 Recipe Details`, `S06 Meal Alternatives`, `S07 Ingredient Summary`, `S08 Shopping List`, `S09 Book Knowledge`, `S10 Saved Plans`.

Wireframe chỉ dùng grayscale, hierarchy, spacing và layout. Không dùng ảnh food thật hoặc decoration. Mỗi frame phải cho thấy app bar/navigation khi có, CTA chính, content hierarchy và vị trí các state/overlay liên quan.

## 8. Final UI contract — Page 03

Mỗi màn hình có master frame 360x800. Các state variant đặt ngay bên phải màn hình gốc với naming rõ ràng, không tính vào 10 screen count.

Bố cục Page 03 chia thành ba cụm đúng user flows:
- Flow 1: S01, S02, S03, S04, S10.
- Flow 2: S07, S08.
- Flow 3: S05, S06, S09.

Các state bắt buộc:
- S03 Loading.
- S03 Generation Error.
- S04 Save Error.
- S06 No Alternatives.
- S06 Update Error.
- S07 Empty Ingredients.
- S07 Edit Ingredient Dialog.
- S07 Dialog Validation Error.
- S07 Undo Snackbar.

## 9. Responsive behavior

Master design ở 360dp. Kiểm tra 412dp bằng Auto Layout / Fill container, không scale toàn bộ frame.

Tại 412dp:
- Horizontal padding có thể tăng nhẹ nhưng hierarchy không đổi.
- Card/list fill width thay vì giữ fixed 328px.
- Text phải wrap tự nhiên, không truncate nội dung quan trọng.
- CTA vẫn đủ rộng và touch target không giảm.

Màn >=600dp thuộc handoff của Member 4; Member 3 chỉ cần đảm bảo cấu trúc component/layout không cản trở adaptive layout về sau.

## 10. Prototype contract — Page 06

Prototype phải có ba Flow Starting Points.

Flow 1: `S01 → S02 (khi cần) → S03 → Loading → S04 → Save → S10`.
- Generation Error: Retry quay về loading; Edit Preferences về S02; Cancel về Home.
- Save Error: Retry giữ nguyên generated plan.

Flow 2: `S04 → S07 → S08`.
- Edit ingredient mở Overlay trên S07.
- Invalid quantity giữ dialog mở và hiển thị lỗi.
- Remove hiển thị Undo snackbar.
- Empty state có đường về S04.

Flow 3: `S04 → S05 → S09 → S05 → S06 → S04`.
- No alternatives dẫn về S02 hoặc giữ món gốc.
- Update error có Retry/Cancel và không mất original meal.

Tất cả nút Back phải hoạt động đúng. Không có dead-end.

## 11. Figma implementation rules

- Reuse component instances from Page 05; không detach nếu không thật sự cần.
- Sửa component master/tokens trước khi sửa hàng loạt screen instance.
- Auto Layout cho container chính, section, list và button groups.
- Layer naming có cấu trúc; tránh `Frame 123`, `Rectangle 45` ở các phần quan trọng.
- Không hard-code màu mới trong từng screen nếu token hiện có hoặc token mới có thể dùng lại.
- Không thay đổi nội dung nghiệp vụ cốt lõi từ `ux/user-flow.md`.
- Không sửa phần Task 4/handoff ngoài những cập nhật cần thiết để phản ánh output Member 3.

## 12. Thứ tự triển khai

1. Tinh chỉnh Page 04 radius/contrast rules để loại excessive rounding.
2. Tinh chỉnh Page 05 component masters tương ứng.
3. Dựng 10 low-fidelity wireframes trên Page 02.
4. Dựng 10 master Final UI screens trên Page 03.
5. Dựng các Loading/Empty/Error/Dialog/Snackbar states.
6. Kiểm tra 360dp và 412dp.
7. Chạy accessibility QA: contrast, touch target, body size, non-color cues.
8. Dựng Page 06 và nối ba prototype flows.
9. Kiểm tra Back, overlay, recovery paths và Loading → Result.
10. Export PNG final screens vào `assets/figma/`.
11. Cập nhật evidence/worklog của Member 3 và commit GitHub theo output thật.

## 13. Acceptance criteria

Công việc Member 3 chỉ được xem là hoàn tất khi:
- Có đúng 10 wireframe độc lập S01–S10.
- Có đúng 10 Final UI độc lập S01–S10.
- Tất cả state bắt buộc tồn tại cạnh parent screen.
- Không còn excessive rounding/pill-everywhere từ Stitch.
- 360dp không overflow; 412dp không bị scale giả.
- Contrast và touch target đạt ngưỡng rubric.
- Ba prototype flows chạy từ đầu đến cuối.
- S07 Dialog là overlay thực tế.
- S03 Loading chuyển tới S04 Result.
- Tất cả Back/recovery paths hoạt động; không dead-end.
- Final PNG của S01–S10 đã được export vào repo.
- Figma page/layer naming đủ rõ để live demo.
- Không sử dụng Claude hoặc Codex trong phần việc này.

## 14. Ngoài phạm vi Member 3

Không xây backend, không triển khai Flutter production, không thay đổi nghiệp vụ dinh dưỡng ngoài tài liệu đã chốt, không viết lại phần handoff của Member 4, và không tạo feature mới ngoài rubric chỉ để làm UI phong phú hơn.

## 15. Trạng thái truy cập

Ngày 21/10/2026 đã xác minh Figma connector đăng nhập bằng `hoangdvse183095@fpt.edu.vn` và đọc được file `Longvita - UI UX Design` cùng đủ 6 pages. Quyền ghi sẽ được xác minh ở bước implementation đầu tiên trước khi thực hiện thay đổi lớn.
