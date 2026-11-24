# MLD Game Store

**MLD Game Store** là website tĩnh HTML5/CSS3 giới thiệu shop tài khoản game mẫu: danh mục acc, gói bảo hành, quy trình giao dịch và biểu mẫu tư vấn. Form chỉ mô phỏng; website không gửi email và không lưu yêu cầu.

## Thông tin dự án

- **Tác giả:** Mai Lâm Duy — MSV: 2071020214 — CNTT 20-04 — Trường Đại học Đại Nam
- **Học phần:** Bài tập lớn A3, FIT4014
- **Repository:** [duy200779/mld-game-store](https://github.com/duy200779/mld-game-store)
- **GitHub Pages:** [https://duy200779.github.io/mld-game-store/](https://duy200779.github.io/mld-game-store/)
- **Hồ sơ tác giả:** [github.com/duy200779](https://github.com/duy200779)

## Cấu trúc thư mục

```text
.
├── AI_LOG.md
├── RELEASE_NOTES.md
├── README.md
├── index.html
├── ket-qua.html
├── assets/
│   └── images/
│       ├── acc-genshin.jpg
│       ├── acc-lien-quan.jpg
│       ├── acc-lmht.jpg
│       ├── acc-valorant.jpg
│       └── banner-shop.jpg
└── css/
    └── style.css
```

Danh sách trên khớp với cây thư mục đã kiểm tra (không tính `.git`). Hiện **không có thư mục `evidence/` hoặc tệp minh chứng ảnh** trong workspace, vì vậy không có ảnh kiểm thử nào được liên kết hay khẳng định tồn tại.

## Chạy local

1. Mở `index.html` trực tiếp trong trình duyệt; hoặc
2. Tại thư mục gốc dự án, chạy `python -m http.server 8000` (Windows cũng có thể dùng `py -m http.server 8000`).
3. Mở [http://localhost:8000](http://localhost:8000). Có thể thay bằng tiện ích **Live Server** trong VS Code.

Website không có bước build hay thư viện phụ thuộc. Dùng dữ liệu giả khi thử form; dữ liệu gửi bằng GET sẽ xuất hiện trong query string của URL.

## Nguồn xuất bản

Thông tin bàn giao của dự án chỉ định GitHub Pages xuất bản từ nhánh `main`, thư mục gốc `/`. URL Pages ở trên đã được mở và trả nội dung website; cấu hình trong Settings → Pages chưa được xác minh độc lập trong lần rà soát này.

## Các bước kiểm tra

Thực hiện trên URL Pages hoặc máy chủ local:

1. **Trang chủ và điều hướng:** mở `index.html`; dùng menu để tới Giới thiệu, Acc nổi bật, Gói bảo hành, Quy trình và Đặt acc. Kiểm tra bốn thẻ acc và các ảnh có đường dẫn trong `assets/images/`.
2. **Responsive:** dùng chế độ responsive của DevTools, lần lượt đặt viewport rộng **320px, 640px, 960px và 1440px**. Kiểm tra menu, card grid và form không làm tràn toàn trang; dự kiến card grid chuyển từ 1 cột sang 2 cột tại 640px và 3 cột tại 960px. Ở 1440px, kiểm tra container không vượt chiều rộng tối đa.
3. **Bảng tại 320px:** tới Bảng giá. Bảng có `min-width: 34rem` bên trong `.table-wrapper` với `overflow-x: auto`, nên vùng bảng có thể cuộn ngang riêng; kiểm tra trang bên ngoài không bị tràn ngang.
4. **Bàn phím và trạng thái nút:** dùng `Tab` / `Shift+Tab` để đi qua liên kết và form; kiểm tra outline `:focus-visible`. Tại acc Genshin, xác nhận nút “Tạm hết hàng” có `disabled` và không thể kích hoạt.
5. **Biểu mẫu – ba trường hợp:**
   - Để trống các trường và gửi: trình duyệt chặn gửi do `required`.
   - Nhập các trường bắt buộc khác hợp lệ nhưng email sai định dạng, rồi gửi: xác thực kiểu `email` chặn gửi.
   - Nhập tên từ 2 ký tự, email đúng định dạng và nội dung 10–500 ký tự: gửi sẽ chuyển tới `ket-qua.html` bằng GET. Đây chỉ là trang kết quả tĩnh, không xử lý đơn hàng.

Các bước trên là hướng dẫn kiểm tra, không phải báo cáo rằng mọi viewport và trường hợp form đã được chạy thử. Xem [AI_LOG.md](AI_LOG.md) để biết trạng thái kiểm chứng.

## Liên kết và minh chứng

- [Hồ sơ tác giả](https://github.com/duy200779)
- [Repository](https://github.com/duy200779/mld-game-store)
- [Website GitHub Pages](https://duy200779.github.io/mld-game-store/)
- [AI_LOG.md](AI_LOG.md)
- [RELEASE_NOTES.md](RELEASE_NOTES.md)

Không có tệp nào trong `evidence/` để liên kết; không tạo tên ảnh minh chứng thay thế.

## Giới hạn

Đây là website tĩnh. Form chỉ kiểm tra dữ liệu bằng HTML5 và điều hướng tới `ket-qua.html`; không gửi email, không lưu dữ liệu và không tạo đơn hàng. Nội dung tài khoản/giá là thông tin mẫu, không xác nhận tồn tại giao dịch thực.
