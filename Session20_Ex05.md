### **1\. Vấn đề**

* **Mục tiêu:** Thiết kế hệ thống đăng nhập và giao dịch cho ví tiền điện tử (Crypto Wallet) đạt độ bảo mật tối đa, vô hiệu hóa hoàn toàn nguy cơ bị mất tài sản ngay cả khi hacker đã đánh cắp được mật khẩu (Password).  
* **Ràng buộc:** Bắt buộc áp dụng mô hình bảo thực đa lớp (MFA) kết hợp thuật toán mật khẩu một lần dựa trên thời gian (TOTP).


### **2\. Yêu cầu đầu ra**

* **Thiết kế kiến trúc (3 lớp bảo vệ):**  
  * *Lớp 1 (Knowledge \- Sơ cấp):* Mật khẩu đăng nhập mạnh \+ Salt/Hashing (ngăn chặn tấn công brute-force cơ bản).  
  * *Lớp 2 (Possession \- Trung cấp):* Thiết bị tin cậy hoặc ứng dụng xác thực cá nhân (như Google Authenticator/Authy) sinh mã TOTP 30 giây/lần.  
  * *Lớp 3 (Inherence / Dynamic Context \- Nâng cao):* Xác thực sinh trắc học (Vân tay/FaceID) hoặc khóa phần cứng phụ (Hardware Key/Phê duyệt giao dịch trên thiết bị gốc).

* **Xử lý tình huống ngoại lệ (Edge Case):**  
  * *Tình huống:* Người dùng ở trên máy bay, không có Internet hay sóng điện thoại để nhận mã OTP qua SMS hay thông báo mạng.  
  * *Giải pháp:* Sử dụng thuật toán **TOTP (Time-based One-Time Password)** chạy ngoại tuyến hoàn toàn trên thiết bị di động (như Google Authenticator). Ứng dụng tự tính toán mã OTP dựa vào bộ đếm thời gian thực của thiết bị và khóa bí mật đã đồng bộ từ trước mà không cần kết nối mạng.

### **3\. Cách làm (Triển khai & Sơ đồ)**

* **Sơ đồ luồng dữ liệu (Data Flow):**  
* $NgườidùngnhậpPass(Lớp1)$  
* $\Downarrow (Đúng)$  
* $YêucầunhậpmãTOTPtừAppOffline(Lớp2)$  
* $\Downarrow (Đúng)$  
* $XácthựcSinhtrắchọc/Phầncứngkhikýgiaodịch(Lớp3)$  
* $\Downarrow (Thànhcông)\rightarrow Truycập/GiaodịchVí$

