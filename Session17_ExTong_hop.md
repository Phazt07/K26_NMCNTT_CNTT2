### **PHẦN 1: VẤN ĐỀ**

* **Bối cảnh:** Bạn đang thực hiện bài tập thực hành trên trình duyệt Chrome liên quan đến quản lý Profile, bộ nhớ Cache, Cookies và các công cụ DevTools để phục vụ công việc phát triển phần mềm và tối ưu hóa hệ thống.

### **PHẦN 2: YÊU CẦU**

1. **Thiết lập và phân tích:** Xử lý xung đột phiên đăng nhập bằng mô hình nhiều Profile và quản lý Bookmark hiệu quả.  
2. **Cấu hình tiện ích:** Lựa chọn Extension phù hợp để đọc dữ liệu JSON và thiết lập quyền truy cập trang web an toàn.  
3. **Phân tích mạng:** Hiểu rõ 4 giai đoạn HTTP Request, phân biệt mã lỗi `404` và `500` trên Tab Network.  
4. **Quản lý Cache & Cookies:** Khắc phục lỗi hiển thị giao diện cũ do Cache và phòng tránh rủi ro bảo mật liên quan đến Cookie.  
5. **Debug trực quan:** Thao tác chỉnh sửa giao diện với DevTools và quy trình gỡ lỗi API trên Tab Network.

### **PHẦN 3: CÁCH LÀM**

#### **1\. Quản lý Profile và Bookmark**

* **Xử lý xung đột:** Tách biệt hoàn toàn các tài khoản công việc và cá nhân bằng cách tạo các Profile Chrome độc lập để tránh việc ghi đè Cookies/Session Storage.  
* **Mô hình Profile:** Phân chia rõ ràng (Profile cá nhân, Profile công việc, Profile thử nghiệm).  
* **Cây Bookmark:** Tổ chức thành các thư mục chuyên biệt (Work\_Internal, Dev\_Tools, Docs\_Reference) kèm thao tác ẩn tên (Favicon-Only) để tối ưu không gian hiển thị.  
* **Khách mượn máy:** Sử dụng Guest Profile khi có đồng nghiệp mượn máy tạm thời để đảm bảo tự động xóa sạch dữ liệu khi đóng cửa sổ.

#### **2\. Cấu hình Extension và Quyền Site Access**

* **Lựa chọn:** Chọn nhóm tiện ích thuộc **Dev Suite** (như JSON Viewer) để định dạng dữ liệu dạng cấu trúc rõ ràng.  
* **Quyền truy cập:** Cấu hình Site Access ở mức **On click** nhằm kiểm soát chặt chẽ thời điểm Extension được phép chạy trên trang web.

#### **3\. Phân tích Luồng HTTP Request và Mã Lỗi**

* **4 giai đoạn:** DNS Lookup \-\> TCP/TLS Handshake \-\> HTTP Request & Response \-\> Rendering Pipeline.  
* **Mã trạng thái:**  
  * `404 Not Found`: Lỗi do sai đường dẫn hoặc tài nguyên không tồn tại (Phía Client).  
  * `500 Internal Server Error`: Lỗi do hệ thống máy chủ hoặc cơ sở dữ liệu gặp sự cố (Phía Server).  
* **Công cụ kiểm tra:** Sử dụng **Network Tab** trong DevTools để theo dõi toàn bộ request và mã trạng thái theo thời gian thực.

#### **4\. Xử lý Cache và Bảo Mật Cookie**

* **Lỗi giao diện cũ (F5):** Nhấn **Ctrl \+ F5** (Hard Reload) để bắt trình duyệt tải lại toàn bộ tài nguyên mới từ server, bỏ qua bộ nhớ đệm (Browser Cache).  
* **Rủi ro bảo mật:** Cookie thiếu thuộc tính `HttpOnly` dễ bị tấn công XSS đánh cắp phiên đăng nhập thông qua mã độc JavaScript.  
* **Xóa phiên làm việc:** Truy cập Tab Application, xóa thủ công mục `session_id` trong Cookies nhưng vẫn giữ lại các tài nguyên Cache khác nếu cần.

#### **5\. Debug trực quan và Network Tab**

* **Sửa giao diện trực tiếp:** Dùng tính năng **Inspect** để thay đổi thuộc tính CSS (ví dụ: `background-color`) trên Tab Elements nhằm kiểm chứng giao diện tạm thời.  
* **Quy trình debug API (4 bước):** Reproduce (Tái hiện lỗi) \-\> Capture (Chọn request lỗi màu đỏ) \-\> Inspect (Kiểm tra Headers/Response) \-\> Fix/Report (Báo cáo lỗi backend).  
* **Tối ưu Network Tab:** Bật bộ lọc **Fetch/XHR** để chỉ hiển thị API và tích chọn **Disable cache** để phục vụ việc test code liên tục.

