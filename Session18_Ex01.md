1. Vấn đề  
* Nam gõ nhầm địa chỉ `phong-dieu-phoi.grenlog.vn` (thiếu chữ 'e') để truy cập trang quản trị.  
* Lỗi : Trình duyệt báo lỗi  
* Nam đổ lỗi cho máy chủ nhưng thực ra là do Nam gõ sai tên miền nên không tìm được tên miền → server trả về lỗi **404 Not Found**  
2. Yêu cầu  
* Xác định Input (Tên miền) / Output (IP address) và mô tả sơ đồ luồng dữ liệu của DNS.  
* Đề xuất quy trình kiểm tra mã trạng thái HTTP Status Code để xác nhận xem yêu cầu đã chạm tới máy chủ hay chưa.  
* Giả định Nam sửa đúng tên miền nhưng vẫn nhận mã **404 Not Found**, hệ thống đang gặp vấn đề gì?  
3. Cách làm

####       **Phần 1\. Phân tích (DNS Lookup & Luồng dữ liệu)**

* **Input / Output:** Input là tên miền greenlog.vn $\rightarrow$ Output là Địa chỉ IP của máy chủ (ví dụ: 192.0.2.1).  
* **Sơ đồ luồng dữ liệu DNS:**  
  1. **Browser Cache:** Trình duyệt kiểm tra xem đã từng lưu IP của tên miền này chưa.  
  2. **OS Cache / Hosts File:** Kiểm tra bộ nhớ cache của hệ điều hành.  
  3. **DNS Resolver (ISP):** Nếu không có, máy tính hỏi nhà mạng (Internet Service Provider).  
  4. **Root Server $\rightarrow$ TLD Server (.vn) $\rightarrow$ Authoritative DNS Server:** Hệ thống phân giải lần lượt truy vấn qua các cấp máy chủ cấp cao để tìm ra IP chính xác của tên miền.

#### **Phần 2\. Triển khai (Phân biệt lỗi & Kiểm tra HTTP Status Code)**

* **Phân biệt lỗi:**  
  1. **Lỗi DNS (NXDOMAIN):** Lỗi ở phía **Client** (do gõ sai tên miền hoặc DNS chưa được đăng ký). Yêu cầu chưa hề chạm được tới máy chủ.  
  2. **Lỗi 500 (Internal Server Error):** Lỗi ở phía **Server** (máy chủ công ty nhận được yêu cầu nhưng gặp sự cố xử lý bên trong mã nguồn/database).  
* **Quy trình kiểm tra HTTP Status Code:**  
  1. Nhấn F12 trên trình duyệt $\rightarrow$ Chọn tab **Network**.  
  2. Tải lại trang và quan sát cột **Status**.  
  3. Nếu trạng thái trả về:  
     * 200 OK: Kết nối thành công.  
     * 4xx (Ví dụ: 404, 403): Yêu cầu đã chạm tới máy chủ nhưng sai đường dẫn hoặc không có quyền.  
     * 5xx (Ví dụ: 500): Máy chủ thực sự gặp sự cố hệ thống.

#### **Phần 3\. Kiểm thử (Xử lý lỗi 404 Not Found)**

* **Vấn đề:** Khi Nam đã sửa đúng tên miền nhưng hệ thống vẫn trả về mã 404 Not Found.  
* **Nguyên nhân:**  
  * Yêu cầu đã kết nối thành công đến máy chủ (tên miền đúng, DNS hoạt động tốt).  
  * Tuy nhiên, **đường dẫn cụ thể (URL path) bên trong trang web không tồn tại** (do gõ sai đường dẫn trang quản trị, hoặc trang đã bị xóa/di dời).

    