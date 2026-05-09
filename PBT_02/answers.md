# GIẢI ĐÁP PHIẾU BÀI TẬP 02
**Họ tên:** Nguyễn Xuân Trường  
**Mã sinh viên:** 2451170955

## PHẦN A — KIỂM TRA ĐỌC HIỂU

### Câu A1 — 10 Input Types trong HTML5
1. `type="email"` → Ô nhập văn bản, tự kiểm tra có @ → Dùng cho form đăng ký.
2. `type="password"` → Ẩn ký tự nhập vào → Dùng nhập mật khẩu.
3. `type="number"` → Có nút tăng giảm số → Dùng chọn số lượng sản phẩm.
4. `type="tel"` → Hiện bàn phím số trên điện thoại → Dùng nhập số điện thoại.
5. `type="date"` → Hiển thị bảng chọn ngày → Dùng chọn ngày giao hàng.
6. `type="color"` → Chọn màu từ bảng màu → Dùng chọn màu sắc sản phẩm.
7. `type="range"` → Thanh trượt kéo → Dùng lọc khoảng giá sản phẩm.
8. `type="file"` → Nút chọn tệp từ máy tính → Dùng tải ảnh đại diện.
9. `type="search"` → Ô nhập có nút xóa nhanh → Dùng thanh tìm kiếm.
10. `type="checkbox"` → Ô tích chọn nhiều → Dùng chọn danh mục yêu thích.

### Câu A2 — Dự đoán Validation
* **Trường hợp 1:** Báo lỗi "Please fill out this field" do `required` mà giá trị rỗng.
* **Trường hợp 2:** Báo lỗi "Please enter an email address" do thiếu định dạng `@`.
* **Trường hợp 3:** Báo lỗi "Value must be less than or equal to 10" do 15 vượt `max`.
* **Trường hợp 4:** Báo lỗi "Please match the requested format" do chữ không khớp `pattern` số.
* **Trường hợp 5:** Báo lỗi "Please lengthen this text to 8 characters or more" do `123` quá ngắn.

### Câu A3 — Accessibility
1. `<label for="email">` giúp screen reader đọc tên trường cho người khiếm thị và giúp click vào nhãn tự focus vào ô nhập.
2. Dùng `<fieldset>` + `<legend>` khi cần nhóm các thông tin liên quan (VD: Thông tin thanh toán).
3. `aria-label` dùng cho các nút chỉ có icon. Không dùng chung với `<label>` để tránh lặp thông tin cho screen reader.

### Câu A4 — Media
1. `loading="lazy"` giúp trì hoãn tải ảnh ngoài màn hình, cải thiện tốc độ trang. Không dùng cho ảnh đầu trang.
2. Nhiều `<source>` giúp trình duyệt chọn định dạng tốt nhất (MP4, WebM, Ogg).
3. `alt` để mô tả ảnh khi không tải được:
   - iPhone 16: `alt="iPhone 16 màu Titan Sa mạc mặt trước và sau"`
   - Trang trí: `alt=""`
   - Biểu đồ: `alt="Biểu đồ cột doanh thu Q1/2026 tăng trưởng 15%"`

### Câu A5 — So sánh `<figure>` vs `<img>`
- **Cách 1 (img):** Dùng cho ảnh minh họa đơn thuần trong bài viết.
- **Cách 2 (figure):** Dùng khi ảnh cần có chú thích đi kèm (figcaption) hoặc là một thực thể độc lập.

---

## PHẦN C — PHÂN TÍCH & SUY LUẬN

### Câu C1 — Debug Form (8 lỗi)
- Lỗi 1: Dòng 2 — Input "Tên" không có `<label for="...">`, vi phạm accessibility.
  - Sửa: `<label for="name">Tên:</label> <input type="text" id="name" id="name">`
- Lỗi 2: Dòng 4 — Email thiếu thuộc tính `name` và `required`.
  - Sửa: `<input type="email" id="email" name="email" required>`
- Lỗi 3: Dòng 6 — Password thiếu `minlength`.
  - Sửa: `<input type="password" name="pwd" minlength="8">`
- Lỗi 4: Dòng 9 — Phone dùng `type="text"`.
  - Sửa: `<input type="tel" name="phone" pattern="[0-9]{10}">`
- Lỗi 5: Dòng 11 — `<select>` thiếu thuộc tính `name`.
- Lỗi 6: Dòng 12-13 — Các `<option>` thiếu thuộc tính `value`.
- Lỗi 7: Dòng 16 — Label không bọc input checkbox.
  - Sửa: `<input type="checkbox" id="agree" required> <label for="agree">Tôi đồng ý...</label>`
- Lỗi 8: Dòng 1 — Thẻ `<form>` thiếu `action` và `method`.

### Câu C2 — Thiết kế chiến lược Validation
1. Pattern: `[0-9]{12}` (CCCD) và `[0-9]{10,15}` (STK).
2. HTML5 validation chưa đủ an toàn vì có thể bị bypass qua Inspect Element.
3. 3 loại JS validation: So sánh 2 trường, check dữ liệu tồn tại trong DB, logic ngày tháng phức tạp.
4. Rủi ro: Sai lệch dữ liệu (Data Integrity) và bị tấn công SQL Injection/XSS.