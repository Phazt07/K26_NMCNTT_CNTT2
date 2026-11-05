### 1\. Vấn đề

* Ký tự lạ: Trong URL `[https://githúb.com/login](https://githúb.com/login)`, ký tự `ú` (`u` mang dấu sắc, mã Unicode: `U+00FA`) là ký tự Unicode đặc biệt được dùng thay cho chữ `u` chuẩn (`U+0075`).  
* Tại sao đánh lừa được người dùng: Ký tự này có hình dáng hiển thị gần như hoàn toàn giống chữ `u` bình thường. Kẻ xấu dùng thủ thuật này (Homograph Attack) để tạo ra các trang web lừa đảo có tên miền nhìn y hệt trang chính thức nhằm chiếm đoạt Master Password.

### 2\. Yêu cầu của bài tập

* Chỉ ra và giải thích bản chất ký tự Unicode gây nhầm lẫn trong URL.  
* Đề xuất quy trình kiểm tra URL trước khi nhập mật khẩu.  
* Nộp báo cáo phân tích lên kho lưu trữ GitHub theo đúng định dạng tên quy định `[Tên Lớp]_[Môn Học]_Session19_Ex01`.

### 3\. Cách làm

* Phân tích & Viết nội dung  
  * Giải thích cơ chế tấn công Homograph Attack dựa trên ví dụ trên.  
  * Xây dựng quy trình kiểm tra nhanh: Quan sát trực quan, sử dụng công cụ mã hóa/giải mã ký tự (Punycode converter) để phát hiện ký tự quốc tế ẩn, và luôn ưu tiên dùng Password Manager (trình quản lý tự động điền) vì chúng không bị lừa bởi các ký tự giả mạo này.

