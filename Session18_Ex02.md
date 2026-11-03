### **1\. Vấn đề**

* **Tình huống:** Shipper hệ thống vận tải bị mất trạng thái đăng nhập và giỏ hàng phụ tùng bị trống mỗi khi đóng trình duyệt hoặc tải lại trang, phải thao tác lại từ đầu.  
* **Nguyên nhân cốt lõi:** Hệ thống đang sử dụng **Session Cookies** sẽ tự động xóa khi đóng trình duyệt thay vì ghi nhớ lâu dài.


### **2\. Yêu cầu**

* **Đầu ra cần thực hiện:**  
  * **Phần 1 (Phân tích):** So sánh đánh đổi giữa Cache (MB/GB) và Cookies (\~4KB).  
  * **Part 2 (Triển khai):** Mô tả cấu trúc mẩu tin Cookie (Token, Max-Age, cờ bảo mật).  
  * **Part 3 (Kiểm thử):** Hướng dẫn Hard Reload xóa Cache khi giao diện không cập nhật màu cũ.  
    

### **3\. Cách làm**

#### **Phần 1\. Phân tích**

* **Cookies (\~4KB):**  
  * *Ưu điểm:* Dung lượng nhỏ, tự động gửi kèm theo mọi HTTP Request lên server, phù hợp lưu trữ mã định danh (Token) người dùng.  
  * *Nhược điểm:* Giới hạn kích thước nghiêm ngặt (khoảng 4KB), không dùng để chứa dữ liệu lớn.  
* **Cache (MB/GB):**  
  * *Ưu điểm:* Dung lượng lưu trữ lớn (hình ảnh, tài nguyên tĩnh), giúp tăng tốc độ tải trang trực tiếp trên trình duyệt.  
  * *Nhược điểm:* Không dùng để xác thực định danh bảo mật và không tự động gửi lên server trong mọi yêu cầu API.  
    

#### **Phần 2\. Triển khai**

Thiết lập mẩu tin Cookie trả về từ Server với các thông số:

* Token: Mã định danh phiên đăng nhập của shipper (ví dụ: auth\_token=xyz123...).  
* Max-Age / Expires: Đặt thời gian sống lâu dài cho Cookie (ví dụ: 2592000 tương đương 30 ngày).  
* HttpOnly: Ngăn chặn mã độc JavaScript (XSS) đọc giá trị Cookie.  
* Secure: Đảm bảo Cookie chỉ được truyền tải qua giao thức HTTPS được mã hóa.


#### **Phần 3\. Kiểm thử**

* **Tình huống:** Giao diện bị kẹt màu cũ do trình duyệt lưu tệp tĩnh trong bộ nhớ đệm (Cache).  
* **Cách khắc phục (Hard Reload):**  
  * Sử dụng tổ hợp phím **Ctrl \+ F5**

