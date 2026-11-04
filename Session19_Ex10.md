### 1\. Vấn đề (Bối cảnh bài toán)

* Tình huống: PixelForge Studio chuẩn bị mở bán vật phẩm game (Early Access) và tích hợp cổng thanh toán, đồng thời cấp quyền GitHub Enterprise cho nhân sự. Ban Giám đốc yêu cầu bắt buộc bật 2FA.  
* Tranh luận:  
  * Nhóm A đề xuất dùng SMS OTP vì quen thuộc, tiện lợi.  
  * Nhóm B đề xuất dùng Authenticator App (TOTP) vì bảo mật cao hơn, tránh lỗi thời.  
* Rủi ro & Ràng buộc: Tài sản lớn (doanh thu, mã nguồn gốc), lập trình viên hay đi nước ngoài/làm việc trên máy bay (offline), và đối mặt rủi ro tấn công SIM Swapping (mạo danh, đánh cắp số điện thoại).

### 2\. Yêu cầu đầu ra cần đạt

* Phần 1: Phân tích giải pháp  
  * Phân tích 3 yếu tố xác thực (Something You Know, Have, Are); xác định mật khẩu và mã OTP thuộc yếu tố nào.  
  * Giải thích nguyên lý thuật toán TOTP sinh mã chính xác khi điện thoại bật chế độ máy bay (offline).

* Phần 2: So sánh & Ra quyết định  
  * Lập bảng so sánh Trade-off giữa SMS OTP và TOTP Authenticator (qua 4 tiêu chí: Chống SIM Swapping, Tính sẵn sàng offline, Chi phí/Tiện dụng, Rủi ro mất điện thoại).  
  * Đưa ra kết luận lựa chọn giải pháp tối ưu cho PixelForge Studio.  
      
* Phần 3: Quản lý rủi ro (Backup Codes)  
  * Nêu mục đích của 10 Mã khôi phục (Backup Codes).  
  * Hướng dẫn 2 vị trí lưu trữ an toàn và 1 sai lầm tai hại cần tránh.

### 3\. Cách làm (Hướng dẫn giải chi tiết để nộp bài)

#### Phần 1: Phân tích 2 Giải pháp Xác thực

1. 3 yếu tố xác thực:  
   * Something You Know (Điều bạn biết): Mật khẩu (Password/PIN).  
   * Something You Have (Điều bạn có): Điện thoại, thiết bị nhận OTP, thẻ cứng.  
   * Something You Are (Đặc điểm sinh trắc học): Vân tay, khuôn mặt.  
   * $\rightarrow$ Mật khẩu đại diện cho yếu tố Know, còn mã OTP đại diện cho yếu tố Have.

2. Nguyên lý TOTP Offline:  
   * Ứng dụng Authenticator và máy chủ đã chia sẻ một khóa bí mật (Shared Secret) từ trước qua mã QR. Cả hai cùng dùng chung một công thức toán học kết hợp với thời gian thực hiện tại (Timestamp) chia cho chu kỳ 30 giây. Do đó, dù bật chế độ máy bay, điện thoại vẫn tự tính toán ra đúng mã 6 số trùng khớp với máy chủ mà không cần internet/SMS.

#### Phần 2: So sánh Trade-off & Ra quyết định

3. So sánh:  
   * SMS OTP: Chống SIM Swapping kém, phụ thuộc sóng di động (mất sóng/nước ngoài không nhận được), tốn chi phí doanh nghiệp, dễ mất SIM.  
   * TOTP Authenticator: Bảo mật tuyệt đối (khóa lưu trên chip thiết bị), hoạt động 100% offline, miễn phí 100%, cần quản lý Backup Codes kỹ khi mất máy.  
       
4. Kết luận lựa chọn:  
   * Chọn Giải pháp 2 (TOTP Authenticator).  
   * Lý do: Phù hợp tuyệt đối với tính chất di chuyển liên tục, làm việc trên máy bay của lập trình viên (offline) và ngăn chặn triệt để rủi ro tấn công SIM Swapping nhằm bảo vệ kho mã nguồn và doanh thu trăm ngàn USD.

#### Phần 3: Quản lý Rủi ro & Backup Codes

5. Backup Codes:  
   * Mục đích: Dùng để đăng nhập thay thế khi người dùng mất điện thoại, đổi thiết bị hoặc ứng dụng Authenticator gặp sự cố.  
   * 2 vị trí lưu trữ an toàn: In ra giấy và cất trong tủ khóa cá nhân; Hoặc mã hóa lưu trong một tập tin bảo mật trên Password Manager cá nhân.  
   * 1 sai lầm tai hại cần tránh: Lưu ảnh chụp màn hình chứa Backup Codes trực tiếp vào album ảnh điện thoại hoặc gửi qua ứng dụng chat công khai (Messenger, Zalo, Slack).

