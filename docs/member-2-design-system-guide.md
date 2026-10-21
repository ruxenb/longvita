# Member 2 — sử dụng và demo thư viện Longvita

Member 2 chuyển các quy tắc lặp trong ba màn Stitch S01/S03/S04 thành **foundations** (màu, chữ, spacing, radius, elevation) và **components** có thể dùng lại. Đây là phần nền tảng UI/UX Lab 2, chưa phải ứng dụng Flutter chạy được.

## Ba điểm mở trực tiếp

1. [Page 04 — Foundations](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=53-2): màu, 8 Text Styles, spacing/radius và 3 Effect Styles.
2. [Page 05 — Component Catalog](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=58-153):9 nhóm bắt buộc,40 variants; các mẫu là instances.
3. [Mẫu tiếng Việt 360/412](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=58-711): minh họa ghép component ở hai chiều rộng, chưa tính là màn Final UI mới.

Chi tiết quy chuẩn: [DESIGN.md](../design/DESIGN.md). Nguồn gốc: [ZIP leader đã giải nén](../assets/stitch/leader-export/).

## Demo Member 2 khoảng 60–90 giây, không chỉnh file nguồn

| Bước | Thao tác đọc trên Figma | Nội dung trình bày |
|---|---|---|
| 1 | Mở Page 04, zoom màu và typography | Màu olive/kem và font lấy từ HTML Stitch; dùng Variables/Styles để nhất quán |
| 2 | Mở Page 05, chỉ9 mục catalog | Button, TextField, Card, Navigation, AppBar, Dialog, Loading, Empty, Error; có40 variants |
| 3 | Chọn [Button Primary/Default](https://www.figma.com/design/73GTcipwH825N7l501or8D/Longvita---UI-UX-Design?node-id=58-165) | Chỉ Label, Emphasis, State, Icon/Show icon trong panel; xem các mẫu trạng thái nằm cạnh nhau, không đổi giá trị |
| 4 | Dùng Go to main component; xem panel Auto Layout và fill variable | Main component quy định cấu trúc; instance dùng lại và cho phép override nội dung |
| 5 | Mở mẫu 360/412 | Chỉ tên món tiếng Việt, error message xuống dòng, Button và Navigation |

Nếu cần biểu diễn đổi property thật, chuẩn bị một instance thử trong vùng làm việc được nhóm cho phép trước buổi demo; lượt chốt này không tạo thêm sandbox hoặc sửa file Figma chính. Không đổi token trực tiếp chỉ để trình diễn.

![Component assembly 360/412](../assets/figma/design-system/responsive.png)

## Member 3 dùng components thế nào?

- Dùng Assets hoặc copy instance từ Catalog sang màn hình trong cùng file.
- Button: chọn Emphasis/State phù hợp, sửa Label; Card: Title/Description; TextField: Label/Value/Unit/Helper text.
- TextField/Error có text layer `Error message`; Dialog/Empty/Error có nội dung theo Kind và có thể override text theo ngữ cảnh.
- Không detach để sửa nhãn; không kéo PNG vào thay cho component; không đổi màu/font lẻ ở mỗi màn.
- Muốn xem cấu trúc, dùng Go to main component. Muốn sửa quy chuẩn, trao đổi với Member 2 trước khi chỉnh master.

## Những điều cần nói đúng khi bàn giao

- File chính là link ở trên. Fix riêng `size/button/min-height = 56` trong sandbox **chưa được đưa vào file chính**. Demo hiện tại dùng Button có icon; không khẳng định tắt icon luôn giữ 56.
- Loading/Empty/Error là các trạng thái thiết kế, không phải API đang chạy. Chưa kết luận mọi thao tác chuyển State/Emphasis/icon đã PASS tương tác.
- JSON token là snapshot 20/10; kiểm tra giá trị đang bind trong Figma khi có khác biệt. Page 04 hiện có mẫu radius 4/8/12/16/full, khác danh mục radius trong snapshot cũ.
- Profile trong navigation là nhãn từ nguồn Stitch; màn riêng và nội dung sách do nhóm thống nhất. Full Final UI, prototype flows và Flutter handoff thuộc các phần việc tiếp theo.
- Kiểm tra nhanh 21/10 thấy đủ thành phần và không có lỗi hiển thị rõ ràng cản demo Member 2. Leader cần thử link bằng quyền xem của giảng viên; lượt này chưa kiểm tra truy cập ẩn danh.

## Lời trình bày gợi ý

> Em phụ trách nền tảng thiết kế của Longvita. Từ ba màn Google Stitch, em trích màu, font và khoảng cách để tạo Variables/Styles ở Page 04. Page 05 có 9 nhóm component với 40 variants. Các mẫu ở đây là instances của component gốc, giúp nhóm ghép màn hình nhất quán. Mẫu 360 và 412 minh họa nội dung tiếng Việt và các trạng thái lỗi. Phần này là thư viện thiết kế để bàn giao cho bạn dựng Final UI, chưa phải Flutter implementation.
