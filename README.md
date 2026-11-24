# MLD Game Store

**Tác giả:** Mai Lâm Duy — MSV 2071020214 — Lớp CNTT 20-04 — Khoa CNTT, Trường Đại học Đại Nam
**Học phần:** Bài tập lớn A3 / Lab 8 — FIT4014

## Sản phẩm

MLD Game Store là website tĩnh HTML5/CSS3 trưng bày tài khoản mẫu của Liên Quân Mobile, Valorant, Liên Minh Huyền Thoại và Genshin Impact. Website còn có bảng gói bảo hành, quy trình giao dịch bốn bước và biểu mẫu đặt giữ acc mô phỏng.

- **Demo:** [https://duy200779.github.io/mld-game-store/](https://duy200779.github.io/mld-game-store/)
- **Repository:** [https://github.com/duy200779/mld-game-store](https://github.com/duy200779/mld-game-store)
- **Hồ sơ tác giả:** [github.com/duy200779](https://github.com/duy200779)

## Tính năng chính

1. Thanh điều hướng Flexbox liên kết tới năm phân mục: Giới thiệu, Acc nổi bật, Gói bảo hành, Quy trình và Đặt acc.
2. Lưới thẻ tài khoản responsive: một cột mặc định, hai cột từ 640px và ba cột từ 960px.
3. Bảng so sánh gói bảo hành nằm trong `.table-wrapper` có thể cuộn ngang riêng; trang có quy trình giao dịch bốn bước.
4. Biểu mẫu dùng các ràng buộc HTML5 và gửi bằng GET tới trang mô phỏng `ket-qua.html`.

## Cách mở và kiểm tra

1. Truy cập [GitHub Pages](https://duy200779.github.io/mld-game-store/), mở `index.html` trực tiếp, hoặc chạy máy chủ tĩnh tại thư mục dự án:

   ```powershell
   python -m http.server 8000
   ```

   Mở `http://localhost:8000`. Có thể dùng **Live Server** trong VS Code thay cho máy chủ Python.
2. Bấm lần lượt Giới thiệu, Acc nổi bật, Gói bảo hành, Quy trình và Đặt acc để tới từng phân mục.
3. Tại khu vực Đặt mua acc & Liên hệ hỗ trợ, nhập tên, email và nội dung/mã acc; bấm **Kiểm tra biểu mẫu** để thử xác thực và chuyển tới `ket-qua.html`.
4. Mở [bảng minh chứng](./docs/evidence-index.md) để xem kết quả kiểm thử và ảnh. Ảnh kiểm thử được chụp từ browser automation ở viewport giả lập; chưa kiểm tra trên iPhone vật lý.

Website không cần cài thư viện hay build. Chỉ dùng dữ liệu giả khi thử form; dữ liệu gửi bằng GET xuất hiện trên URL.

## Cấu trúc thư mục

```text
.
├── README.md
├── CHANGELOG.md
├── index.html
├── ket-qua.html
├── css/
│   └── style.css
├── assets/
│   └── images/
│       ├── acc-genshin.jpg
│       ├── acc-lien-quan.jpg
│       ├── acc-lmht.jpg
│       ├── acc-valorant.jpg
│       └── banner-shop.jpg
└── docs/
    ├── AI_LOG.md
    ├── BAO_CAO_A3_FIT4014.md
    ├── evidence-index.md
    └── evidence/
        ├── 01-desktop-1440px.png
        ├── 02-mobile-375px.png
        ├── 03-keyboard-focus-menu.png
        ├── 04-form-validation-error.png
        └── 05-form-submit-ket-qua.png
```

## Nguồn xuất bản và tài nguyên

- Mã nguồn ở nhánh `main`; thông tin cấu hình bàn giao là GitHub Pages từ nhánh `main`, thư mục gốc `/`.
- Nguồn demo: [GitHub Pages](https://duy200779.github.io/mld-game-store/).
- Tag [`v3`](https://github.com/duy200779/mld-game-store/tree/v3) đã được đẩy lên GitHub tại commit `8a89bf6`; nhánh `main` cũng trỏ tới commit này. Commit v3 chuẩn hóa tài liệu và thêm ảnh minh chứng, không sửa HTML/CSS ứng dụng.
- Xem [báo cáo A3/FIT4014](./docs/BAO_CAO_A3_FIT4014.md) để đọc mô tả thiết kế, kiểm thử và bàn giao. Cấu hình Pages trong GitHub Settings chưa được xác minh độc lập.
- Nguồn ảnh theo thông tin được cung cấp cho dự án: banner từ Pexels; ảnh game từ tài nguyên truyền thông của Garena, Riot Games và HoYoverse, được lưu trong `assets/images/`. Repository không lưu URL ảnh gốc, tên tác giả hay giấy phép cụ thể; cần bổ sung/đối chiếu các thông tin đó trước khi tái sử dụng hoặc phát hành ngoài phạm vi bài tập.
- Tên tài khoản, giá và mô tả trong các thẻ là dữ liệu giả lập phục vụ đồ án.

## Giới hạn và khai báo AI

Form chạy tĩnh bằng phương thức GET, không gửi email và không lưu yêu cầu vào cơ sở dữ liệu. Trang kết quả không xử lý các tham số GET. Chưa kiểm tra trên thiết bị iPhone vật lý.

Trang kết quả dùng class biểu tượng Font Awesome nhưng repository không nạp stylesheet/thư viện Font Awesome; biểu tượng không xuất hiện trong ảnh kiểm thử hiện tại.

AI được dùng hỗ trợ rà soát và chuẩn hóa tài liệu/kiểm thử; mã HTML/CSS ứng dụng không được sửa trong lần bàn giao này. Xem [docs/AI_LOG.md](./docs/AI_LOG.md) để biết các quyết định và kết quả kiểm chứng.
