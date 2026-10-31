### **1\. Vấn đề**

* **Thực trạng:** Kho dữ liệu video giám sát của nhóm lên tới **500GB**, trong khi ổ cứng SSD của Laptop chỉ có **256GB**.  
* **Nguy cơ:** Nếu đồng bộ toàn bộ dữ liệu trực tiếp, SSD sẽ bị tràn, gây treo phần mềm đồng bộ, làm nghẽn băng thông mạng nhà trọ và rủi ro đứt đoạn khi gập máy laptop.

### **2\. Yêu cầu**

* Thiết lập tính năng **Files On-Demand** (Tệp theo yêu cầu) để chỉ hiển thị tên file trên máy và chỉ tải dữ liệu thực tế xuống khi người dùng mở.  
* Lập báo cáo dung lượng để chứng minh tính hiệu quả khi lưu trữ lượng dữ liệu lớn trên Cloud vượt xa dung lượng ổ cứng vật lý.

### **3\. Cách làm (Giải pháp kỹ thuật)**

* **Bước 1 (Kích hoạt Files On-Demand):** Bật tính năng đồng bộ thông minh trên các nền tảng Cloud (như OneDrive, Google Drive, hoặc Nextcloud) để các file trên mây chỉ tồn tại dưới dạng tham chiếu (chữ mây/dấu tích xanh) thay vì chiếm dụng ổ cứng cục bộ.  
* **Bước 2 (Thiết lập quản lý tải lên/tải xuống):**  
  * Khi upload 500GB video lên Cloud, nên chia nhỏ khung giờ hoặc đặt giới hạn băng thông (throttling) để tránh làm nghẽn mạng nhà trọ.  
  * Thiết lập chế độ tự động giải phóng dung lượng (Free up space) sau khi xem xong video.  
* **Bước 3 (Báo cáo hiệu quả):**  
  * Dung lượng Local SSD (256GB) có thể thoải mái vận hành hệ điều hành và phần mềm.  
  * Dung lượng Cloud (500GB+) chứa toàn bộ dữ liệu video. Nhờ Files On-Demand, dung lượng tiêu tốn thực tế trên Local SSD gần như bằng 0 khi không sử dụng, giúp giải quyết hoàn toàn bài toán tràn ổ cứng.

