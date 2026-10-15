# **Phần 1: Phân tích và thiết kế giải pháp**

## **1\. Phân tích bài toán (I/O)**

* **Đầu vào (Input):** Thông tin CLB Lập trình PTIT, danh sách ban chuyên môn, hướng dẫn git, task list và quy tắc ứng xử.  
* **Đầu ra (Output):** File README.md hiển thị chuẩn giao diện Wiki, bảng biểu trực quan và link liên kết hoạt động tốt trên GitHub.

## **2\. Đề xuất giải pháp**

* **Phần 1 (Giới thiệu):** Dùng Heading H1, H2 và chữ đậm (\*\*...\*\*).  
* **Phần 2 (Danh sách Ban):** Dùng bảng Markdown 3 cột kết hợp cú pháp \[Email\](mailto:...).  
* **Phần 3 (Hướng dẫn Gia nhập):** Dùng danh sách có thứ tự 1\. 2\. 3\. kết hợp Code Block cho lệnh git.  
* **Phần 4 (Checklist):** Dùng Task List (\- \[x\] và \- \[ \]).  
* **Phần 5 (Lưu ý):** Dùng Blockquote (\>) để làm nổi bật thông báo.

## **3\. Các bước thiết kế**

1. Tạo repository công khai trên GitHub theo định dạng: K26\_IT108\_Session09\_Bai9.  
2. Tạo và mở file README.md trực tiếp trên GitHub hoặc máy cá nhân.  
3. Soạn nội dung từ Phần 1 đến Phần 5 theo chuẩn Markdown.  
4. Kiểm tra bản xem trước (Preview) để đảm bảo không lỗi cú pháp.  
5. Commit code và copy link repository để nộp bài.

# **Phần 2: Triển khai và chống lỗi**

## **4\. Source file README.md hoàn chỉnh**

# **CLB Lập Trình PTIT \- Trang Wiki Thành Viên Mới**

Chào mừng bạn đến với **CLB Lập trình PTIT**\! Nơi hội tụ của những đam mê công nghệ.

## **1\. Giới thiệu CLB**

* **Tên đầy đủ:** Câu lạc bộ Lập trình Học viện Công nghệ Bưu chính Viễn thông.  
* **Sứ mệnh:** **Xây dựng môi trường học tập, chia sẻ kiến thức lập trình thực chiến và hỗ trợ sinh viên chinh phục các cuộc thi công nghệ.**

## **2\. Danh sách Ban chuyên môn**

| Tên Ban | Trưởng Ban | Liên hệ |
| :---- | :---- | :---- |
| Ban Kỹ thuật | Lã Đức Phát | phatld@ptit.edu.vn |
| Ban Truyền thông | Nguyễn Văn A | anvn@ptit.edu.vn |
| Ban Sự kiện | Trần Thị B | btt@ptit.edu.vn |

## **3\. Hướng dẫn Gia nhập CLB**

1. Clone kho lưu trữ tài liệu về máy:

git clone [https\://github.com/ptit-code-club/new-member-guide.git](https://github.com/ptit-code-club/new-member-guide.git)

      2\.    Tạo nhánh làm việc cá nhân:

git checkout \-b feature/ten-cua-ban

      3\.    Đẩy code lên hệ thống: 

git push origin feature/ten-cua-ban

## **4\. Checklist Nhiệm vụ Thành viên Mới**

* \[x\] Điền thông tin cá nhân vào bảng điểm danh.  
* \[x\] Tham gia nhóm chat chính thức của CLB.  
* \[ \] Hoàn thành bài tập lập trình tuần 1\.  
* \[ \] Đọc kỹ nội quy hoạt động CLB.  
* \[ \] Đóng quỹ sinh hoạt học tập đầu kỳ.

## **5\. Lưu ý quan trọng**

> **\[THÔNG BÁO DEADLINE\]:** Hoàn thành toàn bộ task trước **23:59 Chủ Nhật tuần này**. **Quy tắc ứng xử:** Tôn trọng thành viên khác, giữ thái độ cởi mở và chủ động hỏi khi gặp khó khăn.

## **5\. Trả lời 2 bẫy dữ liệu**

* **Bẫy 1:** Phải dùng cú pháp `[email](mailto:...)`. Nếu chỉ viết dạng chữ thường, người dùng không thể click mở ứng dụng gửi mail trực tiếp.  
* **Bẫy 2:** Nếu paste URL không hợp lệ (sai định dạng hoặc thiếu `https://`), link sẽ bị hỏng (broken link), dẫn đến lỗi không thể truy cập hoặc hiển thị sai dạng văn bản thuần túy.

