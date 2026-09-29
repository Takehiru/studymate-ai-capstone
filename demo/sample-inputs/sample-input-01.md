# Đồ án Lập trình Web - Xây dựng website quản lý thư viện

## 1. Mô tả tổng quan
Sinh viên cần thiết kế và xây dựng một ứng dụng web Quản lý thư viện trường đại học. Hệ thống cho phép sinh viên tra cứu, mượn trả sách và giúp quản trị viên (thủ thư) quản lý kho sách một cách hiệu quả.

## 2. Yêu cầu chức năng
Hệ thống cần đảm bảo tối thiểu các chức năng sau:
- **F01 - Quản lý Tài khoản**: Đăng nhập, đăng ký, phân quyền người dùng (Admin và Student). Cấp lại mật khẩu qua email.
- **F02 - Quản lý Danh mục Sách**: Cho phép Admin Thêm, sửa, xóa sách. Hỗ trợ tìm kiếm sách theo tên, tác giả, thể loại và trạng thái (còn/hết).
- **F03 - Mượn & Trả sách trực tuyến**: Sinh viên có thể tạo yêu cầu mượn sách. Giới hạn mỗi sinh viên chỉ được mượn tối đa 3 cuốn cùng lúc, thời hạn mượn không quá 14 ngày.
- **F04 - Quản lý quá hạn & Phạt**: Tự động tính tiền phạt đối với sách quá hạn. Mức phạt là 5,000 VNĐ/ngày/cuốn.
- **F05 - Báo cáo thống kê (Admin)**: Dashboard thống kê sách mượn nhiều nhất trong tháng, số lượng sinh viên nợ sách, doanh thu tiền phạt.

## 3. Yêu cầu phi chức năng
- **Frontend**: Khuyến khích sử dụng ReactJS, VueJS hoặc Angular.
- **Backend**: Có thể dùng Node.js (Express/NestJS) hoặc Python (Django/FastAPI).
- **Database**: Sử dụng cơ sở dữ liệu quan hệ (MySQL hoặc PostgreSQL).
- **Performance**: Giao diện responsive (hoạt động tốt trên điện thoại di động). Thời gian phản hồi của API không quá 1 giây.

## 4. Thời hạn nộp bài (Deadline)
- 15/12/2026 (23:59 GMT+7). Hệ thống sẽ tự động đóng sau thời gian này.

## 5. Tiêu chí chấm điểm (Thang điểm 10)
- **4 điểm**: Hoàn thành xuất sắc các chức năng cốt lõi (F01 đến F04).
- **2 điểm**: Chức năng nâng cao (F05) và giao diện UI/UX trực quan, đẹp mắt.
- **2 điểm**: Source code sạch, tuân thủ Clean Code, có comments đầy đủ và áp dụng thiết kế RESTful API chuẩn mực.
- **2 điểm**: Báo cáo tài liệu (Report) chi tiết, đúng chuẩn và trình bày bảo vệ đồ án lưu loát.

## 6. Format nộp bài
- Nén toàn bộ mã nguồn vào file ZIP. Đặt tên theo cú pháp: `MSSV_HoVaTen.zip`.
- Kèm theo 1 file `README.md` hướng dẫn chi tiết cách cài đặt biến môi trường và chạy dự án.
- Kèm theo 1 file `Bao_Cao.pdf` (tối đa 15 trang). Nộp toàn bộ trên cổng Elearning của trường.
