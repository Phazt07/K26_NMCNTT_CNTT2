### **PHẦN 1: VẤN ĐỀ**

* **Sự cố:** Bệnh nhân A xem kết quả xét nghiệm (`/records/patient8821`) trên CarePulse nhưng bị lỗi. Thực tập sinh làm biên bản giải trình sai lệch nghiêm trọng về kiến trúc mạng và nguyên lý xử lý dữ liệu.

### **PHẦN 2: YÊU CẦU**

1. Chỉ ra 4 điểm sai kỹ thuật của thực tập sinh (DNS, TCP/TLS, mã lỗi HTTP, DevTools).  
2. Phân tích lỗi `500` vs `404` và hậu quả tâm lý đối với bệnh nhân.  
3. Viết lại biên bản chuẩn theo 4 bước vòng đời HTTP Request.  
4. Giải thích vì sao sửa chữ trên Tab Elements không thay đổi được Database máy chủ.

### **PHẦN 3: CÁCH LÀM (LỜI GIẢI NGẮN GỌN)**

#### **1\. Bốn điểm sai lệch kỹ thuật:**

* **Bước 1 (DNS):** Nghĩ không cần DNS. *(Thực tế: Bắt buộc dùng DNS để dịch tên miền thành IP).*  
* **Bước 2 (TCP/TLS):** Nghĩ HTTPS mở kết nối không cần bắt tay. *(Thực tế: Phải qua TCP Handshake & TLS Handshake).*  
* **Bước 3 (Mã lỗi):** Gán lỗi database sập thành `404 Not Found`. *(Thực tế: Phải là `500 Internal Server Error`).*  
* **Bước 4 (DevTools):** Tưởng sửa chữ trên Tab Elements là đổi được database gốc. *(Thực tế: Chỉ sửa trên RAM cục bộ).*

#### **2\. Phân tích mã lỗi & Hậu quả:**

* **Mã `500`:** Dùng khi máy chủ/database phía backend gặp sự cố đột ngột.  
* **Hậu quả tâm lý:** Dùng nhầm mã `404` khiến bệnh nhân hoảng loạn tưởng hồ sơ bị xóa vĩnh viễn, làm sụt giảm uy tín hệ thống y tế.

#### **3\. Biên bản giải trình chuẩn (4 bước HTTP Request):**

* **Bước 1 (DNS Lookup):** Trình duyệt dịch `carepulse.vn` sang địa chỉ IP máy chủ.  
* **Bước 2 (TCP/TLS Handshake):** Thiết lập kết nối mã hóa an toàn.  
* **Bước 3 (HTTP Request & Response):** Gửi yêu cầu lấy bệnh án; database sập nên server trả về mã **`500 Internal Server Error`**.  
* **Bước 4 (Rendering Pipeline):** Trình duyệt hiển thị giao diện thông báo lỗi hệ thống thay vì dựng cây DOM rỗng.

#### **4\. Nguyên lý bộ nhớ (Client vs Server):**

#### Tab Elements chỉ can thiệp tạm thời vào **RAM máy cá nhân (Client-side)**. Khi ấn **F5 (Reload)**, dữ liệu gốc từ **Server-side Database** sẽ tải về và ghi đè hoàn toàn, xóa sạch mọi thay đổi thủ công.

