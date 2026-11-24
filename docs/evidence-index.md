# Bảng minh chứng kiểm thử – MLD Game Store v3

Các kiểm thử bên dưới chạy trên máy chủ tĩnh local bằng trình duyệt automation, với viewport CSS được đặt bằng Playwright. Trang không gửi dữ liệu tới dịch vụ thật.

| Em thử gì | Thao tác thực hiện | Kết quả thực tế | Ảnh minh chứng |
|---|---|---|---|
| Tải trang, CSS và ảnh | Mở trang qua máy chủ tĩnh local; kiểm tra phản hồi trang, stylesheet và năm ảnh cục bộ. | Trang trả HTTP 200; năm ảnh tải xong (`complete=true`, `naturalWidth>0`). Đường dẫn asset đều tồn tại. | [01-desktop-1440px.png](./evidence/01-desktop-1440px.png) |
| Menu và nút hết hàng | Bấm lần lượt năm liên kết menu; kiểm tra nút của thẻ Genshin `#GI-0409`. | URL lần lượt tới `#gioi-thieu`, `#danh-muc-acc`, `#bang-gia`, `#quy-trinh`, `#dat-acc`; nút hết hàng có trạng thái disabled. | [01-desktop-1440px.png](./evidence/01-desktop-1440px.png) |
| Responsive và bảng | Kiểm tra viewport 320, 375, 640, 960 và 1440px. | Grid lần lượt 1, 1, 2, 3 và 3 cột. Ở 320px document width = 320px; `.table-wrapper` clientWidth = 286px, scrollWidth = 544px nên cuộn trong wrapper, không tràn toàn trang. 375px document width = 375px. | [02-mobile-375px.png](./evidence/02-mobile-375px.png) |
| Bàn phím và form không hợp lệ | Nhấn Tab hai lần; sau đó thử gửi form rỗng và thử `Duy`, `duy@`, `Chào`. | Focus ở liên kết “Giới thiệu”, outline vàng `rgb(251, 191, 36)`. Form rỗng không hợp lệ; email và nội dung ngắn bị chặn, hai trường có `:user-invalid` và viền đỏ `rgb(185, 28, 28)`. | [03-keyboard-focus-menu.png](./evidence/03-keyboard-focus-menu.png), [04-form-validation-error.png](./evidence/04-form-validation-error.png) |
| Gửi form hợp lệ | Nhập `Mai Lâm Duy`, `duy@example.com`, `Đặt giữ acc #LQ-0102 kèm gói bảo hành Tiêu chuẩn` rồi gửi. | Chuyển tới `ket-qua.html`; URL thực tế có `fullname`, `email`, `message` trong query string và trang hiện tiêu đề xác nhận. Không có lưu đơn/email thật. | [05-form-submit-ket-qua.png](./evidence/05-form-submit-ket-qua.png) |

## Lưu ý về ảnh và phạm vi kiểm thử

- Các ảnh PNG được chụp từ nội dung browser thật ở viewport CSS nêu trên. Browser renderer giới hạn kích thước raster trả về; ảnh được nội suy về kích thước pixel viewport để lưu thành bộ ảnh nhất quán. Không thêm nội dung giao diện vào ảnh.
- Ảnh chụp page không bao gồm thanh địa chỉ của browser. URL GET được đọc trực tiếp từ `page.url()` sau khi submit: `http://127.0.0.1:8000/ket-qua.html?fullname=Mai+L%C3%A2m+Duy&email=duy%40example.com&message=%C4%90%E1%BA%B7t+gi%E1%BB%AF+acc+%23LQ-0102+k%C3%A8m+g%C3%B3i+b%E1%BA%A3o+h%C3%A0nh+Ti%C3%AAu+chu%E1%BA%A9n`. Nếu yêu cầu chấm điểm bắt buộc nhìn thấy thanh địa chỉ, cần chụp bổ sung bằng thao tác hệ điều hành trên cửa sổ trình duyệt.
- Đây là viewport giả lập, không phải thiết bị iPhone vật lý. Kiểm tra thiết bị thật: **Chưa kiểm tra**.
- Đã kiểm tra máy chủ local và assets; cấu hình GitHub Pages trong Settings → Pages: **Chưa kiểm tra**.
