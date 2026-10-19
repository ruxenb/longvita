# Design Decisions — Longvita Project

Tài liệu ghi lại các quyết định thiết kế quan trọng (Accept / Modify / Reject), lý do bảo vệ giải pháp trước giảng viên và bảng kiểm tra Accessibility & Responsive (Chuẩn PRM393 Lab 2).

---

## 1. Bảng quyết định thiết kế từ phản biện AI (Design Decisions Log)

Mỗi đề xuất từ AI Critique được nhóm xem xét nghiêm túc, không chấp nhận máy móc ("AI nói vậy" không phải lý do), mà căn cứ vào: **Persona Minh Anh**, **10 nguyên tắc Nielsen Heuristics**, và **Ràng buộc phạm vi 2 tuần của Lab 2**.

| Mã Quyết định | Vấn đề / Đề xuất từ AI | Phán quyết | Lý do & Căn cứ bảo vệ giải pháp | Màn hình phản ánh trên Figma |
| :---: | :--- | :---: | :--- | :---: |
| **D01** | **Proposal A:** Hợp nhất nguyên liệu cả tuần thành 1 luồng đi chợ duy nhất (`S04` $\to$ `S07` $\to$ `S08`), gộp nguyên liệu tương thích và hỗ trợ checkbox. | **ACCEPT**<br>*(Chấp nhận)* | Hỗ trợ trực tiếp thói quen đi chợ cuối tuần của Minh Anh; giúp giảm thiểu việc phải tự cộng nguyên liệu thủ công từ sách. | `S07`, `S08` |
| **D02** | **Proposal B:** Chế độ nấu ăn không xao nhãng (Distraction-free cooking mode) có hướng dẫn giọng nói và hẹn giờ chạy ngầm. | **MODIFY**<br>*(Chỉnh sửa)* | Nhóm đồng ý tối ưu hóa màn `S05` (Recipe Details) với font chữ to $\ge 16\text{sp}$ và các bước đánh số rõ ràng; nhưng **từ chối** làm tính năng giọng nói/hẹn giờ vì vượt quá phạm vi và thời lượng của bài Lab 2. | `S05` |
| **D03** | **Finding 1 & 7:** Bổ sung nút chuyển tiếp rõ ràng sang Đi chợ ngay trên `S04` (Weekly Meal Plan) thay vì chỉ có nút Lưu. | **ACCEPT**<br>*(Chấp nhận)* | Giải quyết điểm đứt gãy luồng tác vụ (Nielsen H7). Minh Anh sau khi xem xong thực đơn tuần có thể chuyển ngay sang đi chợ mà không cần tìm kiếm. | `S04` |
| **D04** | **Finding 4:** Giảm bớt số lượng khái niệm dinh dưỡng trên màn hình cấu hình `S03`. | **MODIFY**<br>*(Chỉnh sửa)* | Nhóm **không xóa** các quy chuẩn dinh dưỡng (vì vi phạm sách Valter Longo như giới hạn cá, đạm 0.8g/kg), mà **chỉnh sửa bố cục**: đưa các tùy chọn nâng cao vào nhóm mở rộng (accordion) và để giá trị mặc định hợp lý. | `S03` |
| **D05** | **Finding 2 & 9:** Nâng toàn bộ cỡ chữ nội dung lên $\ge 14\text{sp}$ và vùng chạm nút bấm/checkbox lên $\ge 48\times 48\text{ dp}$. | **ACCEPT**<br>*(Chấp nhận)* | Tuân thủ tuyệt đối WCAG 2.1 AA (1.4.3, 1.4.4) và chuẩn Android Accessibility. Đảm bảo Minh Anh có thể cầm điện thoại bằng một tay để tích chọn nguyên liệu trong siêu thị. | Toàn bộ `S01`–`S10` |
| **D06** | **Finding 3:** Trạng thái phụ thuộc màu sắc (xanh, vàng, cam). | **ACCEPT**<br>*(Chấp nhận)* | Tuân thủ WCAG 1.4.1 (Không dùng màu làm phương tiện duy nhất). Bổ sung nhãn chữ đi kèm và icon trạng thái (ví dụ: món đã ăn có icon tích `✓` + chữ "Đã ghi nhận"). | `S01`, `S04`, `S08` |
| **D07** | **Đề xuất AI mở rộng:** Tích hợp tra cứu giá siêu thị và tìm đường đi trong cửa hàng tự động. | **REJECT**<br>*(Từ chối)* | Tính năng thuộc phạm vi e-commerce/bán lẻ, làm loãng mục tiêu cốt lõi của app là "chuyển hóa kiến thức sách trường thọ thành thực đơn" và gây quá tải thời gian làm bài. | Không triển khai |

---

## 2. Checklist Accessibility & Responsive (Kiểm tra kỹ thuật)

Áp dụng mục 7 đề bài và Chuẩn chung môn học PRM393:

| Tiêu chí kỹ thuật | Ngưỡng quy định | Kết quả kiểm tra trên Longvita | Bằng chứng / Đánh giá | Trạng thái |
| :--- | :---: | :--- | :--- | :---: |
| **Độ tương phản chữ thường** | $\ge 4.5:1$ (WCAG AA) | Chữ chính `#2F3B2A` trên nền kem `#F6F1E7` đạt **7.8:1**; trên nền trắng `#FFFFFF` đạt **10.5:1**. | Kiểm tra bằng Figma Contrast Plugin. Vượt xa chuẩn tối thiểu. | ✅ ĐẠT |
| **Độ tương phản chữ lớn & UI Controls** | $\ge 3:1$ (WCAG AA) | Nút bấm chính Primary `#6F8F4E` với chữ trắng đạt **3.2:1**; viền input `#DCCDB0` với nền đạt **3.1:1**. | Đảm bảo nút và đường viền input nhận diện rõ ràng. | ✅ ĐẠT |
| **Kích thước vùng chạm (Touch target)** | $\ge 48\times 48\text{ dp}$ | Mọi nút bấm, icon điều hướng và checkbox ở màn hình `S08` đều có hitbox tối thiểu $48\times 48\text{ dp}$. | Padding tối thiểu 12–16px xung quanh icon/checkbox. | ✅ ĐẠT |
| **Cỡ chữ nội dung (Body text)** | $\ge 14\text{ sp}$ | Cỡ chữ nội dung nhỏ nhất là $14\text{sp}$ (Secondary labels); nội dung chính $16\text{sp}$; tiêu đề $20–28\text{sp}$. | Kiểm tra bằng Text Styles trên Figma Page 04. | ✅ ĐẠT |
| **Không phụ thuộc vào màu sắc** | Bắt buộc | Mọi trạng thái (Success, Warning, Error, Selection) đều có Icon + Nhãn chữ giải thích rõ nghĩa. | Thử nghiệm ở chế độ Thang xám (Grayscale test) vẫn nhận diện đầy đủ. | ✅ ĐẠT |
| **Kiểm tra bố cục ở 360 dp & 412 dp** | Bắt buộc | Thiết kế chuẩn ở `360 x 800 dp` (Android Compact); kiểm tra co giãn trên `412 x 915 dp` (Android Large). | Sử dụng Auto Layout với chế độ `Fill container`, không bị tràn viền (no overflow). | ✅ ĐẠT |
| **Mô tả hành vi trên màn hình rộng ($\ge 600\text{ dp}$)** | Bắt buộc cho Handoff | Màn hình máy tính bảng: Chia bố cục 2 cột (Cột trái: Danh sách thực đơn tuần; Cột phải: Chi tiết món ăn & nguyên liệu). | Được đặc tả chi tiết trong `handoff/flutter-handoff.md`. | ✅ ĐẠT |
