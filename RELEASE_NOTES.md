# MLD Game Store – v2: Bản bàn giao hoàn thiện A3

- **Ngày cập nhật:** 24/11/2026
- **Môn học:** Bài tập lớn A3 – FIT4014
- **Phạm vi thay đổi lần này:** tài liệu bàn giao; không sửa HTML/CSS.

## Bản mã và trạng thái phát hành

Đã kiểm tra `git log --oneline` và tag trên remote. Commit hiện tại của mã nguồn là [`8b33ea7`](https://github.com/duy200779/mld-game-store/commit/8b33ea7c3c58e1487064ac2217e91089261ea748) (`Add files via upload`); tag thực tế trỏ tới commit đó là [`v1`](https://github.com/duy200779/mld-game-store/tree/v1). Commit trước là [`4321752`](https://github.com/duy200779/mld-game-store/commit/43217529f4c89cc25f0d6ae53fe67327f5c6f3ec) (`Initial commit`).

**Chưa có tag hoặc commit `v2` trên remote.** Vì vậy không thể dẫn liên kết tag v2 như thể nó đã tồn tại. Bộ tài liệu v2 trong workspace chưa được commit; sau khi tạo commit/tag phát hành thực tế, cập nhật phần này bằng URL chính xác tới tag/commit mới. Có thể kiểm tra danh sách tại [GitHub Tags](https://github.com/duy200779/mld-game-store/tags).

## Thay đổi chính so với trạng thái v1 đã kiểm tra

- Viết lại README với thông tin tác giả, cách chạy, hướng dẫn kiểm thử, nguồn xuất bản và giới hạn ứng dụng.
- Bổ sung AI_LOG ghi lại các nhận định dựa trên source và phân biệt rõ kiểm tra đã làm/chưa làm.
- Tạo ghi chú bàn giao này. Không có thư mục `evidence/` trong workspace, nên chưa thể bàn giao minh chứng ảnh kiểm thử.
- Chưa có cơ sở từ lịch sử commit để xác nhận các sửa đổi code so với v1 về ảnh, overflow, focus hay form; các đặc điểm hiện có được liệt kê dưới đây, không gán là lỗi đã sửa trong v2.

## Rà soát các điểm kỹ thuật trong mã hiện tại

- **Ảnh minh họa:** HTML tham chiếu năm tệp ảnh cục bộ trong `assets/images/`; cả năm đường dẫn khớp với tệp có trong cây thư mục. Việc tải/render ảnh trong trình duyệt **chưa kiểm tra**.
- **Bảng ở màn hình hẹp:** bảng có `min-width: 34rem` trong wrapper `overflow-x: auto`, cho phép vùng bảng cuộn riêng. Kiểm thử thực tế ở 320px **chưa kiểm tra**.
- **Bàn phím/focus:** CSS khai báo `:focus-visible`; nút acc Genshin được đánh dấu `disabled`. Thao tác bàn phím trực tiếp **chưa kiểm tra**.
- **Ràng buộc form:** HTML khai báo `required`, `type=email`, giới hạn độ dài tên và nội dung 10–500 ký tự. Ba ca submit rỗng/sai định dạng/hợp lệ **chưa kiểm tra**.

Đây là các cơ chế có trong source ở commit nền, không phải danh sách lỗi lịch sử đã xác minh được sửa trong v2. Git log chỉ có thông điệp commit chung và không ghi riêng các thay đổi này.

## Hạn chế còn lại

- Website là HTML/CSS tĩnh, chưa có backend hoặc cơ sở dữ liệu.
- Form chỉ xác thực phía trình duyệt và điều hướng GET tới trang tĩnh; không lưu đơn, không gửi email thật.
- Chưa có `evidence/`, ảnh chụp viewport hay báo cáo kiểm thử tương tác trong repo.
- Chưa có tag/commit v2 để liên kết; cần cập nhật sau khi phát hành.

## Kiểm tra nhanh sau bàn giao

1. Mở [GitHub Pages](https://duy200779.github.io/mld-game-store/) và kiểm tra trang chính cùng ảnh minh họa.
2. Dùng DevTools kiểm tra viewport 320px, 640px, 960px, 1440px; ở 320px xác nhận trang không tràn ngang và vùng bảng cuộn riêng.
3. Dùng `Tab`/`Shift+Tab` kiểm tra focus; xác nhận nút hết hàng không kích hoạt được.
4. Thử form rỗng, email sai định dạng, rồi dữ liệu giả hợp lệ để xem điều hướng tới `ket-qua.html`. Không dùng dữ liệu cá nhân: form GET có thể đưa dữ liệu vào URL.
5. Chỉ sau khi kiểm thử thực tế, lưu minh chứng vào `evidence/` và cập nhật liên kết trong README/AI_LOG. Tạo tag v2 khi mã bàn giao đã được commit, rồi thay liên kết bản mã ở phần đầu bằng tag/commit thật.
