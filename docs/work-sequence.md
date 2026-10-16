# Trình tự thực hiện dự án UX/UI — 2 tuần

## 1. Nguyên tắc tổ chức

- Phân công 4 gói công việc chính một lần khi bắt đầu dự án. Mỗi thành viên tự chia phần việc của mình thành các task nhỏ.
- Theo dõi tiến độ theo các mốc chung; không cần giao lại toàn bộ công việc mỗi khi chuyển giai đoạn.
- Làm song song khi có thể, nhưng không bỏ qua các đầu vào mà công việc sau phụ thuộc.
- Commit GitHub khi có phần việc thực sự hoàn thành và lưu Figma Version History ở các mốc quan trọng. Không tạo thay đổi giả chỉ để tăng số lần commit.
- Ưu tiên các đầu ra bắt buộc trong rubric. Không tự ý bỏ yêu cầu chấm điểm để tiết kiệm thời gian.

## 2. Trình tự công việc

### Bước 1 — Chốt đầu vào

**Thời gian dự kiến:** Ngày 1–2

- Rà soát và thống nhất Persona.
- Chốt 3 User Flows và danh sách 10 màn hình `S01`–`S10`.
- Thống nhất nghiệp vụ lấy từ sách và các trạng thái cần có.
- Chốt quy chuẩn ban đầu trong `design/DESIGN.md`.
- Tạo file Figma và 6 Pages theo tên đã thống nhất.

**Đầu ra:** Nhóm cùng dùng một phiên bản yêu cầu và không tự ý thay đổi luồng chính khi chưa trao đổi.

**Lưu ý:** Tài liệu ban đầu có chỗ nói `persona.md`, `user-flow.md`, `DESIGN.md` đã có, nhưng phần phân công vẫn yêu cầu hoàn thiện các file này. Cần xác định rõ đây là bản nháp cần rà soát hay tài liệu đã được chốt.

### Bước 2 — Khởi động các việc có thể làm song song

**Thời gian dự kiến:** Ngày 2–3

- Thành viên 1: tạo prompt ban đầu trên Google Stitch, lưu kết quả và bắt đầu ghi lại các quyết định AI.
- Thành viên 2: thiết lập Design Tokens cơ bản trong Figma.
- Thành viên 3: chuẩn bị khung Wireframe theo danh sách màn hình đã chốt.
- Thành viên 4: tạo khung `design/screen-spec.md` và `handoff/flutter-handoff.md`; chưa cần viết chi tiết khi UI chưa được xác nhận.

**Đầu ra:** Các phần việc đã bắt đầu mà không phải chờ một người hoàn thành toàn bộ mới được làm tiếp.

### Bước 3 — Wireframe và Components

**Thời gian dự kiến:** Ngày 3–4

- Thành viên 3 vẽ Wireframe cho 10 màn hình trên Figma Page 02.
- Thành viên 2 phát triển 9 nhóm Component trên Figma Page 05, dùng Auto Layout, Variants và các Tokens đã thiết lập.
- Thành viên 1 ghi nhận các vòng chỉnh sửa AI và nhận xét UX có thể giúp cải thiện giao diện.
- Thành viên 4 tiếp tục chuẩn bị cấu trúc tài liệu và điền những thông tin đã chắc chắn.

**Đầu ra:** Wireframe đủ rõ để thiết kế Final UI; các Component cơ bản sẵn sàng tái sử dụng.

### Bước 4 — Final UI và tài liệu song song

**Thời gian dự kiến:** Ngày 5–7

- Thành viên 3 thiết kế 10 màn hình trên Figma Page 03, ưu tiên tái sử dụng Components.
- Bổ sung những trạng thái bắt buộc như Loading, Empty, Error và Dialog ở cạnh màn hình liên quan.
- Kiểm tra các kích thước 360 dp và 412 dp, độ tương phản, cỡ chữ và vùng chạm theo yêu cầu bài.
- Thành viên 4 viết Screen Spec và Flutter Handoff theo từng cụm màn hình đã được thống nhất, không đợi cả 10 màn hình xong mới bắt đầu.
- Thành viên 1 hoàn thiện bằng chứng về prompt, các lần lặp AI, AI Critique và quyết định Accept / Modify / Reject.

**Đầu ra:** Bộ Final UI rõ ràng, bằng chứng quá trình thiết kế được lưu lại và tài liệu được cập nhật theo giao diện thực tế.

### Bước 5 — Prototype và kiểm thử

**Thời gian dự kiến:** Ngày 8–9

- Nối 3 User Flows trên Figma Page 06 sau khi màn hình và trạng thái chính đã sẵn sàng.
- Kiểm tra Flow starting point, nút Back, nhánh lỗi và đường phục hồi.
- Kiểm tra Dialog Overlay trên S07 và chuyển cảnh Loading sang Result từ S03 đến S04.
- Xuất PNG sau khi Final UI đã được duyệt.
- Hoàn thiện Flutter Handoff, README và sơ đồ liên kết đến các đầu ra.

**Đầu ra:** Prototype chạy được theo các luồng dự kiến và bộ tài liệu đủ để giảng viên kiểm tra.

### Bước 6 — Chốt bài và tập bảo vệ

**Thời gian dự kiến:** Ngày 10

- Kiểm tra các file GitHub, hình ảnh và liên kết.
- Mở link Figma trong cửa sổ ẩn danh để kiểm tra quyền truy cập.
- Đối chiếu checklist với rubric; xác nhận các đầu ra bắt buộc đã có.
- Hoàn thiện 12 slides và tập Live Demo.
- Sửa các lỗi hiển thị, điều hướng hoặc tài liệu còn lại; tránh thêm thay đổi lớn vào phút cuối.

**Đầu ra:** Có thể trình bày và demo đầy đủ mà không phụ thuộc vào những phần chưa hoàn tất.

## 3. Các mốc kiểm tra chung

### Cuối ngày 2 — Chốt phạm vi

- [ ] Persona, User Flows và danh sách 10 màn hình đã thống nhất.
- [ ] Các nghiệp vụ quan trọng và trạng thái cần làm đã rõ.
- [ ] Figma có đủ 6 Pages theo đúng tên.

### Cuối ngày 4 — Chốt cấu trúc

- [ ] Wireframe cho 10 màn hình đã có.
- [ ] Design Tokens và các Components cốt lõi đã sẵn sàng.
- [ ] Các vấn đề UX lớn đã được ghi nhận.

### Cuối ngày 7 — Chốt giao diện

- [ ] 10 màn hình Final UI đã được thiết kế.
- [ ] Những trạng thái bắt buộc đã được thể hiện.
- [ ] Screen Spec và bằng chứng AI đã được cập nhật.

### Cuối ngày 9 — Chốt chức năng trình diễn

- [ ] 3 Prototype Flows đã nối và được kiểm tra.
- [ ] Flutter Handoff, README và PNG đã gần hoàn chỉnh.
- [ ] Link và quyền truy cập đã được kiểm tra sơ bộ.

### Ngày 10 — Nghiệm thu

- [ ] Đã đối chiếu đủ đầu ra theo rubric.
- [ ] Link Figma truy cập được từ cửa sổ ẩn danh.
- [ ] Slides và Live Demo đã được tập thử.
- [ ] Không còn lỗi nghiêm trọng chặn việc trình bày.

## 4. Những việc phụ thuộc nhau

| Công việc | Cần có trước |
|---|---|
| Vẽ Wireframe | User Flows và danh sách màn hình đã thống nhất |
| Tạo Components gắn với Tokens | Quy chuẩn Design Tokens cơ bản |
| Thiết kế Final UI | Wireframe và định hướng giao diện đã đủ rõ |
| Hoàn thiện Flutter Handoff | Thông tin giao diện, Components và hành vi đã được xác nhận |
| Hoàn thiện Prototype | Màn hình chính, điều hướng và trạng thái cần demo |
| Xuất PNG cuối cùng | Final UI đã được duyệt |
| Hoàn thiện slide và Live Demo | Có kết quả thực tế, prototype và tài liệu để trình bày |

## 5. Các lỗi cần tránh

- Không chờ một thành viên hoàn thành toàn bộ gói việc rồi người tiếp theo mới bắt đầu.
- Không thiết kế Final UI trước khi thống nhất User Flows và danh sách màn hình.
- Không đợi đến cuối dự án mới viết Screen Spec và Flutter Handoff; hãy cập nhật dần khi có thông tin chắc chắn.
- Không thay đổi luồng chính sau khi đã thiết kế nhiều màn hình nếu chưa đánh giá tác động đến Prototype và tài liệu.
- Không tạo commit giả hoặc sửa đổi giả chỉ để đạt số lượng commit. Hãy lưu lại các mốc tiến độ thật và tuân thủ yêu cầu chính thức của đề bài.
- Không xem lịch 10 ngày là bất biến; nếu nhóm có ít thời gian làm việc hơn, hãy ưu tiên yêu cầu bắt buộc theo rubric và báo sớm nguy cơ trễ.

## 6. Quy tắc phân công và theo dõi

- **Đầu dự án:** Giao 4 gói công việc, người chịu trách nhiệm, đầu ra và hạn hoàn thành.
- **Cuối ngày 4:** Kiểm tra Wireframe, Tokens và Components; chỉ điều chỉnh phân công khi có vướng mắc thực tế.
- **Cuối ngày 7:** Kiểm tra Final UI và các việc có nguy cơ trễ.
- **Cuối ngày 10:** Nghiệm thu toàn bộ đầu ra và tập bảo vệ.

Mỗi task có thể theo trạng thái: `Todo` → `In Progress` → `Review` → `Done`.

## Kết luận

Thứ tự cốt lõi là: **chốt yêu cầu và User Flows → thiết lập Tokens và Wireframe → hoàn thiện Components và Final UI → cập nhật tài liệu song song → nối Prototype và kiểm thử → nghiệm thu và bảo vệ**.

Mục tiêu không phải giao việc nhiều lần, mà là giao trách nhiệm một lần, thống nhất đầu ra và kiểm tra theo những mốc chung.
