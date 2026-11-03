### **1\. Vấn đề**

Đội ngũ kỹ sư **GreenLogistics** cần môi trường làm việc số để soi API dữ liệu GPS và chặn quảng cáo độc hại nhằm tránh làm chậm quá trình điều phối xe.

### **2\. Yêu cầu**

* **Chức năng 1:** Chọn và phân loại 5 Extensions theo 3 nhóm:  
  * *Dev Suite:* Soi JSON  
  * *Productivity:* Chấm mã màu  
  * *Security:* Chặn quảng cáo  
* **Chức năng 2:** Thiết lập chế độ **Site Access (On click)** để giới hạn quyền đọc dữ liệu nhạy cảm.

### **3\. Cách làm**

* **Phân tích vai trò JSON Viewer:** Giúp định dạng, làm đẹp (pretty-print) và cấu trúc hóa dữ liệu JSON thô từ máy chủ trả về, giúp kỹ sư dễ dàng kiểm tra, dò lỗi tọa độ GPS và phản hồi API nhanh chóng.  
* **Triển khai 5 tiện ích & Ghim Toolbar:**  
  1. Cài đặt các extension từ Chrome Web Store: *JSON Viewer*, *ColorPick Eyedropper*, *uBlock Origin*, *AdBlock*, *Privacy Badger*.  
  2. Bấm vào biểu tượng **Extensions** trên góc phải Toolbar \> Bấm biểu tượng **Ghim** cạnh tên tiện ích để hiển thị ra ngoài thanh công cụ.  
  3. Nhấp chuột phải vào từng Extension \> Chọn **Site access** \> Chọn **On click** để chỉ cấp quyền khi cần thiết.  
* **Kiểm tra tài nguyên**  
  1. Mở trình duyệt, truy cập đường dẫn: `chrome://extensions`  
  2. Bật công tắc **Developer mode** ở góc trên bên phải.  
  3. Nhấp vào mục **Task Manager** để kiểm tra mức tiêu thụ RAM/CPU thực tế của từng Extension và tiến hành tắt các extension gây quá tải.

