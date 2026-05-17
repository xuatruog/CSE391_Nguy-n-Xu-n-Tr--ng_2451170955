# GIẢI ĐÁP PHIẾU BÀI TẬP 03
**Họ tên:** Nguyễn Xuân Trường  
**Mã sinh viên:** 2451170955

## PHẦN A — KIỂM TRA ĐỌC HIỂU

### Câu A1: 3 Cách nhúng CSS
1. **Inline CSS:** Viết trực tiếp vào thuộc tính `style` của thẻ.
   - VD: `<h1 style="color: blue;">Chào Trường</h1>`
   - Ưu: Nhanh, độ ưu tiên cao nhất. Nhược: Khó quản lý, code rối.
2. **Internal CSS:** Viết trong thẻ `<style>` ở phần `<head>`.
   - VD: `<style> p { color: red; } </style>`
   - Ưu: Gom code vào 1 file HTML. Nhược: Không tái sử dụng được cho trang khác.
3. **External CSS:** Viết ra file `.css` riêng và link vào.
   - VD: `<link rel="stylesheet" href="style.css">`
   - Ưu: Dễ quản lý, chuyên nghiệp. Nhược: Tốn thêm 1 lượt tải file.
**=> Nếu trùng, Inline sẽ thắng.**

### Câu A2: Dự đoán Selectors
1. `h1` → ShopTLU
2. `.price` → 25.990.000đ và 45.990.000đ
3. `#app header` → Toàn bộ nội dung trong header
4. `nav a:first-child` → Home
5. `.product.featured h2` → MacBook Pro
6. `article > p` → Các thẻ p (giá và mô tả) trong article
7. `a[href="/"]` → Home
8. `.top-bar.dark h1` → ShopTLU

### Câu A3: Tính toán Box Model
- **Trường hợp 1 (content-box):** Chiều rộng hiển thị = 450px. Không gian chiếm = 470px.
- **Trường hợp 2 (border-box):** Chiều rộng hiển thị = 400px. Content thực tế = 350px. Không gian chiếm = 420px.
- **Trường hợp 3 (Margin collapse):** Khoảng cách = 40px (lấy số lớn nhất).
- **Nâng cao:** Khoảng cách = 30px (40 + (-10)).

### Câu A4: Specificity
1. Điểm: Rule A(0,0,1), Rule B(0,1,0), Rule C(1,0,0), Rule D(0,1,1).
2. Màu đỏ (Rule C thắng vì có ID).
3. Màu cam (Inline style mạnh hơn ID).
4. Màu đen (Vì !important phá vỡ mọi quy tắc độ ưu tiên).

---

## PHẦN C — DEBUG & SUY LUẬN

### Câu C1: Debug Layout
1. Chiều rộng thực: Sidebar (342px), Content (722px). Tổng = 1064px > 960px nên bị vỡ.
2. Cách sửa 1: Thêm `box-sizing: border-box;` cho cả hai.
3. Cách sửa 2: Giảm Width của Content xuống còn 598px.

### Câu C2: Cascade Puzzle
1. Sản phẩm A: 20px / Green (!important thắng).
2. Mô tả SP: Blue (Inherit từ .card).
3. Sản phẩm B: 20px / Red (#featured .title mạnh hơn .title).
4. Mô tả SP B: Green (!important thắng).