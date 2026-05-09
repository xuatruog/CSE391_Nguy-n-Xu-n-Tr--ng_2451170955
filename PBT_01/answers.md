Câu A1.HTTP & Browser
DNS Lookup: Trình duyệt tìm địa chỉ IP của shopee.vn (giống như tìm số nhà trước khi đi).

Gửi Request: Yêu cầu từ laptop qua router WiFi, chạy xuyên cáp quang dưới đáy biển để đến server của Shopee.

Server xử lý: Server nhận lệnh "Người dùng muốn xem trang chủ" và xử lý dữ liệu.

Gửi Response: Server phản hồi, gửi dữ liệu chạy ngược lại qua cáp quang về laptop.

Render: Chrome nhận các file HTML, CSS, JS và vẽ ra giao diện Shopee để mình lướt.

Câu A2.Semantic HTML
Đầu trang: Thay <div class="header"> bằng <header>.

Nội dung chính: Thay <div class="main"> bằng <main>.

Khối sản phẩm: Thay <div class="product"> bằng <article> (vì mỗi sản phẩm là một nội dung độc lập).

Chân trang: Thay <div class="footer"> bằng <footer>.

Lợi ích: Tốt cho SEO, giúp trình duyệt hiểu cấu trúc trang và hỗ trợ người khiếm thị.

Câu A3. Block vs Inline
Hộp 1, 2, 3: Là phần tử Block nên luôn tự xuống dòng và chiếm hết chiều ngang.

Text A, B, C, D: Là phần tử Inline nên hiển thị nối tiếp nhau trên cùng một dòng, chỉ chiếm diện tích vừa đủ nội dung.

Câu A4. Table
<thead>: Chứa phần tiêu đề của bảng, thường là đầu bảng.
<tbody>: Chứa nội dung chính của bảng, giữa bảng.
<tfoot>: Chứa phần cuối bảng, thường dùng tổng kết.
 KHÔNG NÊN dùng table để tạo layout trang web vì:
     1. HTML5 cung cấp các thẻ để xây dựng bố ccuj nếu sử dụng table thì sẽ phá vơ đi tiêu chuẩn 
     2. Khó tương thích tương thích với điện thoại dó các thẻ trong table vô cùng cứng ngắt
     3. Nếu như table phức tạp sẽ tốn nhiều thời gian tải trang hơn
     4. Khó co giãn trên điện thoại hoặc màn hình nhỏ, dễ bị tràn nội dung

Phần C:
    C2:
    Tối ưu hóa cấu trúc Web: Tại sao không nên lạm dụng thẻ <div>?
Quan điểm “chỉ cần dùng <div> cho mọi thứ rồi định danh bằng class” tuy có vẻ tiện lợi nhưng lại là một sai lầm về mặt kỹ thuật. <div> vốn là một thẻ trung tính, hoàn toàn không mang ý nghĩa về mặt nội dung. Ngược lại, các thẻ Semantic HTML như <header>, <nav>, <main>, <article> đóng vai trò như "nhãn dán", giúp trình duyệt và các công cụ tìm kiếm nhận diện rõ ràng cấu trúc của trang web.

Thứ nhất là về SEO (Tối ưu hóa tìm kiếm). Các thuật toán của Google dựa trên cấu trúc HTML để phân loại thông tin. Chẳng hạn, một bài viết được bao bọc trong thẻ <article> đi kèm tiêu đề <h1> sẽ có độ ưu tiên cao và được lập chỉ mục (index) chính xác hơn so với việc lồng ghép trong những khối <div> vô hồn. Điều này trực tiếp giúp trang web có thứ hạng tốt hơn trên kết quả tìm kiếm.

Thứ hai là khả năng tiếp cận (Accessibility). Đối với người khiếm thị sử dụng trình đọc màn hình (screen reader), Semantic HTML là "bản đồ" dẫn đường. Nhờ các thẻ như <nav> hay <main>, họ có thể nhanh chóng nhảy đến menu hoặc đi thẳng vào nội dung chính thay vì phải nghe trình đọc quét qua hàng loạt khối <div> không tên, gây mất thời gian và giảm trải nghiệm.

Tuy nhiên, <div> không hề vô dụng. Nó vẫn là lựa chọn hàng đầu khi bạn cần một container để dàn trang với Flexbox/Grid, hoặc dùng làm "vỏ bọc" để xử lý hiệu ứng CSS và tương tác JavaScript.