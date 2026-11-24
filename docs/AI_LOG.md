# AI_LOG – MLD Game Store

**Người thực hiện:** Mai Lâm Duy — MSV 2071020214 — CNTT 20-04
**Ngày:** 24/11/2026

Nhật ký này ghi lại các quyết định trong lần chuẩn hóa v3. Lịch sử Git trước đó chỉ có thông điệp commit chung, không có prompt hay biên bản các lượt AI cũ; vì vậy em không hồi dựng những trao đổi hoặc suy nghĩ trước đây. Mã HTML/CSS sản phẩm được giữ nguyên.

**Trạng thái bàn giao hiện tại:** tag `v3` đã được tạo và đẩy lên remote tại commit `8a89bf6145cb78f6c45cd5430422c9f6dd7dcfeb`. Một số nhận định dưới đây ghi rõ trạng thái tại thời điểm bắt đầu chuẩn hóa, trước khi commit/tag v3 được tạo.

| Ngày | Dùng AI làm gì | Em quyết định/sửa lại gì |
|---|---|---|
| 24/11/2026 | Hỗ trợ rà soát cây thư mục, mã nguồn, Git và điều kiện kiểm thử. | Tại thời điểm rà soát ban đầu, chỉ xác nhận v1/v2; không suy diễn rằng v3 đã được phát hành. |
| 24/11/2026 | Hỗ trợ chạy kiểm thử browser ở viewport giả lập và chụp ảnh. | Đối chiếu kết quả đo được; ghi rõ ảnh không có browser chrome và chưa thử iPhone vật lý. |
| 24/11/2026 | Hỗ trợ chuẩn hóa README, CHANGELOG, evidence index và nhật ký AI. | Chỉ thay tài liệu/ảnh minh chứng; không sửa HTML/CSS và không khẳng định nguồn ảnh chưa kiểm chứng độc lập. |

## Lượt 1 – Rà soát source, cây thư mục và lịch sử

1. **Hiện tượng & dữ kiện ban đầu:** repository có `index.html`, `ket-qua.html`, `css/style.css`, năm ảnh, README, AI_LOG và RELEASE_NOTES ở gốc; chưa có `docs/` hoặc `evidence/`. Git log gồm `bf57a4c`, `8b33ea7`, `4321752`; tag remote `v1` và `v2` tồn tại.
2. **Nhận định trước khi hỏi AI:** em cần dựa vào cây file và commit thực tế; không nên tự nhận đã có ảnh minh chứng hay tag v3.
3. **Công cụ/Prompt tóm tắt:** trình trợ lý AI trong môi trường phát triển; yêu cầu đọc source, cây file, git log và chuẩn hóa hồ sơ Lab 8.
4. **Gợi ý từ AI:** lập cây thư mục từ file có thật, kiểm tra literal đường dẫn/secret trong source, lấy commit/tag từ Git và không suy diễn lịch sử sửa code.
5. **Quyết định có lý do của em:** dùng lịch sử Git đã kiểm tra: `4321752` khởi tạo, `8b33ea7` thêm source/ảnh và `bf57a4c` cập nhật bộ tài liệu v2. Không gọi các thay đổi v3 chưa commit là commit phát hành.
6. **Phần đã sửa trong mã nguồn:** không sửa mã nguồn chạy. Chỉ thay README, chuyển AI_LOG vào `docs/`, xóa RELEASE_NOTES ở gốc và tạo CHANGELOG/evidence index.
7. **Cách thử lại và kết quả thực tế:** đã quét source cho `C:\`, `D:\`, `file:///`, `href="/"`, `src="/"` và các literal `password`, `token`, `ghp_`; không có kết quả khớp. Danh sách ảnh và tên file được đối chiếu trực tiếp. Khi xem trang kết quả, class icon Font Awesome không hiện do project không nạp thư viện; em ghi nhận làm giới hạn thay vì sửa code ngoài phạm vi.

## Lượt 2 – Kiểm thử giao diện và biểu mẫu bằng browser

1. **Hiện tượng & dữ kiện ban đầu:** CSS quy định một cột mặc định, hai cột từ 640px, ba cột từ 960px; `.table-wrapper` cuộn ngang riêng; HTML có `:focus-visible`, `:user-invalid`, `required`, email type và form GET.
2. **Nhận định trước khi hỏi AI:** chỉ nhìn CSS/HTML chưa chứng minh hành vi trình duyệt; cần chạy thật ở kích thước đã nêu và ghi nhận các ca form.
3. **Công cụ/Prompt tóm tắt:** browser automation Playwright trên máy chủ tĩnh local; yêu cầu chụp các viewport desktop/mobile, focus bàn phím, lỗi validation và kết quả gửi hợp lệ.
4. **Gợi ý từ AI:** dùng viewport giả lập, kiểm tra `scrollWidth`, số cột, trạng thái focus/disabled, validity và URL sau điều hướng; chụp trạng thái thực tế, không dựng ảnh giao diện.
5. **Quyết định có lý do của em:** dùng dữ liệu mẫu `Duy`, `duy@`, `Chào` và `Mai Lâm Duy`, `duy@example.com`; ghi URL GET riêng vì ảnh chụp page không hiển thị thanh địa chỉ browser.
6. **Phần đã sửa trong mã nguồn:** không sửa HTML/CSS. Lưu năm ảnh vào `docs/evidence/`; các PNG được chuẩn hóa về kích thước pixel viewport sau khi browser trả raster nhỏ hơn viewport CSS.
7. **Cách thử lại và kết quả thực tế:** đã quan sát 320/375/640/960/1440px; ở 320px `documentElement.scrollWidth` bằng 320 và wrapper bảng có scrollWidth 544px so với clientWidth 286px. Menu đi tới đủ năm hash; Tab focus liên kết “Giới thiệu” với viền `rgb(251, 191, 36)`; nút Genshin disabled. Form rỗng bị chặn; `duy@` và “Chào” bị chặn với viền đỏ; form hợp lệ chuyển tới `ket-qua.html` kèm đủ ba tham số. Ảnh tương ứng ở [docs/evidence/](./evidence/).

## Lượt 3 – Chuẩn hóa hồ sơ v3

1. **Hiện tượng & dữ kiện ban đầu:** hồ sơ cũ đặt AI_LOG/RELEASE_NOTES ở root, chưa có bảng evidence; thông điệp Git không lưu chi tiết nguồn gốc/giấy phép của từng ảnh.
2. **Nhận định trước khi hỏi AI:** cần gom tài liệu theo chuẩn Lab 8, nhưng không nên bịa nguồn ảnh, kết quả kiểm thử hoặc commit v3.
3. **Công cụ/Prompt tóm tắt:** trợ lý AI hỗ trợ sắp xếp tài liệu tiếng Việt theo yêu cầu bàn giao v3 và đối chiếu ảnh thực tế.
4. **Gợi ý từ AI:** thay release notes bằng changelog; dùng liên kết tương đối tới evidence; ghi riêng giới hạn form tĩnh, nguồn ảnh chưa xác minh và trạng thái phát hành chưa commit.
5. **Quyết định có lý do của em:** áp dụng cách tổ chức `docs/`; chỉ nêu nguồn ảnh theo thông tin đã cung cấp và đánh dấu URL/giấy phép cụ thể chưa lưu trong repository.
6. **Phần đã sửa trong mã nguồn:** không thay đổi giao diện hay hành vi HTML/CSS; cập nhật README, CHANGELOG, AI_LOG và evidence index.
7. **Cách thử lại và kết quả thực tế:** đã kiểm tra các liên kết tương đối và sự tồn tại của năm ảnh sau khi lưu. Cấu hình nhánh/thư mục trong Settings → Pages và hiển thị trên iPhone vật lý **Chưa kiểm tra**. Tại thời điểm hoàn tất phần nội dung ban đầu, tag v3 chưa được tạo; sau đó hồ sơ và ảnh đã được commit, tag `v3` trỏ tới `8a89bf6`.

## Minh chứng

- [01-desktop-1440px.png](./evidence/01-desktop-1440px.png)
- [02-mobile-375px.png](./evidence/02-mobile-375px.png)
- [03-keyboard-focus-menu.png](./evidence/03-keyboard-focus-menu.png)
- [04-form-validation-error.png](./evidence/04-form-validation-error.png)
- [05-form-submit-ket-qua.png](./evidence/05-form-submit-ket-qua.png)

