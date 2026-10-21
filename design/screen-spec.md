# Screen Specifications

> Trạng thái: **Draft — Final UI structure verified; prototype recovery pending**
>
> Nguồn hiện có: `ux/persona.md`, `ux/user-flow.md`, `design/DESIGN.md` và `docs/task.md`.
>
> Cần đối chiếu lần cuối với Figma Page 03 và Page 06 trước khi đánh dấu hoàn tất.

## 1. Quy ước chung

- Nền tảng: ứng dụng Android, thiết kế chính ở `360 x 800 dp` và kiểm tra thêm ở `412 dp`.
- Với màn hình rộng `>= 600 dp`, giới hạn chiều rộng nội dung để giữ khả năng đọc; giá trị cụ thể chờ Final UI xác nhận.
- Vùng chạm tối thiểu: `48 x 48 dp`.
- Cỡ chữ nội dung tối thiểu: `14 sp`.
- Độ tương phản: chữ thường `>= 4.5:1`; chữ lớn và thành phần điều khiển `>= 3:1`.
- Không dùng màu sắc làm dấu hiệu duy nhất. Trạng thái phải có thêm icon, nhãn hoặc thông báo bằng chữ.
- Mọi trạng thái Loading, Empty và Error phải có thông báo dễ hiểu cùng hành động tiếp theo.
- Nút Back phải đưa người dùng về bước hợp lý mà không làm mất dữ liệu đã nhập nếu không cần thiết.

## 2. Screen inventory

### S01 — Home

**Mục đích:** Điểm vào chính để người dùng tạo thực đơn, mở kế hoạch đã lưu, danh sách mua sắm hoặc kiến thức từ sách.

**Nội dung hiển thị:**

- Lời chào và mô tả ngắn giá trị của Longvita.
- Hành động chính `Create Meal Plan`.
- Lối vào `Saved Plans`, `Shopping List` và `Book Knowledge`.
- Bottom navigation hoặc navigation tương đương theo Final UI.

**Tương tác và điều hướng:**

- `Create Meal Plan` → `S03`; nếu chưa có thiết lập phù hợp, chuyển qua `S02` trước.
- `Saved Plans` → `S10`.
- `Shopping List` → `S08`.
- `Book Knowledge` → `S09`.

**Trạng thái:** Default; có thể có Empty state cho người dùng chưa từng tạo kế hoạch. Nội dung chính xác chờ Final UI.

### S02 — Food Preferences

**Mục đích:** Thu thập các lựa chọn cần thiết để tạo thực đơn phù hợp.

**Nội dung hiển thị:**

- Nhóm tuổi `< 65` hoặc `>= 65`.
- Cân nặng để tính mục tiêu protein tham chiếu `0.8 g/kg`.
- Số bữa mỗi ngày: `2` hoặc `3`.
- Khung giờ ăn `12 giờ`.
- Các bộ lọc hoặc hạn chế ăn uống đã được nhóm xác nhận.

**Tương tác và điều hướng:**

- Người dùng nhập/chọn dữ liệu rồi tiếp tục tới `S03`.
- Khi đi từ `S06` để nới lỏng bộ lọc, lưu thay đổi rồi quay lại danh sách món thay thế.
- Back giữ lại dữ liệu hợp lệ đã nhập trong phiên hiện tại.

**Validation:** Cân nặng phải là số dương trong phạm vi hợp lệ do nhóm nghiệp vụ xác nhận. Lỗi hiển thị cạnh trường nhập bằng văn bản, không chỉ đổi màu.

**Trạng thái:** Default, Focused, Filled, Error, Disabled cho trường nhập và lựa chọn.

### S03 — Create Meal Plan

**Mục đích:** Xác nhận cấu hình và bắt đầu tạo kế hoạch ăn trong 7 ngày.

**Nội dung hiển thị:**

- Tóm tắt sở thích từ `S02`.
- Chu kỳ `7 ngày`.
- Quy tắc cá tối đa `2–3 bữa/tuần`.
- Nút `Generate Plan` và lối quay lại chỉnh sửa sở thích.

**Tương tác và điều hướng:**

- `Generate Plan` → Loading → thành công chuyển tới `S04`.
- `Edit Preferences` → `S02`.
- Back → màn hình trước đó.

**Trạng thái:**

- Loading: khóa thao tác gửi lặp, hiển thị tiến trình có nhãn.
- Generation Error: giải thích ngắn gọn, có `Retry` và `Back/Edit Preferences`.
- No suitable result: cho phép sửa sở thích rồi tạo lại.

### S04 — Weekly Meal Plan

**Mục đích:** Hiển thị, xem và lưu kế hoạch bữa ăn 7 ngày.

**Nội dung hiển thị:**

- Danh sách hoặc lịch 7 ngày, mỗi ngày có 2 hoặc 3 bữa theo lựa chọn.
- Nhãn nguồn `Từ sách` hoặc `App gợi ý` bằng icon và chữ.
- Chỉ báo số bữa cá trong tuần và nhắc Multivitamin/Omega-3 theo chu kỳ đã thống nhất.
- Hành động `Save Plan` và `View Ingredients`.

**Tương tác và điều hướng:**

- Chọn meal card → `S05`.
- `View Ingredients` → `S07`.
- `Save Plan` thành công → xác nhận và có thể mở `S10`.
- Back → `S01` hoặc màn hình nguồn khi mở từ `S10`.

**Trạng thái:** Result, Loading transition, Save Success, Save Error. Khi lưu lỗi phải giữ nguyên kế hoạch và cho phép `Retry`.

### S05 — Recipe Details

**Mục đích:** Cho người dùng xem công thức, định lượng và nguồn kiến thức của một bữa ăn.

**Nội dung hiển thị:**

- Tên món, hình có mô tả thay thế, thời gian chuẩn bị/nấu.
- Nguyên liệu và định lượng; áp dụng tăng `20%` khi điều kiện giới tính nam được chọn theo yêu cầu nghiệp vụ.
- Các bước nấu ngắn gọn theo thứ tự.
- Nhãn bữa chính có `>= 30 g protein` khi phù hợp.
- Nguồn `Từ sách: Phụ lục A` hoặc `App gợi ý` bằng icon và chữ.

**Tương tác và điều hướng:**

- Mở nguồn sách → `S09` tại nội dung liên quan.
- `Replace Meal` → `S06`.
- Back → `S04`.

**Trạng thái:** Default; nội dung dài phải cuộn được và giữ hành động quan trọng dễ tiếp cận.

### S06 — Meal Alternatives

**Mục đích:** Đề xuất món hoặc nguyên liệu thay thế phù hợp với quy tắc sách và sở thích người dùng.

**Nội dung hiển thị:**

- Món hiện tại và danh sách lựa chọn thay thế.
- Lý do phù hợp và nhãn nguồn cho từng lựa chọn.
- Các lựa chọn tinh bột tương đương như pasta nguyên cám, gạo hoang, lúa mạch, farro hoặc gnocchi khi phù hợp.

**Tương tác và điều hướng:**

- Chọn và xác nhận món → cập nhật kế hoạch và quay lại `S04`.
- Cancel/Back → `S05`, giữ nguyên món cũ.
- `Revise Preferences` → `S02` khi không có lựa chọn phù hợp.

**Trạng thái:**

- Empty/No alternative: giải thích nguyên nhân, có `Revise Preferences` và `Keep Original`.
- Update Error: giữ nguyên món gốc, có `Retry` và `Cancel`.
- Confirmation trước khi áp dụng thay thế nếu Final UI yêu cầu.

### S07 — Ingredient Summary

**Mục đích:** Tổng hợp và chỉnh sửa nguyên liệu cần cho toàn bộ thực đơn tuần.

**Nội dung hiển thị:**

- Nguyên liệu đã gộp theo đơn vị tương thích.
- Nhóm Rau củ, Các loại đậu, Hạt, Dầu ô liu và Cá ít thủy ngân.
- Gợi ý tham chiếu: hạt khoảng `30 g/ngày`, dầu ô liu khoảng `3 muỗng canh/ngày`.
- Hành động `Create Shopping List`.

**Tương tác và điều hướng:**

- Chọn chỉnh sửa → mở `Edit Ingredient Dialog` dạng Overlay.
- Xóa nguyên liệu → Snackbar có `Undo`.
- `Create Shopping List` → `S08`.
- Back → `S04`.

**Trạng thái:** Empty, Edit Dialog, Validation Error và Creation Error. Số lượng phải là giá trị dương và đơn vị hợp lệ; dialog không đóng khi dữ liệu sai.

### S08 — Shopping List

**Mục đích:** Hỗ trợ người dùng mua sắm bằng danh sách nguyên liệu đã phân nhóm.

**Nội dung hiển thị:**

- Danh sách theo nhóm nguyên liệu.
- Checkbox có vùng chạm tối thiểu `48 x 48 dp`.
- Trạng thái đã mua thể hiện bằng checkbox, icon/chữ và kiểu trình bày phù hợp, không chỉ bằng màu.

**Tương tác và điều hướng:**

- Đánh dấu hoặc bỏ đánh dấu từng nguyên liệu.
- Back → `S07` hoặc màn hình nguồn.
- Điều hướng chính → các destination cấp cao theo Final UI.

**Trạng thái:** Default, Partially completed, Completed và Empty. Quy tắc lưu trạng thái checkbox chờ nhóm xác nhận.

### S09 — Book Knowledge

**Mục đích:** Giải thích cơ sở từ sách đứng sau các khuyến nghị trong ứng dụng.

**Nội dung hiển thị:**

- Các nguyên tắc dinh dưỡng và 5 trụ cột trường thọ đã được nhóm nội dung xác nhận.
- Trích dẫn/tham chiếu đến phần sách liên quan.
- Phân biệt rõ nội dung từ sách với diễn giải hoặc gợi ý của ứng dụng.

**Tương tác và điều hướng:**

- Khi mở từ `S05`, Back quay về đúng công thức trước đó.
- Khi mở từ Home, Back quay về `S01`.
- Có thể chọn một chủ đề để xem chi tiết trong cùng màn hình; không tạo thêm screen ID nếu chỉ là trạng thái chi tiết.

**Trạng thái:** Default và No result/Unavailable reference nếu dữ liệu tham chiếu chưa có.

### S10 — Saved Plans

**Mục đích:** Cho phép xem lại các kế hoạch đã lưu mà không phải tạo lại.

**Nội dung hiển thị:**

- Danh sách kế hoạch với tên, khoảng ngày và thông tin tóm tắt.
- Hành động mở kế hoạch và tạo kế hoạch mới.

**Tương tác và điều hướng:**

- Chọn một kế hoạch → `S04` ở chế độ xem kế hoạch đã lưu.
- `Create New Plan` → `S03` hoặc `S02` nếu cần cấu hình sở thích.
- Back → `S01`.

**Trạng thái:** Default, Empty và Load Error. Empty state có thông điệp cùng nút `Create Meal Plan`.

## 3. Những điểm cần xác nhận từ Figma

- [x] Tên và hierarchy chính của component đã được đối chiếu với Page 05 trong file `.fig` export ngày 2026-10-21.
- [x] Kích thước màn hình chính `360 x 800`, 10 bản QA `412 x 915`, content width và các metric token chính đã được đối chiếu.
- [ ] Bottom navigation xuất hiện trên màn hình nào và tab nào được chọn.
- [ ] Icon, hình minh họa và asset cuối cùng.
- [ ] Cách thể hiện Dark mode nếu nằm trong phạm vi bài.
- [x] Transition `S03 Loading` → `S04 Result` dùng `AFTER_TIMEOUT = 1000 ms`.
- [ ] Nội dung Dialog, Snackbar và thông báo lỗi đúng với Final UI.
- [ ] Quy tắc lưu trạng thái Shopping List.
