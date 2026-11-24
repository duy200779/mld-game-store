# AI_LOG – MLD Game Store

**Tác giả:** Mai Lâm Duy — MSV 2071020214 — CNTT 20-04 | **Ngày ghi nhận:** 24/11/2026

## Phạm vi và dữ kiện

Trong lần chuẩn bị bàn giao này, đã kiểm tra `index.html`, `ket-qua.html`, `css/style.css`, cây thư mục và `git log --oneline`. Source hiện có các đặc điểm kỹ thuật mô tả dưới đây. Git log chỉ có hai commit với thông điệp chung; không đủ dữ kiện để khẳng định các đặc điểm đó được tạo/sửa ở commit nào hay để tái dựng suy nghĩ của sinh viên trước những lần dùng AI trước đây.

Vì vậy, “nhận định trước AI” dưới đây là nhận định kỹ thuật hình thành khi bắt đầu rà soát hiện tại, không phải trích dẫn hồi tưởng về một cuộc hội thoại cũ. Không sửa `index.html`, `ket-qua.html` hoặc `css/style.css` trong công việc này; các gợi ý bên dưới không được coi là thay đổi đã áp dụng vào mã nguồn.

## Tình huống 1 – Semantic HTML5 và ảnh sản phẩm

1. **Hiện tượng & dữ kiện ban đầu:** `index.html` có `header`, `nav`, `main`, `section`, `article`, `figure`, `form` và `footer`; ảnh dùng đường dẫn tương đối trong `assets/images/` và có `alt`. Năm tệp ảnh tồn tại trong cây thư mục.
2. **Nhận định trước khi hỏi AI:** cấu trúc ngữ nghĩa và liên kết ảnh có vẻ rõ ràng theo mã; cần tránh viết tài liệu làm người đọc nghĩ đây là ứng dụng có backend.
3. **Công cụ/Prompt tóm tắt:** Copilot SDK trong VS Code; yêu cầu đọc source thật và tạo tài liệu bàn giao chính xác, không đoán chức năng.
4. **Gợi ý từ AI:** mô tả trang theo thành phần HTML quan sát được; kiểm tra tên và đường dẫn ảnh có trong repo trước khi liệt kê.
5. **Quyết định có lý do của sinh viên:** giữ mô tả là website tĩnh và liệt kê đúng năm ảnh; không thêm ảnh minh chứng hoặc tính năng không có trong repo.
6. **Phần đã sửa trong mã nguồn:** không sửa mã nguồn trong lần này. Tài liệu được cập nhật; phần HTML/đường dẫn ảnh nêu trên là hiện trạng ở commit nền `8b33ea7`, không phải thay đổi vừa thực hiện.
7. **Cách thử lại và kết quả thực tế:** đã đối chiếu đường dẫn ảnh với cây file; **Chưa kiểm tra** ảnh render trên trình duyệt. `evidence/` không tồn tại nên không có ảnh minh chứng để dẫn.

## Tình huống 2 – Breakpoints Mobile-first và bảng ở 320px

1. **Hiện tượng & dữ kiện ban đầu:** CSS dùng một cột mặc định, breakpoint 640px/960px; bảng có `min-width: 34rem` nằm trong `.table-wrapper { overflow-x: auto; }`.
2. **Nhận định trước khi hỏi AI:** cấu hình CSS cho thấy bảng được thiết kế để cuộn trong khung ở màn hình hẹp, không phải thu nhỏ nội dung bảng về 320px; cần mô tả chính xác sự khác biệt này.
3. **Công cụ/Prompt tóm tắt:** Copilot SDK trong VS Code; yêu cầu kiểm tra CSS và ghi checklist viewport 320, 640, 960, 1440px mà không ghi kết quả chưa chạy.
4. **Gợi ý từ AI:** hướng dẫn dùng DevTools responsive; kiểm tra không tràn ngang toàn trang và chấp nhận cuộn ngang riêng bên trong vùng bảng.
5. **Quyết định có lý do của sinh viên:** dùng checklist đó trong README và không tuyên bố responsive đã được kiểm thử trên bốn kích thước vì chưa có kết quả kiểm thử hoặc ảnh.
6. **Phần đã sửa trong mã nguồn:** không sửa CSS; các breakpoint và wrapper bảng đã có trong mã hiện tại. Lịch sử commit không cho biết chúng có phải bản sửa lỗi so với v1 hay không.
7. **Cách thử lại và kết quả thực tế:** hướng dẫn thử bốn viewport trong README; **Chưa kiểm tra** trực tiếp 320/640/960/1440px. Không có ảnh viewport trong `evidence/`.

## Tình huống 3 – Focus bàn phím, nút disabled và báo lỗi form

1. **Hiện tượng & dữ kiện ban đầu:** CSS định nghĩa `:focus-visible` cho liên kết/nút/ô nhập, `:user-invalid` cho input và textarea, cùng style cho nút `:disabled`; nút acc Genshin có thuộc tính HTML `disabled`.
2. **Nhận định trước khi hỏi AI:** trạng thái tương tác được khai báo trong CSS/HTML; phải kiểm tra bằng thao tác bàn phím và không coi riêng việc có selector là bằng chứng đã hoạt động trực quan.
3. **Công cụ/Prompt tóm tắt:** Copilot SDK trong VS Code; yêu cầu rà soát trạng thái UX thực tế trong mã và ghi cách kiểm tra, nêu rõ nội dung chưa xác nhận.
4. **Gợi ý từ AI:** dùng `Tab`/`Shift+Tab` để quan sát focus, thử nút hết hàng và kiểm tra phản hồi nhập sai sau khi người dùng tương tác.
5. **Quyết định có lý do của sinh viên:** giữ nguyên code ổn định theo phạm vi yêu cầu; đưa các bước này thành checklist thay vì tuyên bố đã đạt kiểm thử accessibility.
6. **Phần đã sửa trong mã nguồn:** không sửa HTML/CSS. Các selector và thuộc tính đang được rà soát đã có ở commit nền; không có commit riêng xác nhận thời điểm bổ sung.
7. **Cách thử lại và kết quả thực tế:** **Chưa kiểm tra** tương tác bàn phím, trạng thái focus hoặc disabled trên trình duyệt. Không có ảnh minh chứng tương ứng trong `evidence/`.

## Tình huống 4 – Xác thực form và trang `ket-qua.html`

1. **Hiện tượng & dữ kiện ban đầu:** form GET tới `ket-qua.html`; ba trường có `required`, email có `type="email"`, tên có min/max length và nội dung có độ dài 10–500. Trang kết quả là HTML tĩnh, không đọc query string hay gọi dịch vụ.
2. **Nhận định trước khi hỏi AI:** có thể hướng dẫn ba tình huống rỗng/sai email/hợp lệ dựa trên HTML, nhưng chưa thể khẳng định luồng đã chạy; nội dung “đã ghi nhận” ở trang kết quả không chứng minh dữ liệu được lưu.
3. **Công cụ/Prompt tóm tắt:** Copilot SDK trong VS Code; yêu cầu mô tả đúng luồng form, phân biệt giao diện mô phỏng với xử lý đơn thật và không bịa kết quả test.
4. **Gợi ý từ AI:** mô tả xác thực HTML5 và điều hướng GET; dùng dữ liệu giả, lưu ý dữ liệu form xuất hiện trong query string và không ghi nhận email/đơn hàng được gửi.
5. **Quyết định có lý do của sinh viên:** README và release notes gọi đây là mô phỏng tĩnh, nêu rõ không gửi email/không lưu dữ liệu; không sửa code theo yêu cầu giới hạn thay đổi chỉ ở ba tài liệu.
6. **Phần đã sửa trong mã nguồn:** không sửa form hoặc trang kết quả. Tài liệu được cập nhật để tránh hứa hẹn xử lý mà source không có.
7. **Cách thử lại và kết quả thực tế:** README hướng dẫn thử form rỗng, sai email và hợp lệ; cả ba ca **Chưa kiểm tra** trực tiếp trong trình duyệt. Không có ảnh kết quả trong `evidence/`.

## Tổng kết kiểm chứng

- Đã kiểm tra cây thư mục: không có `evidence/`, nên không có tên ảnh minh chứng thực tế để dẫn.
- Đã kiểm tra `git log --oneline`: `8b33ea7 Add files via upload`, `4321752 Initial commit`; tag có trên remote là `v1`, chưa thấy tag `v2`.
- Đã mở URL GitHub Pages trong lần rà soát trước và nhận được nội dung trang. Không kiểm thử các kích thước viewport hoặc submit form trong lần này.
- Chỉ cập nhật tài liệu; không sửa source HTML/CSS. Hãy chạy checklist trong README trước khi ghi nhận kết quả kiểm thử mới.
