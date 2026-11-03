### **1\. Vấn đề**

* **Tình huống:** Quản trị viên điều phối gặp xung đột phiên đăng nhập (Session Conflict) do dùng chung một cửa sổ trình duyệt cho 3 tài khoản: cá nhân, quản trị GreenLog, và kiểm thử (Sandbox).  
* **Nguyên nhân cốt lõi:** Các tài khoản chia sẻ chung không gian lưu trữ trình duyệt, dẫn đến việc ghi đè cookie và trạng thái đăng nhập lẫn nhau.


### **2\. Yêu cầu**

* **Cách ly dữ liệu:** Thiết lập mô hình 3 Profile độc lập (Personal \- Work \- Sandbox) để triệt tiêu hoàn toàn rủi ro văng tài khoản.  
* **Tổ chức Bookmark:** Xây dựng cấu trúc cây thư mục Bookmark khoa học để truy cập nhanh các công cụ như GitHub, Canvas LMS và Portal công ty.  
* **Bảo mật:** Đảm bảo mật khẩu và lịch sử web của Profile cá nhân không bao giờ xuất hiện khi đang trình chiếu ở Profile công việc.


### **3\. Cách làm**

#### **Phần 1\. Phân tích**

* **Incognito Mode**  
  * *Đặc điểm:* Lưu trữ trạng thái tạm thời trên RAM, tự động xóa sạch cookie, lịch sử và cache ngay khi đóng cửa sổ.  
  * *Hạn chế:* Không thể lưu giữ phiên đăng nhập lâu dài hay đồng bộ hóa dữ liệu.  
* **Dedicated Profile**  
  * *Đặc điểm:* Lưu trữ lâu dài trên ổ cứng, tách biệt hoàn toàn cookie, lịch sử, extension và mật khẩu giữa các profile.  
  * *Ưu điểm:* Giải quyết triệt để xung đột phiên đăng nhập và cho phép đồng bộ hóa cá nhân hóa.  
    

#### **Phần 2\. Triển khai**

* **Quy trình tạo Profile:** Thêm mới profile riêng biệt cho từng mục đích (Personal, Work, Sandbox) trong trình duyệt.  
* **Đồng bộ hóa Cloud Sync:** Đăng nhập tài khoản Google tương ứng vào từng profile để kích hoạt đồng bộ hóa đám mây (Cloud Sync), giúp bảo vệ và khôi phục toàn bộ cấu trúc thư mục Bookmark, mật khẩu ngay cả khi thay đổi máy tính mới.


#### **Phần 3\. Kiểm thử**

* **Tình huống:** Cần sử dụng trình duyệt trên một thiết bị lạ hoặc máy tính công cộng mà không để lộ thông tin cá nhân.  
* **Giải pháp (Guest Profile):**  
  * Sử dụng tính năng **Guest Mode** (Chế độ Khách).

