### **PHẦN 1: VẤN ĐỀ**

* **Bối cảnh:** Máy tính phòng khám CarePulse dùng chung cho cả bác sĩ, điều dưỡng và thực tập sinh. Dùng chung một cửa sổ Chrome mặc định gây ra xung đột phiên đăng nhập (văng tài khoản), lộ lọt lịch sử duyệt web cá nhân và rối loạn thanh bookmark, ảnh hưởng nghiêm trọng đến quy trình khám chữa bệnh.

### **PHẦN 2: YÊU CẦU**

1. Phân tích nguyên nhân sâu xa gây văng phiên (Session Conflict) do lưu chung Cookies trong thư mục `User Data`.  
2. Thiết kế Mô hình 3 Profile chuyên dụng (Tên, Mục đích, Màu Theme, Dữ liệu độc lập).  
3. Xây dựng cây thư mục Bookmark chuẩn gồm 3 thư mục chính với các dịch vụ web tương ứng.  
4. Hướng dẫn mẹo Favicon-Only và xử lý bẫy an ninh (Guest Profile vs Incognito, rủi ro Cloud Sync).

### **PHẦN 3: CÁCH LÀM (LỜI GIẢI NGẮN GỌN)**

#### **1\. Nguyên nhân văng phiên (Session Conflict):**

* Khi dùng chung 1 Profile Chrome, mọi dữ liệu xác thực (Cookies, Session Storage) của tất cả tài khoản đều ghi đè chung vào một thư mục gốc `User Data`. Khi người này đăng nhập tài khoản mới (GitHub/PTIT), Cookies cũ của người kia (CarePulse) bị ghi đè hoặc xung đột, dẫn đến việc bị văng đăng xuất ngay lập tức.

#### **2\. Mô hình 3 Profile chuyên biệt:**

* **Profile 1 (Work \- Bác sĩ chính):** Màu Theme Xanh dương đậm \| Lưu độc lập Cookies, History, Bookmarks, Extensions phục vụ khám bệnh CarePulse.  
* **Profile 2 (Personal \- Điều dưỡng/Nhân sự):** Màu Theme Xanh lá \| Phục vụ công việc phụ tá, tra cứu y lệnh, báo cáo hành chính.  
* **Profile 3 (Sandbox/Test \- Thực tập sinh):** Màu Theme Xám/Cam \| Dùng thử nghiệm, học tập, đăng nhập tài khoản cá nhân (GitHub, cổng trường) không ảnh hưởng tới hệ thống chính.

#### **3\. Cây thư mục Bookmark chuẩn & Favicon-Only:**

* **Cấu trúc thư mục (`Ctrl + Shift + O`):**  
  * 📁 `01_CarePulse_Clinic`: Trang chủ CarePulse, Tra cứu hồ sơ bệnh án, Hệ thống kê đơn thuốc điện tử.  
  * 📁 `02_Pharma_Portal`: Cổng thông tin BHYT, Tra cứu Dược thư Quốc gia, Danh mục thuốc trúng thầu.  
  * 📁 `03_Medical_Tools`: Google Dịch y tế, Tra cứu ICD-10, Công cụ tính liều lượng thuốc.  
* **Mẹo Favicon-Only:** Nhấp chuột phải vào từng Bookmark trên thanh công cụ \-\> Chọn **Chỉnh sửa (Edit)** \-\> **Xóa sạch tên** (chỉ giữ lại icon), giúp thu gọn không gian thanh công cụ gấp 3 lần, chứa được hơn 30 liên kết mà không bị tràn.

#### **4\. Xử lý Bẫy an ninh & Khách mượn máy (30 phút):**

* **Giải pháp:** Bắt buộc sử dụng **Guest Profile (Khách)** thay vì chế độ ẩn danh (Incognito).  
* **Lý do:** Chế độ ẩn danh vẫn có thể bị lưu cache/download hoặc lộ tiện ích mở rộng đang bật, trong khi Guest Profile tạo một phiên làm việc sạch tuyệt đối, tự động xóa sạch toàn bộ lịch sử và cookies ngay khi đóng cửa sổ.  
* **Cảnh báo Cloud Sync:** Tuyệt đối **không bật đăng nhập tài khoản Google cá nhân** (Cloud Sync) trên máy trạm y tế dùng chung, vì tính năng này sẽ tự động tải toàn bộ mật khẩu, lịch sử, bookmark cá nhân về máy và đồng bộ ngược dữ liệu phòng khám lên tài khoản cá nhân, gây lộ lọt thông tin bệnh nhân nghiêm trọng.

