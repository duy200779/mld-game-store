# Nhật ký thay đổi – MLD Game Store

## v3 (24/11/2026) – Bản bàn giao A3 / Lab 8

- Chuẩn hóa tài liệu: chuyển nhật ký AI vào `docs/AI_LOG.md`, thêm `docs/evidence-index.md`, thay `RELEASE_NOTES.md` bằng `CHANGELOG.md`.
- Tạo `docs/evidence/` và lưu năm ảnh chụp cho desktop, mobile, focus bàn phím, validation lỗi và gửi form hợp lệ.
- Rà soát `index.html`, `ket-qua.html`, `css/style.css`: không phát hiện đường dẫn tuyệt đối cục bộ hoặc các literal nhạy cảm được dò (`password`, `token`, `ghp_`). Không sửa HTML/CSS.
- Ghi nhận giới hạn giao diện: trang kết quả có class Font Awesome nhưng không tải thư viện tương ứng nên biểu tượng không hiển thị; không sửa code ngoài phạm vi tài liệu/minh chứng.
- Ảnh chụp được xuất từ phiên trình duyệt cô lập. Do giới hạn raster đầu ra của browser, các ảnh PNG được chuẩn hóa kích thước đầu ra về viewport kiểm thử; nội dung không được ghép/chỉnh sửa. Chi tiết ở [evidence index](./docs/evidence-index.md).
- Chưa kiểm tra trực tiếp trên iPhone vật lý. Screenshot trang không chứa thanh địa chỉ browser; URL GET được xác nhận từ URL mà Playwright đọc được, xem ghi chú ở evidence index.
- **Trạng thái phát hành:** các thay đổi v3 hiện ở working tree; chưa có commit/tag v3. Commit mới nhất trước lần cập nhật này là `bf57a4c` (tag `v2`).

## v2 (24/11/2026) – Cập nhật tài liệu và ảnh minh họa

- Commit [`bf57a4c`](https://github.com/duy200779/mld-game-store/commit/bf57a4c001ce407ad5ba3473cda31698a98e91b1), tag [`v2`](https://github.com/duy200779/mld-game-store/tree/v2).
- Bổ sung/cập nhật tài liệu bàn giao ở gốc gồm README, AI_LOG và RELEASE_NOTES. Commit này chỉ thay đổi tài liệu theo `git show --stat`; không thêm năm ảnh game.

## v1 (24/11/2026) – Mã nguồn giao diện tĩnh

- Commit [`8b33ea7`](https://github.com/duy200779/mld-game-store/commit/8b33ea7c3c58e1487064ac2217e91089261ea748), tag [`v1`](https://github.com/duy200779/mld-game-store/tree/v1).
- Đưa `index.html`, `ket-qua.html`, `css/style.css` và năm ảnh trong `assets/images/` vào repository.
- CSS hiện có bố cục Mobile-first, breakpoint 640px/960px, wrapper bảng cuộn ngang, trạng thái focus/disabled và ràng buộc form HTML5. Lịch sử commit không ghi các thay đổi này thành từng bản sửa lỗi riêng.

## Khởi tạo

- Commit [`4321752`](https://github.com/duy200779/mld-game-store/commit/43217529f4c89cc25f0d6ae53fe67327f5c6f3ec) (`Initial commit`).

