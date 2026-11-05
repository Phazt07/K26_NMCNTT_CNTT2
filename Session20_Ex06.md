### 1\. Vấn đề

* Mục tiêu: Ngăn chặn tuyệt đối việc rò rỉ các thông tin nhạy cảm (API Keys, mật khẩu cơ sở dữ liệu, token hệ thống) khi đẩy mã nguồn dự án thương mại điện tử lên kho lưu trữ GitHub Public.  
* Rủi ro cốt lõi: Nếu thiếu tệp .gitignore hoặc cấu hình sai, các khóa bảo mật bị hardcode sẽ bị quét tự động bởi bot của hacker chỉ trong vòng vài phút sau khi public repo, dẫn đến thất thoát dữ liệu và tài chính của doanh nghiệp.

### 2\. Yêu cầu

* Xây dựng Pre-push Checklist: Tạo danh sách kiểm tra các bước tự động hoặc thủ công để quét và làm sạch API Keys trước khi git push.  
* Cấu hình môi trường: Thiết lập tệp .env.example chuyên nghiệp, tách biệt rõ ràng các biến môi trường cho 3 môi trường: Dev, Test, và Production.  
* Chính sách bảo mật tài khoản: Hướng dẫn toàn bộ team kích hoạt tính năng Xác thực hai lớp (2FA) bắt buộc cho tài khoản tham gia repository.  
* Yêu cầu đầu ra:  
  * Tạo một GitHub Repository mẫu đúng chuẩn tên: \[TênLớp\]\_\[MônHọc\]\_Session19\_Ex06.  
  * Viết báo cáo đánh giá rủi ro về hậu quả nghiêm trọng nếu không sử dụng tệp .gitignore.

### 3\. Cách làm (Triển khai)

* Bước 1: Cấu hình .gitignore chuẩn  
  * Tạo tệp .gitignore ở thư mục gốc của dự án để loại trừ các tệp nhạy cảm:  
    node\_modules/  
    .env  
    .env.local  
    .env.production  
    \*.log

* Bước 2: Tạo tệp mẫu .env.example

  PORT=3000

  DB\_HOST=localhost

  DB\_USER=root

  DB\_PASSWORD=

  API\_KEY=your\_api\_key\_here


* Bước 3: Thiết lập Pre-push Hook / Kiểm tra thủ công  
  * Sử dụng các công cụ như git-secrets hoặc trufflehog quét mã nguồn trước khi push, hoặc rà soát thủ công toàn bộ từ khóa api\_key, password trong code.

* Bước 4: Bật 2FA và Nộp bài  
  * Yêu cầu team bật 2FA trong phần Settings \-\> Password and authentication trên GitHub.