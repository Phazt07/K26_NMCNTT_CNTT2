### **1\. Vấn đề**

* **Bối cảnh:** Nhóm SmartCampus chuẩn bị đẩy mã nguồn lên GitHub công khai để làm portfolio nhưng đang đối mặt với các lỗ hổng bảo mật lớn: dính bẫy Phishing/Crack phần mềm, dùng chung 1 mật khẩu cho nhiều tài khoản tổ chức (GitHub, Vercel, Email), chưa bật 2FA, và để lộ API Key / DB Password dạng hardcode trong code.

### **2\. Yêu cầu**

* **Phần 1:** Nhận diện tấn công (Phishing, Typosquatting), cạm bẫy mã độc crack, áp dụng Quy tắc 5 KHÔNG và 4 Bước Cấp cứu nếu lỡ chạy file độc.  
* **Phần 2:** Phân tích rủi ro khi dùng chung mật khẩu, hiểu về Zero-Knowledge Architecture, và cấu hình thông số Password Generator.  
* **Phần 3:** So sánh SMS OTP với TOTP Authenticator, liệt kê các bước bật 2FA Google Authenticator cho GitHub, và cách quản lý Backup Codes.  
* **Phần 4:** Xử lý bảo mật code bằng cách đưa Secrets ra file .env, cấu hình .gitignore, tạo .env.example và áp dụng Quy tắc kiểm tra trước khi push.


### **3\. Cách làm (Tóm tắt giải pháp chi tiết)**

* **Phần 1 – Xử lý rủi ro & Sự cố:**  
  * *Tình huống 1:* Lỗi **Phishing / Typosquatting** (giả mạo tên miền githuh-security.com). Áp dụng: **KHÔNG click link lạ**.  
  * *Tình huống 2:* Cạm bẫy **Mã độc Crack**. Tắt Windows Defender mở cửa cho mã độc chiếm quyền kiểm soát máy tính. Áp dụng: **KHÔNG tải phần mềm lậu/crack**.  
  * *4 Bước Cấp cứu:* (1) Ngắt kết nối mạng ngay $\rightarrow$ (2) Cô lập máy tính $\rightarrow$ (3) Quét mã độc bằng phần mềm diệt virus/Khôi phục hệ thống $\rightarrow$ (4) Đổi toàn bộ mật khẩu tài khoản quan trọng từ thiết bị sạch.

* **Phần 2 – Password Manager & Generator:**  
  * *Rủi ro:* Lộ email nhóm sẽ dẫn đến kiểu tấn công **Credential Stuffing** (dùng chung mật khẩu để chiếm đoạt GitHub và Vercel).  
  * *Zero-Knowledge:* Máy chủ Bitwarden chỉ lưu dữ liệu đã mã hóa (Ciphertext); khóa giải mã nằm hoàn toàn trên thiết bị người dùng nên hacker không đọc được dù server bị hack.  
  * *Thông số Generator:* Độ dài: **16–32 ký tự** \| Chữ hoa (A-Z): **Có** \| Chữ thường (a-z): **Có** \| Chữ số (0-9): **Có** \| Ký tự đặc biệt (\!@\#...): **Có**.

* **Phần 3 – Kích hoạt 2FA (TOTP):**  
  * *Nhược điểm SMS OTP:* Dễ bị tấn công **SIM Swapping** và phụ thuộc sóng di động (mất sóng/nước ngoài không nhận được). Dùng **TOTP (Authenticator App)** bảo mật và hoạt động offline tốt hơn.  
  * *Các bước bật GitHub 2FA:* Đăng nhập GitHub $\rightarrow$ Settings $\rightarrow$ Password and Authentication $\rightarrow$ Enable two-factor authentication $\rightarrow$ Dùng Google Authenticator quét mã QR $\rightarrow$ Nhập mã 6 số xác nhận.  
  * *Backup Codes:* Lưu nơi an toàn (in ra giấy cất tủ khóa / Password Manager); **Tuyệt đối KHÔNG** lưu ảnh chụp vào điện thoại hay gửi qua chat.

* **Phần 4 – Bảo vệ Secrets & Đẩy Code:**  
  * *2 Secrets bị hardcode:* API\_KEY \= "sk-proj-abc123456789" và DB\_PASSWORD \= "SmartCampus@2026".  
  * *Sửa code:* Dùng process.env.API\_KEY và process.env.DB\_PASSWORD.  
  * *Nội dung 3 file:*  
    * .env: Chứa giá trị thật (API\_KEY=sk-proj-... và DB\_PASSWORD=...).  
    * .gitignore: Thêm dòng .env để ẩn file này khi push.  
    * .env.example: Chỉ chứa tên biến (API\_KEY= và DB\_PASSWORD=) để chia sẻ nhóm.  
  * *Kiểm tra trước khi Push:* Kiểm tra lịch sử git, quét từ khóa nhạy cảm, kiểm tra file .gitignore đã chặn .env chưa, và test lại biến môi trường xem chạy ổn định không.

